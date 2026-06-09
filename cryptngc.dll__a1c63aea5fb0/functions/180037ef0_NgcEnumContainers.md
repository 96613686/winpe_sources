# NgcEnumContainers

- ea: `0x180037ef0`
- end: `0x1800382d8`
- name: `NgcEnumContainers`
- size: `1000`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800368c8`
- `0x1800384e0`

## callees

- `0x1800065c0`
- `0x18000eb30`
- `0x18000f730`
- `0x1800158e0`
- `0x1800159a0`
- `0x180015a04`
- `0x180018348`
- `0x180018790`
- `0x180019fd8`
- `0x18001a36c`
- `0x180024b70`
- `0x18002b31c`
- `0x180032fcc`
- `0x180036b04`
- `0x180036b24`
- `0x180037ef0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800381d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800381d5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180037faf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180037faf`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180038040`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180038040`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180037f7c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180037f7c`

## string_xrefs

- `0x180037f8e`: `onecore\ds\security\ngc\cryptngc\dll\ngcpinmanagement.cpp`
- `0x180038071`: `onecore\ds\security\ngc\cryptngc\dll\ngcpinmanagement.cpp`

## pseudocode

```c
__int64 __fastcall NgcEnumContainers(const WCHAR *a1, _QWORD *a2, _QWORD *a3)
{
  _QWORD *v5; // r9
  bool v6; // zf
  int v7; // ebx
  const char *v8; // r9
  _QWORD *v9; // rax
  int v10; // eax
  DWORD LengthSid; // eax
  int LogonCredsAvailableRegState; // eax
  __int64 v14; // rcx
  __int64 v15; // r15
  __int64 v16; // r14
  __int64 v17; // r10
  char *v18; // rsi
  const unsigned __int16 *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rcx
  unsigned __int64 v22; // r10
  _OWORD *v23; // rdi
  unsigned __int16 *v24; // rcx
  __int64 *v25; // rcx
  __int128 v26; // xmm0
  _QWORD *v27; // rax
  int *v28; // rdx
  int v29; // [rsp+20h] [rbp-60h]
  unsigned int v30; // [rsp+28h] [rbp-58h]
  PSID Sid[2]; // [rsp+30h] [rbp-50h] BYREF
  _QWORD *v32; // [rsp+40h] [rbp-40h] BYREF
  _QWORD v33[2]; // [rsp+48h] [rbp-38h] BYREF
  __int16 v34; // [rsp+58h] [rbp-28h]
  _BYTE v35[32]; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  const WCHAR *v37; // [rsp+C0h] [rbp+40h] BYREF
  bool v38; // [rsp+C8h] [rbp+48h] BYREF
  HLOCAL hMem; // [rsp+D8h] [rbp+58h] BYREF

  v37 = a1;
  if ( !a2 || !a3 )
    return 2148073511LL;
  *a2 = 0;
  v5 = (_QWORD *)*a3;
  v6 = *a3 == 0;
  v33[0] = &v38;
  v32 = v5;
  v38 = v6;
  v33[1] = &v32;
  v34 = 256;
  if ( v5 )
  {
    if ( *(_DWORD *)v5 != -990845000 )
    {
      v7 = -2146893785;
LABEL_20:
      wil::details::ScopeExitFnGuard__lambda_2b9790504d3d836b73999d924640ead9___::operator()(v33);
      return (unsigned int)v7;
    }
    v7 = 0;
LABEL_22:
    v14 = *((unsigned int *)v5 + 5);
    if ( (unsigned int)v14 < *((_DWORD *)v5 + 4) )
    {
      v15 = v5[1];
      v16 = 5 * v14;
      *((_DWORD *)v5 + 5) = v14 + 1;
      v17 = 64;
      hMem = 0;
      v18 = 0;
      v19 = *(const unsigned __int16 **)(v15 + 40 * v14 + 16);
      if ( v19 )
      {
        v7 = StringCbLengthW(v19, 0x1FEu, (unsigned __int64 *)&hMem);
        if ( v7 < 0 )
        {
          if ( (unsigned int)dword_18006E000 > 2 )
          {
            LODWORD(hMem) = v7;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              (unsigned int)&dword_18006E000,
              (unsigned int)word_18005FE4A,
              0,
              0,
              (__int64)&hMem);
          }
          goto LABEL_20;
        }
        v18 = (char *)hMem + 2;
        if ( (unsigned __int64)hMem + 66 < v22 )
          SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v21, v20);
        v17 = (__int64)hMem + 66;
      }
      wil::make_unique_hlocal_nothrow<unsigned char [0]>(&hMem, v17);
      v23 = hMem;
      if ( hMem )
      {
        v24 = (unsigned __int16 *)((char *)hMem + 64);
        if ( *(_QWORD *)(v15 + 8 * v16 + 16)
          && (*((_QWORD *)hMem + 3) = v24,
              v7 = StringCbCopyExW(
                     v24,
                     (unsigned __int64)v18,
                     *(const unsigned __int16 **)(v15 + 8 * v16 + 16),
                     (unsigned __int16 **)Sid,
                     (unsigned __int64 *)&hMem,
                     v30),
              v7 < 0) )
        {
          if ( (unsigned int)dword_18006E000 > 2 )
          {
            LODWORD(hMem) = v7;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              (unsigned int)&dword_18006E000,
              (unsigned int)byte_18005FDD3,
              0,
              0,
              (__int64)&hMem);
          }
          LocalFree(v23);
        }
        else
        {
          *((_QWORD *)v23 + 4) = 0;
          *((_QWORD *)v23 + 5) = 0;
          *((_QWORD *)v23 + 6) = 0;
          *((_DWORD *)v23 + 14) = *(_DWORD *)(v15 + 8 * v16 + 28);
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl'::`2'::impl) )
          {
            v25 = qword_180056F70;
            do
            {
              if ( (*(_DWORD *)v25 & *(_DWORD *)(v15 + 8 * v16 + 24)) != 0 )
                *((_DWORD *)v23 + 15) |= *((_DWORD *)v25 + 1);
              ++v25;
            }
            while ( v25 != qword_180056FA0 );
          }
          v26 = *(_OWORD *)(v15 + 8 * v16);
          HIBYTE(v34) = 0;
          *v23 = v26;
          *((_DWORD *)v23 + 4) = *(_DWORD *)(v15 + 8 * v16 + 32);
          v27 = v32;
          *a2 = v23;
          *a3 = v27;
        }
        goto LABEL_20;
      }
      if ( (unsigned int)dword_18006E000 <= 2 )
        goto LABEL_46;
      v28 = &dword_18005FE04;
      goto LABEL_45;
    }
