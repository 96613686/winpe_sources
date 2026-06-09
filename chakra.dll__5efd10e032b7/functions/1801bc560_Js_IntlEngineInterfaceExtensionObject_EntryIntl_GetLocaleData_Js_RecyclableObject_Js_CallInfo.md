# Js::IntlEngineInterfaceExtensionObject::EntryIntl_GetLocaleData(Js::RecyclableObject *,Js::CallInfo,...)

- ea: `0x1801bc560`
- end: `0x1801bd738`
- name: `?EntryIntl_GetLocaleData@IntlEngineInterfaceExtensionObject@Js@@SAPEAXPEAVRecyclableObject@2@UCallInfo@2@ZZ`
- size: `4568`
- prototype: ``
- caller_count: `0`
- callee_count: `28`
- tags: `loader_planting`

## callees

- `0x1800981b4`
- `0x1800a21a4`
- `0x1800a2a0c`
- `0x1800a4b54`
- `0x18017e100`
- `0x18017ee14`
- `0x180189ef4`
- `0x1801bc560`
- `0x1801bd740`
- `0x1801bd84c`
- `0x1801bd8b4`
- `0x1801be084`
- `0x1802519b8`
- `0x180251c54`
- `0x180281388`
- `0x180391380`
- `0x18039b844`
- `0x1803bcf80`
- `0x1803c4080`
- `0x1803cf960`
- `0x1803d6a38`
- `0x1803f1e94`
- `0x18053684c`
- `0x1805368b4`
- `0x1805a9c5a`
- `0x1805a9c7e`
- `0x1805a9e80`
- `0x1805cd010`

## import_xrefs

