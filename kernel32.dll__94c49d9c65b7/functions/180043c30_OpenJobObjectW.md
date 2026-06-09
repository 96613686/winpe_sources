# OpenJobObjectW

- ea: `0x180043c30`
- end: `0x180043cf0`
- name: `OpenJobObjectW`
- size: `192`
- prototype: `HANDLE __stdcall(DWORD dwDesiredAccess, BOOL bInheritHandle, LPCWSTR lpName)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800693c0`

## callees

- `0x18000f920`
- `0x180043c30`

## import_xrefs

- `ntdll!NtOpenJobObject` at `0x180043cd2`
- `ntdll!NtOpenJobObject` at `0x180043cd2`
- `ntdll!RtlInitUnicodeString` at `0x180043c7d`
- `ntdll!RtlInitUnicodeString` at `0x180043c7d`
- `KERNELBASE!BasepAdjustObjectAttributesForPrivateNamespace` at `0x180043cc2`
- `KERNELBASE!BasepAdjustObjectAttributesForPrivateNamespace` at `0x180043cc2`
- `KERNELBASE!BaseGetNamedObjectDirectory` at `0x180043c87`
- `KERNELBASE!BaseGetNamedObjectDirectory` at `0x180043c87`

## pseudocode

```c
HANDLE __stdcall OpenJobObjectW(DWORD dwDesiredAccess, BOOL bInheritHandle, LPCWSTR lpName)
{
  __int64 v5; // rcx
  NTSTATUS NamedObjectDirectory; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *v10; // [rsp+80h] [rbp+20h] BYREF
  void *JobHandle; // [rsp+88h] [rbp+28h] BYREF

  JobHandle = 0;
  v10 = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  if ( !lpName )
  {
    v5 = 3221225485LL;
LABEL_3:
    BaseSetLastNTError(v5);
    return 0;
  }
  RtlInitUnicodeString(&DestinationString, lpName);
  NamedObjectDirectory = BaseGetNamedObjectDirectory(&v10);
  if ( NamedObjectDirectory < 0
    || (ObjectAttributes.RootDirectory = v10,
        ObjectAttributes.Length = 48,
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0,
        ObjectAttributes.Attributes = bInheritHandle ? 2 : 0,
        ObjectAttributes.ObjectName = &DestinationString,
        BasepAdjustObjectAttributesForPrivateNamespace(&ObjectAttributes),
        NamedObjectDirectory = NtOpenJobObject(&JobHandle, dwDesiredAccess, &ObjectAttributes),
        NamedObjectDirectory < 0) )
  {
    v5 = (unsigned int)NamedObjectDirectory;
    goto LABEL_3;
  }
  return JobHandle;
}

```

## disassembly

```asm
0x180043c30  mov     [rsp-8+arg_0], rbx
0x180043c35  mov     [rsp-8+arg_8], rdi
0x180043c3a  push    rbp
0x180043c3b  mov     rbp, rsp
0x180043c3e  sub     rsp, 60h
0x180043c42  xorps   xmm0, xmm0
0x180043c45  xor     eax, eax
0x180043c47  mov     [rbp+JobHandle], rax
0x180043c4b  mov     ebx, edx
0x180043c4d  mov     [rbp+arg_10], rax
0x180043c51  mov     edi, ecx
0x180043c53  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180043c57  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180043c5b  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180043c5f  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180043c63  test    r8, r8
0x180043c66  jnz     short loc_180043C76
0x180043c68  mov     ecx, 0C000000Dh
0x180043c6d  call    BaseSetLastNTError
0x180043c72  xor     eax, eax
0x180043c74  jmp     short loc_180043CE0
0x180043c76  mov     rdx, r8; SourceString
0x180043c79  lea     rcx, [rbp+DestinationString]; DestinationString
0x180043c7d  call    cs:__imp_RtlInitUnicodeString
0x180043c83  lea     rcx, [rbp+arg_10]
0x180043c87  call    cs:__imp_BaseGetNamedObjectDirectory
0x180043c8d  test    eax, eax
0x180043c8f  jns     short loc_180043C95
0x180043c91  mov     ecx, eax
0x180043c93  jmp     short loc_180043C6D
0x180043c95  mov     rax, [rbp+arg_10]
0x180043c99  lea     rcx, [rbp+ObjectAttributes]
0x180043c9d  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x180043ca1  xorps   xmm0, xmm0
0x180043ca4  neg     ebx
0x180043ca6  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180043cad  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180043cb2  sbb     eax, eax
0x180043cb4  and     eax, 2
0x180043cb7  mov     [rbp+ObjectAttributes.Attributes], eax
0x180043cba  lea     rax, [rbp+DestinationString]
0x180043cbe  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180043cc2  call    cs:__imp_BasepAdjustObjectAttributesForPrivateNamespace
0x180043cc8  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180043ccc  mov     edx, edi; DesiredAccess
0x180043cce  lea     rcx, [rbp+JobHandle]; JobHandle
0x180043cd2  call    cs:__imp_NtOpenJobObject
0x180043cd8  test    eax, eax
0x180043cda  js      short loc_180043C91
0x180043cdc  mov     rax, [rbp+JobHandle]
0x180043ce0  mov     rbx, [rsp+60h+arg_0]
0x180043ce5  mov     rdi, [rsp+60h+arg_8]
0x180043cea  add     rsp, 60h
0x180043cee  pop     rbp
0x180043cef  retn
```
