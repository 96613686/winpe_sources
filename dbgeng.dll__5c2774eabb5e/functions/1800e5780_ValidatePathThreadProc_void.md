# ValidatePathThreadProc(void *)

- ea: `0x1800e5780`
- end: `0x1800e5a32`
- name: `?ValidatePathThreadProc@@YAKPEAX@Z`
- size: `690`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x1800727b8`
- `0x1800e5780`
- `0x1800e5a38`
- `0x1800e5b60`
- `0x1800f13ec`
- `0x180159910`
- `0x1802ea50c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e5995`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e5995`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e59e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e5a17`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e59e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e5a17`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800e59f1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800e59f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e584e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e5932`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e584e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e5932`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1800e58c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1800e58e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1800e58c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1800e58e6`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x1800e57c6`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x1800e5a07`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x1800e5a25`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x1800e57c6`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x1800e5a07`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x1800e5a25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e59b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e59b6`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800e58d5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800e58d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800e57d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800e5839`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800e5959`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800e57d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800e5839`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800e5959`
- `dbghelp!SymGetOptions` at `0x1800e57ef`
- `dbghelp!SymGetOptions` at `0x1800e57ef`

## string_xrefs

- `0x1800e591c`: `Error: %s attempts to access '%s' failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn ValidatePathThreadProc(_QWORD *Parameter)
{
  __int64 v2; // rdi
  DWORD TickCount; // r14d
  bool AddressForUNChostName; // al
  DWORD LastError; // esi
  __int16 v6; // ax
  UINT v7; // ebx
  DWORD FileAttributesW; // r15d
  __int64 v9; // r9
  DWORD v10; // eax
  __int64 v11; // rbx
  void *v12; // rcx
  const struct std::nothrow_t *v14; // rdx
  int v15; // [rsp+30h] [rbp-10D8h] BYREF
  __int64 v16; // [rsp+38h] [rbp-10D0h]
  _QWORD *v17; // [rsp+40h] [rbp-10C8h]
  unsigned __int16 v18[2104]; // [rsp+50h] [rbp-10B8h] BYREF

  v16 = -2;
  v17 = Parameter;
  v2 = *Parameter;
  if ( !*Parameter )
    ExitThread(0xC000000D);
  TickCount = GetTickCount();
  if ( (*(_BYTE *)(v2 + 1056) & 8) == 0 || (SymGetOptions() & 0x10000000) != 0 )
    goto LABEL_11;
  v15 = 0;
  AddressForUNChostName = FindAddressForUNChostName(
                            (const unsigned __int16 *)(v2 + 1136),
                            (enum PING_STATUS_RSP_ENUM *)&v15);
  *(_DWORD *)(v2 + 1660) = v15;
  if ( !AddressForUNChostName )
  {
    *(_DWORD *)(v2 + 1076) = 0;
    *(_DWORD *)(v2 + 1072) = GetTickCount() - TickCount;
    LastError = GetLastError();
    if ( LastError )
    {
      StringCchPrintfW(v18, 0x832u, L"Error: '%s' did not respond to pings", v2 + 1136);
      PrintLastError(LastError, v18);
    }
    else
    {
      dprintf(L"Error: '%s' did not respond to pings\n", v2 + 1136);
    }
LABEL_20:
    v11 = *(_QWORD *)(v2 + 1064);
    if ( v11 && *(_DWORD *)(v11 + 1080) )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v11 + 1096));
      if ( *(_DWORD *)(v11 + 1084) )
      {
        v12 = *(void **)(v2 + 1048);
        if ( v12 )
        {
          CloseHandle(v12);
          *(_QWORD *)(v2 + 1048) = 0;
        }
      }
      if ( (*(_DWORD *)(v11 + 1080))-- == 1 )
      {
        if ( *(_DWORD *)(v11 + 1084) )
        {
          LeaveCriticalSection((LPCRITICAL_SECTION)(v11 + 1096));
          DeleteCriticalSection((LPCRITICAL_SECTION)(v11 + 1096));
          operator delete((void *)v11, v14);
          ExitThread(0);
        }
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(v11 + 1096));
    }
    ExitThread(0);
  }
  v6 = *(_WORD *)(v2 + 1056);
  if ( (v6 & 0x10) != 0 )
  {
    *(_WORD *)(v2 + 1056) = v6 | 1;
  }
  else
  {
LABEL_11:
    v7 = SetErrorMode(1u);
    FileAttributesW = GetFileAttributesW((LPCWSTR)v2);
    SetErrorMode(v7);
    if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
    {
      *(_DWORD *)(v2 + 1076) = 0;
      if ( *((_DWORD *)Parameter + 5) < 2u )
        v9 = 0;
      else
        v9 = Parameter[1];
      StringCchPrintfW(v18, 0x832u, L"Error: %s attempts to access '%s' failed", v9, v2);
      v10 = GetLastError();
      PrintLastError(v10, v18);
      goto LABEL_19;
    }
    *(_WORD *)(v2 + 1056) |= 1u;
  }
  *(_DWORD *)(v2 + 1076) = 1;
