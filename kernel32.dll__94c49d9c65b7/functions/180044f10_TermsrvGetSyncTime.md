# TermsrvGetSyncTime

- ea: `0x180044f10`
- end: `0x18004521d`
- name: `TermsrvGetSyncTime`
- size: `781`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004ddd0`

## callees

- `0x180044f10`
- `0x18007a7dd`
- `0x18007a840`

## import_xrefs

- `ntdll!RtlAppendUnicodeToString` at `0x180044ff3`
- `ntdll!RtlAppendUnicodeToString` at `0x180044ff3`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180044fd9`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180044fd9`
- `ntdll!NtWaitForSingleObject` at `0x18004515c`
- `ntdll!NtWaitForSingleObject` at `0x18004515c`
- `ntdll!NtOpenFile` at `0x18004505a`
- `ntdll!NtOpenFile` at `0x18004505a`
- `ntdll!NtClose` at `0x1800451ed`
- `ntdll!NtClose` at `0x1800451ed`
- `ntdll!wcslen` at `0x180045191`
- `ntdll!wcslen` at `0x1800451ab`
- `ntdll!wcslen` at `0x180045191`
- `ntdll!wcslen` at `0x1800451ab`
- `ntdll!NtQueryInformationFile` at `0x180045089`
- `ntdll!NtQueryInformationFile` at `0x180045089`
- `ntdll!NtFreeVirtualMemory` at `0x1800451dd`
- `ntdll!NtFreeVirtualMemory` at `0x1800451dd`
- `ntdll!NtReadFile` at `0x180045143`
- `ntdll!NtReadFile` at `0x180045143`
- `ntdll!NtAllocateVirtualMemory` at `0x1800450cd`
- `ntdll!NtAllocateVirtualMemory` at `0x1800450f9`
- `ntdll!NtAllocateVirtualMemory` at `0x1800450cd`
- `ntdll!NtAllocateVirtualMemory` at `0x1800450f9`
- `ntdll!_wcsicmp` at `0x180045184`
- `ntdll!_wcsicmp` at `0x180045184`

## pseudocode

```c
int __fastcall TermsrvGetSyncTime(__int64 a1, const UNICODE_STRING *a2, __int64 a3)
{
  int result; // eax
  NTSTATUS Status; // ebx
  NTSTATUS v8; // eax
  const wchar_t *v9; // rbx
  const wchar_t *v10; // rdi
  int v11; // eax
  size_t v12; // rax
  PVOID BaseAddress; // [rsp+50h] [rbp-B0h] BYREF
  void *FileHandle; // [rsp+58h] [rbp-A8h] BYREF
  ULONG_PTR RegionSize; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+68h] [rbp-98h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-88h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-78h] BYREF
  __int128 FileInformation; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v20; // [rsp+C8h] [rbp-38h]
  _BYTE v21[528]; // [rsp+D0h] [rbp-30h] BYREF

  FileHandle = 0;
  v20 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  FileInformation = 0;
  memset_0(v21, 0, 0x20Au);
  *(_QWORD *)&Destination.Length = 34209792;
  Destination.Buffer = (PWSTR)v21;
  BaseAddress = 0;
  RegionSize = 0;
  if ( !a1 )
    return -1073741585;
  if ( !a2 )
    return -1073741584;
  if ( !a3 )
    return -1073741583;
  result = RtlAppendUnicodeStringToString(&Destination, a2);
  if ( result >= 0 )
  {
    result = RtlAppendUnicodeToString(&Destination, L"\\inifile.upd");
    if ( result >= 0 )
    {
      ObjectAttributes.ObjectName = &Destination;
      *(_QWORD *)a3 = 0;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      IoStatusBlock.Status = 0;
      Status = NtOpenFile(&FileHandle, 0x120089u, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u);
      if ( Status >= 0 )
      {
        v8 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
        Status = v8;
        if ( v8 == -2147483643 || v8 >= 0 )
        {
          RegionSize = DWORD2(FileInformation) + 8LL;
          Status = NtAllocateVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, &BaseAddress, 0, &RegionSize, 0x2000u, 4u);
          if ( Status >= 0 )
          {
            Status = NtAllocateVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, &BaseAddress, 0, &RegionSize, 0x1000u, 4u);
            if ( Status >= 0 )
            {
              Status = NtReadFile(FileHandle, 0, 0, 0, &IoStatusBlock, BaseAddress, DWORD2(FileInformation), 0, 0);
              if ( Status == 259 )
                Status = NtWaitForSingleObject(FileHandle, 0, 0);
              if ( Status >= 0 )
              {
                Status = IoStatusBlock.Status;
                if ( IoStatusBlock.Status >= 0 )
                {
                  v9 = (const wchar_t *)BaseAddress;
                  v10 = (const wchar_t *)((char *)BaseAddress + DWORD2(FileInformation));
                  while ( v9 < v10 )
                  {
                    v11 = _wcsicmp(v9, *(const wchar_t **)(a1 + 8));
                    if ( v11 >= 0 )
                    {
                      if ( !v11 )
                      {
                        v12 = wcslen(v9);
                        *(_DWORD *)a3 = *(_DWORD *)&v9[v12 + 1];
                        *(_DWORD *)(a3 + 4) = *(_DWORD *)&v9[v12 + 3];
                      }
                      break;
                    }
                    v9 += wcslen(v9) + 5;
                  }
                  Status = IoStatusBlock.Status;
                }
              }
            }
          }
        }
      }
      if ( BaseAddress )
        NtFreeVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, &BaseAddress, &RegionSize, 0x8000u);
      if ( FileHandle )
        return NtClose(FileHandle);
      return Status;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180044f10  mov     [rsp-8+arg_18], rbx
