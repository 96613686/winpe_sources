# Js::IntlEngineInterfaceExtensionObject::EntryIntl_FormatNumber(Js::RecyclableObject *,Js::CallInfo,...)

- ea: `0x1803bd810`
- end: `0x1803bda93`
- name: `?EntryIntl_FormatNumber@IntlEngineInterfaceExtensionObject@Js@@SAPEAXPEAVRecyclableObject@2@UCallInfo@2@ZZ`
- size: `643`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18009ce10`
- `0x1800a21a4`
- `0x1800a2a0c`
- `0x1801947dc`
- `0x1801a25bc`
- `0x180282e70`
- `0x1803bcf80`
- `0x1803bd810`
- `0x180536310`
- `0x180536428`
- `0x180536bb8`
- `0x180536c8c`
- `0x180537a5c`
- `0x180537b30`
- `0x1805cd010`

## import_xrefs

- `icu!ufieldpositer_open` at `0x1803bd9d5`
- `icu!ufieldpositer_open` at `0x1803bd9d5`
- `icu!ufieldpositer_next` at `0x1803bda5b`
- `icu!ufieldpositer_next` at `0x1803bda5b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Js::IntlEngineInterfaceExtensionObject::EntryIntl_FormatNumber(
        __int64 a1,
        int a2,
        __int64 a3,
        unsigned __int64 a4,
        void *a5,
        _DWORD *a6,
        _DWORD *a7)
{
  ThreadContext **v8; // r8
  struct Js::ScriptContext *v9; // rbx
  int v10; // edi
  int v11; // esi
  __int64 v12; // rdx
  int v14; // eax
  struct Js::JavascriptArray *v15; // rbx
  unsigned int v16; // [rsp+48h] [rbp-49h] BYREF
  unsigned int i; // [rsp+4Ch] [rbp-45h] BYREF
  unsigned int v18; // [rsp+50h] [rbp-41h] BYREF
  unsigned __int16 *v19; // [rsp+58h] [rbp-39h] BYREF
  __int64 v20; // [rsp+60h] [rbp-31h] BYREF
  int v21; // [rsp+68h] [rbp-29h] BYREF
  double v22; // [rsp+70h] [rbp-21h] BYREF
  __int64 v23; // [rsp+78h] [rbp-19h] BYREF
  __int64 v24; // [rsp+80h] [rbp-11h] BYREF
  __int64 *v25; // [rsp+88h] [rbp-9h] BYREF
  double *v26; // [rsp+90h] [rbp-1h]
  __int64 *v27; // [rsp+98h] [rbp+7h]
  __int64 v28; // [rsp+B8h] [rbp+27h]

  v28 = -2;
  v8 = *(ThreadContext ***)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 1088LL);
  ThreadContext::ProbeStack(v8[110], 0xC00u, (struct Js::ScriptContext *)v8, 0);
  v19 = 0;
  if ( (a2 & 0xFFFFFF) != 5
    || HIWORD(a4) != 1 && a4 < 0x4000000000000LL
    || !Js::DynamicObject::Is(a5)
    || !Js::JavascriptBoolean::Is(a6)
    || !Js::JavascriptBoolean::Is(a7)
    || (v9 = *(struct Js::ScriptContext **)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 1088LL),
        v22 = Js::JavascriptConversion::ToNumber((void *)a4, v9),
        v10 = a6[4],
        v11 = a7[4],
        v23 = 0,
        !(*(unsigned int (__fastcall **)(void *, void *, __int64, __int64 *, _QWORD, struct Js::ScriptContext *))(*(_QWORD *)a5 + 160LL))(
           a5,
           a5,
           10,
           &v23,
           0,
           v9)) )
  {
    Js::Throw::FatalInternalError(-2147467259);
    JUMPOUT(0x1803BDA92LL);
  }
  if ( v11 )
    v12 = 107;
  else
    v12 = (v10 != 0) + 105LL;
  Js::BuiltInCountTracker::Increment(*((_QWORD *)v9 + 122) + 16LL, v12);
  v24 = v23;
  v19 = 0;
  v16 = 0;
  if ( v10 )
  {
    v21 = 0;
    v20 = ufieldpositer_open(&v21);
    v25 = &v24;
    v26 = &v22;
    v27 = &v20;
    Js::EnsureBuffer__lambda_6f6a33015eb9d77b66e0e7f7b8ccb794___(&v25, *((_QWORD *)v9 + 126), &v19, &v16);
    Js::NumberFormatPartsBuilder::NumberFormatPartsBuilder((Js::NumberFormatPartsBuilder *)&v25, v22, v19, v16, v9);
    v18 = 0;
    for ( i = 0; ; Js::NumberFormatPartsBuilder::InsertPart(&v25, (unsigned int)v14, v18, i) )
    {
      v14 = ufieldpositer_next(v20, &v18, &i);
      if ( v14 < 0 )
        break;
    }
    v15 = Js::NumberFormatPartsBuilder::ToPartsArray((Js::NumberFormatPartsBuilder *)&v25);
    PlatformAgnostic::ICUHelpers::ScopedICUObject<UFieldPositionIterator *,&void ufieldpositer_close(UFieldPositionIterator *)>::~ScopedICUObject<UFieldPositionIterator *,&void ufieldpositer_close(UFieldPositionIterator *)>(&v20);
    return (__int64)v15;
  }
  else
  {
    v25 = &v24;
    v26 = &v22;
    Js::EnsureBuffer__lambda_751bf82044a1d12cd216ed696fd1bb00___(&v25, *((_QWORD *)v9 + 126), &v19, &v16);
    return Js::JavascriptString::NewWithBufferT<Js::LiteralString,0>(v19, v16, v9);
  }
}

