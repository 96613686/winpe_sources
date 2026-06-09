# KdNetConnection::ReadEx(void *,ulong,ulong *,ulong)

- ea: `0x180432a20`
- end: `0x180433194`
- name: `?ReadEx@KdNetConnection@@UEAAJPEAXKPEAKK@Z`
- size: `1908`
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
- `0x180432a20`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x180432d98`
- `api-ms-win-core-synch-l1-1-0!SleepEx` at `0x180432d98`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180432a80`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180432af2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180432bbc`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180432a80`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180432af2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180432bbc`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180432a70`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180432ad1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180432bac`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180432c54`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180432d6b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180432a70`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180432ad1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180432bac`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180432c54`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180432d6b`
- `WS2_32!__imp_htonl` at `0x180432e68`
- `WS2_32!__imp_htonl` at `0x180432e68`
- `WS2_32!__imp_inet_ntoa` at `0x180432dfd`
- `WS2_32!__imp_inet_ntoa` at `0x180432e22`
- `WS2_32!__imp_inet_ntoa` at `0x180432eee`
- `WS2_32!__imp_inet_ntoa` at `0x180432f16`
- `WS2_32!__imp_inet_ntoa` at `0x180432ffe`
- `WS2_32!__imp_inet_ntoa` at `0x180433027`
- `WS2_32!__imp_inet_ntoa` at `0x1804330ca`
- `WS2_32!__imp_inet_ntoa` at `0x1804330f3`
- `WS2_32!__imp_inet_ntoa` at `0x180432dfd`
- `WS2_32!__imp_inet_ntoa` at `0x180432e22`
- `WS2_32!__imp_inet_ntoa` at `0x180432eee`
- `WS2_32!__imp_inet_ntoa` at `0x180432f16`
- `WS2_32!__imp_inet_ntoa` at `0x180432ffe`
- `WS2_32!__imp_inet_ntoa` at `0x180433027`
- `WS2_32!__imp_inet_ntoa` at `0x1804330ca`
- `WS2_32!__imp_inet_ntoa` at `0x1804330f3`
- `WS2_32!__imp_ntohs` at `0x180432fe9`
- `WS2_32!__imp_ntohs` at `0x1804330b5`
- `WS2_32!__imp_ntohs` at `0x180432fe9`
- `WS2_32!__imp_ntohs` at `0x1804330b5`
- `WS2_32!__imp_recvfrom` at `0x180432cc7`
- `WS2_32!__imp_recvfrom` at `0x180432cc7`
- `WS2_32!__imp_WSAGetLastError` at `0x180432d47`
- `WS2_32!__imp_WSAGetLastError` at `0x180432d47`

## string_xrefs

- `0x180432c31`: `Target is not responding.  Attempting to reconnect...\n`
- `0x180432ce4`: `READ: EncSeqNum=0x%016I64X, `
- `0x180432e2e`: `Run nslookup %hs from a command prompt to get the machine name.\n`
- `0x180433047`: `You can get the target MAC address by running .kdtargetmac command.\n`
- `0x180433113`: `You can get the target MAC address by running .kdtargetmac command.\n`
- `0x18043314d`: `Net: Read %d bytes of %d\n`
- `0x18043312f`: `WinSock read error.  Error 0n%d\n`

## pseudocode

