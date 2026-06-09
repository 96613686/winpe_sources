# OfficeExtension::ServerRuntime::Utility::ConvertJsonValueToVariant(Mso::Json::value &)

- ea: `0x1804e56c0`
- end: `0x1804e5a86`
- name: `?ConvertJsonValueToVariant@Utility@ServerRuntime@OfficeExtension@@YA?AVVariantHolder@Mso@@AEAVvalue@Json@5@@Z`
- size: `966`
- prototype: ``
- caller_count: `7`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1804e3f00`
- `0x1804e56c0`
- `0x1804e9380`
- `0x180fc3ca4`
- `0x180fc7050`
- `0x180fc7534`
- `0x180fc8da4`

## callees

- `0x1800581b0`
- `0x1802b0cb8`
- `0x1802e3f10`
- `0x1802e50d0`
- `0x1802e5170`
- `0x1802e5190`
- `0x180327644`
- `0x1804dd9a8`
- `0x1804dda90`
- `0x1804e3368`
- `0x1804e36f8`
- `0x1804e3a60`
- `0x1804e56c0`
- `0x1804e7070`
- `0x1804e9790`
- `0x1805e6dc0`
- `0x1808d3fa4`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1804e5708`
- `OLEAUT32!__imp_VariantInit` at `0x1804e5943`
- `OLEAUT32!__imp_VariantInit` at `0x1804e5708`
- `OLEAUT32!__imp_VariantInit` at `0x1804e5943`
- `OLEAUT32!__imp_VariantClear` at `0x1804e5963`
- `OLEAUT32!__imp_VariantClear` at `0x1804e598b`
- `OLEAUT32!__imp_VariantClear` at `0x1804e5963`
- `OLEAUT32!__imp_VariantClear` at `0x1804e598b`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1804e58d2`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1804e58d2`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1804e59bb`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1804e59bb`
- `Mso20Win32Client!__imp_??0value@Json@Mso@@QEAA@$$QEAV012@@Z` at `0x1804e57cb`
- `Mso20Win32Client!__imp_??0value@Json@Mso@@QEAA@$$QEAV012@@Z` at `0x1804e57cb`
- `Mso20Win32Client!__imp_?as_double@value@Json@Mso@@QEBANXZ` at `0x1804e5883`
- `Mso20Win32Client!__imp_?as_double@value@Json@Mso@@QEBANXZ` at `0x1804e5883`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x1804e5a67`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x1804e5a75`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x1804e5a67`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x1804e5a75`
- `Mso20Win32Client!__imp_?as_bool@value@Json@Mso@@QEBA_NXZ` at `0x1804e5840`
- `Mso20Win32Client!__imp_?as_bool@value@Json@Mso@@QEBA_NXZ` at `0x1804e5840`
- `Mso20Win32Client!__imp_?as_integer@value@Json@Mso@@QEBAHXZ` at `0x1804e5864`
- `Mso20Win32Client!__imp_?as_integer@value@Json@Mso@@QEBAHXZ` at `0x1804e5864`
- `Mso20Win32Client!__imp_?type@value@Json@Mso@@QEBA?AW4value_type@123@XZ` at `0x1804e571a`
- `Mso20Win32Client!__imp_?type@value@Json@Mso@@QEBA?AW4value_type@123@XZ` at `0x1804e571a`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x1804e5a3b`
- `Mso20Win32Client!__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z` at `0x1804e5a3b`
- `Mso20Win32Client!__imp_?as_string@value@Json@Mso@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ` at `0x1804e5742`
- `Mso20Win32Client!__imp_?as_string@value@Json@Mso@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ` at `0x1804e5742`

## pseudocode

```c
VARIANTARG *__fastcall OfficeExtension::ServerRuntime::Utility::ConvertJsonValueToVariant(
        VARIANTARG *a1,
        Mso::Json::value *a2)
{
  SAFEARRAY *v4; // rdi
  struct Mso::VariantHolder *v5; // rdx
  int v6; // ecx
  int v7; // r9d
  int v8; // ecx
  int v9; // ecx
  const wchar_t *v10; // r8
  struct Mso::VariantHolder *v11; // rdx
  int v13; // ecx
  unsigned __int64 v14; // rdx
  unsigned int v15; // r8d
  void *v16; // rax
  struct Mso::VariantHolder *v17; // rdx
  __int64 v18; // rbx
  struct Mso::VariantHolder *v19; // rdx
  bool v20; // r8
  LONG v21; // ebx
  struct Mso::VariantHolder *v22; // rdx
  double v23; // xmm6_8
  struct Mso::VariantHolder *v24; // rdx
  int v25; // ecx
  SAFEARRAY *v26; // rax
  struct Mso::VariantHolder *v27; // rdx
  __int64 v28; // rsi
  __int64 v29; // r15
  __int128 v30; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  HRESULT v32; // eax
  __int64 v33; // rax
  HRESULT v34; // eax
  SAFEARRAYBOUND rgsabound; // [rsp+30h] [rbp-D0h] BYREF
  int v36; // [rsp+38h] [rbp-C8h]
  VARIANTARG v37; // [rsp+40h] [rbp-C0h] BYREF
  SAFEARRAY *psa; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v39; // [rsp+60h] [rbp-A0h]
  VARIANTARG *v40; // [rsp+68h] [rbp-98h]
  SAFEARRAY *v41; // [rsp+70h] [rbp-90h]
  _BYTE pvarg[32]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v43; // [rsp+98h] [rbp-68h]
  _BYTE pExceptionObject[144]; // [rsp+B0h] [rbp-50h] BYREF

  v40 = a1;
  VariantInit(a1);
  LODWORD(v4) = 1;
  v36 = 1;
  v6 = Mso::Json::value::type(a2);
  if ( v6 )
  {
    v8 = v6 - 1;
    if ( v8 )
    {
      v9 = v8 - 1;
      if ( v9 )
      {
        v13 = v9 - 1;
        if ( v13 )
        {
          v25 = v13 - 1;
          if ( v25 )
          {
            if ( v25 != 1 )
            {
              rgsabound.cElements = -2147024809;
              Mso::Logging::MsoSendTraceTag<long>(
                36467780,
                (_DWORD)v5,
                15,
                v7,
                (__int64)L"RichApiException 0x%x",
                &rgsabound);
              OfficeExtension::ServerRuntime::RichApiException::RichApiException(
                (OfficeExtension::ServerRuntime::RichApiException *)pExceptionObject,
                rgsabound.cElements);
              throw (OfficeExtension::ServerRuntime::RichApiException *)pExceptionObject;
            }
            OfficeExtension::ServerRuntime::VariantHolderExtension::Clear(
              (OfficeExtension::ServerRuntime::VariantHolderExtension *)a1,
              v5);
          }
          else
          {
            OfficeExtension::ServerRuntime::VariantHolderExtension::Clear(
              (OfficeExtension::ServerRuntime::VariantHolderExtension *)a1,
              v5);
            rgsabound.cElements = Mso::Json::value::size(a2);
            rgsabound.lLbound = 0;
            v26 = SafeArrayCreate(0xCu, 1u, &rgsabound);
            v4 = v26;
            v41 = v26;
            if ( !v26 )
            {
              Mso::Logging::MsoSendTraceTag(36467779, 1251, 15, L"RichApiException false");
              OfficeExtension::ServerRuntime::RichApiException::RichApiException(
                (OfficeExtension::ServerRuntime::RichApiException *)pExceptionObject,
                -2147024882);
              throw (OfficeExtension::ServerRuntime::RichApiException *)pExceptionObject;
            }
            Mso::TSafeArrayLocker<tagVARIANT>::TSafeArrayLocker<tagVARIANT>(&psa, v26);
            v18 = *(_QWORD *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)a2 + 8LL))(*(_QWORD *)a2);
            v28 = *(_QWORD *)((*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)a2 + 8LL))(*(_QWORD *)a2) + 8);
            v29 = 0;
            while ( v18 != v28 )
            {
              OfficeExtension::ServerRuntime::Utility::ConvertJsonValueToVariant(&v37, v18 + 8);
              v30 = *(_OWORD *)&v37.vt;
              pRecInfo = v37.pRecInfo;
              VariantInit((VARIANTARG *)pvarg);
              v37 = *(VARIANTARG *)pvarg;
              v32 = VariantClear((VARIANTARG *)pvarg);
              if ( v32 < 0 )
                goto LABEL_34;
              v33 = v39;
              *(_OWORD *)(v29 + v39) = v30;
              *(_QWORD *)(v29 + v33 + 16) = pRecInfo;
              v29 += 24;
              v34 = VariantClear(&v37);
              if ( v34 < 0 )
              {
                CrashWithRecoveryHrTag(v34, 0x1F7A008Du);
LABEL_34:
                CrashWithRecoveryHrTag(v32, 0x1F7A008Du);
                goto LABEL_35;
              }
              v18 += 16;
            }
            OfficeExtension::ServerRuntime::VariantHolderExtension::Clear(
              (OfficeExtension::ServerRuntime::VariantHolderExtension *)a1,
              v27);
            a1->vt = 8204;
            a1->llVal = (LONGLONG)v4;
            if ( psa )
              SafeArrayUnaccessData(psa);
          }
        }
        else
        {
          Mso::Json::value::value(&pvarg[8], a2);
          *(_OWORD *)&pvarg[16] = 0;
          v43 = 0;
          HIWORD(v43) = 0;
          pvarg[0] = 0;
          v16 = Mso::Memory::Throw::AllocateEx((Mso::Memory::Throw *)0x50, v14, v15);
          if ( v16 )
            v18 = OfficeExtension::ServerRuntime::ComplexTypeValue::ComplexTypeValue(v16, pvarg);
          else
            v18 = 0;
          if ( v18 )
LABEL_35:
            _InterlockedAdd((volatile signed __int32 *)(v18 + 72), (unsigned int)v4);
          OfficeExtension::ServerRuntime::VariantHolderExtension::Clear(
            (OfficeExtension::ServerRuntime::VariantHolderExtension *)a1,
            v17);
          a1->vt = 13;
          a1->llVal = v18;
          std::shared_ptr<xpsrdr::SourceColorBitmap>::~shared_ptr<xpsrdr::SourceColorBitmap>(&pvarg[16]);
          std::unique_ptr<Mso::Json::details::_Value>::~unique_ptr<Mso::Json::details::_Value>(&pvarg[8]);
        }
      }
      else
      {
        Mso::Json::value::as_string(a2, pvarg);
        v11 = (struct Mso::VariantHolder *)pvarg;
        if ( *(_QWORD *)&pvarg[24] > 7u )
          v11 = *(struct Mso::VariantHolder **)pvarg;
        OfficeExtension::ServerRuntime::VariantHolderExtension::SetString(
          (OfficeExtension::ServerRuntime::VariantHolderExtension *)a1,
          v11,
          v10);
        if ( *(_QWORD *)&pvarg[24] > 7u )
          std::_Deallocate<16>(*(_QWORD *)pvarg, 2LL * *(_QWORD *)&pvarg[24] + 2);
      }
    }
    else
    {
      LOBYTE(v19) = Mso::Json::value::as_bool(a2);
      OfficeExtension::ServerRuntime::VariantHolderExtension::SetBool(
        (OfficeExtension::ServerRuntime::VariantHolderExtension *)a1,
        v19,
        v20);
    }
  }
  else if ( (unsigned __int8)sub_1804E9790(a2) )
  {
    v21 = Mso::Json::value::as_integer(a2);
    OfficeExtension::ServerRuntime::VariantHolderExtension::Clear(
      (OfficeExtension::ServerRuntime::VariantHolderExtension *)a1,
      v22);
    a1->vt = 3;
    a1->lVal = v21;
  }
  else
  {
    v23 = Mso::Json::value::as_double(a2);
    OfficeExtension::ServerRuntime::VariantHolderExtension::Clear(
      (OfficeExtension::ServerRuntime::VariantHolderExtension *)a1,
      v24);
    a1->vt = 5;
    a1->dblVal = v23;
  }
  return a1;
}

