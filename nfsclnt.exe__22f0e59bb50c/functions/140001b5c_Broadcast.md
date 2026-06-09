# Broadcast

- ea: `0x140001b5c`
- end: `0x1400022f5`
- name: `Broadcast`
- size: `1945`
- prototype: `int __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation`

## callers

- `0x140002300`

## callees

- `0x140001b5c`
- `0x140002650`
- `0x140002c40`
- `0x140002d1c`
- `0x140002eac`
- `0x140003030`
- `0x14000b030`
- `0x14000ba50`
- `0x14000bf58`
- `0x14000c724`
- `0x14001830e`
- `0x140018350`
- `0x140019010`

## import_xrefs

- `KERNEL32!SleepEx` at `0x140001cdc`
- `KERNEL32!SleepEx` at `0x140001cdc`
- `KERNEL32!GetCurrentProcessId` at `0x140001df9`
- `KERNEL32!GetCurrentProcessId` at `0x140001df9`
- `msvcrt!time` at `0x140001df0`
- `msvcrt!time` at `0x140001df0`
- `WS2_32!FreeAddrInfoW` at `0x140001cc2`
- `WS2_32!FreeAddrInfoW` at `0x140001cc2`
- `WS2_32!GetAddrInfoW` at `0x140001c7a`
- `WS2_32!GetAddrInfoW` at `0x140001c7a`
- `WS2_32!GetHostNameW` at `0x140001c43`
- `WS2_32!GetHostNameW` at `0x140001c43`
- `WS2_32!__imp_bind` at `0x140001d2c`
- `WS2_32!__imp_bind` at `0x140001d2c`
- `WS2_32!__imp_closesocket` at `0x14000222d`
- `WS2_32!__imp_closesocket` at `0x14000222d`
- `WS2_32!__imp_htons` at `0x140001dcf`
- `WS2_32!__imp_htons` at `0x140001dcf`
- `WS2_32!__imp_recvfrom` at `0x1400020cb`
- `WS2_32!__imp_recvfrom` at `0x1400020cb`
- `WS2_32!__imp_select` at `0x14000205c`
- `WS2_32!__imp_select` at `0x14000205c`
- `WS2_32!__imp_sendto` at `0x140001fd8`
- `WS2_32!__imp_sendto` at `0x140001fd8`
- `WS2_32!__imp_setsockopt` at `0x140001d67`
- `WS2_32!__imp_setsockopt` at `0x140001d99`
- `WS2_32!__imp_setsockopt` at `0x140001d67`
- `WS2_32!__imp_setsockopt` at `0x140001d99`
- `WS2_32!__imp_socket` at `0x140001cf9`
- `WS2_32!__imp_socket` at `0x140001cf9`
- `WS2_32!__imp_WSAGetLastError` at `0x14000208a`
- `WS2_32!__imp_WSAGetLastError` at `0x1400021ff`
- `WS2_32!__imp_WSAGetLastError` at `0x14000208a`
- `WS2_32!__imp_WSAGetLastError` at `0x1400021ff`

## pseudocode

