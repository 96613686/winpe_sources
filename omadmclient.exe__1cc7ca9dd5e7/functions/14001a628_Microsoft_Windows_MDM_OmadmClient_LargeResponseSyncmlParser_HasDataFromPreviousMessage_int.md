# Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::HasDataFromPreviousMessage(int *)

- ea: `0x14001a628`
- end: `0x14001a797`
- name: `?HasDataFromPreviousMessage@LargeResponseSyncmlParser@OmadmClient@MDM@Windows@Microsoft@@QEAAJPEAH@Z`
- size: `367`
- prototype: `__int64 __fastcall(Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser *__hidden this, int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14002b464`
- `0x14002e410`

## callees

- `0x14000b0d4`
- `0x14000b0f4`
- `0x140013068`
- `0x14001a628`
- `0x14001a7a0`
- `0x140069010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a6d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a6d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001a756`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001a778`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001a756`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001a778`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x14001a722`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x14001a722`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14001a6c4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14001a6c4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::HasDataFromPreviousMessage(
        const unsigned __int16 **this,
        int *a2)
{
  int v4; // eax
  int v5; // edi
  const unsigned __int16 *v7; // rcx
  HANDLE FileW; // rax
  void *v9; // rbx
  DWORD LastError; // eax
  const char *v11; // r9
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-28h]
  DWORD dwCreationDispositiona; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  union _LARGE_INTEGER FileSize; // [rsp+50h] [rbp+8h] BYREF

  *a2 = 0;
  if ( !*this )
  {
    v4 = Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::InitializePersistFile(
           (Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser *)this,
           this[1],
           0);
    v5 = v4;
    if ( v4 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB0,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
        (const char *)(unsigned int)v4,
        dwCreationDisposition);
      return v5;
    }
  }
  v7 = this[2];
  if ( v7 )
  {
    this[2] = 0;
    (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v7 + 16LL))(v7);
  }
  FileW = CreateFileW(*this, 0x80000000, 1u, 0, 3u, 0, 0);
  v9 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError != 2 && LastError )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0xC7,
               (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
               (const char *)LastError,
               dwCreationDispositiona);
  }
  else
  {
    FileSize.QuadPart = 0;
    if ( !GetFileSizeEx(FileW, &FileSize) )
    {
      v5 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xD1,
             (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmclient\\lib\\src\\largeresponsesyncmlparser.cpp",
             v11);
      if ( v9 )
        CloseHandle(v9);
      return v5;
    }
    if ( FileSize.LowPart )
      *a2 = 1;
    if ( v9 )
      CloseHandle(v9);
  }
  return 0;
}

```

## disassembly

```asm
0x14001a628  mov     [rsp+arg_8], rbx
0x14001a62d  mov     [rsp+arg_10], rsi
0x14001a632  push    rdi
0x14001a633  sub     rsp, 40h
0x14001a637  mov     rsi, rdx
0x14001a63a  mov     rbx, rcx
0x14001a63d  mov     dword ptr [rdx], 0
0x14001a643  cmp     qword ptr [rcx], 0
0x14001a647  jnz     short loc_14001A67B
0x14001a649  xor     r8d, r8d; int
0x14001a64c  mov     rdx, [rcx+8]; unsigned __int16 *
0x14001a650  call    ?InitializePersistFile@LargeResponseSyncmlParser@OmadmClient@MDM@Windows@Microsoft@@IEAAJPEBGH@Z; Microsoft::Windows::MDM::OmadmClient::LargeResponseSyncmlParser::InitializePersistFile(ushort const *,int)
0x14001a655  mov     edi, eax
0x14001a657  test    eax, eax
0x14001a659  jns     short loc_14001A67B
0x14001a65b  mov     rcx, [rsp+48h]; this
0x14001a660  mov     r9d, eax; char *
0x14001a663  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14001a66a  mov     edx, 0B0h; void *
0x14001a66f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001a674  mov     eax, edi
0x14001a676  jmp     loc_14001A786
0x14001a67b  mov     rcx, [rbx+10h]
0x14001a67f  test    rcx, rcx
0x14001a682  jz      short loc_14001A699
0x14001a684  mov     qword ptr [rbx+10h], 0
0x14001a68c  mov     rax, [rcx]
0x14001a68f  mov     rax, [rax+10h]
0x14001a693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a698  nop
0x14001a699  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x14001a6a2  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x14001a6aa  mov     [rsp+48h+dwCreationDisposition], 3; unsigned int
0x14001a6b2  xor     r9d, r9d; lpSecurityAttributes
0x14001a6b5  lea     edi, [r9+1]
0x14001a6b9  mov     r8d, edi; dwShareMode
0x14001a6bc  mov     edx, 80000000h; dwDesiredAccess
0x14001a6c1  mov     rcx, [rbx]; lpFileName
0x14001a6c4  call    cs:__imp_CreateFileW
0x14001a6cb  nop     dword ptr [rax+rax+00h]
0x14001a6d0  mov     rbx, rax
0x14001a6d3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001a6d7  jnz     short loc_14001A711
0x14001a6d9  call    cs:__imp_GetLastError
0x14001a6e0  nop     dword ptr [rax+rax+00h]
0x14001a6e5  cmp     eax, 2
0x14001a6e8  jz      loc_14001A784
0x14001a6ee  test    eax, eax
0x14001a6f0  jz      loc_14001A784
0x14001a6f6  mov     rcx, [rsp+48h]; this
0x14001a6fb  mov     r9d, eax; char *
0x14001a6fe  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14001a705  mov     edx, 0C7h; void *
0x14001a70a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14001a70f  jmp     short loc_14001A786
0x14001a711  mov     qword ptr [rsp+48h+FileSize], 0
0x14001a71a  lea     rdx, [rsp+48h+FileSize]; lpFileSize
0x14001a71f  mov     rcx, rbx; hFile
0x14001a722  call    cs:__imp_GetFileSizeEx
0x14001a729  nop     dword ptr [rax+rax+00h]
0x14001a72e  test    eax, eax
0x14001a730  jnz     short loc_14001A767
0x14001a732  mov     rcx, [rsp+48h]; this
0x14001a737  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\dm\\omadm\\omadmclie"...
0x14001a73e  mov     edx, 0D1h; void *
0x14001a743  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14001a748  mov     edi, eax
0x14001a74a  test    rbx, rbx
0x14001a74d  jz      loc_14001A674
0x14001a753  mov     rcx, rbx; hObject
0x14001a756  call    cs:__imp_CloseHandle
0x14001a75d  nop     dword ptr [rax+rax+00h]
0x14001a762  jmp     loc_14001A674
0x14001a767  cmp     dword ptr [rsp+48h+FileSize], 0
0x14001a76c  jz      short loc_14001A770
0x14001a76e  mov     [rsi], edi
0x14001a770  test    rbx, rbx
0x14001a773  jz      short loc_14001A784
0x14001a775  mov     rcx, rbx; hObject
0x14001a778  call    cs:__imp_CloseHandle
0x14001a77f  nop     dword ptr [rax+rax+00h]
0x14001a784  xor     eax, eax
0x14001a786  mov     rbx, [rsp+48h+arg_8]
0x14001a78b  mov     rsi, [rsp+48h+arg_10]
0x14001a790  add     rsp, 40h
0x14001a794  pop     rdi
0x14001a795  retn
```
