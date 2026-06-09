# CPropertyProvider::GetValue(_tagpropertykey const &,tagPROPVARIANT *)

- ea: `0x180030130`
- end: `0x180030606`
- name: `?GetValue@CPropertyProvider@@UEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z`
- size: `1238`
- prototype: `int(CPropertyProvider *__hidden this, const struct _tagpropertykey *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18002f9e0`
- `0x180030130`
- `0x180031280`
- `0x1800328b0`
- `0x18006ed20`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800304dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800304dd`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1800301e2`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1800301e2`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x18003026c`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x18003026c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800302fd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800302fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800304a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800304a6`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18003021d`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18003021d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800302da`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180030499`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800304bb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800305e4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800302da`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180030499`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800304bb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800305e4`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x180030595`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x180030595`

## string_xrefs

- `0x1800304ff`: `onecoreuap\internal\shell\inc\private\cowthreadusedetection.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPropertyProvider::GetValue(
        CPropertyProvider *this,
        const struct _tagpropertykey *a2,
        PROPVARIANT *a3)
{
  char *v6; // r14
  int v7; // ebx
  int v8; // eax
  DWORD CurrentThreadId; // edi
  HRESULT ApartmentType; // ebx
  __int64 v11; // rcx
  __int64 v12; // rcx
  int GlobalSchemaCache; // r15d
  __int64 v14; // rcx
  int v15; // edi
  __int64 v17; // rax
  bool v18; // zf
  int cchValue; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+30h] [rbp-D0h]
  APTTYPE pAptType[2]; // [rsp+48h] [rbp-B8h] BYREF
  APTTYPEQUALIFIER pAptQualifier[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v23; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR StringSource[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  if ( (byte_1800F1382 & 0x10) != 0 )
    McTemplateU0jq_EtwEventWriteTransfer(this, ShellTraceId_PropertyProvider_GetValue_Start, a2, a2->pid);
  *(_OWORD *)a3 = 0;
  a3[2] = 0;
  v6 = (char *)this + 72;
  if ( !this )
    v6 = 0;
  v7 = *((_DWORD *)v6 + 11);
  v20 = 1;
  if ( v7 == 2 )
    goto LABEL_12;
  v8 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
  if ( !`_ShouldCheckApartments'::`5'::s_tbEnforceForProcess )
  {
    if ( GetModuleFileNameW(0, StringSource, 0x104u) )
    {
      if ( FindStringOrdinal(0x800000u, StringSource, -1, L"\\EXPLORER.EXE", -1, 1) != -1 )
        goto LABEL_66;
      `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = 1;
    }
    else if ( `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess != 1 )
    {
      goto LABEL_21;
    }
    if ( v7 != 1 )
      goto LABEL_12;
    if ( !(unsigned int)IsAppCompatModeEnabled(16) )
    {
      v8 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
      goto LABEL_7;
    }
LABEL_66:
    `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = 2;
    goto LABEL_21;
  }
LABEL_7:
  if ( v8 != 1 )
    goto LABEL_21;
LABEL_12:
  if ( *((_DWORD *)v6 + 10) == -3 )
    goto LABEL_21;
  CurrentThreadId = 0;
  pAptType[0] = APTTYPE_STA;
  pAptQualifier[0] = APTTYPEQUALIFIER_NONE;
  ApartmentType = CoGetApartmentType(pAptType, pAptQualifier);
  if ( ApartmentType < 0 )
    goto LABEL_20;
  if ( pAptType[0] == APTTYPE_STA )
  {
LABEL_59:
    CurrentThreadId = GetCurrentThreadId();
    goto LABEL_18;
  }
  if ( pAptType[0] == APTTYPE_MTA )
    goto LABEL_18;
  if ( pAptType[0] != APTTYPE_NA )
  {
    if ( pAptType[0] != APTTYPE_MAINSTA )
      goto LABEL_18;
    goto LABEL_59;
  }
  CurrentThreadId = -1;
LABEL_18:
  if ( CurrentThreadId != *((_DWORD *)v6 + 10) )
    ApartmentType = -2147417842;
LABEL_20:
  if ( ApartmentType < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xC8,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\cowthreadusedetection.h",
      (const char *)(unsigned int)ApartmentType,
      cchValue);
    goto LABEL_23;
  }
LABEL_21:
  ApartmentType = -2147417842;
  if ( TryEnterCriticalSection((LPCRITICAL_SECTION)v6) )
    ApartmentType = 0;
LABEL_23:
  if ( ApartmentType < 0 )
  {
    v15 = ApartmentType;
    goto LABEL_31;
  }
  *(_OWORD *)a3 = 0;
  a3[2] = 0;
  v12 = *((_QWORD *)this + 18);
  GlobalSchemaCache = -2147467259;
  if ( !v12 )
  {
    v20 = 0;
LABEL_26:
    v14 = *((_QWORD *)this + 16);
    if ( !v14 )
    {
      v15 = -2147024809;
      PropVariantClear(a3);
      goto LABEL_31;
    }
    v15 = (*(__int64 (__fastcall **)(__int64, const struct _tagpropertykey *, PROPVARIANT *))(*(_QWORD *)v14 + 40LL))(
            v14,
            a2,
            a3);
    if ( v15 < 0 )
    {
LABEL_28:
      PropVariantClear(a3);
      goto LABEL_31;
    }
    goto LABEL_36;
  }
  pAptType[0] = APTTYPE_STA;
  v15 = (*(__int64 (__fastcall **)(__int64, const struct _tagpropertykey *, PROPVARIANT *, APTTYPE *))(*(_QWORD *)v12 + 72LL))(
          v12,
          a2,
          a3,
          pAptType);
  v18 = v15 == 0;
  if ( v15 >= 0 )
  {
    if ( pAptType[0] == APTTYPE_NA )
    {
      v15 = -2147467259;
      PropVariantClear(a3);
      goto LABEL_37;
    }
    v18 = v15 == 0;
  }
  if ( v18 && pAptType[0] != APTTYPE_MTA )
  {
LABEL_36:
    v11 = 0;
    goto LABEL_38;
  }
LABEL_37:
  v11 = 0;
  v20 = 0;
  if ( v15 < 0 )
    goto LABEL_26;
LABEL_38:
  if ( *(_WORD *)a3 == 1 )
  {
    *(_WORD *)a3 = 0;
  }
  else if ( *(_WORD *)a3 )
  {
    *(_QWORD *)pAptQualifier = 0;
    if ( (byte_1800F1382 & 0x10) != 0 )
    {
      McTemplateU0jq_EtwEventWriteTransfer(
        0,
        ShellTraceId_PropertyDescription_SHGetPropertyDescription_Start,
        a2,
        a2->pid);
      v11 = 0;
    }
    *(_QWORD *)pAptQualifier = 0;
    v17 = *(_QWORD *)&a2->fmtid.Data1 - PSGUID_FOLDER_COLUMNID;
    if ( *(_QWORD *)&a2->fmtid.Data1 == PSGUID_FOLDER_COLUMNID )
      v17 = *(_QWORD *)a2->fmtid.Data4 - 0x2319B0B80447F794LL;
    if ( v17 )
    {
      v23 = 0;
      *(_QWORD *)pAptType = 0;
      GlobalSchemaCache = _GetGlobalSchemaCache((struct ISchemaCache **)pAptType);
      if ( GlobalSchemaCache >= 0 )
      {
        GlobalSchemaCache = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64 *))(**(_QWORD **)pAptType + 80LL))(
                              *(_QWORD *)pAptType,
                              &GUID_a8765599_6915_4a84_ab8c_3bf8927b06c6,
                              &v23);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptType + 16LL))(*(_QWORD *)pAptType);
        if ( GlobalSchemaCache >= 0 )
        {
          GlobalSchemaCache = (*(__int64 (__fastcall **)(__int64, const struct _tagpropertykey *, GUID *, APTTYPEQUALIFIER *))(*(_QWORD *)v23 + 24LL))(
                                v23,
                                a2,
                                &GUID_6f79d558_3e96_4549_a1d1_7d75d2288814,
                                pAptQualifier);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
        }
      }
    }
    if ( (byte_1800F1382 & 0x10) != 0 )
      McTemplateU0jq_EtwEventWriteTransfer(
        v11,
        ShellTraceId_PropertyDescription_SHGetPropertyDescription_Stop,
        a2,
        a2->pid);
    if ( GlobalSchemaCache >= 0 )
    {
      v15 = (*(__int64 (__fastcall **)(_QWORD, PROPVARIANT *))(**(_QWORD **)pAptQualifier + 168LL))(
              *(_QWORD *)pAptQualifier,
              a3);
      if ( (int)(v15 + 0x80000000) >= 0 && v15 != -2147024882 )
      {
        PropVariantClear(a3);
        v15 = 262560;
      }
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptQualifier + 16LL))(*(_QWORD *)pAptQualifier);
    }
    if ( v15 < 0 )
      goto LABEL_28;
    v11 = *((_QWORD *)this + 18);
    if ( v11 && !v20 )
      (*(void (__fastcall **)(__int64, const struct _tagpropertykey *, PROPVARIANT *))(*(_QWORD *)v11 + 48LL))(
        v11,
        a2,
        a3);
    goto LABEL_31;
  }
  if ( v15 < 0 )
    goto LABEL_28;
LABEL_31:
  if ( (byte_1800F1382 & 0x10) != 0 )
    McTemplateU0jq_EtwEventWriteTransfer(v11, ShellTraceId_PropertyProvider_GetValue_Stop, a2, a2->pid);
  if ( ApartmentType >= 0 )
    LeaveCriticalSection((LPCRITICAL_SECTION)v6);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180030130  mov     [rsp-8+arg_18], rbx
0x180030135  push    rbp
0x180030136  push    rsi
0x180030137  push    rdi
0x180030138  push    r12
0x18003013a  push    r13
0x18003013c  push    r14
0x18003013e  push    r15
0x180030140  lea     rbp, [rsp-180h]
0x180030148  sub     rsp, 280h
0x18003014f  mov     rax, cs:__security_cookie
0x180030156  xor     rax, rsp
0x180030159  mov     [rbp+1B0h+var_40], rax
0x180030160  mov     rsi, r8
0x180030163  mov     r12, rdx
0x180030166  mov     r13, rcx
0x180030169  test    cs:byte_1800F1382, 10h
0x180030170  jnz     loc_180030515
0x180030176  xorps   xmm0, xmm0
0x180030179  xor     eax, eax
0x18003017b  movups  xmmword ptr [rsi], xmm0
0x18003017e  mov     [rsi+10h], rax
0x180030182  lea     r14, [r13+48h]
0x180030186  xor     r15d, r15d
0x180030189  test    r13, r13
0x18003018c  cmovz   r14, r15
0x180030190  mov     [rsp+2B0h+var_278], r14
0x180030195  mov     ebx, [r14+2Ch]
0x180030199  mov     edi, 1
0x18003019e  mov     [rsp+2B0h+var_280], edi
0x1800301a2  cmp     ebx, 2
0x1800301a5  jz      short loc_1800301FF
0x1800301a7  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800301ad  test    eax, eax
0x1800301af  jz      loc_1800304D0
0x1800301b5  cmp     eax, edi
0x1800301b7  jnz     loc_180030269
0x1800301bd  jmp     short loc_1800301FF
0x1800301bf  mov     [rsp+2B0h+bIgnoreCase], edi; bIgnoreCase
0x1800301c3  mov     [rsp+2B0h+cchValue], 0FFFFFFFFh; int
0x1800301cb  lea     r9, StringValue; "\\EXPLORER.EXE"
0x1800301d2  mov     r8d, 0FFFFFFFFh; cchSource
0x1800301d8  lea     rdx, [rsp+2B0h+StringSource]; lpStringSource
0x1800301dd  mov     ecx, 800000h; dwFindStringOrdinalFlags
0x1800301e2  call    cs:__imp_FindStringOrdinal
0x1800301e8  cmp     eax, 0FFFFFFFFh
0x1800301eb  jnz     loc_180030548
0x1800301f1  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, edi; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800301f7  cmp     ebx, edi
0x1800301f9  jz      loc_180030590
0x1800301ff  cmp     dword ptr [r14+28h], 0FFFFFFFDh
0x180030204  jz      short loc_180030269
0x180030206  mov     edi, r15d
0x180030209  mov     [rsp+2B0h+pAptType], r15d
0x18003020e  mov     [rsp+2B0h+pAptQualifier], r15d
0x180030213  lea     rdx, [rsp+2B0h+pAptQualifier]; pAptQualifier
0x180030218  lea     rcx, [rsp+2B0h+pAptType]; pAptType
0x18003021d  call    cs:__imp_CoGetApartmentType
0x180030223  mov     ebx, eax
0x180030225  test    eax, eax
0x180030227  js      short loc_18003025A
0x180030229  mov     ecx, [rsp+2B0h+pAptType]
0x18003022d  test    ecx, ecx
0x18003022f  jz      loc_1800304A6
0x180030235  sub     ecx, 1
0x180030238  jz      short loc_180030250
0x18003023a  sub     ecx, 1
0x18003023d  jz      loc_1800304C6
0x180030243  cmp     ecx, 1
0x180030246  jz      loc_1800304A6
0x18003024c  test    eax, eax
0x18003024e  js      short loc_18003025A
0x180030250  cmp     edi, [r14+28h]
0x180030254  jnz     loc_1800305AA
0x18003025a  mov     rcx, [rbp+1B8h]; this
0x180030261  test    ebx, ebx
0x180030263  js      loc_1800304FC
0x180030269  mov     rcx, r14; lpCriticalSection
0x18003026c  call    cs:__imp_TryEnterCriticalSection
0x180030272  mov     ebx, 8001010Eh
0x180030277  test    eax, eax
0x180030279  cmovnz  ebx, r15d
0x18003027d  mov     [rsp+2B0h+var_270], ebx
0x180030281  test    ebx, ebx
0x180030283  js      loc_180030589
0x180030289  xorps   xmm0, xmm0
0x18003028c  xor     eax, eax
0x18003028e  movups  xmmword ptr [rsi], xmm0
0x180030291  mov     [rsi+10h], rax
0x180030295  mov     rcx, [r13+90h]
0x18003029c  mov     r15d, 80004005h
0x1800302a2  test    rcx, rcx
0x1800302a5  jnz     loc_1800305B4
0x1800302ab  mov     [rsp+2B0h+var_280], eax
0x1800302af  mov     rcx, [r13+80h]
0x1800302b6  test    rcx, rcx
0x1800302b9  jz      loc_1800304B3
0x1800302bf  mov     rax, [rcx]
0x1800302c2  mov     r8, rsi
0x1800302c5  mov     rdx, r12
0x1800302c8  mov     rax, [rax+28h]
0x1800302cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800302d1  mov     edi, eax
0x1800302d3  test    eax, eax
0x1800302d5  jns     short loc_18003032F
0x1800302d7  mov     rcx, rsi; pvar
0x1800302da  call    cs:__imp_PropVariantClear
0x1800302e0  jmp     short loc_1800302E9
0x1800302e2  mov     [rsi], cx
0x1800302e5  test    edi, edi
0x1800302e7  js      short loc_1800302D7
0x1800302e9  test    cs:byte_1800F1382, 10h
0x1800302f0  jnz     loc_180030557
0x1800302f6  test    ebx, ebx
0x1800302f8  js      short loc_180030303
0x1800302fa  mov     rcx, r14; lpCriticalSection
0x1800302fd  call    cs:__imp_LeaveCriticalSection
0x180030303  mov     eax, edi
0x180030305  mov     rcx, [rbp+1B0h+var_40]
0x18003030c  xor     rcx, rsp; StackCookie
0x18003030f  call    __security_check_cookie
0x180030314  mov     rbx, [rsp+2B0h+arg_18]
0x18003031c  add     rsp, 280h
0x180030323  pop     r15
0x180030325  pop     r14
0x180030327  pop     r13
0x180030329  pop     r12
0x18003032b  pop     rdi
0x18003032c  pop     rsi
0x18003032d  pop     rbp
0x18003032e  retn
0x18003032f  xor     ecx, ecx
0x180030331  jmp     short loc_180030341
0x180030333  xor     ecx, ecx
0x180030335  mov     [rsp+2B0h+var_280], ecx
0x180030339  test    edi, edi
0x18003033b  js      loc_1800302AF
0x180030341  movzx   eax, word ptr [rsi]
0x180030344  cmp     ax, 1
0x180030348  jz      short loc_1800302E2
0x18003034a  test    ax, ax
0x18003034d  jz      short loc_1800302E5
0x18003034f  mov     qword ptr [rsp+2B0h+pAptQualifier], rcx
0x180030354  test    cs:byte_1800F1382, 10h
0x18003035b  jnz     loc_18003052D
0x180030361  mov     qword ptr [rsp+2B0h+pAptQualifier], rcx
0x180030366  mov     rax, [r12]
0x18003036a  sub     rax, cs:PSGUID_FOLDER_COLUMNID
0x180030371  jnz     short loc_18003037F
0x180030373  mov     rax, [r12+8]
0x180030378  sub     rax, cs:qword_1800D3848
0x18003037f  test    rax, rax
0x180030382  jz      loc_18003040D
0x180030388  mov     [rsp+2B0h+var_258], rcx
0x18003038d  mov     qword ptr [rsp+2B0h+pAptType], rcx
0x180030392  lea     rcx, [rsp+2B0h+pAptType]; struct ISchemaCache **
0x180030397  call    ?_GetGlobalSchemaCache@@YAJPEAPEAUISchemaCache@@@Z; _GetGlobalSchemaCache(ISchemaCache * *)
0x18003039c  mov     r15d, eax
0x18003039f  test    eax, eax
0x1800303a1  js      short loc_18003040D
0x1800303a3  mov     rcx, qword ptr [rsp+2B0h+pAptType]
0x1800303a8  mov     rax, [rcx]
0x1800303ab  lea     r8, [rsp+2B0h+var_258]
0x1800303b0  lea     rdx, _GUID_a8765599_6915_4a84_ab8c_3bf8927b06c6
0x1800303b7  mov     rax, [rax+50h]
0x1800303bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800303c0  mov     r15d, eax
0x1800303c3  mov     rcx, qword ptr [rsp+2B0h+pAptType]
0x1800303c8  mov     rax, [rcx]
0x1800303cb  mov     rax, [rax+10h]
0x1800303cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800303d4  test    r15d, r15d
0x1800303d7  js      short loc_18003040D
0x1800303d9  mov     rcx, [rsp+2B0h+var_258]
0x1800303de  mov     rax, [rcx]
0x1800303e1  lea     r9, [rsp+2B0h+pAptQualifier]
0x1800303e6  lea     r8, _GUID_6f79d558_3e96_4549_a1d1_7d75d2288814
0x1800303ed  mov     rdx, r12
0x1800303f0  mov     rax, [rax+18h]
0x1800303f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800303f9  mov     r15d, eax
0x1800303fc  mov     rcx, [rsp+2B0h+var_258]
0x180030401  mov     rdx, [rcx]
0x180030404  mov     rax, [rdx+10h]
0x180030408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003040d  test    cs:byte_1800F1382, 10h
0x180030414  jnz     loc_180030570
0x18003041a  test    r15d, r15d
0x18003041d  js      short loc_180030454
0x18003041f  mov     rcx, qword ptr [rsp+2B0h+pAptQualifier]
0x180030424  mov     rax, [rcx]
0x180030427  mov     rdx, rsi
0x18003042a  mov     rax, [rax+0A8h]
0x180030431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030436  mov     edi, eax
0x180030438  mov     ecx, 80000000h
0x18003043d  add     eax, ecx
0x18003043f  test    ecx, eax
0x180030441  jz      short loc_18003048E
0x180030443  mov     rcx, qword ptr [rsp+2B0h+pAptQualifier]
0x180030448  mov     rax, [rcx]
0x18003044b  mov     rax, [rax+10h]
0x18003044f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030454  test    edi, edi
0x180030456  js      loc_1800302D7
0x18003045c  mov     rcx, [r13+90h]
0x180030463  test    rcx, rcx
0x180030466  jz      loc_1800302E9
0x18003046c  cmp     [rsp+2B0h+var_280], 0
0x180030471  jnz     loc_1800302E9
0x180030477  mov     rax, [rcx]
0x18003047a  mov     r8, rsi
0x18003047d  mov     rdx, r12
0x180030480  mov     rax, [rax+30h]
0x180030484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030489  jmp     loc_1800302E9
0x18003048e  cmp     edi, 8007000Eh
0x180030494  jz      short loc_180030443
0x180030496  mov     rcx, rsi; pvar
0x180030499  call    cs:__imp_PropVariantClear
0x18003049f  mov     edi, 401A0h
0x1800304a4  jmp     short loc_180030443
0x1800304a6  call    cs:__imp_GetCurrentThreadId
0x1800304ac  mov     edi, eax
0x1800304ae  jmp     loc_180030250
0x1800304b3  mov     edi, 80070057h
0x1800304b8  mov     rcx, rsi; pvar
0x1800304bb  call    cs:__imp_PropVariantClear
0x1800304c1  jmp     loc_1800302E9
0x1800304c6  mov     edi, 0FFFFFFFFh
0x1800304cb  jmp     loc_180030250
0x1800304d0  mov     r8d, 104h; nSize
0x1800304d6  lea     rdx, [rsp+2B0h+StringSource]; lpFilename
0x1800304db  xor     ecx, ecx; hModule
0x1800304dd  call    cs:__imp_GetModuleFileNameW
0x1800304e3  test    eax, eax
0x1800304e5  jnz     loc_1800301BF
0x1800304eb  cmp     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, edi; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800304f1  jnz     loc_180030269
0x1800304f7  jmp     loc_1800301F7
0x1800304fc  mov     r9d, ebx; char *
0x1800304ff  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180030506  mov     edx, 0C8h; void *
0x18003050b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180030510  jmp     loc_18003027D
0x180030515  mov     r9d, [rdx+10h]
0x180030519  mov     r8, r12
0x18003051c  lea     rdx, ShellTraceId_PropertyProvider_GetValue_Start
0x180030523  call    McTemplateU0jq_EtwEventWriteTransfer
0x180030528  jmp     loc_180030176
0x18003052d  mov     r9d, [r12+10h]
0x180030532  mov     r8, r12
0x180030535  lea     rdx, ShellTraceId_PropertyDescription_SHGetPropertyDescription_Start
0x18003053c  call    McTemplateU0jq_EtwEventWriteTransfer
0x180030541  xor     ecx, ecx
0x180030543  jmp     loc_180030361
0x180030548  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, 2; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x180030552  jmp     loc_180030269
0x180030557  mov     r9d, [r12+10h]
0x18003055c  mov     r8, r12
0x18003055f  lea     rdx, ShellTraceId_PropertyProvider_GetValue_Stop
0x180030566  call    McTemplateU0jq_EtwEventWriteTransfer
0x18003056b  jmp     loc_1800302F6
0x180030570  mov     r9d, [r12+10h]
0x180030575  mov     r8, r12
0x180030578  lea     rdx, ShellTraceId_PropertyDescription_SHGetPropertyDescription_Stop
0x18003057f  call    McTemplateU0jq_EtwEventWriteTransfer
0x180030584  jmp     loc_18003041A
0x180030589  mov     edi, ebx
0x18003058b  jmp     loc_1800302E9
0x180030590  mov     ecx, 10h
0x180030595  call    cs:__imp_IsAppCompatModeEnabled
0x18003059b  test    eax, eax
0x18003059d  jnz     short loc_180030548
0x18003059f  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800305a5  jmp     loc_1800301B5
0x1800305aa  mov     ebx, 8001010Eh
0x1800305af  jmp     loc_18003025A
0x1800305b4  mov     [rsp+2B0h+pAptType], eax
0x1800305b8  mov     rax, [rcx]
0x1800305bb  lea     r9, [rsp+2B0h+pAptType]
0x1800305c0  mov     r8, rsi
0x1800305c3  mov     rdx, r12
0x1800305c6  mov     rax, [rax+48h]
0x1800305ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800305cf  mov     edi, eax
0x1800305d1  mov     eax, [rsp+2B0h+pAptType]
0x1800305d5  test    edi, edi
0x1800305d7  js      short loc_1800305F1
0x1800305d9  cmp     eax, 2
0x1800305dc  jnz     short loc_1800305EF
0x1800305de  mov     edi, r15d
0x1800305e1  mov     rcx, rsi; pvar
0x1800305e4  call    cs:__imp_PropVariantClear
0x1800305ea  jmp     loc_180030333
0x1800305ef  test    edi, edi
0x1800305f1  jnz     loc_180030333
0x1800305f7  cmp     eax, 1
0x1800305fa  jnz     loc_18003032F
0x180030600  jmp     loc_180030333
  ... truncated ...
```
