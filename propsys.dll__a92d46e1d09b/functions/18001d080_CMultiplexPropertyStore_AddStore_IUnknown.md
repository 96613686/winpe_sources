# CMultiplexPropertyStore::AddStore(IUnknown *)

- ea: `0x18001d080`
- end: `0x18001d39a`
- name: `?AddStore@CMultiplexPropertyStore@@UEAAJPEAUIUnknown@@@Z`
- size: `794`
- prototype: `__int64 __fastcall(CMultiplexPropertyStore *__hidden this, struct IUnknown *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001cee0`
- `0x18006d1b0`

## callees

- `0x1800054d0`
- `0x18001d080`
- `0x18002f9e0`
- `0x1800425c0`
- `0x180049780`
- `0x18006ed20`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001d2e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001d2e8`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18001d346`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18001d346`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x18001d156`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x18001d156`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d178`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001d178`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d279`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d279`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18001d107`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18001d107`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x18001d36c`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x18001d36c`

## string_xrefs

- `0x18001d309`: `onecoreuap\internal\shell\inc\private\cowthreadusedetection.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CMultiplexPropertyStore::AddStore(CMultiplexPropertyStore *this, struct IUnknown *a2)
{
  char *v4; // rdi
  int v5; // ebx
  int v6; // eax
  DWORD CurrentThreadId; // ebp
  HRESULT ApartmentType; // ebx
  int v9; // ebp
  HDPA v11; // rax
  HRESULT v12; // eax
  IPropertySetStorage *v13; // rcx
  int v14; // ecx
  int cchValue; // [rsp+20h] [rbp-288h]
  APTTYPE pAptType[2]; // [rsp+40h] [rbp-268h] BYREF
  APTTYPEQUALIFIER pAptQualifier[2]; // [rsp+48h] [rbp-260h] BYREF
  IPropertySetStorage *ppss; // [rsp+50h] [rbp-258h] BYREF
  WCHAR Filename[264]; // [rsp+60h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+0h]

  if ( this == (CMultiplexPropertyStore *)40 )
    v4 = 0;
  else
    v4 = (char *)this + 24;
  v5 = *((_DWORD *)v4 + 11);
  if ( v5 == 2 )
    goto LABEL_8;
  v6 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
  if ( `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess )
    goto LABEL_5;
  if ( GetModuleFileNameW(0, Filename, 0x104u) )
  {
    v14 = (FindStringOrdinal(0x800000u, Filename, -1, L"\\EXPLORER.EXE", -1, 1) != -1) + 1;
    `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = v14;
  }
  else
  {
    v14 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
  }
  if ( v14 != 1 )
    goto LABEL_17;
  if ( v5 == 1 )
  {
    if ( (unsigned int)IsAppCompatModeEnabled(16) )
    {
      `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = 2;
      goto LABEL_17;
    }
    v6 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
LABEL_5:
    if ( v6 != 1 )
      goto LABEL_17;
  }
LABEL_8:
  if ( *((_DWORD *)v4 + 10) == -3 )
    goto LABEL_17;
  CurrentThreadId = 0;
  pAptType[0] = APTTYPE_STA;
  pAptQualifier[0] = APTTYPEQUALIFIER_NONE;
  ApartmentType = CoGetApartmentType(pAptType, pAptQualifier);
  if ( ApartmentType < 0 )
    goto LABEL_16;
  if ( pAptType[0] == APTTYPE_STA )
  {
LABEL_34:
    CurrentThreadId = GetCurrentThreadId();
    goto LABEL_14;
  }
  if ( pAptType[0] == APTTYPE_MTA )
    goto LABEL_14;
  if ( pAptType[0] != APTTYPE_NA )
  {
    if ( pAptType[0] != APTTYPE_MAINSTA )
      goto LABEL_14;
    goto LABEL_34;
  }
  CurrentThreadId = -1;
LABEL_14:
  if ( CurrentThreadId != *((_DWORD *)v4 + 10) )
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
  if ( TryEnterCriticalSection((LPCRITICAL_SECTION)v4) )
    ApartmentType = 0;
LABEL_19:
  if ( ApartmentType < 0 )
  {
    v9 = ApartmentType;
    goto LABEL_21;
  }
  if ( !*((_QWORD *)this + 10) )
  {
    v11 = g_pfn_DPA_Create(4);
    *((_QWORD *)this + 10) = v11;
    if ( !v11 )
    {
      v9 = -2147024882;
      goto LABEL_21;
    }
  }
  v9 = -2147467261;
  if ( !a2 )
    goto LABEL_21;
  *(_QWORD *)pAptQualifier = 0;
  *(_QWORD *)pAptType = 0;
  if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, APTTYPE *))a2->lpVtbl->QueryInterface)(
         a2,
         &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
         pAptType) < 0 )
  {
    ppss = 0;
    v9 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, IPropertySetStorage **))a2->lpVtbl->QueryInterface)(
           a2,
           &GUID_0000013a_0000_0000_c000_000000000046,
           &ppss);
    if ( v9 < 0 )
      goto LABEL_21;
    v12 = PSCreatePropertyStoreFromPropertySetStorage(
            ppss,
            0,
            &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
            (void **)pAptQualifier);
    v13 = ppss;
  }
  else
  {
    v12 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, APTTYPEQUALIFIER *))pAptType)(
            *(_QWORD *)pAptType,
            &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
            pAptQualifier);
    v13 = *(IPropertySetStorage **)pAptType;
  }
  v9 = v12;
  ((void (__fastcall *)(IPropertySetStorage *))v13->lpVtbl->Release)(v13);
  if ( v9 >= 0 )
  {
    if ( DPA_InsertPtr(*((HDPA *)this + 10), 0x7FFFFFFF, *(void **)pAptQualifier) == -1 )
    {
      v9 = -2147024882;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pAptQualifier + 16LL))(*(_QWORD *)pAptQualifier);
    }
    else
    {
      v9 = 0;
    }
  }
LABEL_21:
  if ( ApartmentType >= 0 )
    LeaveCriticalSection((LPCRITICAL_SECTION)v4);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18001d080  mov     [rsp+arg_10], rbx
0x18001d085  push    rbp
0x18001d086  push    rsi
0x18001d087  push    rdi
0x18001d088  push    r14
0x18001d08a  push    r15
0x18001d08c  sub     rsp, 280h
0x18001d093  mov     rax, cs:__security_cookie
0x18001d09a  xor     rax, rsp
0x18001d09d  mov     [rsp+2A8h+var_38], rax
0x18001d0a5  mov     r14, rdx
0x18001d0a8  mov     rsi, rcx
0x18001d0ab  lea     rax, [rcx-28h]
0x18001d0af  xor     r15d, r15d
0x18001d0b2  test    rax, rax
0x18001d0b5  jz      loc_18001D35F
0x18001d0bb  lea     rdi, [rcx+18h]
0x18001d0bf  mov     [rsp+2A8h+var_278], rdi
0x18001d0c4  mov     ebx, [rdi+2Ch]
0x18001d0c7  cmp     ebx, 2
0x18001d0ca  jz      short loc_18001D0EA
0x18001d0cc  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18001d0d2  test    eax, eax
0x18001d0d4  jz      loc_18001D2DB
0x18001d0da  cmp     eax, 1
0x18001d0dd  jnz     short loc_18001D153
0x18001d0df  jmp     short loc_18001D0EA
0x18001d0e1  cmp     ebx, 1
0x18001d0e4  jz      loc_18001D367
0x18001d0ea  cmp     dword ptr [rdi+28h], 0FFFFFFFDh
0x18001d0ee  jz      short loc_18001D153
0x18001d0f0  mov     ebp, r15d
0x18001d0f3  mov     [rsp+2A8h+pAptType], r15d
0x18001d0f8  mov     [rsp+2A8h+pAptQualifier], r15d
0x18001d0fd  lea     rdx, [rsp+2A8h+pAptQualifier]; pAptQualifier
0x18001d102  lea     rcx, [rsp+2A8h+pAptType]; pAptType
0x18001d107  call    cs:__imp_CoGetApartmentType
0x18001d10d  mov     ebx, eax
0x18001d10f  test    eax, eax
0x18001d111  js      short loc_18001D143
0x18001d113  mov     ecx, [rsp+2A8h+pAptType]
0x18001d117  test    ecx, ecx
0x18001d119  jz      loc_18001D279
0x18001d11f  sub     ecx, 1
0x18001d122  jz      short loc_18001D13A
0x18001d124  sub     ecx, 1
0x18001d127  jz      loc_18001D286
0x18001d12d  cmp     ecx, 1
0x18001d130  jz      loc_18001D279
0x18001d136  test    eax, eax
0x18001d138  js      short loc_18001D143
0x18001d13a  cmp     ebp, [rdi+28h]
0x18001d13d  jnz     loc_18001D390
0x18001d143  mov     rcx, [rsp+2A8h]; this
0x18001d14b  test    ebx, ebx
0x18001d14d  js      loc_18001D306
0x18001d153  mov     rcx, rdi; lpCriticalSection
0x18001d156  call    cs:__imp_TryEnterCriticalSection
0x18001d15c  mov     ebx, 8001010Eh
0x18001d161  test    eax, eax
0x18001d163  cmovnz  ebx, r15d
0x18001d167  mov     [rsp+2A8h+var_270], ebx
0x18001d16b  test    ebx, ebx
0x18001d16d  jns     short loc_18001D1A7
0x18001d16f  mov     ebp, ebx
0x18001d171  test    ebx, ebx
0x18001d173  js      short loc_18001D17E
0x18001d175  mov     rcx, rdi; lpCriticalSection
0x18001d178  call    cs:__imp_LeaveCriticalSection
0x18001d17e  mov     eax, ebp
0x18001d180  mov     rcx, [rsp+2A8h+var_38]
0x18001d188  xor     rcx, rsp; StackCookie
0x18001d18b  call    __security_check_cookie
0x18001d190  mov     rbx, [rsp+2A8h+arg_10]
0x18001d198  add     rsp, 280h
0x18001d19f  pop     r15
0x18001d1a1  pop     r14
0x18001d1a3  pop     rdi
0x18001d1a4  pop     rsi
0x18001d1a5  pop     rbp
0x18001d1a6  retn
0x18001d1a7  cmp     qword ptr [rsi+50h], 0
0x18001d1ac  jnz     short loc_18001D1C6
0x18001d1ae  mov     ecx, 4; cItemGrow
0x18001d1b3  call    cs:g_pfn_DPA_Create
0x18001d1b9  mov     [rsi+50h], rax
0x18001d1bd  test    rax, rax
0x18001d1c0  jz      loc_18001D26F
0x18001d1c6  mov     ebp, 80004003h
0x18001d1cb  test    r14, r14
0x18001d1ce  jz      short loc_18001D171
0x18001d1d0  mov     qword ptr [rsp+2A8h+pAptQualifier], r15
0x18001d1d5  mov     qword ptr [rsp+2A8h+pAptType], r15
0x18001d1da  mov     rax, [r14]
0x18001d1dd  lea     r8, [rsp+2A8h+pAptType]
0x18001d1e2  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18001d1e9  mov     rcx, r14
0x18001d1ec  mov     rax, [rax]
0x18001d1ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1f4  test    eax, eax
0x18001d1f6  js      loc_18001D290
0x18001d1fc  mov     rcx, qword ptr [rsp+2A8h+pAptType]
0x18001d201  mov     rax, [rcx]
0x18001d204  lea     r8, [rsp+2A8h+pAptQualifier]
0x18001d209  lea     rdx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18001d210  mov     rax, [rax]
0x18001d213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d218  mov     rcx, qword ptr [rsp+2A8h+pAptType]
0x18001d21d  mov     ebp, eax
0x18001d21f  mov     rax, [rcx]
0x18001d222  mov     rax, [rax+10h]
0x18001d226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d22b  test    ebp, ebp
0x18001d22d  js      loc_18001D171
0x18001d233  mov     r8, qword ptr [rsp+2A8h+pAptQualifier]; p
0x18001d238  mov     edx, 7FFFFFFFh; i
0x18001d23d  mov     rcx, [rsi+50h]; hdpa
0x18001d241  call    cs:__imp_DPA_InsertPtr
0x18001d247  cmp     eax, 0FFFFFFFFh
0x18001d24a  jz      short loc_18001D254
0x18001d24c  mov     ebp, r15d
0x18001d24f  jmp     loc_18001D171
0x18001d254  mov     ebp, 8007000Eh
0x18001d259  mov     rcx, qword ptr [rsp+2A8h+pAptQualifier]
0x18001d25e  mov     rax, [rcx]
0x18001d261  mov     rax, [rax+10h]
0x18001d265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d26a  jmp     loc_18001D171
0x18001d26f  mov     ebp, 8007000Eh
0x18001d274  jmp     loc_18001D171
0x18001d279  call    cs:__imp_GetCurrentThreadId
0x18001d27f  mov     ebp, eax
0x18001d281  jmp     loc_18001D13A
0x18001d286  mov     ebp, 0FFFFFFFFh
0x18001d28b  jmp     loc_18001D13A
0x18001d290  mov     [rsp+2A8h+ppss], r15
0x18001d295  mov     rax, [r14]
0x18001d298  lea     r8, [rsp+2A8h+ppss]
0x18001d29d  lea     rdx, _GUID_0000013a_0000_0000_c000_000000000046
0x18001d2a4  mov     rcx, r14
0x18001d2a7  mov     rax, [rax]
0x18001d2aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2af  mov     ebp, eax
0x18001d2b1  test    eax, eax
0x18001d2b3  js      loc_18001D171
0x18001d2b9  lea     r9, [rsp+2A8h+pAptQualifier]; ppv
0x18001d2be  lea     r8, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x18001d2c5  xor     edx, edx; grfMode
0x18001d2c7  mov     rcx, [rsp+2A8h+ppss]; ppss
0x18001d2cc  call    PSCreatePropertyStoreFromPropertySetStorage
0x18001d2d1  mov     rcx, [rsp+2A8h+ppss]
0x18001d2d6  jmp     loc_18001D21D
0x18001d2db  mov     r8d, 104h; nSize
0x18001d2e1  lea     rdx, [rsp+2A8h+Filename]; lpFilename
0x18001d2e6  xor     ecx, ecx; hModule
0x18001d2e8  call    cs:__imp_GetModuleFileNameW
0x18001d2ee  test    eax, eax
0x18001d2f0  jnz     short loc_18001D31F
0x18001d2f2  mov     ecx, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18001d2f8  cmp     ecx, 1
0x18001d2fb  jnz     loc_18001D153
0x18001d301  jmp     loc_18001D0E1
0x18001d306  mov     r9d, ebx; char *
0x18001d309  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18001d310  mov     edx, 0C8h; void *
0x18001d315  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d31a  jmp     loc_18001D167
0x18001d31f  mov     [rsp+2A8h+bIgnoreCase], 1; bIgnoreCase
0x18001d327  mov     [rsp+2A8h+cchValue], 0FFFFFFFFh; cchValue
0x18001d32f  lea     r9, StringValue; "\\EXPLORER.EXE"
0x18001d336  mov     r8d, 0FFFFFFFFh; cchSource
0x18001d33c  lea     rdx, [rsp+2A8h+Filename]; lpStringSource
0x18001d341  mov     ecx, 800000h; dwFindStringOrdinalFlags
0x18001d346  call    cs:__imp_FindStringOrdinal
0x18001d34c  mov     ecx, r15d
0x18001d34f  cmp     eax, 0FFFFFFFFh
0x18001d352  setnz   cl
0x18001d355  inc     ecx
0x18001d357  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, ecx; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18001d35d  jmp     short loc_18001D2F8
0x18001d35f  mov     rdi, r15
0x18001d362  jmp     loc_18001D0BF
0x18001d367  mov     ecx, 10h
0x18001d36c  call    cs:__imp_IsAppCompatModeEnabled
0x18001d372  test    eax, eax
0x18001d374  jz      short loc_18001D385
0x18001d376  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, 2; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18001d380  jmp     loc_18001D153
0x18001d385  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18001d38b  jmp     loc_18001D0DA
0x18001d390  mov     ebx, 8001010Eh
0x18001d395  jmp     loc_18001D143
```