0x180044f15  push    rbp
0x180044f16  push    rsi
0x180044f17  push    rdi
0x180044f18  push    r12
0x180044f1a  push    r14
0x180044f1c  lea     rbp, [rsp-1F0h]
0x180044f24  sub     rsp, 2F0h
0x180044f2b  mov     rax, cs:__security_cookie
0x180044f32  xor     rax, rsp
0x180044f35  mov     [rbp+210h+var_30], rax
0x180044f3c  xorps   xmm0, xmm0
0x180044f3f  mov     [rsp+310h+FileHandle], 0
0x180044f48  mov     rsi, r8
0x180044f4b  mov     rbx, rdx
0x180044f4e  mov     r14, rcx
0x180044f51  xor     eax, eax
0x180044f53  xorps   xmm1, xmm1
0x180044f56  mov     [rbp+210h+var_248], rax
0x180044f5a  movups  xmmword ptr [rbp+210h+ObjectAttributes.ObjectName], xmm0
0x180044f5e  xor     edx, edx; Val
0x180044f60  lea     rcx, [rbp+210h+var_240]; void *
0x180044f64  mov     r8d, 20Ah; Size
0x180044f6a  movups  xmmword ptr [rbp+210h+ObjectAttributes+1Ch], xmm0
0x180044f6e  movups  xmmword ptr [rbp+210h+ObjectAttributes.Length], xmm0
0x180044f72  movups  xmmword ptr [rsp+310h+IoStatusBlock], xmm0
0x180044f77  movups  [rbp+210h+FileInformation], xmm1
0x180044f7b  call    memset_0
0x180044f80  mov     qword ptr [rsp+310h+Destination.Length], 20A0000h
0x180044f89  lea     rax, [rbp+210h+var_240]
0x180044f8d  mov     [rsp+310h+Destination.Buffer], rax
0x180044f92  mov     [rsp+310h+BaseAddress], 0
0x180044f9b  mov     [rsp+310h+RegionSize], 0
0x180044fa4  test    r14, r14
0x180044fa7  jnz     short loc_180044FB3
0x180044fa9  mov     eax, 0C00000EFh
0x180044fae  jmp     loc_1800451F7
0x180044fb3  test    rbx, rbx
0x180044fb6  jnz     short loc_180044FC2
0x180044fb8  mov     eax, 0C00000F0h
0x180044fbd  jmp     loc_1800451F7
0x180044fc2  test    rsi, rsi
0x180044fc5  jnz     short loc_180044FD1
0x180044fc7  mov     eax, 0C00000F1h
0x180044fcc  jmp     loc_1800451F7
0x180044fd1  mov     rdx, rbx; Source
0x180044fd4  lea     rcx, [rsp+310h+Destination]; Destination
0x180044fd9  call    cs:__imp_RtlAppendUnicodeStringToString
0x180044fdf  test    eax, eax
0x180044fe1  js      loc_1800451F7
0x180044fe7  lea     rdx, aInifileUpd; "\\inifile.upd"
0x180044fee  lea     rcx, [rsp+310h+Destination]; Destination
0x180044ff3  call    cs:__imp_RtlAppendUnicodeToString
0x180044ff9  test    eax, eax
0x180044ffb  js      loc_1800451F7
0x180045001  lea     rax, [rsp+310h+Destination]
0x180045006  mov     [rsp+310h+OpenOptions], 20h ; ' '; OpenOptions
0x18004500e  xorps   xmm0, xmm0
0x180045011  mov     [rbp+210h+ObjectAttributes.ObjectName], rax
0x180045015  lea     r9, [rsp+310h+IoStatusBlock]; IoStatusBlock
0x18004501a  mov     qword ptr [rsi], 0
0x180045021  lea     r8, [rbp+210h+ObjectAttributes]; ObjectAttributes
0x180045025  mov     [rbp+210h+ObjectAttributes.Length], 30h ; '0'
0x18004502c  mov     edx, 120089h; DesiredAccess
0x180045031  mov     [rbp+210h+ObjectAttributes.RootDirectory], 0
0x180045039  lea     rcx, [rsp+310h+FileHandle]; FileHandle
0x18004503e  mov     [rbp+210h+ObjectAttributes.Attributes], 40h ; '@'
0x180045045  movdqu  xmmword ptr [rbp+210h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004504a  mov     dword ptr [rsp+310h+IoStatusBlock], 0
0x180045052  mov     [rsp+310h+ShareAccess], 3; ShareAccess
0x18004505a  call    cs:__imp_NtOpenFile
0x180045060  or      r12, 0FFFFFFFFFFFFFFFFh
0x180045064  mov     ebx, eax
0x180045066  test    eax, eax
0x180045068  js      loc_1800451C2
0x18004506e  mov     rcx, [rsp+310h+FileHandle]; FileHandle
0x180045073  lea     r9d, [r12+19h]; Length
0x180045078  lea     r8, [rbp+210h+FileInformation]; FileInformation
0x18004507c  mov     [rsp+310h+ShareAccess], 5; FileInformationClass
0x180045084  lea     rdx, [rsp+310h+IoStatusBlock]; IoStatusBlock
0x180045089  call    cs:__imp_NtQueryInformationFile
0x18004508f  mov     ebx, eax
0x180045091  cmp     eax, 80000005h
0x180045096  jz      short loc_1800450A0
0x180045098  test    eax, eax
0x18004509a  js      loc_1800451C2
0x1800450a0  mov     eax, dword ptr [rbp+210h+FileInformation+8]
0x1800450a3  lea     r9, [rsp+310h+RegionSize]; RegionSize
0x1800450a8  add     rax, 8
0x1800450ac  lea     rdx, [rsp+310h+BaseAddress]; BaseAddress
0x1800450b1  mov     edi, 4
0x1800450b6  mov     [rsp+310h+RegionSize], rax
0x1800450bb  mov     [rsp+310h+OpenOptions], edi; Protect
0x1800450bf  xor     r8d, r8d; ZeroBits
0x1800450c2  mov     rcx, r12; ProcessHandle
0x1800450c5  mov     [rsp+310h+ShareAccess], 2000h; AllocationType
0x1800450cd  call    cs:__imp_NtAllocateVirtualMemory
0x1800450d3  mov     ebx, eax
0x1800450d5  test    eax, eax
0x1800450d7  js      loc_1800451C2
0x1800450dd  mov     [rsp+310h+OpenOptions], edi; Protect
0x1800450e1  lea     r9, [rsp+310h+RegionSize]; RegionSize
0x1800450e6  xor     r8d, r8d; ZeroBits
0x1800450e9  mov     [rsp+310h+ShareAccess], 1000h; AllocationType
0x1800450f1  lea     rdx, [rsp+310h+BaseAddress]; BaseAddress
0x1800450f6  mov     rcx, r12; ProcessHandle
0x1800450f9  call    cs:__imp_NtAllocateVirtualMemory
0x1800450ff  mov     ebx, eax
0x180045101  test    eax, eax
0x180045103  js      loc_1800451C2
0x180045109  mov     eax, dword ptr [rbp+210h+FileInformation+8]
0x18004510c  xor     r9d, r9d; ApcContext
0x18004510f  mov     rcx, [rsp+310h+FileHandle]; FileHandle
0x180045114  xor     r8d, r8d; ApcRoutine
0x180045117  mov     [rsp+310h+Key], 0; Key
0x180045120  xor     edx, edx; Event
0x180045122  mov     [rsp+310h+ByteOffset], 0; ByteOffset
0x18004512b  mov     [rsp+310h+Length], eax; Length
0x18004512f  mov     rax, [rsp+310h+BaseAddress]
0x180045134  mov     qword ptr [rsp+310h+OpenOptions], rax; Buffer
0x180045139  lea     rax, [rsp+310h+IoStatusBlock]
0x18004513e  mov     qword ptr [rsp+310h+ShareAccess], rax; IoStatusBlock
0x180045143  call    cs:__imp_NtReadFile
0x180045149  mov     ebx, eax
0x18004514b  cmp     eax, 103h
0x180045150  jnz     short loc_180045164
0x180045152  mov     rcx, [rsp+310h+FileHandle]; Handle
0x180045157  xor     r8d, r8d; Timeout
0x18004515a  xor     edx, edx; Alertable
0x18004515c  call    cs:__imp_NtWaitForSingleObject
0x180045162  mov     ebx, eax
0x180045164  test    ebx, ebx
0x180045166  js      short loc_1800451C2
0x180045168  mov     ebx, dword ptr [rsp+310h+IoStatusBlock]
0x18004516c  test    ebx, ebx
0x18004516e  js      short loc_1800451C2
0x180045170  mov     rbx, [rsp+310h+BaseAddress]
0x180045175  mov     edi, dword ptr [rbp+210h+FileInformation+8]
0x180045178  add     rdi, rbx
0x18004517b  jmp     short loc_18004519F
0x18004517d  mov     rdx, [r14+8]; String2
0x180045181  mov     rcx, rbx; String1
0x180045184  call    cs:__imp__wcsicmp
0x18004518a  test    eax, eax
0x18004518c  jns     short loc_1800451A6
0x18004518e  mov     rcx, rbx; String
0x180045191  call    cs:__imp_wcslen
0x180045197  lea     rbx, [rbx+rax*2]
0x18004519b  add     rbx, 0Ah
0x18004519f  cmp     rbx, rdi
0x1800451a2  jb      short loc_18004517D
0x1800451a4  jmp     short loc_1800451BE
0x1800451a6  jnz     short loc_1800451BE
0x1800451a8  mov     rcx, rbx; String
0x1800451ab  call    cs:__imp_wcslen
0x1800451b1  mov     edx, [rbx+rax*2+2]
0x1800451b5  mov     [rsi], edx
0x1800451b7  mov     eax, [rbx+rax*2+6]
0x1800451bb  mov     [rsi+4], eax
0x1800451be  mov     ebx, dword ptr [rsp+310h+IoStatusBlock]
0x1800451c2  cmp     [rsp+310h+BaseAddress], 0
0x1800451c8  jz      short loc_1800451E3
0x1800451ca  mov     r9d, 8000h; FreeType
0x1800451d0  lea     r8, [rsp+310h+RegionSize]; RegionSize
0x1800451d5  lea     rdx, [rsp+310h+BaseAddress]; BaseAddress
0x1800451da  mov     rcx, r12; ProcessHandle
0x1800451dd  call    cs:__imp_NtFreeVirtualMemory
0x1800451e3  mov     rcx, [rsp+310h+FileHandle]; Handle
0x1800451e8  test    rcx, rcx
0x1800451eb  jz      short loc_1800451F5
0x1800451ed  call    cs:__imp_NtClose
0x1800451f3  mov     ebx, eax
0x1800451f5  mov     eax, ebx
0x1800451f7  mov     rcx, [rbp+210h+var_30]
0x1800451fe  xor     rcx, rsp; StackCookie
0x180045201  call    __security_check_cookie
0x180045206  mov     rbx, [rsp+310h+arg_18]
0x18004520e  add     rsp, 2F0h
0x180045215  pop     r14
0x180045217  pop     r12
0x180045219  pop     rdi
0x18004521a  pop     rsi
0x18004521b  pop     rbp
0x18004521c  retn
```
