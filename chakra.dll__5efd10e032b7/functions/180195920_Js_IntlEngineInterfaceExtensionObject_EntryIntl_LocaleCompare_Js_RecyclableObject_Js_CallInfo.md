# Js::IntlEngineInterfaceExtensionObject::EntryIntl_LocaleCompare(Js::RecyclableObject *,Js::CallInfo,...)

- ea: `0x180195920`
- end: `0x180195e33`
- name: `?EntryIntl_LocaleCompare@IntlEngineInterfaceExtensionObject@Js@@SAPEAXPEAVRecyclableObject@2@UCallInfo@2@ZZ`
- size: `1299`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callees

- `0x1800a2a0c`
- `0x180189ef4`
- `0x1801947dc`
- `0x180195920`
- `0x180195e3c`
- `0x180195fb4`
- `0x180196004`
- `0x1801a25bc`
- `0x1801a3b24`
- `0x1801bd874`
- `0x180282e70`
- `0x1802e99f0`
- `0x1803bc130`
- `0x1803bcf80`
- `0x1803c4080`
- `0x1803d8f24`
- `0x1803ee9a0`
- `0x1805a9c5a`
- `0x1805a9e80`
- `0x1805cd010`

## import_xrefs

- `icu!ucol_open` at `0x180195cc0`
- `icu!ucol_open` at `0x180195cc0`
- `icu!ucol_setStrength` at `0x180195d49`
- `icu!ucol_setStrength` at `0x180195d82`
- `icu!ucol_setStrength` at `0x180195d49`
- `icu!ucol_setStrength` at `0x180195d82`
- `icu!ucol_setAttribute` at `0x180195d66`
- `icu!ucol_setAttribute` at `0x180195da9`
- `icu!ucol_setAttribute` at `0x180195dce`
- `icu!ucol_setAttribute` at `0x180195dff`
- `icu!ucol_setAttribute` at `0x180195d66`
- `icu!ucol_setAttribute` at `0x180195da9`
- `icu!ucol_setAttribute` at `0x180195dce`
- `icu!ucol_setAttribute` at `0x180195dff`
- `icu!ucol_strcoll` at `0x180195b15`
- `icu!ucol_strcoll` at `0x180195b15`

## pseudocode

