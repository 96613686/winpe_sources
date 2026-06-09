# Js::IntlEngineInterfaceExtensionObject::EntryIntl_FormatDateTime(Js::RecyclableObject *,Js::CallInfo,...)

- ea: `0x180281b20`
- end: `0x180282420`
- name: `?EntryIntl_FormatDateTime@IntlEngineInterfaceExtensionObject@Js@@SAPEAXPEAVRecyclableObject@2@UCallInfo@2@ZZ`
- size: `2304`
- prototype: ``
- caller_count: `0`
- callee_count: `30`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800a21a4`
- `0x1800a2a0c`
- `0x1800a4b54`
- `0x180189ef4`
- `0x1801947dc`
- `0x1801a25bc`
- `0x1801a3b24`
- `0x1801bd8b4`
- `0x180231404`
- `0x180281b20`
- `0x180282428`
- `0x1802824d0`
- `0x180282e70`
- `0x180282edc`
- `0x180391380`
- `0x1803bcf80`
- `0x1803c4080`
- `0x1803d6a38`
- `0x1803e25ec`
- `0x180507ca4`
- `0x18050c48c`
- `0x180536658`
- `0x18053684c`
- `0x180536880`
- `0x1805368b4`
- `0x180536c8c`
- `0x180536e34`
- `0x1805a9c5a`
- `0x1805a9e80`
- `0x1805cd010`

## import_xrefs

- `icu!ufieldpositer_open` at `0x180281f6d`
- `icu!ufieldpositer_open` at `0x180281f6d`
- `icu!ufieldpositer_next` at `0x180282003`
- `icu!ufieldpositer_next` at `0x180282360`
- `icu!ufieldpositer_next` at `0x180282003`
- `icu!ufieldpositer_next` at `0x180282360`
- `icu!udat_open` at `0x180281e54`
- `icu!udat_open` at `0x180281e54`
- `icu!udat_getCalendar` at `0x180281e9a`
- `icu!udat_getCalendar` at `0x180281e9a`
- `icu!ucal_setGregorianChange` at `0x180281eb6`
- `icu!ucal_setGregorianChange` at `0x180281eb6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Js::IntlEngineInterfaceExtensionObject::EntryIntl_FormatDateTime(
        __int64 a1,
        int a2,
        __int64 a3,
        _QWORD *a4,
        unsigned __int64 a5,
        void *a6,
        _DWORD *a7)
{
  ThreadContext **v8; // r8
  __int64 v9; // r8
  struct Js::ScriptContext *v10; // r15
  int v11; // r13d
  __int64 v12; // rdx
  _DWORD *v13; // rsi
  _DWORD *v14; // r12
  _DWORD *v15; // rdi
  unsigned int v16; // ebx
  __int64 v17; // rax
  int v18; // esi
  __int64 v19; // rbx
  int v20; // edi
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 Calendar; // rax
  __int64 v25; // rdx
  Js::JavascriptLibrary *v27; // rsi
  struct Js::JavascriptArray *Array; // r13
  int v29; // r14d
  int v30; // r12d
  unsigned int v31; // eax
  unsigned int v32; // ecx
  _QWORD *v33; // rbx
  __int64 v34; // rdi
  __int64 v35; // rax
  int v36; // ecx
  __int64 v37; // rax
  int v38; // ebx
  __int64 v39; // rax
  int v40; // [rsp+40h] [rbp-C0h] BYREF
  int v41; // [rsp+44h] [rbp-BCh] BYREF
  int v42; // [rsp+48h] [rbp-B8h] BYREF
  void *v43; // [rsp+50h] [rbp-B0h] BYREF
  void *v44; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v45; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v46; // [rsp+68h] [rbp-98h] BYREF
  void *v47; // [rsp+70h] [rbp-90h] BYREF
  double *v48; // [rsp+78h] [rbp-88h]
  __int64 *v49; // [rsp+80h] [rbp-80h]
  __int64 v50; // [rsp+90h] [rbp-70h] BYREF
  double v51[3]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v52[160]; // [rsp+B0h] [rbp-50h] BYREF

  v51[1] = NAN;
  v8 = *(ThreadContext ***)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 1088LL);
  ThreadContext::ProbeStack(v8[110], 0xC00u, (struct Js::ScriptContext *)v8, 0);
  v47 = 0;
  if ( (a2 & 0xFFFFFF) != 5
    || !Js::DynamicObject::Is(a4)
    || HIWORD(a5) != 1 && a5 < 0x4000000000000LL
    || !Js::JavascriptBoolean::Is(a6)
    || !Js::JavascriptBoolean::Is(a7) )
  {
    Js::Throw::FatalInternalError(-2147467259);
    JUMPOUT(0x18028241FLL);
  }
  v10 = *(struct Js::ScriptContext **)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 1088LL);
  v11 = *(_DWORD *)(v9 + 16);
  v51[0] = Js::TimeClip(a5);
  if ( Js::NumberUtilities::IsNan(v51[0]) )
    Js::JavascriptError::ThrowRangeError(v10, -2146823164, 0);
  if ( a7[4] )
  {
    v12 = 110;
  }
  else
  {
    v12 = 109;
    if ( !v11 )
      v12 = 108;
  }
  Js::BuiltInCountTracker::Increment(*((_QWORD *)v10 + 122) + 16LL, v12);
  v50 = 0;
  v45 = 0;
  v40 = 0;
  if ( (*(unsigned int (__fastcall **)(_QWORD *, _QWORD *, __int64, __int64 *, _QWORD, struct Js::ScriptContext *))(*a4 + 160LL))(
         a4,
         a4,
         11,
         &v50,
         0,
         v10) )
  {
    v45 = v50;
  }
  else
  {
    v43 = 0;
    Js::JavascriptOperators::GetProperty_Internal<0>(
      (int)a4,
      (int)a4,
      0,
      503,
      (__int64)&v43,
      *(_QWORD *)(*(_QWORD *)(a4[1] + 8LL) + 1088LL),
      0);
    v13 = v43;
    if ( !v43 || !Js::JavascriptString::Is(v43) )
    {
      Js::Throw::FatalInternalError(-2147467259);
      __debugbreak();
    }
    v44 = 0;
    Js::JavascriptOperators::GetProperty_Internal<0>(
      (int)a4,
      (int)a4,
      0,
      578,
      (__int64)&v44,
      *(_QWORD *)(*(_QWORD *)(a4[1] + 8LL) + 1088LL),
      0);
    v14 = v44;
    if ( !v44 || !Js::JavascriptString::Is(v44) )
    {
      Js::Throw::FatalInternalError(-2147467259);
      __debugbreak();
    }
    v47 = 0;
    Js::JavascriptOperators::GetProperty_Internal<0>(
      (int)a4,
      (int)a4,
      0,
      576,
      (__int64)&v47,
      *(_QWORD *)(*(_QWORD *)(a4[1] + 8LL) + 1088LL),
      0);
    v15 = v47;
    if ( !v47 || !Js::JavascriptString::Is(v47) )
    {
      Js::Throw::FatalInternalError(-2147467259);
      __debugbreak();
    }
    memset_0(v52, 0, 0x9Du);
    v16 = v13[6];
    v17 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v13 + 752LL))(v13);
    Js::LangtagToLocaleID_157__0(v17, v16, v52);
    v18 = v15[6];
    v19 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v15 + 752LL))(v15);
    v20 = v14[6];
    v21 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v14 + 752LL))(v14);
    v22 = udat_open(4294967294LL, 4294967294LL, v52, v21, v20, v19, v18, &v40);
    v23 = Js::FinalizableICUObject<void * *,&void udat_close(void * *)>::New(*((_QWORD *)v10 + 126), v22);
    v45 = v23;
    if ( v40 == 7 )
      Js::Throw::OutOfMemory();
    if ( v40 > 0
      || v40 == -124
      || (Calendar = udat_getCalendar(*(_QWORD *)(v23 + 8)), ucal_setGregorianChange(Calendar, v25, &v40), v40 > 0)
      && v40 != 16 )
    {
LABEL_94:
      Js::Throw::FatalInternalError(-2147467259);
      __debugbreak();
    }
    v40 = 0;
    (*(void (__fastcall **)(_QWORD *, __int64, __int64))(*a4 + 200LL))(a4, 11, v45);
  }
  v43 = 0;
  LODWORD(v44) = 0;
  if ( !v11 )
  {
    v47 = &v45;
    v48 = v51;
    Js::EnsureBuffer__lambda_b53ca0f8457d9282c575e6d41a9ae4aa___(&v47, *((_QWORD *)v10 + 126), &v43, &v44);
    return Js::JavascriptString::NewWithBufferT<Js::LiteralString,0>(v43, (unsigned int)v44, v10);
  }
  v46 = ufieldpositer_open(&v40);
  if ( v40 == 7 )
    Js::Throw::OutOfMemory();
  if ( v40 > 0 || v40 == -124 )
  {
LABEL_93:
    Js::Throw::FatalInternalError(-2147467259);
    goto LABEL_94;
  }
  v47 = &v45;
  v48 = v51;
  v49 = &v46;
  Js::EnsureBuffer__lambda_a82c8773195ad907d3f462c69baf147f___(&v47, *((_QWORD *)v10 + 126), &v43, &v44);
  v27 = (Js::JavascriptLibrary *)*((_QWORD *)v10 + 1);
  Array = Js::JavascriptLibrary::CreateArray(v27, 0);
  v41 = 0;
  v42 = 0;
  v29 = 0;
  v30 = 0;
  v31 = ufieldpositer_next(v46, &v41, &v42);
  while ( (v31 & 0x80000000) == 0 )
  {
    if ( v31 > 0x11 )
    {
      if ( v31 > 0x1A )
      {
        if ( v31 != 29 )
        {
          if ( v31 == 30 )
          {
LABEL_76:
            v33 = (_QWORD *)((char *)v27 + 3696);
            v34 = *((_QWORD *)v27 + 544);
            if ( v34 )
              goto LABEL_81;
            v35 = Js::StringCache::InitializeString<0,5>((char *)v27 + 3696, L"year");
            *((_QWORD *)v27 + 544) = v35;
            goto LABEL_80;
          }
          if ( v31 != 31 && v31 - 32 >= 2 )
          {
LABEL_74:
            v33 = (_QWORD *)((char *)v27 + 3696);
            v34 = *((_QWORD *)v27 + 554);
            if ( v34 )
              goto LABEL_81;
            v35 = Js::StringCache::InitializeString<0,8>((char *)v27 + 3696, L"unknown");
            *((_QWORD *)v27 + 554) = v35;
            goto LABEL_80;
          }
        }
      }
      else
      {
        switch ( v31 )
        {
          case 0x1Au:
            goto LABEL_68;
          case 0x13u:
            goto LABEL_66;
          case 0x14u:
            goto LABEL_76;
        }
        if ( v31 != 23 && v31 != 24 )
        {
          if ( v31 != 25 )
            goto LABEL_74;
LABEL_66:
          v33 = (_QWORD *)((char *)v27 + 3696);
          v34 = *((_QWORD *)v27 + 550);
          if ( v34 )
            goto LABEL_81;
          v35 = Js::StringCache::InitializeString<0,8>((char *)v27 + 3696, L"weekday");
          *((_QWORD *)v27 + 550) = v35;
          goto LABEL_80;
        }
      }
LABEL_78:
      v33 = (_QWORD *)((char *)v27 + 3696);
      v34 = *((_QWORD *)v27 + 552);
      if ( v34 )
        goto LABEL_81;
      v35 = Js::StringCache::InitializeString<0,13>((char *)v27 + 3696, L"timeZoneName");
      *((_QWORD *)v27 + 552) = v35;
      goto LABEL_80;
    }
    if ( v31 == 17 )
      goto LABEL_78;
    if ( v31 > 6 )
    {
      if ( v31 == 7 )
      {
        v33 = (_QWORD *)((char *)v27 + 3696);
        v34 = *((_QWORD *)v27 + 549);
        if ( v34 )
          goto LABEL_81;
        v35 = Js::StringCache::InitializeString<0,7>((char *)v27 + 3696, L"second");
        *((_QWORD *)v27 + 549) = v35;
        goto LABEL_80;
      }
      if ( v31 == 9 )
        goto LABEL_66;
      v32 = v31 - 14;
      if ( v31 == 14 )
      {
        v33 = (_QWORD *)((char *)v27 + 3696);
        v34 = *((_QWORD *)v27 + 551);
        if ( v34 )
          goto LABEL_81;
        v35 = Js::StringCache::InitializeString<0,10>((char *)v27 + 3696, L"dayPeriod");
        *((_QWORD *)v27 + 551) = v35;
        goto LABEL_80;
      }
    }
    else
    {
      switch ( v31 )
      {
        case 6u:
          v33 = (_QWORD *)((char *)v27 + 3696);
          v34 = *((_QWORD *)v27 + 548);
          if ( v34 )
            goto LABEL_81;
          v35 = Js::StringCache::InitializeString<0,7>((char *)v27 + 3696, L"minute");
          *((_QWORD *)v27 + 548) = v35;
          goto LABEL_80;
        case 0u:
          v33 = (_QWORD *)((char *)v27 + 3696);
          v34 = *((_QWORD *)v27 + 543);
          if ( v34 )
            goto LABEL_81;
          v35 = Js::StringCache::InitializeString<0,4>((char *)v27 + 3696, L"era");
          *((_QWORD *)v27 + 543) = v35;
          goto LABEL_80;
        case 1u:
          goto LABEL_76;
        case 2u:
LABEL_68:
          v33 = (_QWORD *)((char *)v27 + 3696);
          v34 = *((_QWORD *)v27 + 545);
          if ( v34 )
            goto LABEL_81;
          v35 = Js::StringCache::InitializeString<0,6>((char *)v27 + 3696, L"month");
          *((_QWORD *)v27 + 545) = v35;
          goto LABEL_80;
      }
      v32 = v31 - 3;
      if ( v31 == 3 )
      {
        v33 = (_QWORD *)((char *)v27 + 3696);
        v34 = *((_QWORD *)v27 + 546);
        if ( v34 )
          goto LABEL_81;
        v35 = Js::StringCache::InitializeString<0,4>((char *)v27 + 3696, L"day");
        *((_QWORD *)v27 + 546) = v35;
        goto LABEL_80;
      }
    }
    if ( v32 - 1 > 1 )
      goto LABEL_74;
    v33 = (_QWORD *)((char *)v27 + 3696);
    v34 = *((_QWORD *)v27 + 547);
    if ( v34 )
      goto LABEL_81;
    v35 = Js::StringCache::InitializeString<0,5>((char *)v27 + 3696, L"hour");
    *((_QWORD *)v27 + 547) = v35;
LABEL_80:
    v34 = v35;
LABEL_81:
    v36 = v41;
    if ( v41 > v29 )
    {
      v37 = v33[91];
      if ( !v37 )
      {
        v37 = Js::StringCache::InitializeString<0,8>(v33, L"literal");
        v33[91] = v37;
        v36 = v41;
      }
      Js::AddPartToPartsArray((_DWORD)v10, (_DWORD)Array, v30++, (_DWORD)v43, v29, v36, v37);
      v36 = v41;
    }
    Js::AddPartToPartsArray((_DWORD)v10, (_DWORD)Array, v30, (_DWORD)v43, v36, v42, v34);
    v29 = v42;
    v31 = ufieldpositer_next(v46, &v41, &v42);
    ++v30;
  }
  v38 = (int)v44;
  if ( v29 == (_DWORD)v44 )
    goto LABEL_92;
  if ( v29 >= (int)v44 )
    goto LABEL_93;
  v39 = *((_QWORD *)v27 + 553);
  if ( !v39 )
  {
    v39 = Js::StringCache::InitializeString<0,8>((char *)v27 + 3696, L"literal");
    *((_QWORD *)v27 + 553) = v39;
  }
  Js::AddPartToPartsArray((_DWORD)v10, (_DWORD)Array, v30, (_DWORD)v43, v29, v38, v39);
