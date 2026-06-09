# InterfaceContainer::_OpenDriver(void)

- ea: `0x180054828`
- end: `0x1800549d2`
- name: `?_OpenDriver@InterfaceContainer@@AEAAKXZ`
- size: `426`
- prototype: `__int64 __fastcall(InterfaceContainer *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800546bc`

## callees

- `0x1800540cc`
- `0x180054828`
- `0x180058570`

## import_xrefs

- `ntdll!NtCreateFile` at `0x1800548fc`
- `ntdll!NtCreateFile` at `0x1800548fc`
- `ntdll!RtlInitUnicodeString` at `0x180054885`
- `ntdll!RtlInitUnicodeString` at `0x180054885`
- `ntdll!RtlNtStatusToDosError` at `0x180054919`
- `ntdll!RtlNtStatusToDosError` at `0x180054993`
- `ntdll!RtlNtStatusToDosError` at `0x180054919`
- `ntdll!RtlNtStatusToDosError` at `0x180054993`
- `ntdll!NtDeviceIoControlFile` at `0x180054981`
- `ntdll!NtDeviceIoControlFile` at `0x180054981`
- `ntdll!NtClose` at `0x1800549a2`
- `ntdll!NtClose` at `0x1800549a2`

## pseudocode

```c
__int64 __fastcall InterfaceContainer::_OpenDriver(InterfaceContainer *this)
{
  int v1; // eax
  ULONG v2; // ebx
  int v3; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-19h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp+7h] BYREF
  _DWORD InputBuffer[4]; // [rsp+B0h] [rbp+37h] BYREF

  DestinationString = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( !`InterfaceContainer::_OpenDriver'::`2'::bStarted )
  {
    StartIpFilterDriver();
    `InterfaceContainer::_OpenDriver'::`2'::bStarted = 1;
  }
  RtlInitUnicodeString(&DestinationString, L"\\Device\\IPFILTERDRIVER");
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v1 = NtCreateFile(&icContainer, 0x100003u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 3u, 3u, 0x20u, 0, 0);
  Status = v1;
  if ( v1 >= 0 )
  {
    v2 = 0;
    InputBuffer[1] = dword_18008B588 == 0;
    InputBuffer[0] = 0;
    InputBuffer[2] = dword_18008B58C == 0;
    v3 = NtDeviceIoControlFile(icContainer, 0, 0, 0, &IoStatusBlock, 0x12805Cu, InputBuffer, 0xCu, 0, 0);
    Status = v3;
    if ( v3 < 0 )
    {
      v2 = RtlNtStatusToDosError(v3);
      NtClose(icContainer);
      icContainer = (HANDLE)-1LL;
    }
  }
  else
  {
    icContainer = (HANDLE)-1LL;
    return RtlNtStatusToDosError(v1);
  }
  return v2;
}