- `msvcrt!strnlen` at `0x1801bc70f`
- `msvcrt!strnlen` at `0x1801bc70f`
- `msvcrt!free` at `0x1801bcbda`
- `msvcrt!free` at `0x1801bcbda`
- `icu!ucol_getKeywordValuesForLocale` at `0x1801bcf69`
- `icu!ucol_getKeywordValuesForLocale` at `0x1801bcf69`
- `icu!uenum_count` at `0x1801bcd89`
- `icu!uenum_count` at `0x1801bd0fd`
- `icu!uenum_count` at `0x1801bcd89`
- `icu!uenum_count` at `0x1801bd0fd`
- `icu!uenum_next` at `0x1801bcdd7`
- `icu!uenum_next` at `0x1801bcef9`
- `icu!uenum_next` at `0x1801bd160`
- `icu!uenum_next` at `0x1801bd39f`
- `icu!uenum_next` at `0x1801bcdd7`
- `icu!uenum_next` at `0x1801bcef9`
- `icu!uenum_next` at `0x1801bd160`
- `icu!uenum_next` at `0x1801bd39f`
- `icu!uloc_toUnicodeLocaleType` at `0x1801bce23`
- `icu!uloc_toUnicodeLocaleType` at `0x1801bd045`
- `icu!uloc_toUnicodeLocaleType` at `0x1801bce23`
- `icu!uloc_toUnicodeLocaleType` at `0x1801bd045`
- `icu!ucol_open` at `0x1801bcf99`
- `icu!ucol_open` at `0x1801bd3b9`
- `icu!ucol_open` at `0x1801bcf99`
- `icu!ucol_open` at `0x1801bd3b9`
- `icu!ucol_getAttribute` at `0x1801bcfba`
- `icu!ucol_getAttribute` at `0x1801bd3db`
- `icu!ucol_getAttribute` at `0x1801bcfba`
- `icu!ucol_getAttribute` at `0x1801bd3db`
- `icu!ucal_getKeywordValuesForLocale` at `0x1801bcd6d`
- `icu!ucal_getKeywordValuesForLocale` at `0x1801bcd6d`
- `icu!unumsys_open` at `0x1801bc6bf`
- `icu!unumsys_open` at `0x1801bc6bf`
- `icu!unumsys_getName` at `0x1801bc6f4`
- `icu!unumsys_getName` at `0x1801bc6f4`
- `icu!ucol_close` at `0x1801bd4da`
- `icu!ucol_close` at `0x1801bd4da`
- `icu!unumsys_close` at `0x1801bcbef`
- `icu!unumsys_close` at `0x1801bcbef`
- `icu!uenum_close` at `0x1801bcf23`
- `icu!uenum_close` at `0x1801bd0e3`
- `icu!uenum_close` at `0x1801bcf23`
- `icu!uenum_close` at `0x1801bd0e3`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
struct Js::JavascriptArray *Js::IntlEngineInterfaceExtensionObject::EntryIntl_GetLocaleData(__int64 a1, int a2, ...)
{
  ThreadContext **v3; // r8
  __int64 v4; // r12
  struct Js::JavascriptArray *Array; // rsi
  __int64 v6; // rdx
  __int64 v7; // r8
  struct Js::PropertyRecord *v8; // r15
  __int64 v9; // rdi
  __int64 KeywordValuesForLocale; // rbx
  __int64 v11; // rax
  _QWORD *v12; // r14
  int v13; // r13d
  __int64 v14; // rbx
  char *Name; // r15
  size_t v16; // rax
  size_t v17; // rdi
  unsigned __int64 v18; // rsi
  void *v19; // rax
  void (__fastcall *v20)(struct Js::JavascriptArray *, _QWORD, struct Js::JavascriptString *, _QWORD); // rdi
  struct Js::JavascriptString *v21; // rax
  void (__fastcall *v22)(struct Js::JavascriptArray *, __int64, __int64); // r15
  _QWORD *v23; // rdi
  __int64 v24; // rax
  void (__fastcall *v25)(struct Js::JavascriptArray *, __int64, __int64, _QWORD); // r14
  __int64 v26; // rax
  void (__fastcall *v27)(struct Js::JavascriptArray *, __int64, __int64); // r14
  __int64 v28; // rax
  void (__fastcall *v29)(struct Js::JavascriptArray *, __int64, __int64); // r14
  __int64 v30; // rax
  void (__fastcall *v31)(struct Js::JavascriptArray *, __int64, __int64); // r14
  __int64 v32; // rax
  void (__fastcall *v33)(struct Js::JavascriptArray *, __int64, __int64); // r14
  __int64 v34; // rax
  void (__fastcall *v35)(struct Js::JavascriptArray *, __int64, __int64); // r14
  __int64 v36; // rax
  void (__fastcall *v37)(struct Js::JavascriptArray *, __int64, __int64); // r14
  __int64 v38; // rax
  void (__fastcall *v39)(struct Js::JavascriptArray *, __int64, __int64); // r14
  __int64 v40; // rax
  void (__fastcall *v41)(struct Js::JavascriptArray *, __int64, __int64); // r14
  __int64 v42; // rax
  void (__fastcall *v43)(struct Js::JavascriptArray *, __int64, __int64); // r14
  __int64 v44; // rax
  void (__fastcall *v45)(struct Js::JavascriptArray *, __int64, __int64); // r14
  __int64 v46; // rax
  void (__fastcall *v47)(struct Js::JavascriptArray *, __int64, __int64); // r14
  __int64 v48; // rax
  void (__fastcall *v49)(struct Js::JavascriptArray *, __int64, __int64); // r14
  __int64 v50; // rax
  void (__fastcall *v51)(struct Js::JavascriptArray *, __int64, __int64); // r14
  __int64 v52; // rax
  void (__fastcall *v53)(struct Js::JavascriptArray *, __int64, __int64); // r14
  __int64 v54; // rax
  void (__fastcall *v55)(struct Js::JavascriptArray *, __int64, __int64); // r14
  __int64 v56; // rax
  void (__fastcall *v57)(struct Js::JavascriptArray *, __int64, __int64); // r14
  __int64 v58; // rax
  void (__fastcall *v59)(struct Js::JavascriptArray *, __int64, __int64); // r14
  __int64 v60; // rax
  void (__fastcall *v61)(struct Js::JavascriptArray *, __int64, __int64); // r14
  __int64 v62; // rax
  void (__fastcall *v63)(struct Js::JavascriptArray *, __int64, __int64); // r14
  __int64 v64; // rax
  void (__fastcall *v65)(struct Js::JavascriptArray *, __int64, __int64); // r14
  __int64 v66; // rax
  void (__fastcall *v68)(struct Js::JavascriptArray *, __int64, __int64); // rdi
  __int64 v69; // rax
  void (__fastcall *v70)(struct Js::JavascriptArray *, __int64, __int64, _QWORD); // rdi
  __int64 v71; // rax
  void (__fastcall *v72)(struct Js::JavascriptArray *, __int64, __int64); // rdi
  __int64 v73; // rax
  __int64 v74; // rax
  __int64 v75; // rbx
  unsigned int v76; // eax
  __int64 i; // rax
  __int64 v78; // rax
  __int64 v79; // rax
  utf8 *v80; // r15
  __int64 v81; // rdi
  unsigned __int64 v82; // rcx
  unsigned __int64 v83; // rax
  unsigned __int64 v84; // r14
  void (__fastcall *v85)(struct Js::JavascriptArray *, _QWORD, __int64, _QWORD); // rdi
  __int64 v86; // rax
  int v87; // r14d
  const char *v88; // rdi
  __int64 v89; // rax
  __int64 v90; // rax
  utf8 *v91; // r14
  __int64 v92; // r8
  int v93; // eax
  const char *v94; // rax
  __int64 v95; // r15
  __int64 v96; // rdi
  __int64 v97; // r8
  _QWORD *v98; // rbx
  __int64 v99; // r12
  __int64 v100; // r14
  __int64 v101; // rdi
  __int64 v102; // r8
  void (__fastcall *v103)(struct Js::JavascriptArray *, _QWORD, __int64, _QWORD); // rdi
  __int64 v104; // rax
  int Attribute; // r15d
  __int64 v106; // r8
  unsigned int *v107; // [rsp+28h] [rbp-D8h]
  int v108; // [rsp+30h] [rbp-D0h] BYREF
  int v109; // [rsp+34h] [rbp-CCh] BYREF
  unsigned __int64 v110; // [rsp+38h] [rbp-C8h] BYREF
  struct Js::PropertyRecord *v111; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v112; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v113; // [rsp+50h] [rbp-B0h]
  _QWORD v114[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v115; // [rsp+70h] [rbp-90h]
  int v116; // [rsp+74h] [rbp-8Ch]
  __int64 v117; // [rsp+80h] [rbp-80h]
  unsigned __int64 v118; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v119; // [rsp+90h] [rbp-70h]
  char v120; // [rsp+98h] [rbp-68h]
  __int64 v121; // [rsp+A0h] [rbp-60h]
  _BYTE v122[160]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v124; // [rsp+1C0h] [rbp+C0h] BYREF
  va_list va; // [rsp+1C0h] [rbp+C0h]
  unsigned __int64 v126; // [rsp+1C8h] [rbp+C8h]
  unsigned int *v127; // [rsp+1D0h] [rbp+D0h]
  va_list va1; // [rsp+1D8h] [rbp+D8h] BYREF

  va_start(va1, a2);
  va_start(va, a2);
  v124 = va_arg(va1, _QWORD);
  v126 = va_arg(va1, _QWORD);
  v127 = va_arg(va1, unsigned int *);
  v121 = -2;
  v3 = *(ThreadContext ***)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 1088LL);
  ThreadContext::ProbeStack(v3[110], 0xC00u, (struct Js::ScriptContext *)v3, 0);
  v4 = 0;
  v111 = 0;
  va_copy((va_list)Array, va);
  if ( (a2 & 0xFFFFFF) != 3 || HIWORD(v126) != 1 && v126 < 0x4000000000000LL || !Js::JavascriptString::Is(v127) )
    goto LABEL_2;
  v8 = *(struct Js::PropertyRecord **)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 1088LL);
  v111 = v8;
  if ( v6 == 1 )
    v9 = (unsigned int)v126;
  else
    v9 = (unsigned int)(int)COERCE_DOUBLE(v7 ^ 0xFFFC000000000000uLL);
  v108 = 0;
  memset_0(v122, 0, 0x9Du);
  KeywordValuesForLocale = v127[6];
  v11 = (*(__int64 (__fastcall **)(unsigned int *))(*(_QWORD *)v127 + 752LL))(v127);
  Js::LangtagToLocaleID_157__0(v11, (unsigned int)KeywordValuesForLocale, v122);
  v12 = (_QWORD *)*((_QWORD *)v8 + 1);
  if ( !(_DWORD)v9 )
  {
    KeywordValuesForLocale = ucol_getKeywordValuesForLocale("collation", v122, 0, &v108);
    v112 = KeywordValuesForLocale;
    if ( v108 != 7 )
    {
      if ( v108 > 0 || v108 == -124 )
        goto LABEL_121;
      v93 = uenum_count(KeywordValuesForLocale, &v108);
      Array = Js::JavascriptLibrary::CreateArray((Js::JavascriptLibrary *)v12, v93 - 1);
      if ( v108 != 7 )
      {
        if ( v108 <= 0 && v108 != -124 )
        {
          (*(void (__fastcall **)(struct Js::JavascriptArray *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)Array + 328LL))(
            Array,
            0,
            v12[126],
            0);
          v109 = 0;
          v13 = 0;
          v94 = (const char *)uenum_next(KeywordValuesForLocale, &v109, &v108);
          v4 = -1;
          goto LABEL_109;
        }
        goto LABEL_121;
      }
    }
LABEL_106:
    Js::Throw::OutOfMemory();
  }
  if ( (_DWORD)v9 == 1 )
  {
    v112 = ucol_open(v122, &v108);
    Attribute = ucol_getAttribute(v112, 2, &v108);
    if ( v108 == 7 )
      Js::Throw::OutOfMemory();
    if ( v108 > 0 || v108 == -124 )
    {
      Js::Throw::FatalInternalError(-2147467259);
      goto LABEL_167;
    }
    Array = Js::JavascriptLibrary::CreateArray((Js::JavascriptLibrary *)v12, 3u);
    v98 = v12 + 462;
    v99 = v12[506];
    if ( !v99 )
    {
      v111 = 0;
      ThreadContext::FindPropertyRecord(*(ThreadContext **)(*v98 + 880LL), L"false", 5, &v111);
      v99 = Js::ScriptContext::GetProperty<Js::PropertyString>(*v98, *((unsigned int *)v111 + 2), 0);
      v12[506] = v99;
    }
    v100 = v12[515];
    if ( !v100 )
    {
      v100 = Js::StringCache::InitializeString<0,6>(v98, L"upper");
      v98[53] = v100;
    }
    v101 = v98[54];
    if ( !v101 )
    {
      v101 = Js::StringCache::InitializeString<0,6>(v98, L"lower");
      v98[54] = v101;
    }
    if ( Attribute == 16 )
    {
      (*(void (__fastcall **)(struct Js::JavascriptArray *, _QWORD, __int64, _QWORD))(*(_QWORD *)Array + 328LL))(
        Array,
        0,
        v99,
        0);
      (*(void (__fastcall **)(struct Js::JavascriptArray *, __int64, __int64, _QWORD))(*(_QWORD *)Array + 328LL))(
        Array,
        1,
        v100,
        0);
      v102 = v101;
    }
    else
    {
      if ( Attribute == 25 )
      {
        (*(void (__fastcall **)(struct Js::JavascriptArray *, _QWORD, __int64, _QWORD))(*(_QWORD *)Array + 328LL))(
          Array,
          0,
          v100,
          0);
        v106 = v101;
      }
      else
      {
        if ( Attribute != 24 )
        {
LABEL_165:
          PlatformAgnostic::ICUHelpers::ScopedICUObject<UCollator *,&void ucol_close(UCollator *)>::~ScopedICUObject<UCollator *,&void ucol_close(UCollator *)>(&v112);
          return Array;
        }
        (*(void (__fastcall **)(struct Js::JavascriptArray *, _QWORD, __int64, _QWORD))(*(_QWORD *)Array + 328LL))(
          Array,
          0,
          v101,
          0);
        v106 = v100;
      }
      (*(void (__fastcall **)(struct Js::JavascriptArray *, __int64, __int64))(*(_QWORD *)Array + 328LL))(
        Array,
        1,
        v106);
      v102 = v99;
    }
    (*(void (__fastcall **)(struct Js::JavascriptArray *, __int64, __int64, _QWORD))(*(_QWORD *)Array + 328LL))(
      Array,
      2,
      v102,
      0);
    goto LABEL_165;
  }
  v13 = 2;
  if ( (_DWORD)v9 == 2 )
  {
    KeywordValuesForLocale = ucol_open(v122, &v108);
    v111 = (struct Js::PropertyRecord *)KeywordValuesForLocale;
    v4 = (unsigned int)ucol_getAttribute(KeywordValuesForLocale, 7, &v108);
    if ( v108 == 7 )
      Js::Throw::OutOfMemory();
    if ( v108 > 0 || v108 == -124 )
    {
      Js::Throw::FatalInternalError(-2147467259);
LABEL_153:
      if ( (unsigned int)v110 == v9 && (unsigned int)v110 < 0x7FFFFFFE )
      {
        v103 = *(void (__fastcall **)(struct Js::JavascriptArray *, _QWORD, __int64, _QWORD))(*(_QWORD *)Array + 328LL);
        v104 = Js::JavascriptString::NewWithBufferT<Js::LiteralString,0>(v8, (unsigned int)v110, v111);
        v103(Array, (unsigned int)++v13, v104, 0);
        v8 = v111;
        while ( 1 )
        {
          v94 = (const char *)uenum_next(KeywordValuesForLocale, &v109, &v108);
LABEL_109:
          v88 = v94;
          if ( !v94 )
            goto LABEL_122;
          if ( v108 == 7 )
            goto LABEL_106;
          if ( v108 > 0 || v108 == -124 || v109 <= 0 )
            break;
          if ( strcmp_0(v94, "standard") && strcmp_0(v88, "search") )
          {
            v89 = uloc_toUnicodeLocaleType("collation", v88);
            v90 = Js::ThrowOOMIfNull_char_const___(v89);
            v91 = (utf8 *)v90;
            v9 = v4;
            do
              ++v9;
            while ( *(_BYTE *)(v90 + v9) );
            v114[0] = Memory::Recycler::AllocLeaf;
            v114[1] = 0;
            v115 = 0;
            v116 = HIDWORD(v119);
            v92 = v9 + 1;
            if ( v9 == -1 )
              v92 = v4;
            v8 = (struct Js::PropertyRecord *)Memory::AllocateArray<Memory::Recycler,unsigned short,0>(
                                                *((_QWORD *)v8 + 126),
                                                v114,
                                                v92);
            LODWORD(v110) = 0;
            if ( !(unsigned int)utf8::NarrowStringToWideNoAlloc(
                                  v91,
                                  (const char *)v9,
                                  (unsigned __int64)v8,
                                  (unsigned __int16 *)(v9 + 1),
                                  (unsigned __int64)&v110,
                                  v107) )
              goto LABEL_153;
            break;
          }
        }
      }
LABEL_121:
      Js::Throw::FatalInternalError(-2147467259);
LABEL_122:
      if ( KeywordValuesForLocale )
        uenum_close(KeywordValuesForLocale);
      return Array;
    }
    Array = Js::JavascriptLibrary::CreateArray((Js::JavascriptLibrary *)v12, 2u);
    v12 += 462;
    v95 = v12[44];
    if ( v95 )
    {
LABEL_130:
      v96 = v12[43];
      if ( !v96 )
      {
        v96 = Js::StringCache::InitializeString<1,5>(v12, L"true");
        v12[43] = v96;
      }
      if ( (_DWORD)v4 == 16 )
      {
        (*(void (__fastcall **)(struct Js::JavascriptArray *, _QWORD, __int64, _QWORD))(*(_QWORD *)Array + 328LL))(
          Array,
          0,
          v95,
          0);
        v97 = v96;
      }
      else
      {
        if ( (_DWORD)v4 != 17 )
        {
LABEL_135:
          if ( KeywordValuesForLocale )
            ucol_close(KeywordValuesForLocale);
          return Array;
        }
        (*(void (__fastcall **)(struct Js::JavascriptArray *, _QWORD, __int64, _QWORD))(*(_QWORD *)Array + 328LL))(
          Array,
          0,
          v96,
          0);
        v97 = v95;
      }
      (*(void (__fastcall **)(struct Js::JavascriptArray *, __int64, __int64))(*(_QWORD *)Array + 328LL))(Array, 1, v97);
      goto LABEL_135;
    }
LABEL_167:
    v95 = Js::StringCache::InitializeString<1,6>(v12);
    v12[44] = v95;
    goto LABEL_130;
  }
  if ( (_DWORD)v9 != 3 )
  {
    if ( (_DWORD)v9 == 4 )
    {
      v14 = unumsys_open(v122, &v108);
      v113 = v14;
      if ( v108 == 7 )
        Js::Throw::OutOfMemory();
      if ( v108 <= 0 && v108 != -124 )
      {
        Name = (char *)unumsys_getName(v14);
        v117 = 0;
        v16 = strnlen(Name, 0x7FFFFFFFu);
        v17 = v16;
        v18 = 2 * v16 + 2;
        if ( v18 >= v16 )
        {
          v19 = utf8::malloc_allocator::allocate(2 * v16 + 2);
          if ( v19 )
          {
            v119 = v18;
            v117 = (__int64)v19;
            utf8::NarrowStringToWideNoAlloc(
              (utf8 *)Name,
              (const char *)v17,
              (unsigned __int64)v19,
              (unsigned __int16 *)(v17 + 1),
              (unsigned __int64)&v118,
              v107);
            v4 = v117;
          }
        }
        v120 = 1;
        Array = Js::JavascriptLibrary::CreateArray((Js::JavascriptLibrary *)v12, 0x16u);
        v20 = *(void (__fastcall **)(struct Js::JavascriptArray *, _QWORD, struct Js::JavascriptString *, _QWORD))(*(_QWORD *)Array + 328LL);
        v21 = Js::JavascriptString::NewCopySz((const unsigned __int16 *)v4, v111);
        v20(Array, 0, v21, 0);
        v22 = *(void (__fastcall **)(struct Js::JavascriptArray *, __int64, __int64))(*(_QWORD *)Array + 328LL);
        v23 = v12 + 462;
        v24 = v12[517];
        if ( !v24 )
        {
          v24 = Js::StringCache::InitializeString<0,5>(v12 + 462, L"arab");
          v12[517] = v24;
        }
        v22(Array, 1, v24);
        v25 = *(void (__fastcall **)(struct Js::JavascriptArray *, __int64, __int64, _QWORD))(*(_QWORD *)Array + 328LL);
        v26 = v23[56];
        if ( !v26 )
        {
          v26 = Js::StringCache::InitializeString<0,8>(v23, L"arabext");
          v23[56] = v26;
        }
        v25(Array, 2, v26, 0);
        v27 = *(void (__fastcall **)(struct Js::JavascriptArray *, __int64, __int64))(*(_QWORD *)Array + 328LL);
        v28 = v23[57];
        if ( !v28 )
        {
          v28 = Js::StringCache::InitializeString<0,5>(v23, L"bali");
          v23[57] = v28;
        }
        v27(Array, 3, v28);
        v29 = *(void (__fastcall **)(struct Js::JavascriptArray *, __int64, __int64))(*(_QWORD *)Array + 328LL);
        v30 = v23[58];
        if ( !v30 )
        {
          v30 = Js::StringCache::InitializeString<0,5>(v23, L"beng");
          v23[58] = v30;
        }
        v29(Array, 4, v30);
        v31 = *(void (__fastcall **)(struct Js::JavascriptArray *, __int64, __int64))(*(_QWORD *)Array + 328LL);
        v32 = v23[59];
        if ( !v32 )
        {
          v32 = Js::StringCache::InitializeString<0,5>(v23, L"deva");
          v23[59] = v32;
        }
        v31(Array, 5, v32);
        v33 = *(void (__fastcall **)(struct Js::JavascriptArray *, __int64, __int64))(*(_QWORD *)Array + 328LL);
        v34 = v23[60];
        if ( !v34 )
        {
          v34 = Js::StringCache::InitializeString<0,9>(v23, L"fullwide");
          v23[60] = v34;
        }
        v33(Array, 6, v34);
        v35 = *(void (__fastcall **)(struct Js::JavascriptArray *, __int64, __int64))(*(_QWORD *)Array + 328LL);
        v36 = v23[61];
        if ( !v36 )
        {
          v36 = Js::StringCache::InitializeString<0,5>(v23, L"gujr");
          v23[61] = v36;
        }
        v35(Array, 7, v36);
        v37 = *(void (__fastcall **)(struct Js::JavascriptArray *, __int64, __int64))(*(_QWORD *)Array + 328LL);
        v38 = v23[62];
        if ( !v38 )
        {
          v38 = Js::StringCache::InitializeString<0,5>(v23, L"guru");
          v23[62] = v38;
        }
        v37(Array, 8, v38);
        v39 = *(void (__fastcall **)(struct Js::JavascriptArray *, __int64, __int64))(*(_QWORD *)Array + 328LL);
        v40 = v23[63];
        if ( !v40 )
        {
          v40 = Js::StringCache::InitializeString<0,8>(v23, L"hanidec");
          v23[63] = v40;
        }
        v39(Array, 9, v40);
        v41 = *(void (__fastcall **)(struct Js::JavascriptArray *, __int64, __int64))(*(_QWORD *)Array + 328LL);
        v42 = v23[64];
        if ( !v42 )
        {
          v42 = Js::StringCache::InitializeString<0,5>(v23, L"khmr");
          v23[64] = v42;
        }
        v41(Array, 10, v42);
        v43 = *(void (__fastcall **)(struct Js::JavascriptArray *, __int64, __int64))(*(_QWORD *)Array + 328LL);
        v44 = v23[65];
        if ( !v44 )
        {
          v44 = Js::StringCache::InitializeString<0,5>(v23, L"knda");
          v23[65] = v44;
        }
        v43(Array, 11, v44);
        v45 = *(void (__fastcall **)(struct Js::JavascriptArray *, __int64, __int64))(*(_QWORD *)Array + 328LL);
        v46 = v23[66];
        if ( !v46 )
        {
          v46 = Js::StringCache::InitializeString<0,5>(v23, L"laoo");
          v23[66] = v46;
        }
        v45(Array, 12, v46);
        v47 = *(void (__fastcall **)(struct Js::JavascriptArray *, __int64, __int64))(*(_QWORD *)Array + 328LL);
        v48 = v23[67];
        if ( !v48 )
        {
          v48 = Js::StringCache::InitializeString<0,5>(v23, L"latn");
          v23[67] = v48;
        }
        v47(Array, 13, v48);
        v49 = *(void (__fastcall **)(struct Js::JavascriptArray *, __int64, __int64))(*(_QWORD *)Array + 328LL);
        v50 = v23[68];
        if ( !v50 )
        {
          v50 = Js::StringCache::InitializeString<0,5>(v23, L"limb");
          v23[68] = v50;
        }
        v49(Array, 14, v50);
        v51 = *(void (__fastcall **)(struct Js::JavascriptArray *, __int64, __int64))(*(_QWORD *)Array + 328LL);
        v52 = v23[69];
        if ( !v52 )
        {
          v52 = Js::StringCache::InitializeString<0,5>(v23, L"mlym");
          v23[69] = v52;
        }
        v51(Array, 15, v52);
        v53 = *(void (__fastcall **)(struct Js::JavascriptArray *, __int64, __int64))(*(_QWORD *)Array + 328LL);
        v54 = v23[70];
        if ( !v54 )
        {
          v54 = Js::StringCache::InitializeString<0,5>(v23, L"mong");
          v23[70] = v54;
        }
        v53(Array, 16, v54);
        v55 = *(void (__fastcall **)(struct Js::JavascriptArray *, __int64, __int64))(*(_QWORD *)Array + 328LL);
        v56 = v23[71];
        if ( !v56 )
        {
          v56 = Js::StringCache::InitializeString<0,5>(v23, L"mymr");
          v23[71] = v56;
        }
        v55(Array, 17, v56);
        v57 = *(void (__fastcall **)(struct Js::JavascriptArray *, __int64, __int64))(*(_QWORD *)Array + 328LL);
        v58 = v23[72];
        if ( !v58 )
        {
          v58 = Js::StringCache::InitializeString<0,5>(v23, L"orya");
          v23[72] = v58;
        }
        v57(Array, 18, v58);
        v59 = *(void (__fastcall **)(struct Js::JavascriptArray *, __int64, __int64))(*(_QWORD *)Array + 328LL);
        v60 = v23[73];
        if ( !v60 )
        {
          v60 = Js::StringCache::InitializeString<0,8>(v23, L"tamldec");
          v23[73] = v60;
        }
        v59(Array, 19, v60);
        v61 = *(void (__fastcall **)(struct Js::JavascriptArray *, __int64, __int64))(*(_QWORD *)Array + 328LL);
        v62 = v23[74];
        if ( !v62 )
        {
          v62 = Js::StringCache::InitializeString<0,5>(v23, L"telu");
          v23[74] = v62;
        }
        v61(Array, 20, v62);
        v63 = *(void (__fastcall **)(struct Js::JavascriptArray *, __int64, __int64))(*(_QWORD *)Array + 328LL);
        v64 = v23[75];
        if ( !v64 )
        {
          v64 = Js::StringCache::InitializeString<0,5>(v23, L"thai");
          v23[75] = v64;
        }
        v63(Array, 21, v64);
        v65 = *(void (__fastcall **)(struct Js::JavascriptArray *, __int64, __int64))(*(_QWORD *)Array + 328LL);
        v66 = v23[76];
        if ( !v66 )
        {
          v66 = Js::StringCache::InitializeString<0,5>(v23, L"tibt");
          v23[76] = v66;
        }
        v65(Array, 22, v66);
        if ( v4 )
          free((void *)v4);
        if ( v14 )
          unumsys_close(v14);
        return Array;
      }
      Js::Throw::FatalInternalError(-2147467259);
LABEL_173:
      v74 = Js::StringCache::InitializeString<0,4>(v14, L"h24");
      *(_QWORD *)(v14 + 640) = v74;
LABEL_77:
      ((void (__fastcall *)(struct Js::JavascriptArray *, __int64, __int64))v9)(Array, 4, v74);
      return Array;
    }
    if ( (_DWORD)v9 == 5 )
    {
      Array = Js::JavascriptLibrary::CreateArray(*((Js::JavascriptLibrary **)v8 + 1), 5u);
      (*(void (__fastcall **)(struct Js::JavascriptArray *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)Array + 328LL))(
        Array,
        0,
        v12[126],
        0);
      v68 = *(void (__fastcall **)(struct Js::JavascriptArray *, __int64, __int64))(*(_QWORD *)Array + 328LL);
      v14 = (__int64)(v12 + 462);
      v69 = v12[539];
      if ( !v69 )
      {
        v69 = Js::StringCache::InitializeString<0,4>(v12 + 462, L"h11");
        v12[539] = v69;
      }
      v68(Array, 1, v69);
      v70 = *(void (__fastcall **)(struct Js::JavascriptArray *, __int64, __int64, _QWORD))(*(_QWORD *)Array + 328LL);
      v71 = v12[540];
      if ( !v71 )
      {
        v71 = Js::StringCache::InitializeString<0,4>(v12 + 462, L"h12");
        v12[540] = v71;
      }
      v70(Array, 2, v71, 0);
      v72 = *(void (__fastcall **)(struct Js::JavascriptArray *, __int64, __int64))(*(_QWORD *)Array + 328LL);
      v73 = v12[541];
      if ( !v73 )
      {
        v73 = Js::StringCache::InitializeString<0,4>(v12 + 462, L"h23");
        v12[541] = v73;
      }
      v72(Array, 3, v73);
      v9 = *(_QWORD *)(*(_QWORD *)Array + 328LL);
      v74 = v12[542];
      if ( v74 )
        goto LABEL_77;
      goto LABEL_173;
    }
LABEL_2:
    Js::Throw::FatalInternalError(-2147467259);
    __debugbreak();
  }
  v75 = ucal_getKeywordValuesForLocale("calendar", v122, 0, &v108);
  v113 = v75;
  v76 = uenum_count(v75, &v108);
  Array = Js::JavascriptLibrary::CreateArray((Js::JavascriptLibrary *)v12, v76);
  if ( v108 == 7 )