LABEL_92:
  PlatformAgnostic::ICUHelpers::ScopedICUObject<UFieldPositionIterator *,&void ufieldpositer_close(UFieldPositionIterator *)>::~ScopedICUObject<UFieldPositionIterator *,&void ufieldpositer_close(UFieldPositionIterator *)>(&v46);
  return (__int64)Array;
}

```

## disassembly

```asm
0x180281b20  mov     rax, rsp
0x180281b23  mov     [rax+10h], rdx
0x180281b27  mov     [rax+8], rcx
0x180281b2b  mov     [rax+18h], r8
0x180281b2f  mov     [rax+20h], r9
0x180281b33  push    rbp
0x180281b34  push    rbx
0x180281b35  push    rsi
0x180281b36  push    rdi
0x180281b37  push    r12
0x180281b39  push    r13
0x180281b3b  push    r14
0x180281b3d  push    r15
0x180281b3f  lea     rbp, [rsp-68h]
0x180281b44  sub     rsp, 168h
0x180281b4b  mov     [rbp+0A0h+var_100], 0FFFFFFFFFFFFFFFEh
0x180281b53  mov     rax, cs:__security_cookie
0x180281b5a  xor     rax, rsp
0x180281b5d  mov     [rbp+0A0h+var_50], rax
0x180281b61  mov     rbx, [rbp+0A0h+arg_0]
0x180281b68  mov     rax, [rbx+8]
0x180281b6c  mov     rcx, [rax+8]
0x180281b70  mov     rcx, [rcx+440h]
0x180281b77  xor     r9d, r9d; void *
0x180281b7a  mov     r8, rcx; struct Js::ScriptContext *
0x180281b7d  mov     edx, 0C00h; unsigned __int64
0x180281b82  mov     rcx, [rcx+370h]; this
0x180281b89  call    ?ProbeStack@ThreadContext@@QEAAX_KPEAVScriptContext@Js@@PEAX@Z; ThreadContext::ProbeStack(unsigned __int64,Js::ScriptContext *,void *)
0x180281b8e  xor     edi, edi
0x180281b90  mov     [rsp+1A0h+var_130], rdi
0x180281b95  lea     rsi, [rbp+0A0h+arg_10]
0x180281b9c  mov     eax, [rbp+0A0h+arg_8]
0x180281ba2  and     eax, 0FFFFFFh
0x180281ba7  cmp     eax, 5
0x180281baa  jnz     loc_180282415
0x180281bb0  mov     r14, [rsi+8]
0x180281bb4  mov     rcx, r14; void *
0x180281bb7  call    ?Is@DynamicObject@Js@@SA_NPEAX@Z; Js::DynamicObject::Is(void *)
0x180281bbc  test    al, al
0x180281bbe  jz      loc_180282415
0x180281bc4  mov     rax, [rsi+10h]
0x180281bc8  shr     rax, 30h
0x180281bcc  cmp     rax, 1
0x180281bd0  jz      short loc_180281BE6
0x180281bd2  mov     rax, 4000000000000h
0x180281bdc  cmp     [rsi+10h], rax
0x180281be0  jb      loc_180282415
0x180281be6  mov     r8, [rsi+18h]
0x180281bea  mov     rcx, r8; void *
0x180281bed  call    ?Is@JavascriptBoolean@Js@@SA_NPEAX@Z; Js::JavascriptBoolean::Is(void *)
0x180281bf2  test    al, al
0x180281bf4  jz      loc_180282415
0x180281bfa  mov     rcx, [rsi+20h]; void *
0x180281bfe  call    ?Is@JavascriptBoolean@Js@@SA_NPEAX@Z; Js::JavascriptBoolean::Is(void *)
0x180281c03  test    al, al
0x180281c05  jz      loc_180282415
0x180281c0b  mov     rax, [rbx+8]
0x180281c0f  mov     rdx, [rax+8]
0x180281c13  mov     r15, [rdx+440h]
0x180281c1a  mov     r13d, [r8+10h]
0x180281c1e  mov     rcx, [rsi+10h]
0x180281c22  call    Js__TimeClip
0x180281c27  movsd   [rbp+0A0h+var_108], xmm0
0x180281c2c  call    ?IsNan@NumberUtilities@Js@@SA_NN@Z; Js::NumberUtilities::IsNan(double)
0x180281c31  test    al, al
0x180281c33  jz      short loc_180281C46
0x180281c35  xor     r8d, r8d; unsigned __int16 *
0x180281c38  mov     edx, 800A1404h; int
0x180281c3d  mov     rcx, r15; struct Js::ScriptContext *
0x180281c40  call    ?ThrowRangeError@JavascriptError@Js@@SAXPEAVScriptContext@2@HPEBG@Z; Js::JavascriptError::ThrowRangeError(Js::ScriptContext *,int,ushort const *)
0x180281c46  mov     rax, [rsi+20h]
0x180281c4a  cmp     [rax+10h], edi
0x180281c4d  jz      short loc_180281C56
0x180281c4f  mov     edx, 6Eh ; 'n'
0x180281c54  jmp     short loc_180281C65
0x180281c56  test    r13d, r13d
0x180281c59  mov     edx, 6Dh ; 'm'
0x180281c5e  jnz     short loc_180281C65
0x180281c60  mov     edx, 6Ch ; 'l'
0x180281c65  mov     rcx, [r15+3D0h]
0x180281c6c  add     rcx, 10h
0x180281c70  call    ?Increment@BuiltInCountTracker@Js@@QEAAXW4BuiltInFacet@2@@Z; Js::BuiltInCountTracker::Increment(Js::BuiltInFacet)
0x180281c75  mov     [rbp+0A0h+var_110], rdi
0x180281c79  mov     [rsp+1A0h+var_140], rdi
0x180281c7e  mov     [rsp+1A0h+var_160], edi
0x180281c82  mov     rax, [r14]
0x180281c85  mov     [rsp+1A0h+var_178], r15
0x180281c8a  mov     [rsp+1A0h+var_180], rdi
0x180281c8f  lea     r9, [rbp+0A0h+var_110]
0x180281c93  mov     r8d, 0Bh
0x180281c99  mov     rdx, r14
0x180281c9c  mov     rcx, r14
0x180281c9f  mov     rax, [rax+0A0h]
0x180281ca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180281cab  test    eax, eax
0x180281cad  jz      short loc_180281CBD
0x180281caf  mov     rax, [rbp+0A0h+var_110]
0x180281cb3  mov     [rsp+1A0h+var_140], rax
0x180281cb8  jmp     loc_180281EFA
0x180281cbd  mov     [rsp+1A0h+var_150], rdi
0x180281cc2  mov     rax, [r14+8]
0x180281cc6  mov     rax, [rax+8]
0x180281cca  mov     [rsp+1A0h+var_170], rdi; struct Js::PropertyValueInfo *
0x180281ccf  mov     rax, [rax+440h]
0x180281cd6  mov     [rsp+1A0h+var_178], rax; __int64
0x180281cdb  lea     rax, [rsp+1A0h+var_150]
0x180281ce0  mov     [rsp+1A0h+var_180], rax; __int64
0x180281ce5  mov     r9d, 1F7h; int
0x180281ceb  xor     r8d, r8d; int
0x180281cee  mov     rdx, r14; int
0x180281cf1  mov     rcx, r14; int
0x180281cf4  call    ??$GetProperty_Internal@$0A@@JavascriptOperators@Js@@CAHPEAXPEAVRecyclableObject@1@_NHPEAPEAXPEAVScriptContext@1@PEAVPropertyValueInfo@1@@Z; Js::JavascriptOperators::GetProperty_Internal<0>(void *,Js::RecyclableObject *,bool,int,void * *,Js::ScriptContext *,Js::PropertyValueInfo *)
0x180281cf9  mov     rsi, [rsp+1A0h+var_150]
0x180281cfe  test    rsi, rsi
0x180281d01  jz      loc_18028240A
0x180281d07  mov     rcx, rsi; void *
0x180281d0a  call    ?Is@JavascriptString@Js@@SA_NPEAX@Z; Js::JavascriptString::Is(void *)
0x180281d0f  test    al, al
0x180281d11  jz      loc_18028240A
0x180281d17  mov     [rsp+1A0h+var_148], rdi
0x180281d1c  mov     rax, [r14+8]
0x180281d20  mov     rax, [rax+8]
0x180281d24  mov     [rsp+1A0h+var_170], rdi; struct Js::PropertyValueInfo *
0x180281d29  mov     rax, [rax+440h]
0x180281d30  mov     [rsp+1A0h+var_178], rax; __int64
0x180281d35  lea     rax, [rsp+1A0h+var_148]
0x180281d3a  mov     [rsp+1A0h+var_180], rax; __int64
0x180281d3f  mov     r9d, 242h; int
0x180281d45  xor     r8d, r8d; int
0x180281d48  mov     rdx, r14; int
0x180281d4b  mov     rcx, r14; int
0x180281d4e  call    ??$GetProperty_Internal@$0A@@JavascriptOperators@Js@@CAHPEAXPEAVRecyclableObject@1@_NHPEAPEAXPEAVScriptContext@1@PEAVPropertyValueInfo@1@@Z; Js::JavascriptOperators::GetProperty_Internal<0>(void *,Js::RecyclableObject *,bool,int,void * *,Js::ScriptContext *,Js::PropertyValueInfo *)
0x180281d53  mov     r12, [rsp+1A0h+var_148]
0x180281d58  test    r12, r12
0x180281d5b  jz      loc_1802823FF
0x180281d61  mov     rcx, r12; void *
0x180281d64  call    ?Is@JavascriptString@Js@@SA_NPEAX@Z; Js::JavascriptString::Is(void *)
0x180281d69  test    al, al
0x180281d6b  jz      loc_1802823FF
0x180281d71  mov     [rsp+1A0h+var_130], rdi
0x180281d76  mov     rax, [r14+8]
0x180281d7a  mov     rax, [rax+8]
0x180281d7e  mov     [rsp+1A0h+var_170], rdi; struct Js::PropertyValueInfo *
0x180281d83  mov     rax, [rax+440h]
0x180281d8a  mov     [rsp+1A0h+var_178], rax; __int64
0x180281d8f  lea     rax, [rsp+1A0h+var_130]
0x180281d94  mov     [rsp+1A0h+var_180], rax; __int64
0x180281d99  mov     r9d, 240h; int
0x180281d9f  xor     r8d, r8d; int
0x180281da2  mov     rdx, r14; int
0x180281da5  mov     rcx, r14; int
0x180281da8  call    ??$GetProperty_Internal@$0A@@JavascriptOperators@Js@@CAHPEAXPEAVRecyclableObject@1@_NHPEAPEAXPEAVScriptContext@1@PEAVPropertyValueInfo@1@@Z; Js::JavascriptOperators::GetProperty_Internal<0>(void *,Js::RecyclableObject *,bool,int,void * *,Js::ScriptContext *,Js::PropertyValueInfo *)
0x180281dad  mov     rdi, [rsp+1A0h+var_130]
0x180281db2  test    rdi, rdi
0x180281db5  jz      loc_1802823F4
0x180281dbb  mov     rcx, rdi; void *
0x180281dbe  call    ?Is@JavascriptString@Js@@SA_NPEAX@Z; Js::JavascriptString::Is(void *)
0x180281dc3  test    al, al
0x180281dc5  jz      loc_1802823F4
0x180281dcb  xor     edx, edx; Val
0x180281dcd  mov     r8d, 9Dh; Size
0x180281dd3  lea     rcx, [rbp+0A0h+var_F0]; void *
0x180281dd7  call    memset_0
0x180281ddc  mov     ebx, [rsi+18h]
0x180281ddf  mov     rax, [rsi]
0x180281de2  mov     rcx, rsi
0x180281de5  mov     rax, [rax+2F0h]
0x180281dec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180281df1  lea     r8, [rbp+0A0h+var_F0]
0x180281df5  mov     edx, ebx
0x180281df7  mov     rcx, rax
0x180281dfa  call    Js__LangtagToLocaleID_157__0
0x180281dff  mov     esi, [rdi+18h]
0x180281e02  mov     rax, [rdi]
0x180281e05  mov     rcx, rdi
0x180281e08  mov     rax, [rax+2F0h]
0x180281e0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180281e14  mov     rbx, rax
0x180281e17  mov     edi, [r12+18h]
0x180281e1c  mov     rdx, [r12]
0x180281e20  mov     rcx, r12
0x180281e23  mov     rax, [rdx+2F0h]
0x180281e2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180281e2f  lea     rcx, [rsp+1A0h+var_160]
0x180281e34  mov     [rsp+1A0h+var_168], rcx
0x180281e39  mov     dword ptr [rsp+1A0h+var_170], esi
0x180281e3d  mov     [rsp+1A0h+var_178], rbx
0x180281e42  mov     dword ptr [rsp+1A0h+var_180], edi
0x180281e46  mov     r9, rax
0x180281e49  lea     r8, [rbp+0A0h+var_F0]
0x180281e4d  mov     ecx, 0FFFFFFFEh
0x180281e52  mov     edx, ecx
0x180281e54  call    cs:__imp_udat_open
0x180281e5b  nop     dword ptr [rax+rax+00h]
0x180281e60  mov     rdx, rax
0x180281e63  mov     rcx, [r15+3F0h]
0x180281e6a  call    ?New@?$FinalizableICUObject@PEAPEAX$1?udat_close@@YAXPEAPEAX@Z@Js@@SAPEAV12@PEAVRecycler@Memory@@PEAPEAX@Z; Js::FinalizableICUObject<void * *,&udat_close(void * *)>::New(Memory::Recycler *,void * *)
0x180281e6f  mov     [rsp+1A0h+var_140], rax
0x180281e74  mov     ecx, [rsp+1A0h+var_160]
0x180281e78  cmp     ecx, 7
0x180281e7b  jnz     short loc_180281E83
0x180281e7d  call    ?OutOfMemory@Throw@Js@@SAXXZ; Js::Throw::OutOfMemory(void)
0x180281e83  xor     edi, edi
0x180281e85  test    ecx, ecx
0x180281e87  jg      loc_1802823E9
0x180281e8d  cmp     ecx, 0FFFFFF84h
0x180281e90  jz      loc_1802823E9
0x180281e96  mov     rcx, [rax+8]
0x180281e9a  call    cs:__imp_udat_getCalendar
0x180281ea1  nop     dword ptr [rax+rax+00h]
0x180281ea6  lea     r8, [rsp+1A0h+var_160]
0x180281eab  movsd   xmm1, cs:__real@c33eb208c2dc0000
0x180281eb3  mov     rcx, rax
0x180281eb6  call    cs:__imp_ucal_setGregorianChange
0x180281ebd  nop     dword ptr [rax+rax+00h]
0x180281ec2  mov     eax, [rsp+1A0h+var_160]
0x180281ec6  test    eax, eax
0x180281ec8  jle     short loc_180281ED3
0x180281eca  cmp     eax, 10h
0x180281ecd  jnz     loc_1802823E9
0x180281ed3  mov     [rsp+1A0h+var_160], edi
0x180281ed7  mov     rax, [r14]
0x180281eda  mov     [rsp+1A0h+var_180], rdi
0x180281edf  xor     r9d, r9d
0x180281ee2  mov     r8, [rsp+1A0h+var_140]
0x180281ee7  lea     edx, [r9+0Bh]
0x180281eeb  mov     rcx, r14
0x180281eee  mov     rax, [rax+0C8h]
0x180281ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180281efa  mov     [rsp+1A0h+var_150], rdi
0x180281eff  mov     dword ptr [rsp+1A0h+var_148], edi
0x180281f03  test    r13d, r13d
0x180281f06  jnz     short loc_180281F68
0x180281f08  lea     rax, [rsp+1A0h+var_140]
0x180281f0d  mov     [rsp+1A0h+var_130], rax
0x180281f12  lea     rax, [rbp+0A0h+var_108]
0x180281f16  mov     [rsp+1A0h+var_128], rax
0x180281f1b  lea     r9, [rsp+1A0h+var_148]
0x180281f20  lea     r8, [rsp+1A0h+var_150]
0x180281f25  mov     rdx, [r15+3F0h]
0x180281f2c  lea     rcx, [rsp+1A0h+var_130]
0x180281f31  call    Js__EnsureBuffer__lambda_b53ca0f8457d9282c575e6d41a9ae4aa___
0x180281f36  mov     r8, r15
0x180281f39  mov     edx, dword ptr [rsp+1A0h+var_148]
0x180281f3d  mov     rcx, [rsp+1A0h+var_150]
0x180281f42  call    ??$NewWithBufferT@VLiteralString@Js@@$0A@@JavascriptString@Js@@CAPEAV01@PEBGIPEAVScriptContext@1@@Z; Js::JavascriptString::NewWithBufferT<Js::LiteralString,0>(ushort const *,uint,Js::ScriptContext *)
0x180281f47  mov     rcx, [rbp+0A0h+var_50]
0x180281f4b  xor     rcx, rsp; StackCookie
0x180281f4e  call    __security_check_cookie
0x180281f53  add     rsp, 168h
0x180281f5a  pop     r15
0x180281f5c  pop     r14
0x180281f5e  pop     r13
0x180281f60  pop     r12
0x180281f62  pop     rdi
0x180281f63  pop     rsi
0x180281f64  pop     rbx
0x180281f65  pop     rbp
0x180281f66  retn
0x180281f68  lea     rcx, [rsp+1A0h+var_160]
0x180281f6d  call    cs:__imp_ufieldpositer_open
0x180281f74  nop     dword ptr [rax+rax+00h]
0x180281f79  mov     [rsp+1A0h+var_138], rax
0x180281f7e  mov     eax, [rsp+1A0h+var_160]
0x180281f82  cmp     eax, 7
0x180281f85  jnz     short loc_180281F8D
0x180281f87  call    ?OutOfMemory@Throw@Js@@SAXXZ; Js::Throw::OutOfMemory(void)
0x180281f8d  test    eax, eax
0x180281f8f  jg      loc_1802823DE
0x180281f95  cmp     eax, 0FFFFFF84h
0x180281f98  jz      loc_1802823DE
0x180281f9e  lea     rax, [rsp+1A0h+var_140]
0x180281fa3  mov     [rsp+1A0h+var_130], rax
0x180281fa8  lea     rax, [rbp+0A0h+var_108]
0x180281fac  mov     [rsp+1A0h+var_128], rax
0x180281fb1  lea     rax, [rsp+1A0h+var_138]
0x180281fb6  mov     [rbp+0A0h+var_120], rax
0x180281fba  lea     r9, [rsp+1A0h+var_148]
0x180281fbf  lea     r8, [rsp+1A0h+var_150]
0x180281fc4  mov     rdx, [r15+3F0h]
0x180281fcb  lea     rcx, [rsp+1A0h+var_130]
0x180281fd0  call    Js__EnsureBuffer__lambda_a82c8773195ad907d3f462c69baf147f___
0x180281fd5  mov     rsi, [r15+8]
0x180281fd9  xor     edx, edx; unsigned int
0x180281fdb  mov     rcx, rsi; this
0x180281fde  call    ?CreateArray@JavascriptLibrary@Js@@QEAAPEAVJavascriptArray@2@I@Z; Js::JavascriptLibrary::CreateArray(uint)
0x180281fe3  mov     r13, rax
0x180281fe6  mov     [rsp+1A0h+var_15C], edi
0x180281fea  mov     [rsp+1A0h+var_158], edi
0x180281fee  mov     r14d, edi
0x180281ff1  mov     r12d, edi
0x180281ff4  lea     r8, [rsp+1A0h+var_158]
0x180281ff9  lea     rdx, [rsp+1A0h+var_15C]
0x180281ffe  mov     rcx, [rsp+1A0h+var_138]
0x180282003  call    cs:__imp_ufieldpositer_next
0x18028200a  nop     dword ptr [rax+rax+00h]
0x18028200f  jmp     loc_18028236F
0x180282014  cmp     ecx, 11h
0x180282017  ja      loc_1802821A2
0x18028201d  jz      loc_1802822A5
  ... truncated ...
```
