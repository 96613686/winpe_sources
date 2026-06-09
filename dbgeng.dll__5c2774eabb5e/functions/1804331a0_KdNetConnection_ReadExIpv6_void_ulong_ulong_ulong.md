# KdNetConnection::ReadExIpv6(void *,ulong,ulong *,ulong)

- ea: `0x1804331a0`
- end: `0x180433939`
- name: `?ReadExIpv6@KdNetConnection@@UEAAJPEAXKPEAKK@Z`
- size: `1945`
- prototype: `__int64 __usercall@<rax>(KdNetConnection *__hidden this@<rcx>, void *@<rdx>, unsigned int@<r8d>, unsigned int *@<r9>, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1800db578`
- `0x1800f0f40`
- `0x18038605c`
- `0x18042ef34`
- `0x180431ea8`
- `0x180431fe0`
- `0x1804331a0`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x18043355b`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x18043355b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180433211`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18043328c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180433357`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180433211`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x18043328c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180433357`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180433200`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180433268`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180433346`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1804333f2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18043352d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180433200`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180433268`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180433346`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1804333f2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18043352d`
- `WS2_32!inet_ntop` at `0x1804335b5`
- `WS2_32!inet_ntop` at `0x180433643`
- `WS2_32!inet_ntop` at `0x180433671`
- `WS2_32!inet_ntop` at `0x180433776`
- `WS2_32!inet_ntop` at `0x1804337bf`
- `WS2_32!inet_ntop` at `0x180433844`
- `WS2_32!inet_ntop` at `0x18043388d`
- `WS2_32!inet_ntop` at `0x1804335b5`
- `WS2_32!inet_ntop` at `0x180433643`
- `WS2_32!inet_ntop` at `0x180433671`
- `WS2_32!inet_ntop` at `0x180433776`
- `WS2_32!inet_ntop` at `0x1804337bf`
- `WS2_32!inet_ntop` at `0x180433844`
- `WS2_32!inet_ntop` at `0x18043388d`
- `WS2_32!__imp_ntohs` at `0x180433789`
- `WS2_32!__imp_ntohs` at `0x180433857`
- `WS2_32!__imp_ntohs` at `0x180433789`
- `WS2_32!__imp_ntohs` at `0x180433857`
- `WS2_32!__imp_recvfrom` at `0x180433464`
- `WS2_32!__imp_recvfrom` at `0x180433464`
- `WS2_32!__imp_WSAGetLastError` at `0x180433508`
- `WS2_32!__imp_WSAGetLastError` at `0x180433508`

## string_xrefs

- `0x1804333cf`: `Target is not responding.  Attempting to reconnect...\n`
- `0x1804335de`: `Run nslookup %hs from a command prompt to get the machine name.\n`
- `0x1804337e0`: `You can get the target MAC address by running .kdtargetmac command.\n`
- `0x1804338ae`: `You can get the target MAC address by running .kdtargetmac command.\n`
- `0x1804338ee`: `Net: Read %d bytes of %d\n`
- `0x1804338cf`: `WinSock read error.  Error 0n%d\n`

## pseudocode

