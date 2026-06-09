# CPropertyProvider::GetAt(ulong,_tagpropertykey *)

- ea: `0x1800426e0`
- end: `0x18004290d`
- name: `?GetAt@CPropertyProvider@@UEAAJKPEAU_tagpropertykey@@@Z`
- size: `557`
- prototype: `__int64 __fastcall(CPropertyProvider *__hidden this, unsigned int, struct _tagpropertykey *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18002f9e0`
- `0x1800426e0`
- `0x18006ed20`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18004285d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18004285d`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1800428bb`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x1800428bb`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1800427c8`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x1800427c8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042804`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042804`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180042833`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180042833`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180042778`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x180042778`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800428df`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800428df`

## string_xrefs

- `0x18004287e`: `onecoreuap\internal\shell\inc\private\cowthreadusedetection.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPropertyProvider::GetAt(CPropertyProvider *this, unsigned int a2, struct _tagpropertykey *a3)
{
  char *v6; // rdi
  int v7; // ebx
  int v8; // eax
  DWORD CurrentThreadId; // r14d
  HRESULT ApartmentType; // ebx
  unsigned int v11; // esi
  int v13; // ecx
  int cchValue; // [rsp+20h] [rbp-278h]
  APTTYPE pAptType; // [rsp+30h] [rbp-268h] BYREF
  APTTYPEQUALIFIER pAptQualifier; // [rsp+34h] [rbp-264h] BYREF
  char *v17; // [rsp+38h] [rbp-260h]
  HRESULT v18; // [rsp+40h] [rbp-258h]
  WCHAR Filename[264]; // [rsp+50h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]

  *a3 = PKEY_Null;
  if ( this )
    v6 = (char *)this + 72;
  else
    v6 = 0;
  v17 = v6;
  v7 = *((_DWORD *)v6 + 11);
  if ( v7 == 2 )
    goto LABEL_8;
  v8 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
  if ( `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess )
    goto LABEL_5;
  if ( GetModuleFileNameW(0, Filename, 0x104u) )
  {
    v13 = (FindStringOrdinal(0x800000u, Filename, -1, L"\\EXPLORER.EXE", -1, 1) != -1) + 1;
    `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = v13;
  }
  else
  {
    v13 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
  }
  if ( v13 != 1 )
    goto LABEL_17;
  if ( v7 == 1 )
  {
    if ( (unsigned int)IsAppCompatModeEnabled(16) )
    {
      `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = 2;
      goto LABEL_17;
    }
    v8 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
LABEL_5:
    if ( v8 != 1 )
      goto LABEL_17;
  }
LABEL_8:
  if ( *((_DWORD *)v6 + 10) == -3 )
    goto LABEL_17;
  CurrentThreadId = 0;
  pAptType = APTTYPE_STA;
  pAptQualifier = APTTYPEQUALIFIER_NONE;
  ApartmentType = CoGetApartmentType(&pAptType, &pAptQualifier);
  if ( ApartmentType < 0 )
    goto LABEL_16;
  if ( pAptType == APTTYPE_STA )
  {
LABEL_24:
    CurrentThreadId = GetCurrentThreadId();
    goto LABEL_14;
  }
  if ( pAptType == APTTYPE_MTA )
    goto LABEL_14;
  if ( pAptType != APTTYPE_NA )
  {
    if ( pAptType != APTTYPE_MAINSTA )
      goto LABEL_14;
    goto LABEL_24;
  }
  CurrentThreadId = -1;
LABEL_14:
  if ( CurrentThreadId != *((_DWORD *)v6 + 10) )
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
  if ( TryEnterCriticalSection((LPCRITICAL_SECTION)v6) )
    ApartmentType = 0;
LABEL_19:
  v18 = ApartmentType;
  if ( ApartmentType < 0 )
    v11 = ApartmentType;
  else
    v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct _tagpropertykey *))(**((_QWORD **)this + 16) + 32LL))(
            *((_QWORD *)this + 16),
            a2,
            a3);
  if ( ApartmentType >= 0 )
    LeaveCriticalSection((LPCRITICAL_SECTION)v6);
  return v11;
}