```c
__int64 __fastcall KdNetConnection::ReadEx(
        KdNetConnection *this,
        char *a2,
        unsigned int a3,
        unsigned int *a4,
        unsigned int a5)
{
  __int128 v9; // rax
  _QWORD *v10; // rbx
  __int128 v11; // rax
  char v12; // al
  char *v13; // rbx
  SOCKET v14; // rcx
  int v15; // r8d
  int v16; // esi
  __int64 (__fastcall *v17)(KdNetConnection *, char *, _QWORD, int *); // rax
  KdConnection *v18; // rcx
  unsigned int Error; // eax
  const unsigned __int16 *v20; // rdx
  unsigned int v21; // ecx
  struct in_addr v22; // ecx
  char *v23; // rax
  char *v24; // rax
  __int64 (__fastcall *v25)(KdNetConnection *, _QWORD); // rbx
  u_long v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  char *v30; // rax
  char *v31; // rax
  struct sockaddr v32; // xmm0
  unsigned int v33; // eax
  bool v34; // zf
  unsigned int v35; // ebx
  char *v36; // rax
  char *v37; // rax
  unsigned int v38; // ebx
  char *v39; // rax
  char *v40; // rax
  int v42; // [rsp+30h] [rbp-48h] BYREF
  LARGE_INTEGER Frequency; // [rsp+38h] [rbp-40h] BYREF
  LARGE_INTEGER v44; // [rsp+40h] [rbp-38h] BYREF
  int fromlen; // [rsp+48h] [rbp-30h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+50h] [rbp-28h] BYREF
  struct sockaddr from; // [rsp+58h] [rbp-20h] BYREF

  fromlen = 0;
  v42 = 0;
  from = 0;
  v44.QuadPart = 0;
  PerformanceCount.QuadPart = 0;
  Frequency.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  QueryPerformanceFrequency(&Frequency);
  PerformanceCount.QuadPart += Frequency.QuadPart * a5 / 1000000;
  while ( 1 )
  {
    if ( !*((_BYTE *)this + 6873) && *((_BYTE *)this + 6850) )
    {
      QueryPerformanceCounter(&v44);
      if ( v44.QuadPart < *((_QWORD *)this + 857) )
        v44 = *(LARGE_INTEGER *)((char *)this + 6856);
      QueryPerformanceFrequency(&Frequency);
      v9 = v44.QuadPart - *((_QWORD *)this + 857);
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
              QueryPerformanceCounter(&v44);
              QueryPerformanceFrequency(&Frequency);
              v11 = v44.QuadPart - *v10;
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
    v14 = *((_QWORD *)this + 114);
    v15 = 1474;
    if ( !v12 )
      v15 = a3;
    fromlen = 16;
    v16 = -2147024890;
    if ( v14 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
      return (unsigned int)v16;
    v42 = recvfrom(v14, v13, v15, 0, &from, &fromlen);
    if ( v42 == -1 )
    {
      Error = WSAGetLastError();
      v16 = Error;
      if ( Error != 10060 && Error != 10035 )
      {
        LnkOut(0x80000000, L"WinSock read error.  Error 0n%d\n", Error);
        goto LABEL_65;
      }
      QueryPerformanceCounter(&v44);
      if ( v44.QuadPart >= PerformanceCount.QuadPart )
        return 10060;
      if ( v16 == 10035 )
        SleepEx(1u, 1);
    }
    else
    {
      if ( v13 )
        LnkOut(0x80000000, L"READ: EncSeqNum=0x%016I64X, ", *(_QWORD *)(v13 + 6));
      v17 = *(__int64 (__fastcall **)(KdNetConnection *, char *, _QWORD, int *))(*(_QWORD *)this + 136LL);
      *((struct sockaddr *)this + 56) = from;
      v16 = v17(this, a2, a3, &v42);
      KdNetConnection::LogPacketReceived(this, v16);
      if ( v16 != -1879048169 )
      {
        if ( v16 == -805305302 )
        {
          LnkOut(2u, L"KDNET received an out of sequence ping packet.\n");
          v20 = L"The target machine restarted without notifying the debugger.\n";
          goto LABEL_36;
        }
        if ( v16 < 0 )
        {
          v22 = *(struct in_addr *)&from.sa_data[2];
          if ( *((_DWORD *)this + 221) == *(_DWORD *)&from.sa_data[2] )
          {
            FeatureUsageTracker::FeatureUsed(L"KDNET", L"ErrBadPacket", 5u);
            v22 = *(struct in_addr *)&from.sa_data[2];
          }
          v23 = inet_ntoa(v22);
          LnkOut(2u, L"Bad packet sent from %hs.\n", v23);
          v24 = inet_ntoa(*(struct in_addr *)&from.sa_data[2]);
          LnkOut(2u, L"Run nslookup %hs from a command prompt to get the machine name.\n", v24);
          goto LABEL_63;
        }
        if ( v16 )
          goto LABEL_63;
        if ( !*((_DWORD *)this + 217) && v42 == 12 )
        {
          v25 = *(__int64 (__fastcall **)(KdNetConnection *, _QWORD))(*(_QWORD *)this + 56LL);
          v26 = htonl(*((_DWORD *)a2 + 2));
          v27 = v25(this, v26);
          v16 = v27;
          if ( v27 < 0 )
          {
            LnkOut(2u, L"Failed to rebind socket to target specified host IP.  Error 0n%d\n", (unsigned int)v27);
            v28 = (*(__int64 (__fastcall **)(KdNetConnection *, _QWORD))(*(_QWORD *)this + 56LL))(this, 0);
            v16 = v28;
            if ( v28 < 0 )
            {
              LnkOut(2u, L"Failed to reinitialize socket.  Error 0n%d\n", (unsigned int)v28);
              v20 = L"This error is fatal.  Please shutdown and restart the debugger.\n";
LABEL_36:
              v21 = 2;
              goto LABEL_62;
            }
          }
          if ( v16 )
            goto LABEL_63;
        }
        v29 = *((_DWORD *)this + 221);
        v18 = (KdConnection *)*(unsigned int *)&from.sa_data[2];
        if ( *(_DWORD *)&from.sa_data[2] != v29 )
        {
          if ( v29 )
          {
            v30 = inet_ntoa(*(struct in_addr *)&from.sa_data[2]);
            LnkOut(4u, L"WARNING: Received data from %hs ", v30);
            v31 = inet_ntoa(*(struct in_addr *)((char *)this + 884));
            LnkOut(4u, L"while still connected to target %hs.\n", v31);
          }
          if ( *((_BYTE *)this + 6848) )
          {
            if ( ((v42 - 8) & 0xFFFFFFFB) == 0 )
            {
              v32 = from;
              *((_BYTE *)this + 6873) = 1;
              *((struct sockaddr *)this + 55) = v32;
              v33 = KdNetConnection::CalculateDynamicTimeout(this);
              v34 = *((_BYTE *)this + 6848) == 1;
              *((_DWORD *)this + 1724) = v33;
              if ( v34 && *(_QWORD *)a2 >= 0x7FFFFFFFFFFFFFFFuLL )
              {
                *((_QWORD *)this + 855) = *(_QWORD *)a2;
                ++*((_QWORD *)this + 855);
              }
            }
          }
          else
          {
            *((struct sockaddr *)this + 55) = from;
          }
          if ( *((_DWORD *)this + 221) )
          {
            FeatureUsageTracker::FeatureUsed(L"KDNET", L"ConnectionSuccessIPv4", 5u);
            LnkOut(0x80000000, L"\n");
            v35 = ntohs(*((_WORD *)this + 433));
            v36 = inet_ntoa(*(struct in_addr *)((char *)this + 884));
            LnkOut(1u, L"Connected to target %hs on port %d", v36, v35);
            v37 = inet_ntoa(*(struct in_addr *)((char *)this + 868));
            LnkOut(1u, L" on local IP %hs.\n", v37);
            LnkOut(1u, L"You can get the target MAC address by running .kdtargetmac command.\n");
          }
        }
        if ( *((_BYTE *)this + 6849) && v42 == 12 )
        {
          FeatureUsageTracker::FeatureUsed(L"KDNET", L"ConnectionSuccessIPv4", 5u);
          *((_BYTE *)this + 6873) = 1;
          *((_DWORD *)this + 1724) = KdNetConnection::CalculateDynamicTimeout(this);
          LnkOut(0x80000000, L"\n");
          v38 = ntohs(*((_WORD *)this + 433));
          v39 = inet_ntoa(*(struct in_addr *)((char *)this + 884));
          LnkOut(1u, L"Connected to target %hs on port %d", v39, v38);
          v40 = inet_ntoa(*(struct in_addr *)((char *)this + 868));
          LnkOut(1u, L" on local IP %hs.\n", v40);
          v20 = L"You can get the target MAC address by running .kdtargetmac command.\n";
          v21 = 1;
LABEL_62:
          LnkOut(v21, v20);
        }
LABEL_63:
        *a4 = v42;
LABEL_65:
        if ( !v16 )
        {
          if ( (*((_BYTE *)this + 72) & 1) != 0 )
            KdConnection::OutputIo(v18, L"Net: Read %d bytes of %d\n", a2, a3, *a4);
          *((_QWORD *)this + 20) += *a4;
        }
        return (unsigned int)v16;
      }
      LnkOut(0x80000000, L"\n");
    }
  }
}

```

