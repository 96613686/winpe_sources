# CPropertyDescriptionList::GetAt(uint,_GUID const &,void * *)

- ea: `0x1800411c0`
- end: `0x18004143a`
- name: `?GetAt@CPropertyDescriptionList@@UEAAJIAEBU_GUID@@PEAPEAX@Z`
- size: `634`
- prototype: `__int64 __fastcall(CPropertyDescriptionList *__hidden this, unsigned int, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18002f9e0`
- `0x1800411c0`
- `0x18006ed20`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18004137a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18004137a`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1800413d8`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1800413d8`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x18004129c`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x18004129c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004130d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004130d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041356`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041356`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18004124d`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18004124d`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800413fe`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800413fe`

## string_xrefs

- `0x18004139b`: `onecoreuap\internal\shell\inc\private\cowthreadusedetection.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CPropertyDescriptionList::GetAt(
        CPropertyDescriptionList *this,
        unsigned int a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned __int64 v6; // r14
  char *v8; // rsi
  int v9; // ebx
  int v10; // eax
  DWORD CurrentThreadId; // ebx
  HRESULT ApartmentType; // edi
  __int64 v13; // rbx
  __int64 v14; // r14
  unsigned int v15; // ebp
  int v17; // ecx
  int cchValue; // [rsp+20h] [rbp-298h]
  APTTYPE pAptType; // [rsp+30h] [rbp-288h] BYREF
  APTTYPEQUALIFIER pAptQualifier[2]; // [rsp+38h] [rbp-280h] BYREF
  char *v21; // [rsp+40h] [rbp-278h]
  HRESULT v22; // [rsp+48h] [rbp-270h]
  WCHAR Filename[264]; // [rsp+50h] [rbp-268h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+0h]

  v6 = a2;
  *a4 = 0;
  if ( this )
    v8 = (char *)this + 56;
  else
    v8 = 0;
  v21 = v8;
  v9 = *((_DWORD *)v8 + 11);
  if ( v9 == 2 )
    goto LABEL_8;
  v10 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
  if ( `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess )
    goto LABEL_5;
  if ( GetModuleFileNameW(0, Filename, 0x104u) )
  {
    v17 = (FindStringOrdinal(0x800000u, Filename, -1, L"\\EXPLORER.EXE", -1, 1) != -1) + 1;
    `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = v17;
  }
  else
  {
    v17 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
  }
  if ( v17 != 1 )
    goto LABEL_17;
  if ( v9 == 1 )
  {
    if ( (unsigned int)IsAppCompatModeEnabled(16) )
    {
      `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = 2;
      goto LABEL_17;
    }
    v10 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
LABEL_5:
    if ( v10 != 1 )
      goto LABEL_17;
  }
LABEL_8:
  if ( *((_DWORD *)v8 + 10) == -3 )
    goto LABEL_17;
  CurrentThreadId = 0;
  pAptType = APTTYPE_STA;
  pAptQualifier[0] = APTTYPEQUALIFIER_NONE;
  ApartmentType = CoGetApartmentType(&pAptType, pAptQualifier);
  if ( ApartmentType < 0 )
    goto LABEL_16;
  if ( pAptType == APTTYPE_STA )
  {
LABEL_31:
    CurrentThreadId = GetCurrentThreadId();
    goto LABEL_14;
  }
  if ( pAptType == APTTYPE_MTA )
    goto LABEL_14;
  if ( pAptType != APTTYPE_NA )
  {
    if ( pAptType != APTTYPE_MAINSTA )
      goto LABEL_14;
    goto LABEL_31;
  }
  CurrentThreadId = -1;
LABEL_14:
  if ( CurrentThreadId != *((_DWORD *)v8 + 10) )
    ApartmentType = -2147417842;
LABEL_16:
  if ( ApartmentType < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xC8,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\cowthreadusedetection.h",
      (const char *)(unsigned int)ApartmentType,
      cchValue);
    goto LABEL_19;
  }
LABEL_17:
  ApartmentType = -2147417842;
  if ( TryEnterCriticalSection((LPCRITICAL_SECTION)v8) )
    ApartmentType = 0;
