# CPropertyProvider::_GetValueHelper(_tagpropertykey const &,tagPROPVARIANT *,int,ushort * *)

- ea: `0x18002fb20`
- end: `0x18003011e`
- name: `?_GetValueHelper@CPropertyProvider@@AEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@HPEAPEAG@Z`
- size: `1534`
- prototype: `int(CPropertyProvider *__hidden this, const struct _tagpropertykey *, struct tagPROPVARIANT *, int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180086570`

## callees

- `0x18002f9e0`
- `0x18002fb20`
- `0x180031280`
- `0x1800328b0`
- `0x18006ed20`
- `0x180085820`
- `0x180085fc0`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18002ff0f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18002ff0f`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18002fbdf`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18002fbdf`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x18002fc6c`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x18002fc6c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fd23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002fd23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002fed3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002fed3`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18002fc19`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18002fc19`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002fcfb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002fec6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002feef`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003005b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002fcfb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002fec6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002feef`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003005b`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x18002fff7`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x18002fff7`

## string_xrefs

- `0x18002ff31`: `onecoreuap\internal\shell\inc\private\cowthreadusedetection.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPropertyProvider::_GetValueHelper(
        CPropertyProvider *this,
        const struct _tagpropertykey *a2,
        PROPVARIANT *a3,
        int a4,
        unsigned __int16 **a5)
{
  const struct _tagpropertykey *v6; // r15
  char *v8; // r14
  int v9; // ebx
  int v10; // eax
  DWORD CurrentThreadId; // ebx
  HRESULT ApartmentType; // edi
  __int64 v13; // rcx
  __int64 v14; // rcx
  IUnknown *v15; // r15
  int v16; // ebx
  __int64 v18; // rax
  int GlobalSchemaCache; // r15d
  bool v20; // zf
  int cchValue; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+30h] [rbp-D0h]
  APTTYPEQUALIFIER pAptQualifier[2]; // [rsp+50h] [rbp-B0h] BYREF
  APTTYPE pAptType[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v26; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR StringSource[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  LODWORD(v26) = a4;
  v6 = a2;
  if ( (byte_1800F1382 & 0x10) != 0 )
    McTemplateU0jq_EtwEventWriteTransfer(this, ShellTraceId_PropertyProvider_GetValue_Start, a2, a2->pid);
  *(_OWORD *)a3 = 0;
  a3[2] = 0;
  v8 = (char *)this + 72;
  if ( !this )
    v8 = 0;
  v9 = *((_DWORD *)v8 + 11);
  v22 = 1;
  if ( v9 == 2 )
    goto LABEL_12;
  v10 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
  if ( !`_ShouldCheckApartments'::`5'::s_tbEnforceForProcess )
  {
    if ( GetModuleFileNameW(0, StringSource, 0x104u) )
    {
      if ( FindStringOrdinal(0x800000u, StringSource, -1, L"\\EXPLORER.EXE", -1, 1) != -1 )
        goto LABEL_74;
      `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = 1;
    }
    else if ( `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess != 1 )
    {
      goto LABEL_22;
    }
    if ( v9 != 1 )
      goto LABEL_12;
    if ( !(unsigned int)IsAppCompatModeEnabled(16) )
    {
      v10 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
      goto LABEL_7;
    }
LABEL_74:
    `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = 2;
    goto LABEL_22;
  }
LABEL_7:
  if ( v10 != 1 )
    goto LABEL_22;
LABEL_12:
  if ( *((_DWORD *)v8 + 10) == -3 )
    goto LABEL_22;
  CurrentThreadId = 0;
  pAptType[0] = APTTYPE_STA;
  pAptQualifier[0] = APTTYPEQUALIFIER_NONE;
  ApartmentType = CoGetApartmentType(pAptType, pAptQualifier);
  if ( ApartmentType < 0 )
  {
LABEL_18:
    if ( ApartmentType < 0 )
      goto LABEL_21;
    goto LABEL_19;
  }
  switch ( pAptType[0] )
  {
    case APTTYPE_STA:
      goto LABEL_66;
    case APTTYPE_MTA:
      CurrentThreadId = 0;
      break;
    case APTTYPE_NA:
      CurrentThreadId = -1;
      break;
    case APTTYPE_MAINSTA:
LABEL_66:
      CurrentThreadId = GetCurrentThreadId();
      break;
    default:
      goto LABEL_18;
  }
LABEL_19:
  if ( CurrentThreadId != *((_DWORD *)v8 + 10) )
    ApartmentType = -2147417842;
LABEL_21:
  if ( ApartmentType < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xC8,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\cowthreadusedetection.h",
      (const char *)(unsigned int)ApartmentType,
      cchValue);
    goto LABEL_24;
  }
LABEL_22:
  ApartmentType = -2147417842;
  if ( TryEnterCriticalSection((LPCRITICAL_SECTION)v8) )
    ApartmentType = 0;
LABEL_24:
  if ( ApartmentType >= 0 )
  {
    *(_OWORD *)a3 = 0;
    a3[2] = 0;
    if ( a5 )
      *a5 = 0;
    v14 = *((_QWORD *)this + 18);
    if ( !v14 || a5 )
      goto LABEL_28;
    pAptType[0] = APTTYPE_STA;
    v16 = (*(__int64 (__fastcall **)(__int64, const struct _tagpropertykey *, PROPVARIANT *, APTTYPE *))(*(_QWORD *)v14 + 72LL))(
            v14,
            v6,
            a3,
            pAptType);
    v20 = v16 == 0;
    if ( v16 >= 0 )
    {
      if ( pAptType[0] == APTTYPE_NA )
      {
        PropVariantClear(a3);
LABEL_28:
        v15 = (IUnknown *)*((_QWORD *)this + 16);
        if ( !v15 )
        {
          v16 = -2147024809;
          PropVariantClear(a3);
          goto LABEL_36;
        }
        if ( a5
          && (*a5 = 0,
              *(_QWORD *)pAptQualifier = 0,
              ((__int64 (__fastcall *)(IUnknown *, GUID *, APTTYPEQUALIFIER *))v15->lpVtbl->QueryInterface)(
                v15,
                &GUID_cd0188d2_aec9_4c3b_8b58_b79ce800d0b6,
                pAptQualifier) >= 0)
          && (v16 = (*(__int64 (__fastcall **)(_QWORD, const struct _tagpropertykey *, PROPVARIANT *, _QWORD, unsigned __int16 **))(**(_QWORD **)pAptQualifier + 24LL))(
                      *(_QWORD *)pAptQualifier,
                      a2,
                      a3,
                      (unsigned int)v26,
                      a5),
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptQualifier + 16LL))(*(_QWORD *)pAptQualifier),
              v16 >= 0)
          || (v16 = ((__int64 (__fastcall *)(IUnknown *, const struct _tagpropertykey *, PROPVARIANT *))v15->lpVtbl[1].Release)(
                      v15,
                      a2,
                      a3),
              v16 >= 0)
          && a5
          && (!*(_WORD *)a3 || (v16 = PSGetObjectIdentity(v15), v16 >= 0)) )
        {
          if ( (v26 & 1) != 0 && *(_WORD *)a3 )
            PSAppendPropHandlerPath(a5, L"PropertyProvider");
        }
        v22 = 0;
        if ( v16 < 0 )
          goto LABEL_33;
        v6 = a2;
LABEL_44:
        if ( *(_WORD *)a3 == 1 )
        {
          *(_WORD *)a3 = 0;
        }
        else if ( *(_WORD *)a3 )
        {
          *(_QWORD *)pAptQualifier = 0;
          if ( (byte_1800F1382 & 0x10) != 0 )
            McTemplateU0jq_EtwEventWriteTransfer(
              v13,
              ShellTraceId_PropertyDescription_SHGetPropertyDescription_Start,
              v6,
              v6->pid);
          *(_QWORD *)pAptQualifier = 0;
          v18 = *(_QWORD *)&v6->fmtid.Data1 - PSGUID_FOLDER_COLUMNID;
          if ( *(_QWORD *)&v6->fmtid.Data1 == PSGUID_FOLDER_COLUMNID )
            v18 = *(_QWORD *)v6->fmtid.Data4 - 0x2319B0B80447F794LL;
          if ( v18 )
          {
            v26 = 0;
            *(_QWORD *)pAptType = 0;
            GlobalSchemaCache = _GetGlobalSchemaCache((struct ISchemaCache **)pAptType);
            if ( GlobalSchemaCache >= 0 )
            {
              GlobalSchemaCache = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64 *))(**(_QWORD **)pAptType + 80LL))(
                                    *(_QWORD *)pAptType,
                                    &GUID_a8765599_6915_4a84_ab8c_3bf8927b06c6,
                                    &v26);
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptType + 16LL))(*(_QWORD *)pAptType);
              if ( GlobalSchemaCache >= 0 )
              {
                GlobalSchemaCache = (*(__int64 (__fastcall **)(__int64, const struct _tagpropertykey *, GUID *, APTTYPEQUALIFIER *))(*(_QWORD *)v26 + 24LL))(
                                      v26,
                                      a2,
                                      &GUID_6f79d558_3e96_4549_a1d1_7d75d2288814,
                                      pAptQualifier);
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
              }
            }
          }
          else
          {
            GlobalSchemaCache = -2147467259;
          }
          if ( (byte_1800F1382 & 0x10) != 0 )
            McTemplateU0jq_EtwEventWriteTransfer(
              v13,
              ShellTraceId_PropertyDescription_SHGetPropertyDescription_Stop,
              a2,
              a2->pid);
          if ( GlobalSchemaCache >= 0 )
          {
            v16 = (*(__int64 (__fastcall **)(_QWORD, PROPVARIANT *))(**(_QWORD **)pAptQualifier + 168LL))(
                    *(_QWORD *)pAptQualifier,
                    a3);
            if ( (int)(v16 + 0x80000000) >= 0 && v16 != -2147024882 )
            {
              PropVariantClear(a3);
              v16 = 262560;
            }
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptQualifier + 16LL))(*(_QWORD *)pAptQualifier);
          }
          if ( v16 >= 0 )
          {
            v13 = *((_QWORD *)this + 18);
            if ( v13 && !a5 && !v22 )
              (*(void (__fastcall **)(__int64, const struct _tagpropertykey *, PROPVARIANT *))(*(_QWORD *)v13 + 48LL))(
                v13,
                a2,
                a3);
            goto LABEL_36;
          }
LABEL_33:
          PropVariantClear(a3);
LABEL_36:
          v6 = a2;
          goto LABEL_37;
        }
        if ( v16 >= 0 )
          goto LABEL_36;
        goto LABEL_33;
      }
      v20 = v16 == 0;
    }
    if ( v20 && pAptType[0] != APTTYPE_MTA )
      goto LABEL_44;
    v22 = 0;
    if ( v16 >= 0 )
      goto LABEL_44;
    goto LABEL_28;
  }
  v16 = ApartmentType;
LABEL_37:
  if ( (byte_1800F1382 & 0x10) != 0 )
    McTemplateU0jq_EtwEventWriteTransfer(v13, ShellTraceId_PropertyProvider_GetValue_Stop, v6, v6->pid);
  if ( ApartmentType >= 0 )
    LeaveCriticalSection((LPCRITICAL_SECTION)v8);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18002fb20  push    rbp
0x18002fb22  push    rbx
0x18002fb23  push    rsi
0x18002fb24  push    rdi
0x18002fb25  push    r12
0x18002fb27  push    r13
0x18002fb29  push    r14
0x18002fb2b  push    r15
0x18002fb2d  lea     rbp, [rsp-198h]
0x18002fb35  sub     rsp, 298h
0x18002fb3c  mov     rax, cs:__security_cookie
0x18002fb43  xor     rax, rsp
0x18002fb46  mov     [rbp+1D0h+var_50], rax
0x18002fb4d  mov     dword ptr [rsp+2D0h+var_270], r9d
0x18002fb52  mov     rsi, r8
0x18002fb55  mov     r15, rdx
0x18002fb58  mov     [rsp+2D0h+var_298], rdx
0x18002fb5d  mov     r13, rcx
0x18002fb60  mov     r12, [rbp+1D0h+arg_20]
0x18002fb67  test    cs:byte_1800F1382, 10h
0x18002fb6e  jnz     loc_18002FF49
0x18002fb74  xorps   xmm0, xmm0
0x18002fb77  xor     eax, eax
0x18002fb79  movups  xmmword ptr [rsi], xmm0
0x18002fb7c  mov     [rsi+10h], rax
0x18002fb80  lea     r14, [r13+48h]
0x18002fb84  xor     ecx, ecx; hModule
0x18002fb86  test    r13, r13
0x18002fb89  cmovz   r14, rcx
0x18002fb8d  mov     [rsp+2D0h+var_290], r14
0x18002fb92  mov     ebx, [r14+2Ch]
0x18002fb96  mov     edi, 1
0x18002fb9b  mov     [rsp+2D0h+var_2A0], edi
0x18002fb9f  cmp     ebx, 2
0x18002fba2  jz      short loc_18002FBFE
0x18002fba4  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18002fbaa  test    eax, eax
0x18002fbac  jz      loc_18002FF04
0x18002fbb2  cmp     eax, edi
0x18002fbb4  jnz     loc_18002FC69
0x18002fbba  jmp     short loc_18002FBFE
0x18002fbbc  mov     [rsp+2D0h+bIgnoreCase], edi; bIgnoreCase
0x18002fbc0  mov     [rsp+2D0h+cchValue], 0FFFFFFFFh; int
0x18002fbc8  lea     r9, StringValue; "\\EXPLORER.EXE"
0x18002fbcf  mov     r8d, 0FFFFFFFFh; cchSource
0x18002fbd5  lea     rdx, [rsp+2D0h+StringSource]; lpStringSource
0x18002fbda  mov     ecx, 800000h; dwFindStringOrdinalFlags
0x18002fbdf  call    cs:__imp_FindStringOrdinal
0x18002fbe5  cmp     eax, 0FFFFFFFFh
0x18002fbe8  jnz     loc_18002FF7B
0x18002fbee  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, edi; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18002fbf4  cmp     ebx, edi
0x18002fbf6  jz      loc_18002FFF2
0x18002fbfc  xor     ecx, ecx
0x18002fbfe  cmp     dword ptr [r14+28h], 0FFFFFFFDh
0x18002fc03  jz      short loc_18002FC69
0x18002fc05  mov     ebx, ecx
0x18002fc07  mov     [rsp+2D0h+pAptType], ecx
0x18002fc0b  mov     [rsp+2D0h+pAptQualifier], ecx
0x18002fc0f  lea     rdx, [rsp+2D0h+pAptQualifier]; pAptQualifier
0x18002fc14  lea     rcx, [rsp+2D0h+pAptType]; pAptType
0x18002fc19  call    cs:__imp_CoGetApartmentType
0x18002fc1f  mov     edi, eax
0x18002fc21  test    eax, eax
0x18002fc23  js      short loc_18002FC4C
0x18002fc25  mov     eax, [rsp+2D0h+pAptType]
0x18002fc29  test    eax, eax
0x18002fc2b  jz      loc_18002FED3
0x18002fc31  sub     eax, 1
0x18002fc34  jz      loc_18002FEE0
0x18002fc3a  sub     eax, 1
0x18002fc3d  jz      loc_18002FEFA
0x18002fc43  cmp     eax, 1
0x18002fc46  jz      loc_18002FED3
0x18002fc4c  test    edi, edi
0x18002fc4e  js      short loc_18002FC5A
0x18002fc50  cmp     ebx, [r14+28h]
0x18002fc54  jnz     loc_180030012
0x18002fc5a  mov     rcx, [rbp+1D8h]; this
0x18002fc61  test    edi, edi
0x18002fc63  js      loc_18002FF2E
0x18002fc69  mov     rcx, r14; lpCriticalSection
0x18002fc6c  call    cs:__imp_TryEnterCriticalSection
0x18002fc72  xor     edx, edx
0x18002fc74  mov     edi, 8001010Eh
0x18002fc79  test    eax, eax
0x18002fc7b  cmovnz  edi, edx
0x18002fc7e  mov     [rsp+2D0h+var_288], edi
0x18002fc82  test    edi, edi
0x18002fc84  js      loc_18002FFBF
0x18002fc8a  xorps   xmm0, xmm0
0x18002fc8d  xor     eax, eax
0x18002fc8f  movups  xmmword ptr [rsi], xmm0
0x18002fc92  mov     [rsi+10h], rax
0x18002fc96  test    r12, r12
0x18002fc99  jnz     loc_18003001C
0x18002fc9f  mov     rcx, [r13+90h]
0x18002fca6  test    rcx, rcx
0x18002fca9  jnz     loc_180030025
0x18002fcaf  mov     r15, [r13+80h]
0x18002fcb6  test    r15, r15
0x18002fcb9  jz      loc_18002FEE7
0x18002fcbf  test    r12, r12
0x18002fcc2  jnz     loc_180030080
0x18002fcc8  mov     rax, [r15]
0x18002fccb  mov     r8, rsi
0x18002fcce  mov     rdx, [rsp+2D0h+var_298]
0x18002fcd3  mov     rcx, r15
0x18002fcd6  mov     rax, [rax+28h]
0x18002fcda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fcdf  mov     ebx, eax
0x18002fce1  test    eax, eax
0x18002fce3  js      short loc_18002FCEE
0x18002fce5  test    r12, r12
0x18002fce8  jnz     loc_1800300EA
0x18002fcee  xor     edx, edx
0x18002fcf0  mov     [rsp+2D0h+var_2A0], edx
0x18002fcf4  test    ebx, ebx
0x18002fcf6  jns     short loc_18002FD4E
0x18002fcf8  mov     rcx, rsi; pvar
0x18002fcfb  call    cs:__imp_PropVariantClear
0x18002fd01  jmp     short loc_18002FD0A
0x18002fd03  mov     [rsi], dx
0x18002fd06  test    ebx, ebx
0x18002fd08  js      short loc_18002FCF8
0x18002fd0a  mov     r15, [rsp+2D0h+var_298]
0x18002fd0f  test    cs:byte_1800F1382, 10h
0x18002fd16  jnz     loc_18002FF8A
0x18002fd1c  test    edi, edi
0x18002fd1e  js      short loc_18002FD29
0x18002fd20  mov     rcx, r14; lpCriticalSection
0x18002fd23  call    cs:__imp_LeaveCriticalSection
0x18002fd29  mov     eax, ebx
0x18002fd2b  mov     rcx, [rbp+1D0h+var_50]
0x18002fd32  xor     rcx, rsp; StackCookie
0x18002fd35  call    __security_check_cookie
0x18002fd3a  add     rsp, 298h
0x18002fd41  pop     r15
0x18002fd43  pop     r14
0x18002fd45  pop     r13
0x18002fd47  pop     r12
0x18002fd49  pop     rdi
0x18002fd4a  pop     rsi
0x18002fd4b  pop     rbx
0x18002fd4c  pop     rbp
0x18002fd4d  retn
0x18002fd4e  mov     r15, [rsp+2D0h+var_298]
0x18002fd53  jmp     short loc_18002FD63
0x18002fd55  xor     edx, edx
0x18002fd57  mov     [rsp+2D0h+var_2A0], edx
0x18002fd5b  test    ebx, ebx
0x18002fd5d  js      loc_18002FCAF
0x18002fd63  movzx   eax, word ptr [rsi]
0x18002fd66  cmp     ax, 1
0x18002fd6a  jz      short loc_18002FD03
0x18002fd6c  test    ax, ax
0x18002fd6f  jz      short loc_18002FD06
0x18002fd71  mov     qword ptr [rsp+2D0h+pAptQualifier], rdx
0x18002fd76  test    cs:byte_1800F1382, 10h
0x18002fd7d  jnz     loc_18002FF61
0x18002fd83  mov     qword ptr [rsp+2D0h+pAptQualifier], rdx
0x18002fd88  mov     rax, [r15]
0x18002fd8b  sub     rax, cs:PSGUID_FOLDER_COLUMNID
0x18002fd92  jnz     short loc_18002FD9F
0x18002fd94  mov     rax, [r15+8]
0x18002fd98  sub     rax, cs:qword_1800D3848
0x18002fd9f  test    rax, rax
0x18002fda2  jz      loc_18002FFC6
0x18002fda8  mov     [rsp+2D0h+var_270], rdx
0x18002fdad  mov     qword ptr [rsp+2D0h+pAptType], rdx
0x18002fdb2  lea     rcx, [rsp+2D0h+pAptType]; struct ISchemaCache **
0x18002fdb7  call    ?_GetGlobalSchemaCache@@YAJPEAPEAUISchemaCache@@@Z; _GetGlobalSchemaCache(ISchemaCache * *)
0x18002fdbc  mov     r15d, eax
0x18002fdbf  test    eax, eax
0x18002fdc1  js      short loc_18002FE2F
0x18002fdc3  mov     rcx, qword ptr [rsp+2D0h+pAptType]
0x18002fdc8  mov     rax, [rcx]
0x18002fdcb  lea     r8, [rsp+2D0h+var_270]
0x18002fdd0  lea     rdx, _GUID_a8765599_6915_4a84_ab8c_3bf8927b06c6
0x18002fdd7  mov     rax, [rax+50h]
0x18002fddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fde0  mov     r15d, eax
0x18002fde3  mov     rcx, qword ptr [rsp+2D0h+pAptType]
0x18002fde8  mov     rax, [rcx]
0x18002fdeb  mov     rax, [rax+10h]
0x18002fdef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fdf4  test    r15d, r15d
0x18002fdf7  js      short loc_18002FE2F
0x18002fdf9  mov     rcx, [rsp+2D0h+var_270]
0x18002fdfe  mov     rax, [rcx]
0x18002fe01  lea     r9, [rsp+2D0h+pAptQualifier]
0x18002fe06  lea     r8, _GUID_6f79d558_3e96_4549_a1d1_7d75d2288814
0x18002fe0d  mov     rdx, [rsp+2D0h+var_298]
0x18002fe12  mov     rax, [rax+18h]
0x18002fe16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe1b  mov     r15d, eax
0x18002fe1e  mov     rcx, [rsp+2D0h+var_270]
0x18002fe23  mov     rdx, [rcx]
0x18002fe26  mov     rax, [rdx+10h]
0x18002fe2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe2f  test    cs:byte_1800F1382, 10h
0x18002fe36  jnz     loc_18002FFA2
0x18002fe3c  test    r15d, r15d
0x18002fe3f  js      short loc_18002FE76
0x18002fe41  mov     rcx, qword ptr [rsp+2D0h+pAptQualifier]
0x18002fe46  mov     rax, [rcx]
0x18002fe49  mov     rdx, rsi
0x18002fe4c  mov     rax, [rax+0A8h]
0x18002fe53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe58  mov     ebx, eax
0x18002fe5a  mov     ecx, 80000000h
0x18002fe5f  add     eax, ecx
0x18002fe61  test    ecx, eax
0x18002fe63  jz      short loc_18002FEBB
0x18002fe65  mov     rcx, qword ptr [rsp+2D0h+pAptQualifier]
0x18002fe6a  mov     rax, [rcx]
0x18002fe6d  mov     rax, [rax+10h]
0x18002fe71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe76  test    ebx, ebx
0x18002fe78  js      loc_18002FCF8
0x18002fe7e  mov     rcx, [r13+90h]
0x18002fe85  test    rcx, rcx
0x18002fe88  jz      loc_18002FD0A
0x18002fe8e  test    r12, r12
0x18002fe91  jnz     loc_18002FD0A
0x18002fe97  cmp     [rsp+2D0h+var_2A0], r12d
0x18002fe9c  jnz     loc_18002FD0A
0x18002fea2  mov     rax, [rcx]
0x18002fea5  mov     r8, rsi
0x18002fea8  mov     rdx, [rsp+2D0h+var_298]
0x18002fead  mov     rax, [rax+30h]
0x18002feb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002feb6  jmp     loc_18002FD0A
0x18002febb  cmp     ebx, 8007000Eh
0x18002fec1  jz      short loc_18002FE65
0x18002fec3  mov     rcx, rsi; pvar
0x18002fec6  call    cs:__imp_PropVariantClear
0x18002fecc  mov     ebx, 401A0h
0x18002fed1  jmp     short loc_18002FE65
0x18002fed3  call    cs:__imp_GetCurrentThreadId
0x18002fed9  mov     ebx, eax
0x18002fedb  jmp     loc_18002FC50
0x18002fee0  xor     ebx, ebx
0x18002fee2  jmp     loc_18002FC50
0x18002fee7  mov     ebx, 80070057h
0x18002feec  mov     rcx, rsi; pvar
0x18002feef  call    cs:__imp_PropVariantClear
0x18002fef5  jmp     loc_18002FD0A
0x18002fefa  mov     ebx, 0FFFFFFFFh
0x18002feff  jmp     loc_18002FC50
0x18002ff04  mov     r8d, 104h; nSize
0x18002ff0a  lea     rdx, [rsp+2D0h+StringSource]; lpFilename
0x18002ff0f  call    cs:__imp_GetModuleFileNameW
0x18002ff15  test    eax, eax
0x18002ff17  jnz     loc_18002FBBC
0x18002ff1d  cmp     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, edi; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18002ff23  jnz     loc_18002FC69
0x18002ff29  jmp     loc_18002FBF4
0x18002ff2e  mov     r9d, edi; char *
0x18002ff31  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18002ff38  mov     edx, 0C8h; void *
0x18002ff3d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002ff42  xor     edx, edx
0x18002ff44  jmp     loc_18002FC7E
0x18002ff49  mov     r9d, [rdx+10h]
0x18002ff4d  mov     r8, r15
0x18002ff50  lea     rdx, ShellTraceId_PropertyProvider_GetValue_Start
0x18002ff57  call    McTemplateU0jq_EtwEventWriteTransfer
0x18002ff5c  jmp     loc_18002FB74
0x18002ff61  mov     r9d, [r15+10h]
0x18002ff65  mov     r8, r15
0x18002ff68  lea     rdx, ShellTraceId_PropertyDescription_SHGetPropertyDescription_Start
0x18002ff6f  call    McTemplateU0jq_EtwEventWriteTransfer
0x18002ff74  xor     edx, edx
0x18002ff76  jmp     loc_18002FD83
0x18002ff7b  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, 2; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18002ff85  jmp     loc_18002FC69
0x18002ff8a  mov     r9d, [r15+10h]
0x18002ff8e  mov     r8, r15
0x18002ff91  lea     rdx, ShellTraceId_PropertyProvider_GetValue_Stop
0x18002ff98  call    McTemplateU0jq_EtwEventWriteTransfer
0x18002ff9d  jmp     loc_18002FD1C
0x18002ffa2  mov     rax, [rsp+2D0h+var_298]
0x18002ffa7  mov     r9d, [rax+10h]
0x18002ffab  mov     r8, rax
0x18002ffae  lea     rdx, ShellTraceId_PropertyDescription_SHGetPropertyDescription_Stop
0x18002ffb5  call    McTemplateU0jq_EtwEventWriteTransfer
0x18002ffba  jmp     loc_18002FE3C
0x18002ffbf  mov     ebx, edi
0x18002ffc1  jmp     loc_18002FD0F
0x18002ffc6  mov     r15d, 80004005h
0x18002ffcc  jmp     loc_18002FE2F
0x18002ffd1  mov     r9, r12
0x18002ffd4  xor     r8d, r8d
0x18002ffd7  mov     edx, dword ptr [rsp+2D0h+var_270]
0x18002ffdb  mov     rcx, r15; punk
0x18002ffde  call    PSGetObjectIdentity
0x18002ffe3  mov     ebx, eax
0x18002ffe5  test    eax, eax
0x18002ffe7  js      loc_18002FCEE
  ... truncated ...
```