```

## disassembly

```asm
0x1800426e0  mov     [rsp+arg_18], rbx
0x1800426e5  push    rbp
0x1800426e6  push    rsi
0x1800426e7  push    rdi
0x1800426e8  push    r14
0x1800426ea  push    r15
0x1800426ec  sub     rsp, 270h
0x1800426f3  mov     rax, cs:__security_cookie
0x1800426fa  xor     rax, rsp
0x1800426fd  mov     [rsp+298h+var_38], rax
0x180042705  mov     rbp, r8
0x180042708  mov     r15d, edx
0x18004270b  mov     rsi, rcx
0x18004270e  movups  xmm0, xmmword ptr cs:PKEY_Null.fmtid.Data1
0x180042715  movups  xmmword ptr [r8], xmm0
0x180042719  mov     eax, cs:PKEY_Null.pid
0x18004271f  mov     [r8+10h], eax
0x180042723  test    rcx, rcx
0x180042726  jz      loc_1800428D3
0x18004272c  lea     rdi, [rcx+48h]
0x180042730  mov     [rsp+298h+var_260], rdi
0x180042735  mov     ebx, [rdi+2Ch]
0x180042738  cmp     ebx, 2
0x18004273b  jz      short loc_18004275B
0x18004273d  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x180042743  test    eax, eax
0x180042745  jz      loc_180042850
0x18004274b  cmp     eax, 1
0x18004274e  jnz     short loc_1800427C5
0x180042750  jmp     short loc_18004275B
0x180042752  cmp     ebx, 1
0x180042755  jz      loc_1800428DA
0x18004275b  cmp     dword ptr [rdi+28h], 0FFFFFFFDh
0x18004275f  jz      short loc_1800427C5
0x180042761  xor     r14d, r14d
0x180042764  mov     [rsp+298h+pAptType], r14d
0x180042769  mov     [rsp+298h+pAptQualifier], r14d
0x18004276e  lea     rdx, [rsp+298h+pAptQualifier]; pAptQualifier
0x180042773  lea     rcx, [rsp+298h+pAptType]; pAptType
0x180042778  call    cs:__imp_CoGetApartmentType
0x18004277e  mov     ebx, eax
0x180042780  test    eax, eax
0x180042782  js      short loc_1800427B5
0x180042784  mov     ecx, [rsp+298h+pAptType]
0x180042788  test    ecx, ecx
0x18004278a  jz      loc_180042833
0x180042790  sub     ecx, 1
0x180042793  jz      short loc_1800427AB
0x180042795  sub     ecx, 1
0x180042798  jz      loc_180042845
0x18004279e  cmp     ecx, 1
0x1800427a1  jz      loc_180042833
0x1800427a7  test    eax, eax
0x1800427a9  js      short loc_1800427B5
0x1800427ab  cmp     r14d, [rdi+28h]
0x1800427af  jnz     loc_180042903
0x1800427b5  mov     rcx, [rsp+298h]; this
0x1800427bd  test    ebx, ebx
0x1800427bf  js      loc_18004287B
0x1800427c5  mov     rcx, rdi; lpCriticalSection
0x1800427c8  call    cs:__imp_TryEnterCriticalSection
0x1800427ce  xor     ecx, ecx
0x1800427d0  mov     ebx, 8001010Eh
0x1800427d5  test    eax, eax
0x1800427d7  cmovnz  ebx, ecx
0x1800427da  mov     [rsp+298h+var_258], ebx
0x1800427de  test    ebx, ebx
0x1800427e0  js      short loc_180042841
0x1800427e2  mov     rcx, [rsi+80h]
0x1800427e9  mov     rax, [rcx]
0x1800427ec  mov     r8, rbp
0x1800427ef  mov     edx, r15d
0x1800427f2  mov     rax, [rax+20h]
0x1800427f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800427fb  mov     esi, eax
0x1800427fd  test    ebx, ebx
0x1800427ff  js      short loc_18004280A
0x180042801  mov     rcx, rdi; lpCriticalSection
0x180042804  call    cs:__imp_LeaveCriticalSection
0x18004280a  mov     eax, esi
0x18004280c  mov     rcx, [rsp+298h+var_38]
0x180042814  xor     rcx, rsp; StackCookie
0x180042817  call    __security_check_cookie
0x18004281c  mov     rbx, [rsp+298h+arg_18]
0x180042824  add     rsp, 270h
0x18004282b  pop     r15
0x18004282d  pop     r14
0x18004282f  pop     rdi
0x180042830  pop     rsi
0x180042831  pop     rbp
0x180042832  retn
0x180042833  call    cs:__imp_GetCurrentThreadId
0x180042839  mov     r14d, eax
0x18004283c  jmp     loc_1800427AB
0x180042841  mov     esi, ebx
0x180042843  jmp     short loc_1800427FD
0x180042845  mov     r14d, 0FFFFFFFFh
0x18004284b  jmp     loc_1800427AB
0x180042850  mov     r8d, 104h; nSize
0x180042856  lea     rdx, [rsp+298h+Filename]; lpFilename
0x18004285b  xor     ecx, ecx; hModule
0x18004285d  call    cs:__imp_GetModuleFileNameW
0x180042863  test    eax, eax
0x180042865  jnz     short loc_180042894
0x180042867  mov     ecx, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18004286d  cmp     ecx, 1
0x180042870  jnz     loc_1800427C5
0x180042876  jmp     loc_180042752
0x18004287b  mov     r9d, ebx; char *
0x18004287e  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180042885  mov     edx, 0C8h; void *
0x18004288a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004288f  jmp     loc_1800427DA
0x180042894  mov     [rsp+298h+bIgnoreCase], 1; bIgnoreCase
0x18004289c  mov     [rsp+298h+cchValue], 0FFFFFFFFh; cchValue
0x1800428a4  lea     r9, StringValue; "\\EXPLORER.EXE"
0x1800428ab  mov     r8d, 0FFFFFFFFh; cchSource
0x1800428b1  lea     rdx, [rsp+298h+Filename]; lpStringSource
0x1800428b6  mov     ecx, 800000h; dwFindStringOrdinalFlags
0x1800428bb  call    cs:__imp_FindStringOrdinal
0x1800428c1  xor     ecx, ecx
0x1800428c3  cmp     eax, 0FFFFFFFFh
0x1800428c6  setnz   cl
0x1800428c9  inc     ecx
0x1800428cb  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, ecx; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800428d1  jmp     short loc_18004286D
0x1800428d3  xor     edi, edi
0x1800428d5  jmp     loc_180042730
0x1800428da  mov     ecx, 10h
0x1800428df  call    cs:__imp_IsAppCompatModeEnabled
0x1800428e5  test    eax, eax
0x1800428e7  jz      short loc_1800428F8
0x1800428e9  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, 2; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800428f3  jmp     loc_1800427C5
0x1800428f8  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x1800428fe  jmp     loc_18004274B
0x180042903  mov     ebx, 8001010Eh
0x180042908  jmp     loc_1800427B5
```
