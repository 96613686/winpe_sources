# blue2th::Migrator::GenerateRuntimeVariables(void)

- ea: `0x180008520`
- end: `0x18000889c`
- name: `?GenerateRuntimeVariables@Migrator@blue2th@@QEAAXXZ`
- size: `892`
- prototype: `void __fastcall(__int64 ***this)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180008940`
- `0x18000c740`

## callees

- `0x1800022e0`
- `0x180007720`
- `0x180007b38`
- `0x180007dd4`
- `0x18000820c`
- `0x180008520`
- `0x180009f44`
- `0x18000a2a4`

## string_xrefs

- `0x18000872a`: `DiscoveryServiceFullURL`

## pseudocode

```c
void __fastcall blue2th::Migrator::GenerateRuntimeVariables(__int64 ***this)
{
  _QWORD *v2; // rax
  __int64 String; // rax
  _QWORD *v4; // rax
  __int64 v5; // rax
  _QWORD *v6; // rax
  __int64 v7; // rax
  _QWORD *v8; // rax
  __int64 v9; // rax
  __int128 v10; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v11; // [rsp+30h] [rbp-D0h]
  __int64 v12; // [rsp+38h] [rbp-C8h]
  char *v13[4]; // [rsp+40h] [rbp-C0h] BYREF
  char *v14[4]; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v15[2]; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v16[2]; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD v17[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v18; // [rsp+E0h] [rbp-20h] BYREF
  __m128i si128; // [rsp+F0h] [rbp-10h]
  _OWORD v20[2]; // [rsp+100h] [rbp+0h] BYREF
  _OWORD v21[2]; // [rsp+120h] [rbp+20h] BYREF

  if ( !this[1] )
  {
    v18 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v18) = 0;
    v17[0] = 0;
    v17[1] = si128;
    LOWORD(v17[0]) = 0;
    v16[0] = 0;
    v16[1] = si128;
    LOWORD(v16[0]) = 0;
    v21[0] = 0;
    v21[1] = si128;
    LOWORD(v21[0]) = 0;
    v15[0] = 0;
    v15[1] = si128;
    LOWORD(v15[0]) = 0;
    memset(v20, 0, sizeof(v20));
    std::wstring::_Construct<1,unsigned short const *>(v20, L"B92E7305-9462-4B48-AE6D-57D9D09FD698", 0x24u);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::emplace<unsigned short const * &,std::wstring &>(
      this,
      &v10,
      &enrollmentIdRtv,
      v20);
    v10 = 0;
    v11 = 0;
    v12 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v10, L"SOFTWARE\\Microsoft\\Enrollments\\%ENROLLMENTID%", 0x2Du);
    v2 = (_QWORD *)RegistryHelper::ExpandName((__int64)v14, &v10, this);
    if ( v2[3] > 7u )
      v2 = (_QWORD *)*v2;
    String = RegistryHelper::GetString(v13, v2, L"ProviderID");
    std::wstring::operator=((char **)&v18, String);
    std::wstring::~wstring(v13);
    std::wstring::~wstring(v14);
    v10 = 0;
    v11 = 0;
    v12 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v10, L"SOFTWARE\\Microsoft\\Enrollments\\%ENROLLMENTID%", 0x2Du);
    v4 = (_QWORD *)RegistryHelper::ExpandName((__int64)v13, &v10, this);
    if ( v4[3] > 7u )
      v4 = (_QWORD *)*v4;
    v5 = RegistryHelper::GetString(v14, v4, L"UPN");
    std::wstring::operator=((char **)v17, v5);
    std::wstring::~wstring(v14);
    std::wstring::~wstring(v13);
    v10 = 0;
    v11 = 0;
    v12 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v10, L"SOFTWARE\\Microsoft\\Enrollments\\%ENROLLMENTID%", 0x2Du);
    v6 = (_QWORD *)RegistryHelper::ExpandName((__int64)v13, &v10, this);
    if ( v6[3] > 7u )
      v6 = (_QWORD *)*v6;
    v7 = RegistryHelper::GetString(v14, v6, L"DiscoveryServiceFullURL");
    std::wstring::operator=((char **)v16, v7);
    std::wstring::~wstring(v14);
    std::wstring::~wstring(v13);
    v10 = 0;
    v11 = 0;
    v12 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v10, L"SOFTWARE\\Microsoft\\Enrollments\\%ENROLLMENTID%", 0x2Du);
    v8 = (_QWORD *)RegistryHelper::ExpandName((__int64)v13, &v10, this);
    if ( v8[3] > 7u )
      v8 = (_QWORD *)*v8;
    v9 = RegistryHelper::GetString(v14, v8, L"SID");
    std::wstring::operator=((char **)v15, v9);
    std::wstring::~wstring(v14);
    std::wstring::~wstring(v13);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::emplace<unsigned short const * &,std::wstring &>(
      this,
      &v10,
      &providerIdRtv,
      &v18);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::emplace<unsigned short const * &,std::wstring &>(
      this,
      &v10,
      &emailRtv,
      v17);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::emplace<unsigned short const * &,std::wstring &>(
      this,
      &v10,
      &discoveryServerRtv,
      v16);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::emplace<unsigned short const * &,std::wstring &>(
      this,
      &v10,
      &userSidRtv,
      v15);
    std::wstring::~wstring((char **)v20);
    std::wstring::~wstring((char **)v15);
    std::wstring::~wstring((char **)v21);
    std::wstring::~wstring((char **)v16);
    std::wstring::~wstring((char **)v17);
    std::wstring::~wstring((char **)&v18);
  }
}

```