```

## disassembly

```asm
0x1804e56c0  mov     rax, rsp
0x1804e56c3  mov     [rax+18h], rbx
0x1804e56c7  mov     [rax+20h], rsi
0x1804e56cb  push    rbp
0x1804e56cc  push    rdi
0x1804e56cd  push    r12
0x1804e56cf  push    r14
0x1804e56d1  push    r15
0x1804e56d3  lea     rbp, [rsp-70h]
0x1804e56d8  sub     rsp, 170h
0x1804e56df  movaps  xmmword ptr [rax-38h], xmm6
0x1804e56e3  movaps  xmmword ptr [rax-48h], xmm7
0x1804e56e7  mov     rax, cs:__security_cookie
0x1804e56ee  xor     rax, rsp
0x1804e56f1  mov     [rbp+90h+var_50], rax
0x1804e56f5  mov     rsi, rdx
0x1804e56f8  mov     r14, rcx
0x1804e56fb  mov     [rsp+190h+var_128], rcx
0x1804e5700  xor     r12d, r12d
0x1804e5703  mov     [rsp+190h+var_158], r12d
0x1804e5708  call    cs:__imp_VariantInit
0x1804e570e  lea     edi, [r12+1]
0x1804e5713  mov     [rsp+190h+var_158], edi
0x1804e5717  mov     rcx, rsi
0x1804e571a  call    cs:__imp_?type@value@Json@Mso@@QEBA?AW4value_type@123@XZ; Mso::Json::value::type(void)
0x1804e5720  mov     ecx, eax
0x1804e5722  test    eax, eax
0x1804e5724  jz      loc_1804E5855
0x1804e572a  sub     ecx, edi
0x1804e572c  jz      loc_1804E583D
0x1804e5732  sub     ecx, edi
0x1804e5734  jnz     loc_1804E57B7
0x1804e573a  lea     rdx, [rsp+190h+pvarg]
0x1804e573f  mov     rcx, rsi
0x1804e5742  call    cs:__imp_?as_string@value@Json@Mso@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; Mso::Json::value::as_string(void)
0x1804e5748  lea     rdx, [rsp+190h+pvarg]
0x1804e574d  cmp     qword ptr [rbp+90h+pvarg+18h], 7
0x1804e5752  cmova   rdx, qword ptr [rsp+190h+pvarg]; struct Mso::VariantHolder *
0x1804e5758  mov     rcx, r14; this
0x1804e575b  nop     dword ptr [rax+rax+00h]
0x1804e5760  call    ?SetString@VariantHolderExtension@ServerRuntime@OfficeExtension@@YAXAEAVVariantHolder@Mso@@PEB_W@Z; OfficeExtension::ServerRuntime::VariantHolderExtension::SetString(Mso::VariantHolder &,wchar_t const *)
0x1804e5765  mov     rdx, qword ptr [rbp+90h+pvarg+18h]
0x1804e5769  cmp     rdx, 7
0x1804e576d  jbe     short loc_1804E5782
0x1804e576f  nop
0x1804e5770  lea     rdx, ds:2[rdx*2]
0x1804e5778  mov     rcx, qword ptr [rsp+190h+pvarg]
0x1804e577d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1804e5782  mov     rax, r14
0x1804e5785  mov     rcx, [rbp+90h+var_50]
0x1804e5789  xor     rcx, rsp; StackCookie
0x1804e578c  call    __security_check_cookie
0x1804e5791  lea     r11, [rsp+190h+var_20]
0x1804e5799  mov     rbx, [r11+40h]
0x1804e579d  mov     rsi, [r11+48h]
0x1804e57a1  movaps  xmm6, xmmword ptr [r11-10h]
0x1804e57a6  movaps  xmm7, xmmword ptr [r11-20h]
0x1804e57ab  mov     rsp, r11
0x1804e57ae  pop     r15
0x1804e57b0  pop     r14
0x1804e57b2  pop     r12
0x1804e57b4  pop     rdi
0x1804e57b5  pop     rbp
0x1804e57b6  retn
0x1804e57b7  sub     ecx, edi
0x1804e57b9  jnz     loc_1804E58A5
0x1804e57bf  mov     [rsp+190h+pvarg], r12b
0x1804e57c4  mov     rdx, rsi
0x1804e57c7  lea     rcx, [rbp+90h+pvarg+8]
0x1804e57cb  call    cs:__imp_??0value@Json@Mso@@QEAA@$$QEAV012@@Z; Mso::Json::value::value(Mso::Json::value &&)
0x1804e57d1  xorps   xmm0, xmm0
0x1804e57d4  movdqu  xmmword ptr [rbp+90h+pvarg+10h], xmm0
0x1804e57d9  movups  [rbp+90h+var_F8], xmm0
0x1804e57dd  mov     word ptr [rbp+90h+var_F8+0Eh], r12w
0x1804e57e2  mov     [rsp+190h+pvarg], r12b
0x1804e57e7  mov     ecx, 50h ; 'P'; this
0x1804e57ec  call    ?AllocateEx@Throw@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::Throw::AllocateEx(unsigned __int64,ulong)
0x1804e57f1  test    rax, rax
0x1804e57f4  jnz     short loc_1804E582B
0x1804e57f6  mov     rbx, r12
0x1804e57f9  test    rbx, rbx
0x1804e57fc  jnz     loc_1804E5A7C
0x1804e5802  mov     rcx, r14; this
0x1804e5805  call    ?Clear@VariantHolderExtension@ServerRuntime@OfficeExtension@@YAXAEAVVariantHolder@Mso@@@Z; OfficeExtension::ServerRuntime::VariantHolderExtension::Clear(Mso::VariantHolder &)
0x1804e580a  mov     word ptr [r14], 0Dh
0x1804e5810  mov     [r14+8], rbx
0x1804e5814  lea     rcx, [rbp+90h+pvarg+10h]; void *
0x1804e5818  call    ??1?$shared_ptr@USourceColorBitmap@xpsrdr@@@std@@QEAA@XZ; std::shared_ptr<xpsrdr::SourceColorBitmap>::~shared_ptr<xpsrdr::SourceColorBitmap>(void)
0x1804e581d  lea     rcx, [rbp+90h+pvarg+8]
0x1804e5821  call    ??1?$unique_ptr@V_Value@details@Json@Mso@@U?$default_delete@V_Value@details@Json@Mso@@@std@@@std@@QEAA@XZ; std::unique_ptr<Mso::Json::details::_Value>::~unique_ptr<Mso::Json::details::_Value>(void)
0x1804e5826  jmp     loc_1804E5782
0x1804e582b  lea     rdx, [rsp+190h+pvarg]
0x1804e5830  mov     rcx, rax
0x1804e5833  call    ??0ComplexTypeValue@ServerRuntime@OfficeExtension@@QEAA@$$QEAVJsonValueWrapper@12@@Z; OfficeExtension::ServerRuntime::ComplexTypeValue::ComplexTypeValue(OfficeExtension::ServerRuntime::JsonValueWrapper &&)
0x1804e5838  mov     rbx, rax
0x1804e583b  jmp     short loc_1804E57F9
0x1804e583d  mov     rcx, rsi
0x1804e5840  call    cs:__imp_?as_bool@value@Json@Mso@@QEBA_NXZ; Mso::Json::value::as_bool(void)
0x1804e5846  mov     dl, al; struct Mso::VariantHolder *
0x1804e5848  mov     rcx, r14; this
0x1804e584b  call    ?SetBool@VariantHolderExtension@ServerRuntime@OfficeExtension@@YAXAEAVVariantHolder@Mso@@_N@Z; OfficeExtension::ServerRuntime::VariantHolderExtension::SetBool(Mso::VariantHolder &,bool)
0x1804e5850  jmp     loc_1804E5782
0x1804e5855  mov     rcx, rsi
0x1804e5858  call    sub_1804E9790
0x1804e585d  mov     rcx, rsi
0x1804e5860  test    al, al
0x1804e5862  jz      short loc_1804E5883
0x1804e5864  call    cs:__imp_?as_integer@value@Json@Mso@@QEBAHXZ; Mso::Json::value::as_integer(void)
0x1804e586a  mov     ebx, eax
0x1804e586c  mov     rcx, r14; this
0x1804e586f  call    ?Clear@VariantHolderExtension@ServerRuntime@OfficeExtension@@YAXAEAVVariantHolder@Mso@@@Z; OfficeExtension::ServerRuntime::VariantHolderExtension::Clear(Mso::VariantHolder &)
0x1804e5874  mov     word ptr [r14], 3
0x1804e587a  mov     [r14+8], ebx
0x1804e587e  jmp     loc_1804E5782
0x1804e5883  call    cs:__imp_?as_double@value@Json@Mso@@QEBANXZ; Mso::Json::value::as_double(void)
0x1804e5889  movaps  xmm6, xmm0
0x1804e588c  mov     rcx, r14; this
0x1804e588f  call    ?Clear@VariantHolderExtension@ServerRuntime@OfficeExtension@@YAXAEAVVariantHolder@Mso@@@Z; OfficeExtension::ServerRuntime::VariantHolderExtension::Clear(Mso::VariantHolder &)
0x1804e5894  mov     word ptr [r14], 5
0x1804e589a  movsd   qword ptr [r14+8], xmm6
0x1804e58a0  jmp     loc_1804E5782
0x1804e58a5  sub     ecx, edi
0x1804e58a7  jnz     loc_1804E59C7
0x1804e58ad  mov     rcx, r14; this
0x1804e58b0  call    ?Clear@VariantHolderExtension@ServerRuntime@OfficeExtension@@YAXAEAVVariantHolder@Mso@@@Z; OfficeExtension::ServerRuntime::VariantHolderExtension::Clear(Mso::VariantHolder &)
0x1804e58b5  mov     rcx, rsi; this
0x1804e58b8  call    ?size@value@Json@Mso@@QEBA_KXZ; Mso::Json::value::size(void)
0x1804e58bd  mov     [rsp+190h+rgsabound.cElements], eax
0x1804e58c1  mov     [rsp+190h+rgsabound.lLbound], r12d
0x1804e58c6  mov     ecx, 0Ch; vt
0x1804e58cb  lea     r8, [rsp+190h+rgsabound]; rgsabound
0x1804e58d0  mov     edx, edi; cDims
0x1804e58d2  call    cs:__imp_SafeArrayCreate
0x1804e58d8  mov     rdi, rax
0x1804e58db  mov     [rsp+190h+var_120], rax
0x1804e58e0  test    rax, rax
0x1804e58e3  jz      loc_1804E5A24
0x1804e58e9  mov     rdx, rax
0x1804e58ec  lea     rcx, [rsp+190h+psa]
0x1804e58f1  call    ??0?$TSafeArrayLocker@UtagVARIANT@@@Mso@@QEAA@PEAUtagSAFEARRAY@@@Z; Mso::TSafeArrayLocker<tagVARIANT>::TSafeArrayLocker<tagVARIANT>(tagSAFEARRAY *)
0x1804e58f6  mov     rcx, [rsi]
0x1804e58f9  mov     rax, [rcx]
0x1804e58fc  mov     rax, [rax+8]
0x1804e5900  call    cs:__guard_dispatch_icall_fptr
0x1804e5906  mov     rbx, [rax]
0x1804e5909  mov     rcx, [rsi]
0x1804e590c  mov     rax, [rcx]
0x1804e590f  mov     rax, [rax+8]
0x1804e5913  call    cs:__guard_dispatch_icall_fptr
0x1804e5919  mov     rsi, [rax+8]
0x1804e591d  mov     r15, r12
0x1804e5920  cmp     rbx, rsi
0x1804e5923  jz      short loc_1804E599F
0x1804e5925  lea     rdx, [rbx+8]
0x1804e5929  lea     rcx, [rsp+190h+var_150]
0x1804e592e  call    ?ConvertJsonValueToVariant@Utility@ServerRuntime@OfficeExtension@@YA?AVVariantHolder@Mso@@AEAVvalue@Json@5@@Z; OfficeExtension::ServerRuntime::Utility::ConvertJsonValueToVariant(Mso::Json::value &)
0x1804e5933  movups  xmm6, xmmword ptr [rsp+190h+var_150]
0x1804e5938  movsd   xmm7, qword ptr [rsp+190h+var_150+10h]
0x1804e593e  lea     rcx, [rsp+190h+pvarg]; pvarg
0x1804e5943  call    cs:__imp_VariantInit
0x1804e5949  movups  xmm0, xmmword ptr [rsp+190h+pvarg]
0x1804e594e  movups  xmmword ptr [rsp+190h+var_150], xmm0
0x1804e5953  movsd   xmm1, qword ptr [rbp+90h+pvarg+10h]
0x1804e5958  movsd   qword ptr [rsp+190h+var_150+10h], xmm1
0x1804e595e  lea     rcx, [rsp+190h+pvarg]; pvarg
0x1804e5963  call    cs:__imp_VariantClear
0x1804e5969  test    eax, eax
0x1804e596b  js      loc_1804E5A6E
0x1804e5971  mov     rax, [rsp+190h+var_130]
0x1804e5976  movups  xmmword ptr [r15+rax], xmm6
0x1804e597b  movsd   qword ptr [r15+rax+10h], xmm7
0x1804e5982  add     r15, 18h
0x1804e5986  lea     rcx, [rsp+190h+var_150]; pvarg
0x1804e598b  call    cs:__imp_VariantClear
0x1804e5991  test    eax, eax
0x1804e5993  js      loc_1804E5A60
0x1804e5999  add     rbx, 10h
0x1804e599d  jmp     short loc_1804E5920
0x1804e599f  mov     rcx, r14; this
0x1804e59a2  call    ?Clear@VariantHolderExtension@ServerRuntime@OfficeExtension@@YAXAEAVVariantHolder@Mso@@@Z; OfficeExtension::ServerRuntime::VariantHolderExtension::Clear(Mso::VariantHolder &)
0x1804e59a7  mov     word ptr [r14], 200Ch
0x1804e59ad  mov     [r14+8], rdi
0x1804e59b1  mov     rcx, [rsp+190h+psa]; psa
0x1804e59b6  test    rcx, rcx
0x1804e59b9  jz      short loc_1804E59C2
0x1804e59bb  call    cs:__imp_SafeArrayUnaccessData
0x1804e59c1  nop
0x1804e59c2  jmp     loc_1804E5782
0x1804e59c7  cmp     ecx, edi
0x1804e59c9  jz      short loc_1804E5A17
0x1804e59cb  mov     [rsp+190h+rgsabound.cElements], 80070057h
0x1804e59d3  lea     rax, [rsp+190h+rgsabound]
0x1804e59d8  mov     [rsp+190h+var_168], rax
0x1804e59dd  lea     rax, aRichapiexcepti_0; "RichApiException 0x%x"
0x1804e59e4  mov     [rsp+190h+var_170], rax
0x1804e59e9  mov     ecx, 22C7444h
0x1804e59ee  mov     r8d, 0Fh
0x1804e59f4  call    ??$MsoSendTraceTag@J@Logging@Mso@@YAXKW4Category@01@W4Severity@01@W4DataCategories@01@PEB_WAEBJ@Z; Mso::Logging::MsoSendTraceTag<long>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories,wchar_t const *,long const &)
0x1804e59f9  mov     edx, [rsp+190h+rgsabound.cElements]; int
0x1804e59fd  lea     rcx, [rbp+90h+pExceptionObject]; this
0x1804e5a01  call    ??0RichApiException@ServerRuntime@OfficeExtension@@QEAA@J@Z; OfficeExtension::ServerRuntime::RichApiException::RichApiException(long)
0x1804e5a06  lea     rdx, _TI2?AVRichApiException@ServerRuntime@OfficeExtension@@; pThrowInfo
0x1804e5a0d  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x1804e5a11  call    _CxxThrowException_0
0x1804e5a17  mov     rcx, r14; this
0x1804e5a1a  call    ?Clear@VariantHolderExtension@ServerRuntime@OfficeExtension@@YAXAEAVVariantHolder@Mso@@@Z; OfficeExtension::ServerRuntime::VariantHolderExtension::Clear(Mso::VariantHolder &)
0x1804e5a1f  jmp     loc_1804E5782
0x1804e5a24  lea     r9, aRichapiexcepti; "RichApiException false"
0x1804e5a2b  mov     edx, 4E3h
0x1804e5a30  mov     ecx, 22C7443h
0x1804e5a35  mov     r8d, 0Fh
0x1804e5a3b  call    cs:__imp_?MsoSendTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z; Mso::Logging::MsoSendTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,wchar_t const *)
0x1804e5a41  mov     edx, 8007000Eh; int
0x1804e5a46  lea     rcx, [rbp+90h+pExceptionObject]; this
0x1804e5a4a  call    ??0RichApiException@ServerRuntime@OfficeExtension@@QEAA@J@Z; OfficeExtension::ServerRuntime::RichApiException::RichApiException(long)
0x1804e5a4f  lea     rdx, _TI2?AVRichApiException@ServerRuntime@OfficeExtension@@; pThrowInfo
0x1804e5a56  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x1804e5a5a  call    _CxxThrowException_0
0x1804e5a60  mov     edx, 1F7A008Dh
0x1804e5a65  mov     ecx, eax
0x1804e5a67  call    cs:__imp_?CrashWithRecoveryHrTag@@YAXHI@Z; CrashWithRecoveryHrTag(int,uint)
0x1804e5a6d  nop
0x1804e5a6e  mov     edx, 1F7A008Dh
0x1804e5a73  mov     ecx, eax
0x1804e5a75  call    cs:__imp_?CrashWithRecoveryHrTag@@YAXHI@Z; CrashWithRecoveryHrTag(int,uint)
0x1804e5a7b  nop
0x1804e5a7c  lock add [rbx+48h], edi
0x1804e5a80  jmp     loc_1804E5802
```