```c
__int64 __fastcall KdNetConnection::ReadExIpv6(
        KdNetConnection *this,
        char *a2,
        unsigned int a3,
        unsigned int *a4,
        unsigned int a5)
{
  unsigned int v7; // esi
  __int128 v9; // rax
  _QWORD *v10; // rdi
  __int128 v11; // rax
  char v12; // al
  char *v13; // rdx
  SOCKET v14; // rcx
  int v15; // r8d
  int v16; // edi
  __int128 v17; // xmm1
  __int64 (__fastcall *v18)(KdNetConnection *, char *, _QWORD, int *); // rax
  KdConnection *v19; // rcx
  unsigned int Error; // eax
  KdConnection **v21; // rsi
  __int64 v22; // rdx
  struct sockaddr v23; // xmm0
  __int128 v24; // xmm1
  unsigned int v25; // eax
  bool v26; // zf
  __int128 v27; // xmm1
  u_short v28; // ax
  u_short v29; // ax
  int v31; // [rsp+30h] [rbp-91h] BYREF
  LARGE_INTEGER Frequency; // [rsp+38h] [rbp-89h] BYREF
  LARGE_INTEGER v33; // [rsp+40h] [rbp-81h] BYREF
  unsigned int v34; // [rsp+48h] [rbp-79h]
  int fromlen; // [rsp+4Ch] [rbp-75h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+50h] [rbp-71h] BYREF
  struct sockaddr pAddr[2]; // [rsp+58h] [rbp-69h] BYREF
  CHAR pStringBuf[64]; // [rsp+80h] [rbp-41h] BYREF

  v34 = a3;
  fromlen = 0;
  v31 = 0;
  memset(pAddr, 0, 28);
  v33.QuadPart = 0;
  PerformanceCount.QuadPart = 0;
  v7 = a3;
  Frequency.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  QueryPerformanceFrequency(&Frequency);
  PerformanceCount.QuadPart += Frequency.QuadPart * a5 / 1000000;
  while ( 1 )
  {
    if ( !*((_BYTE *)this + 6873) && *((_BYTE *)this + 6850) )
    {
      QueryPerformanceCounter(&v33);
      if ( v33.QuadPart < *((_QWORD *)this + 857) )
        v33 = *(LARGE_INTEGER *)((char *)this + 6856);
      QueryPerformanceFrequency(&Frequency);
      v9 = v33.QuadPart - *((_QWORD *)this + 857);
      Frequency.QuadPart = Frequency.QuadPart / 1024 + 1;
      if ( (__int64)(v9 / Frequency.QuadPart) > 4096 )
      {
        LnkOut(2u, L"No ping packet received, reseting data channel.\n");
        if ( *((_BYTE *)this + 6849) )
          LnkOut(
            2u,
            L"Transport may not re-connect automatically.\n"
             "To re-sync with target type CTRL+R (kd) or CTRL+ALT+R (windbg)\n");
        *((_BYTE *)this + 6850) = 0;
      }
    }
    if ( *((_BYTE *)this + 6849) )
    {
      if ( *((_BYTE *)this + 6850) )
      {
        if ( *((_BYTE *)this + 6848) )
        {
          v10 = (_QWORD *)((char *)this + 6864);
          if ( *((_QWORD *)this + 858) )
          {
            if ( (*(_BYTE *)(*((_QWORD *)this + 3) + 32LL) & 4) != 0 )
            {
              QueryPerformanceCounter(&v33);
              QueryPerformanceFrequency(&Frequency);
              v11 = v33.QuadPart - *v10;
              Frequency.QuadPart = Frequency.QuadPart / 1024 + 1;
              if ( (__int64)(v11 / Frequency.QuadPart) > 7168 )
              {
                LnkOut(0x80000000, L"OFFER stream stale, sending POKE to target.\n");
                if ( !*((_BYTE *)this + 6872) )
                {
                  *((_BYTE *)this + 6872) = 1;
                  FeatureUsageTracker::FeatureUsed(L"KDNET", L"RebootPoke", 5u);
                  LnkOut(4u, L"Target is not responding.  Attempting to reconnect...\n");
                }
                (*(void (__fastcall **)(KdNetConnection *))(*(_QWORD *)this + 104LL))(this);
                QueryPerformanceCounter((LARGE_INTEGER *)this + 858);
                *v10 += -6144 * Frequency.QuadPart;
              }
            }
          }
        }
      }
    }
    v12 = *((_BYTE *)this + 6848);
    v13 = (char *)this + 2502;
    if ( !v12 )
      v13 = a2;
    *a4 = 0;
    v14 = *((_QWORD *)this + 126);
    v15 = 1474;
    if ( !v12 )
      v15 = v7;
    fromlen = 28;
    v16 = -2147024890;
    if ( v14 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
      return (unsigned int)v16;
    v31 = recvfrom(v14, v13, v15, 0, pAddr, &fromlen);
    if ( v31 == -1 )
    {
      Error = WSAGetLastError();
      v16 = Error;
      if ( Error != 10060 && Error != 10035 )
      {
        LnkOut(0x80000000, L"WinSock read error.  Error 0n%d\n", Error);
LABEL_60:
        if ( !v16 )
        {
          if ( (*((_BYTE *)this + 72) & 1) != 0 )
            KdConnection::OutputIo(v19, L"Net: Read %d bytes of %d\n", a2, v7, *a4);
          *((_QWORD *)this + 20) += *a4;
        }
        return (unsigned int)v16;
      }
      QueryPerformanceCounter(&v33);
      if ( v33.QuadPart >= PerformanceCount.QuadPart )
        return 10060;
      if ( v16 == 10035 )
        SleepEx(1u, 1);
    }
    else
    {
      v17 = *(_OWORD *)&pAddr[0].sa_data[10];
      v18 = *(__int64 (__fastcall **)(KdNetConnection *, char *, _QWORD, int *))(*(_QWORD *)this + 136LL);
      *((struct sockaddr *)this + 61) = pAddr[0];
      *(_OWORD *)((char *)this + 988) = v17;
      v16 = v18(this, a2, v7, &v31);
      KdNetConnection::LogPacketReceived(this, v31);
      if ( v16 != -1879048169 )
      {
        if ( v16 == -805305302 )
        {
          LnkOut(2u, L"KDNET received an out of sequence ping packet.\n");
          LnkOut(2u, L"The target machine restarted without notifying the debugger.\n");
          LnkOut(2u, L"Forcing a debugger reconnect...\n");
          goto LABEL_58;
        }
        if ( v16 < 0 )
        {
          if ( *(_QWORD *)&pAddr[0].sa_data[6] == *(_QWORD *)((char *)this + 956)
            && *(_QWORD *)&pAddr[1].sa_family == *(_QWORD *)((char *)this + 964) )
          {
            FeatureUsageTracker::FeatureUsed(L"KDNET", L"ErrBadPacket", 5u);
          }
          inet_ntop(23, &pAddr[0].sa_data[6], pStringBuf, 0x40u);
          LnkOut(2u, L"Bad packet sent from %hs.\n", pStringBuf);
          LnkOut(2u, L"Run nslookup %hs from a command prompt to get the machine name.\n", pStringBuf);
          goto LABEL_58;
        }
        if ( v16 )
        {
LABEL_58:
          *a4 = v31;
          goto LABEL_60;
        }
        v21 = (KdConnection **)((char *)this + 956);
        v19 = *(KdConnection **)((char *)this + 964);
        if ( *(KdConnection **)&pAddr[1].sa_family != v19 || *(KdConnection **)&pAddr[0].sa_data[6] != *v21 )
        {
          v22 = *(_QWORD *)&in6addr_any.u.Word[4];
          if ( v19 != *(KdConnection **)&in6addr_any.u.Word[4]
            || (v19 = *(KdConnection **)in6addr_any.u.Byte, *v21 != *(KdConnection **)in6addr_any.u.Byte) )
          {
            inet_ntop(23, &pAddr[0].sa_data[6], pStringBuf, 0x40u);
            LnkOut(4u, L"WARNING: Received data from %hs ", pStringBuf);
            inet_ntop(23, (char *)this + 956, pStringBuf, 0x40u);
            LnkOut(4u, L"while still connected to target %hs.\n", pStringBuf);
            v22 = *(_QWORD *)&in6addr_any.u.Word[4];
            v19 = *(KdConnection **)in6addr_any.u.Byte;
          }
          if ( !*((_BYTE *)this + 6848) )
          {
            v27 = *(_OWORD *)&pAddr[0].sa_data[10];
            *(struct sockaddr *)((char *)this + 948) = pAddr[0];
            *((_OWORD *)this + 60) = v27;
            goto LABEL_50;
          }
          if ( ((v31 - 8) & 0xFFFFFFFB) == 0 )
          {
            v23 = pAddr[0];
            *((_BYTE *)this + 6873) = 1;
            v24 = *(_OWORD *)&pAddr[0].sa_data[10];
            *(struct sockaddr *)((char *)this + 948) = v23;
            *((_OWORD *)this + 60) = v24;
            v25 = KdNetConnection::CalculateDynamicTimeout(this);
            v26 = *((_BYTE *)this + 6848) == 1;
            *((_DWORD *)this + 1724) = v25;
            if ( v26 && *(_QWORD *)a2 >= 0x7FFFFFFFFFFFFFFFuLL )
            {
              *((_QWORD *)this + 855) = *(_QWORD *)a2;
              ++*((_QWORD *)this + 855);
            }
LABEL_50:
            v22 = *(_QWORD *)&in6addr_any.u.Word[4];
            v19 = *(KdConnection **)in6addr_any.u.Byte;
          }
          if ( *(_QWORD *)((char *)this + 964) != v22 || *v21 != v19 )
          {
            FeatureUsageTracker::FeatureUsed(L"KDNET", L"ConnectionSuccessIPv6", 5u);
            inet_ntop(23, (char *)this + 956, pStringBuf, 0x40u);
            v28 = ntohs(*((_WORD *)this + 461));
            LnkOut(1u, L"Connected to target %hs on port %d", pStringBuf, v28);
            inet_ntop(23, (char *)this + 928, pStringBuf, 0x40u);
            LnkOut(1u, L" on local IP %hs.\n", pStringBuf);
            LnkOut(1u, L"You can get the target MAC address by running .kdtargetmac command.\n");
          }
        }
        if ( *((_BYTE *)this + 6849) && v31 == 12 )
        {
          FeatureUsageTracker::FeatureUsed(L"KDNET", L"ConnectionSuccessIPv6", 5u);
          *((_BYTE *)this + 6873) = 1;
          *((_DWORD *)this + 1724) = KdNetConnection::CalculateDynamicTimeout(this);
          inet_ntop(23, (char *)this + 956, pStringBuf, 0x40u);
          v29 = ntohs(*((_WORD *)this + 461));
          LnkOut(1u, L"Connected to target %hs on port %d", pStringBuf, v29);
          inet_ntop(23, (char *)this + 928, pStringBuf, 0x40u);
          LnkOut(1u, L" on local IP %hs.\n", pStringBuf);
          LnkOut(1u, L"You can get the target MAC address by running .kdtargetmac command.\n");
        }
        v7 = v34;
        goto LABEL_58;
      }
    }
  }
}

```

