# CLanStatEngine::HrGetNewNdisLinkState(_NDIS_LINK_STATE &)

- ea: `0x1800536f8`
- end: `0x180053883`
- name: `?HrGetNewNdisLinkState@CLanStatEngine@@IEAAJAEAU_NDIS_LINK_STATE@@@Z`
- size: `395`
- prototype: `__int64 __fastcall(CLanStatEngine *this, struct _NDIS_LINK_STATE *)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180053890`

## callees

- `0x18001a19c`
- `0x18001e1e0`
- `0x180022274`
- `0x180022294`
- `0x180052338`
- `0x1800536f8`
- `0x1800550bc`
- `0x1800550e0`

## import_xrefs

- `ntdll!NtOpenFile` at `0x180053773`
- `ntdll!NtOpenFile` at `0x180053773`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800537cf`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800537cf`

## string_xrefs

- `0x1800537dd`: `net\config\shell\statmon\smlan.cpp`
- `0x180053801`: `net\config\shell\statmon\smlan.cpp`

## pseudocode

```c
__int64 __fastcall CLanStatEngine::HrGetNewNdisLinkState(CLanStatEngine *this, struct _NDIS_LINK_STATE *a2)
{
  NTSTATUS v3; // eax
  void *v4; // rdx
  unsigned int v5; // r8d
  int LastError; // eax
  const char *v7; // r9
  unsigned int v8; // ebx
  __int64 v9; // rdx
  unsigned int v10; // eax
  void *v11; // rdx
  unsigned int v12; // r8d
  int ShareAccess; // [rsp+20h] [rbp-59h]
  unsigned int ShareAccessa; // [rsp+20h] [rbp-59h]
  DWORD BytesReturned; // [rsp+40h] [rbp-39h] BYREF
  int InBuffer; // [rsp+44h] [rbp-35h] BYREF
  void *FileHandle; // [rsp+48h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp+7h] BYREF
  _DWORD OutBuffer[2]; // [rsp+90h] [rbp+17h] BYREF
  _BYTE Source[48]; // [rsp+98h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  ObjectAttributes.ObjectName = (PUNICODE_STRING)((char *)this + 264);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  FileHandle = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  IoStatusBlock = 0;
  v3 = NtOpenFile(&FileHandle, 0x12019Fu, &ObjectAttributes, &IoStatusBlock, 7u, 0x20u);
  if ( v3 >= 0 )
  {
    InBuffer = 66055;
    BytesReturned = 0;
    if ( DeviceIoControl(FileHandle, 0x17003Eu, &InBuffer, 4u, OutBuffer, 0x34u, &BytesReturned, 0) )
    {
      if ( BytesReturned <= 0x34 )
      {
        if ( OutBuffer[0] == 66055 )
        {
          if ( OutBuffer[1] == 40 )
          {
            v10 = memcpy_s(a2, 0x28u, Source, 0x28u);
            if ( !v10 )
            {
              v8 = 0;
              goto LABEL_16;
            }
            LastError = wil::details::in1diag3::Return_Win32(retaddr, v11, v12, (const char *)v10, ShareAccessa);
            goto LABEL_5;
          }
          v9 = 281;
        }
        else
        {
          v9 = 280;
        }
      }
      else
      {
        v9 = 277;
      }
      v8 = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"net\\config\\shell\\statmon\\smlan.cpp",
        (const char *)0x8000FFFFLL,
        ShareAccessa);
      goto LABEL_16;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x112,
                  (unsigned int)"net\\config\\shell\\statmon\\smlan.cpp",
                  v7);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_NtStatus(retaddr, v4, v5, (const char *)(unsigned int)v3, ShareAccess);
  }
LABEL_5:
  v8 = LastError;
LABEL_16:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileHandle);
  return v8;
}

```

## disassembly

