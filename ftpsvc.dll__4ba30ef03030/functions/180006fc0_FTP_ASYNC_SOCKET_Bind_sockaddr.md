# FTP_ASYNC_SOCKET::Bind(sockaddr *)

- ea: `0x180006fc0`
- end: `0x1800070f0`
- name: `?Bind@FTP_ASYNC_SOCKET@@QEAAJPEAUsockaddr@@@Z`
- size: `304`
- prototype: `__int64 __fastcall(FTP_ASYNC_SOCKET *this, struct sockaddr *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180031df8`
- `0x18003f6b0`
- `0x180040e48`

## callees

- `0x180006fc0`
- `0x180046ff7`

## import_xrefs

- `WS2_32!__imp_bind` at `0x1800070ae`
- `WS2_32!__imp_bind` at `0x1800070ae`
- `WS2_32!__imp_getsockname` at `0x1800070c5`
- `WS2_32!__imp_getsockname` at `0x1800070c5`
- `WS2_32!__imp_setsockopt` at `0x18000706a`
- `WS2_32!__imp_setsockopt` at `0x18000706a`
- `WS2_32!__imp_WSAGetLastError` at `0x180007074`
- `WS2_32!__imp_WSAGetLastError` at `0x180007074`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180006ffc`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180006ffc`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800070d5`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800070d5`

## pseudocode

```c
__int64 __fastcall FTP_ASYNC_SOCKET::Bind(FTP_ASYNC_SOCKET *this, struct sockaddr *a2)
{
  bool v3; // zf
  int v5; // eax
  SOCKET v6; // rcx
  unsigned int v7; // ebx
  int Error; // eax
  size_t Size; // [rsp+50h] [rbp+8h] BYREF
  int optval; // [rsp+58h] [rbp+10h] BYREF

  v3 = a2->sa_family == 2;
  optval = 0;
  v5 = 16;
  if ( !v3 )
    v5 = 28;
  LODWORD(Size) = v5;
  CReaderWriterLock3::ReadLock((FTP_ASYNC_SOCKET *)((char *)this + 576));
  v6 = *((_QWORD *)this + 2);
  if ( v6 == -1 )
  {
    v7 = -2147023660;
  }
  else if ( (a2->sa_family != 23
          || *(_WORD *)&a2->sa_data[6]
          || *(_WORD *)&a2->sa_data[8]
          || *(_WORD *)&a2->sa_data[10]
          || *(_WORD *)&a2->sa_data[12]
          || a2[1].sa_family
          || *(_WORD *)a2[1].sa_data
          || *(_WORD *)&a2[1].sa_data[2]
          || *(_WORD *)&a2[1].sa_data[4]
          || setsockopt(v6, 41, 27, (const char *)&optval, 4) >= 0)
         && (memcpy_0((char *)this + 320, a2, (unsigned int)Size), bind(*((_QWORD *)this + 2), a2, Size) != -1)
         && !getsockname(*((_QWORD *)this + 2), (struct sockaddr *)this + 20, (int *)&Size) )
  {
    v7 = 0;
  }
  else
  {
    Error = WSAGetLastError();
    v7 = Error;
    if ( Error > 0 )
      v7 = (unsigned __int16)Error | 0x80070000;
  }
  CReaderWriterLock3::ReadUnlock((FTP_ASYNC_SOCKET *)((char *)this + 576));
  return v7;
}

```

## disassembly

```asm
0x180006fc0  mov     [rsp+arg_10], rbx
0x180006fc5  mov     [rsp+arg_18], rbp
0x180006fca  push    rsi
0x180006fcb  push    rdi
0x180006fcc  push    r14
0x180006fce  sub     rsp, 30h
0x180006fd2  mov     rdi, rcx
0x180006fd5  xor     r14d, r14d
0x180006fd8  cmp     word ptr [rdx], 2
0x180006fdc  mov     rbx, rdx
0x180006fdf  mov     [rsp+48h+optval], r14d
0x180006fe4  lea     eax, [r14+10h]
0x180006fe8  lea     ecx, [rax+0Ch]
0x180006feb  cmovnz  eax, ecx
0x180006fee  lea     rbp, [rdi+240h]
0x180006ff5  mov     rcx, rbp
0x180006ff8  mov     dword ptr [rsp+48h+Size], eax
0x180006ffc  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180007002  mov     rcx, [rdi+10h]; s
0x180007006  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000700a  jnz     short loc_180007016
0x18000700c  mov     ebx, 800704D4h
0x180007011  jmp     loc_1800070D2
0x180007016  cmp     word ptr [rbx], 17h
0x18000701a  jnz     short loc_18000708B
0x18000701c  cmp     [rbx+8], r14w
0x180007021  jnz     short loc_18000708B
0x180007023  cmp     [rbx+0Ah], r14w
0x180007028  jnz     short loc_18000708B
0x18000702a  cmp     [rbx+0Ch], r14w
0x18000702f  jnz     short loc_18000708B
0x180007031  cmp     [rbx+0Eh], r14w
0x180007036  jnz     short loc_18000708B
0x180007038  cmp     [rbx+10h], r14w
0x18000703d  jnz     short loc_18000708B
0x18000703f  cmp     [rbx+12h], r14w
0x180007044  jnz     short loc_18000708B
0x180007046  cmp     [rbx+14h], r14w
0x18000704b  jnz     short loc_18000708B
0x18000704d  cmp     [rbx+16h], r14w
0x180007052  jnz     short loc_18000708B
0x180007054  mov     edx, 29h ; ')'; level
0x180007059  mov     [rsp+48h+optlen], 4; optlen
0x180007061  lea     r9, [rsp+48h+optval]; optval
0x180007066  lea     r8d, [rdx-0Eh]; optname
0x18000706a  call    cs:__imp_setsockopt
0x180007070  test    eax, eax
0x180007072  jns     short loc_18000708B
0x180007074  call    cs:__imp_WSAGetLastError
0x18000707a  mov     ebx, eax
0x18000707c  test    eax, eax
0x18000707e  jle     short loc_1800070D2
0x180007080  movzx   ebx, ax
0x180007083  or      ebx, 80070000h
0x180007089  jmp     short loc_1800070D2
0x18000708b  mov     r8d, dword ptr [rsp+48h+Size]; Size
0x180007090  lea     rsi, [rdi+140h]
0x180007097  mov     rcx, rsi; void *
0x18000709a  mov     rdx, rbx; Src
0x18000709d  call    memcpy_0
0x1800070a2  mov     r8d, dword ptr [rsp+48h+Size]; namelen
0x1800070a7  mov     rdx, rbx; name
0x1800070aa  mov     rcx, [rdi+10h]; s
0x1800070ae  call    cs:__imp_bind
0x1800070b4  cmp     eax, 0FFFFFFFFh
0x1800070b7  jz      short loc_180007074
0x1800070b9  mov     rcx, [rdi+10h]; s
0x1800070bd  lea     r8, [rsp+48h+Size]; namelen
0x1800070c2  mov     rdx, rsi; name
0x1800070c5  call    cs:__imp_getsockname
0x1800070cb  test    eax, eax
0x1800070cd  jnz     short loc_180007074
0x1800070cf  mov     ebx, r14d
0x1800070d2  mov     rcx, rbp
0x1800070d5  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x1800070db  mov     rbp, [rsp+48h+arg_18]
0x1800070e0  mov     eax, ebx
0x1800070e2  mov     rbx, [rsp+48h+arg_10]
0x1800070e7  add     rsp, 30h
0x1800070eb  pop     r14
0x1800070ed  pop     rdi
0x1800070ee  pop     rsi
0x1800070ef  retn
```