```c
__int64 __fastcall Js::IntlEngineInterfaceExtensionObject::EntryIntl_LocaleCompare(
        __int64 a1,
        int a2,
        __int64 a3,
        _DWORD *a4)
{
  ThreadContext **v5; // r8
  __int64 v6; // rdx
  _DWORD *v7; // rsi
  __int64 v8; // rdx
  _QWORD *v9; // rbx
  __int64 v10; // rdx
  __int64 v11; // rdx
  _QWORD *v12; // r13
  __int64 v13; // rcx
  int v14; // eax
  _QWORD *v15; // rdi
  __int64 TemporaryAllocator; // rax
  __int64 v17; // rcx
  unsigned int v18; // ebx
  __int64 v19; // r12
  __int64 v20; // rax
  __int64 NormalizedString; // rax
  unsigned int v22; // r14d
  unsigned int v23; // ebx
  __int64 v24; // r15
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  int v28; // ecx
  __int64 v29; // rbx
  __int64 v31; // rdx
  __int64 v32; // rax
  void *v33; // rdi
  int v34; // r15d
  int v35; // r12d
  void *v36; // rax
  __int64 v37; // rdx
  _QWORD *v38; // rax
  __int64 v39; // r8
  __int64 v40; // [rsp+28h] [rbp-E0h]
  int v41; // [rsp+48h] [rbp-C0h] BYREF
  char v42; // [rsp+4Ch] [rbp-BCh]
  char v43; // [rsp+4Dh] [rbp-BBh]
  void *v44; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD *v45; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v46; // [rsp+60h] [rbp-A8h]
  _QWORD v47[2]; // [rsp+68h] [rbp-A0h] BYREF
  int v48; // [rsp+78h] [rbp-90h]
  _BYTE v49[160]; // [rsp+88h] [rbp-80h] BYREF

  v5 = *(ThreadContext ***)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 1088LL);
  ThreadContext::ProbeStack(v5[110], 0xC00u, (struct Js::ScriptContext *)v5, 0);
  v46 = 0;
  if ( (a2 & 0xFFFFFF) != 5
    || !Js::JavascriptString::Is(a4)
    || (v7 = *(_DWORD **)(v6 + 16), !Js::JavascriptString::Is(v7))
    || (v9 = *(_QWORD **)(v8 + 24), !Js::DynamicObject::Is(v9))
    || !Js::JavascriptBoolean::Is(*(void **)(v10 + 32)) )
  {
    Js::Throw::FatalInternalError(-2147467259);
    __debugbreak();
  }
  v12 = *(_QWORD **)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 1088LL);
  v13 = v12[122];
  if ( *(_DWORD *)(v11 + 16) )
  {
    v14 = *(_DWORD *)(v13 + 440);
    if ( v14 != -1 )
      *(_DWORD *)(v13 + 440) = v14 + 1;
  }
  else
  {
    Js::BuiltInCountTracker::Increment(v13 + 16, 103);
  }
  v45 = 0;
  v41 = 0;
  if ( (*(unsigned int (__fastcall **)(_QWORD *, _QWORD *, __int64, _QWORD **, _QWORD, _QWORD *))(*v9 + 160LL))(
         v9,
         v9,
         9,
         &v45,
         0,
         v12) )
  {
    v15 = v45;
    goto LABEL_12;
  }
  v32 = v9[1];
  v44 = 0;
  Js::JavascriptOperators::GetProperty_Internal<0>(
    (int)v9,
    (int)v9,
    0,
    503,
    (__int64)&v44,
    *(_QWORD *)(*(_QWORD *)(v32 + 8) + 1088LL),
    0);
  v33 = v44;
  if ( !v44 || !Js::JavascriptString::Is(v44) )
  {
    Js::Throw::FatalInternalError(-2147467259);
    JUMPOUT(0x180195E32LL);
  }
  v34 = Js::AssertIntegerProperty((int)v9);
  v42 = Js::AssertBooleanProperty((int)v9);
  v43 = Js::AssertBooleanProperty((int)v9);
  v35 = Js::AssertIntegerProperty((int)v9);
  memset_0(v49, 0, 0x9Du);
  Js::LangtagToLocaleID_157_(v33, v49);
  v36 = (void *)ucol_open(v49, &v41);
  v37 = v12[126];
  v44 = v36;
  v47[0] = Memory::Recycler::AllocFinalizedInlined;
  v47[1] = 0;
  v48 = 0;
  v38 = (_QWORD *)operator new[]<Memory::JitArenaAllocator>(16, v37, v47);
  v15 = v38;
  if ( v38 )
  {
    *v38 = &Js::FinalizableICUObject<UCollator *,&void ucol_close(UCollator *)>::`vftable';
    v38[1] = v44;
  }
  if ( v41 == 7 )
LABEL_32:
    Js::Throw::OutOfMemory();
  if ( v41 > 0 || v41 == -124 )
  {
LABEL_51:
    Js::Throw::FatalInternalError(-2147467259);
    __debugbreak();
  }
  switch ( v34 )
  {
    case 0:
      v31 = 0;
LABEL_39:
      ucol_setStrength(v38[1], v31);
      break;
    case 1:
      v31 = 1;
      goto LABEL_39;
    case 2:
      ucol_setStrength(v38[1], 0);
      ucol_setAttribute(v15[1], 3, 17, &v41);
      break;
    case 3:
      v31 = 2;
      goto LABEL_39;
  }
  if ( v42 )
    ucol_setAttribute(v15[1], 1, 20, &v41);
  if ( v43 )
    ucol_setAttribute(v15[1], 7, 17, &v41);
  if ( v35 )
  {
    if ( v35 != 1 )
      goto LABEL_49;
    v39 = 24;
  }
  else
  {
    v39 = 25;
  }
  ucol_setAttribute(v15[1], 2, v39, &v41);
LABEL_49:
  if ( v41 == 7 )
    goto LABEL_32;
  if ( v41 > 0 || v41 == -124 )
    goto LABEL_51;
  HIDWORD(v40) = 0;
  (*(void (__fastcall **)(_QWORD *, __int64, _QWORD *))(*v9 + 200LL))(v9, 9, v15);
