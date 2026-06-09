# FTP_ASYNC_SOCKET::OnNewConnectionCompletion(void)

- ea: `0x180007878`
- end: `0x180007af8`
- name: `?OnNewConnectionCompletion@FTP_ASYNC_SOCKET@@QEAAXXZ`
- size: `640`
- prototype: `void __fastcall(FTP_ASYNC_SOCKET *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180006f70`

## callees

- `0x180007878`
- `0x180046ff7`
- `0x18004700f`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `WS2_32!__imp_getpeername` at `0x1800079e2`
- `WS2_32!__imp_getpeername` at `0x1800079e2`
- `WS2_32!__imp_getsockname` at `0x1800079a7`
- `WS2_32!__imp_getsockname` at `0x1800079a7`
- `WS2_32!__imp_setsockopt` at `0x180007985`
- `WS2_32!__imp_setsockopt` at `0x180007985`
- `WS2_32!__imp_WSAGetLastError` at `0x1800079b1`
- `WS2_32!__imp_WSAGetLastError` at `0x1800079b1`
- `MSWSOCK!GetAcceptExSockaddrs` at `0x18000793f`
- `MSWSOCK!GetAcceptExSockaddrs` at `0x18000793f`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800078e0`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800078e0`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180007aac`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180007aac`

## pseudocode

```c
void __fastcall FTP_ASYNC_SOCKET::OnNewConnectionCompletion(FTP_ASYNC_SOCKET *this)
{
  SOCKET v2; // rcx
  int v3; // ebx
  unsigned int v4; // eax
  unsigned int v5; // r15d
  struct sockaddr *p_name; // rdi
  struct sockaddr *v7; // r14
  SOCKET v8; // rcx
  int Error; // eax
  SOCKET v10; // rcx
  __int64 v11; // rax
  int namelen; // [rsp+40h] [rbp-C0h] BYREF
  int Size[3]; // [rsp+44h] [rbp-BCh] BYREF
  struct sockaddr *LocalSockaddr; // [rsp+50h] [rbp-B0h] BYREF
  struct sockaddr v15; // [rsp+60h] [rbp-A0h] BYREF
  sockaddr name; // [rsp+E0h] [rbp-20h] BYREF

  LocalSockaddr = 0;
  namelen = 0;
  memset(Size, 0, sizeof(Size));
  memset_0(&name, 0, 0x80u);
  memset_0(&v15, 0, 0x80u);
  CReaderWriterLock3::WriteLock((FTP_ASYNC_SOCKET *)((char *)this + 576));
  v2 = *((_QWORD *)this + 2);
  if ( v2 == -1 )
  {
    v3 = -2147023660;
    goto LABEL_23;
  }
  if ( *((_DWORD *)this + 79) )
  {
    *((_DWORD *)this + 79) = 0;
    GetAcceptExSockaddrs(
      (char *)this + 24,
      0,
      0x90u,
      0x90u,
      &LocalSockaddr,
      &namelen,
      (struct sockaddr **)&Size[1],
      Size);
    v4 = namelen;
    if ( (unsigned int)namelen > 0x80 || (v5 = Size[0], v3 = 0, Size[0] > 0x80u) )
    {
      v3 = -2147024809;
      goto LABEL_23;
    }
    p_name = LocalSockaddr;
    v7 = *(struct sockaddr **)&Size[1];
    goto LABEL_14;
  }
  v3 = setsockopt(v2, 0xFFFF, 28688, 0, 0);
  if ( v3 < 0 )
    goto LABEL_23;
  v8 = *((_QWORD *)this + 2);
  namelen = 128;
  if ( !getsockname(v8, &name, &namelen) )
  {
    v10 = *((_QWORD *)this + 2);
    Size[0] = 128;
    if ( !getpeername(v10, &v15, Size) )
    {
      v4 = namelen;
      v7 = &v15;
      v5 = Size[0];
      p_name = &name;
      *(_QWORD *)&Size[1] = &v15;
      LocalSockaddr = &name;
LABEL_14:
      memcpy_0((char *)this + 320, p_name, v4);
      memcpy_0((char *)this + 448, v7, v5);
      if ( p_name->sa_family == 23
        && !*(_WORD *)&p_name->sa_data[6]
        && !*(_WORD *)&p_name->sa_data[8]
        && !*(_WORD *)&p_name->sa_data[10]
        && !*(_WORD *)&p_name->sa_data[12]
        && !p_name[1].sa_family
        && *(_WORD *)p_name[1].sa_data == 0xFFFF )
      {
        *((_WORD *)this + 224) = 2;
        *((_DWORD *)this + 113) = *(_DWORD *)&v7[1].sa_data[2];
        *((_WORD *)this + 225) = *(_WORD *)v7->sa_data;
        *((_WORD *)this + 160) = 2;
        *((_DWORD *)this + 81) = *(_DWORD *)&p_name[1].sa_data[2];
        *((_WORD *)this + 161) = *(_WORD *)p_name->sa_data;
        *((_DWORD *)this + 3) = 2;
      }
      *((_DWORD *)this + 78) = 1;
      goto LABEL_23;
    }
  }
  Error = WSAGetLastError();
  v3 = Error;
  if ( Error > 0 )
    v3 = (unsigned __int16)Error | 0x80070000;
LABEL_23:
  CReaderWriterLock3::WriteUnlock((FTP_ASYNC_SOCKET *)((char *)this + 576));
  v11 = *((_QWORD *)this + 80);
  *((_QWORD *)this + 80) = 0;
  if ( v11 )
  {
    *(_DWORD *)(v11 + 68) = v3;
    *(_QWORD *)(v11 + 72) = 0;
    (*(void (__fastcall **)(__int64))(v11 + 8))(v11);
  }
}

```