## disassembly

```asm
0x180432a20  push    rbp
0x180432a22  push    rbx
0x180432a23  push    rsi
0x180432a24  push    rdi
0x180432a25  push    r12
0x180432a27  push    r13
0x180432a29  push    r14
0x180432a2b  push    r15
0x180432a2d  mov     rbp, rsp
0x180432a30  sub     rsp, 78h
0x180432a34  mov     rax, cs:__security_cookie
0x180432a3b  xor     rax, rsp
0x180432a3e  mov     [rbp+var_10], rax
0x180432a42  xor     r13d, r13d
0x180432a45  mov     rdi, rcx
0x180432a48  xorps   xmm0, xmm0
0x180432a4b  mov     [rbp+var_30], r13d
0x180432a4f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180432a53  mov     [rbp+var_48], r13d
0x180432a57  movups  xmmword ptr [rbp+var_20.sa_family], xmm0
0x180432a5b  mov     qword ptr [rbp+var_38], r13
0x180432a5f  mov     r15, r9
0x180432a62  mov     qword ptr [rbp+PerformanceCount], r13
0x180432a66  mov     r12d, r8d
0x180432a69  mov     qword ptr [rbp+Frequency], r13
0x180432a6d  mov     r14, rdx
0x180432a70  call    cs:__imp_QueryPerformanceCounter
0x180432a77  nop     dword ptr [rax+rax+00h]
0x180432a7c  lea     rcx, [rbp+Frequency]; lpFrequency
0x180432a80  call    cs:__imp_QueryPerformanceFrequency
0x180432a87  nop     dword ptr [rax+rax+00h]
0x180432a8c  mov     ecx, [rbp+arg_20]
0x180432a8f  mov     rax, 431BDE82D7B634DBh
0x180432a99  imul    rcx, qword ptr [rbp+Frequency]
0x180432a9e  imul    rcx
0x180432aa1  sar     rdx, 12h
0x180432aa5  mov     rax, rdx
0x180432aa8  shr     rax, 3Fh
0x180432aac  add     rdx, rax
0x180432aaf  add     qword ptr [rbp+PerformanceCount], rdx
0x180432ab3  cmp     [rdi+1AD9h], r13b
0x180432aba  jnz     loc_180432B63
0x180432ac0  cmp     [rdi+1AC2h], r13b
0x180432ac7  jz      loc_180432B63
0x180432acd  lea     rcx, [rbp+var_38]; lpPerformanceCount
0x180432ad1  call    cs:__imp_QueryPerformanceCounter
0x180432ad8  nop     dword ptr [rax+rax+00h]
0x180432add  mov     rax, [rdi+1AC8h]
0x180432ae4  cmp     qword ptr [rbp+var_38], rax
0x180432ae8  jge     short loc_180432AEE
0x180432aea  mov     qword ptr [rbp+var_38], rax
0x180432aee  lea     rcx, [rbp+Frequency]; lpFrequency
0x180432af2  call    cs:__imp_QueryPerformanceFrequency
0x180432af9  nop     dword ptr [rax+rax+00h]
0x180432afe  mov     rax, qword ptr [rbp+Frequency]
0x180432b02  test    rax, rax
0x180432b05  jns     short loc_180432B0D
0x180432b07  add     rax, 3FFh
0x180432b0d  sar     rax, 0Ah
0x180432b11  lea     rcx, [rax+1]
0x180432b15  mov     rax, qword ptr [rbp+var_38]
0x180432b19  sub     rax, [rdi+1AC8h]
0x180432b20  cqo
0x180432b22  mov     qword ptr [rbp+Frequency], rcx
0x180432b26  idiv    rcx
0x180432b29  cmp     rax, 1000h
0x180432b2f  jle     short loc_180432B63
0x180432b31  lea     rdx, aNoPingPacketRe; "No ping packet received, reseting data "...
0x180432b38  mov     ecx, 2; unsigned int
0x180432b3d  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180432b42  cmp     [rdi+1AC1h], r13b
0x180432b49  jz      short loc_180432B5C
0x180432b4b  lea     rdx, aTransportMayNo; "Transport may not re-connect automatica"...
0x180432b52  mov     ecx, 2; unsigned int
0x180432b57  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180432b5c  mov     [rdi+1AC2h], r13b
0x180432b63  cmp     [rdi+1AC1h], r13b
0x180432b6a  jz      loc_180432C6B
0x180432b70  cmp     [rdi+1AC2h], r13b
0x180432b77  jz      loc_180432C6B
0x180432b7d  cmp     [rdi+1AC0h], r13b
0x180432b84  jz      loc_180432C6B
0x180432b8a  lea     rbx, [rdi+1AD0h]
0x180432b91  cmp     [rbx], r13
0x180432b94  jz      loc_180432C6B
0x180432b9a  mov     rax, [rdi+18h]
0x180432b9e  test    byte ptr [rax+20h], 4
0x180432ba2  jz      loc_180432C6B
0x180432ba8  lea     rcx, [rbp+var_38]; lpPerformanceCount
0x180432bac  call    cs:__imp_QueryPerformanceCounter
0x180432bb3  nop     dword ptr [rax+rax+00h]
0x180432bb8  lea     rcx, [rbp+Frequency]; lpFrequency
0x180432bbc  call    cs:__imp_QueryPerformanceFrequency
0x180432bc3  nop     dword ptr [rax+rax+00h]
0x180432bc8  mov     rax, qword ptr [rbp+Frequency]
0x180432bcc  test    rax, rax
0x180432bcf  jns     short loc_180432BD7
0x180432bd1  add     rax, 3FFh
0x180432bd7  sar     rax, 0Ah
0x180432bdb  lea     rcx, [rax+1]
0x180432bdf  mov     rax, qword ptr [rbp+var_38]
0x180432be3  sub     rax, [rbx]
0x180432be6  cqo
0x180432be8  mov     qword ptr [rbp+Frequency], rcx
0x180432bec  idiv    rcx
0x180432bef  cmp     rax, 1C00h
0x180432bf5  jle     short loc_180432C6B
0x180432bf7  lea     rdx, aOfferStreamSta; "OFFER stream stale, sending POKE to tar"...
0x180432bfe  mov     ecx, 80000000h; unsigned int
0x180432c03  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180432c08  cmp     [rdi+1AD8h], r13b
0x180432c0f  jnz     short loc_180432C42
0x180432c11  mov     r8d, 5; unsigned int
0x180432c17  mov     byte ptr [rdi+1AD8h], 1
0x180432c1e  lea     rdx, aRebootpoke; "RebootPoke"
0x180432c25  lea     rcx, aKdnet_0; "KDNET"
0x180432c2c  call    ?FeatureUsed@FeatureUsageTracker@@SAXQEBG0K@Z; FeatureUsageTracker::FeatureUsed(ushort const * const,ushort const * const,ulong)
0x180432c31  lea     rdx, aTargetIsNotRes; "Target is not responding.  Attempting t"...
0x180432c38  mov     ecx, 4; unsigned int
0x180432c3d  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180432c42  mov     rax, [rdi]
0x180432c45  mov     rcx, rdi
0x180432c48  mov     rax, [rax+68h]
0x180432c4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180432c51  mov     rcx, rbx; lpPerformanceCount
0x180432c54  call    cs:__imp_QueryPerformanceCounter
0x180432c5b  nop     dword ptr [rax+rax+00h]
0x180432c60  imul    rax, qword ptr [rbp+Frequency], 0FFFFFFFFFFFFE800h
0x180432c68  add     [rbx], rax
0x180432c6b  mov     al, [rdi+1AC0h]
0x180432c71  lea     rbx, [rdi+9C6h]
0x180432c78  test    al, al
0x180432c7a  jnz     short loc_180432C7F
0x180432c7c  mov     rbx, r14
0x180432c7f  test    al, al
0x180432c81  mov     [r15], r13d
0x180432c84  mov     rcx, [rdi+390h]; s
0x180432c8b  mov     r8d, 5C2h
0x180432c91  cmovz   r8d, r12d; len
0x180432c95  mov     [rbp+var_30], 10h
0x180432c9c  mov     esi, 80070006h
0x180432ca1  lea     rax, [rcx-1]
0x180432ca5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180432ca9  ja      loc_180433174
0x180432caf  lea     rax, [rbp+var_30]
0x180432cb3  xor     r9d, r9d; flags
0x180432cb6  mov     [rsp+78h+fromlen], rax; fromlen
0x180432cbb  mov     rdx, rbx; buf
0x180432cbe  lea     rax, [rbp+var_20]
0x180432cc2  mov     [rsp+78h+from], rax; from
0x180432cc7  call    cs:__imp_recvfrom
0x180432cce  nop     dword ptr [rax+rax+00h]
0x180432cd3  mov     [rbp+var_48], eax
0x180432cd6  cmp     eax, 0FFFFFFFFh
0x180432cd9  jz      short loc_180432D47
0x180432cdb  test    rbx, rbx
0x180432cde  jz      short loc_180432CF5
0x180432ce0  mov     r8, [rbx+6]
0x180432ce4  lea     rdx, aReadEncseqnum0; "READ: EncSeqNum=0x%016I64X, "
0x180432ceb  mov     ecx, 80000000h; unsigned int
0x180432cf0  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180432cf5  mov     rax, [rdi]
0x180432cf8  lea     r9, [rbp+var_48]
0x180432cfc  movups  xmm0, xmmword ptr [rbp+var_20.sa_family]
0x180432d00  mov     r8d, r12d
0x180432d03  mov     rdx, r14
0x180432d06  mov     rcx, rdi
0x180432d09  mov     rax, [rax+88h]
0x180432d10  movdqu  xmmword ptr [rdi+380h], xmm0
0x180432d18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180432d1d  mov     edx, eax; int
0x180432d1f  mov     rcx, rdi; this
0x180432d22  mov     esi, eax
0x180432d24  call    ?LogPacketReceived@KdNetConnection@@QEAAXJ@Z; KdNetConnection::LogPacketReceived(long)
0x180432d29  cmp     esi, 90000017h
0x180432d2f  jnz     short loc_180432DA9
0x180432d31  lea     rdx, asc_1805BAA38; "\n"
0x180432d38  mov     ecx, 80000000h; unsigned int
0x180432d3d  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180432d42  jmp     loc_180432AB3
0x180432d47  call    cs:__imp_WSAGetLastError
0x180432d4e  nop     dword ptr [rax+rax+00h]
0x180432d53  mov     esi, eax
0x180432d55  cmp     eax, 274Ch
0x180432d5a  jz      short loc_180432D67
0x180432d5c  cmp     eax, 2733h
0x180432d61  jnz     loc_18043312C
0x180432d67  lea     rcx, [rbp+var_38]; lpPerformanceCount
0x180432d6b  call    cs:__imp_QueryPerformanceCounter
0x180432d72  nop     dword ptr [rax+rax+00h]
0x180432d77  mov     rax, qword ptr [rbp+PerformanceCount]
0x180432d7b  cmp     qword ptr [rbp+var_38], rax
0x180432d7f  jge     loc_18043316F
0x180432d85  cmp     esi, 2733h
0x180432d8b  jnz     loc_180432AB3
0x180432d91  mov     edx, 1; bAlertable
0x180432d96  mov     ecx, edx; dwMilliseconds
0x180432d98  call    cs:__imp_SleepEx
0x180432d9f  nop     dword ptr [rax+rax+00h]
0x180432da4  jmp     loc_180432AB3
0x180432da9  cmp     esi, 0D000042Ah
0x180432daf  jnz     short loc_180432DD2
0x180432db1  mov     ebx, 2
0x180432db6  lea     rdx, aKdnetReceivedA; "KDNET received an out of sequence ping "...
0x180432dbd  mov     ecx, ebx; unsigned int
0x180432dbf  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180432dc4  lea     rdx, aTheTargetMachi_0; "The target machine restarted without no"...
0x180432dcb  mov     ecx, ebx
0x180432dcd  jmp     loc_18043311F
0x180432dd2  test    esi, esi
0x180432dd4  jns     short loc_180432E44
0x180432dd6  mov     ecx, dword ptr [rbp+var_20.sa_data+2]
0x180432dd9  cmp     [rdi+374h], ecx
0x180432ddf  jnz     short loc_180432DFD
0x180432de1  mov     r8d, 5; unsigned int
0x180432de7  lea     rdx, aErrbadpacket; "ErrBadPacket"
0x180432dee  lea     rcx, aKdnet_0; "KDNET"
0x180432df5  call    ?FeatureUsed@FeatureUsageTracker@@SAXQEBG0K@Z; FeatureUsageTracker::FeatureUsed(ushort const * const,ushort const * const,ulong)
0x180432dfa  mov     ecx, dword ptr [rbp+var_20.sa_data+2]; in
0x180432dfd  call    cs:__imp_inet_ntoa
0x180432e04  nop     dword ptr [rax+rax+00h]
0x180432e09  mov     ebx, 2
0x180432e0e  lea     rdx, aBadPacketSentF; "Bad packet sent from %hs.\n"
0x180432e15  mov     r8, rax
0x180432e18  mov     ecx, ebx; unsigned int
0x180432e1a  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180432e1f  mov     ecx, dword ptr [rbp+var_20.sa_data+2]; in
0x180432e22  call    cs:__imp_inet_ntoa
0x180432e29  nop     dword ptr [rax+rax+00h]
0x180432e2e  lea     rdx, aRunNslookupHsF; "Run nslookup %hs from a command prompt "...
0x180432e35  mov     ecx, ebx; unsigned int
0x180432e37  mov     r8, rax
0x180432e3a  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180432e3f  jmp     loc_180433124
0x180432e44  jnz     loc_180433124
0x180432e4a  cmp     [rdi+364h], r13d
0x180432e51  jnz     loc_180432ED9
0x180432e57  cmp     [rbp+var_48], 0Ch
0x180432e5b  jnz     short loc_180432ED9
0x180432e5d  mov     rax, [rdi]
0x180432e60  mov     ecx, [r14+8]; hostlong
0x180432e64  mov     rbx, [rax+38h]
0x180432e68  call    cs:__imp_htonl
0x180432e6f  nop     dword ptr [rax+rax+00h]
0x180432e74  mov     edx, eax
0x180432e76  mov     rcx, rdi
0x180432e79  mov     rax, rbx
0x180432e7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180432e81  mov     esi, eax
0x180432e83  test    eax, eax
0x180432e85  jns     short loc_180432ED1
0x180432e87  mov     ebx, 2
0x180432e8c  lea     rdx, aFailedToRebind; "Failed to rebind socket to target speci"...
0x180432e93  mov     ecx, ebx; unsigned int
0x180432e95  mov     r8d, eax
0x180432e98  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180432e9d  mov     rax, [rdi]
0x180432ea0  xor     edx, edx
0x180432ea2  mov     rcx, rdi
0x180432ea5  mov     rax, [rax+38h]
0x180432ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180432eae  mov     esi, eax
0x180432eb0  test    eax, eax
0x180432eb2  jns     short loc_180432ED1
0x180432eb4  mov     r8d, eax
0x180432eb7  lea     rdx, aFailedToReinit; "Failed to reinitialize socket.  Error 0"...
0x180432ebe  mov     ecx, ebx; unsigned int
0x180432ec0  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180432ec5  lea     rdx, aThisErrorIsFat; "This error is fatal.  Please shutdown a"...
0x180432ecc  jmp     loc_180432DCB
0x180432ed1  test    esi, esi
0x180432ed3  jnz     loc_180433124
0x180432ed9  mov     eax, [rdi+374h]
0x180432edf  mov     ecx, dword ptr [rbp+var_20.sa_data+2]; in
0x180432ee2  cmp     ecx, eax
0x180432ee4  jz      loc_180433058
0x180432eea  test    eax, eax
0x180432eec  jz      short loc_180432F33
0x180432eee  call    cs:__imp_inet_ntoa
0x180432ef5  nop     dword ptr [rax+rax+00h]
0x180432efa  mov     ebx, 4
0x180432eff  lea     rdx, aWarningReceive; "WARNING: Received data from %hs "
0x180432f06  mov     r8, rax
0x180432f09  mov     ecx, ebx; unsigned int
0x180432f0b  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180432f10  mov     ecx, [rdi+374h]; in
0x180432f16  call    cs:__imp_inet_ntoa
0x180432f1d  nop     dword ptr [rax+rax+00h]
0x180432f22  lea     rdx, aWhileStillConn; "while still connected to target %hs.\n"
0x180432f29  mov     ecx, ebx; unsigned int
0x180432f2b  mov     r8, rax
0x180432f2e  call    ?LnkOut@@YAXKPEBGZZ; LnkOut(ulong,ushort const *,...)
0x180432f33  cmp     [rdi+1AC0h], r13b
0x180432f3a  jz      short loc_180432F9F
0x180432f3c  mov     eax, [rbp+var_48]
0x180432f3f  add     eax, 0FFFFFFF8h
0x180432f42  test    eax, 0FFFFFFFBh
0x180432f47  jnz     short loc_180432FAB
0x180432f49  movups  xmm0, xmmword ptr [rbp+var_20.sa_family]
0x180432f4d  mov     rcx, rdi; this
  ... truncated ...
```