LABEL_12:
  TemporaryAllocator = ThreadContext::GetTemporaryAllocator(v12[110]);
  v17 = *(_QWORD *)a4;
  v18 = a4[6];
  v46 = TemporaryAllocator;
  v19 = TemporaryAllocator + 8;
  LODWORD(v44) = 0;
  v20 = (*(__int64 (__fastcall **)(_DWORD *))(v17 + 752))(a4);
  if ( (unsigned __int8)PlatformAgnostic::UnicodeText::IsNormalizedString(0, v20, v18) )
  {
    NormalizedString = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)a4 + 752LL))(a4);
    v22 = a4[6];
  }
  else
  {
    NormalizedString = Js::JavascriptString::GetNormalizedString(a4, 0, v19, &v44);
    v22 = (unsigned int)v44;
  }
  v23 = v7[6];
  v24 = NormalizedString;
  v25 = *(_QWORD *)v7;
  LODWORD(v44) = 0;
  v26 = (*(__int64 (__fastcall **)(_DWORD *))(v25 + 752))(v7);
  if ( (unsigned __int8)PlatformAgnostic::UnicodeText::IsNormalizedString(0, v26, v23) )
  {
    v27 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v7 + 752LL))(v7);
    v28 = v7[6];
  }
  else
  {
    v27 = Js::JavascriptString::GetNormalizedString(v7, 0, v19, &v44);
    v28 = (int)v44;
  }
  LODWORD(v40) = v28;
  v29 = (unsigned int)ucol_strcoll(v15[1], v24, v22, v27, v40) | 0x1000000000000LL;
  ThreadContext::ReleaseTemporaryAllocator(v12[110], v46);
  return v29;
}

