# Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>::AsioEndpointAddress<boost::asio::ip::udp>(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,ushort,Microsoft::Basix::Dct::SocketTools::AddressFamilyOptions)

- ea: `0x1801765b0`
- end: `0x180176a72`
- name: `??0?$AsioEndpointAddress@Vudp@ip@asio@boost@@@Dct@Basix@Microsoft@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@GW4AddressFamilyOptions@SocketTools@123@@Z`
- size: `1218`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180175f10`
- `0x180178580`

## callees

- `0x180015bb8`
- `0x180017518`
- `0x180024700`
- `0x1800448dc`
- `0x18012de44`
- `0x180145f40`
- `0x180161508`
- `0x180163e0c`
- `0x180165c50`
- `0x18016ea70`
- `0x18016f37c`
- `0x18016f474`
- `0x1801765b0`
- `0x1801a8c3c`
- `0x1802e9b68`
- `0x18032f050`
- `0x18032f0b0`
- `0x180330b40`

## import_xrefs

- `WS2_32!__imp_htonl` at `0x1801766a6`
- `WS2_32!__imp_htonl` at `0x180176968`
- `WS2_32!__imp_htonl` at `0x1801766a6`
- `WS2_32!__imp_htonl` at `0x180176968`
- `WS2_32!__imp_htons` at `0x180176953`
- `WS2_32!__imp_htons` at `0x180176981`
- `WS2_32!__imp_htons` at `0x1801769bb`
- `WS2_32!__imp_htons` at `0x180176953`
- `WS2_32!__imp_htons` at `0x180176981`
- `WS2_32!__imp_htons` at `0x1801769bb`
- `WS2_32!__imp_ntohl` at `0x180176960`
- `WS2_32!__imp_ntohl` at `0x180176960`
- `WS2_32!__imp_ntohs` at `0x180176935`
- `WS2_32!__imp_ntohs` at `0x180176935`
- `WS2_32!__imp_WSACleanup` at `0x1801769d0`
- `WS2_32!__imp_WSACleanup` at `0x1801769d0`

## pseudocode

```c
__int64 __fastcall Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>::AsioEndpointAddress<boost::asio::ip::udp>(
        __int64 a1,
        __int64 a2,
        u_short a3,
        int a4)
{
  int v7; // edi
  int *v8; // rdx
  __int64 v9; // rcx
  u_long v10; // ebx
  int *v11; // rdx
  int v12; // ecx
  int *v13; // rdx
  int v14; // eax
  __m128d v15; // xmm7
  int v16; // r15d
  int v17; // r14d
  int *v18; // r8
  unsigned __int64 v19; // r9
  __int64 v20; // rcx
  const char *v21; // rdx
  int *v22; // rdx
  int v23; // ecx
  int *v24; // rdx
  __int64 v25; // rcx
  int *v26; // rdx
  int v27; // ecx
  __int64 address_v6; // rax
  int *v29; // rdx
  int v30; // eax
  u_long v31; // ebx
  u_short v32; // ax
  __m128d v33; // xmm6
  u_long v34; // eax
  __int64 v36; // rax
  struct boost::system::error_code *v37; // [rsp+28h] [rbp-D8h]
  _BYTE v38[24]; // [rsp+30h] [rbp-D0h] BYREF
  int v39; // [rsp+48h] [rbp-B8h]
  __int64 v40; // [rsp+50h] [rbp-B0h]
  _BYTE v41[40]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE pExceptionObject[128]; // [rsp+80h] [rbp-80h] BYREF
  u_short v43; // [rsp+100h] [rbp+0h] BYREF
  int v44[4]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v45; // [rsp+118h] [rbp+18h]
  unsigned __int64 v46; // [rsp+120h] [rbp+20h]
  char v47[8]; // [rsp+128h] [rbp+28h] BYREF
  unsigned int v48[4]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v49; // [rsp+140h] [rbp+40h]
  _BYTE v50[416]; // [rsp+150h] [rbp+50h] BYREF

  v40 = a1;
  v43 = a3;
  Microsoft::Basix::Dct::EndpointAddress::EndpointAddress((Microsoft::Basix::Dct::EndpointAddress *)a1);
  *(_QWORD *)a1 = &Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>::`vftable';
  v7 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_DWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 8) = 2;
  Microsoft::Basix::WinUtils::WSAStartupObj::WSAStartupObj((Microsoft::Basix::WinUtils::WSAStartupObj *)v50, 0x202u);
  Microsoft::Basix::SplitHostnameAndPort<std::string,unsigned short>(v44, a2, &v43);
  *(_OWORD *)v48 = 0;
  v49 = 0;
  v8 = v44;
  if ( a4 == 1 )
  {
    if ( v46 > 0xF )
      v8 = *(int **)v44;
    if ( v45 != 9 )
      goto LABEL_9;
    v9 = *(_QWORD *)v8 - 0x736F686C61636F6CLL;
    if ( *(_QWORD *)v8 == 0x736F686C61636F6CLL )
      v9 = *((unsigned __int8 *)v8 + 8) - 116LL;
    if ( v9 )
    {
LABEL_9:
      v11 = v44;
      if ( v46 > 0xF )
        v11 = *(int **)v44;
      if ( v45 != 3 )
        goto LABEL_16;
      v12 = *(unsigned __int16 *)v11 - 28257;
      if ( *(_WORD *)v11 == 28257 )
        v12 = *((unsigned __int8 *)v11 + 2) - 121;
      if ( v12 )
      {
LABEL_16:
        v13 = v44;
        if ( v46 > 0xF )
          LODWORD(v13) = v44[0];
        v14 = boost::asio::detail::socket_ops::inet_pton(
                (boost::asio::detail::socket_ops *)2,
                (int)v13,
                v47,
                0,
                v48,
                v37);
        v10 = *(_DWORD *)v47;
        if ( v14 <= 0 )
          v10 = 0;
      }
      else
      {
        v10 = 0;
      }
    }
    else
    {
      v10 = htonl(0x7F000001u);
    }
    v15 = 0;
    v16 = 0;
    v17 = 0;
    goto LABEL_65;
  }
  if ( a4 )
  {
    if ( v46 > 0xF )
      v8 = *(int **)v44;
    if ( v45 != 9 )
      goto LABEL_47;
    v25 = *(_QWORD *)v8 - 0x736F686C61636F6CLL;
    if ( *(_QWORD *)v8 == 0x736F686C61636F6CLL )
      v25 = *((unsigned __int8 *)v8 + 8) - 116LL;
    if ( v25 )
    {
LABEL_47:
      v26 = v44;
      if ( v46 > 0xF )
        v26 = *(int **)v44;
      if ( v45 == 3 )
      {
        v27 = *(unsigned __int16 *)v26 - 28257;
        if ( *(_WORD *)v26 == 28257 )
          v27 = *((unsigned __int8 *)v26 + 2) - 121;
        if ( !v27 )
        {
          v15 = 0;
LABEL_63:
          v17 = 0;
LABEL_64:
          v16 = 1;
          v10 = 0;
          goto LABEL_65;
        }
      }
      address_v6 = boost::asio::ip::make_address_v6(v38, v44, v48);
      v15 = *(__m128d *)address_v6;
      v17 = *(_DWORD *)(address_v6 + 16);
      if ( a4 == 2 )
        goto LABEL_64;
      *(_DWORD *)v38 = 0;
      *(_QWORD *)&v38[8] = 0;
      if ( (unsigned __int8)boost::system::operator==(v48, v38) )
        goto LABEL_64;
      v29 = v44;
      if ( v46 > 0xF )
        LODWORD(v29) = v44[0];
      v30 = boost::asio::detail::socket_ops::inet_pton((boost::asio::detail::socket_ops *)2, (int)v29, v47, 0, v48, v37);
      v31 = *(_DWORD *)v47;
      if ( v30 <= 0 )
        v31 = 0;
      *(_DWORD *)v38 = 0;
      *(_QWORD *)&v38[8] = 0;
      if ( !(unsigned __int8)boost::system::operator==(v48, v38) )
        goto LABEL_64;
      *(_QWORD *)v38 = 0;
      *(_DWORD *)&v38[8] = -65536;
      *(_DWORD *)&v38[12] = v31;
    }
    else
    {
      *(_OWORD *)v38 = 0;
      v38[15] = 1;
    }
    v15 = *(__m128d *)v38;
    goto LABEL_63;
  }
  v18 = *(int **)v44;
  v19 = v46;
  if ( v46 > 0xF )
    v8 = *(int **)v44;
  if ( v45 != 9 )
    goto LABEL_29;
  v20 = *(_QWORD *)v8 - 0x736F686C61636F6CLL;
  if ( *(_QWORD *)v8 == 0x736F686C61636F6CLL )
    v20 = *((unsigned __int8 *)v8 + 8) - 116LL;
  if ( v20 )
  {
LABEL_29:
    v22 = v44;
    if ( v46 > 0xF )
      v22 = *(int **)v44;
    if ( v45 != 3 )
      goto LABEL_37;
    v23 = *(unsigned __int16 *)v22 - 28257;
    if ( *(_WORD *)v22 == 28257 )
      v23 = *((unsigned __int8 *)v22 + 2) - 121;
    if ( v23 )
      goto LABEL_37;
    v21 = "0.0.0.0";
  }
  else
  {
    v21 = "127.0.0.1";
  }
  std::string::assign(v44, v21);
  v18 = *(int **)v44;
  v19 = v46;
LABEL_37:
  v24 = v44;
  if ( v19 > 0xF )
    v24 = v18;
  boost::asio::ip::make_address(v38, v24, v48);
  v16 = *(_DWORD *)v38;
  v10 = *(_DWORD *)&v38[4];
  v15 = *(__m128d *)&v38[8];
  v17 = v39;
LABEL_65:
  *(_DWORD *)v38 = 0;
  *(_QWORD *)&v38[8] = 0;
  if ( !(unsigned __int8)boost::system::operator==(v48, v38) )
  {
    std::string::string(v38, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\asioendpointaddress.h");
    v36 = std::operator+<char>(v41, "Cannot translate IP address: ", a2);
    Microsoft::Basix::Exception::Exception(pExceptionObject, v36, v38, 115);
    throw (Microsoft::Basix::Exception *)pExceptionObject;
  }
  v32 = ntohs(*(_WORD *)(a1 + 10));
  v33 = 0;
  *(_OWORD *)&v38[8] = 0;
  if ( v16 )
  {
    *(_WORD *)v38 = 23;
    *(_WORD *)&v38[2] = htons(v32);
    *(_DWORD *)&v38[4] = 0;
    if ( v16 != 1 )
    {
      boost::asio::ip::bad_address_cast::bad_address_cast((boost::asio::ip::bad_address_cast *)v38);
      boost::throw_exception<boost::asio::ip::bad_address_cast>(v38);
    }
    v33 = v15;
    *(__m128d *)&v38[8] = v15;
    v7 = v17;
  }
  else
  {
    *(_WORD *)v38 = 2;
    *(_WORD *)&v38[2] = htons(v32);
    v34 = ntohl(v10);
    *(_DWORD *)&v38[4] = htonl(v34);
  }
  *(_OWORD *)(a1 + 8) = *(_OWORD *)v38;
  *(_QWORD *)(a1 + 24) = *(_OWORD *)&_mm_unpackhi_pd(v33, v33);
  *(_DWORD *)(a1 + 32) = v7;
  *(_WORD *)(a1 + 10) = htons(v43);
  std::string::_Tidy_deallocate(v44);
  WSACleanup();
  return a1;
}

```

## disassembly

```asm
0x1801765b0  mov     [rsp-8+arg_18], rbx
0x1801765b5  push    rbp
0x1801765b6  push    rsi
0x1801765b7  push    rdi
0x1801765b8  push    r12
0x1801765ba  push    r13
0x1801765bc  push    r14
0x1801765be  push    r15
0x1801765c0  lea     rbp, [rsp-220h]
0x1801765c8  mov     eax, 320h
0x1801765cd  call    _alloca_probe
0x1801765d2  sub     rsp, rax
0x1801765d5  movaps  [rsp+350h+var_40], xmm6
0x1801765dd  movaps  [rsp+350h+var_50], xmm7
0x1801765e5  mov     rax, cs:__security_cookie
0x1801765ec  xor     rax, rsp
0x1801765ef  mov     [rbp+250h+var_60], rax
0x1801765f6  mov     ebx, r9d
0x1801765f9  mov     r12, rdx
0x1801765fc  mov     rsi, rcx
0x1801765ff  mov     [rsp+350h+var_300], rcx
0x180176604  mov     [rbp+250h+var_250], r8w
0x180176609  call    ??0EndpointAddress@Dct@Basix@Microsoft@@QEAA@XZ; Microsoft::Basix::Dct::EndpointAddress::EndpointAddress(void)
0x18017660e  nop
0x18017660f  lea     rax, ??_7?$AsioEndpointAddress@Vudp@ip@asio@boost@@@Dct@Basix@Microsoft@@6B@; const Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>::`vftable'
0x180176616  mov     [rsi], rax
0x180176619  xor     edi, edi
0x18017661b  mov     [rsi+10h], rdi
0x18017661f  mov     [rsi+18h], rdi
0x180176623  mov     [rsi+20h], edi
0x180176626  lea     r13d, [rdi+2]
0x18017662a  mov     [rsi+8], r13
0x18017662e  mov     edx, 202h; unsigned __int16
0x180176633  lea     rcx, [rbp+250h+var_200]; this
0x180176637  call    ??0WSAStartupObj@WinUtils@Basix@Microsoft@@QEAA@G@Z; Microsoft::Basix::WinUtils::WSAStartupObj::WSAStartupObj(ushort)
0x18017663c  nop
0x18017663d  lea     r8, [rbp+250h+var_250]
0x180176641  mov     rdx, r12
0x180176644  lea     rcx, [rbp+250h+var_248]
0x180176648  call    ??$SplitHostnameAndPort@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@G@Basix@Microsoft@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV23@AEAG@Z; Microsoft::Basix::SplitHostnameAndPort<std::string,ushort>(std::string const &,ushort &)
0x18017664d  nop
0x18017664e  xorps   xmm0, xmm0
0x180176651  movups  xmmword ptr [rbp+250h+var_220], xmm0
0x180176655  mov     [rbp+250h+var_210], rdi
0x180176659  lea     rdx, [rbp+250h+var_248]
0x18017665d  cmp     ebx, 1
0x180176660  jnz     loc_180176718
0x180176666  mov     r8, qword ptr [rbp+250h+var_248]
0x18017666a  mov     r9, [rbp+250h+var_230]
0x18017666e  cmp     r9, 0Fh
0x180176672  cmova   rdx, r8
0x180176676  cmp     [rbp+250h+var_238], 9
0x18017667b  jnz     short loc_1801766B0
0x18017667d  mov     rcx, [rdx]
0x180176680  mov     rax, 736F686C61636F6Ch
0x18017668a  sub     rcx, rax
0x18017668d  jnz     short loc_18017669C
0x18017668f  movzx   ecx, byte ptr [rdx+8]
0x180176693  lea     eax, [rdi+74h]
0x180176696  movzx   eax, al
0x180176699  sub     rcx, rax
0x18017669c  test    rcx, rcx
0x18017669f  jnz     short loc_1801766B0
0x1801766a1  mov     ecx, 7F000001h; hostlong
0x1801766a6  call    cs:__imp_htonl
0x1801766ac  mov     ebx, eax
0x1801766ae  jmp     short loc_18017670A
0x1801766b0  lea     rdx, [rbp+250h+var_248]
0x1801766b4  cmp     r9, 0Fh
0x1801766b8  cmova   rdx, r8
0x1801766bc  cmp     [rbp+250h+var_238], 3
0x1801766c1  jnz     short loc_1801766DE
0x1801766c3  movzx   ecx, word ptr [rdx]
0x1801766c6  mov     eax, 6E61h
0x1801766cb  sub     ecx, eax
0x1801766cd  jnz     short loc_1801766D6
0x1801766cf  movzx   ecx, byte ptr [rdx+2]
0x1801766d3  sub     ecx, 79h ; 'y'
0x1801766d6  test    ecx, ecx
0x1801766d8  jnz     short loc_1801766DE
0x1801766da  mov     ebx, edi
0x1801766dc  jmp     short loc_18017670A
0x1801766de  lea     rdx, [rbp+250h+var_248]
0x1801766e2  cmp     r9, 0Fh
0x1801766e6  cmova   rdx, r8; int
0x1801766ea  lea     rax, [rbp+250h+var_220]
0x1801766ee  mov     [rsp+350h+var_330], rax; unsigned int *
0x1801766f3  xor     r9d, r9d; void *
0x1801766f6  lea     r8, [rbp+250h+var_228]; char *
0x1801766fa  mov     ecx, r13d; this
0x1801766fd  call    ?inet_pton@socket_ops@detail@asio@boost@@YAHHPEBDPEAXPEAKAEAVerror_code@system@4@@Z; boost::asio::detail::socket_ops::inet_pton(int,char const *,void *,ulong *,boost::system::error_code &)
0x180176702  mov     ebx, dword ptr [rbp+250h+var_228]
0x180176705  test    eax, eax
0x180176707  cmovle  ebx, edi
0x18017670a  xorps   xmm7, xmm7
0x18017670d  mov     r15d, edi
0x180176710  mov     r14d, edi
0x180176713  jmp     loc_180176912
0x180176718  test    ebx, ebx
0x18017671a  jnz     loc_1801767D8
0x180176720  mov     r8, qword ptr [rbp+250h+var_248]
0x180176724  mov     r9, [rbp+250h+var_230]
0x180176728  cmp     r9, 0Fh
0x18017672c  cmova   rdx, r8
0x180176730  cmp     [rbp+250h+var_238], 9
0x180176735  jnz     short loc_180176764
0x180176737  mov     rcx, [rdx]
0x18017673a  mov     rax, 736F686C61636F6Ch
0x180176744  sub     rcx, rax
0x180176747  jnz     short loc_180176756
0x180176749  movzx   ecx, byte ptr [rdx+8]
0x18017674d  lea     eax, [rbx+74h]
0x180176750  movzx   eax, al
0x180176753  sub     rcx, rax
0x180176756  test    rcx, rcx
0x180176759  jnz     short loc_180176764
0x18017675b  lea     rdx, a127001; "127.0.0.1"
0x180176762  jmp     short loc_180176795
0x180176764  lea     rdx, [rbp+250h+var_248]
0x180176768  cmp     r9, 0Fh
0x18017676c  cmova   rdx, r8
0x180176770  cmp     [rbp+250h+var_238], 3
0x180176775  jnz     short loc_1801767A6
0x180176777  movzx   ecx, word ptr [rdx]
0x18017677a  mov     eax, 6E61h
0x18017677f  sub     ecx, eax
0x180176781  jnz     short loc_18017678A
0x180176783  movzx   ecx, byte ptr [rdx+2]
0x180176787  sub     ecx, 79h ; 'y'
0x18017678a  test    ecx, ecx
0x18017678c  jnz     short loc_1801767A6
0x18017678e  lea     rdx, a0000; "0.0.0.0"
0x180176795  lea     rcx, [rbp+250h+var_248]
0x180176799  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD@Z; std::string::assign(char const * const)
0x18017679e  mov     r8, qword ptr [rbp+250h+var_248]
0x1801767a2  mov     r9, [rbp+250h+var_230]
0x1801767a6  lea     rdx, [rbp+250h+var_248]
0x1801767aa  cmp     r9, 0Fh
0x1801767ae  cmova   rdx, r8
0x1801767b2  lea     r8, [rbp+250h+var_220]
0x1801767b6  lea     rcx, [rsp+350h+var_320]
0x1801767bb  call    ?make_address@ip@asio@boost@@YA?AVaddress@123@PEBDAEAVerror_code@system@3@@Z; boost::asio::ip::make_address(char const *,boost::system::error_code &)
0x1801767c0  mov     r15d, dword ptr [rsp+350h+var_320]
0x1801767c5  mov     ebx, dword ptr [rsp+350h+var_320+4]
0x1801767c9  movups  xmm7, xmmword ptr [rsp+350h+var_320+8]
0x1801767ce  mov     r14d, [rsp+350h+var_308]
0x1801767d3  jmp     loc_180176912
0x1801767d8  cmp     [rbp+250h+var_230], 0Fh
0x1801767dd  cmova   rdx, qword ptr [rbp+250h+var_248]
0x1801767e2  cmp     [rbp+250h+var_238], 9
0x1801767e7  jnz     short loc_18017681E
0x1801767e9  mov     rcx, [rdx]
0x1801767ec  mov     rax, 736F686C61636F6Ch
0x1801767f6  sub     rcx, rax
0x1801767f9  jnz     short loc_18017680A
0x1801767fb  movzx   ecx, byte ptr [rdx+8]
0x1801767ff  mov     eax, 74h ; 't'
0x180176804  movzx   eax, al
0x180176807  sub     rcx, rax
0x18017680a  test    rcx, rcx
0x18017680d  jnz     short loc_18017681E
0x18017680f  movups  xmmword ptr [rsp+350h+var_320], xmm0
0x180176814  mov     [rsp+350h+var_320+0Fh], 1
0x180176819  jmp     loc_180176902
0x18017681e  lea     rdx, [rbp+250h+var_248]
0x180176822  cmp     [rbp+250h+var_230], 0Fh
0x180176827  cmova   rdx, qword ptr [rbp+250h+var_248]
0x18017682c  cmp     [rbp+250h+var_238], 3
0x180176831  jnz     short loc_180176852
0x180176833  movzx   ecx, word ptr [rdx]
0x180176836  mov     eax, 6E61h
0x18017683b  sub     ecx, eax
0x18017683d  jnz     short loc_180176846
0x18017683f  movzx   ecx, byte ptr [rdx+2]
0x180176843  sub     ecx, 79h ; 'y'
0x180176846  test    ecx, ecx
0x180176848  jnz     short loc_180176852
0x18017684a  xorps   xmm7, xmm7
0x18017684d  jmp     loc_180176907
0x180176852  lea     r8, [rbp+250h+var_220]
0x180176856  lea     rdx, [rbp+250h+var_248]
0x18017685a  lea     rcx, [rsp+350h+var_320]
0x18017685f  call    ?make_address_v6@ip@asio@boost@@YA?AVaddress_v6@123@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAVerror_code@system@3@@Z; boost::asio::ip::make_address_v6(std::string const &,boost::system::error_code &)
0x180176864  movups  xmm7, xmmword ptr [rax]
0x180176867  mov     r14d, [rax+10h]
0x18017686b  cmp     ebx, r13d
0x18017686e  jz      loc_18017690A
0x180176874  mov     dword ptr [rsp+350h+var_320], edi
0x180176878  mov     qword ptr [rsp+350h+var_320+8], rdi
0x18017687d  lea     rdx, [rsp+350h+var_320]
0x180176882  lea     rcx, [rbp+250h+var_220]
0x180176886  call    ??8system@boost@@YA_NAEBVerror_code@01@AEBVerror_condition@01@@Z; boost::system::operator==(boost::system::error_code const &,boost::system::error_condition const &)
0x18017688b  test    al, al
0x18017688d  jnz     short loc_18017690A
0x18017688f  lea     rdx, [rbp+250h+var_248]
0x180176893  cmp     [rbp+250h+var_230], 0Fh
0x180176898  cmova   rdx, qword ptr [rbp+250h+var_248]; int
0x18017689d  lea     rax, [rbp+250h+var_220]
0x1801768a1  mov     [rsp+350h+var_330], rax; unsigned int *
0x1801768a6  xor     r9d, r9d; void *
0x1801768a9  lea     r8, [rbp+250h+var_228]; char *
0x1801768ad  mov     ecx, r13d; this
0x1801768b0  call    ?inet_pton@socket_ops@detail@asio@boost@@YAHHPEBDPEAXPEAKAEAVerror_code@system@4@@Z; boost::asio::detail::socket_ops::inet_pton(int,char const *,void *,ulong *,boost::system::error_code &)
0x1801768b5  mov     ebx, dword ptr [rbp+250h+var_228]
0x1801768b8  test    eax, eax
0x1801768ba  cmovle  ebx, edi
0x1801768bd  mov     dword ptr [rsp+350h+var_320], edi
0x1801768c1  mov     qword ptr [rsp+350h+var_320+8], rdi
0x1801768c6  lea     rdx, [rsp+350h+var_320]
0x1801768cb  lea     rcx, [rbp+250h+var_220]
0x1801768cf  call    ??8system@boost@@YA_NAEBVerror_code@01@AEBVerror_condition@01@@Z; boost::system::operator==(boost::system::error_code const &,boost::system::error_condition const &)
0x1801768d4  test    al, al
0x1801768d6  jz      short loc_18017690A
0x1801768d8  mov     qword ptr [rsp+350h+var_320], rdi
0x1801768dd  mov     dword ptr [rsp+350h+var_320+8], 0FFFF0000h
0x1801768e5  mov     [rsp+350h+var_320+0Ch], bl
0x1801768e9  mov     eax, ebx
0x1801768eb  shr     eax, 8
0x1801768ee  mov     [rsp+350h+var_320+0Dh], al
0x1801768f2  mov     eax, ebx
0x1801768f4  shr     eax, 10h
0x1801768f7  mov     [rsp+350h+var_320+0Eh], al
0x1801768fb  shr     ebx, 18h
0x1801768fe  mov     [rsp+350h+var_320+0Fh], bl
0x180176902  movups  xmm7, xmmword ptr [rsp+350h+var_320]
0x180176907  mov     r14d, edi
0x18017690a  mov     r15d, 1
0x180176910  mov     ebx, edi
0x180176912  mov     dword ptr [rsp+350h+var_320], edi
0x180176916  mov     qword ptr [rsp+350h+var_320+8], rdi
0x18017691b  lea     rdx, [rsp+350h+var_320]
0x180176920  lea     rcx, [rbp+250h+var_220]
0x180176924  call    ??8system@boost@@YA_NAEBVerror_code@01@AEBVerror_condition@01@@Z; boost::system::operator==(boost::system::error_code const &,boost::system::error_condition const &)
0x180176929  test    al, al
0x18017692b  jz      loc_180176A23
0x180176931  movzx   ecx, word ptr [rsi+0Ah]; netshort
0x180176935  call    cs:__imp_ntohs
0x18017693b  nop
0x18017693c  xorps   xmm6, xmm6
0x18017693f  movdqu  xmmword ptr [rsp+350h+var_320+8], xmm6
0x180176945  test    r15d, r15d
0x180176948  jnz     short loc_180176974
0x18017694a  mov     word ptr [rsp+350h+var_320], r13w
0x180176950  movzx   ecx, ax; hostshort
0x180176953  call    cs:__imp_htons
0x180176959  mov     word ptr [rsp+350h+var_320+2], ax
0x18017695e  mov     ecx, ebx; netlong
0x180176960  call    cs:__imp_ntohl
0x180176966  mov     ecx, eax; hostlong
0x180176968  call    cs:__imp_htonl
0x18017696e  mov     dword ptr [rsp+350h+var_320+4], eax
0x180176972  jmp     short loc_1801769A2
0x180176974  mov     ecx, 17h
0x180176979  mov     word ptr [rsp+350h+var_320], cx
0x18017697e  movzx   ecx, ax; hostshort
0x180176981  call    cs:__imp_htons
0x180176987  mov     word ptr [rsp+350h+var_320+2], ax
0x18017698c  mov     dword ptr [rsp+350h+var_320+4], edi
0x180176990  cmp     r15d, 1
0x180176994  jnz     short loc_180176A0E
0x180176996  movups  xmm6, xmm7
0x180176999  movdqu  xmmword ptr [rsp+350h+var_320+8], xmm7
0x18017699f  mov     edi, r14d
0x1801769a2  movups  xmm0, xmmword ptr [rsp+350h+var_320]
0x1801769a7  movups  xmmword ptr [rsi+8], xmm0
0x1801769ab  unpckhpd xmm6, xmm6
0x1801769af  movsd   qword ptr [rsi+18h], xmm6
0x1801769b4  mov     [rsi+20h], edi
0x1801769b7  movzx   ecx, [rbp+250h+var_250]; hostshort
0x1801769bb  call    cs:__imp_htons
0x1801769c1  nop
0x1801769c2  mov     [rsi+0Ah], ax
0x1801769c6  lea     rcx, [rbp+250h+var_248]
0x1801769ca  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801769cf  nop
0x1801769d0  call    cs:__imp_WSACleanup
0x1801769d6  nop
0x1801769d7  mov     rax, rsi
0x1801769da  mov     rcx, [rbp+250h+var_60]
0x1801769e1  xor     rcx, rsp; StackCookie
0x1801769e4  call    __security_check_cookie
0x1801769e9  lea     r11, [rsp+350h+var_30]
0x1801769f1  mov     rbx, [r11+58h]
0x1801769f5  movaps  xmm6, xmmword ptr [r11-10h]
0x1801769fa  movaps  xmm7, xmmword ptr [r11-20h]
0x1801769ff  mov     rsp, r11
0x180176a02  pop     r15
0x180176a04  pop     r14
0x180176a06  pop     r13
0x180176a08  pop     r12
0x180176a0a  pop     rdi
0x180176a0b  pop     rsi
0x180176a0c  pop     rbp
0x180176a0d  retn
0x180176a0e  lea     rcx, [rsp+350h+var_320]; this
0x180176a13  call    ??0bad_address_cast@ip@asio@boost@@QEAA@XZ; boost::asio::ip::bad_address_cast::bad_address_cast(void)
0x180176a18  lea     rcx, [rsp+350h+var_320]
0x180176a1d  call    ??$throw_exception@Vbad_address_cast@ip@asio@boost@@@boost@@YAXAEBVbad_address_cast@ip@asio@0@@Z; boost::throw_exception<boost::asio::ip::bad_address_cast>(boost::asio::ip::bad_address_cast const &)
0x180176a23  lea     rdx, aCW1SSrcLibbasi_98; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x180176a2a  lea     rcx, [rsp+350h+var_320]
  ... truncated ...
```
