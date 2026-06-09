# FTP_ASYNC_SOCKET::Initialize(ulong)

- ea: `0x180007578`
- end: `0x1800076b0`
- name: `?Initialize@FTP_ASYNC_SOCKET@@QEAAJK@Z`
- size: `312`
- prototype: `__int64 __fastcall(FTP_ASYNC_SOCKET *__hidden this, unsigned int af)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180031aa0`
- `0x180031df8`
- `0x18003ed9c`
- `0x18003f6b0`
- `0x180040e48`

## callees

- `0x1800070f8`
- `0x180007578`
- `0x180049010`

## import_xrefs

- `WS2_32!WSASocketW` at `0x1800075fe`
- `WS2_32!WSASocketW` at `0x1800075fe`
- `WS2_32!__imp_setsockopt` at `0x18000763d`
- `WS2_32!__imp_setsockopt` at `0x18000765f`
- `WS2_32!__imp_setsockopt` at `0x18000763d`
- `WS2_32!__imp_setsockopt` at `0x18000765f`
- `WS2_32!__imp_WSAGetLastError` at `0x18000760e`
- `WS2_32!__imp_WSAGetLastError` at `0x18000760e`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800075a5`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800075a5`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000768c`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x18000768c`

## pseudocode

```c
__int64 __fastcall FTP_ASYNC_SOCKET::Initialize(FTP_ASYNC_SOCKET *this, int af)
{
  CReaderWriterLock3 *v2; // rsi
  __int64 v5; // rcx
  char *v6; // rax
  __int64 v7; // r8
  char *v8; // rax
  SOCKET v9; // rax
  int Error; // eax
  signed int v11; // ebx
  int v13; // [rsp+40h] [rbp+8h] BYREF
  int optval; // [rsp+48h] [rbp+10h] BYREF

  v2 = (FTP_ASYNC_SOCKET *)((char *)this + 576);
  optval = 1;
  v13 = 10000;
  CReaderWriterLock3::WriteLock((FTP_ASYNC_SOCKET *)((char *)this + 576));
  v5 = 128;
  v6 = (char *)this + 320;
  v7 = 128;
  do
  {
    *v6++ = 0;
    --v7;
  }
  while ( v7 );
  v8 = (char *)this + 448;
  do
  {
    *v8++ = 0;
    --v5;
  }
  while ( v5 );
  *((_DWORD *)this + 177) = 0x10000;
  *((_DWORD *)this + 3) = af;
  v9 = WSASocketW(af, 1, 6, 0, 0, 1u);
  *((_QWORD *)this + 2) = v9;
  if ( v9 == -1
    || setsockopt(v9, 6, 1, (const char *)&optval, 4)
    || setsockopt(*((_QWORD *)this + 2), 0xFFFF, 4101, (const char *)&v13, 4) )
  {
    Error = WSAGetLastError();
    v11 = Error;
    if ( Error > 0 )
      v11 = (unsigned __int16)Error | 0x80070000;
  }
  else
  {
    v11 = (*(__int64 (__fastcall **)(FTP_SERVERP *, _QWORD))(*(_QWORD *)g_pFtpServer + 72LL))(
            g_pFtpServer,
            *((_QWORD *)this + 2));
    if ( v11 >= 0 )
      v11 = 0;
  }
  CReaderWriterLock3::WriteUnlock(v2);
  if ( v11 < 0 )
    FTP_ASYNC_SOCKET::Close(this);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180007578  mov     rax, rsp
0x18000757b  mov     [rax+18h], rbx
0x18000757f  mov     [rax+20h], rsi
0x180007583  push    rdi
0x180007584  sub     rsp, 30h
0x180007588  lea     rsi, [rcx+240h]
0x18000758f  mov     dword ptr [rax+10h], 1
0x180007596  mov     rdi, rcx
0x180007599  mov     dword ptr [rax+8], 2710h
0x1800075a0  mov     rcx, rsi
0x1800075a3  mov     ebx, edx
0x1800075a5  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800075ab  mov     ecx, 80h
0x1800075b0  lea     rax, [rdi+140h]
0x1800075b7  mov     r8d, ecx
0x1800075ba  mov     byte ptr [rax], 0
0x1800075bd  inc     rax
0x1800075c0  sub     r8, 1
0x1800075c4  jnz     short loc_1800075BA
0x1800075c6  lea     rax, [rdi+1C0h]
0x1800075cd  mov     byte ptr [rax], 0
0x1800075d0  inc     rax
0x1800075d3  sub     rcx, 1
0x1800075d7  jnz     short loc_1800075CD
0x1800075d9  lea     edx, [rcx+1]; type
0x1800075dc  mov     [rsp+38h+dwFlags], 1; dwFlags
0x1800075e4  mov     [rsp+38h+g], ecx; g
0x1800075e8  lea     r8d, [rcx+6]; protocol
0x1800075ec  mov     ecx, ebx; af
0x1800075ee  mov     dword ptr [rdi+2C4h], 10000h
0x1800075f8  xor     r9d, r9d; lpProtocolInfo
0x1800075fb  mov     [rdi+0Ch], ebx
0x1800075fe  call    cs:__imp_WSASocketW
0x180007604  mov     [rdi+10h], rax
0x180007608  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000760c  jnz     short loc_180007625
0x18000760e  call    cs:__imp_WSAGetLastError
0x180007614  mov     ebx, eax
0x180007616  test    eax, eax
0x180007618  jle     short loc_180007689
0x18000761a  movzx   ebx, ax
0x18000761d  or      ebx, 80070000h
0x180007623  jmp     short loc_180007689
0x180007625  mov     ebx, 4
0x18000762a  lea     r9, [rsp+38h+optval]; optval
0x18000762f  mov     rcx, rax; s
0x180007632  mov     [rsp+38h+g], ebx; optlen
0x180007636  lea     edx, [rbx+2]; level
0x180007639  lea     r8d, [rbx-3]; optname
0x18000763d  call    cs:__imp_setsockopt
0x180007643  test    eax, eax
0x180007645  jnz     short loc_18000760E
0x180007647  mov     rcx, [rdi+10h]; s
0x18000764b  lea     r9, [rsp+38h+arg_0]; optval
0x180007650  mov     edx, 0FFFFh; level
0x180007655  mov     [rsp+38h+g], ebx; optlen
0x180007659  mov     r8d, 1005h; optname
0x18000765f  call    cs:__imp_setsockopt
0x180007665  test    eax, eax
0x180007667  jnz     short loc_18000760E
0x180007669  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180007670  mov     rdx, [rdi+10h]
0x180007674  mov     rax, [rcx]
0x180007677  mov     rax, [rax+48h]
0x18000767b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007680  xor     edx, edx
0x180007682  mov     ebx, eax
0x180007684  test    eax, eax
0x180007686  cmovns  ebx, edx
0x180007689  mov     rcx, rsi
0x18000768c  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180007692  test    ebx, ebx
0x180007694  jns     short loc_18000769E
0x180007696  mov     rcx, rdi; this
0x180007699  call    ?Close@FTP_ASYNC_SOCKET@@QEAAXXZ; FTP_ASYNC_SOCKET::Close(void)
0x18000769e  mov     rsi, [rsp+38h+arg_18]
0x1800076a3  mov     eax, ebx
0x1800076a5  mov     rbx, [rsp+38h+arg_10]
0x1800076aa  add     rsp, 30h
0x1800076ae  pop     rdi
0x1800076af  retn
```
