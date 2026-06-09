# CBaseExpression::CalculateValue(CExpressionValueStack *,unsigned __int64,CalculateValueResult *)

- ea: `0x180051c50`
- end: `0x18005225b`
- name: `?CalculateValue@CBaseExpression@@IEAAJPEAVCExpressionValueStack@@_KPEAUCalculateValueResult@@@Z`
- size: `1547`
- prototype: `__int64 __fastcall(CBaseExpression *__hidden this, struct CExpressionValueStack *, unsigned __int64, struct CalculateValueResult *)`
- caller_count: `8`
- callee_count: `25`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180051a10`
- `0x180051c50`
- `0x180059930`
- `0x180059ff0`
- `0x18005a570`
- `0x180167040`
- `0x1801674b0`
- `0x180167c80`

## callees

- `0x180025650`
- `0x180050270`
- `0x180051770`
- `0x1800517e0`
- `0x180051840`
- `0x180051c50`
- `0x180052264`
- `0x1800522a0`
- `0x180052bb0`
- `0x180052fb0`
- `0x180056ba8`
- `0x180056c5c`
- `0x180059890`
- `0x1800d31b0`
- `0x18014d268`
- `0x180159498`
- `0x1801606e0`
- `0x1801635a0`
- `0x18016e080`
- `0x1801fb980`
- `0x180200488`
- `0x180219e3c`
- `0x1802284b0`
- `0x180231dfc`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18029de0b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18029de0b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18029de17`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18029de17`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18029de20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18029de20`

## pseudocode