LABEL_99:
    Js::Throw::OutOfMemory();
  if ( v108 > 0 || v108 == -124 )
  {
LABEL_100:
    Js::Throw::FatalInternalError(-2147467259);
  }
  else
  {
    v109 = 0;
    LODWORD(v112) = 0;
    for ( i = uenum_next(v75, &v109, &v108); i; i = uenum_next(v75, &v109, &v108) )
    {
      if ( v108 == 7 )
        goto LABEL_99;
      if ( v108 > 0 || v108 == -124 || v109 <= 0 )
        goto LABEL_100;
      v78 = uloc_toUnicodeLocaleType("calendar", i);
      v79 = Js::ThrowOOMIfNull_char_const___(v78);
      v80 = (utf8 *)v79;
      v81 = -1;
      do
        ++v81;
      while ( *(_BYTE *)(v79 + v81) );
      v82 = v81 + 1;
      if ( v81 == -1 )
        v82 = -1;
      if ( v82 )
      {
        v83 = 2 * v82;
        if ( !is_mul_ok(v82, 2u) )
          v83 = -1;
        v84 = (unsigned __int64)Memory::Recycler::AllocLeaf(*((Memory::Recycler **)v111 + 126), v83);
      }
      else
      {
        v84 = 8;
      }
      LODWORD(v110) = 0;
      if ( (unsigned int)utf8::NarrowStringToWideNoAlloc(
                           v80,
                           (const char *)v81,
                           v84,
                           (unsigned __int16 *)(v81 + 1),
                           (unsigned __int64)&v110,
                           v107)
        || (unsigned int)v110 != v81
        || (unsigned int)v110 >= 0x7FFFFFFE )
      {
        goto LABEL_100;
      }
      v85 = *(void (__fastcall **)(struct Js::JavascriptArray *, _QWORD, __int64, _QWORD))(*(_QWORD *)Array + 328LL);
      v86 = Js::JavascriptString::NewWithBufferT<Js::LiteralString,0>(v84, (unsigned int)v110, v111);
      v87 = v112;
      v85(Array, (unsigned int)v112, v86, 0);
      LODWORD(v112) = v87 + 1;
    }
  }
  if ( v75 )
    uenum_close(v75);
  return Array;
}

