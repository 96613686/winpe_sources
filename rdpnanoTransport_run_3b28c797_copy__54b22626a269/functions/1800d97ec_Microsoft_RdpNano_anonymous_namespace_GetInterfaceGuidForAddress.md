# Microsoft::RdpNano::_anonymous_namespace_::GetInterfaceGuidForAddress

- ea: `0x1800d97ec`
- end: `0x1800d9c5b`
- name: `Microsoft::RdpNano::_anonymous_namespace_::GetInterfaceGuidForAddress`
- size: `1135`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800d7b10`

## callees

- `0x1800158a0`
- `0x180017494`
- `0x18001efc8`
- `0x180024700`
- `0x180027b84`
- `0x1800d515c`
- `0x1800d97ec`
- `0x180249cb4`
- `0x1802e9b68`
- `0x1802e9e58`
- `0x1802ea490`
- `0x18032f050`
- `0x18032f0b0`
- `0x180330b40`

## import_xrefs

- `IPHLPAPI!ConvertInterfaceLuidToGuid` at `0x1800d992b`
- `IPHLPAPI!ConvertInterfaceLuidToGuid` at `0x1800d99ba`
- `IPHLPAPI!ConvertInterfaceLuidToGuid` at `0x1800d992b`
- `IPHLPAPI!ConvertInterfaceLuidToGuid` at `0x1800d99ba`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x1800d990a`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x1800d9bf7`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x1800d990a`
- `IPHLPAPI!ConvertInterfaceIndexToLuid` at `0x1800d9bf7`
- `IPHLPAPI!GetIpAddrTable` at `0x1800d9845`
- `IPHLPAPI!GetIpAddrTable` at `0x1800d98bc`
- `IPHLPAPI!GetIpAddrTable` at `0x1800d9b4d`
- `IPHLPAPI!GetIpAddrTable` at `0x1800d9845`
- `IPHLPAPI!GetIpAddrTable` at `0x1800d98bc`
- `IPHLPAPI!GetIpAddrTable` at `0x1800d9b4d`

## string_xrefs