```

## disassembly

```asm
0x180195920  mov     rax, rsp
0x180195923  mov     [rax+10h], rdx
0x180195927  mov     [rax+8], rcx
0x18019592b  mov     [rax+18h], r8
0x18019592f  mov     [rax+20h], r9
0x180195933  push    rbp
0x180195934  push    rbx
0x180195935  push    rsi
0x180195936  push    rdi
0x180195937  push    r12
0x180195939  push    r13
0x18019593b  push    r14
0x18019593d  push    r15
0x18019593f  lea     rbp, [rax-78h]
0x180195943  sub     rsp, 138h
0x18019594a  mov     rax, cs:__security_cookie
0x180195951  xor     rax, rsp
0x180195954  mov     [rbp+70h+var_50], rax
0x180195958  mov     rdi, [rbp+70h+arg_0]
0x18019595f  xor     r9d, r9d; void *
0x180195962  mov     edx, 0C00h; unsigned __int64
0x180195967  mov     rax, [rdi+8]
0x18019596b  mov     rcx, [rax+8]
0x18019596f  mov     rcx, [rcx+440h]
0x180195976  mov     r8, rcx; struct Js::ScriptContext *
0x180195979  mov     rcx, [rcx+370h]; this
0x180195980  call    ?ProbeStack@ThreadContext@@QEAAX_KPEAVScriptContext@Js@@PEAX@Z; ThreadContext::ProbeStack(unsigned __int64,Js::ScriptContext *,void *)
0x180195985  mov     eax, [rbp+70h+arg_8]
0x18019598b  lea     rdx, [rbp+70h+arg_10]
0x180195992  xor     r15d, r15d
0x180195995  and     eax, 0FFFFFFh
0x18019599a  mov     [rsp+170h+var_118], r15
0x18019599f  cmp     eax, 5
0x1801959a2  jz      short loc_1801959AF
0x1801959a4  mov     ecx, 80004005h; int
0x1801959a9  call    ?FatalInternalError@Throw@Js@@SAXJ@Z; Js::Throw::FatalInternalError(long)
0x1801959ae  int     3; Trap to Debugger
0x1801959af  mov     r14, [rdx+8]
0x1801959b3  mov     rcx, r14; void *
0x1801959b6  call    ?Is@JavascriptString@Js@@SA_NPEAX@Z; Js::JavascriptString::Is(void *)
0x1801959bb  test    al, al
0x1801959bd  jz      short loc_1801959A4
0x1801959bf  mov     rsi, [rdx+10h]
0x1801959c3  mov     rcx, rsi; void *
0x1801959c6  call    ?Is@JavascriptString@Js@@SA_NPEAX@Z; Js::JavascriptString::Is(void *)
0x1801959cb  test    al, al
0x1801959cd  jz      short loc_1801959A4
0x1801959cf  mov     rbx, [rdx+18h]
0x1801959d3  mov     rcx, rbx; void *
0x1801959d6  call    ?Is@DynamicObject@Js@@SA_NPEAX@Z; Js::DynamicObject::Is(void *)
0x1801959db  test    al, al
0x1801959dd  jz      short loc_1801959A4
0x1801959df  mov     rdx, [rdx+20h]
0x1801959e3  mov     rcx, rdx; void *
0x1801959e6  call    ?Is@JavascriptBoolean@Js@@SA_NPEAX@Z; Js::JavascriptBoolean::Is(void *)
0x1801959eb  test    al, al
0x1801959ed  jz      short loc_1801959A4
0x1801959ef  mov     rax, [rdi+8]
0x1801959f3  mov     rcx, [rax+8]
0x1801959f7  mov     r13, [rcx+440h]
0x1801959fe  mov     rcx, [r13+3D0h]
0x180195a05  cmp     [rdx+10h], r15d
0x180195a09  jz      loc_180195B7A
0x180195a0f  mov     eax, [rcx+1B8h]
0x180195a15  cmp     eax, 0FFFFFFFFh
0x180195a18  jz      short loc_180195A22
0x180195a1a  inc     eax
0x180195a1c  mov     [rcx+1B8h], eax
0x180195a22  mov     [rsp+170h+var_120], r15
0x180195a27  lea     r9, [rsp+170h+var_120]
0x180195a2c  mov     dword ptr [rsp+170h+var_130], r15d
0x180195a31  mov     r8d, 9
0x180195a37  mov     rax, [rbx]
0x180195a3a  mov     rdx, rbx
0x180195a3d  mov     [rsp+170h+var_148], r13
0x180195a42  mov     rcx, rbx
0x180195a45  mov     [rsp+170h+var_150], r15
0x180195a4a  mov     rax, [rax+0A0h]
0x180195a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180195a56  test    eax, eax
0x180195a58  jz      loc_180195BFE
0x180195a5e  mov     rdi, [rsp+170h+var_120]
0x180195a63  mov     rcx, [r13+370h]
0x180195a6a  call    ?GetTemporaryAllocator@ThreadContext@@QEAAPEAV?$TempArenaAllocatorWrapper@$0A@@Js@@PEBG@Z; ThreadContext::GetTemporaryAllocator(ushort const *)
0x180195a6f  mov     rcx, [r14]
0x180195a72  mov     ebx, [r14+18h]
0x180195a76  mov     [rsp+170h+var_118], rax
0x180195a7b  lea     r12, [rax+8]
0x180195a7f  mov     dword ptr [rsp+170h+var_128], r15d
0x180195a84  mov     rax, [rcx+2F0h]
0x180195a8b  mov     rcx, r14
0x180195a8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180195a93  mov     r8d, ebx
0x180195a96  mov     rdx, rax
0x180195a99  xor     ecx, ecx
0x180195a9b  call    ?IsNormalizedString@UnicodeText@PlatformAgnostic@@YA_NW4NormalizationForm@12@PEBGH@Z; PlatformAgnostic::UnicodeText::IsNormalizedString(PlatformAgnostic::UnicodeText::NormalizationForm,ushort const *,int)
0x180195aa0  mov     rcx, r14
0x180195aa3  test    al, al
0x180195aa5  jz      loc_180195B8D
0x180195aab  mov     rax, [r14]
0x180195aae  mov     rax, [rax+2F0h]
0x180195ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180195aba  mov     r14d, [r14+18h]
0x180195abe  mov     ebx, [rsi+18h]
0x180195ac1  mov     r15, rax
0x180195ac4  mov     rax, [rsi]
0x180195ac7  mov     rcx, rsi
0x180195aca  mov     dword ptr [rsp+170h+var_128], 0
0x180195ad2  mov     rax, [rax+2F0h]
0x180195ad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180195ade  mov     r8d, ebx
0x180195ae1  mov     rdx, rax
0x180195ae4  xor     ecx, ecx
0x180195ae6  call    ?IsNormalizedString@UnicodeText@PlatformAgnostic@@YA_NW4NormalizationForm@12@PEBGH@Z; PlatformAgnostic::UnicodeText::IsNormalizedString(PlatformAgnostic::UnicodeText::NormalizationForm,ushort const *,int)
0x180195aeb  mov     rcx, rsi
0x180195aee  test    al, al
0x180195af0  jz      short loc_180195B65
0x180195af2  mov     rax, [rsi]
0x180195af5  mov     rax, [rax+2F0h]
0x180195afc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180195b01  mov     ecx, [rsi+18h]
0x180195b04  mov     dword ptr [rsp+170h+var_150], ecx
0x180195b08  mov     r9, rax
0x180195b0b  mov     rcx, [rdi+8]
0x180195b0f  mov     r8d, r14d
0x180195b12  mov     rdx, r15
0x180195b15  call    cs:__imp_ucol_strcoll
0x180195b1c  nop     dword ptr [rax+rax+00h]
0x180195b21  mov     rdx, [rsp+170h+var_118]
0x180195b26  mov     rcx, [r13+370h]
0x180195b2d  mov     ebx, eax
0x180195b2f  mov     rax, 1000000000000h
0x180195b39  or      rbx, rax
0x180195b3c  call    ?ReleaseTemporaryAllocator@ThreadContext@@QEAAXPEAV?$TempArenaAllocatorWrapper@$0A@@Js@@@Z; ThreadContext::ReleaseTemporaryAllocator(Js::TempArenaAllocatorWrapper<0> *)
0x180195b41  mov     rax, rbx
0x180195b44  mov     rcx, [rbp+70h+var_50]
0x180195b48  xor     rcx, rsp; StackCookie
0x180195b4b  call    __security_check_cookie
0x180195b50  add     rsp, 138h
0x180195b57  pop     r15
0x180195b59  pop     r14
0x180195b5b  pop     r13
0x180195b5d  pop     r12
0x180195b5f  pop     rdi
0x180195b60  pop     rsi
0x180195b61  pop     rbx
0x180195b62  pop     rbp
0x180195b63  retn
0x180195b65  lea     r9, [rsp+170h+var_128]
0x180195b6a  mov     r8, r12
0x180195b6d  xor     edx, edx
0x180195b6f  call    ?GetNormalizedString@JavascriptString@Js@@QEAAPEAGW4NormalizationForm@UnicodeText@PlatformAgnostic@@PEAVArenaAllocator@Memory@@AEAI@Z; Js::JavascriptString::GetNormalizedString(PlatformAgnostic::UnicodeText::NormalizationForm,Memory::ArenaAllocator *,uint &)
0x180195b74  mov     ecx, dword ptr [rsp+170h+var_128]
0x180195b78  jmp     short loc_180195B04
0x180195b7a  add     rcx, 10h
0x180195b7e  mov     edx, 67h ; 'g'
0x180195b83  call    ?Increment@BuiltInCountTracker@Js@@QEAAXW4BuiltInFacet@2@@Z; Js::BuiltInCountTracker::Increment(Js::BuiltInFacet)
0x180195b88  jmp     loc_180195A22
0x180195b8d  lea     r9, [rsp+170h+var_128]
0x180195b92  mov     r8, r12
0x180195b95  xor     edx, edx
0x180195b97  call    ?GetNormalizedString@JavascriptString@Js@@QEAAPEAGW4NormalizationForm@UnicodeText@PlatformAgnostic@@PEAVArenaAllocator@Memory@@AEAI@Z; Js::JavascriptString::GetNormalizedString(PlatformAgnostic::UnicodeText::NormalizationForm,Memory::ArenaAllocator *,uint &)
0x180195b9c  mov     r14d, dword ptr [rsp+170h+var_128]
0x180195ba1  jmp     loc_180195ABE
0x180195ba6  test    eax, eax
0x180195ba8  jg      loc_180195E1D
0x180195bae  cmp     eax, 0FFFFFF84h
0x180195bb1  jz      loc_180195E1D
0x180195bb7  test    r15d, r15d
0x180195bba  jnz     loc_180195D32
0x180195bc0  xor     edx, edx
0x180195bc2  jmp     loc_180195D7E
0x180195bc7  test    eax, eax
0x180195bc9  jg      loc_180195E1D
0x180195bcf  cmp     eax, 0FFFFFF84h
0x180195bd2  jz      loc_180195E1D
0x180195bd8  mov     rax, [rbx]
0x180195bdb  xor     r9d, r9d
0x180195bde  mov     r8, rdi
0x180195be1  mov     [rsp+170h+var_150], r15
0x180195be6  mov     rcx, rbx
0x180195be9  mov     rax, [rax+0C8h]
0x180195bf0  lea     edx, [r9+9]
0x180195bf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180195bf9  jmp     loc_180195A63
0x180195bfe  mov     rax, [rbx+8]
0x180195c02  mov     r9d, 1F7h; int
0x180195c08  mov     [rsp+170h+var_128], r15
0x180195c0d  xor     r8d, r8d; int
0x180195c10  mov     [rsp+30h], r15; struct Js::PropertyValueInfo *
0x180195c15  mov     rdx, rbx; int
0x180195c18  mov     rcx, rbx; int
0x180195c1b  mov     rax, [rax+8]
0x180195c1f  mov     rax, [rax+440h]
0x180195c26  mov     [rsp+170h+var_148], rax; __int64
0x180195c2b  lea     rax, [rsp+170h+var_128]
0x180195c30  mov     [rsp+170h+var_150], rax; __int64
0x180195c35  call    ??$GetProperty_Internal@$0A@@JavascriptOperators@Js@@CAHPEAXPEAVRecyclableObject@1@_NHPEAPEAXPEAVScriptContext@1@PEAVPropertyValueInfo@1@@Z; Js::JavascriptOperators::GetProperty_Internal<0>(void *,Js::RecyclableObject *,bool,int,void * *,Js::ScriptContext *,Js::PropertyValueInfo *)
0x180195c3a  mov     rdi, [rsp+170h+var_128]
0x180195c3f  test    rdi, rdi
0x180195c42  jz      loc_180195E28
0x180195c48  mov     rcx, rdi; void *
0x180195c4b  call    ?Is@JavascriptString@Js@@SA_NPEAX@Z; Js::JavascriptString::Is(void *)
0x180195c50  test    al, al
0x180195c52  jz      loc_180195E28
0x180195c58  mov     edx, 222h
0x180195c5d  mov     rcx, rbx; int
0x180195c60  call    Js__AssertIntegerProperty
0x180195c65  mov     edx, 21Fh
0x180195c6a  mov     rcx, rbx; int
0x180195c6d  mov     r15d, eax
0x180195c70  call    Js__AssertBooleanProperty
0x180195c75  mov     edx, 220h
0x180195c7a  mov     byte ptr [rsp+170h+var_130+4], al
0x180195c7e  mov     rcx, rbx; int
0x180195c81  call    Js__AssertBooleanProperty
0x180195c86  mov     edx, 223h
0x180195c8b  mov     byte ptr [rsp+170h+var_130+5], al
0x180195c8f  mov     rcx, rbx; int
0x180195c92  call    Js__AssertIntegerProperty
0x180195c97  xor     edx, edx; Val
0x180195c99  lea     rcx, [rbp+70h+var_F0]; void *
0x180195c9d  mov     r8d, 9Dh; Size
0x180195ca3  mov     r12d, eax
0x180195ca6  call    memset_0
0x180195cab  lea     rdx, [rbp+70h+var_F0]
0x180195caf  mov     rcx, rdi
0x180195cb2  call    Js__LangtagToLocaleID_157_
0x180195cb7  lea     rdx, [rsp+170h+var_130]
0x180195cbc  lea     rcx, [rbp+70h+var_F0]
0x180195cc0  call    cs:__imp_ucol_open
0x180195cc7  nop     dword ptr [rax+rax+00h]
0x180195ccc  mov     ecx, [rsp+74h]
0x180195cd0  lea     r8, [rsp+170h+var_110]
0x180195cd5  mov     rdx, [r13+3F0h]
0x180195cdc  mov     [rsp+170h+var_128], rax
0x180195ce1  lea     rax, ?AllocFinalizedInlined@Recycler@Memory@@QEAAPEAD_K@Z; Memory::Recycler::AllocFinalizedInlined(unsigned __int64)
0x180195ce8  mov     [rsp+170h+var_110], rax
0x180195ced  xor     eax, eax
0x180195cef  mov     [rsp+74h], ecx
0x180195cf3  mov     qword ptr [rsp+170h+var_108], rax
0x180195cf8  mov     [rsp+170h+var_100], eax
0x180195cfc  lea     ecx, [rax+10h]
0x180195cff  call    ??$?_UVJitArenaAllocator@Memory@@@@YAPEAX_KPEAVJitArenaAllocator@Memory@@P801@EAAPEAD0@Z@Z; operator new[]<Memory::JitArenaAllocator>(unsigned __int64,Memory::JitArenaAllocator *,char * (Memory::JitArenaAllocator::*)(unsigned __int64))
0x180195d04  mov     rdi, rax
0x180195d07  test    rax, rax
0x180195d0a  jz      short loc_180195D1F
0x180195d0c  lea     rax, ??_7?$FinalizableICUObject@PEAUUCollator@@$1?ucol_close@@YAXPEAU1@@Z@Js@@6B@; const Js::FinalizableICUObject<UCollator *,&ucol_close(UCollator *)>::`vftable'
0x180195d13  mov     [rdi], rax
0x180195d16  mov     rax, [rsp+170h+var_128]
0x180195d1b  mov     [rdi+8], rax
0x180195d1f  mov     eax, dword ptr [rsp+170h+var_130]
0x180195d23  cmp     eax, 7
0x180195d26  jnz     loc_180195BA6
0x180195d2c  call    ?OutOfMemory@Throw@Js@@SAXXZ; Js::Throw::OutOfMemory(void)
0x180195d32  cmp     r15d, 1
0x180195d36  jnz     short loc_180195D3D
0x180195d38  mov     edx, r15d
0x180195d3b  jmp     short loc_180195D7E
0x180195d3d  cmp     r15d, 2
0x180195d41  jnz     short loc_180195D74
0x180195d43  mov     rcx, [rdi+8]
0x180195d47  xor     edx, edx
0x180195d49  call    cs:__imp_ucol_setStrength
0x180195d50  nop     dword ptr [rax+rax+00h]
0x180195d55  mov     rcx, [rdi+8]
0x180195d59  lea     r9, [rsp+170h+var_130]
0x180195d5e  lea     edx, [r15+1]
0x180195d62  lea     r8d, [r15+0Fh]
0x180195d66  call    cs:__imp_ucol_setAttribute
0x180195d6d  nop     dword ptr [rax+rax+00h]
0x180195d72  jmp     short loc_180195D8E
0x180195d74  cmp     r15d, 3
0x180195d78  jnz     short loc_180195D8E
0x180195d7a  lea     edx, [r15-1]
0x180195d7e  mov     rcx, [rdi+8]
0x180195d82  call    cs:__imp_ucol_setStrength
0x180195d89  nop     dword ptr [rax+rax+00h]
0x180195d8e  xor     r15d, r15d
0x180195d91  cmp     byte ptr [rsp+170h+var_130+4], r15b
0x180195d96  jz      short loc_180195DB5
0x180195d98  mov     rcx, [rdi+8]
0x180195d9c  lea     r9, [rsp+170h+var_130]
0x180195da1  lea     edx, [r15+1]
0x180195da5  lea     r8d, [r15+14h]
0x180195da9  call    cs:__imp_ucol_setAttribute
0x180195db0  nop     dword ptr [rax+rax+00h]
0x180195db5  cmp     byte ptr [rsp+170h+var_130+5], r15b
0x180195dba  jz      short loc_180195DDA
0x180195dbc  mov     rcx, [rdi+8]
0x180195dc0  lea     r9, [rsp+170h+var_130]
0x180195dc5  mov     edx, 7
0x180195dca  lea     r8d, [rdx+0Ah]
0x180195dce  call    cs:__imp_ucol_setAttribute
0x180195dd5  nop     dword ptr [rax+rax+00h]
0x180195dda  test    r12d, r12d
0x180195ddd  jnz     short loc_180195DE6
0x180195ddf  lea     r8d, [r12+19h]
0x180195de4  jmp     short loc_180195DF1
0x180195de6  cmp     r12d, 1
  ... truncated ...
```
