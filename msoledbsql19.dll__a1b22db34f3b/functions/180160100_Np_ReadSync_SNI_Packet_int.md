# Np::ReadSync(SNI_Packet * *,int)

- ea: `0x180160100`
- end: `0x1801606df`
- name: `?ReadSync@Np@@UEAAKPEAPEAVSNI_Packet@@H@Z`
- size: `1503`
- prototype: `unsigned int __fastcall(Np *__hidden this, struct SNI_Packet **, int)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops`

## callees

- `0x180001f70`
- `0x180002ef0`
- `0x1800030c0`
- `0x180003250`
- `0x180003d80`
- `0x180158180`
- `0x180158600`
- `0x18015a6f0`
- `0x18015a880`
- `0x180160100`
- `0x18017f290`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1801601e4`
- `KERNEL32!GetLastError` at `0x1801602c6`
- `KERNEL32!GetLastError` at `0x1801603cb`
- `KERNEL32!GetLastError` at `0x1801601e4`
- `KERNEL32!GetLastError` at `0x1801602c6`
- `KERNEL32!GetLastError` at `0x1801603cb`
- `KERNEL32!GetOverlappedResult` at `0x1801602b8`
- `KERNEL32!GetOverlappedResult` at `0x1801603bd`
- `KERNEL32!GetOverlappedResult` at `0x1801602b8`
- `KERNEL32!GetOverlappedResult` at `0x1801603bd`
- `KERNEL32!ReadFile` at `0x1801601d6`
- `KERNEL32!ReadFile` at `0x1801601d6`
- `KERNEL32!GetTickCount` at `0x18016027e`
- `KERNEL32!GetTickCount` at `0x1801602f3`
- `KERNEL32!GetTickCount` at `0x18016027e`
- `KERNEL32!GetTickCount` at `0x1801602f3`
- `KERNEL32!WaitForSingleObject` at `0x18016028d`
- `KERNEL32!WaitForSingleObject` at `0x18016028d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Np::ReadSync(Np *this, struct SNI_Packet **a2, signed int a3)
{
  DWORD v6; // r14d
  struct SNI_Packet *v7; // rsi
  struct SNI_Packet *Ex2; // rax
  void *v9; // rdx
  DWORD v10; // r8d
  struct _OVERLAPPED *v11; // r15
  DWORD LastError; // ebx
  char v13; // al
  wchar_t *v14; // r8
  __int64 v15; // rdx
  char *v16; // rcx
  DWORD TickCount; // r12d
  DWORD v18; // eax
  DWORD NumberOfBytesTransferred; // [rsp+30h] [rbp-58h] BYREF
  __int64 v21; // [rsp+38h] [rbp-50h] BYREF

  v21 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1802668F0[0] )
    bidScopeEnterW(&v21, off_1802668F0[0], *((unsigned int *)this + 11), a2);
  v6 = 0;
  NumberOfBytesTransferred = 0;
  *a2 = 0;
  while ( 1 )
  {
    v7 = (struct SNI_Packet *)*((_QWORD *)this + 10);
    if ( v7 )
    {
      v11 = (struct _OVERLAPPED *)((char *)v7 + 16);
      *((_QWORD *)this + 10) = 0;
      goto LABEL_18;
    }
    Ex2 = (struct SNI_Packet *)SNIPacketAllocateEx2(*((_QWORD *)this + 4), 0, 0);
    v7 = Ex2;
    if ( !Ex2 )
    {
      LastError = 14;
      if ( (bidGblFlags & 2) != 0 && off_180264200[0] )
      {
        SniErrorIdFromStringId(0xC3B4u);
        bidTraceW(off_180260EB8[0], 493568, off_180264200[0], *((unsigned int *)this + 18));
      }
      SNISetLastError(*((unsigned int *)this + 18), 14, 50100);
      goto LABEL_66;
    }
    SNI::detail::Transport::PrepareForSyncCall(this, Ex2);
    v9 = (void *)(*((_QWORD *)v7 + 9) + *((unsigned int *)v7 + 22));
    v10 = *((_DWORD *)v7 + 21);
    v11 = (struct _OVERLAPPED *)((char *)v7 + 16);
    NumberOfBytesTransferred = 0;
    *((_QWORD *)v7 + 4) = 0;
    if ( ReadFile(*((HANDLE *)this + 8), v9, v10, 0, (LPOVERLAPPED)((char *)v7 + 16)) )
      goto LABEL_32;
    LastError = GetLastError();
    if ( LastError != 997 )
      break;
LABEL_18:
    TickCount = GetTickCount();
    v18 = WaitForSingleObject(v11->hEvent, a3);
    LastError = v18;
    if ( v18 == -1 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180264228[0] )
      {
        SniErrorIdFromStringId(0xC3B4u);
        bidTraceW(off_180260EE0[0], 581632, off_180264228[0], *((unsigned int *)this + 18));
      }
      SNISetLastError(*((unsigned int *)this + 18), LastError, 50100);
      goto LABEL_64;
    }
    if ( v18 == 258 )
    {
      *((_QWORD *)this + 10) = v7;
      if ( (bidGblFlags & 2) != 0 && off_180264230[0] )
      {
        SniErrorIdFromStringId(0xC3BFu);
        bidTraceW(off_180260EE8[0], 588800, off_180264230[0], *((unsigned int *)this + 18));
      }
      SNISetLastError(*((unsigned int *)this + 18), LastError, 50111);
      goto LABEL_66;
    }
    if ( GetOverlappedResult(*((HANDLE *)this + 8), v11, &NumberOfBytesTransferred, 0) )
      goto LABEL_48;
    LastError = GetLastError();
    if ( LastError != 995 )
    {
      if ( LastError == 234 )
        goto LABEL_48;
      if ( (bidGblFlags & 2) != 0 && off_180264240[0] )
      {
        SniErrorIdFromStringId(0xC3B4u);
        v14 = off_180264240[0];
        v15 = 625664;
        v16 = off_180260EF8[0];
LABEL_45:
        bidTraceW(v16, v15, v14, *((unsigned int *)this + 18));
      }
LABEL_46:
      SNISetLastError(*((unsigned int *)this + 18), LastError, 50100);
      if ( LastError != 258 )
      {
LABEL_64:
        if ( v7 )
        {
          SNIPacketRelease(v7);
          *((_QWORD *)this + 10) = 0;
        }
      }
LABEL_66:
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_180264258[0] )
        bidTraceW(off_180260F10[0], 660480, off_180264258[0], LastError);
      v6 = LastError;
      goto LABEL_70;
    }
    SNIPacketRelease(v7);
    *((_QWORD *)this + 10) = 0;
    NumberOfBytesTransferred = 0;
    if ( a3 != -1 )
    {
      a3 += TickCount - GetTickCount();
      if ( a3 <= 0 )
      {
        LastError = 258;
        if ( (bidGblFlags & 2) != 0 && off_180264238[0] )
        {
          SniErrorIdFromStringId(0xC3BFu);
          bidTraceW(off_180260EF0[0], 615424, off_180264238[0], *((unsigned int *)this + 18));
        }
        SNISetLastError(*((unsigned int *)this + 18), 258, 50111);
        goto LABEL_66;
      }
    }
  }
  v13 = bidGblFlags;
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( off_180264208[0] )
      bidTraceW(off_180260EC0[0], 525312, off_180264208[0], LastError);
    v13 = bidGblFlags;
  }
  if ( LastError != 234 )
  {
    if ( (v13 & 2) != 0 && off_180264210[0] )
    {
      SniErrorIdFromStringId(0xC3B4u);
      v14 = off_180264210[0];
      v15 = 532480;
      v16 = off_180260EC8[0];
      goto LABEL_45;
    }
    goto LABEL_46;
  }
  if ( (v13 & 2) != 0 && off_180264218[0] && bidID != -1 )
    ((void (__fastcall *)(__int64, char *, __int64, wchar_t *, _QWORD))off_180248050[0])(
      bidID,
      off_180260ED0[0],
      545792,
      off_180264218[0],
      0);
