# InitStatistics(tagDBC *,ushort const *)

- ea: `0x100535024`
- end: `0x100535187`
- name: `?InitStatistics@@YAFPEAUtagDBC@@PEBG@Z`
- size: `355`
- prototype: `__int16(struct tagDBC *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1004e8a74`
- `0x100530c14`

## callees

- `0x1005212b4`
- `0x100535024`
- `0x100535190`
- `0x10053589c`
- `0x100535a24`
- `0x100546a7c`
- `0x100546f80`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x1005350bd`
- `KERNEL32!CreateFileW` at `0x1005350bd`
- `KERNEL32!CloseHandle` at `0x100535111`
- `KERNEL32!CloseHandle` at `0x100535111`
- `KERNEL32!SetFilePointer` at `0x10053512b`
- `KERNEL32!SetFilePointer` at `0x10053512b`

## pseudocode

```c
__int64 __fastcall InitStatistics(struct tagDBC *a1, const unsigned __int16 *a2)
{
  unsigned __int16 inited; // bx
  HANDLE FileW; // rax

  inited = 0;
  (*(void (__fastcall **)(char *))(*((_QWORD *)g_csSQLPerf + 4) + 8LL))((char *)g_csSQLPerf + 32);
  if ( !g_fPerfStatLogEnabled )
  {
    if ( a2 )
      SQLGetPrivateProfileStringW(a2, L"StatsLogFile", &g_szDefPerfDataFile, &g_szPerfDataFile, 261, L"ODBC.INI");
    FileW = CreateFileW(&g_szPerfDataFile, 0x40000000u, 1u, 0, 4u, 0x80u, 0);
    g_hPerfDataFile = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      inited = -1;
      if ( (bidGblFlags & 2) != 0 )
        bidTraceMark(0, 219145);
    }
    else
    {
      PrintStatisticsHdr(FileW);
      inited = InitTimer(a1);
      if ( (inited & 0xFFFE) != 0 )
      {
        CloseHandle(g_hPerfDataFile);
        g_hPerfDataFile = (HANDLE)-1LL;
      }
      else
      {
        SetFilePointer(g_hPerfDataFile, 0, 0, 2u);
        g_fPerfStatLogEnabled = 1;
        ResetStatistics();
      }
    }
  }
  (*(void (__fastcall **)(char *))(*((_QWORD *)g_csSQLPerf + 4) + 24LL))((char *)g_csSQLPerf + 32);
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned __int16)_bidx_SNACOdbc_ErrCode(0, 0x3A409u, inited);
  return inited;
}

