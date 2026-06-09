# DnsFwUdpReceive(_DNS_FORWARD_SOCKET *)

- ea: `0x1800447bc`
- end: `0x1800449e8`
- name: `?DnsFwUdpReceive@@YAKPEAU_DNS_FORWARD_SOCKET@@@Z`
- size: `556`
- prototype: `__int64 __fastcall(struct _DNS_FORWARD_SOCKET *)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18004368c`
- `0x180043eb8`

## callees

- `0x180008b00`
- `0x1800432fc`
- `0x18004345c`
- `0x18004368c`
- `0x1800447bc`
- `0x180046ec0`
- `0x180086b1c`
- `0x180086f24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800448ac`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800448ac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180044947`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180044947`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800448d0`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x1800448d0`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180044961`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180044961`
- `WS2_32!WSARecvFrom` at `0x18004491d`
- `WS2_32!WSARecvFrom` at `0x18004491d`
- `WS2_32!__imp_WSAGetLastError` at `0x180044928`
- `WS2_32!__imp_WSAGetLastError` at `0x180044928`

## pseudocode

```c
__int64 __fastcall DnsFwUdpReceive(struct _DNS_FORWARD_SOCKET *a1)
{
  unsigned int v2; // ebx
  int v3; // eax
  unsigned int v4; // esi
  struct _DNS_FORWARD_CONTEXT *v5; // r14
  PTP_IO *v6; // r15
  int Error; // eax
  unsigned int v8; // eax
  struct _DNS_FORWARD_CONTEXT *lpMem; // [rsp+58h] [rbp-18h] BYREF

  lpMem = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_q(1035, 24, WPP_ff0c092eea6b3fcea4c12a75948a1cff_Traceguids, a1);
  if ( !a1 )
  {
    v2 = -2147024809;
    goto LABEL_19;
  }
  v3 = DnsFwCreateContext(a1, &lpMem);
  v2 = v3;
  if ( v3 > 0 )
    v2 = (unsigned __int16)v3 | 0x80070000;
  if ( (v2 & 0x80000000) == 0 )
  {
    v4 = 0;
    *((_DWORD *)lpMem + 9) = 3;
    *((_DWORD *)lpMem + 91) = 0;
    *((_DWORD *)lpMem + 90) = 128;
    *((_QWORD *)lpMem + 50) = *((_QWORD *)lpMem + 46);
    *((_DWORD *)lpMem + 98) = *((_DWORD *)lpMem + 95);
    v5 = lpMem;
    _InterlockedIncrement((volatile signed __int32 *)lpMem + 8);
    AcquireSRWLockShared((PSRWLOCK)a1 + 4);
    v6 = (PTP_IO *)((char *)a1 + 72);
    if ( *((_QWORD *)a1 + 6) == -1 )
    {
      v2 = 995;
LABEL_15:
      ReleaseSRWLockShared((PSRWLOCK)a1 + 4);
      if ( v5 )
        DnsFwDerefContext(v5);
      if ( v4 )
      {
        CancelThreadpoolIo(*v6);
        DnsFwIoCompletionRoutine(lpMem, v4, 0);
        lpMem = 0;
      }
      goto LABEL_19;
    }
    v2 = 0;
    StartThreadpoolIo(*v6);
    if ( WSARecvFrom(
           *((_QWORD *)a1 + 6),
           (LPWSABUF)((char *)v5 + 392),
           1u,
           0,
           (LPDWORD)v5 + 91,
           (struct sockaddr *)((char *)v5 + 216),
           (LPINT)v5 + 90,
           (LPWSAOVERLAPPED)v5 + 15,
           0) == -1 )
    {
      Error = WSAGetLastError();
      v4 = Error;
      if ( Error == 997 )
      {
        v4 = 0;
      }
      else if ( Error )
      {
        goto LABEL_15;
      }
    }
    lpMem = 0;
    goto LABEL_15;
  }
LABEL_19:
  if ( lpMem )
  {
    DnsFwDerefContext(lpMem);
    lpMem = 0;
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
  {
    v8 = WX_WIN32_FROM_HR(v2);
    WPP_SF_d(1035, 25, WPP_ff0c092eea6b3fcea4c12a75948a1cff_Traceguids, v8);
  }
  return WX_WIN32_FROM_HR(v2);
}

```