```asm
0x1800536f8  mov     [rsp-8+arg_10], rbx
0x1800536fd  push    rbp
0x1800536fe  lea     rbp, [rsp-57h]
0x180053703  sub     rsp, 0D0h
0x18005370a  mov     rax, cs:__security_cookie
0x180053711  xor     rax, rsp
0x180053714  mov     [rbp+57h+var_8], rax
0x180053718  lea     rax, [rcx+108h]
0x18005371f  mov     [rsp+0D0h+OpenOptions], 20h ; ' '; OpenOptions
0x180053727  xorps   xmm0, xmm0
0x18005372a  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18005372e  mov     rbx, rdx
0x180053731  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180053739  mov     edx, 12019Fh; DesiredAccess
0x18005373e  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180053746  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18005374a  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180053752  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180053756  mov     [rbp+57h+FileHandle], 0
0x18005375e  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180053762  mov     [rsp+0D0h+ShareAccess], 7; int
0x18005376a  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005376f  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180053773  call    cs:__imp_NtOpenFile
0x180053779  test    eax, eax
0x18005377b  jns     short loc_18005378B
0x18005377d  mov     rcx, [rbp+5Fh]; this
0x180053781  mov     r9d, eax; char *
0x180053784  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180053789  jmp     short loc_1800537EE
0x18005378b  mov     rcx, [rbp+57h+FileHandle]; hDevice
0x18005378f  lea     rax, [rbp+57h+BytesReturned]
0x180053793  mov     [rsp+0D0h+lpOverlapped], 0; lpOverlapped
0x18005379c  lea     r8, [rbp+57h+InBuffer]; lpInBuffer
0x1800537a0  mov     [rsp+0D0h+lpBytesReturned], rax; lpBytesReturned
0x1800537a5  mov     r9d, 4; nInBufferSize
0x1800537ab  lea     rax, [rbp+57h+OutBuffer]
0x1800537af  mov     [rsp+0D0h+OpenOptions], 34h ; '4'; nOutBufferSize
0x1800537b7  mov     edx, 17003Eh; dwIoControlCode
0x1800537bc  mov     qword ptr [rsp+0D0h+ShareAccess], rax; unsigned int
0x1800537c1  mov     [rbp+57h+InBuffer], 10207h
0x1800537c8  mov     [rbp+57h+BytesReturned], 0
0x1800537cf  call    cs:__imp_DeviceIoControl
0x1800537d5  test    eax, eax
0x1800537d7  jnz     short loc_1800537F2
0x1800537d9  mov     rcx, [rbp+5Fh]; this
0x1800537dd  lea     r8, aNetConfigShell_0; "net\\config\\shell\\statmon\\smlan.cpp"
0x1800537e4  mov     edx, 112h; void *
0x1800537e9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800537ee  mov     ebx, eax
0x1800537f0  jmp     short loc_18005385B
0x1800537f2  cmp     [rbp+57h+BytesReturned], 34h ; '4'
0x1800537f6  jbe     short loc_180053817
0x1800537f8  mov     edx, 115h; void *
0x1800537fd  mov     rcx, [rbp+5Fh]; this
0x180053801  lea     r8, aNetConfigShell_0; "net\\config\\shell\\statmon\\smlan.cpp"
0x180053808  mov     ebx, 8000FFFFh
0x18005380d  mov     r9d, ebx; char *
0x180053810  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053815  jmp     short loc_18005385B
0x180053817  cmp     [rbp+57h+OutBuffer], 10207h
0x18005381e  jz      short loc_180053827
0x180053820  mov     edx, 118h
0x180053825  jmp     short loc_1800537FD
0x180053827  mov     edx, 28h ; '('; DestinationSize
0x18005382c  cmp     [rbp+57h+var_3C], edx
0x18005382f  jz      short loc_180053838
0x180053831  mov     edx, 119h
0x180053836  jmp     short loc_1800537FD
0x180053838  mov     r9, rdx; SourceSize
0x18005383b  lea     r8, [rbp+57h+Source]; Source
0x18005383f  mov     rcx, rbx; Destination
0x180053842  call    memcpy_s
0x180053847  test    eax, eax
0x180053849  jz      short loc_180053859
0x18005384b  mov     rcx, [rbp+5Fh]; this
0x18005384f  mov     r9d, eax; char *
0x180053852  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180053857  jmp     short loc_1800537EE
0x180053859  xor     ebx, ebx
0x18005385b  lea     rcx, [rbp+57h+FileHandle]
0x18005385f  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180053864  mov     eax, ebx
0x180053866  mov     rcx, [rbp+57h+var_8]
0x18005386a  xor     rcx, rsp; StackCookie
0x18005386d  call    __security_check_cookie
0x180053872  mov     rbx, [rsp+0D0h+arg_10]
0x18005387a  add     rsp, 0D0h
0x180053881  pop     rbp
0x180053882  retn
```
