# PrintStatistics(sqlperf *,void *,ushort const *)

- ea: `0x10053552c`
- end: `0x100535893`
- name: `?PrintStatistics@@YAFPEAUsqlperf@@PEAXPEBG@Z`
- size: `871`
- prototype: `__int16(struct sqlperf *, void *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1004e71f4`
- `0x100530c14`

## callees

- `0x100405948`
- `0x1005212b4`
- `0x10053552c`
- `0x10053590c`
- `0x100546a7c`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!WriteFile` at `0x100535640`
- `KERNEL32!WriteFile` at `0x1005356cf`
- `KERNEL32!WriteFile` at `0x100535765`
- `KERNEL32!WriteFile` at `0x100535818`
- `KERNEL32!WriteFile` at `0x100535640`
- `KERNEL32!WriteFile` at `0x1005356cf`
- `KERNEL32!WriteFile` at `0x100535765`
- `KERNEL32!WriteFile` at `0x100535818`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x100535589`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x100535589`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x10053556b`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x10053556b`
- `api-ms-win-crt-time-l1-1-0!_wctime64` at `0x100535576`
- `api-ms-win-crt-time-l1-1-0!_wctime64` at `0x100535576`

## pseudocode

```c
__int64 __fastcall PrintStatistics(struct sqlperf *a1, void *a2, const unsigned __int16 *a3)
{
  unsigned __int16 v4; // bx
  wchar_t *v7; // rax
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rax
  const wchar_t *v12; // rax
  __int64 v13; // rax
  DWORD lpOverlappedc; // [rsp+20h] [rbp-E0h]
  LPOVERLAPPED lpOverlapped; // [rsp+20h] [rbp-E0h]
  LPOVERLAPPED lpOverlappeda; // [rsp+20h] [rbp-E0h]
  LPOVERLAPPED lpOverlappedb; // [rsp+20h] [rbp-E0h]
  DWORD SQLidu; // [rsp+28h] [rbp-D8h]
  __int64 v20; // [rsp+28h] [rbp-D8h]
  __int64 v21; // [rsp+28h] [rbp-D8h]
  __int64 v22; // [rsp+28h] [rbp-D8h]
  DWORD SQLiduRows; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+30h] [rbp-D0h]
  DWORD SQLSelects; // [rsp+38h] [rbp-C8h]
  __int64 v27; // [rsp+38h] [rbp-C8h]
  __int64 v28; // [rsp+38h] [rbp-C8h]
  DWORD SQLSelectRows; // [rsp+40h] [rbp-C0h]
  __int64 v30; // [rsp+40h] [rbp-C0h]
  __int64 v31; // [rsp+40h] [rbp-C0h]
  DWORD Transactions; // [rsp+48h] [rbp-B8h]
  __int64 v33; // [rsp+48h] [rbp-B8h]
  __int64 v34; // [rsp+48h] [rbp-B8h]
  DWORD SQLPrepares; // [rsp+50h] [rbp-B0h]
  __int64 v36; // [rsp+50h] [rbp-B0h]
  DWORD ExecDirects; // [rsp+58h] [rbp-A8h]
  __int64 v38; // [rsp+58h] [rbp-A8h]
  DWORD SQLExecutes; // [rsp+60h] [rbp-A0h]
  DWORD NumberOfBytesWritten; // [rsp+70h] [rbp-90h] BYREF
  __time64_t Time; // [rsp+78h] [rbp-88h] BYREF
  _BYTE Destination[38]; // [rsp+80h] [rbp-80h] BYREF
  __int16 v43; // [rsp+A6h] [rbp-5Ah]
  unsigned __int16 Buffer[256]; // [rsp+B0h] [rbp-50h] BYREF

  v4 = 0;
  NumberOfBytesWritten = 0;
  _time64(&Time);
  v7 = _wctime64(&Time);
  memcpy_s(Destination, 0x28u, v7, 0x28u);
  v43 = 0;
  ReCalcStatistics();
  (*(void (__fastcall **)(char *))(*((_QWORD *)g_csSQLPerf + 4) + 8LL))((char *)g_csSQLPerf + 32);
  if ( g_fPerfStatLogEnabled )
  {
    SQLExecutes = a1->SQLExecutes;
    ExecDirects = a1->ExecDirects;
    SQLPrepares = a1->SQLPrepares;
    Transactions = a1->Transactions;
    SQLSelectRows = a1->SQLSelectRows;
    SQLSelects = a1->SQLSelects;
    SQLiduRows = a1->SQLiduRows;
    SQLidu = a1->SQLidu;
    lpOverlappedc = a1->TimerResolution;
    StringCchPrintfW(
      Buffer,
      0xFFu,
      L"%s\t%ld\t%ld\t%ld\t%ld\t%ld\t%ld\t%ld\t%ld\t%ld\t",
      Destination,
      lpOverlappedc,
      SQLidu,
      SQLiduRows,
      SQLSelects,
      SQLSelectRows,
      Transactions,
      SQLPrepares,
      ExecDirects,
      SQLExecutes);
    v8 = -1;
    do
      ++v8;
    while ( Buffer[v8] );
    if ( !WriteFile(a2, Buffer, 2 * v8, &NumberOfBytesWritten, 0) )
    {
      v4 = -1;
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_25;
      v9 = 552969;
      goto LABEL_24;
    }
    LODWORD(v38) = a1->SQLFetchCount;
    LODWORD(v36) = a1->SQLFetchTime;
    LODWORD(v20) = a1->CursorUsed;
    LODWORD(lpOverlapped) = a1->CursorSize;
    StringCchPrintfW(
      Buffer,
      0xFFu,
      L"%ld\t%ld\t%ld\t%f\t%f\t%f\t%f\t%ld\t%ld\t",
      a1->CursorOpens,
      lpOverlapped,
      v20,
      a1->PercentCursorUsed,
      a1->AvgFetchTime,
      a1->AvgCursorSize,
      a1->AvgCursorUsed,
      v36,
      v38);
    v10 = -1;
    do
      ++v10;
    while ( Buffer[v10] );
    if ( !WriteFile(a2, Buffer, 2 * v10, &NumberOfBytesWritten, 0) )
    {
      v4 = -1;
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_25;
      v9 = 569353;
      goto LABEL_24;
    }
    LODWORD(v33) = a1->SumConnectiontime;
    LODWORD(v30) = a1->SumConnectionsOpened;
    LODWORD(v27) = a1->MaxConnectionsOpened;
    LODWORD(v24) = a1->CurrentConnectionCount;
    LODWORD(v21) = a1->SumOpenStmt;
    LODWORD(lpOverlappeda) = a1->MaxOpenStmt;
    StringCchPrintfW(
      Buffer,
      0xFFu,
      L"%ld\t%ld\t%ld\t%ld\t%ld\t%ld\t%ld\t%f\t",
      a1->CurrentStmtCount,
      lpOverlappeda,
      v21,
      v24,
      v27,
      v30,
      v33,
      a1->AvgTimeOpened);
    v11 = -1;
    do
      ++v11;
    while ( Buffer[v11] );
    if ( !WriteFile(a2, Buffer, 2 * v11, &NumberOfBytesWritten, 0) )
    {
      v4 = -1;
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_25;
      v9 = 584713;
      goto LABEL_24;
    }
    v12 = &szDefault;
    if ( a3 )
      v12 = a3;
    LODWORD(v34) = a1->msNetWorkServerTime;
    LODWORD(v31) = a1->msExecutionTime;
    LODWORD(v28) = a1->BytesRec;
    LODWORD(v25) = a1->BytesSent;
    LODWORD(v22) = a1->BuffersRec;
    LODWORD(lpOverlappedb) = a1->BuffersSent;
    StringCchPrintfW(
      Buffer,
      0xFFu,
      L"%ld\t%ld\t%ld\t%ld\t%ld\t%ld\t%ld\t%s\r\n",
      a1->ServerRndTrips,
      lpOverlappedb,
      v22,
      v25,
      v28,
      v31,
      v34,
      v12);
    v13 = -1;
    do
      ++v13;
    while ( Buffer[v13] );
    if ( !WriteFile(a2, Buffer, 2 * v13, &NumberOfBytesWritten, 0) )
    {
      v4 = -1;
      if ( (bidGblFlags & 2) != 0 )
      {
        v9 = 600073;
LABEL_24:
        bidTraceMark(0, v9);
      }
    }
  }