LABEL_19:
    v7 = -2146893782;
    goto LABEL_20;
  }
  if ( a1 )
  {
    Sid[0] = 0;
    if ( ConvertStringSidToSidW(a1, Sid) )
    {
      LengthSid = GetLengthSid(Sid[0]);
      std::vector<unsigned char>::vector<unsigned char>(v35, Sid[0], (char *)Sid[0] + LengthSid);
      LODWORD(hMem) = 0;
      LogonCredsAvailableRegState = NgcUtils::QueryLogonCredsAvailableRegState((__int64)v35, (unsigned int *)&hMem);
      if ( LogonCredsAvailableRegState >= 0 )
      {
        std::vector<unsigned char>::_Tidy(v35);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(Sid);
        if ( (_DWORD)hMem != 2 )
          goto LABEL_19;
        goto LABEL_11;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x384,
        (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcpinmanagement.cpp",
        (const char *)(unsigned int)LogonCredsAvailableRegState,
        v29);
      std::vector<unsigned char>::_Tidy(v35);
    }
    else
    {
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x379,
        (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcpinmanagement.cpp",
        v8);
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(Sid);
  }
LABEL_11:
  v9 = LocalAlloc(0, 0x18u);
  if ( !v9 )
  {
    v32 = 0;
    if ( (unsigned int)dword_18006E000 <= 2 )
    {
LABEL_46:
      v7 = -2146893810;
      goto LABEL_20;
    }
    v28 = (int *)byte_18005FEB3;
LABEL_45:
    LODWORD(hMem) = -2146893810;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18006E000,
      (_DWORD)v28,
      0,
      0,
      (__int64)&hMem);
    goto LABEL_46;
  }
  *(_OWORD *)v9 = 0;
  v9[2] = 0;
  v32 = v9;
  *(_DWORD *)v9 = -990845000;
  Sid[0] = &v37;
  Sid[1] = &v32;
  v10 = HResultErrorContract__lambda_9132ae26d942fa36fac3f8bb36e2b605_(Sid);
  v7 = v10;
  if ( v10 >= 0 )
  {
    v5 = v32;
    goto LABEL_22;
  }
  if ( (unsigned int)dword_18006E000 > 2 )
  {
    LODWORD(hMem) = v10;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18006E000,
      (unsigned int)&word_18005FE86,
      0,
      0,
      (__int64)&hMem);
  }
  wil::details::ScopeExitFnGuard__lambda_2b9790504d3d836b73999d924640ead9___::operator()(v33);
  return HResultToSecurityStatus(v7);
}