LABEL_19:
  *(_DWORD *)(v2 + 1072) = GetTickCount() - TickCount;
  goto LABEL_20;
}

```

## disassembly

```asm
0x1800e5780  push    rbx
0x1800e5782  push    rbp
0x1800e5783  push    rsi
0x1800e5784  push    rdi
0x1800e5785  push    r14
0x1800e5787  push    r15
0x1800e5789  mov     eax, 10D8h
0x1800e578e  call    _alloca_probe
0x1800e5793  sub     rsp, rax
0x1800e5796  mov     [rsp+1108h+var_10D0], 0FFFFFFFFFFFFFFFEh
0x1800e579f  mov     rax, cs:__security_cookie
0x1800e57a6  xor     rax, rsp
0x1800e57a9  mov     [rsp+1108h+var_48], rax
0x1800e57b1  mov     rsi, rcx
0x1800e57b4  mov     [rsp+1108h+var_10C8], rcx
0x1800e57b9  mov     rdi, [rcx]
0x1800e57bc  test    rdi, rdi
0x1800e57bf  jnz     short loc_1800E57D3
0x1800e57c1  mov     ecx, 0C000000Dh; dwExitCode
0x1800e57c6  call    cs:__imp_ExitThread
0x1800e57d3  call    cs:__imp_GetTickCount
0x1800e57da  nop     dword ptr [rax+rax+00h]
0x1800e57df  mov     r14d, eax
0x1800e57e2  test    byte ptr [rdi+420h], 8
0x1800e57e9  jz      loc_1800E58BD
0x1800e57ef  call    cs:__imp_SymGetOptions
0x1800e57f6  nop     dword ptr [rax+rax+00h]
0x1800e57fb  bt      eax, 1Ch
0x1800e57ff  jb      loc_1800E58BD
0x1800e5805  mov     [rsp+1108h+var_10D8], 0
0x1800e580d  lea     rbx, [rdi+470h]
0x1800e5814  lea     rdx, [rsp+1108h+var_10D8]; enum PING_STATUS_RSP_ENUM *
0x1800e5819  mov     rcx, rbx; unsigned __int16 *
0x1800e581c  call    ?FindAddressForUNChostName@@YA_NPEBGPEAW4PING_STATUS_RSP_ENUM@@@Z; FindAddressForUNChostName(ushort const *,PING_STATUS_RSP_ENUM *)
0x1800e5821  mov     ecx, [rsp+1108h+var_10D8]
0x1800e5825  mov     [rdi+67Ch], ecx
0x1800e582b  test    al, al
0x1800e582d  jnz     short loc_1800E589E
0x1800e582f  mov     dword ptr [rdi+434h], 0
0x1800e5839  call    cs:__imp_GetTickCount
0x1800e5840  nop     dword ptr [rax+rax+00h]
0x1800e5845  sub     eax, r14d
0x1800e5848  mov     [rdi+430h], eax
0x1800e584e  call    cs:__imp_GetLastError
0x1800e5855  nop     dword ptr [rax+rax+00h]
0x1800e585a  mov     esi, eax
0x1800e585c  test    eax, eax
0x1800e585e  jz      short loc_1800E588A
0x1800e5860  mov     r9, rbx
0x1800e5863  lea     r8, aErrorSDidNotRe_0; "Error: '%s' did not respond to pings"
0x1800e586a  mov     edx, 832h; unsigned __int64
0x1800e586f  lea     rcx, [rsp+1108h+var_10B8]; unsigned __int16 *
0x1800e5874  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800e5879  lea     rdx, [rsp+1108h+var_10B8]; unsigned __int16 *
0x1800e587e  mov     ecx, esi; int
0x1800e5880  call    ?PrintLastError@@YAXJPEBG@Z; PrintLastError(long,ushort const *)
0x1800e5885  jmp     loc_1800E596E
0x1800e588a  mov     rdx, rbx
0x1800e588d  lea     rcx, aErrorSDidNotRe; "Error: '%s' did not respond to pings\n"
0x1800e5894  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1800e5899  jmp     loc_1800E596E
0x1800e589e  movzx   eax, word ptr [rdi+420h]
0x1800e58a5  test    al, 10h
0x1800e58a7  jz      short loc_1800E58BD
0x1800e58a9  mov     ebp, 1
0x1800e58ae  or      ax, bp
0x1800e58b1  mov     [rdi+420h], ax
0x1800e58b8  jmp     loc_1800E5953
0x1800e58bd  mov     ebp, 1
0x1800e58c2  mov     ecx, ebp; uMode
0x1800e58c4  call    cs:__imp_SetErrorMode
0x1800e58cb  nop     dword ptr [rax+rax+00h]
0x1800e58d0  mov     ebx, eax
0x1800e58d2  mov     rcx, rdi; lpFileName
0x1800e58d5  call    cs:__imp_GetFileAttributesW
0x1800e58dc  nop     dword ptr [rax+rax+00h]
0x1800e58e1  mov     r15d, eax
0x1800e58e4  mov     ecx, ebx; uMode
0x1800e58e6  call    cs:__imp_SetErrorMode
0x1800e58ed  nop     dword ptr [rax+rax+00h]
0x1800e58f2  cmp     r15d, 0FFFFFFFFh
0x1800e58f6  jz      short loc_1800E58FE
0x1800e58f8  test    r15b, 10h
0x1800e58fc  jnz     short loc_1800E594C
0x1800e58fe  mov     dword ptr [rdi+434h], 0
0x1800e5908  cmp     dword ptr [rsi+14h], 2
0x1800e590c  jb      short loc_1800E5914
0x1800e590e  mov     r9, [rsi+8]
0x1800e5912  jmp     short loc_1800E5917
0x1800e5914  xor     r9d, r9d
0x1800e5917  mov     [rsp+1108h+var_10E8], rdi
0x1800e591c  lea     r8, aErrorSAttempts; "Error: %s attempts to access '%s' faile"...
0x1800e5923  mov     edx, 832h; unsigned __int64
0x1800e5928  lea     rcx, [rsp+1108h+var_10B8]; unsigned __int16 *
0x1800e592d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800e5932  call    cs:__imp_GetLastError
0x1800e5939  nop     dword ptr [rax+rax+00h]
0x1800e593e  mov     ecx, eax; int
0x1800e5940  lea     rdx, [rsp+1108h+var_10B8]; unsigned __int16 *
0x1800e5945  call    ?PrintLastError@@YAXJPEBG@Z; PrintLastError(long,ushort const *)
0x1800e594a  jmp     short loc_1800E5959
0x1800e594c  or      [rdi+420h], bp
0x1800e5953  mov     [rdi+434h], ebp
0x1800e5959  call    cs:__imp_GetTickCount
0x1800e5960  nop     dword ptr [rax+rax+00h]
0x1800e5965  sub     eax, r14d
0x1800e5968  mov     [rdi+430h], eax
0x1800e596e  mov     rbx, [rdi+428h]
0x1800e5975  test    rbx, rbx
0x1800e5978  jz      loc_1800E5A23
0x1800e597e  cmp     dword ptr [rbx+438h], 0
0x1800e5985  jz      loc_1800E5A23
0x1800e598b  lea     rsi, [rbx+448h]
0x1800e5992  mov     rcx, rsi; lpCriticalSection
0x1800e5995  call    cs:__imp_EnterCriticalSection
0x1800e599c  nop     dword ptr [rax+rax+00h]
0x1800e59a1  cmp     dword ptr [rbx+43Ch], 0
0x1800e59a8  jz      short loc_1800E59CD
0x1800e59aa  mov     rcx, [rdi+418h]; hObject
0x1800e59b1  test    rcx, rcx
0x1800e59b4  jz      short loc_1800E59CD
0x1800e59b6  call    cs:__imp_CloseHandle
0x1800e59bd  nop     dword ptr [rax+rax+00h]
0x1800e59c2  mov     qword ptr [rdi+418h], 0
0x1800e59cd  add     dword ptr [rbx+438h], 0FFFFFFFFh
0x1800e59d4  jnz     short loc_1800E5A14
0x1800e59d6  cmp     dword ptr [rbx+43Ch], 0
0x1800e59dd  jz      short loc_1800E5A14
0x1800e59df  mov     rcx, rsi; lpCriticalSection
0x1800e59e2  call    cs:__imp_LeaveCriticalSection
0x1800e59e9  nop     dword ptr [rax+rax+00h]
0x1800e59ee  mov     rcx, rsi; lpCriticalSection
0x1800e59f1  call    cs:__imp_DeleteCriticalSection
0x1800e59f8  nop     dword ptr [rax+rax+00h]
0x1800e59fd  mov     rcx, rbx; void *
0x1800e5a00  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800e5a05  xor     ecx, ecx; dwExitCode
0x1800e5a07  call    cs:__imp_ExitThread
0x1800e5a14  mov     rcx, rsi; lpCriticalSection
0x1800e5a17  call    cs:__imp_LeaveCriticalSection
0x1800e5a1e  nop     dword ptr [rax+rax+00h]
0x1800e5a23  xor     ecx, ecx; dwExitCode
0x1800e5a25  call    cs:__imp_ExitThread
```