```c
int __fastcall Broadcast(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // r12
  int v6; // r8d
  __int64 v7; // rax
  int v8; // edx
  int v9; // r8d
  struct addrinfoW *v10; // rcx
  unsigned int v11; // edi
  PADDRINFOW i; // r8
  __int64 v13; // rdx
  int v14; // esi
  SOCKET v15; // rax
  SOCKET v16; // rbx
  _DWORD *v17; // rax
  int v18; // esi
  u_short v19; // ax
  _DWORD *v20; // rcx
  int v21; // ebx
  DWORD v22; // r14d
  _OWORD *v23; // rbx
  __int64 v24; // r8
  int v25; // r9d
  __int64 v26; // xmm1_8
  _QWORD *v27; // r10
  __int64 (__fastcall *v28)(); // rax
  unsigned int v29; // r13d
  int v30; // ebx
  u_int v31; // ecx
  unsigned int v32; // r8d
  u_int j; // edx
  int v34; // eax
  int v35; // esi
  SOCKET k; // rcx
  int v37; // eax
  int v38; // ebx
  int v39; // eax
  __int64 v40; // rbx
  char v42[4]; // [rsp+50h] [rbp-B0h] BYREF
  int fromlen; // [rsp+54h] [rbp-ACh] BYREF
  __int16 v44; // [rsp+58h] [rbp-A8h] BYREF
  char optval[4]; // [rsp+5Ch] [rbp-A4h] BYREF
  PADDRINFOW ppResult; // [rsp+60h] [rbp-A0h] BYREF
  timeval timeout; // [rsp+68h] [rbp-98h] BYREF
  ADDRINFOW pHints; // [rsp+70h] [rbp-90h] BYREF
  int v49; // [rsp+A0h] [rbp-60h] BYREF
  int v50; // [rsp+A4h] [rbp-5Ch]
  __int64 (__fastcall **v51)(); // [rsp+A8h] [rbp-58h]
  char *v52; // [rsp+B8h] [rbp-48h]
  char *v53; // [rsp+C0h] [rbp-40h]
  int v54; // [rsp+C8h] [rbp-38h]
  struct sockaddr to; // [rsp+100h] [rbp+0h] BYREF
  struct sockaddr v56; // [rsp+110h] [rbp+10h] BYREF
  struct sockaddr from; // [rsp+120h] [rbp+20h] BYREF
  fd_set readfds; // [rsp+130h] [rbp+30h] BYREF
  __int64 v59; // [rsp+340h] [rbp+240h] BYREF
  __int64 v60; // [rsp+348h] [rbp+248h]
  _BYTE v61[24]; // [rsp+350h] [rbp+250h]
  __int64 v62; // [rsp+368h] [rbp+268h]
  __int128 v63; // [rsp+370h] [rbp+270h]
  __int64 v64; // [rsp+380h] [rbp+280h]
  SOCKET s[20]; // [rsp+390h] [rbp+290h]
  char v66[16]; // [rsp+430h] [rbp+330h] BYREF
  char buf[128]; // [rsp+440h] [rbp+340h] BYREF
  char v68[128]; // [rsp+4C0h] [rbp+3C0h] BYREF
  WCHAR name[1032]; // [rsp+540h] [rbp+440h] BYREF

  strcpy(v66, "Broadcast");
  memset_0(buf, 0, sizeof(buf));
  *(_DWORD *)optval = 0;
  *(&readfds.fd_count + 1) = 0;
  v5 = 0;
  v56 = 0;
  to = 0;
  from = 0;
  memset_0(&readfds, 0, 0x204u);
  timeout = 0;
  fromlen = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_sSDddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      **(_DWORD **)(a4 + 24),
      v6,
      (unsigned int)v66,
      *(_QWORD *)(a4 + 8),
      **(_DWORD **)(a4 + 24));
  LODWORD(v7) = GetHostNameW(name, 1025);
  if ( (_DWORD)v7 != -1 )
  {
    ppResult = 0;
    memset(&pHints, 0, sizeof(pHints));
    LODWORD(v7) = GetAddrInfoW(name, 0, &pHints, &ppResult);
    if ( !(_DWORD)v7 )
    {
      v10 = ppResult;
      v11 = 0;
      for ( i = ppResult; i; i = i->ai_next )
      {
        if ( v11 >= 0x14 )
          break;
        if ( i->ai_family == 2 )
        {
          v13 = v11++;
          *((_DWORD *)&v59 + v13) = *(_DWORD *)&i->ai_addr->sa_data[2];
        }
      }
      FreeAddrInfoW(v10);
      if ( v11 )
      {
        while ( 2 )
        {
          v14 = 0;
          while ( 1 )
          {
            v15 = socket(2, 2, 17);
            s[v5] = v15;
            v16 = v15;
            if ( v15 != -1 )
              break;
            LODWORD(v7) = SleepEx(0x3E8u, 0);
            if ( (unsigned int)++v14 > 0x32 )
            {
              v27 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                LODWORD(v7) = WPP_SF_s(
                                *((_QWORD *)WPP_GLOBAL_Control + 2),
                                11,
                                &WPP_85ad4d236ab33e750ff5ff1970e92ee3_Traceguids,
                                v66);
                goto LABEL_62;
              }
              goto LABEL_63;
            }
          }
          *(_DWORD *)&v56.sa_data[2] = *((_DWORD *)&v59 + v5);
          *(_DWORD *)&v56.sa_family = 2;
          LODWORD(v7) = bind(v15, &v56, 16);
          if ( (_DWORD)v7 == -1 )
            goto LABEL_62;
          v17 = *(_DWORD **)(a4 + 24);
          *(_DWORD *)optval = 1;
          if ( *v17 == -1 )
          {
            LODWORD(v7) = setsockopt(v16, 0xFFFF, 32, optval, 4);
            if ( (_DWORD)v7 == -1 )
              goto LABEL_62;
          }
          *(_DWORD *)v42 = 1;
          LODWORD(v7) = setsockopt(v16, 0xFFFF, -5, v42, 4);
          if ( (_DWORD)v7 == -1 )
            goto LABEL_62;
          v5 = (unsigned int)(v5 + 1);
          if ( (unsigned int)v5 < v11 )
            continue;
          break;
        }
      }
      v18 = 128;
      to = 0;
      *(_DWORD *)v42 = 128;
      to.sa_family = 2;
      v19 = htons(0x6Fu);
      v20 = *(_DWORD **)(a4 + 24);
      *(_WORD *)to.sa_data = v19;
      *(_DWORD *)&to.sa_data[2] = *v20;
      timeout.tv_sec = v20[2];
      timeout.tv_usec = 0;
      v21 = time(0);
      v22 = v21 ^ GetCurrentProcessId();
      LODWORD(ppResult) = v22;
      memset_0(&v59, 0, 0x48u);
      v50 = 0;
      memset(&pHints, 0, 32);
      memset_0(&v49, 0, 0x54u);
      v23 = authunix_create_default();
      if ( v23 )
      {
        v59 = v22;
        v60 = 0x186A000000002LL;
        *(_QWORD *)v61 = 0x500000002LL;
        *(_OWORD *)&v61[8] = *v23;
        v62 = *((_QWORD *)v23 + 2);
        v63 = *(_OWORD *)((char *)v23 + 24);
        v26 = *((_QWORD *)v23 + 5);
        pHints.ai_canonname = (PWSTR)xdr_void;
        v53 = buf;
        v51 = off_140020030;
        v52 = buf;
        v64 = v26;
        pHints.ai_flags = 100005;
        *(_QWORD *)&pHints.ai_family = 1;
        pHints.ai_addrlen = 0;
        v49 = 0;
        v54 = 128;
        if ( (unsigned int)xdr_callmsg((__int64)&v49, (__int64)&v59, v24, v25)
          && (unsigned int)xdr_rmtcall_args(&v49, &pHints) )
        {
          v18 = ((__int64 (__fastcall *)(int *))v51[4])(&v49);
        }
        else
        {
          v18 = 0;
        }
        *(_DWORD *)v42 = v18;
        v28 = v51[7];
        if ( v28 )
          ((void (__fastcall *)(int *))v28)(&v49);
        (*(void (__fastcall **)(_OWORD *))(*((_QWORD *)v23 + 7) + 32LL))(v23);
      }
      v29 = 0;
LABEL_32:
      v30 = 0;
      if ( !v11 )
        goto LABEL_35;
      while ( 1 )
      {
        LODWORD(v7) = sendto(s[v30], buf, v18, 0, &to, 16);
        if ( (_DWORD)v7 == -1 )
          break;
        if ( ++v30 >= v11 )
        {
          while ( 1 )
          {
            while ( 1 )
            {
LABEL_35:
              v31 = 0;
              v32 = 0;
              for ( readfds.fd_count = 0; v32 < v11; ++v32 )
              {
                for ( j = 0; j < v31; ++j )
                {
                  if ( readfds.fd_array[j] == s[v32] )
                    break;
                }
                if ( j == v31 && v31 < 0x40 )
                {
                  readfds.fd_array[j] = s[v32];
                  v31 = ++readfds.fd_count;
                }
              }
              v34 = select(0, &readfds, 0, 0, &timeout);
              if ( v34 != -1 )
                break;
              LODWORD(v7) = WSAGetLastError();
              if ( (_DWORD)v7 != 10004 )
                goto LABEL_62;
            }
            if ( !v34 )
              break;
            v35 = 0;
            if ( readfds.fd_count )
            {
              while ( 1 )
              {
                for ( k = readfds.fd_array[v35]; ; k = readfds.fd_array[v35] )
                {
                  fromlen = 16;
                  v37 = recvfrom(k, v68, 128, 0, &from, &fromlen);
                  v38 = v37;
                  if ( v37 >= 0 )
                    break;
                  LODWORD(v7) = WSAGetLastError();
                  if ( (_DWORD)v7 != 10004 )
                    goto LABEL_62;
                }
                if ( (unsigned int)v37 < 4 )
                  break;
                v59 = 0;
                v60 = 0;
                if ( v37 == 10040 )
                  v38 = 128;
                v62 = 0;
                v64 = 0;
                v50 = 0;
                *(_QWORD *)&pHints.ai_socktype = 0;
                v44 = 0;
                memset_0(&v49, 0, 0x54u);
                pHints.ai_addrlen = 0;
                *(_QWORD *)&v63 = &pHints;
                *(_OWORD *)v61 = null_auth;
                *((_QWORD *)&v63 + 1) = xdr_rmtcallres;
                *(_QWORD *)&pHints.ai_flags = &v44;
                pHints.ai_canonname = (PWSTR)xdr_void;
                v51 = off_140020030;
                v53 = v68;
                v52 = v68;
                *(_QWORD *)&v61[16] = qword_140022270;
                v49 = 1;
                v54 = v38;
                if ( !(unsigned int)xdr_replymsg((__int64)&v49, (__int64)&v59)
                  || (_DWORD)v60
                  || (v39 = v59, (_DWORD)v62) )
                {
                  v39 = 0;
                }
                if ( (_DWORD)ppResult == v39 )
                {
                  LODWORD(v7) = RPCBroadcastReply(a4, &from);
                  if ( (_DWORD)v7 )
                    goto LABEL_62;
                }
                if ( ++v35 >= readfds.fd_count )
                  goto LABEL_35;
              }
            }
          }
          v27 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          {
            WPP_SF_sdd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v8,
              v9,
              (unsigned int)v66,
              v29,
              *(_DWORD *)(*(_QWORD *)(a4 + 24) + 4LL));
            v27 = WPP_GLOBAL_Control;
          }
          v7 = *(_QWORD *)(a4 + 24);
          ++v29;
          v18 = *(_DWORD *)v42;
          if ( v29 <= *(_DWORD *)(v7 + 4) )
            goto LABEL_32;
          goto LABEL_63;
        }
      }
    }
  }
LABEL_62:
  v27 = WPP_GLOBAL_Control;
LABEL_63:
  v40 = 0;
  if ( (_DWORD)v5 )
  {
    do
    {
      LODWORD(v7) = closesocket(s[v40]);
      v40 = (unsigned int)(v40 + 1);
    }
    while ( (unsigned int)v40 < (unsigned int)v5 );
    v27 = WPP_GLOBAL_Control;
  }
  if ( v27 != &WPP_GLOBAL_Control && (*((_BYTE *)v27 + 28) & 0x10) != 0 )
    LODWORD(v7) = WPP_SF_sSD(v27[2], v8, v9, (unsigned int)v66, *(_QWORD *)(a4 + 8), **(_DWORD **)(a4 + 24));
  return v7;
}

```

