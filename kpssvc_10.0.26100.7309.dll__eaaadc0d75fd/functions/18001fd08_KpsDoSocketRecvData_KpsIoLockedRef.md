# KpsDoSocketRecvData(KpsIoLockedRef &)

- ea: `0x18001fd08`
- end: `0x180020030`
- name: `?KpsDoSocketRecvData@@YAXAEAVKpsIoLockedRef@@@Z`
- size: `808`
- prototype: `void __fastcall(struct _KPS_IO **this)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180022a5c`

## callees

- `0x18001ae38`
- `0x18001ae7c`
- `0x18001e728`
- `0x18001fd08`
- `0x180022d38`
- `0x180024be0`
- `0x180026a08`
- `0x180026d9c`
- `0x18002cc3c`
- `0x180030168`

## import_xrefs

- `WS2_32!WSARecv` at `0x18001fec8`
- `WS2_32!WSARecv` at `0x18001fec8`
- `WS2_32!__imp_ntohl` at `0x18001fd76`
- `WS2_32!__imp_ntohl` at `0x18001fd76`
- `WS2_32!__imp_WSAGetLastError` at `0x18001fed9`
- `WS2_32!__imp_WSAGetLastError` at `0x18001ff02`
- `WS2_32!__imp_WSAGetLastError` at `0x18001fed9`
- `WS2_32!__imp_WSAGetLastError` at `0x18001ff02`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18001fe6c`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18001fe6c`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18001fef6`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18001fef6`
- `ntdll!RtlLeaveCriticalSection` at `0x18001ff87`
- `ntdll!RtlLeaveCriticalSection` at `0x18001ff87`

## string_xrefs

- `0x18001ff26`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`
- `0x18001ffc7`: `ds\security\protocols\kerberos\kps\kpshttp.cxx`

## pseudocode

```c
void __fastcall KpsDoSocketRecvData(struct _KPS_IO **this)
{
  unsigned int Error; // esi
  u_long v3; // ebx
  struct _KPS_IO *v4; // rcx
  _QWORD *v5; // rcx
  void *v6; // rax
  int v7; // edx
  struct _KPS_IO *v8; // rcx
  struct _KPS_IO *v9; // rbx
  int lpOverlapped; // [rsp+28h] [rbp-40h]
  LPWSAOVERLAPPED lpOverlappeda; // [rsp+28h] [rbp-40h]
  _WSABUF Buffers; // [rsp+40h] [rbp-28h] BYREF
  DWORD Flags; // [rsp+70h] [rbp+8h] BYREF

  Error = 0;
  Flags = 0;
  Buffers = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, *this);
  if ( !KpsServiceReady() )
    goto LABEL_31;
  v3 = ntohl(**((_DWORD **)*this + 32));
  *((_DWORD *)*this + 66) = 4;
  v4 = *this;
  if ( v3 >= 0xFFFFFFFC )
  {
    *((_DWORD *)v4 + 67) = -1;
    Error = -1073741675;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_32;
    v7 = 71;
    lpOverlapped = 1571;
    goto LABEL_30;
  }
  *((_DWORD *)v4 + 67) = v3 + 4;
  if ( *((_DWORD *)*this + 67) <= (unsigned int)dword_18003A9C0 )
  {
    v6 = KpsReAllocMem(*((unsigned int *)*this + 67), *((void **)*this + 32));
    if ( v6 )
    {
      *((_QWORD *)*this + 32) = v6;
      v8 = *this;
      Buffers.len = v3;
      Buffers.buf = (CHAR *)(*((_QWORD *)v8 + 32) + 4LL);
      *((_DWORD *)v8 + 8) = 10;
      StartThreadpoolIo(*((PTP_IO *)*this + 28));
      if ( *this && _InterlockedIncrement64((volatile signed __int64 *)*this + 43) <= 1 )
        __fastfail(0xEu);
      if ( WSARecv(*((_QWORD *)*this + 27), &Buffers, 1u, 0, &Flags, (LPWSAOVERLAPPED)*this, 0) != -1
        || WSAGetLastError() == 997 )
      {
        v9 = *this;
        KpsStartTimeoutTimer(*this);
        *((_DWORD *)v9 + 84) = 1;
        if ( *this )
        {
          if ( !KpsIoLockedRef::RemoveRef((KpsIoLockedRef *)this) )
            RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)((char *)*this + 288));
          *this = 0;
        }
      }
      else
      {
        CancelThreadpoolIo(*((PTP_IO *)*this + 28));
        Error = WSAGetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          LODWORD(lpOverlappeda) = 1614;
          WPP_SF_Dsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            74,
            (unsigned int)&WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
            Error,
            (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpshttp.cxx",
            lpOverlappeda);
        }
        KpsIoLockedRef::RemoveRef((KpsIoLockedRef *)this);
      }
      goto LABEL_31;
    }
    Error = 8;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_32;
    v7 = 73;
    lpOverlapped = 1588;
