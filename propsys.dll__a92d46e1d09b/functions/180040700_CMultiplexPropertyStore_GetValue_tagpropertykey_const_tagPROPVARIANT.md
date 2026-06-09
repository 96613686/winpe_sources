# CMultiplexPropertyStore::GetValue(_tagpropertykey const &,tagPROPVARIANT *)

- ea: `0x180040700`
- end: `0x1800409f6`
- name: `?GetValue@CMultiplexPropertyStore@@UEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z`
- size: `758`
- prototype: `__int64 __fastcall(CMultiplexPropertyStore *__hidden this, const struct _tagpropertykey *, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18002f9e0`
- `0x180040700`
- `0x180042330`
- `0x18006ed20`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18004091e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18004091e`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18004097c`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18004097c`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1800407ea`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1800407ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800408c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800408c0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800408f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800408f3`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18004079a`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18004079a`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x180040999`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x180040999`

## string_xrefs

- `0x18004093f`: `onecoreuap\internal\shell\inc\private\cowthreadusedetection.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMultiplexPropertyStore::GetValue(
        CMultiplexPropertyStore *this,
        const struct _tagpropertykey *a2,
        struct tagPROPVARIANT *a3)
{
  char *v5; // r14
  int v6; // ebx
  int v7; // eax
  DWORD CurrentThreadId; // ebx
  HRESULT ApartmentType; // edi
  int v10; // esi
  BOOL v11; // ebp
  int v12; // r15d
  int v13; // ebx
  const struct _tagpropertykey *v14; // r14
  __int64 v15; // rcx
  unsigned int v16; // ebx
  int v18; // ecx
  int cchValue; // [rsp+20h] [rbp-298h]
  APTTYPE pAptType; // [rsp+30h] [rbp-288h] BYREF
  const struct _tagpropertykey *v21; // [rsp+38h] [rbp-280h]
  char *v22; // [rsp+40h] [rbp-278h]
  char *v23; // [rsp+48h] [rbp-270h]
  HRESULT v24; // [rsp+50h] [rbp-268h]
  APTTYPEQUALIFIER pAptQualifier[2]; // [rsp+58h] [rbp-260h] BYREF
  WCHAR Filename[264]; // [rsp+60h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+0h]