LABEL_32:
  if ( !GetOverlappedResult(*((HANDLE *)this + 8), (LPOVERLAPPED)((char *)v7 + 16), &NumberOfBytesTransferred, 1) )
  {
    LastError = GetLastError();
    if ( LastError != 234 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180264220[0] )
      {
        SniErrorIdFromStringId(0xC3B4u);
        v14 = off_180264220[0];
        v15 = 555008;
        v16 = off_180260ED8[0];
        goto LABEL_45;
      }
      goto LABEL_46;
    }
  }
LABEL_48:
  *((_DWORD *)v7 + 20) = NumberOfBytesTransferred;
  *a2 = v7;
  if ( (bidGblFlags & 0x24002) == 0x24002 && off_180264248[0] )
    bidTraceW(off_180260F00[0], 642048, off_180264248[0], NumberOfBytesTransferred);
  if ( (bidGblFlags & 0x24002) == 0x24002 )
    bidWriteBin(bidID, 16, *((_QWORD *)v7 + 9) + *((unsigned int *)v7 + 22), NumberOfBytesTransferred, 0);
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_180264250[0] )
    bidTraceW(off_180260F08[0], 645120, off_180264250[0], 0);
LABEL_70:
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v21);
  return v6;
}

```

## disassembly

```asm
0x180160100  mov     [rsp+arg_18], rbx
0x180160105  push    rbp
0x180160106  push    rsi
0x180160107  push    rdi
0x180160108  push    r12
0x18016010a  push    r13
0x18016010c  push    r14
0x18016010e  push    r15
0x180160110  sub     rsp, 50h
0x180160114  mov     rax, cs:__security_cookie
0x18016011b  xor     rax, rsp
0x18016011e  mov     [rsp+88h+var_48], rax
0x180160123  mov     ebp, r8d
0x180160126  mov     r13, rdx
0x180160129  mov     rdi, rcx
0x18016012c  mov     [rsp+88h+var_50], 0FFFFFFFFFFFFFFFFh
0x180160135  mov     eax, cs:_bidGblFlags
0x18016013b  and     eax, 20004h
0x180160140  cmp     eax, 20004h
0x180160145  jnz     short loc_180160170
0x180160147  mov     rax, cs:off_1802668F0; "<Np::ReadSync|API|SNI> %u#, ppNewPacket"...
0x18016014e  test    rax, rax
0x180160151  jz      short loc_180160170
0x180160153  mov     dword ptr [rsp+88h+lpOverlapped], r8d
0x180160158  mov     r9, rdx
0x18016015b  mov     r8d, [rcx+2Ch]
0x18016015f  mov     rdx, cs:off_1802668F0; "<Np::ReadSync|API|SNI> %u#, ppNewPacket"...
0x180160166  lea     rcx, [rsp+88h+var_50]
0x18016016b  call    _bidScopeEnterW
0x180160170  xor     r14d, r14d
0x180160173  mov     [rsp+88h+NumberOfBytesTransferred], r14d
0x180160178  mov     [r13+0], r14
0x18016017c  nop     dword ptr [rax+00h]
0x180160180  mov     rsi, [rdi+50h]
0x180160184  test    rsi, rsi
0x180160187  jnz     loc_180160276
0x18016018d  xor     r8d, r8d
0x180160190  xor     edx, edx
0x180160192  mov     rcx, [rdi+20h]
0x180160196  call    SNIPacketAllocateEx2
0x18016019b  mov     rsi, rax
0x18016019e  test    rax, rax
0x1801601a1  jz      loc_18016041F
0x1801601a7  mov     rdx, rax; struct SNI_Packet *
0x1801601aa  mov     rcx, rdi; this
0x1801601ad  call    ?PrepareForSyncCall@Transport@detail@SNI@@IEAAXPEAVSNI_Packet@@@Z; SNI::detail::Transport::PrepareForSyncCall(SNI_Packet *)
0x1801601b2  mov     edx, [rsi+58h]
0x1801601b5  add     rdx, [rsi+48h]; lpBuffer
0x1801601b9  mov     r8d, [rsi+54h]; nNumberOfBytesToRead
0x1801601bd  lea     r15, [rsi+10h]
0x1801601c1  mov     [rsp+88h+NumberOfBytesTransferred], r14d
0x1801601c6  mov     [r15+10h], r14
0x1801601ca  mov     [rsp+88h+lpOverlapped], r15; lpOverlapped
0x1801601cf  xor     r9d, r9d; lpNumberOfBytesRead
0x1801601d2  mov     rcx, [rdi+40h]; hFile
0x1801601d6  call    cs:__imp_ReadFile
0x1801601dc  test    eax, eax
0x1801601de  jnz     loc_1801603AB
0x1801601e4  call    cs:__imp_GetLastError
0x1801601ea  mov     ebx, eax
0x1801601ec  cmp     eax, 3E5h
0x1801601f1  jz      loc_18016027E
0x1801601f7  mov     eax, cs:_bidGblFlags
0x1801601fd  test    al, 2
0x1801601ff  jz      short loc_18016022E
0x180160201  mov     rax, cs:off_180264208; "<Np::ReadSync|ERR|SNI> ReadFile: %d{WIN"...
0x180160208  test    rax, rax
0x18016020b  jz      short loc_180160228
0x18016020d  mov     r9d, ebx
0x180160210  mov     r8, cs:off_180264208; "<Np::ReadSync|ERR|SNI> ReadFile: %d{WIN"...
0x180160217  mov     edx, 80400h
0x18016021c  mov     rcx, cs:off_180260EC0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180160223  call    _bidTraceW
0x180160228  mov     eax, cs:_bidGblFlags
0x18016022e  cmp     ebx, 0EAh
0x180160234  jz      loc_180160364
0x18016023a  mov     ebp, 0C3B4h
0x18016023f  test    al, 2
0x180160241  jz      loc_1801604C8
0x180160247  mov     rax, cs:off_180264210; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x18016024e  test    rax, rax
0x180160251  jz      loc_1801604C8
0x180160257  mov     ecx, ebp; unsigned int
0x180160259  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x18016025e  mov     r8, cs:off_180264210; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x180160265  mov     edx, 82000h
0x18016026a  mov     rcx, cs:off_180260EC8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180160271  jmp     loc_1801604B7
0x180160276  lea     r15, [rsi+10h]
0x18016027a  mov     [rdi+50h], r14
0x18016027e  call    cs:__imp_GetTickCount
0x180160284  mov     r12d, eax
0x180160287  mov     edx, ebp; dwMilliseconds
0x180160289  mov     rcx, [r15+18h]; hHandle
0x18016028d  call    cs:__imp_WaitForSingleObject
0x180160293  mov     ebx, eax
0x180160295  cmp     eax, 0FFFFFFFFh
0x180160298  jz      loc_180160604
0x18016029e  cmp     eax, 102h
0x1801602a3  jz      loc_1801605A7
0x1801602a9  xor     r9d, r9d; bWait
0x1801602ac  lea     r8, [rsp+88h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1801602b1  mov     rdx, r15; lpOverlapped
0x1801602b4  mov     rcx, [rdi+40h]; hFile
0x1801602b8  call    cs:__imp_GetOverlappedResult
0x1801602be  test    eax, eax
0x1801602c0  jnz     loc_1801604E6
0x1801602c6  call    cs:__imp_GetLastError
0x1801602cc  mov     ebx, eax
0x1801602ce  cmp     eax, 3E3h
0x1801602d3  jnz     loc_18016047B
0x1801602d9  mov     rcx, rsi; struct SNI_Packet *
0x1801602dc  call    SNIPacketRelease
0x1801602e1  mov     [rdi+50h], r14
0x1801602e5  mov     [rsp+88h+NumberOfBytesTransferred], r14d
0x1801602ea  cmp     ebp, 0FFFFFFFFh
0x1801602ed  jz      loc_180160180
0x1801602f3  call    cs:__imp_GetTickCount
0x1801602f9  sub     r12d, eax
0x1801602fc  add     ebp, r12d
0x1801602ff  test    ebp, ebp
0x180160301  jg      loc_180160180
0x180160307  mov     ebx, 102h
0x18016030c  test    byte ptr cs:_bidGblFlags, 2
0x180160313  jz      short loc_18016034F
0x180160315  mov     rax, cs:off_180264238; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x18016031c  test    rax, rax
0x18016031f  jz      short loc_18016034F
0x180160321  mov     ecx, 0C3BFh; unsigned int
0x180160326  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x18016032b  mov     [rsp+88h+var_60], ebx
0x18016032f  mov     dword ptr [rsp+88h+lpOverlapped], eax
0x180160333  mov     r9d, [rdi+48h]
0x180160337  mov     r8, cs:off_180264238; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x18016033e  mov     edx, 96400h
0x180160343  mov     rcx, cs:off_180260EF0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18016034a  call    _bidTraceW
0x18016034f  mov     edx, ebx
0x180160351  mov     r8d, 0C3BFh
0x180160357  mov     ecx, [rdi+48h]
0x18016035a  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x18016035f  jmp     loc_180160670
0x180160364  test    al, 2
0x180160366  jz      short loc_1801603AB
0x180160368  mov     rax, cs:off_180264218; "<Np::ReadSync|ERR|SNI> ReadFile returne"...
0x18016036f  test    rax, rax
0x180160372  jz      short loc_1801603AB
0x180160374  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x18016037c  jz      short loc_1801603AB
0x18016037e  mov     rax, cs:off_180248050
0x180160385  mov     [rsp+88h+lpOverlapped], r14
0x18016038a  mov     r9, cs:off_180264218; "<Np::ReadSync|ERR|SNI> ReadFile returne"...
0x180160391  mov     r8d, 85400h
0x180160397  mov     rdx, cs:off_180260ED0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18016039e  mov     rcx, cs:_bidID
0x1801603a5  call    cs:__guard_dispatch_icall_fptr
0x1801603ab  mov     r9d, 1; bWait
0x1801603b1  lea     r8, [rsp+88h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1801603b6  mov     rdx, r15; lpOverlapped
0x1801603b9  mov     rcx, [rdi+40h]; hFile
0x1801603bd  call    cs:__imp_GetOverlappedResult
0x1801603c3  test    eax, eax
0x1801603c5  jnz     loc_1801604E6
0x1801603cb  call    cs:__imp_GetLastError
0x1801603d1  mov     ebx, eax
0x1801603d3  cmp     eax, 0EAh
0x1801603d8  jz      loc_1801604E6
0x1801603de  mov     ebp, 0C3B4h
0x1801603e3  test    byte ptr cs:_bidGblFlags, 2
0x1801603ea  jz      loc_1801604C8
0x1801603f0  mov     rax, cs:off_180264220; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x1801603f7  test    rax, rax
0x1801603fa  jz      loc_1801604C8
0x180160400  mov     ecx, ebp; unsigned int
0x180160402  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x180160407  mov     r8, cs:off_180264220; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x18016040e  mov     edx, 87800h
0x180160413  mov     rcx, cs:off_180260ED8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18016041a  jmp     loc_1801604B7
0x18016041f  mov     ebx, 0Eh
0x180160424  mov     ebp, 0C3B4h
0x180160429  test    byte ptr cs:_bidGblFlags, 2
0x180160430  jz      short loc_180160469
0x180160432  mov     rax, cs:off_180264200; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x180160439  test    rax, rax
0x18016043c  jz      short loc_180160469
0x18016043e  mov     ecx, ebp; unsigned int
0x180160440  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x180160445  mov     [rsp+88h+var_60], ebx
0x180160449  mov     dword ptr [rsp+88h+lpOverlapped], eax
0x18016044d  mov     r9d, [rdi+48h]
0x180160451  mov     r8, cs:off_180264200; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x180160458  mov     edx, 78800h
0x18016045d  mov     rcx, cs:off_180260EB8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180160464  call    _bidTraceW
0x180160469  mov     r8d, ebp
0x18016046c  mov     edx, ebx
0x18016046e  mov     ecx, [rdi+48h]
0x180160471  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x180160476  jmp     loc_180160670
0x18016047b  cmp     ebx, 0EAh
0x180160481  jz      short loc_1801604E6
0x180160483  mov     ebp, 0C3B4h
0x180160488  test    byte ptr cs:_bidGblFlags, 2
0x18016048f  jz      short loc_1801604C8
0x180160491  mov     rax, cs:off_180264240; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x180160498  test    rax, rax
0x18016049b  jz      short loc_1801604C8
0x18016049d  mov     ecx, ebp; unsigned int
0x18016049f  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x1801604a4  mov     r8, cs:off_180264240; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x1801604ab  mov     edx, 98C00h
0x1801604b0  mov     rcx, cs:off_180260EF8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801604b7  mov     [rsp+88h+var_60], ebx
0x1801604bb  mov     dword ptr [rsp+88h+lpOverlapped], eax
0x1801604bf  mov     r9d, [rdi+48h]
0x1801604c3  call    _bidTraceW
0x1801604c8  mov     r8d, ebp
0x1801604cb  mov     edx, ebx
0x1801604cd  mov     ecx, [rdi+48h]
0x1801604d0  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x1801604d5  cmp     ebx, 102h
0x1801604db  jz      loc_180160670
0x1801604e1  jmp     loc_18016065A
0x1801604e6  mov     eax, [rsp+88h+NumberOfBytesTransferred]
0x1801604ea  mov     [rsi+50h], eax
0x1801604ed  mov     [r13+0], rsi
0x1801604f1  mov     eax, cs:_bidGblFlags
0x1801604f7  and     eax, 24002h
0x1801604fc  cmp     eax, 24002h
0x180160501  jnz     short loc_18016052C
0x180160503  mov     rax, cs:off_180264248; "<Np::ReadSync|SNI> Receive Packet, Byte"...
0x18016050a  test    rax, rax
0x18016050d  jz      short loc_18016052C
0x18016050f  mov     r9d, [rsp+88h+NumberOfBytesTransferred]
0x180160514  mov     r8, cs:off_180264248; "<Np::ReadSync|SNI> Receive Packet, Byte"...
0x18016051b  mov     edx, 9CC00h
0x180160520  mov     rcx, cs:off_180260F00; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180160527  call    _bidTraceW
0x18016052c  mov     eax, cs:_bidGblFlags
0x180160532  and     eax, 24002h
0x180160537  cmp     eax, 24002h
0x18016053c  jnz     short loc_180160561
0x18016053e  mov     r8d, [rsi+58h]
0x180160542  add     r8, [rsi+48h]
0x180160546  mov     [rsp+88h+lpOverlapped], r14
0x18016054b  mov     r9d, [rsp+88h+NumberOfBytesTransferred]
0x180160550  mov     edx, 10h
0x180160555  mov     rcx, cs:_bidID
0x18016055c  call    _bidWriteBin
0x180160561  mov     eax, cs:_bidGblFlags
0x180160567  and     eax, 20002h
0x18016056c  cmp     eax, 20002h
0x180160571  jnz     loc_1801606AC
0x180160577  mov     rax, cs:off_180264250; "<Np::ReadSync|RET|SNI> %d{WINERR}\n"
0x18016057e  test    rax, rax
0x180160581  jz      loc_1801606AC
0x180160587  xor     r9d, r9d
0x18016058a  mov     r8, cs:off_180264250; "<Np::ReadSync|RET|SNI> %d{WINERR}\n"
0x180160591  mov     edx, 9D800h
0x180160596  mov     rcx, cs:off_180260F08; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18016059d  call    _bidTraceW
0x1801605a2  jmp     loc_1801606AC
0x1801605a7  mov     [rdi+50h], rsi
0x1801605ab  test    byte ptr cs:_bidGblFlags, 2
0x1801605b2  jz      short loc_1801605F2
0x1801605b4  mov     rax, cs:off_180264230; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x1801605bb  test    rax, rax
0x1801605be  jz      short loc_1801605F2
0x1801605c0  mov     ecx, 0C3BFh; unsigned int
0x1801605c5  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x1801605ca  mov     [rsp+88h+var_60], 102h
0x1801605d2  mov     dword ptr [rsp+88h+lpOverlapped], eax
0x1801605d6  mov     r9d, [rdi+48h]
0x1801605da  mov     r8, cs:off_180264230; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x1801605e1  mov     edx, 8FC00h
0x1801605e6  mov     rcx, cs:off_180260EE8; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x1801605ed  call    _bidTraceW
0x1801605f2  mov     r8d, 0C3BFh
0x1801605f8  mov     edx, ebx
0x1801605fa  mov     ecx, [rdi+48h]
0x1801605fd  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x180160602  jmp     short loc_180160670
0x180160604  mov     ebp, 0C3B4h
0x180160609  test    byte ptr cs:_bidGblFlags, 2
0x180160610  jz      short loc_18016064D
0x180160612  mov     rax, cs:off_180264228; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x180160619  test    rax, rax
0x18016061c  jz      short loc_18016064D
0x18016061e  mov     ecx, ebp; unsigned int
0x180160620  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x180160625  mov     [rsp+88h+var_60], 0FFFFFFFFh
0x18016062d  mov     dword ptr [rsp+88h+lpOverlapped], eax
0x180160631  mov     r9d, [rdi+48h]
0x180160635  mov     r8, cs:off_180264228; "<Np::ReadSync|ERR|SNI> ProviderNum: %d{"...
0x18016063c  mov     edx, 8E000h
0x180160641  mov     rcx, cs:off_180260EE0; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x180160648  call    _bidTraceW
0x18016064d  mov     r8d, ebp
0x180160650  mov     edx, ebx
  ... truncated ...
```