## disassembly

```asm
0x1804331a0  push    rbp
0x1804331a2  push    rbx
0x1804331a3  push    rsi
0x1804331a4  push    rdi
0x1804331a5  push    r12
0x1804331a7  push    r13
0x1804331a9  push    r14
0x1804331ab  push    r15
0x1804331ad  lea     rbp, [rsp-17h]
0x1804331b2  sub     rsp, 0D8h
0x1804331b9  mov     rax, cs:__security_cookie
0x1804331c0  xor     rax, rsp
0x1804331c3  mov     [rbp+4Fh+var_50], rax
0x1804331c7  xor     r14d, r14d
0x1804331ca  mov     [rbp+4Fh+var_C8], r8d
0x1804331ce  xorps   xmm0, xmm0
0x1804331d1  mov     [rbp+4Fh+var_C4], r14d
0x1804331d5  mov     rbx, rcx
0x1804331d8  mov     [rsp+110h+var_E0], r14d
0x1804331dd  movups  xmmword ptr [rbp+4Fh+pAddr.sa_family], xmm0
0x1804331e1  lea     rcx, [rbp+4Fh+PerformanceCount]; lpPerformanceCount
0x1804331e5  mov     qword ptr [rsp+110h+var_D0], r14
0x1804331ea  movups  xmmword ptr [rbp+4Fh+pAddr.sa_data+0Ah], xmm0
0x1804331ee  mov     r12, r9
0x1804331f1  mov     qword ptr [rbp+4Fh+PerformanceCount], r14
0x1804331f5  mov     esi, r8d
0x1804331f8  mov     qword ptr [rsp+110h+Frequency], r14
0x1804331fd  mov     r13, rdx
0x180433200  call    cs:__imp_QueryPerformanceCounter
0x180433207  nop     dword ptr [rax+rax+00h]
0x18043320c  lea     rcx, [rsp+110h+Frequency]; lpFrequency
0x180433211  call    cs:__imp_QueryPerformanceFrequency
0x180433218  nop     dword ptr [rax+rax+00h]
0x18043321d  mov     ecx, [rbp+4Fh+arg_20]
0x180433220  lea     r15d, [r14+2]
0x180433224  imul    rcx, qword ptr [rsp+110h+Frequency]
0x18043322a  mov     rax, 431BDE82D7B634DBh
0x180433234  imul    rcx
0x180433237  sar     rdx, 12h
0x18043323b  mov     rax, rdx
0x18043323e  shr     rax, 3Fh
0x180433242  add     rdx, rax
0x180433245  add     qword ptr [rbp+4Fh+PerformanceCount], rdx
0x180433249  cmp     [rbx+1AD9h], r14b
0x180433250  jnz     loc_1804332FC
0x180433256  cmp     [rbx+1AC2h], r14b
0x18043325d  jz      loc_1804332FC
0x180433263  lea     rcx, [rsp+110h+var_D0]; lpPerformanceCount
0x180433268  call    cs:__imp_QueryPerformanceCounter
0x18043326f  nop     dword ptr [rax+rax+00h]
0x180433274  mov     rax, [rbx+1AC8h]
0x18043327b  cmp     qword ptr [rsp+110h+var_D0], rax
0x180433280  jge     short loc_180433287
0x180433282  mov     qword ptr [rsp+110h+var_D0], rax
0x180433287  lea     rcx, [rsp+110h+Frequency]; lpFrequency
0x18043328c  call    cs:__imp_QueryPerformanceFrequency
0x180433293  nop     dword ptr [rax+rax+00h]
0x180433298  mov     rax, qword ptr [rsp+110h+Frequency]
0x18043329d  test    rax, rax
0x1804332a0  jns     short loc_1804332A8
0x1804332a2  add     rax, 3FFh
0x1804332a8  sar     rax, 0Ah
0x1804332ac  lea     rcx, [rax+1]
0x1804332b0  mov     rax, qword ptr [rsp+110h+var_D0]
0x1804332b5  sub     rax, [rbx+1AC8h]
0x1804332bc  cqo
0x1804332be  mov     qword ptr [rsp+110h+Frequency], rcx
0x1804332c3  idiv    rcx
0x1804332c6  cmp     rax, 1000h
0x1804332cc  jle     short loc_1804332FC
0x1804332ce  lea     rdx, aNoPingPacketRe; "No ping packet received, reseting data "...
0x1804332d5  mov     ecx, r15d; unsigned int
0x1804332d8  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x1804332dd  cmp     [rbx+1AC1h], r14b
0x1804332e4  jz      short loc_1804332F5
0x1804332e6  lea     rdx, aTransportMayNo; "Transport may not re-connect automatica"...
0x1804332ed  mov     ecx, r15d; unsigned int
0x1804332f0  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x1804332f5  mov     [rbx+1AC2h], r14b
0x1804332fc  cmp     [rbx+1AC1h], r14b
0x180433303  jz      loc_18043340A
0x180433309  cmp     [rbx+1AC2h], r14b
0x180433310  jz      loc_18043340A
0x180433316  cmp     [rbx+1AC0h], r14b
0x18043331d  jz      loc_18043340A
0x180433323  lea     rdi, [rbx+1AD0h]
0x18043332a  cmp     [rdi], r14
0x18043332d  jz      loc_18043340A
0x180433333  mov     rax, [rbx+18h]
0x180433337  test    byte ptr [rax+20h], 4
0x18043333b  jz      loc_18043340A
0x180433341  lea     rcx, [rsp+110h+var_D0]; lpPerformanceCount
0x180433346  call    cs:__imp_QueryPerformanceCounter
0x18043334d  nop     dword ptr [rax+rax+00h]
0x180433352  lea     rcx, [rsp+110h+Frequency]; lpFrequency
0x180433357  call    cs:__imp_QueryPerformanceFrequency
0x18043335e  nop     dword ptr [rax+rax+00h]
0x180433363  mov     rax, qword ptr [rsp+110h+Frequency]
0x180433368  test    rax, rax
0x18043336b  jns     short loc_180433373
0x18043336d  add     rax, 3FFh
0x180433373  sar     rax, 0Ah
0x180433377  lea     rcx, [rax+1]
0x18043337b  mov     rax, qword ptr [rsp+110h+var_D0]
0x180433380  sub     rax, [rdi]
0x180433383  cqo
0x180433385  mov     qword ptr [rsp+110h+Frequency], rcx
0x18043338a  idiv    rcx
0x18043338d  cmp     rax, 1C00h
0x180433393  jle     short loc_18043340A
0x180433395  lea     rdx, aOfferStreamSta; "OFFER stream stale, sending POKE to tar"...
0x18043339c  mov     ecx, 80000000h; unsigned int
0x1804333a1  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x1804333a6  cmp     [rbx+1AD8h], r14b
0x1804333ad  jnz     short loc_1804333E0
0x1804333af  mov     r8d, 5; unsigned int
0x1804333b5  mov     byte ptr [rbx+1AD8h], 1
0x1804333bc  lea     rdx, aRebootpoke; "RebootPoke"
0x1804333c3  lea     rcx, aKdnet_0; "KDNET"
0x1804333ca  call    ?FeatureUsed@FeatureUsageTracker@@SAXQEBG0K@Z; FeatureUsageTracker::FeatureUsed(ushort const * const,ushort const * const,ulong)
0x1804333cf  lea     rdx, aTargetIsNotRes; "Target is not responding.  Attempting t"...
0x1804333d6  mov     ecx, 4; unsigned int
0x1804333db  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x1804333e0  mov     rax, [rbx]
0x1804333e3  mov     rcx, rbx
0x1804333e6  mov     rax, [rax+68h]
0x1804333ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804333ef  mov     rcx, rdi; lpPerformanceCount
0x1804333f2  call    cs:__imp_QueryPerformanceCounter
0x1804333f9  nop     dword ptr [rax+rax+00h]
0x1804333fe  imul    rax, qword ptr [rsp+110h+Frequency], 0FFFFFFFFFFFFE800h
0x180433407  add     [rdi], rax
0x18043340a  mov     al, [rbx+1AC0h]
0x180433410  lea     rdx, [rbx+9C6h]
0x180433417  test    al, al
0x180433419  jnz     short loc_18043341E
0x18043341b  mov     rdx, r13; buf
0x18043341e  test    al, al
0x180433420  mov     [r12], r14d
0x180433424  mov     rcx, [rbx+3F0h]; s
0x18043342b  mov     r8d, 5C2h
0x180433431  cmovz   r8d, esi; len
0x180433435  mov     [rbp+4Fh+var_C4], 1Ch
0x18043343c  mov     edi, 80070006h
0x180433441  lea     rax, [rcx-1]
0x180433445  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180433449  ja      loc_180433916
0x18043344f  lea     rax, [rbp+4Fh+var_C4]
0x180433453  xor     r9d, r9d; flags
0x180433456  mov     [rsp+110h+fromlen], rax; fromlen
0x18043345b  lea     rax, [rbp+4Fh+pAddr]
0x18043345f  mov     [rsp+110h+from], rax; from
0x180433464  call    cs:__imp_recvfrom
0x18043346b  nop     dword ptr [rax+rax+00h]
0x180433470  mov     [rsp+110h+var_E0], eax
0x180433474  cmp     eax, 0FFFFFFFFh
0x180433477  jz      loc_180433508
0x18043347d  mov     rax, [rbx]
0x180433480  lea     r9, [rsp+110h+var_E0]
0x180433485  movups  xmm0, xmmword ptr [rbp+4Fh+pAddr.sa_family]
0x180433489  mov     r8d, esi
0x18043348c  mov     rdx, r13
0x18043348f  movups  xmm1, xmmword ptr [rbp+4Fh+pAddr.sa_data+0Ah]
0x180433493  mov     rax, [rax+88h]
0x18043349a  mov     rcx, rbx
0x18043349d  movups  xmmword ptr [rbx+3D0h], xmm0
0x1804334a4  movups  xmmword ptr [rbx+3DCh], xmm1
0x1804334ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804334b0  mov     edx, [rsp+110h+var_E0]; int
0x1804334b4  mov     rcx, rbx; this
0x1804334b7  mov     edi, eax
0x1804334b9  call    ?LogPacketReceived@KdNetConnection@@QEAAXJ@Z; KdNetConnection::LogPacketReceived(long)
0x1804334be  cmp     edi, 90000017h
0x1804334c4  jz      loc_180433249
0x1804334ca  cmp     edi, 0D000042Ah
0x1804334d0  jnz     loc_18043356C
0x1804334d6  lea     rdx, aKdnetReceivedA; "KDNET received an out of sequence ping "...
0x1804334dd  mov     ecx, r15d; unsigned int
0x1804334e0  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x1804334e5  lea     rdx, aTheTargetMachi_0; "The target machine restarted without no"...
0x1804334ec  mov     ecx, r15d; unsigned int
0x1804334ef  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x1804334f4  lea     rdx, aForcingADebugg; "Forcing a debugger reconnect...\n"
0x1804334fb  mov     ecx, r15d; unsigned int
0x1804334fe  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180433503  jmp     loc_1804338C2
0x180433508  call    cs:__imp_WSAGetLastError
0x18043350f  nop     dword ptr [rax+rax+00h]
0x180433514  mov     edi, eax
0x180433516  cmp     eax, 274Ch
0x18043351b  jz      short loc_180433528
0x18043351d  cmp     eax, 2733h
0x180433522  jnz     loc_1804338CC
0x180433528  lea     rcx, [rsp+110h+var_D0]; lpPerformanceCount
0x18043352d  call    cs:__imp_QueryPerformanceCounter
0x180433534  nop     dword ptr [rax+rax+00h]
0x180433539  mov     rax, qword ptr [rbp+4Fh+PerformanceCount]
0x18043353d  cmp     qword ptr [rsp+110h+var_D0], rax
0x180433542  jge     loc_180433911
0x180433548  cmp     edi, 2733h
0x18043354e  jnz     loc_180433249
0x180433554  mov     edx, 1; bAlertable
0x180433559  mov     ecx, edx; dwMilliseconds
0x18043355b  call    cs:__imp_SleepEx
0x180433562  nop     dword ptr [rax+rax+00h]
0x180433567  jmp     loc_180433249
0x18043356c  test    edi, edi
0x18043356e  jns     short loc_1804335EF
0x180433570  mov     rax, qword ptr [rbp+4Fh+pAddr.sa_data+6]
0x180433574  cmp     rax, [rbx+3BCh]
0x18043357b  jnz     short loc_1804335A3
0x18043357d  mov     rax, [rbp+4Fh+var_A8]
0x180433581  cmp     rax, [rbx+3C4h]
0x180433588  jnz     short loc_1804335A3
0x18043358a  mov     r8d, 5; unsigned int
0x180433590  lea     rdx, aErrbadpacket; "ErrBadPacket"
0x180433597  lea     rcx, aKdnet_0; "KDNET"
0x18043359e  call    ?FeatureUsed@FeatureUsageTracker@@SAXQEBG0K@Z; FeatureUsageTracker::FeatureUsed(ushort const * const,ushort const * const,ulong)
0x1804335a3  mov     r9d, 40h ; '@'; StringBufSize
0x1804335a9  lea     r8, [rbp+4Fh+pStringBuf]; pStringBuf
0x1804335ad  lea     rdx, [rbp+4Fh+pAddr.sa_data+6]; pAddr
0x1804335b1  lea     ecx, [r9-29h]; Family
0x1804335b5  call    cs:__imp_inet_ntop
0x1804335bc  nop     dword ptr [rax+rax+00h]
0x1804335c1  lea     r8, [rbp+4Fh+pStringBuf]
0x1804335c5  mov     ecx, r15d; unsigned int
0x1804335c8  lea     rdx, aBadPacketSentF; "Bad packet sent from %hs.\n"
0x1804335cf  mov     r14d, r15d
0x1804335d2  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x1804335d7  lea     r8, [rbp+4Fh+pStringBuf]
0x1804335db  mov     ecx, r15d; unsigned int
0x1804335de  lea     rdx, aRunNslookupHsF; "Run nslookup %hs from a command prompt "...
0x1804335e5  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x1804335ea  jmp     loc_1804338C2
0x1804335ef  jnz     loc_1804338C2
0x1804335f5  lea     rsi, [rbx+3BCh]
0x1804335fc  mov     r14d, 40h ; '@'
0x180433602  mov     rcx, [rsi+8]
0x180433606  lea     r15d, [r14-29h]
0x18043360a  cmp     [rbp+4Fh+var_A8], rcx
0x18043360e  jnz     short loc_18043361D
0x180433610  mov     rax, [rsi]
0x180433613  cmp     qword ptr [rbp+4Fh+pAddr.sa_data+6], rax
0x180433617  jz      loc_1804337F1
0x18043361d  mov     rdx, qword ptr cs:in6addr_any.u+8
0x180433624  cmp     rcx, rdx
0x180433627  jnz     short loc_180433635
0x180433629  mov     rcx, qword ptr cs:in6addr_any.u
0x180433630  cmp     [rsi], rcx
0x180433633  jz      short loc_1804336A0
0x180433635  mov     r9, r14; StringBufSize
0x180433638  lea     r8, [rbp+4Fh+pStringBuf]; pStringBuf
0x18043363c  lea     rdx, [rbp+4Fh+pAddr.sa_data+6]; pAddr
0x180433640  mov     ecx, r15d; Family
0x180433643  call    cs:__imp_inet_ntop
0x18043364a  nop     dword ptr [rax+rax+00h]
0x18043364f  lea     r8, [rbp+4Fh+pStringBuf]
0x180433653  mov     ecx, 4; unsigned int
0x180433658  lea     rdx, aWarningReceive; "WARNING: Received data from %hs "
0x18043365f  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180433664  mov     r9, r14; StringBufSize
0x180433667  lea     r8, [rbp+4Fh+pStringBuf]; pStringBuf
0x18043366b  mov     rdx, rsi; pAddr
0x18043366e  mov     ecx, r15d; Family
0x180433671  call    cs:__imp_inet_ntop
0x180433678  nop     dword ptr [rax+rax+00h]
0x18043367d  lea     r8, [rbp+4Fh+pStringBuf]
0x180433681  mov     ecx, 4; unsigned int
0x180433686  lea     rdx, aWhileStillConn; "while still connected to target %hs.\n"
0x18043368d  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180433692  mov     rdx, qword ptr cs:in6addr_any.u+8
0x180433699  mov     rcx, qword ptr cs:in6addr_any.u
0x1804336a0  cmp     byte ptr [rbx+1AC0h], 0
0x1804336a7  jz      short loc_18043371D
0x1804336a9  mov     eax, [rsp+110h+var_E0]
0x1804336ad  add     eax, 0FFFFFFF8h
0x1804336b0  test    eax, 0FFFFFFFBh
0x1804336b5  jnz     loc_180433741
0x1804336bb  movups  xmm0, xmmword ptr [rbp+4Fh+pAddr.sa_family]
0x1804336bf  mov     rcx, rbx; this
0x1804336c2  mov     byte ptr [rbx+1AD9h], 1
0x1804336c9  movups  xmm1, xmmword ptr [rbp+4Fh+pAddr.sa_data+0Ah]
0x1804336cd  movups  xmmword ptr [rbx+3B4h], xmm0
0x1804336d4  movups  xmmword ptr [rbx+3C0h], xmm1
0x1804336db  call    ?CalculateDynamicTimeout@KdNetConnection@@QEAAKXZ; KdNetConnection::CalculateDynamicTimeout(void)
0x1804336e0  cmp     byte ptr [rbx+1AC0h], 1
0x1804336e7  mov     [rbx+1AF0h], eax
0x1804336ed  jnz     short loc_180433733
0x1804336ef  mov     rax, 7FFFFFFFFFFFFFFFh
0x1804336f9  cmp     [r13+0], rax
0x1804336fd  jb      short loc_180433733
0x1804336ff  mov     rax, [r13+0]
0x180433703  mov     [rbx+1AB8h], rax
0x18043370a  mov     rax, [rbx+1AB8h]
0x180433711  inc     rax
0x180433714  mov     [rbx+1AB8h], rax
0x18043371b  jmp     short loc_180433733
0x18043371d  movups  xmm0, xmmword ptr [rbp+4Fh+pAddr.sa_family]
0x180433721  movups  xmm1, xmmword ptr [rbp+4Fh+pAddr.sa_data+0Ah]
0x180433725  movups  xmmword ptr [rbx+3B4h], xmm0
  ... truncated ...
```