  v21 = a2;
  *(_OWORD *)&a3->vt = 0;
  a3->bstrblobVal.pData = 0;
  v5 = (char *)this + 64;
  if ( !this )
    v5 = 0;
  v22 = v5;
  v23 = v5;
  v6 = *((_DWORD *)v5 + 11);
  if ( v6 == 2 )
    goto LABEL_8;
  v7 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
  if ( `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess )
    goto LABEL_5;
  if ( GetModuleFileNameW(0, Filename, 0x104u) )
  {
    v18 = (FindStringOrdinal(0x800000u, Filename, -1, L"\\EXPLORER.EXE", -1, 1) != -1) + 1;
    `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = v18;
  }
  else
  {
    v18 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
  }
  if ( v18 != 1 )
    goto LABEL_18;
  if ( v6 == 1 )
  {
    if ( (unsigned int)IsAppCompatModeEnabled(16) )
    {
      `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = 2;
      goto LABEL_18;
    }
    v7 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
LABEL_5:
    if ( v7 != 1 )
      goto LABEL_18;
  }
LABEL_8:
  if ( *((_DWORD *)v5 + 10) == -3 )
    goto LABEL_18;
  CurrentThreadId = 0;
  pAptType = APTTYPE_STA;
  pAptQualifier[0] = APTTYPEQUALIFIER_NONE;
  ApartmentType = CoGetApartmentType(&pAptType, pAptQualifier);
  if ( ApartmentType < 0 )
  {
LABEL_14:
    if ( ApartmentType < 0 )
      goto LABEL_17;
    goto LABEL_15;
  }
  if ( pAptType == APTTYPE_STA )
    goto LABEL_37;
  if ( pAptType == APTTYPE_MTA )
    goto LABEL_15;
  if ( pAptType != APTTYPE_NA )
  {
    if ( pAptType != APTTYPE_MAINSTA )
      goto LABEL_14;
LABEL_37:
    CurrentThreadId = GetCurrentThreadId();
    goto LABEL_15;
  }
  CurrentThreadId = -1;
LABEL_15:
  if ( CurrentThreadId != *((_DWORD *)v5 + 10) )
    ApartmentType = -2147417842;
LABEL_17:
  if ( ApartmentType < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xC8,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\cowthreadusedetection.h",
      (const char *)(unsigned int)ApartmentType,
      cchValue);
    goto LABEL_20;
  }
LABEL_18:
  ApartmentType = -2147417842;
  if ( TryEnterCriticalSection((LPCRITICAL_SECTION)v5) )
    ApartmentType = 0;
LABEL_20:
  v24 = ApartmentType;
  v10 = ApartmentType;
  if ( ApartmentType >= 0 )
  {
    v11 = 0;
    v12 = (*(__int64 (__fastcall **)(CMultiplexPropertyStore *))(*(_QWORD *)this + 80LL))(this);
    v13 = 0;
    if ( v12 > 0 )
    {
      v14 = v21;
      do
      {
        if ( v11 )
          break;
        *(_QWORD *)pAptQualifier = 0;
        if ( (*(int (__fastcall **)(CMultiplexPropertyStore *, _QWORD, GUID *, APTTYPEQUALIFIER *))(*(_QWORD *)this
                                                                                                  + 72LL))(
               this,
               (unsigned int)v13,
               &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
               pAptQualifier) >= 0 )
        {
          v15 = *(_QWORD *)pAptQualifier;
          if ( *(_QWORD *)pAptQualifier )
          {
            v10 = (*(__int64 (__fastcall **)(_QWORD, const struct _tagpropertykey *, struct tagPROPVARIANT *))(**(_QWORD **)pAptQualifier + 40LL))(
                    *(_QWORD *)pAptQualifier,
                    v14,
                    a3);
            if ( v10 >= 0 )
              v11 = a3->vt != 0;
            v15 = *(_QWORD *)pAptQualifier;
          }
          else
          {
            v10 = -2147024809;
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        }
        ++v13;
      }
      while ( v13 < v12 );
      v5 = v22;
      if ( v10 < 0 && (unsigned int)operator==(v21, &PKEY_ItemDate) )
      {
        v10 = 0;
        *(_OWORD *)&a3->vt = 0;
        a3->bstrblobVal.pData = 0;
      }
    }
  }
  v16 = 0;
  if ( v10 < 0 )
    v16 = v10;
  if ( ApartmentType >= 0 )
    LeaveCriticalSection((LPCRITICAL_SECTION)v5);
  return v16;
}

```

## disassembly

```asm
0x180040700  mov     [rsp+arg_18], rbx
0x180040705  push    rbp
0x180040706  push    rsi
0x180040707  push    rdi
0x180040708  push    r12
0x18004070a  push    r13
0x18004070c  push    r14
0x18004070e  push    r15
0x180040710  sub     rsp, 280h
0x180040717  mov     rax, cs:__security_cookie
0x18004071e  xor     rax, rsp
0x180040721  mov     [rsp+2B8h+var_48], rax
0x180040729  mov     r13, r8
0x18004072c  mov     [rsp+2B8h+var_280], rdx
0x180040731  mov     r12, rcx
0x180040734  xorps   xmm0, xmm0
0x180040737  xor     eax, eax
0x180040739  movups  xmmword ptr [r8], xmm0
0x18004073d  mov     [r8+10h], rax
0x180040741  lea     r14, [rcx+40h]
0x180040745  xor     esi, esi
0x180040747  test    rcx, rcx
0x18004074a  cmovz   r14, rsi
0x18004074e  mov     [rsp+2B8h+var_278], r14
0x180040753  mov     [rsp+2B8h+var_270], r14
0x180040758  mov     ebx, [r14+2Ch]
0x18004075c  cmp     ebx, 2
0x18004075f  jz      short loc_18004077F
0x180040761  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x180040767  test    eax, eax
0x180040769  jz      loc_180040911
0x18004076f  cmp     eax, 1
0x180040772  jnz     short loc_1800407E7
0x180040774  jmp     short loc_18004077F
0x180040776  cmp     ebx, 1
0x180040779  jz      loc_180040994
0x18004077f  cmp     dword ptr [r14+28h], 0FFFFFFFDh
0x180040784  jz      short loc_1800407E7
0x180040786  mov     ebx, esi
0x180040788  mov     [rsp+2B8h+pAptType], esi
0x18004078c  mov     [rsp+2B8h+pAptQualifier], esi
0x180040790  lea     rdx, [rsp+2B8h+pAptQualifier]; pAptQualifier
0x180040795  lea     rcx, [rsp+2B8h+pAptType]; pAptType
0x18004079a  call    cs:__imp_CoGetApartmentType
0x1800407a0  mov     edi, eax
0x1800407a2  test    eax, eax
0x1800407a4  js      short loc_1800407C9
0x1800407a6  mov     eax, [rsp+2B8h+pAptType]
0x1800407aa  test    eax, eax
0x1800407ac  jz      loc_1800408F3
0x1800407b2  sub     eax, 1
0x1800407b5  jz      short loc_1800407CD
0x1800407b7  sub     eax, 1
0x1800407ba  jz      loc_180040907
0x1800407c0  cmp     eax, 1
0x1800407c3  jz      loc_1800408F3
0x1800407c9  test    edi, edi
0x1800407cb  js      short loc_1800407D7
0x1800407cd  cmp     ebx, [r14+28h]
0x1800407d1  jnz     loc_1800409BD
0x1800407d7  mov     rcx, [rsp+2B8h]; this
0x1800407df  test    edi, edi
0x1800407e1  js      loc_18004093C
0x1800407e7  mov     rcx, r14; lpCriticalSection
0x1800407ea  call    cs:__imp_TryEnterCriticalSection
0x1800407f0  mov     edi, 8001010Eh
0x1800407f5  test    eax, eax
0x1800407f7  cmovnz  edi, esi
0x1800407fa  mov     [rsp+2B8h+var_268], edi
0x1800407fe  mov     esi, edi
0x180040800  test    edi, edi
0x180040802  js      loc_1800408B2
0x180040808  xor     ebp, ebp
0x18004080a  mov     rax, [r12]
0x18004080e  mov     rcx, r12
0x180040811  mov     rax, [rax+50h]
0x180040815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004081a  mov     r15d, eax
0x18004081d  xor     ebx, ebx
0x18004081f  test    eax, eax
0x180040821  jle     loc_1800408B2
0x180040827  mov     r14, [rsp+2B8h+var_280]
0x18004082c  test    ebp, ebp
0x18004082e  jnz     short loc_1800408A5
0x180040830  mov     qword ptr [rsp+2B8h+pAptQualifier], 0
0x180040839  mov     rcx, [r12]
0x18004083d  mov     rax, [rcx+48h]
0x180040841  lea     r9, [rsp+2B8h+pAptQualifier]
0x180040846  lea     r8, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18004084d  mov     edx, ebx
0x18004084f  mov     rcx, r12
0x180040852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040857  test    eax, eax
0x180040859  js      short loc_18004089E
0x18004085b  mov     rcx, qword ptr [rsp+2B8h+pAptQualifier]
0x180040860  test    rcx, rcx
0x180040863  jz      loc_180040900
0x180040869  mov     rax, [rcx]
0x18004086c  mov     r8, r13
0x18004086f  mov     rdx, r14
0x180040872  mov     rax, [rax+28h]
0x180040876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004087b  mov     esi, eax
0x18004087d  test    eax, eax
0x18004087f  js      short loc_18004088D
0x180040881  cmp     [r13+0], bp
0x180040886  jz      short loc_18004088D
0x180040888  mov     ebp, 1
0x18004088d  mov     rcx, qword ptr [rsp+2B8h+pAptQualifier]
0x180040892  mov     rax, [rcx]
0x180040895  mov     rax, [rax+10h]
0x180040899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004089e  inc     ebx
0x1800408a0  cmp     ebx, r15d
0x1800408a3  jl      short loc_18004082C
0x1800408a5  test    esi, esi
0x1800408a7  mov     r14, [rsp+2B8h+var_278]
0x1800408ac  js      loc_1800409C7
0x1800408b2  xor     ebx, ebx
0x1800408b4  test    esi, esi
0x1800408b6  cmovs   ebx, esi
0x1800408b9  test    edi, edi
0x1800408bb  js      short loc_1800408C6
0x1800408bd  mov     rcx, r14; lpCriticalSection
0x1800408c0  call    cs:__imp_LeaveCriticalSection
0x1800408c6  mov     eax, ebx
0x1800408c8  mov     rcx, [rsp+2B8h+var_48]
0x1800408d0  xor     rcx, rsp; StackCookie
0x1800408d3  call    __security_check_cookie
0x1800408d8  mov     rbx, [rsp+2B8h+arg_18]
0x1800408e0  add     rsp, 280h
0x1800408e7  pop     r15
0x1800408e9  pop     r14
0x1800408eb  pop     r13
0x1800408ed  pop     r12
0x1800408ef  pop     rdi
0x1800408f0  pop     rsi
0x1800408f1  pop     rbp
0x1800408f2  retn
0x1800408f3  call    cs:__imp_GetCurrentThreadId
0x1800408f9  mov     ebx, eax
0x1800408fb  jmp     loc_1800407CD
0x180040900  mov     esi, 80070057h
0x180040905  jmp     short loc_180040892
0x180040907  mov     ebx, 0FFFFFFFFh
0x18004090c  jmp     loc_1800407CD
0x180040911  mov     r8d, 104h; nSize
0x180040917  lea     rdx, [rsp+2B8h+Filename]; lpFilename
0x18004091c  xor     ecx, ecx; hModule
0x18004091e  call    cs:__imp_GetModuleFileNameW
0x180040924  test    eax, eax
0x180040926  jnz     short loc_180040955
0x180040928  mov     ecx, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18004092e  cmp     ecx, 1
0x180040931  jnz     loc_1800407E7
0x180040937  jmp     loc_180040776
0x18004093c  mov     r9d, edi; char *
0x18004093f  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180040946  mov     edx, 0C8h; void *
0x18004094b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180040950  jmp     loc_1800407FA
0x180040955  mov     [rsp+2B8h+bIgnoreCase], 1; bIgnoreCase
0x18004095d  mov     [rsp+2B8h+cchValue], 0FFFFFFFFh; cchValue
0x180040965  lea     r9, StringValue; "\\EXPLORER.EXE"
0x18004096c  mov     r8d, 0FFFFFFFFh; cchSource
0x180040972  lea     rdx, [rsp+2B8h+Filename]; lpStringSource
0x180040977  mov     ecx, 800000h; dwFindStringOrdinalFlags
0x18004097c  call    cs:__imp_FindStringOrdinal
0x180040982  mov     ecx, esi
0x180040984  cmp     eax, 0FFFFFFFFh
0x180040987  setnz   cl
0x18004098a  inc     ecx
0x18004098c  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, ecx; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x180040992  jmp     short loc_18004092E
0x180040994  mov     ecx, 10h
0x180040999  call    cs:__imp_IsAppCompatModeEnabled
0x18004099f  test    eax, eax
0x1800409a1  jz      short loc_1800409B2
0x1800409a3  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, 2; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800409ad  jmp     loc_1800407E7
0x1800409b2  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800409b8  jmp     loc_18004076F
0x1800409bd  mov     edi, 8001010Eh
0x1800409c2  jmp     loc_1800407D7
0x1800409c7  lea     rdx, PKEY_ItemDate
0x1800409ce  mov     rcx, [rsp+2B8h+var_280]
0x1800409d3  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x1800409d8  test    eax, eax
0x1800409da  jz      loc_1800408B2
0x1800409e0  xor     esi, esi
0x1800409e2  xorps   xmm0, xmm0
0x1800409e5  xor     eax, eax
0x1800409e7  movups  xmmword ptr [r13+0], xmm0
0x1800409ec  mov     [r13+10h], rax
0x1800409f0  jmp     loc_1800408B2
```