```c
__int64 __fastcall CBaseExpression::CalculateValue(
        CBaseExpression *this,
        struct CExpressionValueStack *a2,
        __int64 a3,
        struct CalculateValueResult *a4)
{
  unsigned int v4; // esi
  __int64 v5; // rbx
  __int64 v6; // rbp
  struct CalculateValueResult *v7; // r12
  __int64 v8; // r15
  int v11; // r13d
  CBaseExpression *v12; // rsi
  int Property; // eax
  CBaseExpression *v14; // rcx
  struct CExpressionValue *v15; // r15
  bool v16; // r12
  int v17; // r15d
  bool v18; // zf
  __int64 v20; // rbp
  __int64 v21; // rax
  CBaseExpression **v22; // rsi
  _QWORD *v23; // rsi
  _QWORD *v24; // rbx
  CExpressionManager *i; // r15
  __int64 v26; // rdx
  __int64 v27; // rcx
  CResource *TargetResource; // rax
  struct CResource *v29; // rsi
  int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // rdx
  int v33; // eax
  int v34; // eax
  CBaseExpression **v35; // r12
  unsigned __int64 v36; // r15
  __int64 Elapsed; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  int v40; // eax
  HANDLE EventW; // rsi
  unsigned int v42; // [rsp+20h] [rbp-118h]
  unsigned int v43; // [rsp+20h] [rbp-118h]
  char v44; // [rsp+30h] [rbp-108h]
  __int64 v45; // [rsp+38h] [rbp-100h] BYREF
  CBaseExpression *v46; // [rsp+40h] [rbp-F8h]
  __int64 v47; // [rsp+48h] [rbp-F0h] BYREF
  CBaseExpression *v48; // [rsp+50h] [rbp-E8h]
  __int64 v49; // [rsp+58h] [rbp-E0h] BYREF
  __int64 v50; // [rsp+60h] [rbp-D8h]
  struct CalculateValueResult *v51; // [rsp+68h] [rbp-D0h]
  WCHAR Name[64]; // [rsp+70h] [rbp-C8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v4 = 0;
  v51 = a4;
  v5 = 0;
  v50 = a3;
  v6 = 0;
  v47 = 0;
  v7 = a4;
  v8 = a3;
  v45 = 0;
  if ( *((_QWORD *)this + 21) == a3 )
    goto LABEL_28;
  if ( *((_DWORD *)this + 55) || CCommonRegistryData::LogExpressionPerfStats )
  {
    v12 = (CBaseExpression *)((char *)this + 24);
    v20 = *(_QWORD *)(*((_QWORD *)this + 3) + 816LL);
    QpcStopwatch::Start((QpcStopwatch *)&v47);
    v11 = *((_DWORD *)this + 56);
    v46 = v12;
    v6 = v20 + 128;
    if ( v6 )
    {
      QpcStopwatch::Start((QpcStopwatch *)&v45);
      v5 = v45;
    }
    v44 = 1;
  }
  else
  {
    v11 = *((_DWORD *)this + 56);
    v12 = (CBaseExpression *)((char *)this + 24);
    v46 = (CBaseExpression *)((char *)this + 24);
    v44 = 0;
  }
  if ( (*((_BYTE *)this + 216) & 0x10) == 0 )
  {
    v21 = *(_QWORD *)v12;
    v22 = (CBaseExpression **)*((_QWORD *)this + 29);
    if ( v22 != *((CBaseExpression ***)this + 30) )
    {
      v35 = (CBaseExpression **)*((_QWORD *)this + 30);
      v36 = *(_QWORD *)(v21 + 880);
      do
      {
        v48 = *v22;
        v49 = 0;
        v34 = CBaseExpression::CalculateValue(v48, a2, v36, (struct CalculateValueResult *)&v49);
        if ( v34 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x31C,
            (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\baseexpression.cpp",
            (const char *)(unsigned int)v34,
            v42);
        CBaseExpression::EnsureExpressionIsUnregistered(v48);
        ++v22;
      }
      while ( v22 != v35 );
      v8 = v50;
      v7 = v51;
    }
    *((_BYTE *)this + 216) |= 0x10u;
  }
  if ( !v11 )
    *((_DWORD *)this + 56) = 4;
  if ( *((_DWORD *)a2 + 24) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x442,
      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\resources\\baseexpression.cpp",
      (const char *)a4);
  Property = (*(__int64 (__fastcall **)(CBaseExpression *, struct CExpressionValueStack *, struct CalculateValueResult *))(*(_QWORD *)this + 224LL))(
               this,
               a2,
               v7);
  v4 = Property;
  if ( Property < 0 )
  {
    v43 = 1092;
    goto LABEL_32;
  }
  *((_QWORD *)this + 21) = v8;
  if ( *((_BYTE *)v7 + 1) )
    goto LABEL_28;
  if ( v5 )
  {
    Elapsed = QpcStopwatch::GetElapsed((QpcStopwatch *)&v45);
    CExpressionPerformanceCounter::AddDurationSample(v6, 1, Elapsed);
    v5 = 0;
    v45 = 0;
  }
  v14 = v46;
  if ( v44 )
  {
    if ( (*((_BYTE *)this + 216) & 2) != 0 )
    {
      v32 = *(_QWORD *)(*(_QWORD *)v46 + 816LL);
      v33 = *((_DWORD *)this + 55);
      ++*(_DWORD *)(v32 + 420);
      if ( v33 )
        ++*(_DWORD *)(v32 + 424);
    }
  }
  if ( *((_DWORD *)a2 + 24) == 1 )
  {
    v15 = *(struct CExpressionValue **)a2;
    if ( *(_DWORD *)(*(_QWORD *)a2 + 64LL) != *((_DWORD *)this + 38) )
    {
      CBaseExpression::EnsureExpressionIsUnregistered(this);
      v4 = -2147467259;
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_1802D4170, 2u, -2147467259, 0x46Au, 0);
      goto LABEL_28;
    }
    if ( CBaseExpression::IsExpressionValueValid(v14, *(const struct CExpressionValue **)a2) )
    {
LABEL_17:
      if ( v6 )
      {
        QpcStopwatch::Start((QpcStopwatch *)&v45);
        v5 = v45;
      }
      if ( *((_DWORD *)v15 + 16) != *((_DWORD *)this + 38) )
      {
        v4 = -2147024809;
        v17 = -2147024809;
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2147024809, 0x25Au, 0);
LABEL_79:
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_1802D4170, 2u, v17, 0x492u, 0);
        goto LABEL_28;
      }
      v16 = 0;
      if ( *((_DWORD *)this + 55) )
        v16 = (unsigned __int8)CExpressionValue::operator==((char *)this + 80, v15) == 0;
      CExpressionValue::CopyFrom((CBaseExpression *)((char *)this + 80), v15);
      if ( v16 )
      {
        CBaseExpression::LogSetOutputValue(this);
        v40 = StringCchPrintfW(Name, 0x3Cu, L"DwmExpression_SetValue_%d", *((unsigned int *)this + 55));
        v17 = v40;
        if ( v40 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v40, 0x281u, 0);
LABEL_78:
          v4 = v17;
          goto LABEL_79;
        }
        EventW = CreateEventW(0, 1, 0, Name);
        SetEvent(EventW);
        CloseHandle(EventW);
      }
      if ( (*((_BYTE *)this + 216) & 3) != 3 || (v17 = CBaseExpression::SetOutputValueOnTarget(this), v17 >= 0) )
      {
        if ( v5 )
        {
          v38 = QpcStopwatch::GetElapsed((QpcStopwatch *)&v45);
          CExpressionPerformanceCounter::AddDurationSample(v6, 5, v38);
        }
        v4 = 0;
        goto LABEL_28;
      }
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v17, 0x291u, 0);
      goto LABEL_78;
    }
    v29 = CBaseExpression::ResolveTargetNoRef(this);
    if ( !v29 )
    {
      v4 = -2147024782;
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_1802D4170, 2u, -2147024782, 0x474u, 0);
      goto LABEL_28;
    }
    v15 = CExpressionValueStack::PushStackValue(a2);
    v30 = *((_DWORD *)a2 + 24);
    if ( v30 )
      *((_DWORD *)a2 + 24) = v30 - 1;
    Property = CResource::TranslateAndGetProperty(v29, *((unsigned int *)this + 45), v15);
    v4 = Property;
    if ( Property < 0 )
    {
      v43 = 1147;
    }
    else
    {
      v31 = *((_QWORD *)this + 24);
      if ( !v31
        || !*(_BYTE *)(v31 + 4)
        || (Property = CExpressionValue::ApplyMaskToValue(v15, (const struct SubchannelMaskInfo *)v31),
            v4 = Property,
            Property >= 0) )
      {
        if ( *((_DWORD *)v15 + 16) != *((_DWORD *)this + 38) )
        {
          v4 = -2147024809;
          MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_1802D4170, 2u, -2147024809, 0x486u, 0);
          goto LABEL_28;
        }
        goto LABEL_17;
      }
      v43 = 1153;
    }
LABEL_32:
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_1802D4170, 2u, Property, v43, 0);
    goto LABEL_28;
  }
  v23 = (_QWORD *)*((_QWORD *)this + 33);
  v24 = (_QWORD *)*((_QWORD *)this + 32);
  for ( i = *(CExpressionManager **)(*(_QWORD *)v14 + 816LL); v24 != v23; ++v24 )
  {
    TargetResource = (CResource *)CWeakReference<CGdiSpriteBitmap>::GetTargetResource(*v24);
    if ( TargetResource )
      CResource::RemoveAnimationProducer(TargetResource, this);
  }
  v26 = *((_QWORD *)this + 33);
  v27 = *((_QWORD *)this + 32);
  if ( v27 != v26 )
  {
    std::_Destroy_range<std::allocator<wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy>>>(v27, v26);
    *((_QWORD *)this + 33) = *((_QWORD *)this + 32);
  }
  if ( (*((_BYTE *)this + 216) & 0x20) != 0 )
  {
    if ( (*((_BYTE *)this + 217) & 1) != 0 )
      CExpressionManager::EnsureAutoCompleteOnOccludedAnimationRemoved(i, this);
    CExpressionManager::UnregisterExpression(i, this);
    *((_BYTE *)this + 216) &= ~0x20u;
  }
  v4 = -2147467259;
  MilInstrumentationCheckHR_MaybeFailFast(0x14u, &qword_1802D4170, 2u, -2147467259, 0x461u, 0);
LABEL_28:
  v18 = v47 == 0;
  *((_DWORD *)a2 + 24) = 0;
  if ( !v18 )
  {
    v39 = QpcStopwatch::GetElapsed((QpcStopwatch *)&v47);
    CExpressionPerformanceCounter::AddDurationSample(v6, 0, v39);
  }
  return v4;
}

```

