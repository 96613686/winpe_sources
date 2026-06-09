# SharedMemory::OpenSharedMemory(wchar_t const *)

- ea: `0x18000e55c`
- end: `0x18000e61b`
- name: `?OpenSharedMemory@SharedMemory@@QEAAHPEB_W@Z`
- size: `191`
- prototype: `__int64 __fastcall(SharedMemory *this, const wchar_t *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000da9c`

## callees

- `0x18000c84c`
- `0x18000e55c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e57b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e5d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e57b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e5d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e601`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e601`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18000e56d`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18000e56d`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000e5c2`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000e5c2`

## string_xrefs

- `0x18000e590`: `[UtilCommon] MSSCNTRS: Cannot open shared memory.  Error in OpenFileMappingW. 0x%08x`
- `0x18000e59c`: `"onecoreuap\\base\\appmodel\\search\\common\\pkmcntrs\\pkmcntrs.cxx"`
- `0x18000e5f2`: `"onecoreuap\\base\\appmodel\\search\\common\\pkmcntrs\\pkmcntrs.cxx"`
- `0x18000e5e6`: `[UtilCommon] MSSCNTRS: Cannot open shared memory.  Error in MapViewOfFile. 0x%08x`

## pseudocode

```c
__int64 __fastcall SharedMemory::OpenSharedMemory(SharedMemory *this, const wchar_t *a2)
{
  HANDLE v3; // rax
  signed int LastError; // eax
  LPVOID v6; // rax
  signed int v7; // eax

  v3 = OpenFileMappingW(4u, 0, a2);
  *(_QWORD *)this = v3;
  if ( !v3 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    SearchIndexerTrace::Error(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\pkmcntrs\\\\pkmcntrs.cxx\"",
      (const wchar_t *)0x46,
      (unsigned int)L"[UtilCommon] MSSCNTRS: Cannot open shared memory.  Error in OpenFileMappingW. 0x%08x",
      (const wchar_t *)(unsigned int)LastError);
    return 0;
  }
  v6 = MapViewOfFile(v3, 4u, 0, 0, 0);
  *((_QWORD *)this + 1) = v6;
  if ( !v6 )
  {
    v7 = GetLastError();
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    SearchIndexerTrace::Error(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\pkmcntrs\\\\pkmcntrs.cxx\"",
      (const wchar_t *)0x4F,
      (unsigned int)L"[UtilCommon] MSSCNTRS: Cannot open shared memory.  Error in MapViewOfFile. 0x%08x",
      (const wchar_t *)(unsigned int)v7);
    CloseHandle(*(HANDLE *)this);
    *(_QWORD *)this = 0;
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18000e55c  push    rbx
0x18000e55e  sub     rsp, 30h
0x18000e562  mov     r8, rdx; lpName
0x18000e565  mov     rbx, rcx
0x18000e568  xor     edx, edx; bInheritHandle
0x18000e56a  lea     ecx, [rdx+4]; dwDesiredAccess
0x18000e56d  call    cs:__imp_OpenFileMappingW
0x18000e573  mov     [rbx], rax
0x18000e576  test    rax, rax
0x18000e579  jnz     short loc_18000E5AC
0x18000e57b  call    cs:__imp_GetLastError
0x18000e581  test    eax, eax
0x18000e583  jle     short loc_18000E58D
0x18000e585  movzx   eax, ax
0x18000e588  or      eax, 80070000h
0x18000e58d  mov     r9d, eax; wchar_t *
0x18000e590  lea     r8, aUtilcommonMssc_4; "[UtilCommon] MSSCNTRS: Cannot open shar"...
0x18000e597  mov     edx, 46h ; 'F'; wchar_t *
0x18000e59c  lea     rcx, aOnecoreuapBase_1; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18000e5a3  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x18000e5a8  xor     eax, eax
0x18000e5aa  jmp     short loc_18000E615
0x18000e5ac  xor     r9d, r9d; dwFileOffsetLow
0x18000e5af  mov     [rsp+38h+dwNumberOfBytesToMap], 0; dwNumberOfBytesToMap
0x18000e5b8  xor     r8d, r8d; dwFileOffsetHigh
0x18000e5bb  mov     rcx, rax; hFileMappingObject
0x18000e5be  lea     edx, [r9+4]; dwDesiredAccess
0x18000e5c2  call    cs:__imp_MapViewOfFile
0x18000e5c8  mov     [rbx+8], rax
0x18000e5cc  test    rax, rax
0x18000e5cf  jnz     short loc_18000E610
0x18000e5d1  call    cs:__imp_GetLastError
0x18000e5d7  test    eax, eax
0x18000e5d9  jle     short loc_18000E5E3
0x18000e5db  movzx   eax, ax
0x18000e5de  or      eax, 80070000h
0x18000e5e3  mov     r9d, eax; wchar_t *
0x18000e5e6  lea     r8, aUtilcommonMssc_13; "[UtilCommon] MSSCNTRS: Cannot open shar"...
0x18000e5ed  mov     edx, 4Fh ; 'O'; wchar_t *
0x18000e5f2  lea     rcx, aOnecoreuapBase_1; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18000e5f9  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x18000e5fe  mov     rcx, [rbx]; hObject
0x18000e601  call    cs:__imp_CloseHandle
0x18000e607  mov     qword ptr [rbx], 0
0x18000e60e  jmp     short loc_18000E5A8
0x18000e610  mov     eax, 1
0x18000e615  add     rsp, 30h
0x18000e619  pop     rbx
0x18000e61a  retn
```
