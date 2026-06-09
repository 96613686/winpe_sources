# Js::IntlEngineInterfaceExtensionObject::EntryIntl_PluralRulesSelect(Js::RecyclableObject *,Js::CallInfo,...)

- ea: `0x1803bd0e0`
- end: `0x1803bd3f0`
- name: `?EntryIntl_PluralRulesSelect@IntlEngineInterfaceExtensionObject@Js@@SAPEAXPEAVRecyclableObject@2@UCallInfo@2@ZZ`
- size: `784`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800a21a4`
- `0x1800a2a0c`
- `0x180189ef4`
- `0x1801a25bc`
- `0x1801a3b24`
- `0x1801bd874`
- `0x180282e70`
- `0x1803bc034`
- `0x1803bcf80`
- `0x1803bd0e0`
- `0x1803bdca0`
- `0x1803c4080`
- `0x1803f562c`
- `0x180536310`
- `0x180536540`
- `0x1805a9c5a`
- `0x1805a9e80`

## import_xrefs

- `icu!unum_open` at `0x1803bd294`
- `icu!unum_open` at `0x1803bd294`
- `icu!unum_parseDouble` at `0x1803bd320`
- `icu!unum_parseDouble` at `0x1803bd320`

## pseudocode

```c
__int64 __fastcall Js::IntlEngineInterfaceExtensionObject::EntryIntl_PluralRulesSelect(
        __int64 a1,
        int a2,
        __int64 a3,
        _QWORD *a4)
{
  ThreadContext **v5; // r8
  __int64 v6; // rdx
  __int64 v7; // rdi
  unsigned __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // r8
  __int64 v11; // rax
  __int64 v12; // rdx
  double v13; // xmm0_8
  __int64 v14; // rdx
  void *v16; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v17; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v18; // [rsp+58h] [rbp-B0h] BYREF
  double v19; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v20; // [rsp+68h] [rbp-A0h] BYREF
  __int64 *p_PluralRulesCache; // [rsp+78h] [rbp-90h] BYREF
  double *v22; // [rsp+80h] [rbp-88h]
  __int64 PluralRulesCache; // [rsp+88h] [rbp-80h] BYREF
  double v24; // [rsp+90h] [rbp-78h] BYREF
  _BYTE v25[160]; // [rsp+98h] [rbp-70h] BYREF

  v5 = *(ThreadContext ***)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 1088LL);
  ThreadContext::ProbeStack(v5[110], 0xC00u, (struct Js::ScriptContext *)v5, 0);
  v18 = 0;
  if ( (a2 & 0xFFFFFF) != 3 || !Js::DynamicObject::Is(a4) )
    goto LABEL_17;
  v7 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 1088LL);
  v19 = 0.0;
  v8 = *(_QWORD *)(v6 + 16);
  if ( HIWORD(v8) == 1 )
  {
    v19 = (double)*(int *)(v6 + 16);
  }
  else
  {
    if ( v8 < 0x4000000000000LL )
      goto LABEL_17;
    *(_QWORD *)&v19 = v8 ^ 0xFFFC000000000000uLL;
  }
  Js::BuiltInCountTracker::Increment(*(_QWORD *)(v7 + 976) + 16LL, 111);
  PluralRulesCache = Js::GetOrCreatePluralRulesCache(a4, v7);
  memset_0(v25, 0, 0x9Du);
  v9 = a4[1];
  v16 = 0;
  Js::JavascriptOperators::GetProperty_Internal<0>(
    (int)a4,
    (int)a4,
    0,
    503,
    (__int64)&v16,
    *(_QWORD *)(*(_QWORD *)(v9 + 8) + 1088LL),
    0);
  if ( !v16 || !Js::JavascriptString::Is(v16) )
  {
    Js::Throw::FatalInternalError(-2147467259);
    __debugbreak();
  }
  Js::LangtagToLocaleID_157_(v10, v25);
  LODWORD(v17) = 0;
  v11 = unum_open(1, 0, 0, v25, 0, &v17);
  v20 = Js::FinalizableICUObject<void * *,&void unum_close(void * *)>::New(*(_QWORD *)(v7 + 1008), v11);
  Js::SetUNumberFormatDigitOptions(*(_QWORD *)(v20 + 8), a4);
  v12 = *(_QWORD *)(v7 + 1008);
  p_PluralRulesCache = &v20;
  v18 = 0;
  v22 = &v19;
  LODWORD(v16) = 0;
  Js::EnsureBuffer__lambda_751bf82044a1d12cd216ed696fd1bb00___(&p_PluralRulesCache, v12, &v18, &v16);
  v13 = unum_parseDouble(*(_QWORD *)(v20 + 8), v18, (unsigned int)v16, 0, &v17);
  v24 = v13;
  if ( (_DWORD)v17 == 7 )
    Js::Throw::OutOfMemory();
  if ( (int)v17 > 0 || (_DWORD)v17 == -124 || v19 - v13 > 1.0 || v19 - v13 < -1.0 )
  {
LABEL_17:
    Js::Throw::FatalInternalError(-2147467259);
    JUMPOUT(0x1803BD3EFLL);
  }
  v14 = *(_QWORD *)(v7 + 1008);
  p_PluralRulesCache = &PluralRulesCache;
  v18 = 0;
  v22 = &v24;
  LODWORD(v16) = 0;
  Js::EnsureBuffer__lambda_91a56519026194cd731ce18999811188___(&p_PluralRulesCache, v14, &v18, &v16);
  return Js::JavascriptString::NewWithBufferT<Js::LiteralString,0>(v18, (unsigned int)v16, v7);
}