LABEL_25:
  (*(void (__fastcall **)(char *))(*((_QWORD *)g_csSQLPerf + 4) + 24LL))((char *)g_csSQLPerf + 32);
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned __int16)_bidx_SNACOdbc_ErrCode(0, 0x93C09u, v4);
  return v4;
}

```

## disassembly

```asm
0x10053552c  push    rbp
0x10053552e  push    rbx
0x10053552f  push    rsi
0x100535530  push    rdi
0x100535531  push    r13
0x100535533  push    r14
0x100535535  push    r15
0x100535537  lea     rbp, [rsp-1C0h]
0x10053553f  sub     rsp, 2C0h
0x100535546  mov     rax, cs:__security_cookie
0x10053554d  xor     rax, rsp
0x100535550  mov     [rbp+1F0h+var_40], rax
0x100535557  mov     rdi, rcx
0x10053555a  xor     ebx, ebx
0x10053555c  lea     rcx, [rsp+2F0h+Time]; Time
0x100535561  mov     [rsp+2F0h+NumberOfBytesWritten], ebx
0x100535565  mov     r14, r8
0x100535568  mov     rsi, rdx
0x10053556b  call    cs:__imp__time64
0x100535571  lea     rcx, [rsp+2F0h+Time]; Time
0x100535576  call    cs:__imp__wctime64
0x10053557c  lea     edx, [rbx+28h]; DestinationSize
0x10053557f  mov     r8, rax; Source
0x100535582  mov     r9d, edx; SourceSize
0x100535585  lea     rcx, [rbp+1F0h+Destination]; Destination
0x100535589  call    cs:__imp_memcpy_s
0x10053558f  mov     [rbp+1F0h+var_24A], bx
0x100535593  call    ?ReCalcStatistics@@YAXXZ; ReCalcStatistics(void)
0x100535598  mov     rcx, cs:?g_csSQLPerf@@3PEAVCCriticalSection@@EA; CCriticalSection * g_csSQLPerf
0x10053559f  add     rcx, 20h ; ' '
0x1005355a3  mov     rax, [rcx]
0x1005355a6  mov     rax, [rax+8]
0x1005355aa  call    cs:__guard_dispatch_icall_fptr
0x1005355b0  cmp     cs:?g_fPerfStatLogEnabled@@3HA, ebx; int g_fPerfStatLogEnabled
0x1005355b6  jz      loc_10053583B
0x1005355bc  mov     eax, [rdi+20h]
0x1005355bf  lea     r9, [rbp+1F0h+Destination]
0x1005355c3  mov     [rsp+2F0h+var_290], eax
0x1005355c7  lea     r8, aSLdLdLdLdLdLdL; "%s\t%ld\t%ld\t%ld\t%ld\t%ld\t%ld\t%ld\t"...
0x1005355ce  mov     eax, [rdi+1Ch]
0x1005355d1  lea     rcx, [rbp+1F0h+Buffer]; unsigned __int16 *
0x1005355d5  mov     dword ptr [rsp+2F0h+var_298], eax
0x1005355d9  mov     r13d, 0FFh
0x1005355df  mov     eax, [rdi+18h]
0x1005355e2  mov     edx, r13d; unsigned __int64
0x1005355e5  mov     dword ptr [rsp+2F0h+var_2A0], eax
0x1005355e9  mov     eax, [rdi+14h]
0x1005355ec  mov     dword ptr [rsp+2F0h+var_2B0+8], eax
0x1005355f0  mov     eax, [rdi+10h]
0x1005355f3  mov     dword ptr [rsp+2F0h+var_2B0], eax
0x1005355f7  mov     eax, [rdi+0Ch]
0x1005355fa  mov     dword ptr [rsp+2F0h+var_2C0+8], eax
0x1005355fe  mov     eax, [rdi+8]
0x100535601  mov     dword ptr [rsp+2F0h+var_2C0], eax
0x100535605  mov     eax, [rdi+4]
0x100535608  mov     dword ptr [rsp+2F0h+var_2C8], eax
0x10053560c  mov     eax, [rdi]
0x10053560e  mov     dword ptr [rsp+2F0h+lpOverlapped], eax
0x100535612  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x100535617  or      r15, 0FFFFFFFFFFFFFFFFh
0x10053561b  lea     rcx, [rbp+1F0h+Buffer]
0x10053561f  mov     rax, r15
0x100535622  inc     rax
0x100535625  cmp     [rcx+rax*2], bx
0x100535629  jnz     short loc_100535622
0x10053562b  lea     r8d, [rax+rax]; nNumberOfBytesToWrite
0x10053562f  mov     [rsp+2F0h+lpOverlapped], rbx; lpOverlapped
0x100535634  lea     r9, [rsp+2F0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x100535639  mov     rcx, rsi; hFile
0x10053563c  lea     rdx, [rbp+1F0h+Buffer]; lpBuffer
0x100535640  call    cs:__imp_WriteFile
0x100535646  test    eax, eax
0x100535648  jnz     short loc_100535665
0x10053564a  test    byte ptr cs:_bidGblFlags, 2
0x100535651  movzx   ebx, r15w
0x100535655  jz      loc_10053583B
0x10053565b  mov     edx, 87009h
0x100535660  jmp     loc_100535834
0x100535665  mov     eax, [rdi+54h]
0x100535668  lea     r8, aLdLdLdFFFFLdLd; "%ld\t%ld\t%ld\t%f\t%f\t%f\t%f\t%ld\t%ld"...
0x10053566f  movups  xmm0, xmmword ptr [rdi+40h]
0x100535673  mov     r9d, [rdi+24h]
0x100535677  lea     rcx, [rbp+1F0h+Buffer]; unsigned __int16 *
0x10053567b  mov     dword ptr [rsp+2F0h+var_298], eax
0x10053567f  mov     rdx, r13; unsigned __int64
0x100535682  mov     eax, [rdi+50h]
0x100535685  mov     dword ptr [rsp+2F0h+var_2A0], eax
0x100535689  mov     eax, [rdi+2Ch]
0x10053568c  movups  [rsp+2F0h+var_2B0], xmm0
0x100535691  movups  xmm0, xmmword ptr [rdi+30h]
0x100535695  movups  [rsp+2F0h+var_2C0], xmm0
0x10053569a  mov     dword ptr [rsp+2F0h+var_2C8], eax
0x10053569e  mov     eax, [rdi+28h]
0x1005356a1  mov     dword ptr [rsp+2F0h+lpOverlapped], eax
0x1005356a5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1005356aa  lea     rcx, [rbp+1F0h+Buffer]
0x1005356ae  mov     rax, r15
0x1005356b1  inc     rax
0x1005356b4  cmp     [rcx+rax*2], bx
0x1005356b8  jnz     short loc_1005356B1
0x1005356ba  lea     r8d, [rax+rax]; nNumberOfBytesToWrite
0x1005356be  mov     [rsp+2F0h+lpOverlapped], rbx; lpOverlapped
0x1005356c3  lea     r9, [rsp+2F0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1005356c8  mov     rcx, rsi; hFile
0x1005356cb  lea     rdx, [rbp+1F0h+Buffer]; lpBuffer
0x1005356cf  call    cs:__imp_WriteFile
0x1005356d5  test    eax, eax
0x1005356d7  jnz     short loc_1005356F4
0x1005356d9  test    byte ptr cs:_bidGblFlags, 2
0x1005356e0  movzx   ebx, r15w
0x1005356e4  jz      loc_10053583B
0x1005356ea  mov     edx, 8B009h
0x1005356ef  jmp     loc_100535834
0x1005356f4  mov     eax, [rdi+70h]
0x1005356f7  lea     r8, aLdLdLdLdLdLdLd_0; "%ld\t%ld\t%ld\t%ld\t%ld\t%ld\t%ld\t%f\t"
0x1005356fe  movsd   xmm0, qword ptr [rdi+78h]
0x100535703  lea     rcx, [rbp+1F0h+Buffer]; unsigned __int16 *
0x100535707  mov     r9d, [rdi+58h]
0x10053570b  mov     rdx, r13; unsigned __int64
0x10053570e  movsd   [rsp+2F0h+var_2A0], xmm0
0x100535714  mov     dword ptr [rsp+2F0h+var_2B0+8], eax
0x100535718  mov     eax, [rdi+6Ch]
0x10053571b  mov     dword ptr [rsp+2F0h+var_2B0], eax
0x10053571f  mov     eax, [rdi+68h]
0x100535722  mov     dword ptr [rsp+2F0h+var_2C0+8], eax
0x100535726  mov     eax, [rdi+64h]
0x100535729  mov     dword ptr [rsp+2F0h+var_2C0], eax
0x10053572d  mov     eax, [rdi+60h]
0x100535730  mov     dword ptr [rsp+2F0h+var_2C8], eax
0x100535734  mov     eax, [rdi+5Ch]
0x100535737  mov     dword ptr [rsp+2F0h+lpOverlapped], eax
0x10053573b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x100535740  lea     rcx, [rbp+1F0h+Buffer]
0x100535744  mov     rax, r15
0x100535747  inc     rax
0x10053574a  cmp     [rcx+rax*2], bx
0x10053574e  jnz     short loc_100535747
0x100535750  lea     r8d, [rax+rax]; nNumberOfBytesToWrite
0x100535754  mov     [rsp+2F0h+lpOverlapped], rbx; lpOverlapped
0x100535759  lea     r9, [rsp+2F0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x10053575e  mov     rcx, rsi; hFile
0x100535761  lea     rdx, [rbp+1F0h+Buffer]; lpBuffer
0x100535765  call    cs:__imp_WriteFile
0x10053576b  test    eax, eax
0x10053576d  jnz     short loc_10053578A
0x10053576f  test    byte ptr cs:_bidGblFlags, 2
0x100535776  movzx   ebx, r15w
0x10053577a  jz      loc_10053583B
0x100535780  mov     edx, 8EC09h
0x100535785  jmp     loc_100535834
0x10053578a  mov     r9d, [rdi+80h]
0x100535791  lea     rax, szDefault
0x100535798  test    r14, r14
0x10053579b  lea     r8, aLdLdLdLdLdLdLd; "%ld\t%ld\t%ld\t%ld\t%ld\t%ld\t%ld\t%s\r"...
0x1005357a2  mov     rdx, r13; unsigned __int64
0x1005357a5  lea     rcx, [rbp+1F0h+Buffer]; unsigned __int16 *
0x1005357a9  cmovnz  rax, r14
0x1005357ad  mov     [rsp+2F0h+var_2A0], rax
0x1005357b2  mov     eax, [rdi+98h]
0x1005357b8  mov     dword ptr [rsp+2F0h+var_2B0+8], eax
0x1005357bc  mov     eax, [rdi+94h]
0x1005357c2  mov     dword ptr [rsp+2F0h+var_2B0], eax
0x1005357c6  mov     eax, [rdi+90h]
0x1005357cc  mov     dword ptr [rsp+2F0h+var_2C0+8], eax
0x1005357d0  mov     eax, [rdi+8Ch]
0x1005357d6  mov     dword ptr [rsp+2F0h+var_2C0], eax
0x1005357da  mov     eax, [rdi+88h]
0x1005357e0  mov     dword ptr [rsp+2F0h+var_2C8], eax
0x1005357e4  mov     eax, [rdi+84h]
0x1005357ea  mov     dword ptr [rsp+2F0h+lpOverlapped], eax
0x1005357ee  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1005357f3  lea     rcx, [rbp+1F0h+Buffer]
0x1005357f7  mov     rax, r15
0x1005357fa  inc     rax
0x1005357fd  cmp     [rcx+rax*2], bx
0x100535801  jnz     short loc_1005357FA
0x100535803  lea     r8d, [rax+rax]; nNumberOfBytesToWrite
0x100535807  mov     [rsp+2F0h+lpOverlapped], rbx; lpOverlapped
0x10053580c  lea     r9, [rsp+2F0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x100535811  mov     rcx, rsi; hFile
0x100535814  lea     rdx, [rbp+1F0h+Buffer]; lpBuffer
0x100535818  call    cs:__imp_WriteFile
0x10053581e  test    eax, eax
0x100535820  jnz     short loc_10053583B
0x100535822  test    byte ptr cs:_bidGblFlags, 2
0x100535829  movzx   ebx, r15w
0x10053582d  jz      short loc_10053583B
0x10053582f  mov     edx, 92809h
0x100535834  xor     ecx, ecx
0x100535836  call    _bidTraceMark
0x10053583b  mov     rcx, cs:?g_csSQLPerf@@3PEAVCCriticalSection@@EA; CCriticalSection * g_csSQLPerf
0x100535842  add     rcx, 20h ; ' '
0x100535846  mov     rax, [rcx]
0x100535849  mov     rax, [rax+18h]
0x10053584d  call    cs:__guard_dispatch_icall_fptr
0x100535853  test    byte ptr cs:_bidGblFlags, 2
0x10053585a  jz      short loc_10053586F
0x10053585c  movzx   r8d, bx; __int16
0x100535860  mov     edx, 93C09h; unsigned __int64
0x100535865  xor     ecx, ecx; unsigned __int64
0x100535867  call    ?_bidx_SNACOdbc_ErrCode@@YAF_K0F@Z; _bidx_SNACOdbc_ErrCode(unsigned __int64,unsigned __int64,short)
0x10053586c  movzx   ebx, ax
0x10053586f  movzx   eax, bx
0x100535872  mov     rcx, [rbp+1F0h+var_40]
0x100535879  xor     rcx, rsp; StackCookie
0x10053587c  call    __security_check_cookie
0x100535881  add     rsp, 2C0h
0x100535888  pop     r15
0x10053588a  pop     r14
0x10053588c  pop     r13
0x10053588e  pop     rdi
0x10053588f  pop     rsi
0x100535890  pop     rbx
0x100535891  pop     rbp
0x100535892  retn
```
