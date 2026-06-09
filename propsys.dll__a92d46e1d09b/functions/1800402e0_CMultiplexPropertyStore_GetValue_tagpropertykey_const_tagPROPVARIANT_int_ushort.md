# CMultiplexPropertyStore::_GetValue(_tagpropertykey const &,tagPROPVARIANT *,int,ushort * *)

- ea: `0x1800402e0`
- end: `0x1800406ed`
- name: `?_GetValue@CMultiplexPropertyStore@@IEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@HPEAPEAG@Z`
- size: `1037`
- prototype: `__int64 __fastcall(CMultiplexPropertyStore *__hidden this, const struct _tagpropertykey *, struct tagPROPVARIANT *, int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800804b0`

## callees

- `0x18002f9e0`
- `0x1800402e0`
- `0x180042330`
- `0x18006ed20`
- `0x180085820`
- `0x180085fc0`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180040594`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180040594`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1800405f5`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1800405f5`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1800403e7`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1800403e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040531`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040531`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004055d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004055d`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18004038f`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18004038f`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x18004061b`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x18004061b`

## string_xrefs

- `0x1800405b5`: `onecoreuap\internal\shell\inc\private\cowthreadusedetection.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMultiplexPropertyStore::_GetValue(
        CMultiplexPropertyStore *this,
        const struct _tagpropertykey *a2,
        struct tagPROPVARIANT *a3,
        unsigned int a4,
        unsigned __int16 **a5)
{
  char *v6; // r14
  int v7; // ebx
  int v8; // eax
  DWORD CurrentThreadId; // ebx
  APTTYPEQUALIFIER ApartmentType; // ebp
  int v11; // edi
  int v12; // r13d
  APTTYPE v13; // esi
  struct tagPROPVARIANT *v14; // r14
  const struct _tagpropertykey *v15; // rbp
  IUnknown *v16; // rbx
  unsigned int v17; // ebx
  int v19; // ecx
  struct tagPROPVARIANT *v20; // rax
  int cchValue; // [rsp+20h] [rbp-2C8h]
  APTTYPEQUALIFIER pAptQualifier; // [rsp+30h] [rbp-2B8h] BYREF
  APTTYPE pAptType; // [rsp+34h] [rbp-2B4h] BYREF
  unsigned int v24; // [rsp+38h] [rbp-2B0h]
  const struct _tagpropertykey *v25; // [rsp+40h] [rbp-2A8h]
  struct tagPROPVARIANT *v26; // [rsp+48h] [rbp-2A0h]
  char *v27; // [rsp+50h] [rbp-298h]
  char *v28; // [rsp+58h] [rbp-290h]
  APTTYPEQUALIFIER v29; // [rsp+60h] [rbp-288h]
  IUnknown *punk; // [rsp+68h] [rbp-280h] BYREF
  __int64 v31; // [rsp+70h] [rbp-278h] BYREF
  WCHAR Filename[264]; // [rsp+80h] [rbp-268h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+0h]

  v24 = a4;
  v26 = a3;
  v25 = a2;
  *(_OWORD *)&a3->vt = 0;
  a3->bstrblobVal.pData = 0;
  if ( a5 )
    *a5 = 0;
  v6 = (char *)this + 64;
  if ( !this )
    v6 = 0;
  v27 = v6;
  v28 = v6;
  v7 = *((_DWORD *)v6 + 11);
  if ( v7 == 2 )
    goto LABEL_10;
  v8 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
  if ( !`_ShouldCheckApartments'::`5'::s_tbEnforceForProcess )
  {
    if ( GetModuleFileNameW(0, Filename, 0x104u) )
    {
      v19 = (FindStringOrdinal(0x800000u, Filename, -1, L"\\EXPLORER.EXE", -1, 1) != -1) + 1;
      `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = v19;
    }
    else
    {
      v19 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
    }
    if ( v19 != 1 )
      goto LABEL_20;
    if ( v7 != 1 )
      goto LABEL_10;
    if ( (unsigned int)IsAppCompatModeEnabled(16) )
    {
      `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = 2;
      goto LABEL_20;
    }
    v8 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
  }
  if ( v8 != 1 )
    goto LABEL_20;
