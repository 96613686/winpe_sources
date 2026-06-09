# TermsrvGetSyncTime

- ea: `0x180049588`
- end: `0x1800498e4`
- name: `TermsrvGetSyncTime`
- size: `860`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180053ab8`

## callees

- `0x180049588`
- `0x18008275d`
- `0x1800827c0`

## import_xrefs

- `ntdll!RtlAppendUnicodeToString` at `0x180049671`
- `ntdll!RtlAppendUnicodeToString` at `0x180049671`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180049651`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180049651`
- `ntdll!NtWaitForSingleObject` at `0x1800497fe`
- `ntdll!NtWaitForSingleObject` at `0x1800497fe`
- `ntdll!NtOpenFile` at `0x1800496de`
- `ntdll!NtOpenFile` at `0x1800496de`
- `ntdll!NtClose` at `0x1800498ad`
- `ntdll!NtClose` at `0x1800498ad`
- `ntdll!wcslen` at `0x18004983f`
- `ntdll!wcslen` at `0x18004985f`
- `ntdll!wcslen` at `0x18004983f`
- `ntdll!wcslen` at `0x18004985f`
- `ntdll!NtQueryInformationFile` at `0x180049713`
- `ntdll!NtQueryInformationFile` at `0x180049713`
- `ntdll!NtFreeVirtualMemory` at `0x180049897`
- `ntdll!NtFreeVirtualMemory` at `0x180049897`
- `ntdll!NtReadFile` at `0x1800497df`
- `ntdll!NtReadFile` at `0x1800497df`
- `ntdll!NtAllocateVirtualMemory` at `0x18004975d`
- `ntdll!NtAllocateVirtualMemory` at `0x18004978f`
- `ntdll!NtAllocateVirtualMemory` at `0x18004975d`
- `ntdll!NtAllocateVirtualMemory` at `0x18004978f`
- `ntdll!_wcsicmp` at `0x18004982c`
- `ntdll!_wcsicmp` at `0x18004982c`

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
0x180049588  mov     [rsp-8+arg_18], rbx
0x18004958d  push    rbp
0x18004958e  push    rsi
0x18004958f  push    rdi
0x180049590  push    r12
0x180049592  push    r14
0x180049594  lea     rbp, [rsp-1F0h]
0x18004959c  sub     rsp, 2F0h
0x1800495a3  mov     rax, cs:__security_cookie
0x1800495aa  xor     rax, rsp
0x1800495ad  mov     [rbp+210h+var_30], rax
0x1800495b4  xorps   xmm0, xmm0
0x1800495b7  mov     [rsp+310h+FileHandle], 0
0x1800495c0  mov     rsi, r8
0x1800495c3  mov     rbx, rdx
0x1800495c6  mov     r14, rcx
0x1800495c9  xor     eax, eax
0x1800495cb  xorps   xmm1, xmm1
0x1800495ce  mov     [rbp+210h+var_248], rax
0x1800495d2  movups  xmmword ptr [rbp+210h+ObjectAttributes.ObjectName], xmm0
0x1800495d6  xor     edx, edx; Val
0x1800495d8  lea     rcx, [rbp+210h+var_240]; void *
0x1800495dc  mov     r8d, 20Ah; Size
0x1800495e2  movups  xmmword ptr [rbp+210h+ObjectAttributes+1Ch], xmm0
0x1800495e6  movups  xmmword ptr [rbp+210h+ObjectAttributes.Length], xmm0
0x1800495ea  movups  xmmword ptr [rsp+310h+IoStatusBlock], xmm0
0x1800495ef  movups  [rbp+210h+FileInformation], xmm1
0x1800495f3  call    memset_0
0x1800495f8  mov     qword ptr [rsp+310h+Destination.Length], 20A0000h
0x180049601  lea     rax, [rbp+210h+var_240]
0x180049605  mov     [rsp+310h+Destination.Buffer], rax
0x18004960a  mov     [rsp+310h+BaseAddress], 0
0x180049613  mov     [rsp+310h+RegionSize], 0
0x18004961c  test    r14, r14
0x18004961f  jnz     short loc_18004962B
0x180049621  mov     eax, 0C00000EFh
0x180049626  jmp     loc_1800498BD
0x18004962b  test    rbx, rbx
0x18004962e  jnz     short loc_18004963A
0x180049630  mov     eax, 0C00000F0h
0x180049635  jmp     loc_1800498BD
0x18004963a  test    rsi, rsi
0x18004963d  jnz     short loc_180049649
0x18004963f  mov     eax, 0C00000F1h
0x180049644  jmp     loc_1800498BD
0x180049649  mov     rdx, rbx; Source
0x18004964c  lea     rcx, [rsp+310h+Destination]; Destination
0x180049651  call    cs:__imp_RtlAppendUnicodeStringToString
0x180049658  nop     dword ptr [rax+rax+00h]
0x18004965d  test    eax, eax
0x18004965f  js      loc_1800498BD
0x180049665  lea     rdx, aInifileUpd; "\\inifile.upd"
0x18004966c  lea     rcx, [rsp+310h+Destination]; Destination
0x180049671  call    cs:__imp_RtlAppendUnicodeToString
0x180049678  nop     dword ptr [rax+rax+00h]
0x18004967d  test    eax, eax
0x18004967f  js      loc_1800498BD
0x180049685  lea     rax, [rsp+310h+Destination]
0x18004968a  mov     [rsp+310h+OpenOptions], 20h ; ' '; OpenOptions
0x180049692  xorps   xmm0, xmm0
0x180049695  mov     [rbp+210h+ObjectAttributes.ObjectName], rax
0x180049699  lea     r9, [rsp+310h+IoStatusBlock]; IoStatusBlock
0x18004969e  mov     qword ptr [rsi], 0
0x1800496a5  lea     r8, [rbp+210h+ObjectAttributes]; ObjectAttributes
0x1800496a9  mov     [rbp+210h+ObjectAttributes.Length], 30h ; '0'
0x1800496b0  mov     edx, 120089h; DesiredAccess
0x1800496b5  mov     [rbp+210h+ObjectAttributes.RootDirectory], 0
0x1800496bd  lea     rcx, [rsp+310h+FileHandle]; FileHandle
0x1800496c2  mov     [rbp+210h+ObjectAttributes.Attributes], 40h ; '@'
0x1800496c9  movdqu  xmmword ptr [rbp+210h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800496ce  mov     dword ptr [rsp+310h+IoStatusBlock], 0
0x1800496d6  mov     [rsp+310h+ShareAccess], 3; ShareAccess
0x1800496de  call    cs:__imp_NtOpenFile
0x1800496e5  nop     dword ptr [rax+rax+00h]
0x1800496ea  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800496ee  mov     ebx, eax
0x1800496f0  test    eax, eax
0x1800496f2  js      loc_18004987C
0x1800496f8  mov     rcx, [rsp+310h+FileHandle]; FileHandle
0x1800496fd  lea     r9d, [r12+19h]; Length
0x180049702  lea     r8, [rbp+210h+FileInformation]; FileInformation
0x180049706  mov     [rsp+310h+ShareAccess], 5; FileInformationClass
0x18004970e  lea     rdx, [rsp+310h+IoStatusBlock]; IoStatusBlock
0x180049713  call    cs:__imp_NtQueryInformationFile
0x18004971a  nop     dword ptr [rax+rax+00h]
0x18004971f  mov     ebx, eax
0x180049721  cmp     eax, 80000005h
0x180049726  jz      short loc_180049730
0x180049728  test    eax, eax
0x18004972a  js      loc_18004987C
0x180049730  mov     eax, dword ptr [rbp+210h+FileInformation+8]
0x180049733  lea     r9, [rsp+310h+RegionSize]; RegionSize
0x180049738  add     rax, 8
0x18004973c  lea     rdx, [rsp+310h+BaseAddress]; BaseAddress
0x180049741  mov     edi, 4
0x180049746  mov     [rsp+310h+RegionSize], rax
0x18004974b  mov     [rsp+310h+OpenOptions], edi; Protect
0x18004974f  xor     r8d, r8d; ZeroBits
0x180049752  mov     rcx, r12; ProcessHandle
0x180049755  mov     [rsp+310h+ShareAccess], 2000h; AllocationType
0x18004975d  call    cs:__imp_NtAllocateVirtualMemory
0x180049764  nop     dword ptr [rax+rax+00h]
0x180049769  mov     ebx, eax
0x18004976b  test    eax, eax
0x18004976d  js      loc_18004987C
0x180049773  mov     [rsp+310h+OpenOptions], edi; Protect
0x180049777  lea     r9, [rsp+310h+RegionSize]; RegionSize
0x18004977c  xor     r8d, r8d; ZeroBits
0x18004977f  mov     [rsp+310h+ShareAccess], 1000h; AllocationType
0x180049787  lea     rdx, [rsp+310h+BaseAddress]; BaseAddress
0x18004978c  mov     rcx, r12; ProcessHandle
0x18004978f  call    cs:__imp_NtAllocateVirtualMemory
0x180049796  nop     dword ptr [rax+rax+00h]
0x18004979b  mov     ebx, eax
0x18004979d  test    eax, eax
0x18004979f  js      loc_18004987C
0x1800497a5  mov     eax, dword ptr [rbp+210h+FileInformation+8]
0x1800497a8  xor     r9d, r9d; ApcContext
0x1800497ab  mov     rcx, [rsp+310h+FileHandle]; FileHandle
0x1800497b0  xor     r8d, r8d; ApcRoutine
0x1800497b3  mov     [rsp+310h+Key], 0; Key
0x1800497bc  xor     edx, edx; Event
0x1800497be  mov     [rsp+310h+ByteOffset], 0; ByteOffset
0x1800497c7  mov     [rsp+310h+Length], eax; Length
0x1800497cb  mov     rax, [rsp+310h+BaseAddress]
0x1800497d0  mov     qword ptr [rsp+310h+OpenOptions], rax; Buffer
0x1800497d5  lea     rax, [rsp+310h+IoStatusBlock]
0x1800497da  mov     qword ptr [rsp+310h+ShareAccess], rax; IoStatusBlock
0x1800497df  call    cs:__imp_NtReadFile
0x1800497e6  nop     dword ptr [rax+rax+00h]
0x1800497eb  mov     ebx, eax
0x1800497ed  cmp     eax, 103h
0x1800497f2  jnz     short loc_18004980C
0x1800497f4  mov     rcx, [rsp+310h+FileHandle]; Handle
0x1800497f9  xor     r8d, r8d; Timeout
0x1800497fc  xor     edx, edx; Alertable
0x1800497fe  call    cs:__imp_NtWaitForSingleObject
0x180049805  nop     dword ptr [rax+rax+00h]
0x18004980a  mov     ebx, eax
0x18004980c  test    ebx, ebx
0x18004980e  js      short loc_18004987C
0x180049810  mov     ebx, dword ptr [rsp+310h+IoStatusBlock]
0x180049814  test    ebx, ebx
0x180049816  js      short loc_18004987C
0x180049818  mov     rbx, [rsp+310h+BaseAddress]
0x18004981d  mov     edi, dword ptr [rbp+210h+FileInformation+8]
0x180049820  add     rdi, rbx
0x180049823  jmp     short loc_180049853
0x180049825  mov     rdx, [r14+8]; String2
0x180049829  mov     rcx, rbx; String1
0x18004982c  call    cs:__imp__wcsicmp
0x180049833  nop     dword ptr [rax+rax+00h]
0x180049838  test    eax, eax
0x18004983a  jns     short loc_18004985A
0x18004983c  mov     rcx, rbx; String
0x18004983f  call    cs:__imp_wcslen
0x180049846  nop     dword ptr [rax+rax+00h]
0x18004984b  lea     rbx, [rbx+rax*2]
0x18004984f  add     rbx, 0Ah
0x180049853  cmp     rbx, rdi
0x180049856  jb      short loc_180049825
0x180049858  jmp     short loc_180049878
0x18004985a  jnz     short loc_180049878
0x18004985c  mov     rcx, rbx; String
0x18004985f  call    cs:__imp_wcslen
0x180049866  nop     dword ptr [rax+rax+00h]
0x18004986b  mov     edx, [rbx+rax*2+2]
0x18004986f  mov     [rsi], edx
0x180049871  mov     eax, [rbx+rax*2+6]
0x180049875  mov     [rsi+4], eax
0x180049878  mov     ebx, dword ptr [rsp+310h+IoStatusBlock]
0x18004987c  cmp     [rsp+310h+BaseAddress], 0
0x180049882  jz      short loc_1800498A3
0x180049884  mov     r9d, 8000h; FreeType
0x18004988a  lea     r8, [rsp+310h+RegionSize]; RegionSize
0x18004988f  lea     rdx, [rsp+310h+BaseAddress]; BaseAddress
0x180049894  mov     rcx, r12; ProcessHandle
0x180049897  call    cs:__imp_NtFreeVirtualMemory
0x18004989e  nop     dword ptr [rax+rax+00h]
0x1800498a3  mov     rcx, [rsp+310h+FileHandle]; Handle
0x1800498a8  test    rcx, rcx
0x1800498ab  jz      short loc_1800498BB
0x1800498ad  call    cs:__imp_NtClose
0x1800498b4  nop     dword ptr [rax+rax+00h]
0x1800498b9  mov     ebx, eax
0x1800498bb  mov     eax, ebx
0x1800498bd  mov     rcx, [rbp+210h+var_30]
0x1800498c4  xor     rcx, rsp; StackCookie
0x1800498c7  call    __security_check_cookie
0x1800498cc  mov     rbx, [rsp+310h+arg_18]
0x1800498d4  add     rsp, 2F0h
0x1800498db  pop     r14
0x1800498dd  pop     r12
0x1800498df  pop     rdi
0x1800498e0  pop     rsi
0x1800498e1  pop     rbp
0x1800498e2  retn
```