## disassembly

```asm
0x180008520  mov     [rsp-8+arg_8], rbx
0x180008525  mov     [rsp-8+arg_10], rsi
0x18000852a  push    rbp
0x18000852b  lea     rbp, [rsp-50h]
0x180008530  sub     rsp, 150h
0x180008537  mov     rax, cs:__security_cookie
0x18000853e  xor     rax, rsp
0x180008541  mov     [rbp+50h+var_10], rax
0x180008545  mov     rbx, rcx
0x180008548  cmp     qword ptr [rcx+8], 0
0x18000854d  jnz     loc_18000887B
0x180008553  xorps   xmm0, xmm0
0x180008556  movups  [rbp+50h+var_70], xmm0
0x18000855a  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180008562  movdqu  [rbp+50h+var_60], xmm1
0x180008567  xor     eax, eax
0x180008569  mov     word ptr [rbp+50h+var_70], ax
0x18000856d  movups  [rbp+50h+var_90], xmm0
0x180008571  movdqu  [rbp+50h+var_80], xmm1
0x180008576  mov     word ptr [rbp+50h+var_90], ax
0x18000857a  movups  [rbp+50h+var_B0], xmm0
0x18000857e  movdqu  [rbp+50h+var_A0], xmm1
0x180008583  mov     word ptr [rbp+50h+var_B0], ax
0x180008587  movups  [rbp+50h+var_30], xmm0
0x18000858b  movdqu  [rbp+50h+var_20], xmm1
0x180008590  mov     word ptr [rbp+50h+var_30], ax
0x180008594  movups  [rbp+50h+var_D0], xmm0
0x180008598  movdqu  [rbp+50h+var_C0], xmm1
0x18000859d  mov     word ptr [rbp+50h+var_D0], ax
0x1800085a1  movups  [rbp+50h+var_50], xmm0
0x1800085a5  xorps   xmm1, xmm1
0x1800085a8  movdqu  [rbp+50h+var_40], xmm1
0x1800085ad  lea     r8d, [rax+24h]
0x1800085b1  lea     rdx, aB92e730594624b; "B92E7305-9462-4B48-AE6D-57D9D09FD698"
0x1800085b8  lea     rcx, [rbp+50h+var_50]
0x1800085bc  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800085c1  nop
0x1800085c2  lea     r9, [rbp+50h+var_50]
0x1800085c6  lea     r8, ?enrollmentIdRtv@@3PEBGEB; ushort const * const enrollmentIdRtv
0x1800085cd  lea     rdx, [rsp+150h+var_130]
0x1800085d2  mov     rcx, rbx
0x1800085d5  call    ??$emplace@AEAPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@_N@1@AEAPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::emplace<ushort const * &,std::wstring &>(ushort const * &,std::wstring &)
0x1800085da  xorps   xmm0, xmm0
0x1800085dd  movups  [rsp+150h+var_130], xmm0
0x1800085e2  mov     [rsp+150h+var_120], 0
0x1800085eb  mov     [rsp+150h+var_118], 0
0x1800085f4  mov     esi, 2Dh ; '-'
0x1800085f9  mov     r8d, esi
0x1800085fc  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Enrollments\\%ENRO"...
0x180008603  lea     rcx, [rsp+150h+var_130]
0x180008608  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000860d  mov     r8, rbx
0x180008610  lea     rdx, [rsp+150h+var_130]
0x180008615  lea     rcx, [rsp+150h+var_F0]
0x18000861a  call    ?ExpandName@RegistryHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@3@@Z; RegistryHelper::ExpandName(std::wstring,std::map<std::wstring,std::wstring> const &)
0x18000861f  nop
0x180008620  cmp     qword ptr [rax+18h], 7
0x180008625  jbe     short loc_18000862A
0x180008627  mov     rax, [rax]
0x18000862a  lea     r8, aProviderid; "ProviderID"
0x180008631  mov     rdx, rax
0x180008634  lea     rcx, [rsp+150h+var_110]
0x180008639  call    ?GetString@RegistryHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; RegistryHelper::GetString(ushort const *,ushort const *)
0x18000863e  mov     rdx, rax
0x180008641  lea     rcx, [rbp+50h+var_70]
0x180008645  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000864a  lea     rcx, [rsp+150h+var_110]; void *
0x18000864f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008654  nop
0x180008655  lea     rcx, [rsp+150h+var_F0]; void *
0x18000865a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000865f  xorps   xmm0, xmm0
0x180008662  movups  [rsp+150h+var_130], xmm0
0x180008667  mov     [rsp+150h+var_120], 0
0x180008670  mov     [rsp+150h+var_118], 0
0x180008679  mov     r8, rsi
0x18000867c  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Enrollments\\%ENRO"...
0x180008683  lea     rcx, [rsp+150h+var_130]
0x180008688  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000868d  mov     r8, rbx
0x180008690  lea     rdx, [rsp+150h+var_130]
0x180008695  lea     rcx, [rsp+150h+var_110]
0x18000869a  call    ?ExpandName@RegistryHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@3@@Z; RegistryHelper::ExpandName(std::wstring,std::map<std::wstring,std::wstring> const &)
0x18000869f  nop
0x1800086a0  cmp     qword ptr [rax+18h], 7
0x1800086a5  jbe     short loc_1800086AA
0x1800086a7  mov     rax, [rax]
0x1800086aa  lea     r8, aUpn; "UPN"
0x1800086b1  mov     rdx, rax
0x1800086b4  lea     rcx, [rsp+150h+var_F0]
0x1800086b9  call    ?GetString@RegistryHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; RegistryHelper::GetString(ushort const *,ushort const *)
0x1800086be  mov     rdx, rax
0x1800086c1  lea     rcx, [rbp+50h+var_90]
0x1800086c5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800086ca  lea     rcx, [rsp+150h+var_F0]; void *
0x1800086cf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800086d4  nop
0x1800086d5  lea     rcx, [rsp+150h+var_110]; void *
0x1800086da  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800086df  xorps   xmm0, xmm0
0x1800086e2  movups  [rsp+150h+var_130], xmm0
0x1800086e7  mov     [rsp+150h+var_120], 0
0x1800086f0  mov     [rsp+150h+var_118], 0
0x1800086f9  mov     r8, rsi
0x1800086fc  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Enrollments\\%ENRO"...
0x180008703  lea     rcx, [rsp+150h+var_130]
0x180008708  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000870d  mov     r8, rbx
0x180008710  lea     rdx, [rsp+150h+var_130]
0x180008715  lea     rcx, [rsp+150h+var_110]
0x18000871a  call    ?ExpandName@RegistryHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@3@@Z; RegistryHelper::ExpandName(std::wstring,std::map<std::wstring,std::wstring> const &)
0x18000871f  nop
0x180008720  cmp     qword ptr [rax+18h], 7
0x180008725  jbe     short loc_18000872A
0x180008727  mov     rax, [rax]
0x18000872a  lea     r8, aDiscoveryservi; "DiscoveryServiceFullURL"
0x180008731  mov     rdx, rax
0x180008734  lea     rcx, [rsp+150h+var_F0]
0x180008739  call    ?GetString@RegistryHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; RegistryHelper::GetString(ushort const *,ushort const *)
0x18000873e  mov     rdx, rax
0x180008741  lea     rcx, [rbp+50h+var_B0]
0x180008745  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000874a  lea     rcx, [rsp+150h+var_F0]; void *
0x18000874f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008754  nop
0x180008755  lea     rcx, [rsp+150h+var_110]; void *
0x18000875a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000875f  xorps   xmm0, xmm0
0x180008762  movups  [rsp+150h+var_130], xmm0
0x180008767  mov     [rsp+150h+var_120], 0
0x180008770  mov     [rsp+150h+var_118], 0
0x180008779  mov     r8, rsi
0x18000877c  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Enrollments\\%ENRO"...
0x180008783  lea     rcx, [rsp+150h+var_130]
0x180008788  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000878d  mov     r8, rbx
0x180008790  lea     rdx, [rsp+150h+var_130]
0x180008795  lea     rcx, [rsp+150h+var_110]
0x18000879a  call    ?ExpandName@RegistryHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@AEBV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@3@@Z; RegistryHelper::ExpandName(std::wstring,std::map<std::wstring,std::wstring> const &)
0x18000879f  nop
0x1800087a0  cmp     qword ptr [rax+18h], 7
0x1800087a5  jbe     short loc_1800087AA
0x1800087a7  mov     rax, [rax]
0x1800087aa  lea     r8, aSid; "SID"
0x1800087b1  mov     rdx, rax
0x1800087b4  lea     rcx, [rsp+150h+var_F0]
0x1800087b9  call    ?GetString@RegistryHelper@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; RegistryHelper::GetString(ushort const *,ushort const *)
0x1800087be  mov     rdx, rax
0x1800087c1  lea     rcx, [rbp+50h+var_D0]
0x1800087c5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800087ca  lea     rcx, [rsp+150h+var_F0]; void *
0x1800087cf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800087d4  nop
0x1800087d5  lea     rcx, [rsp+150h+var_110]; void *
0x1800087da  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800087df  lea     r9, [rbp+50h+var_70]
0x1800087e3  lea     r8, ?providerIdRtv@@3PEBGEB; ushort const * const providerIdRtv
0x1800087ea  lea     rdx, [rsp+150h+var_130]
0x1800087ef  mov     rcx, rbx
0x1800087f2  call    ??$emplace@AEAPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@_N@1@AEAPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::emplace<ushort const * &,std::wstring &>(ushort const * &,std::wstring &)
0x1800087f7  lea     r9, [rbp+50h+var_90]
0x1800087fb  lea     r8, ?emailRtv@@3PEBGEB; ushort const * const emailRtv
0x180008802  lea     rdx, [rsp+150h+var_130]
0x180008807  mov     rcx, rbx
0x18000880a  call    ??$emplace@AEAPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@_N@1@AEAPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::emplace<ushort const * &,std::wstring &>(ushort const * &,std::wstring &)
0x18000880f  lea     r9, [rbp+50h+var_B0]
0x180008813  lea     r8, ?discoveryServerRtv@@3PEBGEB; ushort const * const discoveryServerRtv
0x18000881a  lea     rdx, [rsp+150h+var_130]
0x18000881f  mov     rcx, rbx
0x180008822  call    ??$emplace@AEAPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@_N@1@AEAPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::emplace<ushort const * &,std::wstring &>(ushort const * &,std::wstring &)
0x180008827  lea     r9, [rbp+50h+var_D0]
0x18000882b  lea     r8, ?userSidRtv@@3PEBGEB; ushort const * const userSidRtv
0x180008832  lea     rdx, [rsp+150h+var_130]
0x180008837  mov     rcx, rbx
0x18000883a  call    ??$emplace@AEAPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@std@@_N@1@AEAPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::emplace<ushort const * &,std::wstring &>(ushort const * &,std::wstring &)
0x18000883f  nop
0x180008840  lea     rcx, [rbp+50h+var_50]; void *
0x180008844  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008849  nop
0x18000884a  lea     rcx, [rbp+50h+var_D0]; void *
0x18000884e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008853  nop
0x180008854  lea     rcx, [rbp+50h+var_30]; void *
0x180008858  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000885d  nop
0x18000885e  lea     rcx, [rbp+50h+var_B0]; void *
0x180008862  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008867  nop
0x180008868  lea     rcx, [rbp+50h+var_90]; void *
0x18000886c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008871  nop
0x180008872  lea     rcx, [rbp+50h+var_70]; void *
0x180008876  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000887b  mov     rcx, [rbp+50h+var_10]
0x18000887f  xor     rcx, rsp; StackCookie
0x180008882  call    __security_check_cookie
0x180008887  lea     r11, [rsp+150h+var_s0]
0x18000888f  mov     rbx, [r11+18h]
0x180008893  mov     rsi, [r11+20h]
0x180008897  mov     rsp, r11
0x18000889a  pop     rbp
0x18000889b  retn
```
