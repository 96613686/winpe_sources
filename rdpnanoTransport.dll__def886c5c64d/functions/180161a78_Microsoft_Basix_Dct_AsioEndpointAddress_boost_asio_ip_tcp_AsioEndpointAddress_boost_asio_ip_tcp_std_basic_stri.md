# Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::tcp>::AsioEndpointAddress<boost::asio::ip::tcp>(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,ushort,Microsoft::Basix::Dct::SocketTools::AddressFamilyOptions)

- ea: `0x180161a78`
- end: `0x180161f3a`
- name: `??0?$AsioEndpointAddress@Vtcp@ip@asio@boost@@@Dct@Basix@Microsoft@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@GW4AddressFamilyOptions@SocketTools@123@@Z`
- size: `1218`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801603f8`
- `0x18017fb10`

## callees

- `0x180015bb8`
- `0x180017518`
- `0x180024700`
- `0x1800448dc`
- `0x18012de44`
- `0x180145f40`
- `0x180161508`
- `0x180161a78`
- `0x180163e0c`
- `0x180165c50`
- `0x18016ea70`
- `0x18016f37c`
- `0x18016f474`
- `0x1801a8c3c`
- `0x1802e9b68`
- `0x18032f050`
- `0x18032f0b0`
- `0x180330b40`

## import_xrefs

- `WS2_32!__imp_htonl` at `0x180161b6e`
- `WS2_32!__imp_htonl` at `0x180161e30`
- `WS2_32!__imp_htonl` at `0x180161b6e`
- `WS2_32!__imp_htonl` at `0x180161e30`
- `WS2_32!__imp_htons` at `0x180161e1b`
- `WS2_32!__imp_htons` at `0x180161e49`
- `WS2_32!__imp_htons` at `0x180161e83`
- `WS2_32!__imp_htons` at `0x180161e1b`
- `WS2_32!__imp_htons` at `0x180161e49`
- `WS2_32!__imp_htons` at `0x180161e83`
- `WS2_32!__imp_ntohl` at `0x180161e28`
- `WS2_32!__imp_ntohl` at `0x180161e28`
- `WS2_32!__imp_ntohs` at `0x180161dfd`
- `WS2_32!__imp_ntohs` at `0x180161dfd`
- `WS2_32!__imp_WSACleanup` at `0x180161e98`
- `WS2_32!__imp_WSACleanup` at `0x180161e98`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::tcp>::AsioEndpointAddress<boost::asio::ip::tcp>(
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
  *(_QWORD *)a1 = &Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::tcp>::`vftable';
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
0x180161a78  mov     [rsp-8+arg_18], rbx
0x180161a7d  push    rbp
0x180161a7e  push    rsi
0x180161a7f  push    rdi
0x180161a80  push    r12
0x180161a82  push    r13
0x180161a84  push    r14
0x180161a86  push    r15
0x180161a88  lea     rbp, [rsp-220h]
0x180161a90  mov     eax, 320h
0x180161a95  call    _alloca_probe
0x180161a9a  sub     rsp, rax
0x180161a9d  movaps  [rsp+350h+var_40], xmm6
0x180161aa5  movaps  [rsp+350h+var_50], xmm7
0x180161aad  mov     rax, cs:__security_cookie
0x180161ab4  xor     rax, rsp
0x180161ab7  mov     [rbp+250h+var_60], rax
0x180161abe  mov     ebx, r9d
0x180161ac1  mov     r12, rdx
0x180161ac4  mov     rsi, rcx
0x180161ac7  mov     [rsp+350h+var_300], rcx
0x180161acc  mov     [rbp+250h+var_250], r8w
0x180161ad1  call    ??0EndpointAddress@Dct@Basix@Microsoft@@QEAA@XZ; Microsoft::Basix::Dct::EndpointAddress::EndpointAddress(void)
0x180161ad6  nop
0x180161ad7  lea     rax, ??_7?$AsioEndpointAddress@Vtcp@ip@asio@boost@@@Dct@Basix@Microsoft@@6B@; const Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::tcp>::`vftable'
0x180161ade  mov     [rsi], rax
0x180161ae1  xor     edi, edi
0x180161ae3  mov     [rsi+10h], rdi
0x180161ae7  mov     [rsi+18h], rdi
0x180161aeb  mov     [rsi+20h], edi
0x180161aee  lea     r13d, [rdi+2]
0x180161af2  mov     [rsi+8], r13
0x180161af6  mov     edx, 202h; unsigned __int16
0x180161afb  lea     rcx, [rbp+250h+var_200]; this
0x180161aff  call    ??0WSAStartupObj@WinUtils@Basix@Microsoft@@QEAA@G@Z; Microsoft::Basix::WinUtils::WSAStartupObj::WSAStartupObj(ushort)
0x180161b04  nop
0x180161b05  lea     r8, [rbp+250h+var_250]
0x180161b09  mov     rdx, r12
0x180161b0c  lea     rcx, [rbp+250h+var_248]
0x180161b10  call    ??$SplitHostnameAndPort@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@G@Basix@Microsoft@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV23@AEAG@Z; Microsoft::Basix::SplitHostnameAndPort<std::string,ushort>(std::string const &,ushort &)
0x180161b15  nop
0x180161b16  xorps   xmm0, xmm0
0x180161b19  movups  xmmword ptr [rbp+250h+var_220], xmm0
0x180161b1d  mov     [rbp+250h+var_210], rdi
0x180161b21  lea     rdx, [rbp+250h+var_248]
0x180161b25  cmp     ebx, 1
0x180161b28  jnz     loc_180161BE0
0x180161b2e  mov     r8, qword ptr [rbp+250h+var_248]
0x180161b32  mov     r9, [rbp+250h+var_230]
0x180161b36  cmp     r9, 0Fh
0x180161b3a  cmova   rdx, r8
0x180161b3e  cmp     [rbp+250h+var_238], 9
0x180161b43  jnz     short loc_180161B78
0x180161b45  mov     rcx, [rdx]
0x180161b48  mov     rax, 736F686C61636F6Ch
0x180161b52  sub     rcx, rax
0x180161b55  jnz     short loc_180161B64
0x180161b57  movzx   ecx, byte ptr [rdx+8]
0x180161b5b  lea     eax, [rdi+74h]
0x180161b5e  movzx   eax, al
0x180161b61  sub     rcx, rax
0x180161b64  test    rcx, rcx
0x180161b67  jnz     short loc_180161B78
0x180161b69  mov     ecx, 7F000001h; hostlong
0x180161b6e  call    cs:__imp_htonl
0x180161b74  mov     ebx, eax
0x180161b76  jmp     short loc_180161BD2
0x180161b78  lea     rdx, [rbp+250h+var_248]
0x180161b7c  cmp     r9, 0Fh
0x180161b80  cmova   rdx, r8
0x180161b84  cmp     [rbp+250h+var_238], 3
0x180161b89  jnz     short loc_180161BA6
0x180161b8b  movzx   ecx, word ptr [rdx]
0x180161b8e  mov     eax, 6E61h
0x180161b93  sub     ecx, eax
0x180161b95  jnz     short loc_180161B9E
0x180161b97  movzx   ecx, byte ptr [rdx+2]
0x180161b9b  sub     ecx, 79h ; 'y'
0x180161b9e  test    ecx, ecx
0x180161ba0  jnz     short loc_180161BA6
0x180161ba2  mov     ebx, edi
0x180161ba4  jmp     short loc_180161BD2
0x180161ba6  lea     rdx, [rbp+250h+var_248]
0x180161baa  cmp     r9, 0Fh
0x180161bae  cmova   rdx, r8; int
0x180161bb2  lea     rax, [rbp+250h+var_220]
0x180161bb6  mov     [rsp+350h+var_330], rax; unsigned int *
0x180161bbb  xor     r9d, r9d; void *
0x180161bbe  lea     r8, [rbp+250h+var_228]; char *
0x180161bc2  mov     ecx, r13d; this
0x180161bc5  call    ?inet_pton@socket_ops@detail@asio@boost@@YAHHPEBDPEAXPEAKAEAVerror_code@system@4@@Z; boost::asio::detail::socket_ops::inet_pton(int,char const *,void *,ulong *,boost::system::error_code &)
0x180161bca  mov     ebx, dword ptr [rbp+250h+var_228]
0x180161bcd  test    eax, eax
0x180161bcf  cmovle  ebx, edi
0x180161bd2  xorps   xmm7, xmm7
0x180161bd5  mov     r15d, edi
0x180161bd8  mov     r14d, edi
0x180161bdb  jmp     loc_180161DDA
0x180161be0  test    ebx, ebx
0x180161be2  jnz     loc_180161CA0
0x180161be8  mov     r8, qword ptr [rbp+250h+var_248]
0x180161bec  mov     r9, [rbp+250h+var_230]
0x180161bf0  cmp     r9, 0Fh
0x180161bf4  cmova   rdx, r8
0x180161bf8  cmp     [rbp+250h+var_238], 9
0x180161bfd  jnz     short loc_180161C2C
0x180161bff  mov     rcx, [rdx]
0x180161c02  mov     rax, 736F686C61636F6Ch
0x180161c0c  sub     rcx, rax
0x180161c0f  jnz     short loc_180161C1E
0x180161c11  movzx   ecx, byte ptr [rdx+8]
0x180161c15  lea     eax, [rbx+74h]
0x180161c18  movzx   eax, al
0x180161c1b  sub     rcx, rax
0x180161c1e  test    rcx, rcx
0x180161c21  jnz     short loc_180161C2C
0x180161c23  lea     rdx, a127001; "127.0.0.1"
0x180161c2a  jmp     short loc_180161C5D
0x180161c2c  lea     rdx, [rbp+250h+var_248]
0x180161c30  cmp     r9, 0Fh
0x180161c34  cmova   rdx, r8
0x180161c38  cmp     [rbp+250h+var_238], 3
0x180161c3d  jnz     short loc_180161C6E
0x180161c3f  movzx   ecx, word ptr [rdx]
0x180161c42  mov     eax, 6E61h
0x180161c47  sub     ecx, eax
0x180161c49  jnz     short loc_180161C52
0x180161c4b  movzx   ecx, byte ptr [rdx+2]
0x180161c4f  sub     ecx, 79h ; 'y'
0x180161c52  test    ecx, ecx
0x180161c54  jnz     short loc_180161C6E
0x180161c56  lea     rdx, a0000; "0.0.0.0"
0x180161c5d  lea     rcx, [rbp+250h+var_248]
0x180161c61  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD@Z; std::string::assign(char const * const)
0x180161c66  mov     r8, qword ptr [rbp+250h+var_248]
0x180161c6a  mov     r9, [rbp+250h+var_230]
0x180161c6e  lea     rdx, [rbp+250h+var_248]
0x180161c72  cmp     r9, 0Fh
0x180161c76  cmova   rdx, r8
0x180161c7a  lea     r8, [rbp+250h+var_220]
0x180161c7e  lea     rcx, [rsp+350h+var_320]
0x180161c83  call    ?make_address@ip@asio@boost@@YA?AVaddress@123@PEBDAEAVerror_code@system@3@@Z; boost::asio::ip::make_address(char const *,boost::system::error_code &)
0x180161c88  mov     r15d, dword ptr [rsp+350h+var_320]
0x180161c8d  mov     ebx, dword ptr [rsp+350h+var_320+4]
0x180161c91  movups  xmm7, xmmword ptr [rsp+350h+var_320+8]
0x180161c96  mov     r14d, [rsp+350h+var_308]
0x180161c9b  jmp     loc_180161DDA
0x180161ca0  cmp     [rbp+250h+var_230], 0Fh
0x180161ca5  cmova   rdx, qword ptr [rbp+250h+var_248]
0x180161caa  cmp     [rbp+250h+var_238], 9
0x180161caf  jnz     short loc_180161CE6
0x180161cb1  mov     rcx, [rdx]
0x180161cb4  mov     rax, 736F686C61636F6Ch
0x180161cbe  sub     rcx, rax
0x180161cc1  jnz     short loc_180161CD2
0x180161cc3  movzx   ecx, byte ptr [rdx+8]
0x180161cc7  mov     eax, 74h ; 't'
0x180161ccc  movzx   eax, al
0x180161ccf  sub     rcx, rax
0x180161cd2  test    rcx, rcx
0x180161cd5  jnz     short loc_180161CE6
0x180161cd7  movups  xmmword ptr [rsp+350h+var_320], xmm0
0x180161cdc  mov     [rsp+350h+var_320+0Fh], 1
0x180161ce1  jmp     loc_180161DCA
0x180161ce6  lea     rdx, [rbp+250h+var_248]
0x180161cea  cmp     [rbp+250h+var_230], 0Fh
0x180161cef  cmova   rdx, qword ptr [rbp+250h+var_248]
0x180161cf4  cmp     [rbp+250h+var_238], 3
0x180161cf9  jnz     short loc_180161D1A
0x180161cfb  movzx   ecx, word ptr [rdx]
0x180161cfe  mov     eax, 6E61h
0x180161d03  sub     ecx, eax
0x180161d05  jnz     short loc_180161D0E
0x180161d07  movzx   ecx, byte ptr [rdx+2]
0x180161d0b  sub     ecx, 79h ; 'y'
0x180161d0e  test    ecx, ecx
0x180161d10  jnz     short loc_180161D1A
0x180161d12  xorps   xmm7, xmm7
0x180161d15  jmp     loc_180161DCF
0x180161d1a  lea     r8, [rbp+250h+var_220]
0x180161d1e  lea     rdx, [rbp+250h+var_248]
0x180161d22  lea     rcx, [rsp+350h+var_320]
0x180161d27  call    ?make_address_v6@ip@asio@boost@@YA?AVaddress_v6@123@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAVerror_code@system@3@@Z; boost::asio::ip::make_address_v6(std::string const &,boost::system::error_code &)
0x180161d2c  movups  xmm7, xmmword ptr [rax]
0x180161d2f  mov     r14d, [rax+10h]
0x180161d33  cmp     ebx, r13d
0x180161d36  jz      loc_180161DD2
0x180161d3c  mov     dword ptr [rsp+350h+var_320], edi
0x180161d40  mov     qword ptr [rsp+350h+var_320+8], rdi
0x180161d45  lea     rdx, [rsp+350h+var_320]
0x180161d4a  lea     rcx, [rbp+250h+var_220]
0x180161d4e  call    ??8system@boost@@YA_NAEBVerror_code@01@AEBVerror_condition@01@@Z; boost::system::operator==(boost::system::error_code const &,boost::system::error_condition const &)
0x180161d53  test    al, al
0x180161d55  jnz     short loc_180161DD2
0x180161d57  lea     rdx, [rbp+250h+var_248]
0x180161d5b  cmp     [rbp+250h+var_230], 0Fh
0x180161d60  cmova   rdx, qword ptr [rbp+250h+var_248]; int
0x180161d65  lea     rax, [rbp+250h+var_220]
0x180161d69  mov     [rsp+350h+var_330], rax; unsigned int *
0x180161d6e  xor     r9d, r9d; void *
0x180161d71  lea     r8, [rbp+250h+var_228]; char *
0x180161d75  mov     ecx, r13d; this
0x180161d78  call    ?inet_pton@socket_ops@detail@asio@boost@@YAHHPEBDPEAXPEAKAEAVerror_code@system@4@@Z; boost::asio::detail::socket_ops::inet_pton(int,char const *,void *,ulong *,boost::system::error_code &)
0x180161d7d  mov     ebx, dword ptr [rbp+250h+var_228]
0x180161d80  test    eax, eax
0x180161d82  cmovle  ebx, edi
0x180161d85  mov     dword ptr [rsp+350h+var_320], edi
0x180161d89  mov     qword ptr [rsp+350h+var_320+8], rdi
0x180161d8e  lea     rdx, [rsp+350h+var_320]
0x180161d93  lea     rcx, [rbp+250h+var_220]
0x180161d97  call    ??8system@boost@@YA_NAEBVerror_code@01@AEBVerror_condition@01@@Z; boost::system::operator==(boost::system::error_code const &,boost::system::error_condition const &)
0x180161d9c  test    al, al
0x180161d9e  jz      short loc_180161DD2
0x180161da0  mov     qword ptr [rsp+350h+var_320], rdi
0x180161da5  mov     dword ptr [rsp+350h+var_320+8], 0FFFF0000h
0x180161dad  mov     [rsp+350h+var_320+0Ch], bl
0x180161db1  mov     eax, ebx
0x180161db3  shr     eax, 8
0x180161db6  mov     [rsp+350h+var_320+0Dh], al
0x180161dba  mov     eax, ebx
0x180161dbc  shr     eax, 10h
0x180161dbf  mov     [rsp+350h+var_320+0Eh], al
0x180161dc3  shr     ebx, 18h
0x180161dc6  mov     [rsp+350h+var_320+0Fh], bl
0x180161dca  movups  xmm7, xmmword ptr [rsp+350h+var_320]
0x180161dcf  mov     r14d, edi
0x180161dd2  mov     r15d, 1
0x180161dd8  mov     ebx, edi
0x180161dda  mov     dword ptr [rsp+350h+var_320], edi
0x180161dde  mov     qword ptr [rsp+350h+var_320+8], rdi
0x180161de3  lea     rdx, [rsp+350h+var_320]
0x180161de8  lea     rcx, [rbp+250h+var_220]
0x180161dec  call    ??8system@boost@@YA_NAEBVerror_code@01@AEBVerror_condition@01@@Z; boost::system::operator==(boost::system::error_code const &,boost::system::error_condition const &)
0x180161df1  test    al, al
0x180161df3  jz      loc_180161EEB
0x180161df9  movzx   ecx, word ptr [rsi+0Ah]; netshort
0x180161dfd  call    cs:__imp_ntohs
0x180161e03  nop
0x180161e04  xorps   xmm6, xmm6
0x180161e07  movdqu  xmmword ptr [rsp+350h+var_320+8], xmm6
0x180161e0d  test    r15d, r15d
0x180161e10  jnz     short loc_180161E3C
0x180161e12  mov     word ptr [rsp+350h+var_320], r13w
0x180161e18  movzx   ecx, ax; hostshort
0x180161e1b  call    cs:__imp_htons
0x180161e21  mov     word ptr [rsp+350h+var_320+2], ax
0x180161e26  mov     ecx, ebx; netlong
0x180161e28  call    cs:__imp_ntohl
0x180161e2e  mov     ecx, eax; hostlong
0x180161e30  call    cs:__imp_htonl
0x180161e36  mov     dword ptr [rsp+350h+var_320+4], eax
0x180161e3a  jmp     short loc_180161E6A
0x180161e3c  mov     ecx, 17h
0x180161e41  mov     word ptr [rsp+350h+var_320], cx
0x180161e46  movzx   ecx, ax; hostshort
0x180161e49  call    cs:__imp_htons
0x180161e4f  mov     word ptr [rsp+350h+var_320+2], ax
0x180161e54  mov     dword ptr [rsp+350h+var_320+4], edi
0x180161e58  cmp     r15d, 1
0x180161e5c  jnz     short loc_180161ED6
0x180161e5e  movups  xmm6, xmm7
0x180161e61  movdqu  xmmword ptr [rsp+350h+var_320+8], xmm7
0x180161e67  mov     edi, r14d
0x180161e6a  movups  xmm0, xmmword ptr [rsp+350h+var_320]
0x180161e6f  movups  xmmword ptr [rsi+8], xmm0
0x180161e73  unpckhpd xmm6, xmm6
0x180161e77  movsd   qword ptr [rsi+18h], xmm6
0x180161e7c  mov     [rsi+20h], edi
0x180161e7f  movzx   ecx, [rbp+250h+var_250]; hostshort
0x180161e83  call    cs:__imp_htons
0x180161e89  nop
0x180161e8a  mov     [rsi+0Ah], ax
0x180161e8e  lea     rcx, [rbp+250h+var_248]
0x180161e92  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180161e97  nop
0x180161e98  call    cs:__imp_WSACleanup
0x180161e9e  nop
0x180161e9f  mov     rax, rsi
0x180161ea2  mov     rcx, [rbp+250h+var_60]
0x180161ea9  xor     rcx, rsp; StackCookie
0x180161eac  call    __security_check_cookie
0x180161eb1  lea     r11, [rsp+350h+var_30]
0x180161eb9  mov     rbx, [r11+58h]
0x180161ebd  movaps  xmm6, xmmword ptr [r11-10h]
0x180161ec2  movaps  xmm7, xmmword ptr [r11-20h]
0x180161ec7  mov     rsp, r11
0x180161eca  pop     r15
0x180161ecc  pop     r14
0x180161ece  pop     r13
0x180161ed0  pop     r12
0x180161ed2  pop     rdi
0x180161ed3  pop     rsi
0x180161ed4  pop     rbp
0x180161ed5  retn
0x180161ed6  lea     rcx, [rsp+350h+var_320]; this
0x180161edb  call    ??0bad_address_cast@ip@asio@boost@@QEAA@XZ; boost::asio::ip::bad_address_cast::bad_address_cast(void)
0x180161ee0  lea     rcx, [rsp+350h+var_320]
0x180161ee5  call    ??$throw_exception@Vbad_address_cast@ip@asio@boost@@@boost@@YAXAEBVbad_address_cast@ip@asio@0@@Z; boost::throw_exception<boost::asio::ip::bad_address_cast>(boost::asio::ip::bad_address_cast const &)
0x180161eeb  lea     rdx, aCW1SSrcLibbasi_98; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x180161ef2  lea     rcx, [rsp+350h+var_320]
  ... truncated ...
```