## disassembly

```asm
0x1800447bc  mov     [rsp-28h+arg_8], rbx
0x1800447c1  mov     [rsp-28h+arg_10], rsi
0x1800447c6  push    rbp
0x1800447c7  push    rdi
0x1800447c8  push    r12
0x1800447ca  push    r14
0x1800447cc  push    r15
0x1800447ce  mov     rbp, rsp
0x1800447d1  sub     rsp, 70h
0x1800447d5  mov     rax, cs:__security_cookie
0x1800447dc  xor     rax, rsp
0x1800447df  mov     [rbp+var_10], rax
0x1800447e3  mov     rdi, rcx
0x1800447e6  mov     [rbp+var_1C], 0
0x1800447ed  mov     [rbp+lpMem], 0
0x1800447f5  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800447fc  jz      short loc_180044817
0x1800447fe  mov     edx, 18h
0x180044803  lea     r8, WPP_ff0c092eea6b3fcea4c12a75948a1cff_Traceguids
0x18004480a  mov     ecx, 40Bh
0x18004480f  mov     r9, rdi
0x180044812  call    WPP_SF_q
0x180044817  test    rdi, rdi
0x18004481a  jnz     short loc_18004482D
0x18004481c  mov     ebx, 80070057h
0x180044821  mov     [rbp+var_1C], 273h
0x180044828  jmp     loc_18004497D
0x18004482d  lea     rdx, [rbp+lpMem]; struct _DNS_FORWARD_CONTEXT **
0x180044831  mov     rcx, rdi; struct _DNS_FORWARD_SOCKET *
0x180044834  call    ?DnsFwCreateContext@@YAKPEAU_DNS_FORWARD_SOCKET@@PEAPEAU_DNS_FORWARD_CONTEXT@@@Z; DnsFwCreateContext(_DNS_FORWARD_SOCKET *,_DNS_FORWARD_CONTEXT * *)
0x180044839  mov     ebx, eax
0x18004483b  test    eax, eax
0x18004483d  jle     short loc_180044848
0x18004483f  movzx   ebx, ax
0x180044842  or      ebx, 80070000h
0x180044848  test    ebx, ebx
0x18004484a  jns     short loc_180044858
0x18004484c  mov     [rbp+var_1C], 279h
0x180044853  jmp     loc_18004497D
0x180044858  mov     rax, [rbp+lpMem]
0x18004485c  xor     esi, esi
0x18004485e  mov     dword ptr [rax+24h], 3
0x180044865  mov     rax, [rbp+lpMem]
0x180044869  mov     [rax+16Ch], esi
0x18004486f  mov     rax, [rbp+lpMem]
0x180044873  mov     dword ptr [rax+168h], 80h
0x18004487d  mov     rcx, [rbp+lpMem]
0x180044881  mov     rax, [rcx+170h]
0x180044888  mov     [rcx+190h], rax
0x18004488f  mov     rcx, [rbp+lpMem]
0x180044893  mov     eax, [rcx+17Ch]
0x180044899  mov     [rcx+188h], eax
0x18004489f  mov     r14, [rbp+lpMem]
0x1800448a3  lock inc dword ptr [r14+20h]
0x1800448a8  lea     rcx, [rdi+20h]; SRWLock
0x1800448ac  call    cs:__imp_AcquireSRWLockShared
0x1800448b2  cmp     qword ptr [rdi+30h], 0FFFFFFFFFFFFFFFFh
0x1800448b7  lea     r15, [rdi+48h]
0x1800448bb  jnz     short loc_1800448CB
0x1800448bd  mov     ebx, 3E3h
0x1800448c2  mov     [rbp+var_1C], 294h
0x1800448c9  jmp     short loc_180044943
0x1800448cb  mov     rcx, [r15]; pio
0x1800448ce  xor     ebx, ebx
0x1800448d0  call    cs:__imp_StartThreadpoolIo
0x1800448d6  mov     [rsp+70h+lpCompletionRoutine], rbx; lpCompletionRoutine
0x1800448db  lea     r8, [r14+0D8h]
0x1800448e2  lea     rax, [r14+1E0h]
0x1800448e9  mov     [rsp+70h+lpOverlapped], rax; lpOverlapped
0x1800448ee  lea     rcx, [r14+168h]
0x1800448f5  mov     [rsp+70h+lpFromlen], rcx; lpFromlen
0x1800448fa  lea     r9, [r14+16Ch]
0x180044901  mov     rcx, [rdi+30h]; s
0x180044905  lea     rdx, [r14+188h]; lpBuffers
0x18004490c  mov     [rsp+70h+lpFrom], r8; lpFrom
0x180044911  lea     r8d, [rbx+1]; dwBufferCount
0x180044915  mov     [rsp+70h+lpFlags], r9; lpFlags
0x18004491a  xor     r9d, r9d; lpNumberOfBytesRecvd
0x18004491d  call    cs:__imp_WSARecvFrom
0x180044923  cmp     eax, 0FFFFFFFFh
0x180044926  jnz     short loc_18004493F
0x180044928  call    cs:__imp_WSAGetLastError
0x18004492e  mov     esi, eax
0x180044930  cmp     eax, 3E5h
0x180044935  jnz     short loc_18004493B
0x180044937  xor     esi, esi
0x180044939  jmp     short loc_18004493F
0x18004493b  test    eax, eax
0x18004493d  jnz     short loc_180044943
0x18004493f  mov     [rbp+lpMem], rbx
0x180044943  lea     rcx, [rdi+20h]; SRWLock
0x180044947  call    cs:__imp_ReleaseSRWLockShared
0x18004494d  test    r14, r14
0x180044950  jz      short loc_18004495A
0x180044952  mov     rcx, r14; lpMem
0x180044955  call    ?DnsFwDerefContext@@YAXPEAU_DNS_FORWARD_CONTEXT@@@Z; DnsFwDerefContext(_DNS_FORWARD_CONTEXT *)
0x18004495a  test    esi, esi
0x18004495c  jz      short loc_18004497D
0x18004495e  mov     rcx, [r15]; pio
0x180044961  call    cs:__imp_CancelThreadpoolIo
0x180044967  mov     rcx, [rbp+lpMem]; lpMem
0x18004496b  xor     r8d, r8d; unsigned int
0x18004496e  mov     edx, esi; unsigned int
0x180044970  call    ?DnsFwIoCompletionRoutine@@YAKPEAU_DNS_FORWARD_CONTEXT@@KK@Z; DnsFwIoCompletionRoutine(_DNS_FORWARD_CONTEXT *,ulong,ulong)
0x180044975  mov     [rbp+lpMem], 0
0x18004497d  mov     rcx, [rbp+lpMem]; lpMem
0x180044981  test    rcx, rcx
0x180044984  jz      short loc_180044993
0x180044986  call    ?DnsFwDerefContext@@YAXPEAU_DNS_FORWARD_CONTEXT@@@Z; DnsFwDerefContext(_DNS_FORWARD_CONTEXT *)
0x18004498b  mov     [rbp+lpMem], 0
0x180044993  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004499a  jz      short loc_1800449BC
0x18004499c  mov     ecx, ebx
0x18004499e  call    WX_WIN32_FROM_HR
0x1800449a3  mov     r9d, eax
0x1800449a6  lea     r8, WPP_ff0c092eea6b3fcea4c12a75948a1cff_Traceguids
0x1800449ad  mov     edx, 19h
0x1800449b2  mov     ecx, 40Bh
0x1800449b7  call    WPP_SF_d
0x1800449bc  mov     ecx, ebx
0x1800449be  call    WX_WIN32_FROM_HR
0x1800449c3  mov     rcx, [rbp+var_10]
0x1800449c7  xor     rcx, rsp; StackCookie
0x1800449ca  call    __security_check_cookie
0x1800449cf  lea     r11, [rsp+70h+var_s0]
0x1800449d4  mov     rbx, [r11+38h]
0x1800449d8  mov     rsi, [r11+40h]
0x1800449dc  mov     rsp, r11
0x1800449df  pop     r15
0x1800449e1  pop     r14
0x1800449e3  pop     r12
0x1800449e5  pop     rdi
0x1800449e6  pop     rbp
0x1800449e7  retn
```