## disassembly

```asm
0x140001b5c  push    rbp
0x140001b5e  push    rbx
0x140001b5f  push    rsi
0x140001b60  push    rdi
0x140001b61  push    r12
0x140001b63  push    r13
0x140001b65  push    r14
0x140001b67  push    r15
0x140001b69  lea     rbp, [rsp-0C68h]
0x140001b71  sub     rsp, 0D68h
0x140001b78  mov     rax, cs:__security_cookie
0x140001b7f  xor     rax, rsp
0x140001b82  mov     [rbp+0CA0h+var_50], rax
0x140001b89  movsd   xmm0, qword ptr cs:aBroadcast; "Broadcast"
0x140001b91  lea     rcx, [rbp+0CA0h+buf]; void *
0x140001b98  movzx   eax, word ptr cs:aBroadcast+8; "t"
0x140001b9f  xor     edx, edx; Val
0x140001ba1  mov     r8d, 80h; Size
0x140001ba7  movsd   qword ptr [rbp+0CA0h+var_970], xmm0
0x140001baf  mov     word ptr [rbp+0CA0h+var_970+8], ax
0x140001bb6  mov     r15, r9
0x140001bb9  call    memset_0
0x140001bbe  xorps   xmm0, xmm0
0x140001bc1  lea     rcx, [rbp+0CA0h+readfds]; void *
0x140001bc5  xor     r14d, r14d
0x140001bc8  xorps   xmm1, xmm1
0x140001bcb  xor     eax, eax
0x140001bcd  mov     dword ptr [rsp+0DA0h+optval], r14d
0x140001bd2  xor     edx, edx; Val
0x140001bd4  mov     dword ptr [rbp+0CA0h+readfds+4], eax
0x140001bd7  mov     r8d, 204h; Size
0x140001bdd  mov     r12d, r14d
0x140001be0  movups  xmmword ptr [rbp+0CA0h+var_C90.sa_family], xmm0
0x140001be4  movups  xmmword ptr [rbp+0CA0h+to.sa_family], xmm1
0x140001be8  movups  xmmword ptr [rbp+0CA0h+from.sa_family], xmm0
0x140001bec  call    memset_0
0x140001bf1  mov     qword ptr [rsp+0DA0h+timeout.tv_sec], r14
0x140001bf6  mov     [rsp+0DA0h+fromlen], r14d
0x140001bfb  mov     rcx, cs:WPP_GLOBAL_Control
0x140001c02  lea     rax, WPP_GLOBAL_Control
0x140001c09  cmp     rcx, rax
0x140001c0c  jz      short loc_140001C37
0x140001c0e  test    byte ptr [rcx+1Ch], 10h
0x140001c12  jz      short loc_140001C37
0x140001c14  mov     rax, [r15+18h]
0x140001c18  lea     r9, [rbp+0CA0h+var_970]
0x140001c1f  mov     rcx, [rcx+10h]
0x140001c23  mov     edx, [rax]
0x140001c25  mov     rax, [r15+8]
0x140001c29  mov     [rsp+0DA0h+tolen], edx
0x140001c2d  mov     qword ptr [rsp+0DA0h+optlen], rax
0x140001c32  call    WPP_SF_sSDddd
0x140001c37  mov     edx, 401h; namelen
0x140001c3c  lea     rcx, [rbp+0CA0h+name]; name
0x140001c43  call    cs:__imp_GetHostNameW
0x140001c49  cmp     eax, 0FFFFFFFFh
0x140001c4c  jz      loc_140002210
0x140001c52  xorps   xmm0, xmm0
0x140001c55  mov     [rsp+0DA0h+ppResult], r14
0x140001c5a  lea     r9, [rsp+0DA0h+ppResult]; ppResult
0x140001c5f  xor     edx, edx; pServiceName
0x140001c61  lea     r8, [rsp+0DA0h+pHints]; pHints
0x140001c66  lea     rcx, [rbp+0CA0h+name]; pNodeName
0x140001c6d  movups  xmmword ptr [rsp+0DA0h+pHints.ai_flags], xmm0
0x140001c72  movups  xmmword ptr [rbp+0CA0h+pHints.ai_addrlen], xmm0
0x140001c76  movups  xmmword ptr [rbp+0CA0h+pHints.ai_addr], xmm0
0x140001c7a  call    cs:__imp_GetAddrInfoW
0x140001c80  test    eax, eax
0x140001c82  jnz     loc_140002210
0x140001c88  mov     rcx, [rsp+0DA0h+ppResult]; pAddrInfo
0x140001c8d  lea     r13d, [rax+2]
0x140001c91  mov     edi, r14d
0x140001c94  mov     r8, rcx
0x140001c97  test    rcx, rcx
0x140001c9a  jz      short loc_140001CC2
0x140001c9c  cmp     edi, 14h
0x140001c9f  jnb     short loc_140001CC2
0x140001ca1  cmp     [r8+4], r13d
0x140001ca5  jnz     short loc_140001CB9
0x140001ca7  mov     rax, [r8+20h]
0x140001cab  mov     edx, edi
0x140001cad  inc     edi
0x140001caf  mov     eax, [rax+4]
0x140001cb2  mov     dword ptr [rbp+rdx*4+0CA0h+var_A60], eax
0x140001cb9  mov     r8, [r8+28h]
0x140001cbd  test    r8, r8
0x140001cc0  jnz     short loc_140001C9C
0x140001cc2  call    cs:__imp_FreeAddrInfoW
0x140001cc8  test    edi, edi
0x140001cca  jz      loc_140001DB7
0x140001cd0  mov     esi, r14d
0x140001cd3  jmp     short loc_140001CED
0x140001cd5  xor     edx, edx; bAlertable
0x140001cd7  mov     ecx, 3E8h; dwMilliseconds
0x140001cdc  call    cs:__imp_SleepEx
0x140001ce2  inc     esi
0x140001ce4  cmp     esi, 32h ; '2'
0x140001ce7  ja      loc_140001F32
0x140001ced  mov     r8d, 11h; protocol
0x140001cf3  mov     edx, r13d; type
0x140001cf6  mov     ecx, r13d; af
0x140001cf9  call    cs:__imp_socket
0x140001cff  mov     [rbp+r12*8+0CA0h+s], rax
0x140001d07  mov     rbx, rax
0x140001d0a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140001d0e  jz      short loc_140001CD5
0x140001d10  mov     eax, dword ptr [rbp+r12*4+0CA0h+var_A60]
0x140001d18  lea     rdx, [rbp+0CA0h+var_C90]; name
0x140001d1c  mov     r8d, 10h; namelen
0x140001d22  mov     dword ptr [rbp+0CA0h+var_C90.sa_data+2], eax
0x140001d25  mov     rcx, rbx; s
0x140001d28  mov     dword ptr [rbp+0CA0h+var_C90.sa_family], r13d
0x140001d2c  call    cs:__imp_bind
0x140001d32  cmp     eax, 0FFFFFFFFh
0x140001d35  jz      loc_140002210
0x140001d3b  mov     rax, [r15+18h]
0x140001d3f  mov     dword ptr [rsp+0DA0h+optval], 1
0x140001d47  cmp     dword ptr [rax], 0FFFFFFFFh
0x140001d4a  jnz     short loc_140001D76
0x140001d4c  lea     r9, [rsp+0DA0h+optval]; optval
0x140001d51  mov     [rsp+0DA0h+optlen], 4; optlen
0x140001d59  mov     edx, 0FFFFh; level
0x140001d5e  mov     r8d, 20h ; ' '; optname
0x140001d64  mov     rcx, rbx; s
0x140001d67  call    cs:__imp_setsockopt
0x140001d6d  cmp     eax, 0FFFFFFFFh
0x140001d70  jz      loc_140002210
0x140001d76  lea     r9, [rsp+0DA0h+var_D50]; optval
0x140001d7b  mov     dword ptr [rsp+0DA0h+var_D50], 1
0x140001d83  mov     edx, 0FFFFh; level
0x140001d88  mov     [rsp+0DA0h+optlen], 4; optlen
0x140001d90  mov     r8d, 0FFFFFFFBh; optname
0x140001d96  mov     rcx, rbx; s
0x140001d99  call    cs:__imp_setsockopt
0x140001d9f  cmp     eax, 0FFFFFFFFh
0x140001da2  jz      loc_140002210
0x140001da8  inc     r12d
0x140001dab  xor     r14d, r14d
0x140001dae  cmp     r12d, edi
0x140001db1  jb      loc_140001CD0
0x140001db7  mov     esi, 80h
0x140001dbc  xorps   xmm0, xmm0
0x140001dbf  movups  xmmword ptr [rbp+0CA0h+to.sa_family], xmm0
0x140001dc3  mov     dword ptr [rsp+0DA0h+var_D50], esi
0x140001dc7  mov     [rbp+0CA0h+to.sa_family], r13w
0x140001dcc  lea     ecx, [rsi-11h]; hostshort
0x140001dcf  call    cs:__imp_htons
0x140001dd5  mov     rcx, [r15+18h]
0x140001dd9  mov     word ptr [rbp+0CA0h+to.sa_data], ax
0x140001ddd  mov     eax, [rcx]
0x140001ddf  mov     dword ptr [rbp+0CA0h+to.sa_data+2], eax
0x140001de2  mov     eax, [rcx+8]
0x140001de5  xor     ecx, ecx; Time
0x140001de7  mov     [rsp+0DA0h+timeout.tv_sec], eax
0x140001deb  mov     [rsp+0DA0h+timeout.tv_usec], r14d
0x140001df0  call    cs:__imp_time
0x140001df6  mov     rbx, rax
0x140001df9  call    cs:__imp_GetCurrentProcessId
0x140001dff  xor     edx, edx; Val
0x140001e01  lea     r8d, [rsi-38h]; Size
0x140001e05  mov     r14d, eax
0x140001e08  lea     rcx, [rbp+0CA0h+var_A60]; void *
0x140001e0f  xor     r14d, ebx
0x140001e12  mov     dword ptr [rsp+0DA0h+ppResult], r14d
0x140001e17  call    memset_0
0x140001e1c  xorps   xmm0, xmm0
0x140001e1f  lea     r8d, [rsi-2Ch]; Size
0x140001e23  xor     eax, eax
0x140001e25  lea     rcx, [rbp+0CA0h+var_D00]; void *
0x140001e29  xor     edx, edx; Val
0x140001e2b  mov     [rbp+0CA0h+var_CFC], eax
0x140001e2e  movups  xmmword ptr [rsp+0DA0h+pHints.ai_flags], xmm0
0x140001e33  movups  xmmword ptr [rbp+0CA0h+pHints.ai_addrlen], xmm0
0x140001e37  call    memset_0
0x140001e3c  call    authunix_create_default
0x140001e41  mov     rbx, rax
0x140001e44  lea     rcx, off_140020030
0x140001e4b  lea     rax, xdr_void
0x140001e52  test    rbx, rbx
0x140001e55  jz      loc_140001FA3
0x140001e5b  mov     dword ptr [rbp+0CA0h+var_A60], r14d
0x140001e62  lea     rdx, [rbp+0CA0h+var_A60]
0x140001e69  mov     dword ptr [rbp+0CA0h+var_A58], r13d
0x140001e70  xor     r14d, r14d
0x140001e73  mov     dword ptr [rbp+0CA0h+var_A60+4], r14d
0x140001e7a  mov     dword ptr [rbp+0CA0h+var_A58+4], 186A0h
0x140001e84  mov     dword ptr [rbp+0CA0h+var_A50], r13d
0x140001e8b  mov     dword ptr [rbp+0CA0h+var_A50+4], 5
0x140001e95  movups  xmm0, xmmword ptr [rbx]
0x140001e98  movups  [rbp+0CA0h+var_A50+8], xmm0
0x140001e9f  movsd   xmm1, qword ptr [rbx+10h]
0x140001ea4  movsd   [rbp+0CA0h+var_A38], xmm1
0x140001eac  movups  xmm0, xmmword ptr [rbx+18h]
0x140001eb0  movaps  [rbp+0CA0h+var_A30], xmm0
0x140001eb7  movsd   xmm1, qword ptr [rbx+28h]
0x140001ebc  mov     [rbp+0CA0h+pHints.ai_canonname], rax
0x140001ec0  lea     rax, [rbp+0CA0h+buf]
0x140001ec7  mov     [rbp+0CA0h+var_CE0], rax
0x140001ecb  lea     rax, [rbp+0CA0h+buf]
0x140001ed2  mov     [rbp+0CA0h+var_CF8], rcx
0x140001ed6  lea     rcx, [rbp+0CA0h+var_D00]
0x140001eda  mov     [rbp+0CA0h+var_CE8], rax
0x140001ede  movsd   [rbp+0CA0h+var_A20], xmm1
0x140001ee6  mov     [rsp+0DA0h+pHints.ai_flags], 186A5h
0x140001eee  mov     qword ptr [rsp+0DA0h+pHints.ai_family], 1
0x140001ef7  mov     [rbp+0CA0h+pHints.ai_addrlen], r14
0x140001efb  mov     [rbp+0CA0h+var_D00], r14d
0x140001eff  mov     [rbp+0CA0h+var_CD8], esi
0x140001f02  call    xdr_callmsg
0x140001f07  test    eax, eax
0x140001f09  jz      short loc_140001F74
0x140001f0b  lea     rdx, [rsp+0DA0h+pHints]
0x140001f10  lea     rcx, [rbp+0CA0h+var_D00]
0x140001f14  call    xdr_rmtcall_args
0x140001f19  test    eax, eax
0x140001f1b  jz      short loc_140001F74
0x140001f1d  mov     rax, [rbp+0CA0h+var_CF8]
0x140001f21  lea     rcx, [rbp+0CA0h+var_D00]
0x140001f25  mov     rax, [rax+20h]
0x140001f29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001f2e  mov     esi, eax
0x140001f30  jmp     short loc_140001F77
0x140001f32  mov     r10, cs:WPP_GLOBAL_Control
0x140001f39  lea     rdi, WPP_GLOBAL_Control
0x140001f40  cmp     r10, rdi
0x140001f43  jz      loc_14000221E
0x140001f49  test    [r10+1Ch], r13b
0x140001f4d  jz      loc_14000221E
0x140001f53  mov     rcx, [r10+10h]
0x140001f57  lea     r9, [rbp+0CA0h+var_970]
0x140001f5e  mov     edx, 0Bh
0x140001f63  lea     r8, WPP_85ad4d236ab33e750ff5ff1970e92ee3_Traceguids
0x140001f6a  call    WPP_SF_s
0x140001f6f  jmp     loc_140002217
0x140001f74  mov     esi, r14d
0x140001f77  mov     rax, [rbp+0CA0h+var_CF8]
0x140001f7b  mov     dword ptr [rsp+0DA0h+var_D50], esi
0x140001f7f  mov     rax, [rax+38h]
0x140001f83  test    rax, rax
0x140001f86  jz      short loc_140001F91
0x140001f88  lea     rcx, [rbp+0CA0h+var_D00]
0x140001f8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001f91  mov     rax, [rbx+38h]
0x140001f95  mov     rcx, rbx
0x140001f98  mov     rax, [rax+20h]
0x140001f9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001fa1  jmp     short loc_140001FA6
0x140001fa3  xor     r14d, r14d
0x140001fa6  mov     r13d, r14d
0x140001fa9  mov     ebx, r14d
0x140001fac  test    edi, edi
0x140001fae  jz      short loc_140001FED
0x140001fb0  lea     rax, [rbp+0CA0h+to]
0x140001fb4  mov     ecx, ebx
0x140001fb6  mov     [rsp+0DA0h+tolen], 10h; tolen
0x140001fbe  lea     rdx, [rbp+0CA0h+buf]; buf
0x140001fc5  xor     r9d, r9d; flags
0x140001fc8  mov     qword ptr [rsp+0DA0h+optlen], rax; to
0x140001fcd  mov     r8d, esi; len
0x140001fd0  mov     rcx, [rbp+rcx*8+0CA0h+s]; s
0x140001fd8  call    cs:__imp_sendto
0x140001fde  cmp     eax, 0FFFFFFFFh
0x140001fe1  jz      loc_140002210
0x140001fe7  inc     ebx
0x140001fe9  cmp     ebx, edi
0x140001feb  jb      short loc_140001FB0
0x140001fed  mov     ecx, r14d
0x140001ff0  mov     r8d, r14d
0x140001ff3  mov     [rbp+0CA0h+readfds.fd_count], ecx
0x140001ff6  test    edi, edi
0x140001ff8  jz      short loc_140002046
0x140001ffa  mov     edx, r14d
0x140001ffd  test    ecx, ecx
0x140001fff  jz      short loc_14000201B
0x140002001  mov     eax, r8d
0x140002004  mov     r9, [rbp+rax*8+0CA0h+s]
0x14000200c  mov     eax, edx
0x14000200e  cmp     [rbp+rax*8+0CA0h+readfds.fd_array], r9
0x140002013  jz      short loc_14000201B
0x140002015  inc     edx
0x140002017  cmp     edx, ecx
0x140002019  jb      short loc_14000200C
0x14000201b  cmp     edx, ecx
0x14000201d  jnz     short loc_14000203E
0x14000201f  cmp     ecx, 40h ; '@'
0x140002022  jnb     short loc_14000203E
0x140002024  mov     ecx, edx
0x140002026  mov     eax, r8d
0x140002029  mov     rax, [rbp+rax*8+0CA0h+s]
0x140002031  mov     [rbp+rcx*8+0CA0h+readfds.fd_array], rax
0x140002036  mov     ecx, [rbp+0CA0h+readfds.fd_count]
0x140002039  inc     ecx
0x14000203b  mov     [rbp+0CA0h+readfds.fd_count], ecx
0x14000203e  inc     r8d
0x140002041  cmp     r8d, edi
0x140002044  jb      short loc_140001FFA
0x140002046  lea     rax, [rsp+0DA0h+timeout]
0x14000204b  xor     r9d, r9d; exceptfds
0x14000204e  xor     r8d, r8d; writefds
0x140002051  mov     qword ptr [rsp+0DA0h+optlen], rax; timeout
  ... truncated ...
```
