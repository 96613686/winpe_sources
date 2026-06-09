# _RegRtlOpenKeyTransacted

- ea: `0x1800045b0`
- end: `0x1800047a8`
- name: `_RegRtlOpenKeyTransacted`
- size: `504`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180002a80`
- `0x180003500`
- `0x1800037f0`
- `0x180003e40`
- `0x180003ed0`
- `0x180003f50`
- `0x1800049f0`
- `0x18007c284`
- `0x18007c368`

## callees

- `0x1800045b0`
- `0x1800049f0`
- `0x18007cce4`
- `0x18007d3e4`
- `0x18007d474`
- `0x180082010`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18000479b`
- `ntdll!NtOpenKey` at `0x18000479b`
- `ntdll!NtClose` at `0x1800046f6`
- `ntdll!NtClose` at `0x1800046f6`
- `ntdll!RtlInitUnicodeStringEx` at `0x18000461c`
- `ntdll!RtlInitUnicodeStringEx` at `0x18000461c`

## string_xrefs

- `0x180004762`: `NtOpenKeyEx`

## pseudocode

```c
__int64 __fastcall RegRtlOpenKeyTransacted(
        char *a1,
        const WCHAR *a2,
        unsigned int a3,
        ACCESS_MASK a4,
        PHANDLE KeyHandle,
        __int64 a6)
{
  HANDLE v9; // rdi
  NTSTATUS inited; // ebx
  ULONG v11; // ecx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(PHANDLE, _QWORD, struct _OBJECT_ATTRIBUTES *, _QWORD); // rax
  void **v14; // rdi
  unsigned int v16; // r9d
  PHANDLE v17; // rsi
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-58h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-48h] BYREF
  HANDLE Handle; // [rsp+90h] [rbp+8h] BYREF

  Handle = 0;
  v9 = a1;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  if ( (unsigned __int64)(a1 + 0x80000000) > 7 || (inited = RegRtlOpenPredefinedKey(a1, &Handle), inited >= 0) )
  {
    inited = RtlInitUnicodeStringEx(&DestinationString, a2);
    if ( inited >= 0 )
    {
      v11 = 64;
      if ( (a3 & 8) != 0 )
        v11 = 320;
      ObjectAttributes.Length = 48;
      ObjectAttributes.Attributes = v11;
      if ( Handle )
        v9 = Handle;
      ObjectAttributes.RootDirectory = v9;
      v12 = a6;
      ObjectAttributes.ObjectName = &DestinationString;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( a6 )
      {
        v16 = a3;
        v17 = KeyHandle;
        inited = NtOpenKeyTransactedEx_Stub((_DWORD)KeyHandle, a4, (unsigned int)&ObjectAttributes, v16, a6);
        if ( inited == -1073741702 )
        {
          inited = NtOpenKeyTransacted_Stub(v17, a4, &ObjectAttributes, v12);
          if ( inited == -1073741702 )
            inited = -1072103420;
        }
      }
      else
      {
        if ( byte_1800A4A09 )
        {
          v13 = (__int64 (__fastcall *)(PHANDLE, _QWORD, struct _OBJECT_ATTRIBUTES *, _QWORD))qword_1800A4A20;
        }
        else
        {
          if ( (int)LookupNtdllProcedureAddress("NtOpenKeyEx", (PVOID *)&qword_1800A4A20) >= 0 )
          {
            v13 = (__int64 (__fastcall *)(PHANDLE, _QWORD, struct _OBJECT_ATTRIBUTES *, _QWORD))qword_1800A4A20;
          }
          else
          {
            v13 = 0;
            qword_1800A4A20 = 0;
          }
          byte_1800A4A09 = 1;
        }
        v14 = KeyHandle;
        if ( !v13 || (inited = v13(KeyHandle, a4, &ObjectAttributes, a3), inited == -1073741702) )
          inited = NtOpenKey(v14, a4, &ObjectAttributes);
      }
    }
  }
  if ( Handle )
    NtClose(Handle);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1800045b0  mov     r11, rsp
0x1800045b3  push    rbx
0x1800045b4  sub     rsp, 80h
0x1800045bb  mov     [r11+10h], rbp
0x1800045bf  xorps   xmm0, xmm0
0x1800045c2  xor     eax, eax
0x1800045c4  mov     [r11+18h], rsi
0x1800045c8  mov     [r11-10h], rdi
0x1800045cc  mov     esi, r8d
0x1800045cf  mov     [r11+8], rax
0x1800045d3  mov     rbp, rdx
0x1800045d6  lea     rax, [rcx-80000000h]
0x1800045dd  mov     [r11-18h], r14
0x1800045e1  mov     r14d, r9d
0x1800045e4  mov     rdi, rcx
0x1800045e7  movups  xmmword ptr [rsp+88h+ObjectAttributes.ObjectName], xmm0
0x1800045ec  movups  xmmword ptr [rsp+88h+ObjectAttributes.Length], xmm0
0x1800045f1  movups  xmmword ptr [rsp+88h+ObjectAttributes+1Ch], xmm0
0x1800045f6  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x1800045fb  cmp     rax, 7
0x1800045ff  ja      short loc_180004614
0x180004601  lea     rdx, [r11+8]
0x180004605  call    _RegRtlOpenPredefinedKey
0x18000460a  mov     ebx, eax
0x18000460c  test    eax, eax
0x18000460e  js      loc_1800046C4
0x180004614  mov     rdx, rbp; SourceString
0x180004617  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x18000461c  call    cs:__imp_RtlInitUnicodeStringEx
0x180004622  mov     ebx, eax
0x180004624  test    eax, eax
0x180004626  js      loc_1800046C4
0x18000462c  mov     ecx, 40h ; '@'
0x180004631  test    sil, 8
0x180004635  jnz     loc_1800046FE
0x18000463b  mov     rax, [rsp+88h+Handle]
0x180004643  xorps   xmm0, xmm0
0x180004646  test    rax, rax
0x180004649  mov     [rsp+88h+ObjectAttributes.Length], 30h ; '0'
0x180004651  mov     [rsp+88h+ObjectAttributes.Attributes], ecx
0x180004655  cmovnz  rdi, rax
0x180004659  lea     rax, [rsp+88h+DestinationString]
0x18000465e  mov     [rsp+88h+ObjectAttributes.RootDirectory], rdi
0x180004663  mov     rdi, [rsp+88h+arg_28]
0x18000466b  mov     [rsp+88h+ObjectAttributes.ObjectName], rax
0x180004670  movdqu  xmmword ptr [rsp+88h+ObjectAttributes.SecurityDescriptor], xmm0
0x180004676  test    rdi, rdi
0x180004679  jnz     loc_180004708
0x18000467f  cmp     cs:byte_1800A4A09, dil
0x180004686  jz      loc_18000475B
0x18000468c  mov     rax, cs:qword_1800A4A20
0x180004693  mov     rdi, [rsp+88h+KeyHandle]
0x18000469b  test    rax, rax
0x18000469e  jz      loc_180004790
0x1800046a4  mov     r9d, esi
0x1800046a7  lea     r8, [rsp+88h+ObjectAttributes]
0x1800046ac  mov     edx, r14d
0x1800046af  mov     rcx, rdi
0x1800046b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046b7  mov     ebx, eax
0x1800046b9  cmp     eax, 0C000007Ah
0x1800046be  jz      loc_180004790
0x1800046c4  mov     rcx, [rsp+88h+Handle]; Handle
0x1800046cc  mov     r14, [rsp+88h+var_18]
0x1800046d1  mov     rdi, [rsp+88h+var_10]
0x1800046d6  mov     rsi, [rsp+88h+arg_10]
0x1800046de  mov     rbp, [rsp+88h+arg_8]
0x1800046e6  test    rcx, rcx
0x1800046e9  jnz     short loc_1800046F6
0x1800046eb  mov     eax, ebx
0x1800046ed  add     rsp, 80h
0x1800046f4  pop     rbx
0x1800046f5  retn
0x1800046f6  call    cs:__imp_NtClose
0x1800046fc  jmp     short loc_1800046EB
0x1800046fe  mov     ecx, 140h
0x180004703  jmp     loc_18000463B
0x180004708  mov     r9d, esi
0x18000470b  mov     [rsp+88h+var_68], rdi
0x180004710  mov     rsi, [rsp+88h+KeyHandle]
0x180004718  lea     r8, [rsp+88h+ObjectAttributes]
0x18000471d  mov     rcx, rsi
0x180004720  mov     edx, r14d
0x180004723  call    NtOpenKeyTransactedEx_Stub
0x180004728  mov     ebx, eax
0x18000472a  cmp     eax, 0C000007Ah
0x18000472f  jnz     short loc_1800046C4
0x180004731  mov     r9, rdi
0x180004734  lea     r8, [rsp+88h+ObjectAttributes]
0x180004739  mov     edx, r14d
0x18000473c  mov     rcx, rsi
0x18000473f  call    NtOpenKeyTransacted_Stub
0x180004744  mov     ebx, eax
0x180004746  cmp     eax, 0C000007Ah
0x18000474b  jnz     loc_1800046C4
0x180004751  mov     ebx, 0C0190004h
0x180004756  jmp     loc_1800046C4
0x18000475b  lea     rdx, qword_1800A4A20
0x180004762  lea     rcx, aNtopenkeyex; "NtOpenKeyEx"
0x180004769  call    _LookupNtdllProcedureAddress
0x18000476e  test    eax, eax
0x180004770  jns     short loc_18000477D
0x180004772  xor     eax, eax
0x180004774  mov     cs:qword_1800A4A20, rax
0x18000477b  jmp     short loc_180004784
0x18000477d  mov     rax, cs:qword_1800A4A20
0x180004784  mov     cs:byte_1800A4A09, 1
0x18000478b  jmp     loc_180004693
0x180004790  lea     r8, [rsp+88h+ObjectAttributes]; ObjectAttributes
0x180004795  mov     edx, r14d; DesiredAccess
0x180004798  mov     rcx, rdi; KeyHandle
0x18000479b  call    cs:__imp_NtOpenKey
0x1800047a1  mov     ebx, eax
0x1800047a3  jmp     loc_1800046C4
```