```

## disassembly

```asm
0x1801bc560  mov     rax, rsp
0x1801bc563  mov     [rax+10h], rdx
0x1801bc567  mov     [rax+8], rcx
0x1801bc56b  mov     [rax+18h], r8
0x1801bc56f  mov     [rax+20h], r9
0x1801bc573  push    rbp
0x1801bc574  push    rbx
0x1801bc575  push    rsi
0x1801bc576  push    rdi
0x1801bc577  push    r12
0x1801bc579  push    r13
0x1801bc57b  push    r14
0x1801bc57d  push    r15
0x1801bc57f  lea     rbp, [rsp-68h]
0x1801bc584  sub     rsp, 168h
0x1801bc58b  mov     [rbp+0A0h+var_100], 0FFFFFFFFFFFFFFFEh
0x1801bc593  mov     rax, cs:__security_cookie
0x1801bc59a  xor     rax, rsp
0x1801bc59d  mov     [rbp+0A0h+var_50], rax
0x1801bc5a1  mov     rbx, [rbp+0A0h+arg_0]
0x1801bc5a8  mov     rax, [rbx+8]
0x1801bc5ac  mov     rcx, [rax+8]
0x1801bc5b0  mov     rcx, [rcx+440h]
0x1801bc5b7  xor     r9d, r9d; void *
0x1801bc5ba  mov     r8, rcx; struct Js::ScriptContext *
0x1801bc5bd  mov     edx, 0C00h; unsigned __int64
0x1801bc5c2  mov     rcx, [rcx+370h]; this
0x1801bc5c9  call    ?ProbeStack@ThreadContext@@QEAAX_KPEAVScriptContext@Js@@PEAX@Z; ThreadContext::ProbeStack(unsigned __int64,Js::ScriptContext *,void *)
0x1801bc5ce  xor     r12d, r12d
0x1801bc5d1  mov     [rsp+1A0h+var_160], r12
0x1801bc5d6  lea     rsi, [rbp+0A0h+arg_10]
0x1801bc5dd  mov     eax, [rbp+0A0h+arg_8]
0x1801bc5e3  and     eax, 0FFFFFFh
0x1801bc5e8  cmp     eax, 3
0x1801bc5eb  jz      short loc_1801BC5F8
0x1801bc5ed  mov     ecx, 80004005h; int
0x1801bc5f2  call    ?FatalInternalError@Throw@Js@@SAXJ@Z; Js::Throw::FatalInternalError(long)
0x1801bc5f7  int     3; Trap to Debugger
0x1801bc5f8  mov     r8, [rsi+8]
0x1801bc5fc  mov     rdx, r8
0x1801bc5ff  shr     rdx, 30h
0x1801bc603  mov     rax, 4000000000000h
0x1801bc60d  cmp     rdx, 1
0x1801bc611  jz      short loc_1801BC618
0x1801bc613  cmp     r8, rax
0x1801bc616  jb      short loc_1801BC5ED
0x1801bc618  mov     rcx, [rsi+10h]; void *
0x1801bc61c  call    ?Is@JavascriptString@Js@@SA_NPEAX@Z; Js::JavascriptString::Is(void *)
0x1801bc621  test    al, al
0x1801bc623  jz      short loc_1801BC5ED
0x1801bc625  mov     rax, [rbx+8]
0x1801bc629  mov     rcx, [rax+8]
0x1801bc62d  mov     r15, [rcx+440h]
0x1801bc634  mov     [rsp+1A0h+var_160], r15
0x1801bc639  cmp     rdx, 1
0x1801bc63d  jnz     loc_1801BCC20
0x1801bc643  mov     edi, [rsi+8]
0x1801bc646  mov     [rsp+1A0h+var_170], r12d
0x1801bc64b  xor     edx, edx; Val
0x1801bc64d  mov     r8d, 9Dh; Size
0x1801bc653  lea     rcx, [rbp+0A0h+var_F0]; void *
0x1801bc657  call    memset_0
0x1801bc65c  mov     rcx, [rsi+10h]
0x1801bc660  mov     ebx, [rcx+18h]
0x1801bc663  mov     rax, [rcx]
0x1801bc666  mov     rax, [rax+2F0h]
0x1801bc66d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bc672  lea     r8, [rbp+0A0h+var_F0]
0x1801bc676  mov     edx, ebx
0x1801bc678  mov     rcx, rax
0x1801bc67b  call    Js__LangtagToLocaleID_157__0
0x1801bc680  mov     r14, [r15+8]
0x1801bc684  test    edi, edi
0x1801bc686  jz      loc_1801BCF56
0x1801bc68c  cmp     edi, 1
0x1801bc68f  jz      loc_1801BD3B0
0x1801bc695  mov     r13d, 2
0x1801bc69b  cmp     edi, r13d
0x1801bc69e  jz      loc_1801BCF90
0x1801bc6a4  cmp     edi, 3
0x1801bc6a7  jz      loc_1801BCD5A
0x1801bc6ad  cmp     edi, 4
0x1801bc6b0  jnz     loc_1801BCC3B
0x1801bc6b6  lea     rdx, [rsp+1A0h+var_170]
0x1801bc6bb  lea     rcx, [rbp+0A0h+var_F0]
0x1801bc6bf  call    cs:__imp_unumsys_open
0x1801bc6c6  nop     dword ptr [rax+rax+00h]
0x1801bc6cb  mov     rbx, rax
0x1801bc6ce  mov     [rsp+1A0h+var_150], rax
0x1801bc6d3  mov     eax, [rsp+1A0h+var_170]
0x1801bc6d7  cmp     eax, 7
0x1801bc6da  jz      loc_1801BCF50
0x1801bc6e0  test    eax, eax
0x1801bc6e2  jg      loc_1801BD712
0x1801bc6e8  cmp     eax, 0FFFFFF84h
0x1801bc6eb  jz      loc_1801BD712
0x1801bc6f1  mov     rcx, rbx
0x1801bc6f4  call    cs:__imp_unumsys_getName
0x1801bc6fb  nop     dword ptr [rax+rax+00h]
0x1801bc700  mov     r15, rax
0x1801bc703  mov     [rbp+0A0h+var_120], r12
0x1801bc707  mov     edx, 7FFFFFFFh; MaxCount
0x1801bc70c  mov     rcx, rax; String
0x1801bc70f  call    cs:__imp_strnlen
0x1801bc716  nop     dword ptr [rax+rax+00h]
0x1801bc71b  mov     rdi, rax
0x1801bc71e  lea     rsi, ds:2[rax*2]
0x1801bc726  cmp     rsi, rax
0x1801bc729  jb      short loc_1801BC75F
0x1801bc72b  mov     rcx, rsi; unsigned __int64
0x1801bc72e  call    ?allocate@malloc_allocator@utf8@@SAPEAX_K@Z; utf8::malloc_allocator::allocate(unsigned __int64)
0x1801bc733  test    rax, rax
0x1801bc736  jz      short loc_1801BC75F
0x1801bc738  mov     [rbp+0A0h+var_110], rsi
0x1801bc73c  mov     [rbp+0A0h+var_120], rax
0x1801bc740  lea     r9, [rdi+1]; unsigned __int16 *
0x1801bc744  lea     rcx, [rbp+0A0h+var_118]
0x1801bc748  mov     [rsp+1A0h+var_180], rcx; unsigned __int64
0x1801bc74d  mov     r8, rax; unsigned __int64
0x1801bc750  mov     rdx, rdi; char *
0x1801bc753  mov     rcx, r15; this
0x1801bc756  call    ?NarrowStringToWideNoAlloc@utf8@@YAJPEBD_KPEAG1PEAI@Z; utf8::NarrowStringToWideNoAlloc(char const *,unsigned __int64,ushort *,unsigned __int64,uint *)
0x1801bc75b  mov     r12, [rbp+0A0h+var_120]
0x1801bc75f  mov     [rbp+0A0h+var_108], 1
0x1801bc763  mov     edx, 16h; unsigned int
0x1801bc768  mov     rcx, r14; this
0x1801bc76b  call    ?CreateArray@JavascriptLibrary@Js@@QEAAPEAVJavascriptArray@2@I@Z; Js::JavascriptLibrary::CreateArray(uint)
0x1801bc770  mov     rsi, rax
0x1801bc773  mov     rax, [rax]
0x1801bc776  mov     rdi, [rax+148h]
0x1801bc77d  mov     rdx, [rsp+1A0h+var_160]; struct Js::ScriptContext *
0x1801bc782  mov     rcx, r12; Source
0x1801bc785  call    ?NewCopySz@JavascriptString@Js@@SAPEAV12@PEBGPEAVScriptContext@2@@Z; Js::JavascriptString::NewCopySz(ushort const *,Js::ScriptContext *)
0x1801bc78a  xor     r9d, r9d
0x1801bc78d  mov     r8, rax
0x1801bc790  xor     edx, edx
0x1801bc792  mov     rcx, rsi
0x1801bc795  mov     rax, rdi
0x1801bc798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bc79d  mov     rax, [rsi]
0x1801bc7a0  mov     r15, [rax+148h]
0x1801bc7a7  lea     rdi, [r14+0E70h]
0x1801bc7ae  mov     rax, [rdi+1B8h]
0x1801bc7b5  test    rax, rax
0x1801bc7b8  jz      loc_1801BD4F6
0x1801bc7be  xor     r9d, r9d
0x1801bc7c1  mov     r8, rax
0x1801bc7c4  lea     edx, [r9+1]
0x1801bc7c8  mov     rcx, rsi
0x1801bc7cb  mov     rax, r15
0x1801bc7ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bc7d3  mov     rax, [rsi]
0x1801bc7d6  mov     r14, [rax+148h]
0x1801bc7dd  mov     rax, [rdi+1C0h]
0x1801bc7e4  test    rax, rax
0x1801bc7e7  jz      loc_1801BD511
0x1801bc7ed  xor     r9d, r9d
0x1801bc7f0  mov     r8, rax
0x1801bc7f3  mov     edx, r13d
0x1801bc7f6  mov     rcx, rsi
0x1801bc7f9  mov     rax, r14
0x1801bc7fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bc801  mov     rax, [rsi]
0x1801bc804  mov     r14, [rax+148h]
0x1801bc80b  mov     rax, [rdi+1C8h]
0x1801bc812  test    rax, rax
0x1801bc815  jz      loc_1801BD52C
0x1801bc81b  xor     r9d, r9d
0x1801bc81e  mov     r8, rax
0x1801bc821  lea     edx, [r9+3]
0x1801bc825  mov     rcx, rsi
0x1801bc828  mov     rax, r14
0x1801bc82b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bc830  mov     rax, [rsi]
0x1801bc833  mov     r14, [rax+148h]
0x1801bc83a  mov     rax, [rdi+1D0h]
0x1801bc841  test    rax, rax
0x1801bc844  jz      loc_1801BD547
0x1801bc84a  xor     r9d, r9d
0x1801bc84d  mov     r8, rax
0x1801bc850  lea     edx, [r9+4]
0x1801bc854  mov     rcx, rsi
0x1801bc857  mov     rax, r14
0x1801bc85a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bc85f  mov     rax, [rsi]
0x1801bc862  mov     r14, [rax+148h]
0x1801bc869  mov     rax, [rdi+1D8h]
0x1801bc870  test    rax, rax
0x1801bc873  jnz     short loc_1801BC88B
0x1801bc875  lea     rdx, aDeva; "deva"
0x1801bc87c  mov     rcx, rdi
0x1801bc87f  call    ??$InitializeString@$0A@$04@StringCache@Js@@AEBAPEAVJavascriptString@1@AEAY04$$CBG@Z; Js::StringCache::InitializeString<0,5>(ushort const (&)[5])
0x1801bc884  mov     [rdi+1D8h], rax
0x1801bc88b  xor     r9d, r9d
0x1801bc88e  mov     r8, rax
0x1801bc891  lea     edx, [r9+5]
0x1801bc895  mov     rcx, rsi
0x1801bc898  mov     rax, r14
0x1801bc89b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bc8a0  mov     rax, [rsi]
0x1801bc8a3  mov     r14, [rax+148h]
0x1801bc8aa  mov     rax, [rdi+1E0h]
0x1801bc8b1  test    rax, rax
0x1801bc8b4  jnz     short loc_1801BC8CC
0x1801bc8b6  lea     rdx, aFullwide; "fullwide"
0x1801bc8bd  mov     rcx, rdi
0x1801bc8c0  call    ??$InitializeString@$0A@$08@StringCache@Js@@AEBAPEAVJavascriptString@1@AEAY08$$CBG@Z; Js::StringCache::InitializeString<0,9>(ushort const (&)[9])
0x1801bc8c5  mov     [rdi+1E0h], rax
0x1801bc8cc  xor     r9d, r9d
0x1801bc8cf  mov     r8, rax
0x1801bc8d2  lea     edx, [r9+6]
0x1801bc8d6  mov     rcx, rsi
0x1801bc8d9  mov     rax, r14
0x1801bc8dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bc8e1  mov     rax, [rsi]
0x1801bc8e4  mov     r14, [rax+148h]
0x1801bc8eb  mov     rax, [rdi+1E8h]
0x1801bc8f2  test    rax, rax
0x1801bc8f5  jz      loc_1801BD562
0x1801bc8fb  xor     r9d, r9d
0x1801bc8fe  mov     r8, rax
0x1801bc901  lea     edx, [r9+7]
0x1801bc905  mov     rcx, rsi
0x1801bc908  mov     rax, r14
0x1801bc90b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bc910  mov     rax, [rsi]
0x1801bc913  mov     r14, [rax+148h]
0x1801bc91a  mov     rax, [rdi+1F0h]
0x1801bc921  test    rax, rax
0x1801bc924  jz      loc_1801BD57D
0x1801bc92a  xor     r9d, r9d
0x1801bc92d  mov     r8, rax
0x1801bc930  lea     edx, [r9+8]
0x1801bc934  mov     rcx, rsi
0x1801bc937  mov     rax, r14
0x1801bc93a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bc93f  mov     rax, [rsi]
0x1801bc942  mov     r14, [rax+148h]
0x1801bc949  mov     rax, [rdi+1F8h]
0x1801bc950  test    rax, rax
0x1801bc953  jz      loc_1801BD598
0x1801bc959  xor     r9d, r9d
0x1801bc95c  mov     r8, rax
0x1801bc95f  lea     edx, [r9+9]
0x1801bc963  mov     rcx, rsi
0x1801bc966  mov     rax, r14
0x1801bc969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bc96e  mov     rax, [rsi]
0x1801bc971  mov     r14, [rax+148h]
0x1801bc978  mov     rax, [rdi+200h]
0x1801bc97f  test    rax, rax
0x1801bc982  jz      loc_1801BD5B3
0x1801bc988  xor     r9d, r9d
0x1801bc98b  mov     r8, rax
0x1801bc98e  lea     edx, [r9+0Ah]
0x1801bc992  mov     rcx, rsi
0x1801bc995  mov     rax, r14
0x1801bc998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bc99d  mov     rax, [rsi]
0x1801bc9a0  mov     r14, [rax+148h]
0x1801bc9a7  mov     rax, [rdi+208h]
0x1801bc9ae  test    rax, rax
0x1801bc9b1  jz      loc_1801BD5CE
0x1801bc9b7  xor     r9d, r9d
0x1801bc9ba  mov     r8, rax
0x1801bc9bd  lea     edx, [r9+0Bh]
0x1801bc9c1  mov     rcx, rsi
0x1801bc9c4  mov     rax, r14
0x1801bc9c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bc9cc  mov     rax, [rsi]
0x1801bc9cf  mov     r14, [rax+148h]
0x1801bc9d6  mov     rax, [rdi+210h]
0x1801bc9dd  test    rax, rax
0x1801bc9e0  jz      loc_1801BD5E9
0x1801bc9e6  xor     r9d, r9d
0x1801bc9e9  mov     r8, rax
0x1801bc9ec  lea     edx, [r9+0Ch]
0x1801bc9f0  mov     rcx, rsi
0x1801bc9f3  mov     rax, r14
0x1801bc9f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bc9fb  mov     rax, [rsi]
0x1801bc9fe  mov     r14, [rax+148h]
0x1801bca05  mov     rax, [rdi+218h]
0x1801bca0c  test    rax, rax
0x1801bca0f  jz      loc_1801BD604
0x1801bca15  xor     r9d, r9d
0x1801bca18  mov     r8, rax
0x1801bca1b  lea     edx, [r9+0Dh]
0x1801bca1f  mov     rcx, rsi
0x1801bca22  mov     rax, r14
0x1801bca25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bca2a  mov     rax, [rsi]
0x1801bca2d  mov     r14, [rax+148h]
0x1801bca34  mov     rax, [rdi+220h]
0x1801bca3b  test    rax, rax
0x1801bca3e  jz      loc_1801BD61F
0x1801bca44  xor     r9d, r9d
0x1801bca47  mov     r8, rax
0x1801bca4a  lea     edx, [r9+0Eh]
0x1801bca4e  mov     rcx, rsi
  ... truncated ...
```