```

## disassembly

```asm
0x1803bd810  mov     rax, rsp
0x1803bd813  mov     [rax+10h], rdx
0x1803bd817  mov     [rax+8], rcx
0x1803bd81b  mov     [rax+18h], r8
0x1803bd81f  mov     [rax+20h], r9
0x1803bd823  push    rbp
0x1803bd824  push    rbx
0x1803bd825  push    rsi
0x1803bd826  push    rdi
0x1803bd827  lea     rbp, [rax-5Fh]
0x1803bd82b  sub     rsp, 0C8h
0x1803bd832  mov     [rbp+57h+var_30], 0FFFFFFFFFFFFFFFEh
0x1803bd83a  mov     rbx, [rbp+57h+arg_0]
0x1803bd83e  mov     rax, [rbx+8]
0x1803bd842  mov     rcx, [rax+8]
0x1803bd846  mov     rcx, [rcx+440h]
0x1803bd84d  xor     r9d, r9d; void *
0x1803bd850  mov     r8, rcx; struct Js::ScriptContext *
0x1803bd853  mov     edx, 0C00h; unsigned __int64
0x1803bd858  mov     rcx, [rcx+370h]; this
0x1803bd85f  call    ?ProbeStack@ThreadContext@@QEAAX_KPEAVScriptContext@Js@@PEAX@Z; ThreadContext::ProbeStack(unsigned __int64,Js::ScriptContext *,void *)
0x1803bd864  mov     [rbp+57h+var_90], 0
0x1803bd86c  lea     rsi, [rbp+57h+arg_10]
0x1803bd870  mov     eax, [rbp+57h+arg_8]
0x1803bd873  and     eax, 0FFFFFFh
0x1803bd878  cmp     eax, 5
0x1803bd87b  jnz     loc_1803BDA88
0x1803bd881  mov     rax, [rsi+8]
0x1803bd885  shr     rax, 30h
0x1803bd889  cmp     rax, 1
0x1803bd88d  jz      short loc_1803BD8A3
0x1803bd88f  mov     rax, 4000000000000h
0x1803bd899  cmp     [rsi+8], rax
0x1803bd89d  jb      loc_1803BDA88
0x1803bd8a3  mov     rcx, [rsi+10h]; void *
0x1803bd8a7  call    ?Is@DynamicObject@Js@@SA_NPEAX@Z; Js::DynamicObject::Is(void *)
0x1803bd8ac  test    al, al
0x1803bd8ae  jz      loc_1803BDA88
0x1803bd8b4  mov     rcx, [rsi+18h]; void *
0x1803bd8b8  call    ?Is@JavascriptBoolean@Js@@SA_NPEAX@Z; Js::JavascriptBoolean::Is(void *)
0x1803bd8bd  test    al, al
0x1803bd8bf  jz      loc_1803BDA88
0x1803bd8c5  mov     rcx, [rsi+20h]; void *
0x1803bd8c9  call    ?Is@JavascriptBoolean@Js@@SA_NPEAX@Z; Js::JavascriptBoolean::Is(void *)
0x1803bd8ce  test    al, al
0x1803bd8d0  jz      loc_1803BDA88
0x1803bd8d6  mov     rax, [rbx+8]
0x1803bd8da  mov     rdx, [rax+8]
0x1803bd8de  mov     rbx, [rdx+440h]
0x1803bd8e5  mov     rdx, rbx; struct Js::ScriptContext *
0x1803bd8e8  mov     rcx, [rsi+8]; void *
0x1803bd8ec  call    ?ToNumber@JavascriptConversion@Js@@SANPEAXPEAVScriptContext@2@@Z; Js::JavascriptConversion::ToNumber(void *,Js::ScriptContext *)
0x1803bd8f1  movsd   [rbp+57h+var_78], xmm0
0x1803bd8f6  mov     rcx, [rsi+10h]
0x1803bd8fa  mov     rax, [rsi+18h]
0x1803bd8fe  mov     edi, [rax+10h]
0x1803bd901  mov     rax, [rsi+20h]
0x1803bd905  mov     esi, [rax+10h]
0x1803bd908  mov     [rbp+57h+var_70], 0
0x1803bd910  mov     rax, [rcx]
0x1803bd913  mov     [rsp+28h], rbx
0x1803bd918  mov     [rsp+0E0h+var_C0], 0
0x1803bd921  lea     r9, [rbp+57h+var_70]
0x1803bd925  mov     r8d, 0Ah
0x1803bd92b  mov     rdx, rcx
0x1803bd92e  mov     rax, [rax+0A0h]
0x1803bd935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803bd93a  test    eax, eax
0x1803bd93c  jz      loc_1803BDA88
0x1803bd942  test    esi, esi
0x1803bd944  jz      short loc_1803BD94D
0x1803bd946  mov     edx, 6Bh ; 'k'
0x1803bd94b  jmp     short loc_1803BD95B
0x1803bd94d  mov     eax, edi
0x1803bd94f  neg     eax
0x1803bd951  sbb     rdx, rdx
0x1803bd954  neg     rdx
0x1803bd957  add     rdx, 69h ; 'i'
0x1803bd95b  mov     rcx, [rbx+3D0h]
0x1803bd962  add     rcx, 10h
0x1803bd966  call    ?Increment@BuiltInCountTracker@Js@@QEAAXW4BuiltInFacet@2@@Z; Js::BuiltInCountTracker::Increment(Js::BuiltInFacet)
0x1803bd96b  mov     rcx, [rbp+57h+var_70]
0x1803bd96f  mov     [rbp+57h+var_68], rcx
0x1803bd973  mov     [rbp+57h+var_90], 0
0x1803bd97b  mov     [rbp+57h+var_A0], 0
0x1803bd982  test    edi, edi
0x1803bd984  jnz     short loc_1803BD9CA
0x1803bd986  lea     rax, [rbp+57h+var_68]
0x1803bd98a  mov     [rbp+57h+var_60], rax
0x1803bd98e  lea     rax, [rbp+57h+var_78]
0x1803bd992  mov     [rbp+57h+var_58], rax
0x1803bd996  lea     r9, [rbp+57h+var_A0]
0x1803bd99a  lea     r8, [rbp+57h+var_90]
0x1803bd99e  mov     rdx, [rbx+3F0h]
0x1803bd9a5  lea     rcx, [rbp+57h+var_60]
0x1803bd9a9  call    Js__EnsureBuffer__lambda_751bf82044a1d12cd216ed696fd1bb00___
0x1803bd9ae  mov     r8, rbx
0x1803bd9b1  mov     edx, [rbp+57h+var_A0]
0x1803bd9b4  mov     rcx, [rbp+57h+var_90]
0x1803bd9b8  call    ??$NewWithBufferT@VLiteralString@Js@@$0A@@JavascriptString@Js@@CAPEAV01@PEBGIPEAVScriptContext@1@@Z; Js::JavascriptString::NewWithBufferT<Js::LiteralString,0>(ushort const *,uint,Js::ScriptContext *)
0x1803bd9bd  add     rsp, 0C8h
0x1803bd9c4  pop     rdi
0x1803bd9c5  pop     rsi
0x1803bd9c6  pop     rbx
0x1803bd9c7  pop     rbp
0x1803bd9c8  retn
0x1803bd9ca  mov     [rbp+57h+var_80], 0
0x1803bd9d1  lea     rcx, [rbp+57h+var_80]
0x1803bd9d5  call    cs:__imp_ufieldpositer_open
0x1803bd9dc  nop     dword ptr [rax+rax+00h]
0x1803bd9e1  mov     [rbp+57h+var_88], rax
0x1803bd9e5  lea     rax, [rbp+57h+var_68]
0x1803bd9e9  mov     [rbp+57h+var_60], rax
0x1803bd9ed  lea     rax, [rbp+57h+var_78]
0x1803bd9f1  mov     [rbp+57h+var_58], rax
0x1803bd9f5  lea     rax, [rbp+57h+var_88]
0x1803bd9f9  mov     [rbp+57h+var_50], rax
0x1803bd9fd  lea     r9, [rbp+57h+var_A0]
0x1803bda01  lea     r8, [rbp+57h+var_90]
0x1803bda05  mov     rdx, [rbx+3F0h]
0x1803bda0c  lea     rcx, [rbp+57h+var_60]
0x1803bda10  call    Js__EnsureBuffer__lambda_6f6a33015eb9d77b66e0e7f7b8ccb794___
0x1803bda15  mov     [rsp+0E0h+var_C0], rbx; struct Js::ScriptContext *
0x1803bda1a  mov     r9d, [rbp+57h+var_A0]; unsigned int
0x1803bda1e  mov     r8, [rbp+57h+var_90]; unsigned __int16 *
0x1803bda22  movsd   xmm1, [rbp+57h+var_78]; double
0x1803bda27  lea     rcx, [rbp+57h+var_60]; this
0x1803bda2b  call    ??0NumberFormatPartsBuilder@Js@@QEAA@NPEBGIPEAVScriptContext@1@@Z; Js::NumberFormatPartsBuilder::NumberFormatPartsBuilder(double,ushort const *,uint,Js::ScriptContext *)
0x1803bda30  mov     [rbp+57h+var_98], 0
0x1803bda37  mov     [rbp+57h+var_9C], 0
0x1803bda3e  jmp     short loc_1803BDA4F
0x1803bda40  mov     r9d, [rbp+57h+var_9C]
0x1803bda44  mov     r8d, [rbp+57h+var_98]
0x1803bda48  mov     edx, eax
0x1803bda4a  call    ?InsertPart@NumberFormatPartsBuilder@Js@@QEAAXW4UNumberFormatFields@@HH@Z; Js::NumberFormatPartsBuilder::InsertPart(UNumberFormatFields,int,int)
0x1803bda4f  lea     r8, [rbp+57h+var_9C]
0x1803bda53  lea     rdx, [rbp+57h+var_98]
0x1803bda57  mov     rcx, [rbp+57h+var_88]
0x1803bda5b  call    cs:__imp_ufieldpositer_next
0x1803bda62  nop     dword ptr [rax+rax+00h]
0x1803bda67  lea     rcx, [rbp+57h+var_60]; this
0x1803bda6b  test    eax, eax
0x1803bda6d  jns     short loc_1803BDA40
0x1803bda6f  call    ?ToPartsArray@NumberFormatPartsBuilder@Js@@QEAAPEAVJavascriptArray@2@XZ; Js::NumberFormatPartsBuilder::ToPartsArray(void)
0x1803bda74  mov     rbx, rax
0x1803bda77  lea     rcx, [rbp+57h+var_88]
0x1803bda7b  call    ??1?$ScopedICUObject@PEAUUFieldPositionIterator@@$1?ufieldpositer_close@@YAXPEAU1@@Z@ICUHelpers@PlatformAgnostic@@QEAA@XZ; PlatformAgnostic::ICUHelpers::ScopedICUObject<UFieldPositionIterator *,&ufieldpositer_close(UFieldPositionIterator *)>::~ScopedICUObject<UFieldPositionIterator *,&ufieldpositer_close(UFieldPositionIterator *)>(void)
0x1803bda80  mov     rax, rbx
0x1803bda83  jmp     loc_1803BD9BD
0x1803bda88  mov     ecx, 80004005h; int
0x1803bda8d  call    ?FatalInternalError@Throw@Js@@SAXJ@Z; Js::Throw::FatalInternalError(long)
```