```

## disassembly

```asm
0x180054828  mov     [rsp-8+arg_0], rbx
0x18005482d  push    rbp
0x18005482e  lea     rbp, [rsp-57h]
0x180054833  sub     rsp, 0D0h
0x18005483a  mov     rax, cs:__security_cookie
0x180054841  xor     rax, rsp
0x180054844  mov     [rbp+57h+var_10], rax
0x180054848  cmp     cs:?bStarted@?1??_OpenDriver@InterfaceContainer@@AEAAKXZ@4HA, 0; int `InterfaceContainer::_OpenDriver(void)'::`2'::bStarted
0x18005484f  xorps   xmm0, xmm0
0x180054852  xorps   xmm1, xmm1
0x180054855  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180054859  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x18005485d  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180054861  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180054865  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180054869  jnz     short loc_18005487A
0x18005486b  call    ?StartIpFilterDriver@@YAKXZ; StartIpFilterDriver(void)
0x180054870  mov     cs:?bStarted@?1??_OpenDriver@InterfaceContainer@@AEAAKXZ@4HA, 1; int `InterfaceContainer::_OpenDriver(void)'::`2'::bStarted
0x18005487a  lea     rdx, aDeviceIpfilter; "\\Device\\IPFILTERDRIVER"
0x180054881  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180054885  call    cs:__imp_RtlInitUnicodeString
0x18005488b  mov     [rsp+0D0h+EaLength], 0; EaLength
0x180054893  lea     rax, [rbp+57h+DestinationString]
0x180054897  mov     [rsp+0D0h+EaBuffer], 0; EaBuffer
0x1800548a0  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800548a4  mov     [rsp+0D0h+CreateOptions], 20h ; ' '; CreateOptions
0x1800548ac  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800548b0  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800548b4  lea     rcx, ?icContainer@@3VInterfaceContainer@@A; FileHandle
0x1800548bb  mov     eax, 3
0x1800548c0  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800548c7  mov     [rsp+0D0h+CreateDisposition], eax; CreateDisposition
0x1800548cb  xorps   xmm0, xmm0
0x1800548ce  mov     [rsp+0D0h+ShareAccess], eax; ShareAccess
0x1800548d2  mov     edx, 100003h; DesiredAccess
0x1800548d7  mov     [rsp+0D0h+FileAttributes], 80h; FileAttributes
0x1800548df  mov     [rsp+0D0h+AllocationSize], 0; AllocationSize
0x1800548e8  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1800548f0  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800548f7  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800548fc  call    cs:__imp_NtCreateFile
0x180054902  mov     cs:Status, eax
0x180054908  test    eax, eax
0x18005490a  jns     short loc_180054926
0x18005490c  mov     ecx, eax; Status
0x18005490e  mov     cs:?icContainer@@3VInterfaceContainer@@A, 0FFFFFFFFFFFFFFFFh; InterfaceContainer icContainer
0x180054919  call    cs:__imp_RtlNtStatusToDosError
0x18005491f  mov     ebx, eax
0x180054921  jmp     loc_1800549B3
0x180054926  mov     rcx, cs:?icContainer@@3VInterfaceContainer@@A; FileHandle
0x18005492d  xor     eax, eax
0x18005492f  xor     ebx, ebx
0x180054931  cmp     cs:dword_18008B588, eax
0x180054937  mov     dword ptr [rsp+0D0h+EaBuffer], ebx; OutputBufferLength
0x18005493b  setz    al
0x18005493e  mov     qword ptr [rsp+0D0h+CreateOptions], rbx; OutputBuffer
0x180054943  mov     [rbp+57h+var_1C], eax
0x180054946  xor     eax, eax
0x180054948  cmp     cs:dword_18008B58C, eax
0x18005494e  mov     [rsp+0D0h+CreateDisposition], 0Ch; InputBufferLength
0x180054956  setz    al
0x180054959  mov     [rbp+57h+InputBuffer], ebx
0x18005495c  mov     [rbp+57h+var_18], eax
0x18005495f  xor     r9d, r9d; ApcContext
0x180054962  lea     rax, [rbp+57h+InputBuffer]
0x180054966  xor     r8d, r8d; ApcRoutine
0x180054969  mov     qword ptr [rsp+0D0h+ShareAccess], rax; InputBuffer
0x18005496e  xor     edx, edx; Event
0x180054970  lea     rax, [rbp+57h+IoStatusBlock]
0x180054974  mov     [rsp+0D0h+FileAttributes], 12805Ch; IoControlCode
0x18005497c  mov     [rsp+0D0h+AllocationSize], rax; IoStatusBlock
0x180054981  call    cs:__imp_NtDeviceIoControlFile
0x180054987  mov     cs:Status, eax
0x18005498d  test    eax, eax
0x18005498f  jns     short loc_1800549B3
0x180054991  mov     ecx, eax; Status
0x180054993  call    cs:__imp_RtlNtStatusToDosError
0x180054999  mov     rcx, cs:?icContainer@@3VInterfaceContainer@@A; Handle
0x1800549a0  mov     ebx, eax
0x1800549a2  call    cs:__imp_NtClose
0x1800549a8  mov     cs:?icContainer@@3VInterfaceContainer@@A, 0FFFFFFFFFFFFFFFFh; InterfaceContainer icContainer
0x1800549b3  mov     eax, ebx
0x1800549b5  mov     rcx, [rbp+57h+var_10]
0x1800549b9  xor     rcx, rsp; StackCookie
0x1800549bc  call    __security_check_cookie
0x1800549c1  mov     rbx, [rsp+0D0h+arg_0]
0x1800549c9  add     rsp, 0D0h
0x1800549d0  pop     rbp
0x1800549d1  retn
```
