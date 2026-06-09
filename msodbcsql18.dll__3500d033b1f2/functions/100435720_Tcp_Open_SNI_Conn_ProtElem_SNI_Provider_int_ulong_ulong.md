# Tcp::Open(SNI_Conn *,ProtElem *,SNI_Provider * *,int,ulong,ulong)

- ea: `0x100435720`
- end: `0x1004360b1`
- name: `?Open@Tcp@@SAKPEAVSNI_Conn@@PEAVProtElem@@PEAPEAVSNI_Provider@@HKK@Z`
- size: `2449`
- prototype: `unsigned int __usercall@<eax>(struct SNI_Conn *@<rcx>, struct ProtElem *@<rdx>, struct SNI_Provider **@<r8>, int@<r9d>, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callers

- `0x100417890`

## callees

- `0x100430ffc`
- `0x100431044`
- `0x100431ec4`
- `0x100435720`
- `0x1004361b0`
- `0x100436438`
- `0x100436600`
- `0x1004367d4`
- `0x100436dc0`
- `0x10043a7c4`
- `0x10043a930`
- `0x10043ae8c`
- `0x10043b1c4`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`
- `0x100546af8`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x1004357bb`
- `KERNEL32!GetTickCount` at `0x100435aff`
- `KERNEL32!GetTickCount` at `0x100435c48`
- `KERNEL32!GetTickCount` at `0x1004357bb`
- `KERNEL32!GetTickCount` at `0x100435aff`
- `KERNEL32!GetTickCount` at `0x100435c48`
- `WS2_32!__imp_closesocket` at `0x100435999`
- `WS2_32!__imp_closesocket` at `0x100435999`
- `WS2_32!__imp_getpeername` at `0x100435dd0`
- `WS2_32!__imp_getpeername` at `0x100435dd0`
- `WS2_32!__imp_getsockname` at `0x100435e8c`
- `WS2_32!__imp_getsockname` at `0x100435e8c`
- `WS2_32!__imp_ioctlsocket` at `0x100435fbe`
- `WS2_32!__imp_ioctlsocket` at `0x100435fbe`
- `WS2_32!__imp_setsockopt` at `0x100435d28`
- `WS2_32!__imp_setsockopt` at `0x100435d28`
- `WS2_32!__imp_shutdown` at `0x10043598f`
- `WS2_32!__imp_shutdown` at `0x10043598f`
- `WS2_32!__imp_WSAGetLastError` at `0x100435d33`
- `WS2_32!__imp_WSAGetLastError` at `0x100435dda`
- `WS2_32!__imp_WSAGetLastError` at `0x100435e96`
- `WS2_32!__imp_WSAGetLastError` at `0x100435fc9`
- `WS2_32!__imp_WSAGetLastError` at `0x100435d33`
- `WS2_32!__imp_WSAGetLastError` at `0x100435dda`
- `WS2_32!__imp_WSAGetLastError` at `0x100435e96`
- `WS2_32!__imp_WSAGetLastError` at `0x100435fc9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Tcp::Open(
        struct SNI_Conn *a1,
        struct ProtElem *a2,
        struct SNI_Provider **a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6)
{
  struct SNI_Provider **v7; // r12
  unsigned int v10; // ebx
  Tcp *v11; // rax
  Tcp *v12; // r15
  unsigned int Error; // edi
  wchar_t *v14; // r8
  __int64 v15; // rdx
  unsigned int CachedAddrInfo; // eax
  unsigned int v17; // r14d
  wchar_t *v18; // r8
  __int64 v19; // rdx
  __int64 v20; // rdx
  SOCKET v21; // rcx
  unsigned int v23; // r12d
  char v24; // r8
  unsigned int v25; // edx
  struct addrinfoW *i; // rcx
  bool v27; // al
  signed int v28; // r12d
  unsigned int v29; // edx
  int *v30; // rcx
  struct addrinfoW *v31; // r13
  int v32; // eax
  unsigned int v33; // r14d
  signed int v34; // ecx
  SOCKET v35; // rcx
  unsigned int v36; // r14d
  bool v37; // [rsp+30h] [rbp-D0h]
  char optval[4]; // [rsp+34h] [rbp-CCh] BYREF
  struct SNI_Provider **v39; // [rsp+38h] [rbp-C8h]
  unsigned int v40; // [rsp+40h] [rbp-C0h]
  struct DNSCacheEntry *v41; // [rsp+48h] [rbp-B8h] BYREF
  signed int v42; // [rsp+50h] [rbp-B0h]
  unsigned int TickCount; // [rsp+54h] [rbp-ACh]
  int v44; // [rsp+58h] [rbp-A8h] BYREF
  int v45; // [rsp+5Ch] [rbp-A4h]
  u_long argp; // [rsp+60h] [rbp-A0h] BYREF
  int *v47; // [rsp+68h] [rbp-98h]
  __int64 v48; // [rsp+70h] [rbp-90h] BYREF
  struct SNI_Conn *v49; // [rsp+78h] [rbp-88h]
  struct addrinfoW v50; // [rsp+80h] [rbp-80h] BYREF
  __int64 v51; // [rsp+B0h] [rbp-50h]
  struct sockaddr name; // [rsp+C0h] [rbp-40h] BYREF
  struct sockaddr v53; // [rsp+140h] [rbp+40h] BYREF

