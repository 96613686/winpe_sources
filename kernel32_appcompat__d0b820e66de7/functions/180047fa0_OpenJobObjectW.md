# OpenJobObjectW

- ea: `0x180047fa0`
- end: `0x18004807c`
- name: `OpenJobObjectW`
- size: `220`
- prototype: `HANDLE __stdcall(DWORD dwDesiredAccess, BOOL bInheritHandle, LPCWSTR lpName)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180070560`

## callees

- `0x18000ccf0`
- `0x180047fa0`

## import_xrefs

- `ntdll!NtOpenJobObject` at `0x180048057`
- `ntdll!NtOpenJobObject` at `0x180048057`
- `ntdll!RtlInitUnicodeString` at `0x180047ff0`
- `ntdll!RtlInitUnicodeString` at `0x180047ff0`
- `KERNELBASE!BasepAdjustObjectAttributesForPrivateNamespace` at `0x180048041`
- `KERNELBASE!BasepAdjustObjectAttributesForPrivateNamespace` at `0x180048041`
- `KERNELBASE!BaseGetNamedObjectDirectory` at `0x180048000`
- `KERNELBASE!BaseGetNamedObjectDirectory` at `0x180048000`

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
0x180047fa0  mov     [rsp-8+arg_0], rbx
0x180047fa5  mov     [rsp-8+arg_8], rdi
0x180047faa  push    rbp
0x180047fab  mov     rbp, rsp
0x180047fae  sub     rsp, 60h
0x180047fb2  xorps   xmm0, xmm0
0x180047fb5  xor     eax, eax
0x180047fb7  mov     [rbp+JobHandle], rax
0x180047fbb  mov     ebx, edx
0x180047fbd  mov     [rbp+arg_10], rax
0x180047fc1  mov     edi, ecx
0x180047fc3  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180047fc7  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180047fcb  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180047fcf  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180047fd3  test    r8, r8
0x180047fd6  jnz     short loc_180047FE9
0x180047fd8  mov     ecx, 0C000000Dh
0x180047fdd  call    BaseSetLastNTError
0x180047fe2  xor     eax, eax
0x180047fe4  jmp     loc_18004806B
0x180047fe9  mov     rdx, r8; SourceString
0x180047fec  lea     rcx, [rbp+DestinationString]; DestinationString
0x180047ff0  call    cs:__imp_RtlInitUnicodeString
0x180047ff7  nop     dword ptr [rax+rax+00h]
0x180047ffc  lea     rcx, [rbp+arg_10]
0x180048000  call    cs:__imp_BaseGetNamedObjectDirectory
0x180048007  nop     dword ptr [rax+rax+00h]
0x18004800c  test    eax, eax
0x18004800e  jns     short loc_180048014
0x180048010  mov     ecx, eax
0x180048012  jmp     short loc_180047FDD
0x180048014  mov     rax, [rbp+arg_10]
0x180048018  lea     rcx, [rbp+ObjectAttributes]
0x18004801c  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x180048020  xorps   xmm0, xmm0
0x180048023  neg     ebx
0x180048025  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18004802c  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180048031  sbb     eax, eax
0x180048033  and     eax, 2
0x180048036  mov     [rbp+ObjectAttributes.Attributes], eax
0x180048039  lea     rax, [rbp+DestinationString]
0x18004803d  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180048041  call    cs:__imp_BasepAdjustObjectAttributesForPrivateNamespace
0x180048048  nop     dword ptr [rax+rax+00h]
0x18004804d  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180048051  mov     edx, edi; DesiredAccess
0x180048053  lea     rcx, [rbp+JobHandle]; JobHandle
0x180048057  call    cs:__imp_NtOpenJobObject
0x18004805e  nop     dword ptr [rax+rax+00h]
0x180048063  test    eax, eax
0x180048065  js      short loc_180048010
0x180048067  mov     rax, [rbp+JobHandle]
0x18004806b  mov     rbx, [rsp+60h+arg_0]
0x180048070  mov     rdi, [rsp+60h+arg_8]
0x180048075  add     rsp, 60h
0x180048079  pop     rbp
0x18004807a  retn
```