LABEL_30:
    WPP_SF_Dsd(
      v5[2],
      v7,
      (unsigned int)&WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
      Error,
      (__int64)"ds\\security\\protocols\\kerberos\\kps\\kpshttp.cxx",
      lpOverlapped);
    goto LABEL_31;
  }
  Error = 111;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_dD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      72,
      &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids,
      v3,
      dword_18003A9C0);
LABEL_31:
    v5 = WPP_GLOBAL_Control;
  }
LABEL_32:
  if ( *this )
  {
    KpsDoHttpCancelRequest((struct KpsIoLockedRef *)this);
    v5 = WPP_GLOBAL_Control;
  }
  if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x20) != 0 )
    WPP_SF_D(v5[2], 75, &WPP_59490f119f693f52f35bc65fc82e376b_Traceguids, Error);
}

```

## disassembly

```asm
0x18001fd08  mov     rax, rsp
0x18001fd0b  mov     [rax+10h], rbx
0x18001fd0f  mov     [rax+18h], rsi
0x18001fd13  push    rdi
0x18001fd14  push    r14
0x18001fd16  push    r15
0x18001fd18  sub     rsp, 50h
0x18001fd1c  xor     esi, esi
0x18001fd1e  xorps   xmm0, xmm0
0x18001fd21  and     [rax+8], esi
0x18001fd24  mov     rdi, rcx
0x18001fd27  movups  xmmword ptr [rax-28h], xmm0
0x18001fd2b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fd32  lea     r14, WPP_GLOBAL_Control
0x18001fd39  lea     r15, WPP_59490f119f693f52f35bc65fc82e376b_Traceguids
0x18001fd40  cmp     rcx, r14
0x18001fd43  jz      short loc_18001FD5D
0x18001fd45  test    byte ptr [rcx+1Ch], 20h
0x18001fd49  jz      short loc_18001FD5D
0x18001fd4b  mov     r9, [rdi]
0x18001fd4e  lea     edx, [rsi+46h]
0x18001fd51  mov     rcx, [rcx+10h]
0x18001fd55  mov     r8, r15
0x18001fd58  call    WPP_SF_q
0x18001fd5d  call    ?KpsServiceReady@@YAEXZ; KpsServiceReady(void)
0x18001fd62  test    al, al
0x18001fd64  jz      loc_18001FFDE
0x18001fd6a  mov     rax, [rdi]
0x18001fd6d  mov     rcx, [rax+100h]
0x18001fd74  mov     ecx, [rcx]; netlong
0x18001fd76  call    cs:__imp_ntohl
0x18001fd7d  nop     dword ptr [rax+rax+00h]
0x18001fd82  mov     rcx, [rdi]
0x18001fd85  mov     ebx, eax
0x18001fd87  lea     edx, [rax+4]
0x18001fd8a  mov     dword ptr [rcx+108h], 4
0x18001fd94  mov     rcx, [rdi]
0x18001fd97  cmp     edx, 4
0x18001fd9a  jb      loc_18001FF98
0x18001fda0  mov     [rcx+10Ch], edx
0x18001fda6  mov     rdx, [rdi]
0x18001fda9  mov     r8d, cs:dword_18003A9C0
0x18001fdb0  mov     eax, [rdx+10Ch]
0x18001fdb6  cmp     eax, r8d
0x18001fdb9  jbe     short loc_18001FDF6
0x18001fdbb  mov     esi, 6Fh ; 'o'
0x18001fdc0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fdc7  cmp     rcx, r14
0x18001fdca  jz      loc_18001FFE5
0x18001fdd0  test    byte ptr [rcx+1Ch], 1
0x18001fdd4  jz      loc_18001FFE5
0x18001fdda  mov     rcx, [rcx+10h]
0x18001fdde  lea     edx, [rsi-27h]
0x18001fde1  mov     dword ptr [rsp+68h+lpFlags], r8d
0x18001fde6  mov     r9d, ebx
0x18001fde9  mov     r8, r15
0x18001fdec  call    WPP_SF_dD
0x18001fdf1  jmp     loc_18001FFDE
0x18001fdf6  mov     rdx, [rdx+100h]; void *
0x18001fdfd  mov     rcx, rax; unsigned __int64
0x18001fe00  call    ?KpsReAllocMem@@YAPEAX_KPEAX@Z; KpsReAllocMem(unsigned __int64,void *)
0x18001fe05  mov     rcx, rax
0x18001fe08  test    rax, rax
0x18001fe0b  jnz     short loc_18001FE3A
0x18001fe0d  lea     esi, [rax+8]
0x18001fe10  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fe17  cmp     rcx, r14
0x18001fe1a  jz      loc_18001FFE5
0x18001fe20  test    byte ptr [rcx+1Ch], 1
0x18001fe24  jz      loc_18001FFE5
0x18001fe2a  lea     edx, [rax+49h]
0x18001fe2d  mov     dword ptr [rsp+68h+lpOverlapped], 634h
0x18001fe35  jmp     loc_18001FFC3
0x18001fe3a  mov     rax, [rdi]
0x18001fe3d  mov     [rax+100h], rcx
0x18001fe44  mov     rcx, [rdi]
0x18001fe47  mov     [rsp+68h+Buffers.len], ebx
0x18001fe4b  mov     rax, [rcx+100h]
0x18001fe52  add     rax, 4
0x18001fe56  mov     [rsp+68h+Buffers.buf], rax
0x18001fe5b  mov     dword ptr [rcx+20h], 0Ah
0x18001fe62  mov     rcx, [rdi]
0x18001fe65  mov     rcx, [rcx+0E0h]; pio
0x18001fe6c  call    cs:__imp_StartThreadpoolIo
0x18001fe73  nop     dword ptr [rax+rax+00h]
0x18001fe78  mov     rcx, [rdi]
0x18001fe7b  test    rcx, rcx
0x18001fe7e  jz      short loc_18001FE9E
0x18001fe80  mov     eax, 1
0x18001fe85  lock xadd [rcx+158h], rax
0x18001fe8e  inc     rax
0x18001fe91  cmp     rax, 1
0x18001fe95  jg      short loc_18001FE9E
0x18001fe97  mov     ecx, 0Eh
0x18001fe9c  int     29h; Win8: RtlFailFast(ecx)
0x18001fe9e  mov     rax, [rdi]
0x18001fea1  lea     rcx, [rsp+68h+Flags]
0x18001fea6  and     [rsp+68h+var_38], rsi
0x18001feab  lea     rdx, [rsp+68h+Buffers]; lpBuffers
0x18001feb0  xor     r9d, r9d; lpNumberOfBytesRecvd
0x18001feb3  mov     [rsp+68h+lpOverlapped], rax; lpOverlapped
0x18001feb8  mov     [rsp+68h+lpFlags], rcx; lpFlags
0x18001febd  mov     rcx, [rax+0D8h]; s
0x18001fec4  lea     r8d, [r9+1]; dwBufferCount
0x18001fec8  call    cs:__imp_WSARecv
0x18001fecf  nop     dword ptr [rax+rax+00h]
0x18001fed4  cmp     eax, 0FFFFFFFFh
0x18001fed7  jnz     short loc_18001FF57
0x18001fed9  call    cs:__imp_WSAGetLastError
0x18001fee0  nop     dword ptr [rax+rax+00h]
0x18001fee5  cmp     eax, 3E5h
0x18001feea  jz      short loc_18001FF57
0x18001feec  mov     rcx, [rdi]
0x18001feef  mov     rcx, [rcx+0E0h]; pio
0x18001fef6  call    cs:__imp_CancelThreadpoolIo
0x18001fefd  nop     dword ptr [rax+rax+00h]
0x18001ff02  call    cs:__imp_WSAGetLastError
0x18001ff09  nop     dword ptr [rax+rax+00h]
0x18001ff0e  mov     esi, eax
0x18001ff10  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ff17  cmp     rcx, r14
0x18001ff1a  jz      short loc_18001FF4A
0x18001ff1c  test    byte ptr [rcx+1Ch], 1
0x18001ff20  jz      short loc_18001FF4A
0x18001ff22  mov     rcx, [rcx+10h]
0x18001ff26  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x18001ff2d  mov     edx, 4Ah ; 'J'
0x18001ff32  mov     dword ptr [rsp+68h+lpOverlapped], 64Eh
0x18001ff3a  mov     r9d, esi
0x18001ff3d  mov     [rsp+68h+lpFlags], rax
0x18001ff42  mov     r8, r15
0x18001ff45  call    WPP_SF_Dsd
0x18001ff4a  mov     rcx, rdi; this
0x18001ff4d  call    ?RemoveRef@KpsIoLockedRef@@QEAA_NXZ; KpsIoLockedRef::RemoveRef(void)
0x18001ff52  jmp     loc_18001FFDE
0x18001ff57  mov     rbx, [rdi]
0x18001ff5a  mov     rcx, rbx; struct _KPS_IO *
0x18001ff5d  call    ?KpsStartTimeoutTimer@@YAXPEAU_KPS_IO@@@Z; KpsStartTimeoutTimer(_KPS_IO *)
0x18001ff62  mov     dword ptr [rbx+150h], 1
0x18001ff6c  cmp     [rdi], rsi
0x18001ff6f  jz      short loc_18001FFDE
0x18001ff71  mov     rcx, rdi; this
0x18001ff74  call    ?RemoveRef@KpsIoLockedRef@@QEAA_NXZ; KpsIoLockedRef::RemoveRef(void)
0x18001ff79  test    al, al
0x18001ff7b  jnz     short loc_18001FF93
0x18001ff7d  mov     rcx, [rdi]
0x18001ff80  add     rcx, 120h; CriticalSection
0x18001ff87  call    cs:__imp_RtlLeaveCriticalSection
0x18001ff8e  nop     dword ptr [rax+rax+00h]
0x18001ff93  and     [rdi], rsi
0x18001ff96  jmp     short loc_18001FFDE
0x18001ff98  or      dword ptr [rcx+10Ch], 0FFFFFFFFh
0x18001ff9f  mov     esi, 0C0000095h
0x18001ffa4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ffab  cmp     rcx, r14
0x18001ffae  jz      short loc_18001FFE5
0x18001ffb0  test    byte ptr [rcx+1Ch], 1
0x18001ffb4  jz      short loc_18001FFE5
0x18001ffb6  mov     edx, 47h ; 'G'
0x18001ffbb  mov     dword ptr [rsp+68h+lpOverlapped], 623h
0x18001ffc3  mov     rcx, [rcx+10h]
0x18001ffc7  lea     rax, aDsSecurityProt_0; "ds\\security\\protocols\\kerberos\\kps"...
0x18001ffce  mov     r9d, esi
0x18001ffd1  mov     [rsp+68h+lpFlags], rax
0x18001ffd6  mov     r8, r15
0x18001ffd9  call    WPP_SF_Dsd
0x18001ffde  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ffe5  cmp     qword ptr [rdi], 0
0x18001ffe9  jz      short loc_18001FFFA
0x18001ffeb  mov     rcx, rdi; this
0x18001ffee  call    ?KpsDoHttpCancelRequest@@YAXAEAVKpsIoLockedRef@@@Z; KpsDoHttpCancelRequest(KpsIoLockedRef &)
0x18001fff3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fffa  cmp     rcx, r14
0x18001fffd  jz      short loc_180020019
0x18001ffff  test    byte ptr [rcx+1Ch], 20h
0x180020003  jz      short loc_180020019
0x180020005  mov     rcx, [rcx+10h]
0x180020009  mov     edx, 4Bh ; 'K'
0x18002000e  mov     r9d, esi
0x180020011  mov     r8, r15
0x180020014  call    WPP_SF_D
0x180020019  lea     r11, [rsp+68h+var_18]
0x18002001e  mov     rbx, [r11+28h]
0x180020022  mov     rsi, [r11+30h]
0x180020026  mov     rsp, r11
0x180020029  pop     r15
0x18002002b  pop     r14
0x18002002d  pop     rdi
0x18002002e  retn
```