LABEL_10:
  if ( *((_DWORD *)v6 + 10) == -3 )
    goto LABEL_20;
  CurrentThreadId = 0;
  pAptType = APTTYPE_STA;
  pAptQualifier = APTTYPEQUALIFIER_NONE;
  ApartmentType = CoGetApartmentType(&pAptType, &pAptQualifier);
  pAptQualifier = ApartmentType;
  if ( ApartmentType < APTTYPEQUALIFIER_NONE )
  {
LABEL_16:
    if ( ApartmentType < APTTYPEQUALIFIER_NONE )
      goto LABEL_19;
    goto LABEL_17;
  }
  if ( pAptType == APTTYPE_STA )
    goto LABEL_49;
  if ( pAptType != APTTYPE_MTA )
  {
    if ( pAptType != APTTYPE_NA )
    {
      if ( pAptType != APTTYPE_MAINSTA )
        goto LABEL_16;
LABEL_49:
      CurrentThreadId = GetCurrentThreadId();
      pAptQualifier = ApartmentType;
      goto LABEL_17;
    }
    CurrentThreadId = -1;
  }
  pAptQualifier = ApartmentType;
LABEL_17:
  if ( CurrentThreadId != *((_DWORD *)v6 + 10) )
  {
    ApartmentType = -2147417842;
    pAptQualifier = -2147417842;
  }
LABEL_19:
  if ( ApartmentType < APTTYPEQUALIFIER_NONE )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xC8,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\cowthreadusedetection.h",
      (const char *)(unsigned int)ApartmentType,
      cchValue);
    goto LABEL_23;
  }
LABEL_20:
  ApartmentType = -2147417842;
  if ( TryEnterCriticalSection((LPCRITICAL_SECTION)v6) )
    ApartmentType = APTTYPEQUALIFIER_NONE;
  pAptQualifier = ApartmentType;
LABEL_23:
  v29 = ApartmentType;
  v11 = ApartmentType;
  if ( ApartmentType >= APTTYPEQUALIFIER_NONE )
  {
    v12 = 0;
    pAptType = (*(unsigned int (__fastcall **)(CMultiplexPropertyStore *))(*(_QWORD *)this + 80LL))(this);
    v13 = APTTYPE_STA;
    if ( pAptType > APTTYPE_STA )
    {
      v14 = v26;
      v15 = v25;
      do
      {
        if ( v12 )
          break;
        punk = 0;
        if ( (*(int (__fastcall **)(CMultiplexPropertyStore *, _QWORD, GUID *, IUnknown **))(*(_QWORD *)this + 72LL))(
               this,
               (unsigned int)v13,
               &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
               &punk) >= 0 )
        {
          v16 = punk;
          if ( punk )
          {
            if ( a5
              && (*a5 = 0,
                  v31 = 0,
                  ((__int64 (__fastcall *)(IUnknown *, GUID *, __int64 *))v16->lpVtbl->QueryInterface)(
                    v16,
                    &GUID_cd0188d2_aec9_4c3b_8b58_b79ce800d0b6,
                    &v31) >= 0)
              && (v11 = (*(__int64 (__fastcall **)(__int64, const struct _tagpropertykey *, struct tagPROPVARIANT *, _QWORD, unsigned __int16 **))(*(_QWORD *)v31 + 24LL))(
                          v31,
                          v15,
                          v14,
                          v24,
                          a5),
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31),
                  v11 >= 0)
              || (v11 = ((__int64 (__fastcall *)(IUnknown *, const struct _tagpropertykey *, struct tagPROPVARIANT *))v16->lpVtbl[1].Release)(
                          v16,
                          v15,
                          v14),
                  v11 >= 0)
              && a5
              && (!v14->vt || (v11 = PSGetObjectIdentity(v16), v11 >= 0)) )
            {
              if ( (v24 & 1) != 0 && v14->vt )
                PSAppendPropHandlerPath(a5, L"mux");
            }
            if ( v11 >= 0 && v14->vt )
              v12 = 1;
            v16 = punk;
          }
          else
          {
            v11 = -2147024809;
          }
          ((void (__fastcall *)(IUnknown *))v16->lpVtbl->Release)(v16);
        }
        ++v13;
      }
      while ( v13 < pAptType );
      ApartmentType = pAptQualifier;
      v6 = v27;
      if ( v11 < 0 && (unsigned int)operator==(v25, &PKEY_ItemDate) )
      {
        v11 = 0;
        v20 = v26;
        *(_OWORD *)&v26->vt = 0;
        v20->bstrblobVal.pData = 0;
      }
    }
  }
  v17 = 0;
  if ( v11 < 0 )
    v17 = v11;
  if ( ApartmentType >= APTTYPEQUALIFIER_NONE )
    LeaveCriticalSection((LPCRITICAL_SECTION)v6);
  return v17;
}