```

## disassembly

```asm
0x180037ef0  mov     [rsp-38h+arg_10], rbx
0x180037ef5  mov     [rsp-38h+arg_0], rcx
0x180037efa  push    rbp
0x180037efb  push    rsi
0x180037efc  push    rdi
0x180037efd  push    r12
0x180037eff  push    r13
0x180037f01  push    r14
0x180037f03  push    r15
0x180037f05  mov     rbp, rsp
0x180037f08  sub     rsp, 80h
0x180037f0f  xor     edi, edi
0x180037f11  mov     r12, r8
0x180037f14  mov     r13, rdx
0x180037f17  test    rdx, rdx
0x180037f1a  jz      loc_1800382B2
0x180037f20  test    r8, r8
0x180037f23  jz      loc_1800382B2
0x180037f29  lea     rax, [rbp+arg_8]
0x180037f2d  mov     [rdx], rdi
0x180037f30  mov     r9, [r8]
0x180037f33  test    r9, r9
0x180037f36  mov     [rbp+var_38], rax
0x180037f3a  lea     rax, [rbp+var_40]
0x180037f3e  mov     [rbp+var_40], r9
0x180037f42  setz    [rbp+arg_8]
0x180037f46  mov     [rbp+var_30], rax
0x180037f4a  mov     [rbp+var_28], 100h
0x180037f50  test    r9, r9
0x180037f53  jz      short loc_180037F6F
0x180037f55  cmp     dword ptr [r9], 0C4F0E7B8h
0x180037f5c  jz      short loc_180037F68
0x180037f5e  mov     ebx, 80090027h
0x180037f63  jmp     loc_1800380B4
0x180037f68  mov     ebx, edi
0x180037f6a  jmp     loc_1800380C8
0x180037f6f  test    rcx, rcx
0x180037f72  jz      short loc_180037FA8
0x180037f74  lea     rdx, [rbp+Sid]; Sid
0x180037f78  mov     [rbp+Sid], rdi
0x180037f7c  call    cs:__imp_ConvertStringSidToSidW
0x180037f82  test    eax, eax
0x180037f84  jnz     loc_18003803C
0x180037f8a  mov     rcx, [rbp+38h]; this
0x180037f8e  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180037f95  mov     edx, 379h; void *
0x180037f9a  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180037f9f  lea     rcx, [rbp+Sid]; void *
0x180037fa3  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180037fa8  mov     edx, 18h; uBytes
0x180037fad  xor     ecx, ecx; uFlags
0x180037faf  call    cs:__imp_LocalAlloc
0x180037fb5  test    rax, rax
0x180037fb8  jz      loc_180038270
0x180037fbe  xor     ecx, ecx
0x180037fc0  xorps   xmm0, xmm0
0x180037fc3  movups  xmmword ptr [rax], xmm0
0x180037fc6  mov     [rax+10h], rcx
0x180037fca  lea     rcx, [rbp+Sid]
0x180037fce  mov     [rbp+var_40], rax
0x180037fd2  mov     dword ptr [rax], 0C4F0E7B8h
0x180037fd8  lea     rax, [rbp+arg_0]
0x180037fdc  mov     [rbp+Sid], rax
0x180037fe0  lea     rax, [rbp+var_40]
0x180037fe4  mov     [rbp+var_48], rax
0x180037fe8  call    HResultErrorContract__lambda_9132ae26d942fa36fac3f8bb36e2b605___; HResultErrorContract__lambda_9132ae26d942fa36fac3f8bb36e2b605_
0x180037fed  mov     ebx, eax
0x180037fef  test    eax, eax
0x180037ff1  jns     loc_1800380C4
0x180037ff7  mov     ecx, cs:dword_18006E000
0x180037ffd  cmp     ecx, 2
0x180038000  jbe     short loc_180038027
0x180038002  mov     dword ptr [rbp+hMem], eax
0x180038005  lea     rdx, word_18005FE86
0x18003800c  lea     rax, [rbp+hMem]
0x180038010  xor     r9d, r9d
0x180038013  xor     r8d, r8d
0x180038016  mov     [rsp+80h+var_60], rax
0x18003801b  lea     rcx, dword_18006E000
0x180038022  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180038027  lea     rcx, [rbp+var_38]
0x18003802b  call    wil__details__ScopeExitFnGuard__lambda_2b9790504d3d836b73999d924640ead9_____operator__
0x180038030  mov     ecx, ebx; int
0x180038032  call    ?HResultToSecurityStatus@@YAJJ@Z; HResultToSecurityStatus(long)
0x180038037  jmp     loc_1800382B7
0x18003803c  mov     rcx, [rbp+Sid]; pSid
0x180038040  call    cs:__imp_GetLengthSid
0x180038046  mov     rdx, [rbp+Sid]
0x18003804a  lea     rcx, [rbp+var_20]
0x18003804e  mov     r8d, eax
0x180038051  add     r8, rdx
0x180038054  call    ??$?0PEAE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEAE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar *,uchar *,std::allocator<uchar> const &)
0x180038059  lea     rdx, [rbp+hMem]
0x18003805d  mov     dword ptr [rbp+hMem], edi
0x180038060  lea     rcx, [rbp+var_20]
0x180038064  call    ?QueryLogonCredsAvailableRegState@NgcUtils@@YAJAEBV?$vector@EV?$allocator@E@std@@@std@@PEAW4LogonCredsAvailableRegState@1@@Z; NgcUtils::QueryLogonCredsAvailableRegState(std::vector<uchar> const &,NgcUtils::LogonCredsAvailableRegState *)
0x180038069  test    eax, eax
0x18003806b  jns     short loc_180038093
0x18003806d  mov     rcx, [rbp+38h]; this
0x180038071  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180038078  mov     r9d, eax; char *
0x18003807b  mov     edx, 384h; void *
0x180038080  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180038085  lea     rcx, [rbp+var_20]
0x180038089  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18003808e  jmp     loc_180037F9F
0x180038093  lea     rcx, [rbp+var_20]
0x180038097  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18003809c  lea     rcx, [rbp+Sid]; void *
0x1800380a0  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800380a5  cmp     dword ptr [rbp+hMem], 2
0x1800380a9  jz      loc_180037FA8
0x1800380af  mov     ebx, 8009002Ah
0x1800380b4  lea     rcx, [rbp+var_38]
0x1800380b8  call    wil__details__ScopeExitFnGuard__lambda_2b9790504d3d836b73999d924640ead9_____operator__
0x1800380bd  mov     eax, ebx
0x1800380bf  jmp     loc_1800382B7
0x1800380c4  mov     r9, [rbp+var_40]
0x1800380c8  mov     ecx, [r9+14h]
0x1800380cc  cmp     ecx, [r9+10h]
0x1800380d0  jnb     short loc_1800380AF
0x1800380d2  mov     r15, [r9+8]
0x1800380d6  lea     eax, [rcx+1]
0x1800380d9  lea     r14, [rcx+rcx*4]
0x1800380dd  mov     [r9+14h], eax
0x1800380e1  mov     r10d, 40h ; '@'
0x1800380e7  mov     [rbp+hMem], rdi
0x1800380eb  mov     rsi, rdi
0x1800380ee  mov     rcx, [r15+r14*8+10h]; unsigned __int16 *
0x1800380f3  test    rcx, rcx
0x1800380f6  jz      short loc_180038159
0x1800380f8  lea     r8, [rbp+hMem]; unsigned __int64 *
0x1800380fc  mov     edx, 1FEh; unsigned __int64
0x180038101  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180038106  mov     ebx, eax
0x180038108  test    eax, eax
0x18003810a  jns     short loc_180038141
0x18003810c  mov     eax, cs:dword_18006E000
0x180038112  cmp     eax, 2
0x180038115  jbe     short loc_1800380B4
0x180038117  lea     rax, [rbp+hMem]
0x18003811b  mov     dword ptr [rbp+hMem], ebx
0x18003811e  xor     r9d, r9d
0x180038121  mov     [rsp+80h+var_60], rax
0x180038126  xor     r8d, r8d
0x180038129  lea     rdx, word_18005FE4A
0x180038130  lea     rcx, dword_18006E000
0x180038137  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003813c  jmp     loc_1800380B4
0x180038141  mov     rsi, [rbp+hMem]
0x180038145  add     rsi, 2
0x180038149  lea     rax, [rsi+40h]
0x18003814d  cmp     rax, r10
0x180038150  jb      loc_1800382D2
0x180038156  mov     r10, rax
0x180038159  mov     rdx, r10
0x18003815c  lea     rcx, [rbp+hMem]
0x180038160  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x180038165  mov     rdi, [rbp+hMem]
0x180038169  test    rdi, rdi
0x18003816c  jz      loc_18003825C
0x180038172  cmp     qword ptr [r15+r14*8+10h], 0
0x180038178  lea     rcx, [rdi+40h]; unsigned __int16 *
0x18003817c  jz      short loc_1800381E0
0x18003817e  mov     [rdi+18h], rcx
0x180038182  lea     rax, [rbp+hMem]
0x180038186  mov     r8, [r15+r14*8+10h]; unsigned __int16 *
0x18003818b  lea     r9, [rbp+Sid]; unsigned __int16 **
0x18003818f  mov     rdx, rsi; unsigned __int64
0x180038192  mov     [rsp+80h+var_60], rax; unsigned __int64 *
0x180038197  call    ?StringCbCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCbCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18003819c  mov     ebx, eax
0x18003819e  test    eax, eax
0x1800381a0  jns     short loc_1800381E0
0x1800381a2  mov     eax, cs:dword_18006E000
0x1800381a8  cmp     eax, 2
0x1800381ab  jbe     short loc_1800381D2
0x1800381ad  lea     rax, [rbp+hMem]
0x1800381b1  mov     dword ptr [rbp+hMem], ebx
0x1800381b4  xor     r9d, r9d
0x1800381b7  mov     [rsp+80h+var_60], rax
0x1800381bc  xor     r8d, r8d
0x1800381bf  lea     rdx, byte_18005FDD3
0x1800381c6  lea     rcx, dword_18006E000
0x1800381cd  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800381d2  mov     rcx, rdi; hMem
0x1800381d5  call    cs:__imp_LocalFree
0x1800381db  jmp     loc_1800380B4
0x1800381e0  mov     qword ptr [rdi+20h], 0
0x1800381e8  mov     qword ptr [rdi+28h], 0
0x1800381f0  mov     qword ptr [rdi+30h], 0
0x1800381f8  mov     eax, [r15+r14*8+1Ch]
0x1800381fd  mov     [rdi+38h], eax
0x180038200  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EssFprPeripherals@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals> `wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl(void)'::`2'::impl
0x180038207  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(void)
0x18003820c  test    al, al
0x18003820e  jz      short loc_180038236
0x180038210  lea     rcx, qword_180056F70
0x180038217  mov     eax, [rcx]
0x180038219  test    [r15+r14*8+18h], eax
0x18003821e  jz      short loc_180038226
0x180038220  mov     eax, [rcx+4]
0x180038223  or      [rdi+3Ch], eax
0x180038226  add     rcx, 8
0x18003822a  lea     rax, qword_180056FA0
0x180038231  cmp     rcx, rax
0x180038234  jnz     short loc_180038217
0x180038236  movups  xmm0, xmmword ptr [r15+r14*8]
0x18003823b  mov     byte ptr [rbp+var_28+1], 0
0x18003823f  movdqu  xmmword ptr [rdi], xmm0
0x180038243  mov     eax, [r15+r14*8+20h]
0x180038248  mov     [rdi+10h], eax
0x18003824b  mov     rax, [rbp+var_40]
0x18003824f  mov     [r13+0], rdi
0x180038253  mov     [r12], rax
0x180038257  jmp     loc_1800380B4
0x18003825c  mov     eax, cs:dword_18006E000
0x180038262  cmp     eax, 2
0x180038265  jbe     short loc_1800382A8
0x180038267  lea     rdx, dword_18005FE04
0x18003826e  jmp     short loc_180038286
0x180038270  mov     [rbp+var_40], rax
0x180038274  mov     eax, cs:dword_18006E000
0x18003827a  cmp     eax, 2
0x18003827d  jbe     short loc_1800382A8
0x18003827f  lea     rdx, byte_18005FEB3
0x180038286  lea     rax, [rbp+hMem]
0x18003828a  mov     [rsp+80h+var_60], rax
0x18003828f  xor     r9d, r9d
0x180038292  mov     dword ptr [rbp+hMem], 8009000Eh
0x180038299  xor     r8d, r8d
0x18003829c  lea     rcx, dword_18006E000
0x1800382a3  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800382a8  mov     ebx, 8009000Eh
0x1800382ad  jmp     loc_1800380B4
0x1800382b2  mov     eax, 80090027h
0x1800382b7  mov     rbx, [rsp+80h+arg_10]
0x1800382bf  add     rsp, 80h
0x1800382c6  pop     r15
0x1800382c8  pop     r14
0x1800382ca  pop     r13
0x1800382cc  pop     r12
0x1800382ce  pop     rdi
0x1800382cf  pop     rsi
0x1800382d0  pop     rbp
0x1800382d1  retn
0x1800382d2  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
```
