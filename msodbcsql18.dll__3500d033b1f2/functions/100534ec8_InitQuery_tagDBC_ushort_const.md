# InitQuery(tagDBC *,ushort const *)

- ea: `0x100534ec8`
- end: `0x10053501e`
- name: `?InitQuery@@YAFPEAUtagDBC@@PEBG@Z`
- size: `342`
- prototype: `__int16(struct tagDBC *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1004e8a74`
- `0x100530c14`

## callees

- `0x1005212b4`
- `0x100534ec8`
- `0x100535190`
- `0x100546a7c`
- `0x100546f80`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x100534f61`
- `KERNEL32!CreateFileW` at `0x100534f61`
- `KERNEL32!CloseHandle` at `0x100534fad`
- `KERNEL32!CloseHandle` at `0x100534fad`
- `KERNEL32!SetFilePointer` at `0x100534fc7`
- `KERNEL32!SetFilePointer` at `0x100534fc7`

## pseudocode

```c
__int64 __fastcall InitQuery(struct tagDBC *a1, const unsigned __int16 *a2)
{
  unsigned __int16 inited; // bx

  inited = 0;
  (*(void (__fastcall **)(char *))(*((_QWORD *)g_csSQLPerf + 4) + 8LL))((char *)g_csSQLPerf + 32);
  if ( !g_fLogSlowQuery )
  {
    if ( a2 )
      SQLGetPrivateProfileStringW(a2, L"QueryLogFile", &g_szDefPerfQueryFile, &g_szPerfQueryFile, 261, L"ODBC.INI");
    g_hPerfQueryFile = CreateFileW(&g_szPerfQueryFile, 0x40000000u, 1u, 0, 4u, 0x80u, 0);
    if ( g_hPerfQueryFile == (HANDLE)-1LL )
    {
      inited = -1;
      if ( (bidGblFlags & 2) != 0 )
        bidTraceMark(0, 146441);
    }
    else
    {
      inited = InitTimer(a1);
      if ( (inited & 0xFFFE) != 0 )
      {
        CloseHandle(g_hPerfQueryFile);
        g_hPerfQueryFile = (HANDLE)-1LL;
      }
      else
      {
        SetFilePointer(g_hPerfQueryFile, 0, 0, 2u);
        g_fLogSlowQuery = 1;
      }
    }
  }
  (*(void (__fastcall **)(char *))(*((_QWORD *)g_csSQLPerf + 4) + 24LL))((char *)g_csSQLPerf + 32);
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned __int16)_bidx_SNACOdbc_ErrCode(0, 0x27C09u, inited);
  return inited;
}

