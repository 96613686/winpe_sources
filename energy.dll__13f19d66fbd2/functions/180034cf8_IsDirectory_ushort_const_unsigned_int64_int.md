# IsDirectory(ushort const *,unsigned __int64,int *)

- ea: `0x180034cf8`
- end: `0x180034e03`
- name: `?IsDirectory@@YAKPEBG_KPEAH@Z`
- size: `267`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, unsigned __int64, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180034cb4`

## callees

- `0x180008740`
- `0x180034cf8`
- `0x180045d70`
- `0x18004ca90`
- `0x18004d8fc`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180034d97`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180034d97`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180034dc4`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180034dc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034dac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180034dac`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180034d47`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180034d47`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034d31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034dca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034d31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180034dca`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034dd8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180034dd8`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x180034d7c`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveBackslash` at `0x180034d7c`

## pseudocode

```c
__int64 __fastcall IsDirectory(const unsigned __int16 *a1, __int64 a2, DWORD *a3)
{
  HANDLE ProcessHeap; // rax
  DWORD LastError; // ebx
  unsigned __int16 *v7; // rax
  unsigned __int64 v8; // rdx
  WCHAR *v9; // rdi
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r8
  HRESULT v14; // eax
  HANDLE FirstFileW; // rcx
  HANDLE v16; // rax
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+20h] [rbp-278h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  ProcessHeap = GetProcessHeap();
  LastError = 8;
  v7 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, 0x208u);
  v9 = v7;
  if ( v7 )
  {
    v10 = StringCchCopyW(v7, v8, a1);
    LOWORD(LastError) = v10;
    if ( v10 < 0 || (v14 = PathCchRemoveBackslash(v9, 0x104u), LOWORD(LastError) = v14, v14 < 0) )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v12, v11, v13);
      LastError = (unsigned __int16)LastError;
    }
    else
    {
      FirstFileW = FindFirstFileW(v9, &FindFileData);
      if ( FirstFileW == (HANDLE)-1LL )
      {
        *a3 = 0;
        LastError = GetLastError();
      }
      else
      {
        LastError = 0;
        *a3 = (FindFileData.dwFileAttributes >> 4) & 1;
        FindClose(FirstFileW);
      }
    }
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v9);
  }
  return LastError;
}

```

## disassembly

```asm
0x180034cf8  mov     [rsp+arg_8], rbx
0x180034cfd  push    rbp
0x180034cfe  push    rsi
0x180034cff  push    rdi
0x180034d00  sub     rsp, 280h
0x180034d07  mov     rax, cs:__security_cookie
0x180034d0e  xor     rax, rsp
0x180034d11  mov     [rsp+298h+var_28], rax
0x180034d19  mov     rsi, r8
0x180034d1c  mov     rbp, rcx
0x180034d1f  mov     r8d, 250h; Size
0x180034d25  lea     rcx, [rsp+298h+FindFileData]; void *
0x180034d2a  xor     edx, edx; Val
0x180034d2c  call    memset_0
0x180034d31  call    cs:__imp_GetProcessHeap
0x180034d37  mov     ebx, 8
0x180034d3c  mov     r8d, 208h; dwBytes
0x180034d42  mov     rcx, rax; hHeap
0x180034d45  mov     edx, ebx; dwFlags
0x180034d47  call    cs:__imp_HeapAlloc
0x180034d4d  mov     rdi, rax
0x180034d50  test    rax, rax
0x180034d53  jz      loc_180034DDE
0x180034d59  mov     r8, rbp; unsigned __int16 *
0x180034d5c  mov     rcx, rax; unsigned __int16 *
0x180034d5f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180034d64  mov     ebx, eax
0x180034d66  test    eax, eax
0x180034d68  jns     short loc_180034D74
0x180034d6a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180034d6f  movzx   ebx, bx
0x180034d72  jmp     short loc_180034DCA
0x180034d74  mov     edx, 104h; cchPath
0x180034d79  mov     rcx, rdi; pszPath
0x180034d7c  call    cs:__imp_PathCchRemoveBackslash
0x180034d82  mov     ebx, eax
0x180034d84  test    eax, eax
0x180034d86  jns     short loc_180034D8F
0x180034d88  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180034d8d  jmp     short loc_180034D6F
0x180034d8f  lea     rdx, [rsp+298h+FindFileData]; lpFindFileData
0x180034d94  mov     rcx, rdi; lpFileName
0x180034d97  call    cs:__imp_FindFirstFileW
0x180034d9d  mov     rcx, rax; hFindFile
0x180034da0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180034da4  jnz     short loc_180034DB6
0x180034da6  mov     dword ptr [rsi], 0
0x180034dac  call    cs:__imp_GetLastError
0x180034db2  mov     ebx, eax
0x180034db4  jmp     short loc_180034DCA
0x180034db6  mov     eax, [rsp+298h+FindFileData.dwFileAttributes]
0x180034dba  xor     ebx, ebx
0x180034dbc  shr     eax, 4
0x180034dbf  and     eax, 1
0x180034dc2  mov     [rsi], eax
0x180034dc4  call    cs:__imp_FindClose
0x180034dca  call    cs:__imp_GetProcessHeap
0x180034dd0  mov     r8, rdi; lpMem
0x180034dd3  xor     edx, edx; dwFlags
0x180034dd5  mov     rcx, rax; hHeap
0x180034dd8  call    cs:__imp_HeapFree
0x180034dde  mov     eax, ebx
0x180034de0  mov     rcx, [rsp+298h+var_28]
0x180034de8  xor     rcx, rsp; StackCookie
0x180034deb  call    __security_check_cookie
0x180034df0  mov     rbx, [rsp+298h+arg_8]
0x180034df8  add     rsp, 280h
0x180034dff  pop     rdi
0x180034e00  pop     rsi
0x180034e01  pop     rbp
0x180034e02  retn
```