## disassembly

```asm
0x180007878  push    rbp
0x18000787a  push    rbx
0x18000787b  push    rsi
0x18000787c  push    rdi
0x18000787d  push    r12
0x18000787f  push    r13
0x180007881  push    r14
0x180007883  push    r15
0x180007885  lea     rbp, [rsp-78h]
0x18000788a  sub     rsp, 178h
0x180007891  mov     rax, cs:__security_cookie
0x180007898  xor     rax, rsp
0x18000789b  mov     [rbp+0B0h+var_50], rax
0x18000789f  xor     edi, edi
0x1800078a1  mov     rsi, rcx
0x1800078a4  mov     r14d, 80h
0x1800078aa  mov     [rsp+1B0h+var_160], rdi
0x1800078af  mov     r8d, r14d; Size
0x1800078b2  mov     [rsp+1B0h+namelen], edi
0x1800078b6  xor     edx, edx; Val
0x1800078b8  mov     qword ptr [rsp+1B0h+Size+4], rdi
0x1800078bd  lea     rcx, [rbp+0B0h+name]; void *
0x1800078c1  mov     dword ptr [rsp+1B0h+Size], edi
0x1800078c5  call    memset_0
0x1800078ca  mov     r8d, r14d; Size
0x1800078cd  lea     rcx, [rsp+1B0h+var_150]; void *
0x1800078d2  xor     edx, edx; Val
0x1800078d4  call    memset_0
0x1800078d9  lea     rcx, [rsi+240h]
0x1800078e0  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800078e6  mov     rcx, [rsi+10h]; s
0x1800078ea  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800078ee  jnz     short loc_1800078FA
0x1800078f0  mov     ebx, 800704D4h
0x1800078f5  jmp     loc_180007AA5
0x1800078fa  cmp     [rsi+13Ch], edi
0x180007900  jz      short loc_180007973
0x180007902  lea     rax, [rsp+1B0h+Size]
0x180007907  mov     [rsi+13Ch], edi
0x18000790d  mov     [rsp+1B0h+RemoteSockaddrLength], rax; RemoteSockaddrLength
0x180007912  lea     rcx, [rsi+18h]; lpOutputBuffer
0x180007916  lea     rax, [rsp+1B0h+Size+4]
0x18000791b  mov     r8d, 90h; dwLocalAddressLength
0x180007921  mov     [rsp+1B0h+RemoteSockaddr], rax; RemoteSockaddr
0x180007926  mov     r9d, r8d; dwRemoteAddressLength
0x180007929  lea     rax, [rsp+1B0h+namelen]
0x18000792e  xor     edx, edx; dwReceiveDataLength
0x180007930  mov     [rsp+1B0h+LocalSockaddrLength], rax; LocalSockaddrLength
0x180007935  lea     rax, [rsp+1B0h+var_160]
0x18000793a  mov     [rsp+1B0h+LocalSockaddr], rax; LocalSockaddr
0x18000793f  call    cs:__imp_GetAcceptExSockaddrs
0x180007945  mov     eax, [rsp+1B0h+namelen]
0x180007949  cmp     eax, r14d
0x18000794c  ja      short loc_180007969
0x18000794e  mov     r15d, dword ptr [rsp+1B0h+Size]
0x180007953  mov     ebx, edi
0x180007955  cmp     r15d, r14d
0x180007958  ja      short loc_180007969
0x18000795a  mov     rdi, [rsp+1B0h+var_160]
0x18000795f  mov     r14, qword ptr [rsp+1B0h+Size+4]
0x180007964  jmp     loc_180007A08
0x180007969  mov     ebx, 80070057h
0x18000796e  jmp     loc_180007AA5
0x180007973  xor     r9d, r9d; optval
0x180007976  mov     dword ptr [rsp+1B0h+LocalSockaddr], edi; optlen
0x18000797a  mov     edx, 0FFFFh; level
0x18000797f  mov     r8d, 7010h; optname
0x180007985  call    cs:__imp_setsockopt
0x18000798b  mov     ebx, eax
0x18000798d  test    eax, eax
0x18000798f  js      loc_180007AA5
0x180007995  mov     rcx, [rsi+10h]; s
0x180007999  lea     r8, [rsp+1B0h+namelen]; namelen
0x18000799e  lea     rdx, [rbp+0B0h+name]; name
0x1800079a2  mov     [rsp+1B0h+namelen], r14d
0x1800079a7  call    cs:__imp_getsockname
0x1800079ad  test    eax, eax
0x1800079af  jz      short loc_1800079CF
0x1800079b1  call    cs:__imp_WSAGetLastError
0x1800079b7  mov     ebx, eax
0x1800079b9  test    eax, eax
0x1800079bb  jle     loc_180007AA5
0x1800079c1  movzx   ebx, ax
0x1800079c4  or      ebx, 80070000h
0x1800079ca  jmp     loc_180007AA5
0x1800079cf  mov     rcx, [rsi+10h]; s
0x1800079d3  lea     r8, [rsp+1B0h+Size]; namelen
0x1800079d8  lea     rdx, [rsp+1B0h+var_150]; name
0x1800079dd  mov     dword ptr [rsp+1B0h+Size], r14d
0x1800079e2  call    cs:__imp_getpeername
0x1800079e8  test    eax, eax
0x1800079ea  jnz     short loc_1800079B1
0x1800079ec  mov     eax, [rsp+1B0h+namelen]
0x1800079f0  lea     r14, [rsp+1B0h+var_150]
0x1800079f5  mov     r15d, dword ptr [rsp+1B0h+Size]
0x1800079fa  lea     rdi, [rbp+0B0h+name]
0x1800079fe  mov     qword ptr [rsp+1B0h+Size+4], r14
0x180007a03  mov     [rsp+1B0h+var_160], rdi
0x180007a08  lea     r12, [rsi+140h]
0x180007a0f  mov     r8d, eax; Size
0x180007a12  mov     rcx, r12; void *
0x180007a15  mov     rdx, rdi; Src
0x180007a18  call    memcpy_0
0x180007a1d  lea     r13, [rsi+1C0h]
0x180007a24  mov     r8d, r15d; Size
0x180007a27  mov     rcx, r13; void *
0x180007a2a  mov     rdx, r14; Src
0x180007a2d  call    memcpy_0
0x180007a32  cmp     word ptr [rdi], 17h
0x180007a36  jnz     short loc_180007A99
0x180007a38  xor     eax, eax
0x180007a3a  cmp     [rdi+8], ax
0x180007a3e  jnz     short loc_180007A99
0x180007a40  cmp     [rdi+0Ah], ax
0x180007a44  jnz     short loc_180007A99
0x180007a46  cmp     [rdi+0Ch], ax
0x180007a4a  jnz     short loc_180007A99
0x180007a4c  cmp     [rdi+0Eh], ax
0x180007a50  jnz     short loc_180007A99
0x180007a52  cmp     [rdi+10h], ax
0x180007a56  jnz     short loc_180007A99
0x180007a58  mov     eax, 0FFFFh
0x180007a5d  cmp     [rdi+12h], ax
0x180007a61  jnz     short loc_180007A99
0x180007a63  mov     ecx, 2
0x180007a68  mov     [r13+0], cx
0x180007a6d  mov     eax, [r14+14h]
0x180007a71  mov     [r13+4], eax
0x180007a75  movzx   eax, word ptr [r14+2]
0x180007a7a  mov     [r13+2], ax
0x180007a7f  mov     [r12], cx
0x180007a84  mov     eax, [rdi+14h]
0x180007a87  mov     [r12+4], eax
0x180007a8c  movzx   eax, word ptr [rdi+2]
0x180007a90  mov     [r12+2], ax
0x180007a96  mov     [rsi+0Ch], ecx
0x180007a99  mov     dword ptr [rsi+138h], 1
0x180007aa3  xor     edi, edi
0x180007aa5  lea     rcx, [rsi+240h]
0x180007aac  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180007ab2  mov     rax, [rsi+280h]
0x180007ab9  mov     [rsi+280h], rdi
0x180007ac0  test    rax, rax
0x180007ac3  jz      short loc_180007AD8
0x180007ac5  mov     [rax+44h], ebx
0x180007ac8  mov     rcx, rax
0x180007acb  mov     [rax+48h], rdi
0x180007acf  mov     rax, [rax+8]
0x180007ad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ad8  mov     rcx, [rbp+0B0h+var_50]
0x180007adc  xor     rcx, rsp; StackCookie
0x180007adf  call    __security_check_cookie
0x180007ae4  add     rsp, 178h
0x180007aeb  pop     r15
0x180007aed  pop     r14
0x180007aef  pop     r13
0x180007af1  pop     r12
0x180007af3  pop     rdi
0x180007af4  pop     rsi
0x180007af5  pop     rbx
0x180007af6  pop     rbp
0x180007af7  retn
```