LABEL_19:
  v22 = ApartmentType;
  if ( ApartmentType < 0 )
  {
    v15 = ApartmentType;
  }
  else
  {
    v13 = 0;
    *(_QWORD *)pAptQualifier = 0;
    if ( v6 >= *((_QWORD *)this + 15) )
    {
      v15 = -2147316575;
      v14 = 0;
    }
    else
    {
      v14 = *(_QWORD *)(*((_QWORD *)this + 14) + 8 * v6);
      if ( v14 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
        v13 = v14;
        *(_QWORD *)pAptQualifier = v14;
      }
      else
      {
        v14 = 0;
      }
      v15 = (**(__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v14)(v14, a3, a4);
    }
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  if ( ApartmentType >= 0 )
    LeaveCriticalSection((LPCRITICAL_SECTION)v8);
  return v15;
}

```

## disassembly

```asm
0x1800411c0  push    rbx
0x1800411c2  push    rbp
0x1800411c3  push    rsi
0x1800411c4  push    rdi
0x1800411c5  push    r12
0x1800411c7  push    r13
0x1800411c9  push    r14
0x1800411cb  push    r15
0x1800411cd  sub     rsp, 278h
0x1800411d4  mov     rax, cs:__security_cookie
0x1800411db  xor     rax, rsp
0x1800411de  mov     [rsp+2B8h+var_58], rax
0x1800411e6  mov     r15, r9
0x1800411e9  mov     r12, r8
0x1800411ec  mov     r14d, edx
0x1800411ef  mov     rbp, rcx
0x1800411f2  xor     r13d, r13d
0x1800411f5  mov     [r9], r13
0x1800411f8  test    rcx, rcx
0x1800411fb  jz      loc_1800413F1
0x180041201  lea     rsi, [rcx+38h]
0x180041205  mov     [rsp+2B8h+var_278], rsi
0x18004120a  mov     ebx, [rsi+2Ch]
0x18004120d  cmp     ebx, 2
0x180041210  jz      short loc_180041230
0x180041212  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x180041218  test    eax, eax
0x18004121a  jz      loc_18004136D
0x180041220  cmp     eax, 1
0x180041223  jnz     short loc_180041299
0x180041225  jmp     short loc_180041230
0x180041227  cmp     ebx, 1
0x18004122a  jz      loc_1800413F9
0x180041230  cmp     dword ptr [rsi+28h], 0FFFFFFFDh
0x180041234  jz      short loc_180041299
0x180041236  mov     ebx, r13d
0x180041239  mov     [rsp+2B8h+pAptType], r13d
0x18004123e  mov     [rsp+2B8h+pAptQualifier], r13d
0x180041243  lea     rdx, [rsp+2B8h+pAptQualifier]; pAptQualifier
0x180041248  lea     rcx, [rsp+2B8h+pAptType]; pAptType
0x18004124d  call    cs:__imp_CoGetApartmentType
0x180041253  mov     edi, eax
0x180041255  test    eax, eax
0x180041257  js      short loc_180041289
0x180041259  mov     ecx, [rsp+2B8h+pAptType]
0x18004125d  test    ecx, ecx
0x18004125f  jz      loc_180041356
0x180041265  sub     ecx, 1
0x180041268  jz      short loc_180041280
0x18004126a  sub     ecx, 1
0x18004126d  jz      loc_180041363
0x180041273  cmp     ecx, 1
0x180041276  jz      loc_180041356
0x18004127c  test    eax, eax
0x18004127e  js      short loc_180041289
0x180041280  cmp     ebx, [rsi+28h]
0x180041283  jnz     loc_180041422
0x180041289  mov     rcx, [rsp+2B8h]; this
0x180041291  test    edi, edi
0x180041293  js      loc_180041398
0x180041299  mov     rcx, rsi; lpCriticalSection
0x18004129c  call    cs:__imp_TryEnterCriticalSection
0x1800412a2  mov     edi, 8001010Eh
0x1800412a7  test    eax, eax
0x1800412a9  cmovnz  edi, r13d
0x1800412ad  mov     [rsp+2B8h+var_270], edi
0x1800412b1  test    edi, edi
0x1800412b3  js      loc_180041339
0x1800412b9  mov     rbx, r13
0x1800412bc  mov     qword ptr [rsp+2B8h+pAptQualifier], rbx
0x1800412c1  cmp     r14, [rbp+78h]
0x1800412c5  jnb     loc_18004142C
0x1800412cb  mov     rax, [rbp+70h]
0x1800412cf  mov     r14, [rax+r14*8]
0x1800412d3  test    r14, r14
0x1800412d6  jnz     short loc_18004133D
0x1800412d8  mov     r14, r13
0x1800412db  mov     rax, [r14]
0x1800412de  mov     r8, r15
0x1800412e1  mov     rdx, r12
0x1800412e4  mov     rcx, r14
0x1800412e7  mov     rax, [rax]
0x1800412ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800412ef  mov     ebp, eax
0x1800412f1  test    r14, r14
0x1800412f4  jz      short loc_180041306
0x1800412f6  mov     rax, [rbx]
0x1800412f9  mov     rcx, rbx
0x1800412fc  mov     rax, [rax+10h]
0x180041300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041305  nop
0x180041306  test    edi, edi
0x180041308  js      short loc_180041313
0x18004130a  mov     rcx, rsi; lpCriticalSection
0x18004130d  call    cs:__imp_LeaveCriticalSection
0x180041313  mov     eax, ebp
0x180041315  mov     rcx, [rsp+2B8h+var_58]
0x18004131d  xor     rcx, rsp; StackCookie
0x180041320  call    __security_check_cookie
0x180041325  add     rsp, 278h
0x18004132c  pop     r15
0x18004132e  pop     r14
0x180041330  pop     r13
0x180041332  pop     r12
0x180041334  pop     rdi
0x180041335  pop     rsi
0x180041336  pop     rbp
0x180041337  pop     rbx
0x180041338  retn
0x180041339  mov     ebp, edi
0x18004133b  jmp     short loc_180041306
0x18004133d  mov     rax, [r14]
0x180041340  mov     rcx, r14
0x180041343  mov     rax, [rax+8]
0x180041347  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004134c  mov     rbx, r14
0x18004134f  mov     qword ptr [rsp+2B8h+pAptQualifier], rbx
0x180041354  jmp     short loc_1800412DB
0x180041356  call    cs:__imp_GetCurrentThreadId
0x18004135c  mov     ebx, eax
0x18004135e  jmp     loc_180041280
0x180041363  mov     ebx, 0FFFFFFFFh
0x180041368  jmp     loc_180041280
0x18004136d  mov     r8d, 104h; nSize
0x180041373  lea     rdx, [rsp+2B8h+Filename]; lpFilename
0x180041378  xor     ecx, ecx; hModule
0x18004137a  call    cs:__imp_GetModuleFileNameW
0x180041380  test    eax, eax
0x180041382  jnz     short loc_1800413B1
0x180041384  mov     ecx, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18004138a  cmp     ecx, 1
0x18004138d  jnz     loc_180041299
0x180041393  jmp     loc_180041227
0x180041398  mov     r9d, edi; char *
0x18004139b  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x1800413a2  mov     edx, 0C8h; void *
0x1800413a7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800413ac  jmp     loc_1800412AD
0x1800413b1  mov     [rsp+2B8h+bIgnoreCase], 1; bIgnoreCase
0x1800413b9  mov     [rsp+2B8h+cchValue], 0FFFFFFFFh; cchValue
0x1800413c1  lea     r9, StringValue; "\\EXPLORER.EXE"
0x1800413c8  mov     r8d, 0FFFFFFFFh; cchSource
0x1800413ce  lea     rdx, [rsp+2B8h+Filename]; lpStringSource
0x1800413d3  mov     ecx, 800000h; dwFindStringOrdinalFlags
0x1800413d8  call    cs:__imp_FindStringOrdinal
0x1800413de  mov     ecx, r13d
0x1800413e1  cmp     eax, 0FFFFFFFFh
0x1800413e4  setnz   cl
0x1800413e7  inc     ecx
0x1800413e9  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, ecx; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800413ef  jmp     short loc_18004138A
0x1800413f1  mov     rsi, r13
0x1800413f4  jmp     loc_180041205
0x1800413f9  mov     ecx, 10h
0x1800413fe  call    cs:__imp_IsAppCompatModeEnabled
0x180041404  test    eax, eax
0x180041406  jz      short loc_180041417
0x180041408  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, 2; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x180041412  jmp     loc_180041299
0x180041417  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18004141d  jmp     loc_180041220
0x180041422  mov     edi, 8001010Eh
0x180041427  jmp     loc_180041289
0x18004142c  mov     ebp, 80028CA1h
0x180041431  mov     r14, r13
0x180041434  jmp     loc_1800412F1
```