```

## disassembly

```asm
0x100534ec8  mov     [rsp+arg_0], rbx
0x100534ecd  mov     [rsp+arg_8], rsi
0x100534ed2  push    rdi
0x100534ed3  sub     rsp, 40h
0x100534ed7  mov     rsi, rcx
0x100534eda  mov     rdi, rdx
0x100534edd  mov     rcx, cs:?g_csSQLPerf@@3PEAVCCriticalSection@@EA; CCriticalSection * g_csSQLPerf
0x100534ee4  xor     ebx, ebx
0x100534ee6  add     rcx, 20h ; ' '
0x100534eea  mov     rax, [rcx]
0x100534eed  mov     rax, [rax+8]
0x100534ef1  call    cs:__guard_dispatch_icall_fptr
0x100534ef7  cmp     cs:?g_fLogSlowQuery@@3HA, ebx; int g_fLogSlowQuery
0x100534efd  jnz     loc_100534FD7
0x100534f03  test    rdi, rdi
0x100534f06  jz      short loc_100534F39
0x100534f08  lea     rax, szFilename; "ODBC.INI"
0x100534f0f  mov     rcx, rdi; lpszSection
0x100534f12  mov     [rsp+48h+lpszFilename], rax; lpszFilename
0x100534f17  lea     r9, ?g_szPerfQueryFile@@3PAGA; lpszRetBuffer
0x100534f1e  lea     r8, ?g_szDefPerfQueryFile@@3PAGA; lpszDefault
0x100534f25  mov     [rsp+48h+cchRetBuffer], 105h; cchRetBuffer
0x100534f2d  lea     rdx, aQuerylogfile; "QueryLogFile"
0x100534f34  call    SQLGetPrivateProfileStringW
0x100534f39  xor     r9d, r9d; lpSecurityAttributes
0x100534f3c  mov     [rsp+48h+hTemplateFile], rbx; hTemplateFile
0x100534f41  mov     dword ptr [rsp+48h+lpszFilename], 80h; dwFlagsAndAttributes
0x100534f49  lea     rcx, ?g_szPerfQueryFile@@3PAGA; lpFileName
0x100534f50  mov     edx, 40000000h; dwDesiredAccess
0x100534f55  mov     [rsp+48h+cchRetBuffer], 4; dwCreationDisposition
0x100534f5d  lea     r8d, [r9+1]; dwShareMode
0x100534f61  call    cs:__imp_CreateFileW
0x100534f67  or      rdi, 0FFFFFFFFFFFFFFFFh
0x100534f6b  mov     cs:?g_hPerfQueryFile@@3PEAXEA, rax; void * g_hPerfQueryFile
0x100534f72  cmp     rax, rdi
0x100534f75  jnz     short loc_100534F91
0x100534f77  test    byte ptr cs:_bidGblFlags, 2
0x100534f7e  movzx   ebx, di
0x100534f81  jz      short loc_100534FD7
0x100534f83  mov     edx, 23C09h
0x100534f88  xor     ecx, ecx
0x100534f8a  call    _bidTraceMark
0x100534f8f  jmp     short loc_100534FD7
0x100534f91  mov     rcx, rsi; struct tagDBC *
0x100534f94  call    ?InitTimer@@YAFPEAUtagDBC@@@Z; InitTimer(tagDBC *)
0x100534f99  mov     rcx, cs:?g_hPerfQueryFile@@3PEAXEA; hFile
0x100534fa0  movzx   ebx, ax
0x100534fa3  mov     eax, 0FFFEh
0x100534fa8  test    ax, bx
0x100534fab  jz      short loc_100534FBC
0x100534fad  call    cs:__imp_CloseHandle
0x100534fb3  mov     cs:?g_hPerfQueryFile@@3PEAXEA, rdi; void * g_hPerfQueryFile
0x100534fba  jmp     short loc_100534FD7
0x100534fbc  mov     r9d, 2; dwMoveMethod
0x100534fc2  xor     r8d, r8d; lpDistanceToMoveHigh
0x100534fc5  xor     edx, edx; lDistanceToMove
0x100534fc7  call    cs:__imp_SetFilePointer
0x100534fcd  mov     cs:?g_fLogSlowQuery@@3HA, 1; int g_fLogSlowQuery
0x100534fd7  mov     rcx, cs:?g_csSQLPerf@@3PEAVCCriticalSection@@EA; CCriticalSection * g_csSQLPerf
0x100534fde  add     rcx, 20h ; ' '
0x100534fe2  mov     rax, [rcx]
0x100534fe5  mov     rax, [rax+18h]
0x100534fe9  call    cs:__guard_dispatch_icall_fptr
0x100534fef  test    byte ptr cs:_bidGblFlags, 2
0x100534ff6  jz      short loc_10053500B
0x100534ff8  movzx   r8d, bx; __int16
0x100534ffc  mov     edx, 27C09h; unsigned __int64
0x100535001  xor     ecx, ecx; unsigned __int64
0x100535003  call    ?_bidx_SNACOdbc_ErrCode@@YAF_K0F@Z; _bidx_SNACOdbc_ErrCode(unsigned __int64,unsigned __int64,short)
0x100535008  movzx   ebx, ax
0x10053500b  mov     rsi, [rsp+48h+arg_8]
0x100535010  movzx   eax, bx
0x100535013  mov     rbx, [rsp+48h+arg_0]
0x100535018  add     rsp, 40h
0x10053501c  pop     rdi
0x10053501d  retn
```