## disassembly

```asm
0x180051c50  push    rbx
0x180051c52  push    rbp
0x180051c53  push    rsi
0x180051c54  push    rdi
0x180051c55  push    r12
0x180051c57  push    r14
0x180051c59  push    r15
0x180051c5b  sub     rsp, 100h
0x180051c62  mov     rax, cs:__security_cookie
0x180051c69  xor     rax, rsp
0x180051c6c  mov     [rsp+138h+var_48], rax
0x180051c74  xor     esi, esi
0x180051c76  mov     [rsp+138h+var_D0], r9
0x180051c7b  xor     ebx, ebx
0x180051c7d  mov     [rsp+138h+var_D8], r8
0x180051c82  xor     ebp, ebp
0x180051c84  mov     [rsp+138h+var_F0], rsi
0x180051c89  mov     r12, r9
0x180051c8c  mov     r15, r8
0x180051c8f  mov     r14, rdx
0x180051c92  mov     rdi, rcx
0x180051c95  mov     [rsp+138h+var_100], rbx
0x180051c9a  cmp     [rcx+0A8h], r8
0x180051ca1  jz      loc_180051DF8
0x180051ca7  mov     [rsp+138h+arg_10], r13
0x180051caf  cmp     [rcx+0DCh], ebx
0x180051cb5  jnz     loc_180051E5D
0x180051cbb  cmp     cs:?LogExpressionPerfStats@CCommonRegistryData@@2V?$CRegistryKey@_N_N@details@@B, bl; details::CRegistryKey<bool,bool> const CCommonRegistryData::LogExpressionPerfStats
0x180051cc1  jnz     loc_180051E5D
0x180051cc7  mov     r13d, [rcx+0E0h]
0x180051cce  lea     rsi, [rcx+18h]
0x180051cd2  mov     [rsp+138h+var_F8], rsi
0x180051cd7  mov     [rsp+138h+var_108], bl
0x180051cdb  test    byte ptr [rdi+0D8h], 10h
0x180051ce2  jz      loc_180051EBF
0x180051ce8  test    r13d, r13d
0x180051ceb  mov     r13, [rsp+138h+arg_10]
0x180051cf3  jz      loc_180051EB0
0x180051cf9  cmp     dword ptr [r14+60h], 0
0x180051cfe  jnz     loc_180051E96
0x180051d04  mov     rax, [rdi]
0x180051d07  mov     r8, r12
0x180051d0a  mov     rdx, r14
0x180051d0d  mov     rcx, rdi
0x180051d10  mov     rax, [rax+0E0h]
0x180051d17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051d1c  mov     esi, eax
0x180051d1e  test    eax, eax
0x180051d20  js      loc_180051E30
0x180051d26  mov     [rdi+0A8h], r15
0x180051d2d  cmp     byte ptr [r12+1], 0
0x180051d33  jnz     loc_180051DF8
0x180051d39  test    rbx, rbx
0x180051d3c  jnz     loc_1800520E0
0x180051d42  cmp     [rsp+138h+var_108], 0
0x180051d47  mov     rcx, [rsp+138h+var_F8]; this
0x180051d4c  jnz     loc_180052106
0x180051d52  mov     eax, [r14+60h]
0x180051d56  cmp     eax, 1
0x180051d59  jnz     loc_180051EEC
0x180051d5f  dec     eax
0x180051d61  lea     rdx, [rax+rax*8]
0x180051d65  mov     rax, [r14]
0x180051d68  lea     r15, [rax+rdx*8]
0x180051d6c  mov     eax, [rdi+98h]
0x180051d72  cmp     [r15+40h], eax
0x180051d76  jnz     loc_180052140
0x180051d7c  mov     rdx, r15; struct CExpressionValue *
0x180051d7f  call    ?IsExpressionValueValid@CBaseExpression@@AEAA_NPEBVCExpressionValue@@@Z; CBaseExpression::IsExpressionValueValid(CExpressionValue const *)
0x180051d84  test    al, al
0x180051d86  jz      loc_180051F8B
0x180051d8c  test    rbp, rbp
0x180051d8f  jnz     loc_1800521C2
0x180051d95  mov     eax, [rdi+98h]
0x180051d9b  cmp     [r15+40h], eax
0x180051d9f  jnz     loc_1800521D6
0x180051da5  xor     r12b, r12b
0x180051da8  lea     rsi, [rdi+50h]
0x180051dac  cmp     dword ptr [rdi+0DCh], 0
0x180051db3  jnz     loc_180052040
0x180051db9  mov     rdx, r15; struct CExpressionValue *
0x180051dbc  mov     rcx, rsi; this
0x180051dbf  call    ?CopyFrom@CExpressionValue@@QEAAXAEBV1@@Z; CExpressionValue::CopyFrom(CExpressionValue const &)
0x180051dc4  test    r12b, r12b
0x180051dc7  jnz     loc_18029DDD0
0x180051dcd  movzx   eax, byte ptr [rdi+0D8h]
0x180051dd4  and     al, 3
0x180051dd6  cmp     al, 3
0x180051dd8  jnz     short loc_180051DED
0x180051dda  mov     rcx, rdi; this
0x180051ddd  call    ?SetOutputValueOnTarget@CBaseExpression@@IEAAJXZ; CBaseExpression::SetOutputValueOnTarget(void)
0x180051de2  mov     r15d, eax
0x180051de5  test    eax, eax
0x180051de7  js      loc_180052207
0x180051ded  test    rbx, rbx
0x180051df0  jnz     loc_180052220
0x180051df6  xor     esi, esi
0x180051df8  cmp     [rsp+138h+var_F0], 0
0x180051dfe  mov     dword ptr [r14+60h], 0
0x180051e06  jnz     loc_18005223F
0x180051e0c  mov     eax, esi
0x180051e0e  mov     rcx, [rsp+138h+var_48]
0x180051e16  xor     rcx, rsp; StackCookie
0x180051e19  call    __security_check_cookie
0x180051e1e  add     rsp, 100h
0x180051e25  pop     r15
0x180051e27  pop     r14
0x180051e29  pop     r12
0x180051e2b  pop     rdi
0x180051e2c  pop     rsi
0x180051e2d  pop     rbp
0x180051e2e  pop     rbx
0x180051e2f  retn
0x180051e30  mov     [rsp+138h+var_110], 0; void *
0x180051e39  mov     [rsp+138h+var_118], 444h; unsigned int
0x180051e41  mov     r9d, eax; int
0x180051e44  mov     r8d, 2; unsigned int
0x180051e4a  lea     rdx, qword_1802D4170; int *
0x180051e51  mov     ecx, 14h; unsigned int
0x180051e56  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180051e5b  jmp     short loc_180051DF8
0x180051e5d  mov     rax, [rcx+18h]
0x180051e61  lea     rsi, [rcx+18h]
0x180051e65  lea     rcx, [rsp+138h+var_F0]; this
0x180051e6a  mov     rbp, [rax+330h]
0x180051e71  call    ?Start@QpcStopwatch@@QEAAXXZ; QpcStopwatch::Start(void)
0x180051e76  mov     r13d, [rdi+0E0h]
0x180051e7d  mov     [rsp+138h+var_F8], rsi
0x180051e82  sub     rbp, 0FFFFFFFFFFFFFF80h
0x180051e86  jnz     loc_1800520C1
0x180051e8c  mov     [rsp+138h+var_108], 1
0x180051e91  jmp     loc_180051CDB
0x180051e96  mov     rcx, [rsp+138h]; this
0x180051e9e  lea     r8, aOnecoreuapWind_172; "onecoreuap\\windows\\dwm\\dwmcore\\reso"...
0x180051ea5  mov     edx, 442h; void *
0x180051eaa  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180051eb0  mov     dword ptr [rdi+0E0h], 4
0x180051eba  jmp     loc_180051CF9
0x180051ebf  mov     rax, [rsi]
0x180051ec2  mov     rsi, [rdi+0E8h]
0x180051ec9  mov     rcx, [rax+370h]
0x180051ed0  mov     rax, [rdi+0F0h]
0x180051ed7  cmp     rsi, rax
0x180051eda  jnz     loc_1800520D5
0x180051ee0  or      byte ptr [rdi+0D8h], 10h
0x180051ee7  jmp     loc_180051CE8
0x180051eec  mov     rax, [rcx]
0x180051eef  mov     rsi, [rdi+108h]
0x180051ef6  mov     rbx, [rdi+100h]
0x180051efd  mov     r15, [rax+330h]
0x180051f04  cmp     rbx, rsi
0x180051f07  jnz     short loc_180051F47
0x180051f09  mov     rdx, [rdi+108h]
0x180051f10  mov     rcx, [rdi+100h]
0x180051f17  cmp     rcx, rdx
0x180051f1a  jnz     loc_180052128
0x180051f20  test    byte ptr [rdi+0D8h], 20h
0x180051f27  jnz     short loc_180051F63
0x180051f29  mov     esi, 80004005h
0x180051f2e  mov     [rsp+138h+var_110], 0
0x180051f37  mov     r9d, esi
0x180051f3a  mov     [rsp+138h+var_118], 461h
0x180051f42  jmp     loc_180051E44
0x180051f47  mov     rcx, [rbx]
0x180051f4a  call    ?GetTargetResource@?$CWeakReference@VCGdiSpriteBitmap@@@@QEBAPEAVCGdiSpriteBitmap@@XZ; CWeakReference<CGdiSpriteBitmap>::GetTargetResource(void)
0x180051f4f  test    rax, rax
0x180051f52  jnz     loc_180052118
0x180051f58  add     rbx, 8
0x180051f5c  cmp     rbx, rsi
0x180051f5f  jz      short loc_180051F09
0x180051f61  jmp     short loc_180051F47
0x180051f63  test    byte ptr [rdi+0D9h], 1
0x180051f6a  jz      short loc_180051F77
0x180051f6c  mov     rdx, rdi; struct CBaseExpression *
0x180051f6f  mov     rcx, r15; this
0x180051f72  call    ?EnsureAutoCompleteOnOccludedAnimationRemoved@CExpressionManager@@QEAAXPEAVCBaseExpression@@@Z; CExpressionManager::EnsureAutoCompleteOnOccludedAnimationRemoved(CBaseExpression *)
0x180051f77  mov     rdx, rdi; struct CBaseExpression *
0x180051f7a  mov     rcx, r15; this
0x180051f7d  call    ?UnregisterExpression@CExpressionManager@@QEAAXPEAVCBaseExpression@@@Z; CExpressionManager::UnregisterExpression(CBaseExpression *)
0x180051f82  and     byte ptr [rdi+0D8h], 0DFh
0x180051f89  jmp     short loc_180051F29
0x180051f8b  mov     rcx, rdi; this
0x180051f8e  call    ?ResolveTargetNoRef@CBaseExpression@@IEBAPEAVCResource@@XZ; CBaseExpression::ResolveTargetNoRef(void)
0x180051f93  mov     rsi, rax
0x180051f96  test    rax, rax
0x180051f99  jz      loc_180052166
0x180051f9f  mov     rcx, r14; this
0x180051fa2  call    ?PushStackValue@CExpressionValueStack@@QEAAPEAVCExpressionValue@@XZ; CExpressionValueStack::PushStackValue(void)
0x180051fa7  mov     r15, rax
0x180051faa  mov     eax, [r14+60h]
0x180051fae  test    eax, eax
0x180051fb0  jz      short loc_180051FB8
0x180051fb2  dec     eax
0x180051fb4  mov     [r14+60h], eax
0x180051fb8  mov     edx, [rdi+0B4h]
0x180051fbe  mov     r8, r15
0x180051fc1  mov     rcx, rsi
0x180051fc4  call    ?TranslateAndGetProperty@CResource@@QEAAJUDCOMPOSITION_PROPERTY_REFERENCE@@PEAVCExpressionValue@@@Z; CResource::TranslateAndGetProperty(DCOMPOSITION_PROPERTY_REFERENCE,CExpressionValue *)
0x180051fc9  mov     esi, eax
0x180051fcb  test    eax, eax
0x180051fcd  js      loc_1800521AC
0x180051fd3  mov     rdx, [rdi+0C0h]; struct SubchannelMaskInfo *
0x180051fda  test    rdx, rdx
0x180051fdd  jz      short loc_180051FE9
0x180051fdf  cmp     byte ptr [rdx+4], 0
0x180051fe3  ja      loc_180052184
0x180051fe9  mov     eax, [rdi+98h]
0x180051fef  cmp     [r15+40h], eax
0x180051ff3  jz      loc_180051D8C
0x180051ff9  mov     esi, 80070057h
0x180051ffe  mov     [rsp+138h+var_110], 0
0x180052007  mov     r9d, esi
0x18005200a  mov     [rsp+138h+var_118], 486h
0x180052012  jmp     loc_180051E44
0x180052017  mov     rax, [rcx]
0x18005201a  mov     rdx, [rax+330h]
0x180052021  mov     eax, [rdi+0DCh]
0x180052027  inc     dword ptr [rdx+1A4h]
0x18005202d  test    eax, eax
0x18005202f  jz      loc_180051D52
0x180052035  inc     dword ptr [rdx+1A8h]
0x18005203b  jmp     loc_180051D52
0x180052040  mov     rdx, r15
0x180052043  mov     rcx, rsi
0x180052046  call    ??8CExpressionValue@@QEBA_NAEBV0@@Z; CExpressionValue::operator==(CExpressionValue const &)
0x18005204b  test    al, al
0x18005204d  jnz     loc_180051DB9
0x180052053  mov     r12b, 1
0x180052056  jmp     loc_180051DB9
0x18005205b  mov     rax, [rsi]
0x18005205e  lea     r9, [rsp+138h+var_E0]; struct CalculateValueResult *
0x180052063  mov     rcx, rax; this
0x180052066  mov     [rsp+138h+var_E8], rax
0x18005206b  mov     r8, r15; unsigned __int64
0x18005206e  mov     [rsp+138h+var_E0], 0
0x180052077  mov     rdx, r14; struct CExpressionValueStack *
0x18005207a  call    ?CalculateValue@CBaseExpression@@IEAAJPEAVCExpressionValueStack@@_KPEAUCalculateValueResult@@@Z; CBaseExpression::CalculateValue(CExpressionValueStack *,unsigned __int64,CalculateValueResult *)
0x18005207f  test    eax, eax
0x180052081  jns     short loc_18005209F
0x180052083  mov     rcx, [rsp+138h]; this
0x18005208b  lea     r8, aOnecoreuapWind_172; "onecoreuap\\windows\\dwm\\dwmcore\\reso"...
0x180052092  mov     r9d, eax; char *
0x180052095  mov     edx, 31Ch; void *
0x18005209a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005209f  mov     rcx, [rsp+138h+var_E8]; this
0x1800520a4  call    ?EnsureExpressionIsUnregistered@CBaseExpression@@QEAAXXZ; CBaseExpression::EnsureExpressionIsUnregistered(void)
0x1800520a9  add     rsi, 8
0x1800520ad  cmp     rsi, r12
0x1800520b0  jnz     short loc_18005205B
0x1800520b2  mov     r15, [rsp+138h+var_D8]
0x1800520b7  mov     r12, [rsp+138h+var_D0]
0x1800520bc  jmp     loc_180051EE0
0x1800520c1  lea     rcx, [rsp+138h+var_100]; this
0x1800520c6  call    ?Start@QpcStopwatch@@QEAAXXZ; QpcStopwatch::Start(void)
0x1800520cb  mov     rbx, [rsp+138h+var_100]
0x1800520d0  jmp     loc_180051E8C
0x1800520d5  mov     r12, rax
0x1800520d8  mov     r15, rcx
0x1800520db  jmp     loc_18005205B
0x1800520e0  lea     rcx, [rsp+138h+var_100]; this
0x1800520e5  call    ?GetElapsed@QpcStopwatch@@QEAA_JXZ; QpcStopwatch::GetElapsed(void)
0x1800520ea  mov     r8, rax
0x1800520ed  mov     edx, 1
0x1800520f2  mov     rcx, rbp
0x1800520f5  call    ?AddDurationSample@CExpressionPerformanceCounter@@QEAAXW4ExpressionPerformanceLabel@@_J@Z; CExpressionPerformanceCounter::AddDurationSample(ExpressionPerformanceLabel,__int64)
0x1800520fa  xor     ebx, ebx
0x1800520fc  mov     [rsp+138h+var_100], rbx
0x180052101  jmp     loc_180051D42
0x180052106  test    byte ptr [rdi+0D8h], 2
0x18005210d  jz      loc_180051D52
0x180052113  jmp     loc_180052017
0x180052118  mov     rdx, rdi; struct CBaseExpression *
0x18005211b  mov     rcx, rax; this
0x18005211e  call    ?RemoveAnimationProducer@CResource@@QEAAXPEAVCBaseExpression@@@Z; CResource::RemoveAnimationProducer(CBaseExpression *)
0x180052123  jmp     loc_180051F58
0x180052128  call    ??$_Destroy_range@V?$allocator@V?$com_ptr_t@VCCachedTexture@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@YAXPEAV?$com_ptr_t@VCCachedTexture@@Uerr_returncode_policy@wil@@@wil@@QEAV12@AEAV?$allocator@V?$com_ptr_t@VCCachedTexture@@Uerr_returncode_policy@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy>>>(wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy> *,wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy> * const,std::allocator<wil::com_ptr_t<CCachedTexture,wil::err_returncode_policy>> &)
0x18005212d  mov     rax, [rdi+100h]
0x180052134  mov     [rdi+108h], rax
0x18005213b  jmp     loc_180051F20
0x180052140  mov     rcx, rdi; this
0x180052143  call    ?EnsureExpressionIsUnregistered@CBaseExpression@@QEAAXXZ; CBaseExpression::EnsureExpressionIsUnregistered(void)
0x180052148  mov     esi, 80004005h
0x18005214d  mov     [rsp+138h+var_110], 0
0x180052156  mov     r9d, esi
0x180052159  mov     [rsp+138h+var_118], 46Ah
0x180052161  jmp     loc_180051E44
0x180052166  mov     esi, 80070072h
0x18005216b  mov     [rsp+138h+var_110], 0
0x180052174  mov     r9d, esi
0x180052177  mov     [rsp+138h+var_118], 474h
0x18005217f  jmp     loc_180051E44
0x180052184  mov     rcx, r15; this
0x180052187  call    ?ApplyMaskToValue@CExpressionValue@@QEAAJPEBVSubchannelMaskInfo@@@Z; CExpressionValue::ApplyMaskToValue(SubchannelMaskInfo const *)
0x18005218c  mov     esi, eax
0x18005218e  test    eax, eax
0x180052190  jns     loc_180051FE9
0x180052196  mov     [rsp+138h+var_110], 0
0x18005219f  mov     [rsp+138h+var_118], 481h
0x1800521a7  jmp     loc_180051E41
0x1800521ac  mov     [rsp+138h+var_110], 0
  ... truncated ...
```