```

## disassembly

```asm
0x1800402e0  push    rbx
0x1800402e2  push    rbp
0x1800402e3  push    rsi
0x1800402e4  push    rdi
0x1800402e5  push    r12
0x1800402e7  push    r13
0x1800402e9  push    r14
0x1800402eb  push    r15
0x1800402ed  sub     rsp, 2A8h
0x1800402f4  mov     rax, cs:__security_cookie
0x1800402fb  xor     rax, rsp
0x1800402fe  mov     [rsp+2E8h+var_58], rax
0x180040306  mov     [rsp+2E8h+var_2B0], r9d
0x18004030b  mov     [rsp+2E8h+var_2A0], r8
0x180040310  mov     [rsp+2E8h+var_2A8], rdx
0x180040315  mov     r15, rcx
0x180040318  mov     r12, [rsp+2E8h+arg_20]
0x180040320  xorps   xmm0, xmm0
0x180040323  xor     ecx, ecx; hModule
0x180040325  movups  xmmword ptr [r8], xmm0
0x180040329  mov     [r8+10h], rcx
0x18004032d  xor     edi, edi
0x18004032f  test    r12, r12
0x180040332  jnz     loc_18004060D
0x180040338  lea     r14, [r15+40h]
0x18004033c  test    r15, r15
0x18004033f  cmovz   r14, rdi
0x180040343  mov     [rsp+2E8h+var_298], r14
0x180040348  mov     [rsp+2E8h+var_290], r14
0x18004034d  mov     ebx, [r14+2Ch]
0x180040351  cmp     ebx, 2
0x180040354  jz      short loc_180040374
0x180040356  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18004035c  test    eax, eax
0x18004035e  jz      loc_180040586
0x180040364  cmp     eax, 1
0x180040367  jnz     short loc_1800403E4
0x180040369  jmp     short loc_180040374
0x18004036b  cmp     ebx, 1
0x18004036e  jz      loc_180040616
0x180040374  cmp     dword ptr [r14+28h], 0FFFFFFFDh
0x180040379  jz      short loc_1800403E4
0x18004037b  mov     ebx, edi
0x18004037d  mov     [rsp+2E8h+pAptType], edi
0x180040381  mov     [rsp+2E8h+pAptQualifier], edi
0x180040385  lea     rdx, [rsp+2E8h+pAptQualifier]; pAptQualifier
0x18004038a  lea     rcx, [rsp+2E8h+pAptType]; pAptType
0x18004038f  call    cs:__imp_CoGetApartmentType
0x180040395  mov     ebp, eax
0x180040397  mov     [rsp+2E8h+pAptQualifier], eax
0x18004039b  test    eax, eax
0x18004039d  js      short loc_1800403C6
0x18004039f  mov     eax, [rsp+2E8h+pAptType]
0x1800403a3  test    eax, eax
0x1800403a5  jz      loc_18004055D
0x1800403ab  sub     eax, 1
0x1800403ae  jz      loc_180040573
0x1800403b4  sub     eax, 1
0x1800403b7  jz      loc_18004056E
0x1800403bd  cmp     eax, 1
0x1800403c0  jz      loc_18004055D
0x1800403c6  test    ebp, ebp
0x1800403c8  js      short loc_1800403D4
0x1800403ca  cmp     ebx, [r14+28h]
0x1800403ce  jnz     loc_18004063F
0x1800403d4  mov     rcx, [rsp+2E8h]; this
0x1800403dc  test    ebp, ebp
0x1800403de  js      loc_1800405B2
0x1800403e4  mov     rcx, r14; lpCriticalSection
0x1800403e7  call    cs:__imp_TryEnterCriticalSection
0x1800403ed  xor     ecx, ecx
0x1800403ef  mov     ebp, 8001010Eh
0x1800403f4  test    eax, eax
0x1800403f6  cmovnz  ebp, ecx
0x1800403f9  mov     [rsp+2E8h+pAptQualifier], ebp
0x1800403fd  mov     [rsp+2E8h+var_288], ebp
0x180040401  mov     edi, ebp
0x180040403  test    ebp, ebp
0x180040405  js      loc_180040523
0x18004040b  xor     r13d, r13d
0x18004040e  mov     rax, [r15]
0x180040411  mov     rcx, r15
0x180040414  mov     rax, [rax+50h]
0x180040418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004041d  mov     [rsp+2E8h+pAptType], eax
0x180040421  xor     esi, esi
0x180040423  test    eax, eax
0x180040425  jle     loc_180040523
0x18004042b  mov     r14, [rsp+2E8h+var_2A0]
0x180040430  mov     rbp, [rsp+2E8h+var_2A8]
0x180040435  test    r13d, r13d
0x180040438  jnz     loc_180040512
0x18004043e  mov     [rsp+2E8h+punk], 0
0x180040447  mov     rax, [r15]
0x18004044a  lea     r9, [rsp+2E8h+punk]
0x18004044f  lea     r8, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x180040456  mov     edx, esi
0x180040458  mov     rcx, r15
0x18004045b  mov     rax, [rax+48h]
0x18004045f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040464  test    eax, eax
0x180040466  js      loc_180040506
0x18004046c  mov     rbx, [rsp+2E8h+punk]
0x180040471  test    rbx, rbx
0x180040474  jz      loc_18004057C
0x18004047a  test    r12, r12
0x18004047d  jnz     loc_18004064D
0x180040483  mov     rax, [rbx]
0x180040486  mov     r8, r14
0x180040489  mov     rdx, rbp
0x18004048c  mov     rcx, rbx
0x18004048f  mov     rax, [rax+28h]
0x180040493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040498  mov     edi, eax
0x18004049a  test    eax, eax
0x18004049c  js      short loc_1800404E1
0x18004049e  test    r12, r12
0x1800404a1  jz      short loc_1800404E1
0x1800404a3  cmp     word ptr [r14], 0
0x1800404a8  jnz     short loc_1800404C9
0x1800404aa  test    byte ptr [rsp+2E8h+var_2B0], 1
0x1800404af  jz      short loc_1800404E1
0x1800404b1  cmp     word ptr [r14], 0
0x1800404b6  jz      short loc_1800404E1
0x1800404b8  lea     rdx, aMux; "mux"
0x1800404bf  mov     rcx, r12; unsigned __int16 **
0x1800404c2  call    ?PSAppendPropHandlerPath@@YAXPEAPEAGPEBG@Z; PSAppendPropHandlerPath(ushort * *,ushort const *)
0x1800404c7  jmp     short loc_1800404E1
0x1800404c9  mov     r9, r12
0x1800404cc  xor     r8d, r8d
0x1800404cf  mov     edx, [rsp+2E8h+var_2B0]
0x1800404d3  mov     rcx, rbx; punk
0x1800404d6  call    PSGetObjectIdentity
0x1800404db  mov     edi, eax
0x1800404dd  test    eax, eax
0x1800404df  jns     short loc_1800404AA
0x1800404e1  test    edi, edi
0x1800404e3  js      short loc_1800404F2
0x1800404e5  cmp     word ptr [r14], 0
0x1800404ea  jz      short loc_1800404F2
0x1800404ec  mov     r13d, 1
0x1800404f2  mov     rbx, [rsp+2E8h+punk]
0x1800404f7  mov     rax, [rbx]
0x1800404fa  mov     rcx, rbx
0x1800404fd  mov     rax, [rax+10h]
0x180040501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040506  inc     esi
0x180040508  cmp     esi, [rsp+2E8h+pAptType]
0x18004050c  jl      loc_180040435
0x180040512  test    edi, edi
0x180040514  mov     ebp, [rsp+2E8h+pAptQualifier]
0x180040518  mov     r14, [rsp+2E8h+var_298]
0x18004051d  js      loc_1800406BB
0x180040523  xor     ebx, ebx
0x180040525  test    edi, edi
0x180040527  cmovs   ebx, edi
0x18004052a  test    ebp, ebp
0x18004052c  js      short loc_180040537
0x18004052e  mov     rcx, r14; lpCriticalSection
0x180040531  call    cs:__imp_LeaveCriticalSection
0x180040537  mov     eax, ebx
0x180040539  mov     rcx, [rsp+2E8h+var_58]
0x180040541  xor     rcx, rsp; StackCookie
0x180040544  call    __security_check_cookie
0x180040549  add     rsp, 2A8h
0x180040550  pop     r15
0x180040552  pop     r14
0x180040554  pop     r13
0x180040556  pop     r12
0x180040558  pop     rdi
0x180040559  pop     rsi
0x18004055a  pop     rbp
0x18004055b  pop     rbx
0x18004055c  retn
0x18004055d  call    cs:__imp_GetCurrentThreadId
0x180040563  mov     ebx, eax
0x180040565  mov     [rsp+2E8h+pAptQualifier], ebp
0x180040569  jmp     loc_1800403CA
0x18004056e  mov     ebx, 0FFFFFFFFh
0x180040573  mov     [rsp+2E8h+pAptQualifier], ebp
0x180040577  jmp     loc_1800403CA
0x18004057c  mov     edi, 80070057h
0x180040581  jmp     loc_1800404F7
0x180040586  mov     r8d, 104h; nSize
0x18004058c  lea     rdx, [rsp+2E8h+Filename]; lpFilename
0x180040594  call    cs:__imp_GetModuleFileNameW
0x18004059a  test    eax, eax
0x18004059c  jnz     short loc_1800405CB
0x18004059e  mov     ecx, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800405a4  cmp     ecx, 1
0x1800405a7  jnz     loc_1800403E4
0x1800405ad  jmp     loc_18004036B
0x1800405b2  mov     r9d, ebp; char *
0x1800405b5  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x1800405bc  mov     edx, 0C8h; void *
0x1800405c1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800405c6  jmp     loc_1800403FD
0x1800405cb  mov     [rsp+2E8h+bIgnoreCase], 1; bIgnoreCase
0x1800405d3  mov     [rsp+2E8h+cchValue], 0FFFFFFFFh; cchValue
0x1800405db  lea     r9, StringValue; "\\EXPLORER.EXE"
0x1800405e2  mov     r8d, 0FFFFFFFFh; cchSource
0x1800405e8  lea     rdx, [rsp+2E8h+Filename]; lpStringSource
0x1800405f0  mov     ecx, 800000h; dwFindStringOrdinalFlags
0x1800405f5  call    cs:__imp_FindStringOrdinal
0x1800405fb  mov     ecx, edi
0x1800405fd  cmp     eax, 0FFFFFFFFh
0x180040600  setnz   cl
0x180040603  inc     ecx
0x180040605  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, ecx; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18004060b  jmp     short loc_1800405A4
0x18004060d  mov     [r12], rdi
0x180040611  jmp     loc_180040338
0x180040616  mov     ecx, 10h
0x18004061b  call    cs:__imp_IsAppCompatModeEnabled
0x180040621  test    eax, eax
0x180040623  jz      short loc_180040634
0x180040625  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, 2; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18004062f  jmp     loc_1800403E4
0x180040634  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18004063a  jmp     loc_180040364
0x18004063f  mov     ebp, 8001010Eh
0x180040644  mov     [rsp+2E8h+pAptQualifier], ebp
0x180040648  jmp     loc_1800403D4
0x18004064d  xor     edi, edi
0x18004064f  mov     [r12], rdi
0x180040653  mov     [rsp+2E8h+var_278], rdi
0x180040658  mov     rax, [rbx]
0x18004065b  lea     r8, [rsp+2E8h+var_278]
0x180040660  lea     rdx, _GUID_cd0188d2_aec9_4c3b_8b58_b79ce800d0b6
0x180040667  mov     rcx, rbx
0x18004066a  mov     rax, [rax]
0x18004066d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040672  test    eax, eax
0x180040674  js      loc_180040483
0x18004067a  mov     rcx, [rsp+2E8h+var_278]
0x18004067f  mov     rax, [rcx]
0x180040682  mov     qword ptr [rsp+2E8h+cchValue], r12
0x180040687  mov     r9d, [rsp+2E8h+var_2B0]
0x18004068c  mov     r8, r14
0x18004068f  mov     rdx, rbp
0x180040692  mov     rax, [rax+18h]
0x180040696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004069b  mov     edi, eax
0x18004069d  mov     rcx, [rsp+2E8h+var_278]
0x1800406a2  mov     rdx, [rcx]
0x1800406a5  mov     rax, [rdx+10h]
0x1800406a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800406ae  test    edi, edi
0x1800406b0  jns     loc_1800404AA
0x1800406b6  jmp     loc_180040483
0x1800406bb  lea     rdx, PKEY_ItemDate
0x1800406c2  mov     rcx, [rsp+2E8h+var_2A8]
0x1800406c7  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x1800406cc  test    eax, eax
0x1800406ce  jz      loc_180040523
0x1800406d4  xor     edi, edi
0x1800406d6  xorps   xmm0, xmm0
0x1800406d9  xor     ecx, ecx
0x1800406db  mov     rax, [rsp+2E8h+var_2A0]
0x1800406e0  movups  xmmword ptr [rax], xmm0
0x1800406e3  mov     [rax+10h], rcx
0x1800406e7  jmp     loc_180040523
```
