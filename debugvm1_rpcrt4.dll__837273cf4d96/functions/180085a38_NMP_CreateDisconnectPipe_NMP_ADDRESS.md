# NMP_CreateDisconnectPipe(NMP_ADDRESS *)

- ea: `0x180085a38`
- end: `0x180085bbc`
- name: `?NMP_CreateDisconnectPipe@@YAJPEAUNMP_ADDRESS@@@Z`
- size: `388`
- prototype: `__int64 __fastcall(struct NMP_ADDRESS *)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800847b0`

## callees

- `0x180085a38`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180085b63`
- `ntdll!RtlFreeHeap` at `0x180085b63`
- `ntdll!NtCreateNamedPipeFile` at `0x180085b41`
- `ntdll!NtCreateNamedPipeFile` at `0x180085b41`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180085a8a`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180085a8a`

## pseudocode

```c
__int64 __fastcall NMP_CreateDisconnectPipe(struct NMP_ADDRESS *a1)
{
  const WCHAR *v2; // rcx
  NTSTATUS v3; // ebx
  bool v4; // cf
  __int64 result; // rax
  struct _UNICODE_STRING NtPathName; // [rsp+70h] [rbp-9h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp+7h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp+17h] BYREF
  union _LARGE_INTEGER DefaultTimeOut; // [rsp+E0h] [rbp+67h] BYREF
  void *NamedPipeFileHandle; // [rsp+E8h] [rbp+6Fh] BYREF
  PCWSTR NtFileNamePart; // [rsp+F0h] [rbp+77h] BYREF

  NamedPipeFileHandle = 0;
  *(_QWORD *)&NtPathName.Length = 0;
  v2 = (const WCHAR *)*((_QWORD *)a1 + 35);
  NtPathName.Buffer = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  NtFileNamePart = 0;
  DefaultTimeOut.QuadPart = 0;
  IoStatusBlock = 0;
  if ( RtlDosPathNameToNtPathName_U(v2, &NtPathName, &NtFileNamePart, 0) )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &NtPathName;
    ObjectAttributes.SecurityDescriptor = (PVOID)*((_QWORD *)a1 + 34);
    v4 = *((_DWORD *)a1 + 72) != 0;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.SecurityQualityOfService = 0;
    DefaultTimeOut.QuadPart = -500000;
    v3 = NtCreateNamedPipeFile(
           &NamedPipeFileHandle,
           0x100000u,
           &ObjectAttributes,
           &IoStatusBlock,
           3u,
           2u,
           0x20u,
           v4 ? 3 : 1,
           1u,
           0,
           0xFFFFFFFF,
           0x800u,
           0x800u,
           &DefaultTimeOut);
  }
  else
  {
    v3 = -1073741620;
  }
  if ( NtPathName.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
  if ( v3 < 0 )
  {
    *((_QWORD *)a1 + 33) = 0;
    if ( v3 == -1073741790 )
    {
      return 1740;
    }
    else
    {
      result = 1706;
      if ( v3 != -1073741773 && v3 != -1073741620 )
        return 14;
    }
  }
  else
  {
    *((_QWORD *)a1 + 33) = NamedPipeFileHandle;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180085a38  push    rbp
0x180085a3a  push    rbx
0x180085a3b  push    rdi
0x180085a3c  lea     rbp, [rsp-47h]
0x180085a41  sub     rsp, 0C0h
0x180085a48  xorps   xmm0, xmm0
0x180085a4b  mov     [rbp+57h+NamedPipeFileHandle], 0
0x180085a53  xor     eax, eax
0x180085a55  lea     r8, [rbp+57h+NtFileNamePart]; NtFileNamePart
0x180085a59  mov     rdi, rcx
0x180085a5c  mov     qword ptr [rbp+57h+NtPathName.Length], rax
0x180085a60  mov     rcx, [rcx+118h]; DosPathName
0x180085a67  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x180085a6b  xor     r9d, r9d; DirectoryInfo
0x180085a6e  mov     [rbp+57h+NtPathName.Buffer], rax
0x180085a72  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180085a76  mov     [rbp+57h+NtFileNamePart], rax
0x180085a7a  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180085a7e  mov     qword ptr [rbp+57h+arg_0], rax
0x180085a82  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180085a86  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180085a8a  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180085a90  test    al, al
0x180085a92  jnz     short loc_180085A9E
0x180085a94  mov     ebx, 0C00000CCh
0x180085a99  jmp     loc_180085B49
0x180085a9e  lea     rax, [rbp+57h+NtPathName]
0x180085aa2  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180085aa9  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180085aad  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180085ab1  mov     rax, [rdi+110h]
0x180085ab8  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180085abc  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rax
0x180085ac0  mov     edx, 100000h; DesiredAccess
0x180085ac5  mov     eax, [rdi+120h]
0x180085acb  neg     eax
0x180085acd  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180085ad5  lea     rax, [rbp+57h+arg_0]
0x180085ad9  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180085ae0  mov     [rsp+0D0h+DefaultTimeOut], rax; DefaultTimeOut
0x180085ae5  sbb     ecx, ecx
0x180085ae7  mov     eax, 800h
0x180085aec  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], 0
0x180085af4  mov     [rsp+0D0h+OutBufferSize], eax; OutBufferSize
0x180085af8  and     ecx, 2
0x180085afb  mov     [rsp+0D0h+InBufferSize], eax; InBufferSize
0x180085aff  inc     ecx
0x180085b01  mov     [rsp+0D0h+MaxInstances], 0FFFFFFFFh; MaxInstances
0x180085b09  mov     [rsp+0D0h+NonBlocking], 0; NonBlocking
0x180085b11  mov     [rsp+0D0h+ReadModeMessage], 1; ReadModeMessage
0x180085b19  mov     [rsp+0D0h+WriteModeMessage], ecx; WriteModeMessage
0x180085b1d  lea     rcx, [rbp+57h+NamedPipeFileHandle]; NamedPipeFileHandle
0x180085b21  mov     [rsp+0D0h+CreateOptions], 20h ; ' '; CreateOptions
0x180085b29  mov     [rsp+0D0h+CreateDisposition], 2; CreateDisposition
0x180085b31  mov     [rsp+0D0h+ShareAccess], 3; ShareAccess
0x180085b39  mov     qword ptr [rbp+57h+arg_0], 0FFFFFFFFFFF85EE0h
0x180085b41  call    cs:__imp_NtCreateNamedPipeFile
0x180085b47  mov     ebx, eax
0x180085b49  cmp     [rbp+57h+NtPathName.Buffer], 0
0x180085b4e  jz      short loc_180085B69
0x180085b50  mov     rcx, gs:60h
0x180085b59  xor     edx, edx; Flags
0x180085b5b  mov     r8, [rbp+57h+NtPathName.Buffer]; P
0x180085b5f  mov     rcx, [rcx+30h]; HeapHandle
0x180085b63  call    cs:__imp_RtlFreeHeap
0x180085b69  test    ebx, ebx
0x180085b6b  js      short loc_180085B7C
0x180085b6d  mov     rax, [rbp+57h+NamedPipeFileHandle]
0x180085b71  mov     [rdi+108h], rax
0x180085b78  xor     eax, eax
0x180085b7a  jmp     short loc_180085BB1
0x180085b7c  mov     qword ptr [rdi+108h], 0
0x180085b87  cmp     ebx, 0C0000022h
0x180085b8d  jz      short loc_180085BAC
0x180085b8f  mov     eax, 6AAh
0x180085b94  cmp     ebx, 0C0000033h
0x180085b9a  jz      short loc_180085BB1
0x180085b9c  cmp     ebx, 0C00000CCh
0x180085ba2  mov     ecx, 0Eh
0x180085ba7  cmovnz  eax, ecx
0x180085baa  jmp     short loc_180085BB1
0x180085bac  mov     eax, 6CCh
0x180085bb1  add     rsp, 0C0h
0x180085bb8  pop     rdi
0x180085bb9  pop     rbx
0x180085bba  pop     rbp
0x180085bbb  retn
```