  v51 = -2;
  v40 = a4;
  v7 = a3;
  v39 = a3;
  v49 = a1;
  v48 = -1;
  v10 = 0;
  if ( (bidGblFlags & 0x20004) == 0x20004 && off_1005E7D40[0] )
    bidScopeEnterW(&v48, off_1005E7D40[0], a1);
  v41 = 0;
  TickCount = GetTickCount();
  v42 = a4;
  v11 = (Tcp *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)gpmo + 88LL))(gpmo, 352);
  v12 = v11;
  v47 = (int *)v11;
  if ( v11 )
  {
    Tcp::Tcp(v11, a1);
    *(_QWORD *)v12 = &TcpWSA::`vftable';
  }
  else
  {
    v12 = 0;
  }
  if ( !v12 )
  {
    Error = 14;
    if ( (bidGblFlags & 2) == 0 || !off_1005E5900[0] )
      goto LABEL_12;
    SniErrorIdFromStringId(0xC3B4u);
    v14 = off_1005E5900[0];
    v15 = 2914304;
LABEL_11:
    bidTraceW(0, v15, v14, 7);
LABEL_12:
    SNISetLastError(7, Error, 50100);
    goto LABEL_27;
  }
  Error = (*(__int64 (__fastcall **)(Tcp *))(*(_QWORD *)v12 + 64LL))(v12);
  if ( Error )
  {
    if ( (bidGblFlags & 2) == 0 || !off_1005E5908[0] )
      goto LABEL_12;
    SniErrorIdFromStringId(0xC3B4u);
    v14 = off_1005E5908[0];
    v15 = 2922496;
    goto LABEL_11;
  }
  memset(&v50, 0, sizeof(v50));
  v50.ai_socktype = 1;
  CachedAddrInfo = GetCachedAddrInfo((const unsigned __int16 *)a2 + 4, (const unsigned __int16 *)a2 + 772, &v50, &v41);
  Error = CachedAddrInfo;
  if ( CachedAddrInfo )
  {
    if ( CachedAddrInfo != 11001
      || (v50.ai_flags |= 4u,
          (Error = GetCachedAddrInfo((const unsigned __int16 *)a2 + 4, (const unsigned __int16 *)a2 + 772, &v50, &v41)) != 0) )
    {
      v17 = 50100;
      if ( (bidGblFlags & 2) == 0 || !off_1005E5910[0] )
        goto LABEL_24;
      SniErrorIdFromStringId(0xC3B4u);
      v18 = off_1005E5910[0];
      v19 = 2947072;
      goto LABEL_23;
    }
  }
  v23 = -1;
  if ( *((_BYTE *)a2 + 2056) )
    goto LABEL_83;
  v24 = *((_BYTE *)a2 + 2057);
  if ( v24 != 1 )
  {
    v27 = 0;
    v37 = 0;
    if ( v24 != 2 )
      goto LABEL_46;
LABEL_83:
    Error = Tcp::ParallelOpen(v12, *(struct addrinfoW **)v41, a4, TickCount, a2);
    if ( !Error )
      goto LABEL_74;
    goto LABEL_26;
  }
  v25 = 0;
  for ( i = *(struct addrinfoW **)v41; i; i = i->ai_next )
  {
    if ( i->ai_family == 2 || i->ai_family == 23 )
      ++v25;
  }
  v27 = v25 > 0x40;
  v37 = v25 > 0x40;
LABEL_46:
  v44 = 2;
  v45 = 23;
  if ( *((_DWORD *)a2 + 516) == 1 )
  {
    v44 = 23;
    v45 = 2;
  }
  if ( v24 == 1 && v27 )
    v28 = *((_DWORD *)a2 + 515);
  else
    v28 = v40;
  v29 = 0;
  *(_DWORD *)optval = 0;
  v30 = &v44;
  v47 = &v44;
  while ( 1 )
  {
    v31 = *(struct addrinfoW **)v41;
    if ( *(_QWORD *)v41 )
      break;
LABEL_72:
    *(_DWORD *)optval = ++v29;
    v47 = ++v30;
    if ( v29 >= 2 )
      goto LABEL_73;
  }
  v32 = *v30;
  v40 = *v30;
  while ( v31->ai_family != v32 && *((_DWORD *)a2 + 516) )
  {
LABEL_70:
    v31 = v31->ai_next;
    if ( !v31 )
    {
      v30 = v47;
      v29 = *(_DWORD *)optval;
      goto LABEL_72;
    }
  }
  if ( v28 == -1 )
  {
    v33 = TickCount - 1;
    v34 = v42;
  }
  else
  {
    v33 = v28 + TickCount;
    v34 = v33 - GetTickCount();
    v42 = v34;
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E5918[0] )
    {
      bidTraceW(0, 3010560, off_1005E5918[0], (unsigned int)v34);
      v34 = v42;
    }
    if ( v34 <= 0 || v34 > v28 )
    {
      v23 = -1;
      if ( !Error )
        Error = 258;
      goto LABEL_74;
    }
  }
  Error = Tcp::SocketOpenSync(v12, v31, v34, a2);
  if ( Error )
  {
    if ( *((_BYTE *)a2 + 2057) == 1 && !v37 )
      goto LABEL_73;
    v32 = v40;
    goto LABEL_70;
  }
  if ( v28 != -1 )
  {
    v36 = v33 - GetTickCount();
    if ( (bidGblFlags & 0x20002) == 0x20002 )
    {
      if ( off_1005E5920[0] )
        bidTraceW(0, 3038208, off_1005E5920[0], v36);
    }
  }
LABEL_73:
  v23 = -1;
LABEL_74:
  FreeCachedAddrInfo(v41);
  v41 = 0;
  v35 = *((_QWORD *)v12 + 8);
  if ( v35 != -1 )
  {
    *(_DWORD *)optval = 1;
    if ( setsockopt(v35, 6, 1, optval, 4) == -1 )
    {
      Error = WSAGetLastError();
      v17 = 50100;
      if ( (bidGblFlags & 2) == 0 || !off_1005E5938[0] )
        goto LABEL_24;
      SniErrorIdFromStringId(0xC3B4u);
      v18 = off_1005E5938[0];
      v19 = 3094528;
    }
    else
    {
      Error = Tcp::SetKeepAliveOption(v12, a5, a6);
      if ( Error )
        goto LABEL_26;
      Error = (*(__int64 (__fastcall **)(Tcp *))(*(_QWORD *)v12 + 184LL))(v12);
      if ( Error )
        goto LABEL_26;
      *(_DWORD *)optval = 128;
      if ( getpeername(*((_QWORD *)v12 + 8), &name, (int *)optval) )
      {
        Error = WSAGetLastError();
        v17 = 50100;
        if ( (bidGblFlags & 2) == 0 || !off_1005E5940[0] )
          goto LABEL_24;
        SniErrorIdFromStringId(0xC3B4u);
        v18 = off_1005E5940[0];
        v19 = 3122176;
      }
      else
      {
        Error = Tcp::SetPeerAddrInfo(v12, &name, *(int *)optval);
        if ( Error )
        {
          v17 = 50100;
          if ( (bidGblFlags & 2) == 0 || !off_1005E5948[0] )
            goto LABEL_24;
          SniErrorIdFromStringId(0xC3B4u);
          v18 = off_1005E5948[0];
          v19 = 3129344;
        }
        else
        {
          *(_DWORD *)optval = 128;
          if ( getsockname(*((_QWORD *)v12 + 8), &v53, (int *)optval) )
          {
            Error = WSAGetLastError();
            v17 = 50100;
            if ( (bidGblFlags & 2) == 0 || !off_1005E5950[0] )
              goto LABEL_24;
            SniErrorIdFromStringId(0xC3B4u);
            v18 = off_1005E5950[0];
            v19 = 3142656;
          }
          else
          {
            Error = Tcp::SetLocalAddrInfo(v12, &v53, *(int *)optval);
            if ( Error )
            {
              v17 = 50100;
              if ( (bidGblFlags & 2) == 0 || !off_1005E5958[0] )
                goto LABEL_24;
              SniErrorIdFromStringId(0xC3B4u);
              v18 = off_1005E5958[0];
              v19 = 3149824;
            }
            else
            {
              *((_QWORD *)v12 + 2) = *((_QWORD *)v12 + 8);
              Error = SNI::detail::Transport::DWSetSkipCompletionPortOnSuccess(v12);
              if ( Error )
              {
                v17 = 50100;
                if ( (bidGblFlags & 2) == 0 || !off_1005E5960[0] )
                  goto LABEL_24;
                SniErrorIdFromStringId(0xC3B4u);
                v18 = off_1005E5960[0];
                v19 = 3162112;
              }
              else
              {
                if ( SNI::detail::Transport::FWillSkipCompletionPortOnSuccess(v12)
                  || (argp = 1, (*((_BYTE *)v49 + 236) & 1) != 0)
                  || ioctlsocket(*((_QWORD *)v12 + 8), -2147195266, &argp) != -1 )
                {
                  *((_DWORD *)v12 + 11) = bidUpdateItemIDA(*((unsigned int *)v12 + 11), off_1005E4298[0], a2);
                  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E5970[0] )
                    bidTraceW(0, 3189760, off_1005E5970[0], *((unsigned int *)v12 + 11));
                  *v39 = v12;
                  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E5978[0] )
                    bidTraceW(0, 3201024, off_1005E5978[0], 0);
                  goto LABEL_35;
                }
                Error = WSAGetLastError();
                v17 = 50100;
                if ( (bidGblFlags & 2) == 0 || !off_1005E5968[0] )
                {
LABEL_24:
                  v20 = Error;
                  goto LABEL_25;
                }
                SniErrorIdFromStringId(0xC3B4u);
                v18 = off_1005E5968[0];
                v19 = 3176448;
              }
            }
          }
        }
      }
    }
LABEL_23:
    bidTraceW(0, v19, v18, 7);
    goto LABEL_24;
  }
  if ( Error )
  {
    v17 = 50100;
    if ( (bidGblFlags & 2) != 0 && off_1005E5930[0] )
    {
      SniErrorIdFromStringId(0xC3B4u);
      bidTraceW(0, 3080192, off_1005E5930[0], 7);
    }
    v23 = Error;
  }
  else
  {
    Error = -1;
    v17 = 50117;
    if ( (bidGblFlags & 2) != 0 && off_1005E5928[0] )
    {
      SniErrorIdFromStringId(0xC3C5u);
      bidTraceW(0, 3076096, off_1005E5928[0], 7);
    }
  }
  v20 = v23;
LABEL_25:
  SNISetLastError(7, v20, v17);
LABEL_26:
  v7 = v39;
LABEL_27:
  FreeCachedAddrInfo(v41);
  if ( v12 )
  {
    v21 = *((_QWORD *)v12 + 8);
    if ( v21 != -1 )
    {
      shutdown(v21, 1);
      closesocket(*((_QWORD *)v12 + 8));
    }
    (**(void (__fastcall ***)(Tcp *, __int64))v12)(v12, 1);
  }
  *v7 = 0;
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E5980[0] )
    bidTraceW(0, 3228672, off_1005E5980[0], Error);
  v10 = Error;
LABEL_35:
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v48);
  return v10;
}

```

## disassembly

```asm
0x100435720  push    rbp
0x100435722  push    rbx
0x100435723  push    rsi
0x100435724  push    rdi
0x100435725  push    r12
0x100435727  push    r13
0x100435729  push    r14
0x10043572b  push    r15
0x10043572d  lea     rbp, [rsp-0D8h]
0x100435735  sub     rsp, 1D8h
0x10043573c  mov     [rbp+110h+var_160], 0FFFFFFFFFFFFFFFEh
0x100435744  mov     rax, cs:__security_cookie
0x10043574b  xor     rax, rsp
0x10043574e  mov     [rbp+110h+var_50], rax
0x100435755  mov     r13d, r9d
0x100435758  mov     [rsp+210h+var_1D0], r9d
0x10043575d  mov     r12, r8
0x100435760  mov     [rsp+210h+var_1D8], r8
0x100435765  mov     rsi, rdx
0x100435768  mov     rdi, rcx
0x10043576b  mov     [rsp+210h+var_198], rcx
0x100435770  or      [rsp+210h+var_1A0], 0FFFFFFFFFFFFFFFFh
0x100435776  mov     eax, cs:_bidGblFlags
0x10043577c  mov     ecx, 20004h
0x100435781  and     eax, ecx
0x100435783  xor     ebx, ebx
0x100435785  cmp     eax, ecx
0x100435787  jnz     short loc_1004357B6
0x100435789  mov     rax, cs:off_1005E7D40; "<Tcp::Open|API|SNI> pConn: %p{SNI_Conn*"...
0x100435790  test    rax, rax
0x100435793  jz      short loc_1004357B6
0x100435795  mov     [rsp+210h+var_1E8], r9d
0x10043579a  mov     qword ptr [rsp+210h+optlen], r8
0x10043579f  mov     r9, rdx
0x1004357a2  mov     r8, rdi
0x1004357a5  mov     rdx, cs:off_1005E7D40; "<Tcp::Open|API|SNI> pConn: %p{SNI_Conn*"...
0x1004357ac  lea     rcx, [rsp+210h+var_1A0]
0x1004357b1  call    _bidScopeEnterW
0x1004357b6  mov     [rsp+210h+var_1C8], rbx
0x1004357bb  call    cs:__imp_GetTickCount
0x1004357c1  mov     [rsp+210h+var_1BC], eax
0x1004357c5  mov     [rsp+210h+var_1C0], r13d
0x1004357ca  mov     rcx, cs:?gpmo@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * gpmo
0x1004357d1  mov     rax, [rcx]
0x1004357d4  mov     edx, 160h
0x1004357d9  mov     rax, [rax+58h]
0x1004357dd  call    cs:__guard_dispatch_icall_fptr
0x1004357e3  mov     r15, rax
0x1004357e6  mov     [rsp+210h+var_1A8], rax
0x1004357eb  test    rax, rax
0x1004357ee  jz      short loc_100435807
0x1004357f0  mov     rdx, rdi; struct SNI_Conn *
0x1004357f3  mov     rcx, rax; this
0x1004357f6  call    ??0Tcp@@QEAA@PEAVSNI_Conn@@@Z; Tcp::Tcp(SNI_Conn *)
0x1004357fb  lea     rax, ??_7TcpWSA@@6B@; const TcpWSA::`vftable'
0x100435802  mov     [r15], rax
0x100435805  jmp     short loc_10043580A
0x100435807  mov     r15, rbx
0x10043580a  test    r15, r15
0x10043580d  jnz     short loc_100435868
0x10043580f  lea     edi, [r15+0Eh]
0x100435813  lea     esi, [rdi-7]
0x100435816  mov     r14d, 0C3B4h
0x10043581c  test    byte ptr cs:_bidGblFlags, 2
0x100435823  jz      short loc_100435857
0x100435825  mov     rax, cs:off_1005E5900; "<Tcp::Open|ERR|SNI> ProviderNum: %d{Pro"...
0x10043582c  test    rax, rax
0x10043582f  jz      short loc_100435857
0x100435831  mov     ecx, r14d; unsigned int
0x100435834  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100435839  mov     r8, cs:off_1005E5900; "<Tcp::Open|ERR|SNI> ProviderNum: %d{Pro"...
0x100435840  mov     edx, 2C7800h
0x100435845  mov     [rsp+210h+var_1E8], edi
0x100435849  mov     r9d, esi
0x10043584c  mov     [rsp+210h+optlen], eax
0x100435850  xor     ecx, ecx
0x100435852  call    _bidTraceW
0x100435857  mov     r8d, r14d
0x10043585a  mov     edx, edi
0x10043585c  mov     ecx, esi
0x10043585e  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100435863  jmp     loc_100435971
0x100435868  mov     rax, [r15]
0x10043586b  mov     rcx, r15
0x10043586e  mov     rax, [rax+40h]
0x100435872  call    cs:__guard_dispatch_icall_fptr
0x100435878  mov     edi, eax
0x10043587a  test    eax, eax
0x10043587c  jz      short loc_1004358B4
0x10043587e  mov     esi, 7
0x100435883  mov     r14d, 0C3B4h
0x100435889  test    byte ptr cs:_bidGblFlags, 2
0x100435890  jz      short loc_100435857
0x100435892  mov     rax, cs:off_1005E5908; "<Tcp::Open|ERR|SNI> ProviderNum: %d{Pro"...
0x100435899  test    rax, rax
0x10043589c  jz      short loc_100435857
0x10043589e  mov     ecx, r14d; unsigned int
0x1004358a1  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x1004358a6  mov     r8, cs:off_1005E5908; "<Tcp::Open|ERR|SNI> ProviderNum: %d{Pro"...
0x1004358ad  mov     edx, 2C9800h
0x1004358b2  jmp     short loc_100435845
0x1004358b4  xorps   xmm0, xmm0
0x1004358b7  movups  xmmword ptr [rbp+110h+var_190.ai_flags], xmm0
0x1004358bb  movups  xmmword ptr [rbp+110h+var_190.ai_addrlen], xmm0
0x1004358bf  movups  xmmword ptr [rbp+110h+var_190.ai_addr], xmm0
0x1004358c3  mov     [rbp+110h+var_190.ai_socktype], 1
0x1004358ca  lea     r14, [rsi+608h]
0x1004358d1  lea     r9, [rsp+210h+var_1C8]; struct DNSCacheEntry **
0x1004358d6  lea     r8, [rbp+110h+var_190]; struct addrinfoW *
0x1004358da  mov     rdx, r14; unsigned __int16 *
0x1004358dd  lea     rcx, [rsi+8]; unsigned __int16 *
0x1004358e1  call    ?GetCachedAddrInfo@@YAKPEBG0PEBUaddrinfoW@@PEAPEAUDNSCacheEntry@@@Z; GetCachedAddrInfo(ushort const *,ushort const *,addrinfoW const *,DNSCacheEntry * *)
0x1004358e6  mov     edi, eax
0x1004358e8  test    eax, eax
0x1004358ea  jz      loc_100435A1B
0x1004358f0  cmp     eax, 2AF9h
0x1004358f5  jnz     short loc_10043591A
0x1004358f7  or      [rbp+110h+var_190.ai_flags], 4
0x1004358fb  lea     r9, [rsp+210h+var_1C8]; struct DNSCacheEntry **
0x100435900  lea     r8, [rbp+110h+var_190]; struct addrinfoW *
0x100435904  mov     rdx, r14; unsigned __int16 *
0x100435907  lea     rcx, [rsi+8]; unsigned __int16 *
0x10043590b  call    ?GetCachedAddrInfo@@YAKPEBG0PEBUaddrinfoW@@PEAPEAUDNSCacheEntry@@@Z; GetCachedAddrInfo(ushort const *,ushort const *,addrinfoW const *,DNSCacheEntry * *)
0x100435910  mov     edi, eax
0x100435912  test    eax, eax
0x100435914  jz      loc_100435A1B
0x10043591a  mov     esi, 7
0x10043591f  mov     r14d, 0C3B4h
0x100435925  test    byte ptr cs:_bidGblFlags, 2
0x10043592c  jz      short loc_100435960
0x10043592e  mov     rax, cs:off_1005E5910; "<Tcp::Open|ERR|SNI> ProviderNum: %d{Pro"...
0x100435935  test    rax, rax
0x100435938  jz      short loc_100435960
0x10043593a  mov     ecx, r14d; unsigned int
0x10043593d  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100435942  mov     r8, cs:off_1005E5910; "<Tcp::Open|ERR|SNI> ProviderNum: %d{Pro"...
0x100435949  mov     edx, 2CF800h
0x10043594e  mov     [rsp+210h+var_1E8], edi
0x100435952  mov     r9d, esi
0x100435955  mov     [rsp+210h+optlen], eax
0x100435959  xor     ecx, ecx
0x10043595b  call    _bidTraceW
0x100435960  mov     edx, edi
0x100435962  mov     r8d, r14d
0x100435965  mov     ecx, esi
0x100435967  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x10043596c  mov     r12, [rsp+210h+var_1D8]
0x100435971  mov     rcx, [rsp+210h+var_1C8]; struct DNSCacheEntry *
0x100435976  call    ?FreeCachedAddrInfo@@YAXPEAUDNSCacheEntry@@@Z; FreeCachedAddrInfo(DNSCacheEntry *)
0x10043597b  test    r15, r15
0x10043597e  jz      short loc_1004359B3
0x100435980  mov     rcx, [r15+40h]; s
0x100435984  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x100435988  jz      short loc_10043599F
0x10043598a  mov     edx, 1; how
0x10043598f  call    cs:__imp_shutdown
0x100435995  mov     rcx, [r15+40h]; s
0x100435999  call    cs:__imp_closesocket
0x10043599f  mov     rax, [r15]
0x1004359a2  mov     edx, 1
0x1004359a7  mov     rcx, r15
0x1004359aa  mov     rax, [rax]
0x1004359ad  call    cs:__guard_dispatch_icall_fptr
0x1004359b3  mov     [r12], rbx
0x1004359b7  mov     eax, cs:_bidGblFlags
0x1004359bd  mov     ecx, 20002h
0x1004359c2  and     eax, ecx
0x1004359c4  cmp     eax, ecx
0x1004359c6  jnz     short loc_1004359EA
0x1004359c8  mov     rax, cs:off_1005E5980; "<Tcp::Open|RET|SNI> %d{WINERR}\n"
0x1004359cf  test    rax, rax
0x1004359d2  jz      short loc_1004359EA
0x1004359d4  mov     r9d, edi
0x1004359d7  mov     r8, cs:off_1005E5980; "<Tcp::Open|RET|SNI> %d{WINERR}\n"
0x1004359de  mov     edx, 314400h
0x1004359e3  xor     ecx, ecx
0x1004359e5  call    _bidTraceW
0x1004359ea  mov     ebx, edi
0x1004359ec  lea     rcx, [rsp+210h+var_1A0]; this
0x1004359f1  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x1004359f6  mov     eax, ebx
0x1004359f8  mov     rcx, [rbp+110h+var_50]
0x1004359ff  xor     rcx, rsp; StackCookie
0x100435a02  call    __security_check_cookie
0x100435a07  add     rsp, 1D8h
0x100435a0e  pop     r15
0x100435a10  pop     r14
0x100435a12  pop     r13
0x100435a14  pop     r12
0x100435a16  pop     rdi
0x100435a17  pop     rsi
0x100435a18  pop     rbx
0x100435a19  pop     rbp
0x100435a1a  retn
0x100435a1b  or      r12d, 0FFFFFFFFh
0x100435a1f  cmp     [rsi+808h], bl
0x100435a25  jnz     loc_100435C92
0x100435a2b  mov     r8b, [rsi+809h]
0x100435a32  mov     r9d, 17h
0x100435a38  cmp     r8b, 1
0x100435a3c  jnz     short loc_100435A6D
0x100435a3e  mov     edx, ebx
0x100435a40  mov     rax, [rsp+210h+var_1C8]
0x100435a45  mov     rcx, [rax]
0x100435a48  jmp     short loc_100435A5C
0x100435a4a  cmp     dword ptr [rcx+4], 2
0x100435a4e  jz      short loc_100435A56
0x100435a50  cmp     [rcx+4], r9d
0x100435a54  jnz     short loc_100435A58
0x100435a56  inc     edx
0x100435a58  mov     rcx, [rcx+28h]
0x100435a5c  test    rcx, rcx
0x100435a5f  jnz     short loc_100435A4A
0x100435a61  cmp     edx, 40h ; '@'
0x100435a64  setnbe  al
0x100435a67  mov     [rsp+210h+var_1E0], al
0x100435a6b  jmp     short loc_100435A7D
0x100435a6d  mov     al, bl
0x100435a6f  mov     [rsp+210h+var_1E0], bl
0x100435a73  cmp     r8b, 2
0x100435a77  jz      loc_100435C92
0x100435a7d  mov     [rsp+210h+var_1B8], 2
0x100435a85  mov     [rsp+210h+var_1B4], r9d
0x100435a8a  cmp     dword ptr [rsi+810h], 1
0x100435a91  jnz     short loc_100435AA0
0x100435a93  mov     [rsp+210h+var_1B8], r9d
0x100435a98  mov     [rsp+210h+var_1B4], 2
0x100435aa0  cmp     r8b, 1
0x100435aa4  jnz     short loc_100435AB3
0x100435aa6  test    al, al
0x100435aa8  jz      short loc_100435AB3
0x100435aaa  mov     r12d, [rsi+80Ch]
0x100435ab1  jmp     short loc_100435AB8
0x100435ab3  mov     r12d, [rsp+210h+var_1D0]
0x100435ab8  mov     edx, ebx
0x100435aba  mov     dword ptr [rsp+210h+optval], ebx
0x100435abe  lea     rcx, [rsp+210h+var_1B8]
0x100435ac3  mov     [rsp+210h+var_1A8], rcx
0x100435ac8  mov     rax, [rsp+210h+var_1C8]
0x100435acd  mov     r13, [rax]
0x100435ad0  test    r13, r13
0x100435ad3  jz      loc_100435BA8
0x100435ad9  mov     eax, [rcx]
0x100435adb  mov     [rsp+210h+var_1D0], eax
0x100435adf  cmp     [r13+4], eax
0x100435ae3  jz      short loc_100435AF1
0x100435ae5  cmp     [rsi+810h], ebx
0x100435aeb  jnz     loc_100435B92
0x100435af1  mov     r14d, [rsp+210h+var_1BC]
0x100435af6  cmp     r12d, 0FFFFFFFFh
0x100435afa  jz      short loc_100435B5D
0x100435afc  add     r14d, r12d
0x100435aff  call    cs:__imp_GetTickCount
0x100435b05  mov     ecx, r14d
0x100435b08  sub     ecx, eax
0x100435b0a  mov     [rsp+210h+var_1C0], ecx
0x100435b0e  mov     eax, cs:_bidGblFlags
0x100435b14  mov     edx, 20002h
0x100435b19  and     eax, edx
0x100435b1b  cmp     eax, edx
0x100435b1d  jnz     short loc_100435B45
0x100435b1f  mov     rax, cs:off_1005E5918; "<Tcp::Open|SNI> timeout: %d\n"
0x100435b26  test    rax, rax
0x100435b29  jz      short loc_100435B45
0x100435b2b  mov     r9d, ecx
0x100435b2e  mov     r8, cs:off_1005E5918; "<Tcp::Open|SNI> timeout: %d\n"
0x100435b35  mov     edx, 2DF000h
0x100435b3a  xor     ecx, ecx
0x100435b3c  call    _bidTraceW
0x100435b41  mov     ecx, [rsp+210h+var_1C0]
0x100435b45  test    ecx, ecx
0x100435b47  jle     short loc_100435B4E
0x100435b49  cmp     ecx, r12d
0x100435b4c  jle     short loc_100435B64
0x100435b4e  or      r12d, 0FFFFFFFFh
0x100435b52  test    edi, edi
0x100435b54  jnz     short loc_100435BC4
0x100435b56  mov     edi, 102h
0x100435b5b  jmp     short loc_100435BC4
0x100435b5d  dec     r14d
0x100435b60  mov     ecx, [rsp+210h+var_1C0]
0x100435b64  mov     r9, rsi; struct ProtElem *
0x100435b67  mov     r8d, ecx; dwMilliseconds
0x100435b6a  mov     rdx, r13; struct addrinfoW *
0x100435b6d  mov     rcx, r15; this
0x100435b70  call    ?SocketOpenSync@Tcp@@QEAAKPEAUaddrinfoW@@HPEAVProtElem@@@Z; Tcp::SocketOpenSync(addrinfoW *,int,ProtElem *)
0x100435b75  mov     edi, eax
0x100435b77  test    eax, eax
0x100435b79  jz      loc_100435C3E
0x100435b7f  cmp     byte ptr [rsi+809h], 1
0x100435b86  jnz     short loc_100435B8E
0x100435b88  cmp     [rsp+210h+var_1E0], bl
0x100435b8c  jz      short loc_100435BC0
0x100435b8e  mov     eax, [rsp+210h+var_1D0]
0x100435b92  mov     r13, [r13+28h]
0x100435b96  test    r13, r13
0x100435b99  jnz     loc_100435ADF
0x100435b9f  mov     rcx, [rsp+210h+var_1A8]
0x100435ba4  mov     edx, dword ptr [rsp+210h+optval]
0x100435ba8  inc     edx
  ... truncated ...
```
