# _PnpCtxRegCreateKey

- ea: `0x180001d20`
- end: `0x180001f41`
- name: `_PnpCtxRegCreateKey`
- size: `545`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180003500`
- `0x1800037f0`
- `0x1800651b0`
- `0x180068888`
- `0x1800780c0`

## callees

- `0x180001490`
- `0x180001d20`
- `0x1800026b0`
- `0x1800049f0`
- `0x18007d328`

## import_xrefs

- `ntdll!NtCreateKey` at `0x180001e7a`
- `ntdll!NtCreateKey` at `0x180001e7a`
- `ntdll!NtClose` at `0x180001e90`
- `ntdll!NtClose` at `0x180001e90`
- `ntdll!RtlInitUnicodeStringEx` at `0x180001ded`
- `ntdll!RtlInitUnicodeStringEx` at `0x180001ded`

## pseudocode

```c
__int64 __fastcall PnpCtxRegCreateKey(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        __int64 a4,
        ACCESS_MASK DesiredAccess,
        PSECURITY_DESCRIPTOR a6,
        PHANDLE KeyHandle,
        PULONG Disposition)
{
  HANDLE v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rdi
  int v13; // r9d
  int inited; // r14d
  unsigned __int8 CreateOptions; // [rsp+28h] [rbp-80h]
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-58h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-48h] BYREF
  HANDLE Handle; // [rsp+B0h] [rbp+8h] BYREF

  v9 = (HANDLE)a2;
  if ( !a1 )
    return RegRtlCreateKeyTransacted(a2, a3, 0, DesiredAccess, a6);
  v10 = *(_QWORD *)(a1 + 224);
  if ( !v10 )
    return RegRtlCreateKeyTransacted(a2, a3, 0, DesiredAccess, a6);
  v11 = *(_QWORD *)(v10 + 8);
  if ( *(_BYTE *)(v10 + 16) )
    return RegRtlCreateProtectedKeyTransacted(
             a2,
             a3,
             (int)a3,
             DesiredAccess,
             a6,
             CreateOptions,
             KeyHandle,
             Disposition,
             v11);
  Handle = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  if ( (unsigned __int64)(a2 - 0x80000000LL) > 7 || (inited = RegRtlOpenPredefinedKey(a2, &Handle), inited >= 0) )
  {
    inited = RtlInitUnicodeStringEx(&DestinationString, a3);
    if ( inited >= 0 )
    {
      if ( Handle )
        v9 = Handle;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = v9;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.SecurityDescriptor = a6;
      ObjectAttributes.Attributes = 192;
      ObjectAttributes.SecurityQualityOfService = 0;
      if ( v11 )
      {
        inited = NtCreateKeyTransacted_Stub((_DWORD)KeyHandle, DesiredAccess, (unsigned int)&ObjectAttributes, v13);
        if ( inited == -1073741702 )
          inited = -1072103420;
      }
      else
      {
        inited = NtCreateKey(KeyHandle, DesiredAccess, &ObjectAttributes, 0, 0, 0, Disposition);
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
0x180001d20  mov     r11, rsp
0x180001d23  push    rbx
0x180001d24  push    rbp
0x180001d25  push    rsi
0x180001d26  sub     rsp, 90h
0x180001d2d  mov     rsi, r8
0x180001d30  mov     rbx, rdx
0x180001d33  test    rcx, rcx
0x180001d36  jz      loc_180001EA6
0x180001d3c  mov     rax, [rcx+0E0h]
0x180001d43  test    rax, rax
0x180001d46  jz      loc_180001EA6
0x180001d4c  cmp     byte ptr [rax+10h], 0
0x180001d50  mov     [r11+10h], rdi
0x180001d54  mov     rdi, [rax+8]
0x180001d58  jz      short loc_180001DA9
0x180001d5a  mov     rax, [rsp+0A8h+arg_38]
0x180001d62  mov     rdx, r8
0x180001d65  mov     r9d, [rsp+0A8h+DesiredAccess]
0x180001d6d  mov     rcx, rbx
0x180001d70  mov     [r11-68h], rdi
0x180001d74  mov     [r11-70h], rax
0x180001d78  mov     rax, [rsp+0A8h+KeyHandle]
0x180001d80  mov     [r11-78h], rax
0x180001d84  mov     rax, [rsp+0A8h+arg_28]
0x180001d8c  mov     [rsp+0A8h+Class], rax
0x180001d91  call    _RegRtlCreateProtectedKeyTransacted
0x180001d96  mov     rdi, [rsp+0A8h+arg_8]
0x180001d9e  add     rsp, 90h
0x180001da5  pop     rsi
0x180001da6  pop     rbp
0x180001da7  pop     rbx
0x180001da8  retn
0x180001da9  xorps   xmm0, xmm0
0x180001dac  mov     [rsp+0A8h+arg_10], r14
0x180001db4  xor     eax, eax
0x180001db6  xor     ebp, ebp
0x180001db8  lea     rax, [rdx-80000000h]
0x180001dbf  mov     [rsp+0A8h+Handle], rbp
0x180001dc7  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.ObjectName], xmm0
0x180001dcc  movups  xmmword ptr [rsp+0A8h+ObjectAttributes.Length], xmm0
0x180001dd1  movups  xmmword ptr [rsp+0A8h+ObjectAttributes+1Ch], xmm0
0x180001dd6  movups  xmmword ptr [rsp+0A8h+DestinationString.Length], xmm0
0x180001ddb  cmp     rax, 7
0x180001ddf  jbe     loc_180001EF5
0x180001de5  mov     rdx, rsi; SourceString
0x180001de8  lea     rcx, [rsp+0A8h+DestinationString]; DestinationString
0x180001ded  call    cs:__imp_RtlInitUnicodeStringEx
0x180001df3  mov     r14d, eax
0x180001df6  test    eax, eax
0x180001df8  js      loc_180001E83
0x180001dfe  mov     rax, [rsp+0A8h+Handle]
0x180001e06  lea     r8, [rsp+0A8h+ObjectAttributes]; ObjectAttributes
0x180001e0b  mov     edx, [rsp+0A8h+DesiredAccess]; DesiredAccess
0x180001e12  test    rax, rax
0x180001e15  mov     rcx, [rsp+0A8h+KeyHandle]; KeyHandle
0x180001e1d  cmovnz  rbx, rax
0x180001e21  mov     [rsp+0A8h+ObjectAttributes.Length], 30h ; '0'
0x180001e29  mov     [rsp+0A8h+ObjectAttributes.RootDirectory], rbx
0x180001e2e  lea     rax, [rsp+0A8h+DestinationString]
0x180001e33  mov     [rsp+0A8h+ObjectAttributes.ObjectName], rax
0x180001e38  mov     rax, [rsp+0A8h+arg_28]
0x180001e40  mov     [rsp+0A8h+ObjectAttributes.SecurityDescriptor], rax
0x180001e48  mov     rax, [rsp+0A8h+arg_38]
0x180001e50  mov     [rsp+0A8h+ObjectAttributes.Attributes], 0C0h
0x180001e58  mov     [rsp+0A8h+ObjectAttributes.SecurityQualityOfService], rbp
0x180001e60  test    rdi, rdi
0x180001e63  jnz     loc_180001F15
0x180001e69  mov     [rsp+0A8h+Disposition], rax; Disposition
0x180001e6e  xor     r9d, r9d; TitleIndex
0x180001e71  mov     dword ptr [rsp+0A8h+CreateOptions], ebp; CreateOptions
0x180001e75  mov     [rsp+0A8h+Class], rbp; Class
0x180001e7a  call    cs:__imp_NtCreateKey
0x180001e80  mov     r14d, eax
0x180001e83  mov     rcx, [rsp+0A8h+Handle]; Handle
0x180001e8b  test    rcx, rcx
0x180001e8e  jz      short loc_180001E96
0x180001e90  call    cs:__imp_NtClose
0x180001e96  mov     eax, r14d
0x180001e99  mov     r14, [rsp+0A8h+arg_10]
0x180001ea1  jmp     loc_180001D96
0x180001ea6  mov     rax, [rsp+0A8h+arg_38]
0x180001eae  xor     ebp, ebp
0x180001eb0  mov     r9d, [rsp+0A8h+DesiredAccess]
0x180001eb8  xor     r8d, r8d
0x180001ebb  mov     [rsp+0A8h+var_68], rbp
0x180001ec0  mov     rdx, rsi
0x180001ec3  mov     [rsp+0A8h+var_70], rax
0x180001ec8  mov     rcx, rbx
0x180001ecb  mov     rax, [rsp+0A8h+KeyHandle]
0x180001ed3  mov     [rsp+0A8h+Disposition], rax
0x180001ed8  mov     rax, [rsp+0A8h+arg_28]
0x180001ee0  mov     [rsp+0A8h+Class], rax
0x180001ee5  call    _RegRtlCreateKeyTransacted
0x180001eea  add     rsp, 90h
0x180001ef1  pop     rsi
0x180001ef2  pop     rbp
0x180001ef3  pop     rbx
0x180001ef4  retn
0x180001ef5  lea     rdx, [rsp+0A8h+Handle]
0x180001efd  mov     rcx, rbx
0x180001f00  call    _RegRtlOpenPredefinedKey
0x180001f05  mov     r14d, eax
0x180001f08  test    eax, eax
0x180001f0a  js      loc_180001E83
0x180001f10  jmp     loc_180001DE5
0x180001f15  mov     [rsp+0A8h+var_70], rax
0x180001f1a  mov     [rsp+0A8h+Disposition], rdi
0x180001f1f  mov     dword ptr [rsp+0A8h+CreateOptions], ebp
0x180001f23  call    NtCreateKeyTransacted_Stub
0x180001f28  mov     r14d, eax
0x180001f2b  cmp     eax, 0C000007Ah
0x180001f30  jnz     loc_180001E83
0x180001f36  mov     r14d, 0C0190004h
0x180001f3c  jmp     loc_180001E83
```