- `0x1800d9987`: `C:\__w\1\s\rdpnanodll\upnp\upnpmanager.cpp`
- `0x1800d9a1e`: `C:\__w\1\s\rdpnanodll\upnp\upnpmanager.cpp`
- `0x1800d9a8c`: `C:\__w\1\s\rdpnanodll\upnp\upnpmanager.cpp`
- `0x1800d9b18`: `C:\__w\1\s\rdpnanodll\upnp\upnpmanager.cpp`
- `0x1800d9bc3`: `C:\__w\1\s\rdpnanodll\upnp\upnpmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
GUID *__fastcall Microsoft::RdpNano::_anonymous_namespace_::GetInterfaceGuidForAddress(GUID *a1, __int64 a2)
{
  DWORD IpAddrTable; // ebx
  struct _MIB_IPADDRTABLE *v5; // rdi
  unsigned __int64 v6; // rax
  struct _MIB_IPADDRTABLE *v7; // rbx
  __int64 v8; // rax
  MIB_IPADDRROW *table; // rcx
  __int64 v10; // r15
  Microsoft::Basix *v12; // rcx
  const struct std::error_category *v13; // rbx
  NTSTATUS v14; // eax
  unsigned int v15; // edx
  __int64 v16; // rax
  __int64 v17; // rax
  Microsoft::Basix *v18; // rcx
  const struct std::error_category *v19; // rax
  Microsoft::Basix *v20; // rcx
  const struct std::error_category *v21; // rbx
  signed int v22; // eax
  unsigned int v23; // edx
  Microsoft::Basix *v24; // rcx
  const struct std::error_category *v25; // rbx
  NTSTATUS v26; // eax
  unsigned int v27; // edx
  _BYTE v28[8]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v29[3]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v30[32]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v31[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v32[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v33[16]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE pExceptionObject[144]; // [rsp+C0h] [rbp-40h] BYREF
  ULONG pdwSize; // [rsp+150h] [rbp+50h] BYREF
  NET_LUID InterfaceLuid; // [rsp+158h] [rbp+58h] BYREF
  PMIB_IPADDRTABLE pIpAddrTable[2]; // [rsp+160h] [rbp+60h] BYREF
  __int64 v38; // [rsp+170h] [rbp+70h]
  GUID InterfaceGuid; // [rsp+178h] [rbp+78h] BYREF

  *(_OWORD *)pIpAddrTable = 0;
  v38 = 0;
  pdwSize = 0;
  IpAddrTable = GetIpAddrTable(0, &pdwSize, 0);
  if ( IpAddrTable != 122 )
  {
    std::string::string(v31, (const char *)&Str1);
    std::string::string(v32, "C:\\__w\\1\\s\\rdpnanodll\\upnp\\upnpmanager.cpp");
    std::string::string(v30, "Failed to get IP address table size");
    v19 = Microsoft::Basix::WindowsCategory(v18);
    *(_OWORD *)&v29[1] = *(_OWORD *)std::error_code::error_code((std::error_code *)v33, IpAddrTable, v19);
    Microsoft::Basix::SystemException::SystemException(
      (unsigned int)pExceptionObject,
      (unsigned int)&v29[1],
      (unsigned int)v30,
      (unsigned int)v32,
      105,
      (__int64)v31);
    throw (Microsoft::Basix::SystemException *)pExceptionObject;
  }
  v5 = pIpAddrTable[0];
  if ( (PMIB_IPADDRTABLE)pdwSize >= (PMIB_IPADDRTABLE)((char *)pIpAddrTable[1] - (char *)pIpAddrTable[0]) )
  {
    if ( (PMIB_IPADDRTABLE)pdwSize > (PMIB_IPADDRTABLE)((char *)pIpAddrTable[1] - (char *)pIpAddrTable[0]) )
    {
      v6 = v38 - (unsigned __int64)pIpAddrTable[0];
      _mm_lfence();
      if ( pdwSize <= v6 )
      {
        v7 = (PMIB_IPADDRTABLE)((char *)pIpAddrTable[0] + pdwSize);
        std::_Zero_range<std::pair<std::shared_ptr<Microsoft::Basix::Dct::IAsyncTransport::InBuffer> const,std::chrono::duration<__int64,std::ratio<1,1000>>> * *>(
          pIpAddrTable[1],
          v7);
        pIpAddrTable[1] = v7;
      }
      else
      {
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(pIpAddrTable, pdwSize, v28);
      }
      v5 = pIpAddrTable[0];
    }
  }
  else
  {
    pIpAddrTable[1] = (PMIB_IPADDRTABLE)((char *)pIpAddrTable[0] + pdwSize);
  }
  LODWORD(v8) = GetIpAddrTable(v5, &pdwSize, 0);
  if ( (_DWORD)v8 )
  {
    std::string::string(v30, (const char *)&Str1);
    std::string::string(v32, "C:\\__w\\1\\s\\rdpnanodll\\upnp\\upnpmanager.cpp");
    std::string::string(v31, "Failed to get IP address table");
    v21 = Microsoft::Basix::WindowsCategory(v20);
    v22 = GetIpAddrTable(v5, &pdwSize, 0);
    v23 = (unsigned __int16)v22 | 0x80070000;
    if ( v22 <= 0 )
      v23 = v22;
    *(_OWORD *)&v29[1] = *(_OWORD *)std::error_code::error_code((std::error_code *)v33, v23, v21);
    Microsoft::Basix::SystemException::SystemException(
      (unsigned int)pExceptionObject,
      (unsigned int)&v29[1],
      (unsigned int)v31,
      (unsigned int)v32,
      110,
      (__int64)v30);
    throw (Microsoft::Basix::SystemException *)pExceptionObject;
  }
  InterfaceLuid.Value = 0;
  InterfaceGuid = 0;
  if ( !v5->dwNumEntries )
    goto LABEL_22;
  table = v5->table;
  while ( table->dwAddr != *(_DWORD *)(a2 + 4) )
  {
    v8 = (unsigned int)(v8 + 1);
    ++table;
    if ( (unsigned int)v8 >= v5->dwNumEntries )
      goto LABEL_22;
  }
  v10 = v8;
  if ( ConvertInterfaceIndexToLuid(v5->table[v8].dwIndex, &InterfaceLuid) )
  {
    std::string::string(v30, (const char *)&Str1);
    std::string::string(v32, "C:\\__w\\1\\s\\rdpnanodll\\upnp\\upnpmanager.cpp");
    std::string::string(v31, "Failed to convert interface index to luid");
    v25 = Microsoft::Basix::WindowsCategory(v24);
    v26 = ConvertInterfaceIndexToLuid(v5->table[v10].dwIndex, &InterfaceLuid);
    v27 = (unsigned __int16)v26 | 0x80070000;
    if ( v26 <= 0 )
      v27 = v26;
    *(_OWORD *)&v29[1] = *(_OWORD *)std::error_code::error_code((std::error_code *)v33, v27, v25);
    Microsoft::Basix::SystemException::SystemException(
      (unsigned int)pExceptionObject,
      (unsigned int)&v29[1],
      (unsigned int)v31,
      (unsigned int)v32,
      122,
      (__int64)v30);
    throw (Microsoft::Basix::SystemException *)pExceptionObject;
  }
  if ( !InterfaceLuid.Value )
  {
LABEL_22:
    std::string::string(v30, "C:\\__w\\1\\s\\rdpnanodll\\upnp\\upnpmanager.cpp");
    v16 = Microsoft::Basix::Dct::SocketAddress::ToNumericString(a2, v32);
    v17 = std::operator+<char>(v31, "Failed to find interface ", v16);
    Microsoft::Basix::Exception::Exception(pExceptionObject, v17, v30, 127);
    throw (Microsoft::Basix::Exception *)pExceptionObject;
  }
  if ( ConvertInterfaceLuidToGuid(&InterfaceLuid, &InterfaceGuid) )
  {
    std::string::string(v30, (const char *)&Str1);
    std::string::string(v32, "C:\\__w\\1\\s\\rdpnanodll\\upnp\\upnpmanager.cpp");
    std::string::string(v31, "Failed to convert interface luid to guid");
    v13 = Microsoft::Basix::WindowsCategory(v12);
    v14 = ConvertInterfaceLuidToGuid(&InterfaceLuid, &InterfaceGuid);
    v15 = (unsigned __int16)v14 | 0x80070000;
    if ( v14 <= 0 )
      v15 = v14;
    *(_OWORD *)&v29[1] = *(_OWORD *)std::error_code::error_code((std::error_code *)v33, v15, v13);
    Microsoft::Basix::SystemException::SystemException(
      (unsigned int)pExceptionObject,
      (unsigned int)&v29[1],
      (unsigned int)v31,
      (unsigned int)v32,
      128,
      (__int64)v30);
    throw (Microsoft::Basix::SystemException *)pExceptionObject;
  }
  *a1 = InterfaceGuid;
  std::vector<unsigned char>::_Tidy(pIpAddrTable);
  return a1;
}

```

