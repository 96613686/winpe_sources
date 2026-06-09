# _RegRtlCreateKeyTransacted

- ea: `0x180001490`
- end: `0x180001619`
- name: `_RegRtlCreateKeyTransacted`
- size: `393`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180001620`
- `0x180001d20`
- `0x1800026b0`
- `0x180003f50`

## callees

- `0x180001490`
- `0x1800049f0`
- `0x18007d328`

## import_xrefs

- `ntdll!NtCreateKey` at `0x180001581`
- `ntdll!NtCreateKey` at `0x180001581`
- `ntdll!NtClose` at `0x1800015be`
- `ntdll!NtClose` at `0x1800015be`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800014f4`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800014f4`

## pseudocode

```c
__int64 __fastcall RegRtlCreateKeyTransacted(
        char *a1,
        const WCHAR *a2,
        ULONG a3,
        ACCESS_MASK a4,
        void *a5,
        __int64 a6,
        PHANDLE KeyHandle,
        PULONG Disposition,
        __int64 a9)
{
  HANDLE v12; // rdi
  int inited; // ebx
  int v14; // r9d
  _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-58h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-48h] BYREF
  HANDLE Handle; // [rsp+A0h] [rbp+8h] BYREF

  Handle = 0;
  v12 = a1;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  if ( (unsigned __int64)(a1 + 0x80000000) > 7 || (inited = RegRtlOpenPredefinedKey(a1, &Handle), inited >= 0) )
  {
    inited = RtlInitUnicodeStringEx(&DestinationString, a2);
    if ( inited >= 0 )
    {
      ObjectAttributes.Length = 48;
      ObjectAttributes.SecurityQualityOfService = 0;
      ObjectAttributes.Attributes = 32 * (a3 & 8 | 6);
      if ( Handle )
        v12 = Handle;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.SecurityDescriptor = a5;
      ObjectAttributes.RootDirectory = v12;
      if ( a9 )
      {
        inited = NtCreateKeyTransacted_Stub((_DWORD)KeyHandle, a4, (unsigned int)&ObjectAttributes, v14);
        if ( inited == -1073741702 )
          inited = -1072103420;
      }
      else
      {
        inited = NtCreateKey(KeyHandle, a4, &ObjectAttributes, 0, 0, a3, Disposition);
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
0x180001490  mov     r11, rsp
0x180001493  push    rbx
0x180001494  sub     rsp, 90h
0x18000149b  mov     [r11+10h], rbp
0x18000149f  xorps   xmm0, xmm0
0x1800014a2  mov     [r11+18h], rsi
0x1800014a6  xor     eax, eax
0x1800014a8  mov     [r11+20h], rdi
0x1800014ac  lea     rax, [rcx-80000000h]
0x1800014b3  mov     [r11-10h], r14
0x1800014b7  mov     esi, r8d
0x1800014ba  mov     [r11-18h], r15
0x1800014be  mov     r14d, r9d
0x1800014c1  xor     r15d, r15d
0x1800014c4  mov     rbp, rdx
0x1800014c7  mov     [r11+8], r15
0x1800014cb  mov     rdi, rcx
0x1800014ce  movups  xmmword ptr [rsp+98h+ObjectAttributes.ObjectName], xmm0
0x1800014d3  movups  xmmword ptr [rsp+98h+ObjectAttributes.Length], xmm0
0x1800014d8  movups  xmmword ptr [rsp+98h+ObjectAttributes+1Ch], xmm0
0x1800014dd  movups  xmmword ptr [rsp+98h+DestinationString.Length], xmm0
0x1800014e2  cmp     rax, 7
0x1800014e6  jbe     loc_1800015CF
0x1800014ec  mov     rdx, rbp; SourceString
0x1800014ef  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x1800014f4  call    cs:__imp_RtlInitUnicodeStringEx
0x1800014fa  mov     ebx, eax
0x1800014fc  test    eax, eax
0x1800014fe  js      loc_180001589
0x180001504  mov     rax, [rsp+98h+Handle]
0x18000150c  lea     r8, [rsp+98h+ObjectAttributes]; ObjectAttributes
0x180001511  mov     ecx, esi
0x180001513  mov     [rsp+98h+ObjectAttributes.Length], 30h ; '0'
0x18000151b  and     ecx, 8
0x18000151e  mov     [rsp+98h+ObjectAttributes.SecurityQualityOfService], r15
0x180001523  or      ecx, 6
0x180001526  mov     edx, r14d; DesiredAccess
0x180001529  shl     ecx, 5
0x18000152c  test    rax, rax
0x18000152f  mov     [rsp+98h+ObjectAttributes.Attributes], ecx
0x180001533  mov     rcx, [rsp+98h+arg_40]
0x18000153b  cmovnz  rdi, rax
0x18000153f  lea     rax, [rsp+98h+DestinationString]
0x180001544  mov     [rsp+98h+ObjectAttributes.ObjectName], rax
0x180001549  mov     rax, [rsp+98h+arg_20]
0x180001551  mov     [rsp+98h+ObjectAttributes.SecurityDescriptor], rax
0x180001556  mov     rax, [rsp+98h+arg_38]
0x18000155e  mov     [rsp+98h+ObjectAttributes.RootDirectory], rdi
0x180001563  test    rcx, rcx
0x180001566  jnz     short loc_1800015E7
0x180001568  mov     rcx, [rsp+98h+KeyHandle]; KeyHandle
0x180001570  xor     r9d, r9d; TitleIndex
0x180001573  mov     [rsp+98h+Disposition], rax; Disposition
0x180001578  mov     [rsp+98h+CreateOptions], esi; CreateOptions
0x18000157c  mov     [rsp+98h+Class], r15; Class
0x180001581  call    cs:__imp_NtCreateKey
0x180001587  mov     ebx, eax
0x180001589  mov     rcx, [rsp+98h+Handle]; Handle
0x180001591  mov     r15, [rsp+98h+var_18]
0x180001599  mov     r14, [rsp+98h+var_10]
0x1800015a1  mov     rdi, [rsp+98h+arg_18]
0x1800015a9  mov     rsi, [rsp+98h+arg_10]
0x1800015b1  mov     rbp, [rsp+98h+arg_8]
0x1800015b9  test    rcx, rcx
0x1800015bc  jz      short loc_1800015C4
0x1800015be  call    cs:__imp_NtClose
0x1800015c4  mov     eax, ebx
0x1800015c6  add     rsp, 90h
0x1800015cd  pop     rbx
0x1800015ce  retn
0x1800015cf  lea     rdx, [rsp+98h+Handle]
0x1800015d7  call    _RegRtlOpenPredefinedKey
0x1800015dc  mov     ebx, eax
0x1800015de  test    eax, eax
0x1800015e0  js      short loc_180001589
0x1800015e2  jmp     loc_1800014EC
0x1800015e7  mov     [rsp+98h+var_60], rax
0x1800015ec  mov     [rsp+98h+Disposition], rcx
0x1800015f1  mov     rcx, [rsp+98h+KeyHandle]
0x1800015f9  mov     [rsp+98h+CreateOptions], esi
0x1800015fd  call    NtCreateKeyTransacted_Stub
0x180001602  mov     ebx, eax
0x180001604  cmp     eax, 0C000007Ah
0x180001609  jnz     loc_180001589
0x18000160f  mov     ebx, 0C0190004h
0x180001614  jmp     loc_180001589
```
