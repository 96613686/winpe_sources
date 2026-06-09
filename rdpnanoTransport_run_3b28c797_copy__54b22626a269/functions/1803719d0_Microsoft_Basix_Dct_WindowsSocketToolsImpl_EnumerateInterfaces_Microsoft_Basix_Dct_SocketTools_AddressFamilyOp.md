# Microsoft::Basix::Dct::WindowsSocketToolsImpl::EnumerateInterfaces(Microsoft::Basix::Dct::SocketTools::AddressFamilyOptions)

- ea: `0x1803719d0`
- end: `0x180371d5b`
- name: `?EnumerateInterfaces@WindowsSocketToolsImpl@Dct@Basix@Microsoft@@UEBA?AV?$vector@UInterfaceInformation@Dct@Basix@Microsoft@@V?$allocator@UInterfaceInformation@Dct@Basix@Microsoft@@@std@@@std@@W4AddressFamilyOptions@SocketTools@234@@Z`
- size: `907`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800158a0`
- `0x180015bb8`
- `0x180024700`
- `0x180027b84`
- `0x1800440d4`
- `0x1800d515c`
- `0x18012de44`
- `0x1801dc8bc`
- `0x1801fda1c`
- `0x180249184`
- `0x180249198`
- `0x1802e9e58`
- `0x1802ea490`
- `0x18032f050`
- `0x18032f0b0`
- `0x180330b40`
- `0x18037122c`
- `0x1803714b4`
- `0x180371694`
- `0x18037195c`
- `0x1803719d0`

## import_xrefs

- `WS2_32!__imp_WSACleanup` at `0x180371c82`
- `WS2_32!__imp_WSACleanup` at `0x180371c82`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180371ab4`
- `IPHLPAPI!GetAdaptersAddresses` at `0x180371ab4`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Microsoft::Basix::Dct::WindowsSocketToolsImpl::EnumerateInterfaces(
        __int64 a1,
        __int64 a2,
        unsigned int a3)
{
  PIP_ADAPTER_ADDRESSES v5; // rbx
  ULONG v6; // r14d
  __int64 v7; // rsi
  signed int AdaptersAddresses; // r15d
  __m128i si128; // xmm6
  PIP_ADAPTER_UNICAST_ADDRESS_LH FirstUnicastAddress; // rsi
  __int64 v12; // r14
  IFTYPE IfType; // r14d
  bool v14; // zf
  ULONG Ipv6Metric; // eax
  __int64 v16; // rax
  __int64 v17; // rdx
  Microsoft::Basix *v19; // rcx
  const struct std::error_category *v20; // rax
  unsigned int v21; // edx
  _QWORD v22[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v23; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v24[32]; // [rsp+50h] [rbp-B0h] BYREF
  char v25[16]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v26[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v27[32]; // [rsp+A0h] [rbp-60h] BYREF
  char v28[136]; // [rsp+C0h] [rbp-40h] BYREF
  ULONG SizePointer; // [rsp+148h] [rbp+48h] BYREF
  PIP_ADAPTER_ADDRESSES AdapterAddresses[2]; // [rsp+150h] [rbp+50h] BYREF
  __int64 v31; // [rsp+160h] [rbp+60h]
  __int128 v32; // [rsp+168h] [rbp+68h] BYREF
  __m128i v33; // [rsp+178h] [rbp+78h]
  __int128 v34; // [rsp+188h] [rbp+88h] BYREF
  __int64 v35; // [rsp+198h] [rbp+98h]
  _BYTE pExceptionObject[136]; // [rsp+1A0h] [rbp+A0h] BYREF
  char v37; // [rsp+228h] [rbp+128h]
  ULONG v38; // [rsp+22Ch] [rbp+12Ch]
  char v39[416]; // [rsp+230h] [rbp+130h] BYREF

  v22[1] = a2;
  HIDWORD(v22[0]) = 0;
  Microsoft::Basix::WinUtils::WSAStartupObj::WSAStartupObj((Microsoft::Basix::WinUtils::WSAStartupObj *)v39, 0x202u);
  *(_OWORD *)AdapterAddresses = 0;
  v31 = 0;
  std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(AdapterAddresses, 15000, v22);
  v5 = 0;
  if ( !a3 )
    goto LABEL_6;
  if ( a3 == 1 )
  {
    v6 = 2;
    goto LABEL_7;
  }
  if ( a3 != 2 )
  {
LABEL_6:
    v6 = 0;
    goto LABEL_7;
  }
  v6 = 23;
LABEL_7:
  v7 = 3;
  while ( v7-- )
  {
    v5 = AdapterAddresses[0];
    SizePointer = LODWORD(AdapterAddresses[1]) - LODWORD(AdapterAddresses[0]);
    AdaptersAddresses = GetAdaptersAddresses(v6, 0xEu, 0, AdapterAddresses[0], &SizePointer);
    if ( AdaptersAddresses == 111 )
    {
      std::vector<unsigned char>::_Resize<std::_Value_init_tag>(AdapterAddresses, SizePointer, v22);
      v5 = 0;
    }
    else
    {
      if ( AdaptersAddresses )
      {
        std::string::string(v26, (const char *)&Str1);
        std::string::string(v27, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\windowssockettools.cpp");
        std::string::string(v24, "Failed to get interfaces");
        v20 = Microsoft::Basix::WindowsCategory(v19);
        v21 = (unsigned __int16)AdaptersAddresses | 0x80070000;
        if ( AdaptersAddresses <= 0 )
          v21 = AdaptersAddresses;
        v23 = *(_OWORD *)std::error_code::error_code((std::error_code *)v25, v21, v20);
        Microsoft::Basix::SystemException::SystemException(
          (unsigned int)pExceptionObject,
          (unsigned int)&v23,
          (unsigned int)v24,
          (unsigned int)v27,
          197,
          (__int64)v26);
        throw (Microsoft::Basix::SystemException *)pExceptionObject;
      }
      if ( v5 )
        break;
    }
  }
  *(_OWORD *)a2 = 0;
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_QWORD *)(a2 + 16) = 0;
  HIDWORD(v22[0]) = 1;
  if ( v5 )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    do
    {
      FirstUnicastAddress = v5->FirstUnicastAddress;
      v32 = 0;
      v33 = si128;
      LOBYTE(v32) = 0;
      v34 = 0;
      v35 = 0;
      v12 = Microsoft::Basix::ToString(v24, v5->FriendlyName);
      if ( &v32 != (__int128 *)v12 )
      {
        std::string::_Tidy_deallocate(&v32);
        v32 = *(_OWORD *)v12;
        v33 = *(__m128i *)(v12 + 16);
        *(_QWORD *)(v12 + 16) = 0;
        *(_QWORD *)(v12 + 24) = 15;
        *(_BYTE *)v12 = 0;
      }
      std::string::_Tidy_deallocate(v24);
      IfType = v5->IfType;
      while ( FirstUnicastAddress )
      {
        if ( FirstUnicastAddress->DadState == NldsPreferred )
        {
          Microsoft::Basix::Dct::SocketAddress::SocketAddress((Microsoft::Basix::Dct::SocketAddress *)pExceptionObject);
          if ( FirstUnicastAddress->Address.lpSockaddr->sa_family == 23 )
          {
            if ( IfType == 24
              || FirstUnicastAddress->PrefixOrigin == IpPrefixOriginDhcp
              || (v14 = FirstUnicastAddress->SuffixOrigin == NlsoRandom, v37 = 1, v14) )
            {
              v37 = 0;
            }
            Ipv6Metric = v5->Ipv6Metric;
          }
          else
          {
            v37 = 0;
            Ipv6Metric = v5->Ipv4Metric;
          }
          v38 = Ipv6Metric;
          v16 = Microsoft::Basix::Dct::_anonymous_namespace_::CreateWithRemap(
                  v28,
                  FirstUnicastAddress->Address.lpSockaddr,
                  FirstUnicastAddress->Address.iSockaddrLength,
                  a3);
          Microsoft::Basix::Dct::SocketAddress::operator=(pExceptionObject, v16);
          std::vector<Microsoft::Basix::Dct::InterfaceInformation::InterfaceAddress>::_Emplace_one_at_back<Microsoft::Basix::Dct::InterfaceInformation::InterfaceAddress const &>(
            &v34,
            pExceptionObject);
        }
        FirstUnicastAddress = FirstUnicastAddress->Next;
      }
      v17 = *(_QWORD *)(a2 + 8);
      if ( v17 == *(_QWORD *)(a2 + 16) )
        std::vector<Microsoft::Basix::Dct::InterfaceInformation>::_Emplace_reallocate<Microsoft::Basix::Dct::InterfaceInformation const &>(
          a2,
          v17,
          &v32);
      else
        std::vector<Microsoft::Basix::Dct::InterfaceInformation>::_Emplace_back_with_unused_capacity<Microsoft::Basix::Dct::InterfaceInformation const &>(
          a2,
          &v32);
      v5 = v5->Next;
      std::vector<Microsoft::Basix::Dct::InterfaceInformation::InterfaceAddress>::_Tidy(&v34);
      std::string::_Tidy_deallocate(&v32);
    }
    while ( v5 );
  }
  std::vector<unsigned char>::_Tidy(AdapterAddresses);
  WSACleanup();
  return a2;
}

```

## disassembly

```asm
0x1803719d0  mov     rax, rsp
0x1803719d3  mov     [rax+8], rbx
0x1803719d7  mov     [rax+20h], rsi
0x1803719db  mov     [rax+10h], rdx
0x1803719df  push    rbp
0x1803719e0  push    rdi
0x1803719e1  push    r12
0x1803719e3  push    r14
0x1803719e5  push    r15
0x1803719e7  lea     rbp, [rax-318h]
0x1803719ee  mov     eax, 3F0h
0x1803719f3  call    _alloca_probe
0x1803719f8  sub     rsp, rax
0x1803719fb  movaps  [rsp+410h+var_38+8], xmm6
0x180371a03  mov     rax, cs:__security_cookie
0x180371a0a  xor     rax, rsp
0x180371a0d  mov     [rbp+310h+var_40], rax
0x180371a14  mov     r12d, r8d
0x180371a17  mov     rdi, rdx
0x180371a1a  mov     qword ptr [rsp+410h+var_3D8], rdx
0x180371a1f  mov     dword ptr [rsp+410h+var_3E0+4], 0
0x180371a27  mov     edx, 202h; unsigned __int16
0x180371a2c  lea     rcx, [rbp+310h+var_1E0]; this
0x180371a33  call    ??0WSAStartupObj@WinUtils@Basix@Microsoft@@QEAA@G@Z; Microsoft::Basix::WinUtils::WSAStartupObj::WSAStartupObj(ushort)
0x180371a38  nop
0x180371a39  xor     eax, eax
0x180371a3b  xorps   xmm1, xmm1
0x180371a3e  movdqu  xmmword ptr [rbp+310h+AdapterAddresses], xmm1
0x180371a43  mov     [rbp+310h+var_2B0], rax
0x180371a47  lea     r8, [rsp+410h+var_3E0]
0x180371a4c  mov     edx, 3A98h
0x180371a51  lea     rcx, [rbp+310h+AdapterAddresses]
0x180371a55  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180371a5a  xor     ebx, ebx
0x180371a5c  mov     ecx, r12d
0x180371a5f  lea     r15d, [rbx+17h]
0x180371a63  test    r12d, r12d
0x180371a66  jz      short loc_180371A7F
0x180371a68  sub     ecx, 1
0x180371a6b  jz      short loc_180371A77
0x180371a6d  cmp     ecx, 1
0x180371a70  jnz     short loc_180371A7F
0x180371a72  mov     r14d, r15d
0x180371a75  jmp     short loc_180371A82
0x180371a77  mov     r14d, 2
0x180371a7d  jmp     short loc_180371A82
0x180371a7f  xor     r14d, r14d
0x180371a82  mov     esi, 3
0x180371a87  mov     rax, rsi
0x180371a8a  dec     rsi
0x180371a8d  test    rax, rax
0x180371a90  jz      short loc_180371AE5
0x180371a92  mov     rbx, [rbp+310h+AdapterAddresses]
0x180371a96  mov     eax, dword ptr [rbp+310h+AdapterAddresses+8]
0x180371a99  sub     eax, ebx
0x180371a9b  mov     [rbp+310h+var_2C8], eax
0x180371a9e  lea     rax, [rbp+310h+var_2C8]
0x180371aa2  mov     [rsp+410h+SizePointer], rax; SizePointer
0x180371aa7  mov     r9, rbx; AdapterAddresses
0x180371aaa  xor     r8d, r8d; Reserved
0x180371aad  lea     edx, [r8+0Eh]; Flags
0x180371ab1  mov     ecx, r14d; Family
0x180371ab4  call    cs:__imp_GetAdaptersAddresses
0x180371aba  mov     r15d, eax
0x180371abd  cmp     eax, 6Fh ; 'o'
0x180371ac0  jnz     short loc_180371AD7
0x180371ac2  mov     edx, [rbp+310h+var_2C8]
0x180371ac5  lea     r8, [rsp+410h+var_3E0]
0x180371aca  lea     rcx, [rbp+310h+AdapterAddresses]
0x180371ace  call    ??$_Resize@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x180371ad3  xor     ebx, ebx
0x180371ad5  jmp     short loc_180371A87
0x180371ad7  test    r15d, r15d
0x180371ada  jnz     loc_180371CBB
0x180371ae0  test    rbx, rbx
0x180371ae3  jz      short loc_180371A87
0x180371ae5  xorps   xmm0, xmm0
0x180371ae8  xor     eax, eax
0x180371aea  movups  xmmword ptr [rdi], xmm0
0x180371aed  mov     [rdi], rax
0x180371af0  mov     [rdi+8], rax
0x180371af4  mov     [rdi+10h], rax
0x180371af8  mov     dword ptr [rsp+410h+var_3E0+4], 1
0x180371b00  test    rbx, rbx
0x180371b03  jz      loc_180371C78
0x180371b09  movdqa  xmm6, cs:__xmm@000000000000000f0000000000000000
0x180371b11  lea     r15d, [rax+17h]
0x180371b15  mov     rsi, [rbx+18h]
0x180371b19  xorps   xmm0, xmm0
0x180371b1c  movups  [rbp+310h+var_2A8], xmm0
0x180371b20  movdqu  [rbp+310h+var_298], xmm6
0x180371b25  mov     byte ptr [rbp+310h+var_2A8], 0
0x180371b29  movdqu  [rbp+310h+var_288], xmm0
0x180371b31  mov     [rbp+310h+var_278], 0
0x180371b3c  mov     rdx, [rbx+48h]
0x180371b40  lea     rcx, [rsp+410h+var_3C0]
0x180371b45  call    ?ToString@Basix@Microsoft@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEA_W@Z; Microsoft::Basix::ToString(wchar_t *)
0x180371b4a  mov     r14, rax
0x180371b4d  lea     rax, [rbp+310h+var_2A8]
0x180371b51  cmp     rax, r14
0x180371b54  jz      short loc_180371B84
0x180371b56  lea     rcx, [rbp+310h+var_2A8]
0x180371b5a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180371b5f  movups  xmm0, xmmword ptr [r14]
0x180371b63  movups  [rbp+310h+var_2A8], xmm0
0x180371b67  movups  xmm1, xmmword ptr [r14+10h]
0x180371b6c  movups  [rbp+310h+var_298], xmm1
0x180371b70  mov     qword ptr [r14+10h], 0
0x180371b78  mov     qword ptr [r14+18h], 0Fh
0x180371b80  mov     byte ptr [r14], 0
0x180371b84  lea     rcx, [rsp+410h+var_3C0]
0x180371b89  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180371b8e  mov     r14d, [rbx+64h]
0x180371b92  jmp     loc_180371C2C
0x180371b97  cmp     dword ptr [rsi+28h], 4
0x180371b9b  jnz     loc_180371C28
0x180371ba1  lea     rcx, [rbp+310h+pExceptionObject]; this
0x180371ba8  call    ??0SocketAddress@Dct@Basix@Microsoft@@QEAA@XZ; Microsoft::Basix::Dct::SocketAddress::SocketAddress(void)
0x180371bad  mov     rax, [rsi+10h]
0x180371bb1  cmp     [rax], r15w
0x180371bb5  jnz     short loc_180371BDF
0x180371bb7  cmp     r14d, 18h
0x180371bbb  jz      short loc_180371BD0
0x180371bbd  cmp     dword ptr [rsi+20h], 3
0x180371bc1  jz      short loc_180371BD0
0x180371bc3  cmp     dword ptr [rsi+24h], 5
0x180371bc7  mov     [rbp+310h+var_1E8], 1
0x180371bce  jnz     short loc_180371BD7
0x180371bd0  mov     [rbp+310h+var_1E8], 0
0x180371bd7  mov     eax, [rbx+0DCh]
0x180371bdd  jmp     short loc_180371BEC
0x180371bdf  mov     [rbp+310h+var_1E8], 0
0x180371be6  mov     eax, [rbx+0D8h]
0x180371bec  mov     [rbp+310h+var_1E4], eax
0x180371bf2  movsxd  r8, dword ptr [rsi+18h]
0x180371bf6  mov     r9d, r12d
0x180371bf9  mov     rdx, [rsi+10h]
0x180371bfd  lea     rcx, [rbp+310h+var_350]
0x180371c01  call    Microsoft__Basix__Dct___anonymous_namespace___CreateWithRemap
0x180371c06  mov     rdx, rax
0x180371c09  lea     rcx, [rbp+310h+pExceptionObject]
0x180371c10  call    ??4SocketAddress@Dct@Basix@Microsoft@@QEAAAEAV0123@AEBV0123@@Z; Microsoft::Basix::Dct::SocketAddress::operator=(Microsoft::Basix::Dct::SocketAddress const &)
0x180371c15  lea     rdx, [rbp+310h+pExceptionObject]
0x180371c1c  lea     rcx, [rbp+310h+var_288]
0x180371c23  call    ??$_Emplace_one_at_back@AEBUInterfaceAddress@InterfaceInformation@Dct@Basix@Microsoft@@@?$vector@UInterfaceAddress@InterfaceInformation@Dct@Basix@Microsoft@@V?$allocator@UInterfaceAddress@InterfaceInformation@Dct@Basix@Microsoft@@@std@@@std@@AEAAAEAUInterfaceAddress@InterfaceInformation@Dct@Basix@Microsoft@@AEBU23456@@Z; std::vector<Microsoft::Basix::Dct::InterfaceInformation::InterfaceAddress>::_Emplace_one_at_back<Microsoft::Basix::Dct::InterfaceInformation::InterfaceAddress const &>(Microsoft::Basix::Dct::InterfaceInformation::InterfaceAddress const &)
0x180371c28  mov     rsi, [rsi+8]
0x180371c2c  test    rsi, rsi
0x180371c2f  jnz     loc_180371B97
0x180371c35  mov     rdx, [rdi+8]
0x180371c39  mov     rcx, rdi
0x180371c3c  cmp     rdx, [rdi+10h]
0x180371c40  jz      short loc_180371C4D
0x180371c42  lea     rdx, [rbp+310h+var_2A8]
0x180371c46  call    ??$_Emplace_back_with_unused_capacity@AEBUInterfaceInformation@Dct@Basix@Microsoft@@@?$vector@UInterfaceInformation@Dct@Basix@Microsoft@@V?$allocator@UInterfaceInformation@Dct@Basix@Microsoft@@@std@@@std@@AEAAAEAUInterfaceInformation@Dct@Basix@Microsoft@@AEBU2345@@Z; std::vector<Microsoft::Basix::Dct::InterfaceInformation>::_Emplace_back_with_unused_capacity<Microsoft::Basix::Dct::InterfaceInformation const &>(Microsoft::Basix::Dct::InterfaceInformation const &)
0x180371c4b  jmp     short loc_180371C56
0x180371c4d  lea     r8, [rbp+310h+var_2A8]
0x180371c51  call    ??$_Emplace_reallocate@AEBUInterfaceInformation@Dct@Basix@Microsoft@@@?$vector@UInterfaceInformation@Dct@Basix@Microsoft@@V?$allocator@UInterfaceInformation@Dct@Basix@Microsoft@@@std@@@std@@AEAAPEAUInterfaceInformation@Dct@Basix@Microsoft@@QEAU2345@AEBU2345@@Z; std::vector<Microsoft::Basix::Dct::InterfaceInformation>::_Emplace_reallocate<Microsoft::Basix::Dct::InterfaceInformation const &>(Microsoft::Basix::Dct::InterfaceInformation * const,Microsoft::Basix::Dct::InterfaceInformation const &)
0x180371c56  mov     rbx, [rbx+8]
0x180371c5a  lea     rcx, [rbp+310h+var_288]
0x180371c61  call    ?_Tidy@?$vector@UInterfaceAddress@InterfaceInformation@Dct@Basix@Microsoft@@V?$allocator@UInterfaceAddress@InterfaceInformation@Dct@Basix@Microsoft@@@std@@@std@@AEAAXXZ; std::vector<Microsoft::Basix::Dct::InterfaceInformation::InterfaceAddress>::_Tidy(void)
0x180371c66  lea     rcx, [rbp+310h+var_2A8]
0x180371c6a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180371c6f  test    rbx, rbx
0x180371c72  jnz     loc_180371B15
0x180371c78  lea     rcx, [rbp+310h+AdapterAddresses]
0x180371c7c  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180371c81  nop
0x180371c82  call    cs:__imp_WSACleanup
0x180371c88  mov     rax, rdi
0x180371c8b  mov     rcx, [rbp+310h+var_40]
0x180371c92  xor     rcx, rsp; StackCookie
0x180371c95  call    __security_check_cookie
0x180371c9a  lea     r11, [rsp+410h+var_20]
0x180371ca2  mov     rbx, [r11+30h]
0x180371ca6  mov     rsi, [r11+48h]
0x180371caa  movaps  xmm6, xmmword ptr [r11-10h]
0x180371caf  mov     rsp, r11
0x180371cb2  pop     r15
0x180371cb4  pop     r14
0x180371cb6  pop     r12
0x180371cb8  pop     rdi
0x180371cb9  pop     rbp
0x180371cba  retn
0x180371cbb  lea     rdx, Str1
0x180371cc2  lea     rcx, [rbp+310h+var_390]
0x180371cc6  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180371ccb  nop
0x180371ccc  lea     rdx, aCW1SSrcLibbasi_5; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x180371cd3  lea     rcx, [rbp+310h+var_370]
0x180371cd7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180371cdc  nop
0x180371cdd  lea     rdx, aFailedToGetInt; "Failed to get interfaces"
0x180371ce4  lea     rcx, [rsp+410h+var_3C0]
0x180371ce9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180371cee  nop
0x180371cef  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x180371cf4  movzx   edx, r15w
0x180371cf8  or      edx, 80070000h
0x180371cfe  test    r15d, r15d
0x180371d01  cmovle  edx, r15d; int
0x180371d05  mov     r8, rax; struct std::error_category *
0x180371d08  lea     rcx, [rsp+410h+var_3A0]; this
0x180371d0d  call    ??0error_code@std@@QEAA@HAEBVerror_category@1@@Z; std::error_code::error_code(int,std::error_category const &)
0x180371d12  movups  xmm0, xmmword ptr [rax]
0x180371d15  movdqu  xmmword ptr [rsp+410h+var_3D8+8], xmm0
0x180371d1b  lea     rax, [rbp+310h+var_390]
0x180371d1f  mov     qword ptr [rsp+410h+var_3E8], rax
0x180371d24  mov     [rsp+410h+SizePointer], 0C5h
0x180371d2d  lea     r9, [rbp+310h+var_370]
0x180371d31  lea     r8, [rsp+410h+var_3C0]
0x180371d36  lea     rdx, [rsp+410h+var_3D8+8]
0x180371d3b  lea     rcx, [rbp+310h+pExceptionObject]
0x180371d42  call    ??0SystemException@Basix@Microsoft@@QEAA@Verror_code@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1_K1@Z; Microsoft::Basix::SystemException::SystemException(std::error_code,std::string const &,std::string const &,unsigned __int64,std::string const &)
0x180371d47  lea     rdx, _TI6?AVSystemException@Basix@Microsoft@@; pThrowInfo
0x180371d4e  lea     rcx, [rbp+310h+pExceptionObject]; pExceptionObject
0x180371d55  call    _CxxThrowException
```