```

## disassembly

```asm
0x100535024  mov     [rsp+arg_0], rbx
0x100535029  mov     [rsp+arg_8], rsi
0x10053502e  push    rdi
0x10053502f  sub     rsp, 40h
0x100535033  mov     rsi, rcx
0x100535036  mov     rdi, rdx
0x100535039  mov     rcx, cs:?g_csSQLPerf@@3PEAVCCriticalSection@@EA; CCriticalSection * g_csSQLPerf
0x100535040  xor     ebx, ebx
0x100535042  add     rcx, 20h ; ' '
0x100535046  mov     rax, [rcx]
0x100535049  mov     rax, [rax+8]
0x10053504d  call    cs:__guard_dispatch_icall_fptr
0x100535053  cmp     cs:?g_fPerfStatLogEnabled@@3HA, ebx; int g_fPerfStatLogEnabled
0x100535059  jnz     loc_100535140
0x10053505f  test    rdi, rdi
0x100535062  jz      short loc_100535095
0x100535064  lea     rax, szFilename; "ODBC.INI"
0x10053506b  mov     rcx, rdi; lpszSection
0x10053506e  mov     [rsp+48h+lpszFilename], rax; lpszFilename
0x100535073  lea     r9, ?g_szPerfDataFile@@3PAGA; lpszRetBuffer
0x10053507a  lea     r8, ?g_szDefPerfDataFile@@3PAGA; lpszDefault
0x100535081  mov     [rsp+48h+cchRetBuffer], 105h; cchRetBuffer
0x100535089  lea     rdx, aStatslogfile; "StatsLogFile"
0x100535090  call    SQLGetPrivateProfileStringW
0x100535095  xor     r9d, r9d; lpSecurityAttributes
0x100535098  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x10053509d  mov     dword ptr [rsp+48h+lpszFilename], 80h; dwFlagsAndAttributes
0x1005350a5  lea     rcx, ?g_szPerfDataFile@@3PAGA; lpFileName
0x1005350ac  mov     edx, 40000000h; dwDesiredAccess
0x1005350b1  mov     [rsp+48h+cchRetBuffer], 4; dwCreationDisposition
0x1005350b9  lea     r8d, [r9+1]; dwShareMode
0x1005350bd  call    cs:__imp_CreateFileW
0x1005350c3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1005350c7  mov     cs:?g_hPerfDataFile@@3PEAXEA, rax; void * g_hPerfDataFile
0x1005350ce  cmp     rax, rdi
0x1005350d1  jnz     short loc_1005350ED
0x1005350d3  test    byte ptr cs:_bidGblFlags, 2
0x1005350da  movzx   ebx, di
0x1005350dd  jz      short loc_100535140
0x1005350df  mov     edx, 35809h
0x1005350e4  xor     ecx, ecx
0x1005350e6  call    _bidTraceMark
0x1005350eb  jmp     short loc_100535140
0x1005350ed  mov     rcx, rax; void *
0x1005350f0  call    ?PrintStatisticsHdr@@YAFPEAX@Z; PrintStatisticsHdr(void *)
0x1005350f5  mov     rcx, rsi; struct tagDBC *
0x1005350f8  call    ?InitTimer@@YAFPEAUtagDBC@@@Z; InitTimer(tagDBC *)
0x1005350fd  mov     rcx, cs:?g_hPerfDataFile@@3PEAXEA; hFile
0x100535104  movzx   ebx, ax
0x100535107  mov     eax, 0FFFEh
0x10053510c  test    ax, bx
0x10053510f  jz      short loc_100535120
0x100535111  call    cs:__imp_CloseHandle
0x100535117  mov     cs:?g_hPerfDataFile@@3PEAXEA, rdi; void * g_hPerfDataFile
0x10053511e  jmp     short loc_100535140
0x100535120  mov     r9d, 2; dwMoveMethod
0x100535126  xor     r8d, r8d; lpDistanceToMoveHigh
0x100535129  xor     edx, edx; lDistanceToMove
0x10053512b  call    cs:__imp_SetFilePointer
0x100535131  mov     cs:?g_fPerfStatLogEnabled@@3HA, 1; int g_fPerfStatLogEnabled
0x10053513b  call    ?ResetStatistics@@YAXXZ; ResetStatistics(void)
0x100535140  mov     rcx, cs:?g_csSQLPerf@@3PEAVCCriticalSection@@EA; CCriticalSection * g_csSQLPerf
0x100535147  add     rcx, 20h ; ' '
0x10053514b  mov     rax, [rcx]
0x10053514e  mov     rax, [rax+18h]
0x100535152  call    cs:__guard_dispatch_icall_fptr
0x100535158  test    byte ptr cs:_bidGblFlags, 2
0x10053515f  jz      short loc_100535174
0x100535161  movzx   r8d, bx; __int16
0x100535165  mov     edx, 3A409h; unsigned __int64
0x10053516a  xor     ecx, ecx; unsigned __int64
0x10053516c  call    ?_bidx_SNACOdbc_ErrCode@@YAF_K0F@Z; _bidx_SNACOdbc_ErrCode(unsigned __int64,unsigned __int64,short)
0x100535171  movzx   ebx, ax
0x100535174  mov     rsi, [rsp+48h+arg_8]
0x100535179  movzx   eax, bx
0x10053517c  mov     rbx, [rsp+48h+arg_0]
0x100535181  add     rsp, 40h
0x100535185  pop     rdi
0x100535186  retn
```