## disassembly

```asm
0x1800d97ec  mov     rax, rsp
0x1800d97ef  mov     [rax+8], rbx
0x1800d97f3  mov     [rax+18h], rsi
0x1800d97f7  mov     [rax+20h], rdi
0x1800d97fb  push    rbp
0x1800d97fc  push    r14
0x1800d97fe  push    r15
0x1800d9800  lea     rbp, [rax-0A8h]
0x1800d9807  mov     eax, 190h
0x1800d980c  call    _alloca_probe
0x1800d9811  sub     rsp, rax
0x1800d9814  mov     rax, cs:__security_cookie
0x1800d981b  xor     rax, rsp
0x1800d981e  mov     [rbp+0A0h+var_18], rax
0x1800d9825  mov     r14, rdx
0x1800d9828  mov     rsi, rcx
0x1800d982b  xor     eax, eax
0x1800d982d  xorps   xmm1, xmm1
0x1800d9830  movdqu  xmmword ptr [rbp+0A0h+pIpAddrTable], xmm1
0x1800d9835  mov     [rbp+0A0h+var_30], rax
0x1800d9839  mov     [rbp+0A0h+pdwSize], eax
0x1800d983c  xor     r8d, r8d; bOrder
0x1800d983f  lea     rdx, [rbp+0A0h+pdwSize]; pdwSize
0x1800d9843  xor     ecx, ecx; pIpAddrTable
0x1800d9845  call    cs:__imp_GetIpAddrTable
0x1800d984b  mov     ebx, eax
0x1800d984d  cmp     eax, 7Ah ; 'z'
0x1800d9850  jnz     loc_1800D9A7A
0x1800d9856  mov     ecx, [rbp+0A0h+pdwSize]
0x1800d9859  mov     rax, [rbp+0A0h+pIpAddrTable+8]
0x1800d985d  mov     rdi, [rbp+0A0h+pIpAddrTable]
0x1800d9861  sub     rax, rdi
0x1800d9864  cmp     rcx, rax
0x1800d9867  jnb     short loc_1800D9873
0x1800d9869  lea     rax, [rdi+rcx]
0x1800d986d  mov     [rbp+0A0h+pIpAddrTable+8], rax
0x1800d9871  jmp     short loc_1800D98B2
0x1800d9873  jbe     short loc_1800D98B2
0x1800d9875  mov     rax, [rbp+0A0h+var_30]
0x1800d9879  sub     rax, rdi
0x1800d987c  lfence
0x1800d987f  cmp     rcx, rax
0x1800d9882  jbe     short loc_1800D9897
0x1800d9884  lea     r8, [rsp+1A0h+var_170]
0x1800d9889  mov     rdx, rcx
0x1800d988c  lea     rcx, [rbp+0A0h+pIpAddrTable]
0x1800d9890  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800d9895  jmp     short loc_1800D98AE
0x1800d9897  mov     rbx, [rbp+0A0h+pIpAddrTable]
0x1800d989b  add     rbx, rcx
0x1800d989e  mov     rdx, rbx
0x1800d98a1  mov     rcx, [rbp+0A0h+pIpAddrTable+8]
0x1800d98a5  call    ??$_Zero_range@PEAPEAU?$pair@$$CBV?$shared_ptr@VInBuffer@IAsyncTransport@Dct@Basix@Microsoft@@@std@@V?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@2@@std@@@std@@YAPEAPEAU?$pair@$$CBV?$shared_ptr@VInBuffer@IAsyncTransport@Dct@Basix@Microsoft@@@std@@V?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@2@@0@QEAPEAU10@0@Z; std::_Zero_range<std::pair<std::shared_ptr<Microsoft::Basix::Dct::IAsyncTransport::InBuffer> const,std::chrono::duration<__int64,std::ratio<1,1000>>> * *>(std::pair<std::shared_ptr<Microsoft::Basix::Dct::IAsyncTransport::InBuffer> const,std::chrono::duration<__int64,std::ratio<1,1000>>> * * const,std::pair<std::shared_ptr<Microsoft::Basix::Dct::IAsyncTransport::InBuffer> const,std::chrono::duration<__int64,std::ratio<1,1000>>> * * const)
0x1800d98aa  mov     [rbp+0A0h+pIpAddrTable+8], rbx
0x1800d98ae  mov     rdi, [rbp+0A0h+pIpAddrTable]
0x1800d98b2  xor     r8d, r8d; bOrder
0x1800d98b5  lea     rdx, [rbp+0A0h+pdwSize]; pdwSize
0x1800d98b9  mov     rcx, rdi; pIpAddrTable
0x1800d98bc  call    cs:__imp_GetIpAddrTable
0x1800d98c2  test    eax, eax
0x1800d98c4  jnz     loc_1800D9B06
0x1800d98ca  mov     qword ptr [rbp+0A0h+InterfaceLuid], 0
0x1800d98d2  xorps   xmm0, xmm0
0x1800d98d5  movups  xmmword ptr [rbp+0A0h+InterfaceGuid.Data1], xmm0
0x1800d98d9  mov     edx, [r14+4]
0x1800d98dd  cmp     [rdi], eax
0x1800d98df  jbe     loc_1800D9A1E
0x1800d98e5  lea     rcx, [rdi+4]
0x1800d98e9  cmp     [rcx], edx
0x1800d98eb  jz      short loc_1800D98FD
0x1800d98ed  inc     eax
0x1800d98ef  add     rcx, 18h
0x1800d98f3  cmp     eax, [rdi]
0x1800d98f5  jnb     loc_1800D9A1E
0x1800d98fb  jmp     short loc_1800D98E9
0x1800d98fd  lea     r15, [rax+rax*2]
0x1800d9901  lea     rdx, [rbp+0A0h+InterfaceLuid]; InterfaceLuid
0x1800d9905  mov     ecx, [rdi+r15*8+8]; InterfaceIndex
0x1800d990a  call    cs:__imp_ConvertInterfaceIndexToLuid
0x1800d9910  test    eax, eax
0x1800d9912  jnz     loc_1800D9BB1
0x1800d9918  cmp     qword ptr [rbp+0A0h+InterfaceLuid], 0
0x1800d991d  jz      loc_1800D9A1E
0x1800d9923  lea     rdx, [rbp+0A0h+InterfaceGuid]; InterfaceGuid
0x1800d9927  lea     rcx, [rbp+0A0h+InterfaceLuid]; InterfaceLuid
0x1800d992b  call    cs:__imp_ConvertInterfaceLuidToGuid
0x1800d9931  test    eax, eax
0x1800d9933  jnz     short loc_1800D9975
0x1800d9935  movups  xmm0, xmmword ptr [rbp+0A0h+InterfaceGuid.Data1]
0x1800d9939  movdqu  xmmword ptr [rsi], xmm0
0x1800d993d  lea     rcx, [rbp+0A0h+pIpAddrTable]
0x1800d9941  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800d9946  mov     rax, rsi
0x1800d9949  mov     rcx, [rbp+0A0h+var_18]
0x1800d9950  xor     rcx, rsp; StackCookie
0x1800d9953  call    __security_check_cookie
0x1800d9958  lea     r11, [rsp+1A0h+var_10]
0x1800d9960  mov     rbx, [r11+20h]
0x1800d9964  mov     rsi, [r11+30h]
0x1800d9968  mov     rdi, [r11+38h]
0x1800d996c  mov     rsp, r11
0x1800d996f  pop     r15
0x1800d9971  pop     r14
0x1800d9973  pop     rbp
0x1800d9974  retn
0x1800d9975  lea     rdx, Str1
0x1800d997c  lea     rcx, [rsp+1A0h+var_150]
0x1800d9981  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800d9986  nop
0x1800d9987  lea     rdx, aCW1SRdpnanodll_13; "C:\\__w\\1\\s\\rdpnanodll\\upnp\\upnpma"...
0x1800d998e  lea     rcx, [rbp+0A0h+var_110]
0x1800d9992  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800d9997  nop
0x1800d9998  lea     rdx, aFailedToConver_0; "Failed to convert interface luid to gui"...
0x1800d999f  lea     rcx, [rsp+1A0h+var_130]
0x1800d99a4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800d99a9  nop
0x1800d99aa  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x1800d99af  mov     rbx, rax
0x1800d99b2  lea     rdx, [rbp+0A0h+InterfaceGuid]; InterfaceGuid
0x1800d99b6  lea     rcx, [rbp+0A0h+InterfaceLuid]; InterfaceLuid
0x1800d99ba  call    cs:__imp_ConvertInterfaceLuidToGuid
0x1800d99c0  movzx   edx, ax
0x1800d99c3  or      edx, 80070000h
0x1800d99c9  test    eax, eax
0x1800d99cb  cmovle  edx, eax; int
0x1800d99ce  mov     r8, rbx; struct std::error_category *
0x1800d99d1  lea     rcx, [rbp+0A0h+var_F0]; this
0x1800d99d5  call    ??0error_code@std@@QEAA@HAEBVerror_category@1@@Z; std::error_code::error_code(int,std::error_category const &)
0x1800d99da  movups  xmm0, xmmword ptr [rax]
0x1800d99dd  movdqu  xmmword ptr [rsp+1A0h+var_168+8], xmm0
0x1800d99e3  lea     rax, [rsp+1A0h+var_150]
0x1800d99e8  mov     qword ptr [rsp+1A0h+var_178], rax
0x1800d99ed  mov     [rsp+1A0h+var_180], 80h
0x1800d99f6  lea     r9, [rbp+0A0h+var_110]
0x1800d99fa  lea     r8, [rsp+1A0h+var_130]
0x1800d99ff  lea     rdx, [rsp+1A0h+var_168+8]
0x1800d9a04  lea     rcx, [rbp+0A0h+pExceptionObject]
0x1800d9a08  call    ??0SystemException@Basix@Microsoft@@QEAA@Verror_code@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1_K1@Z; Microsoft::Basix::SystemException::SystemException(std::error_code,std::string const &,std::string const &,unsigned __int64,std::string const &)
0x1800d9a0d  lea     rdx, _TI6?AVSystemException@Basix@Microsoft@@; pThrowInfo
0x1800d9a14  lea     rcx, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x1800d9a18  call    _CxxThrowException
0x1800d9a1e  lea     rdx, aCW1SRdpnanodll_13; "C:\\__w\\1\\s\\rdpnanodll\\upnp\\upnpma"...
0x1800d9a25  lea     rcx, [rsp+1A0h+var_150]
0x1800d9a2a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800d9a2f  nop
0x1800d9a30  lea     rdx, [rbp+0A0h+var_110]
0x1800d9a34  mov     rcx, r14
0x1800d9a37  call    ?ToNumericString@SocketAddress@Dct@Basix@Microsoft@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; Microsoft::Basix::Dct::SocketAddress::ToNumericString(void)
0x1800d9a3c  nop
0x1800d9a3d  mov     r8, rax
0x1800d9a40  lea     rdx, aFailedToFindIn; "Failed to find interface "
0x1800d9a47  lea     rcx, [rsp+1A0h+var_130]
0x1800d9a4c  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBD$$QEAV10@@Z; std::operator+<char>(char const * const,std::string &&)
0x1800d9a51  nop
0x1800d9a52  mov     r9d, 7Fh
0x1800d9a58  lea     r8, [rsp+1A0h+var_150]
0x1800d9a5d  mov     rdx, rax
0x1800d9a60  lea     rcx, [rbp+0A0h+pExceptionObject]
0x1800d9a64  call    ??0Exception@Basix@Microsoft@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0_K@Z; Microsoft::Basix::Exception::Exception(std::string const &,std::string const &,unsigned __int64)
0x1800d9a69  lea     rdx, _TI4?AVException@Basix@Microsoft@@; pThrowInfo
0x1800d9a70  lea     rcx, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x1800d9a74  call    _CxxThrowException
0x1800d9a7a  lea     rdx, Str1
0x1800d9a81  lea     rcx, [rsp+1A0h+var_130]
0x1800d9a86  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800d9a8b  nop
0x1800d9a8c  lea     rdx, aCW1SRdpnanodll_13; "C:\\__w\\1\\s\\rdpnanodll\\upnp\\upnpma"...
0x1800d9a93  lea     rcx, [rbp+0A0h+var_110]
0x1800d9a97  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800d9a9c  nop
0x1800d9a9d  lea     rdx, aFailedToGetIpA; "Failed to get IP address table size"
0x1800d9aa4  lea     rcx, [rsp+1A0h+var_150]
0x1800d9aa9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800d9aae  nop
0x1800d9aaf  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x1800d9ab4  mov     r8, rax; struct std::error_category *
0x1800d9ab7  mov     edx, ebx; int
0x1800d9ab9  lea     rcx, [rbp+0A0h+var_F0]; this
0x1800d9abd  call    ??0error_code@std@@QEAA@HAEBVerror_category@1@@Z; std::error_code::error_code(int,std::error_category const &)
0x1800d9ac2  movups  xmm0, xmmword ptr [rax]
0x1800d9ac5  movdqu  xmmword ptr [rsp+1A0h+var_168+8], xmm0
0x1800d9acb  lea     rax, [rsp+1A0h+var_130]
0x1800d9ad0  mov     qword ptr [rsp+1A0h+var_178], rax
0x1800d9ad5  mov     [rsp+1A0h+var_180], 69h ; 'i'
0x1800d9ade  lea     r9, [rbp+0A0h+var_110]
0x1800d9ae2  lea     r8, [rsp+1A0h+var_150]
0x1800d9ae7  lea     rdx, [rsp+1A0h+var_168+8]
0x1800d9aec  lea     rcx, [rbp+0A0h+pExceptionObject]
0x1800d9af0  call    ??0SystemException@Basix@Microsoft@@QEAA@Verror_code@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1_K1@Z; Microsoft::Basix::SystemException::SystemException(std::error_code,std::string const &,std::string const &,unsigned __int64,std::string const &)
0x1800d9af5  lea     rdx, _TI6?AVSystemException@Basix@Microsoft@@; pThrowInfo
0x1800d9afc  lea     rcx, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x1800d9b00  call    _CxxThrowException
0x1800d9b06  lea     rdx, Str1
0x1800d9b0d  lea     rcx, [rsp+1A0h+var_150]
0x1800d9b12  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800d9b17  nop
0x1800d9b18  lea     rdx, aCW1SRdpnanodll_13; "C:\\__w\\1\\s\\rdpnanodll\\upnp\\upnpma"...
0x1800d9b1f  lea     rcx, [rbp+0A0h+var_110]
0x1800d9b23  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800d9b28  nop
0x1800d9b29  lea     rdx, aFailedToGetIpA_0; "Failed to get IP address table"
0x1800d9b30  lea     rcx, [rsp+1A0h+var_130]
0x1800d9b35  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800d9b3a  nop
0x1800d9b3b  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x1800d9b40  mov     rbx, rax
0x1800d9b43  xor     r8d, r8d; bOrder
0x1800d9b46  lea     rdx, [rbp+0A0h+pdwSize]; pdwSize
0x1800d9b4a  mov     rcx, rdi; pIpAddrTable
0x1800d9b4d  call    cs:__imp_GetIpAddrTable
0x1800d9b53  movzx   edx, ax
0x1800d9b56  or      edx, 80070000h
0x1800d9b5c  test    eax, eax
0x1800d9b5e  cmovle  edx, eax; int
0x1800d9b61  mov     r8, rbx; struct std::error_category *
0x1800d9b64  lea     rcx, [rbp+0A0h+var_F0]; this
0x1800d9b68  call    ??0error_code@std@@QEAA@HAEBVerror_category@1@@Z; std::error_code::error_code(int,std::error_category const &)
0x1800d9b6d  movups  xmm0, xmmword ptr [rax]
0x1800d9b70  movdqu  xmmword ptr [rsp+1A0h+var_168+8], xmm0
0x1800d9b76  lea     rax, [rsp+1A0h+var_150]
0x1800d9b7b  mov     qword ptr [rsp+1A0h+var_178], rax
0x1800d9b80  mov     [rsp+1A0h+var_180], 6Eh ; 'n'
0x1800d9b89  lea     r9, [rbp+0A0h+var_110]
0x1800d9b8d  lea     r8, [rsp+1A0h+var_130]
0x1800d9b92  lea     rdx, [rsp+1A0h+var_168+8]
0x1800d9b97  lea     rcx, [rbp+0A0h+pExceptionObject]
0x1800d9b9b  call    ??0SystemException@Basix@Microsoft@@QEAA@Verror_code@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1_K1@Z; Microsoft::Basix::SystemException::SystemException(std::error_code,std::string const &,std::string const &,unsigned __int64,std::string const &)
0x1800d9ba0  lea     rdx, _TI6?AVSystemException@Basix@Microsoft@@; pThrowInfo
0x1800d9ba7  lea     rcx, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x1800d9bab  call    _CxxThrowException
0x1800d9bb1  lea     rdx, Str1
0x1800d9bb8  lea     rcx, [rsp+1A0h+var_150]
0x1800d9bbd  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800d9bc2  nop
0x1800d9bc3  lea     rdx, aCW1SRdpnanodll_13; "C:\\__w\\1\\s\\rdpnanodll\\upnp\\upnpma"...
0x1800d9bca  lea     rcx, [rbp+0A0h+var_110]
0x1800d9bce  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800d9bd3  nop
0x1800d9bd4  lea     rdx, aFailedToConver_3; "Failed to convert interface index to lu"...
0x1800d9bdb  lea     rcx, [rsp+1A0h+var_130]
0x1800d9be0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800d9be5  nop
0x1800d9be6  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x1800d9beb  mov     rbx, rax
0x1800d9bee  lea     rdx, [rbp+0A0h+InterfaceLuid]; InterfaceLuid
0x1800d9bf2  mov     ecx, [rdi+r15*8+8]; InterfaceIndex
0x1800d9bf7  call    cs:__imp_ConvertInterfaceIndexToLuid
0x1800d9bfd  movzx   edx, ax
0x1800d9c00  or      edx, 80070000h
0x1800d9c06  test    eax, eax
0x1800d9c08  cmovle  edx, eax; int
0x1800d9c0b  mov     r8, rbx; struct std::error_category *
0x1800d9c0e  lea     rcx, [rbp+0A0h+var_F0]; this
0x1800d9c12  call    ??0error_code@std@@QEAA@HAEBVerror_category@1@@Z; std::error_code::error_code(int,std::error_category const &)
0x1800d9c17  movups  xmm0, xmmword ptr [rax]
0x1800d9c1a  movdqu  xmmword ptr [rsp+1A0h+var_168+8], xmm0
0x1800d9c20  lea     rax, [rsp+1A0h+var_150]
0x1800d9c25  mov     qword ptr [rsp+1A0h+var_178], rax
0x1800d9c2a  mov     [rsp+1A0h+var_180], 7Ah ; 'z'
0x1800d9c33  lea     r9, [rbp+0A0h+var_110]
0x1800d9c37  lea     r8, [rsp+1A0h+var_130]
0x1800d9c3c  lea     rdx, [rsp+1A0h+var_168+8]
0x1800d9c41  lea     rcx, [rbp+0A0h+pExceptionObject]
0x1800d9c45  call    ??0SystemException@Basix@Microsoft@@QEAA@Verror_code@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1_K1@Z; Microsoft::Basix::SystemException::SystemException(std::error_code,std::string const &,std::string const &,unsigned __int64,std::string const &)
0x1800d9c4a  lea     rdx, _TI6?AVSystemException@Basix@Microsoft@@; pThrowInfo
0x1800d9c51  lea     rcx, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x1800d9c55  call    _CxxThrowException
```