```

## disassembly

```asm
0x1803bd0e0  mov     rax, rsp
0x1803bd0e3  mov     [rax+10h], rdx
0x1803bd0e7  mov     [rax+8], rcx
0x1803bd0eb  mov     [rax+18h], r8
0x1803bd0ef  mov     [rax+20h], r9
0x1803bd0f3  push    rbp
0x1803bd0f4  push    rbx
0x1803bd0f5  push    rdi
0x1803bd0f6  lea     rbp, [rax-58h]
0x1803bd0fa  sub     rsp, 140h
0x1803bd101  mov     rax, cs:__security_cookie
0x1803bd108  xor     rax, rsp
0x1803bd10b  mov     [rbp+50h+var_20], rax
0x1803bd10f  mov     rdi, [rbp+50h+arg_0]
0x1803bd113  xor     r9d, r9d; void *
0x1803bd116  mov     edx, 0C00h; unsigned __int64
0x1803bd11b  mov     rax, [rdi+8]
0x1803bd11f  mov     rcx, [rax+8]
0x1803bd123  mov     rcx, [rcx+440h]
0x1803bd12a  mov     r8, rcx; struct Js::ScriptContext *
0x1803bd12d  mov     rcx, [rcx+370h]; this
0x1803bd134  call    ?ProbeStack@ThreadContext@@QEAAX_KPEAVScriptContext@Js@@PEAX@Z; ThreadContext::ProbeStack(unsigned __int64,Js::ScriptContext *,void *)
0x1803bd139  mov     eax, [rbp+50h+arg_8]
0x1803bd13c  lea     rdx, [rbp+50h+arg_10]
0x1803bd140  and     eax, 0FFFFFFh
0x1803bd145  mov     [rsp+150h+var_100], 0
0x1803bd14e  cmp     eax, 3
0x1803bd151  jnz     loc_1803BD3E5
0x1803bd157  mov     rbx, [rdx+8]
0x1803bd15b  mov     rcx, rbx; void *
0x1803bd15e  call    ?Is@DynamicObject@Js@@SA_NPEAX@Z; Js::DynamicObject::Is(void *)
0x1803bd163  test    al, al
0x1803bd165  jz      loc_1803BD3E5
0x1803bd16b  mov     rax, [rdi+8]
0x1803bd16f  xorps   xmm0, xmm0
0x1803bd172  mov     rcx, [rax+8]
0x1803bd176  mov     rdi, [rcx+440h]
0x1803bd17d  movsd   [rsp+150h+var_F8], xmm0
0x1803bd183  mov     rcx, [rdx+10h]
0x1803bd187  mov     rax, rcx
0x1803bd18a  shr     rax, 30h
0x1803bd18e  cmp     rax, 1
0x1803bd192  jnz     short loc_1803BD1A5
0x1803bd194  movd    xmm0, dword ptr [rdx+10h]
0x1803bd199  cvtdq2pd xmm0, xmm0
0x1803bd19d  movsd   [rsp+150h+var_F8], xmm0
0x1803bd1a3  jmp     short loc_1803BD1CA
0x1803bd1a5  mov     rax, 4000000000000h
0x1803bd1af  cmp     rcx, rax
0x1803bd1b2  jb      loc_1803BD3E5
0x1803bd1b8  mov     rax, 0FFFC000000000000h
0x1803bd1c2  xor     rcx, rax
0x1803bd1c5  mov     [rsp+150h+var_F8], rcx
0x1803bd1ca  mov     rcx, [rdi+3D0h]
0x1803bd1d1  mov     edx, 6Fh ; 'o'
0x1803bd1d6  add     rcx, 10h
0x1803bd1da  call    ?Increment@BuiltInCountTracker@Js@@QEAAXW4BuiltInFacet@2@@Z; Js::BuiltInCountTracker::Increment(Js::BuiltInFacet)
0x1803bd1df  mov     rdx, rdi
0x1803bd1e2  mov     rcx, rbx
0x1803bd1e5  call    Js__GetOrCreatePluralRulesCache
0x1803bd1ea  xor     edx, edx; Val
0x1803bd1ec  mov     [rbp+50h+var_D0], rax
0x1803bd1f0  mov     r8d, 9Dh; Size
0x1803bd1f6  lea     rcx, [rbp+50h+var_C0]; void *
0x1803bd1fa  call    memset_0
0x1803bd1ff  mov     rax, [rbx+8]
0x1803bd203  mov     r9d, 1F7h; int
0x1803bd209  mov     [rsp+150h+var_110], 0
0x1803bd212  xor     r8d, r8d; int
0x1803bd215  mov     qword ptr [rsp+30h], 0; struct Js::PropertyValueInfo *
0x1803bd21e  mov     rdx, rbx; int
0x1803bd221  mov     rcx, rbx; int
0x1803bd224  mov     rax, [rax+8]
0x1803bd228  mov     rax, [rax+440h]
0x1803bd22f  mov     [rsp+150h+var_128], rax; __int64
0x1803bd234  lea     rax, [rsp+150h+var_110]
0x1803bd239  mov     [rsp+150h+var_130], rax; __int64
0x1803bd23e  call    ??$GetProperty_Internal@$0A@@JavascriptOperators@Js@@CAHPEAXPEAVRecyclableObject@1@_NHPEAPEAXPEAVScriptContext@1@PEAVPropertyValueInfo@1@@Z; Js::JavascriptOperators::GetProperty_Internal<0>(void *,Js::RecyclableObject *,bool,int,void * *,Js::ScriptContext *,Js::PropertyValueInfo *)
0x1803bd243  mov     r8, [rsp+150h+var_110]
0x1803bd248  test    r8, r8
0x1803bd24b  jz      loc_1803BD3DA
0x1803bd251  mov     rcx, r8; void *
0x1803bd254  call    ?Is@JavascriptString@Js@@SA_NPEAX@Z; Js::JavascriptString::Is(void *)
0x1803bd259  test    al, al
0x1803bd25b  jz      loc_1803BD3DA
0x1803bd261  lea     rdx, [rbp+50h+var_C0]
0x1803bd265  mov     rcx, r8
0x1803bd268  call    Js__LangtagToLocaleID_157_
0x1803bd26d  xor     edx, edx
0x1803bd26f  mov     dword ptr [rsp+150h+var_108], 0
0x1803bd277  lea     rax, [rsp+150h+var_108]
0x1803bd27c  xor     r8d, r8d
0x1803bd27f  mov     [rsp+150h+var_128], rax
0x1803bd284  lea     r9, [rbp+50h+var_C0]
0x1803bd288  mov     [rsp+150h+var_130], 0
0x1803bd291  lea     ecx, [rdx+1]
0x1803bd294  call    cs:__imp_unum_open
0x1803bd29b  nop     dword ptr [rax+rax+00h]
0x1803bd2a0  mov     rcx, [rdi+3F0h]
0x1803bd2a7  mov     rdx, rax
0x1803bd2aa  call    ?New@?$FinalizableICUObject@PEAPEAX$1?unum_close@@YAXPEAPEAX@Z@Js@@SAPEAV12@PEAVRecycler@Memory@@PEAPEAX@Z; Js::FinalizableICUObject<void * *,&unum_close(void * *)>::New(Memory::Recycler *,void * *)
0x1803bd2af  mov     [rsp+150h+var_F0], rax
0x1803bd2b4  mov     rdx, rbx
0x1803bd2b7  mov     rcx, [rax+8]
0x1803bd2bb  call    Js__SetUNumberFormatDigitOptions
0x1803bd2c0  mov     rdx, [rdi+3F0h]
0x1803bd2c7  lea     rax, [rsp+150h+var_F0]
0x1803bd2cc  mov     [rsp+150h+var_E0], rax
0x1803bd2d1  lea     r9, [rsp+150h+var_110]
0x1803bd2d6  lea     rax, [rsp+150h+var_F8]
0x1803bd2db  mov     [rsp+150h+var_100], 0
0x1803bd2e4  lea     r8, [rsp+150h+var_100]
0x1803bd2e9  mov     [rsp+150h+var_D8], rax
0x1803bd2ee  lea     rcx, [rsp+150h+var_E0]
0x1803bd2f3  mov     dword ptr [rsp+150h+var_110], 0
0x1803bd2fb  call    Js__EnsureBuffer__lambda_751bf82044a1d12cd216ed696fd1bb00___
0x1803bd300  mov     rcx, [rsp+150h+var_F0]
0x1803bd305  lea     rax, [rsp+150h+var_108]
0x1803bd30a  mov     r8d, dword ptr [rsp+150h+var_110]
0x1803bd30f  xor     r9d, r9d
0x1803bd312  mov     rdx, [rsp+150h+var_100]
0x1803bd317  mov     [rsp+150h+var_130], rax
0x1803bd31c  mov     rcx, [rcx+8]
0x1803bd320  call    cs:__imp_unum_parseDouble
0x1803bd327  nop     dword ptr [rax+rax+00h]
0x1803bd32c  mov     eax, dword ptr [rsp+150h+var_108]
0x1803bd330  movsd   [rbp+50h+var_C8], xmm0
0x1803bd335  cmp     eax, 7
0x1803bd338  jnz     short loc_1803BD340
0x1803bd33a  call    ?OutOfMemory@Throw@Js@@SAXXZ; Js::Throw::OutOfMemory(void)
0x1803bd340  test    eax, eax
0x1803bd342  jg      loc_1803BD3E5
0x1803bd348  cmp     eax, 0FFFFFF84h
0x1803bd34b  jz      loc_1803BD3E5
0x1803bd351  movsd   xmm1, [rsp+150h+var_F8]
0x1803bd357  subsd   xmm1, xmm0
0x1803bd35b  movsd   xmm0, cs:__real@3ff0000000000000
0x1803bd363  comisd  xmm0, xmm1
0x1803bd367  jb      short loc_1803BD3E5
0x1803bd369  comisd  xmm1, cs:__real@bff0000000000000
0x1803bd371  jb      short loc_1803BD3E5
0x1803bd373  mov     rdx, [rdi+3F0h]
0x1803bd37a  lea     rax, [rbp+50h+var_D0]
0x1803bd37e  mov     [rsp+150h+var_E0], rax
0x1803bd383  lea     r9, [rsp+150h+var_110]
0x1803bd388  lea     rax, [rbp+50h+var_C8]
0x1803bd38c  mov     [rsp+150h+var_100], 0
0x1803bd395  lea     r8, [rsp+150h+var_100]
0x1803bd39a  mov     [rsp+150h+var_D8], rax
0x1803bd39f  lea     rcx, [rsp+150h+var_E0]
0x1803bd3a4  mov     dword ptr [rsp+150h+var_110], 0
0x1803bd3ac  call    Js__EnsureBuffer__lambda_91a56519026194cd731ce18999811188___
0x1803bd3b1  mov     edx, dword ptr [rsp+150h+var_110]
0x1803bd3b5  mov     r8, rdi
0x1803bd3b8  mov     rcx, [rsp+150h+var_100]
0x1803bd3bd  call    ??$NewWithBufferT@VLiteralString@Js@@$0A@@JavascriptString@Js@@CAPEAV01@PEBGIPEAVScriptContext@1@@Z; Js::JavascriptString::NewWithBufferT<Js::LiteralString,0>(ushort const *,uint,Js::ScriptContext *)
0x1803bd3c2  mov     rcx, [rbp+50h+var_20]
0x1803bd3c6  xor     rcx, rsp; StackCookie
0x1803bd3c9  call    __security_check_cookie
0x1803bd3ce  add     rsp, 140h
0x1803bd3d5  pop     rdi
0x1803bd3d6  pop     rbx
0x1803bd3d7  pop     rbp
0x1803bd3d8  retn
0x1803bd3da  mov     ecx, 80004005h; int
0x1803bd3df  call    ?FatalInternalError@Throw@Js@@SAXJ@Z; Js::Throw::FatalInternalError(long)
0x1803bd3e4  int     3; Trap to Debugger
0x1803bd3e5  mov     ecx, 80004005h; int
0x1803bd3ea  call    ?FatalInternalError@Throw@Js@@SAXJ@Z; Js::Throw::FatalInternalError(long)
```
