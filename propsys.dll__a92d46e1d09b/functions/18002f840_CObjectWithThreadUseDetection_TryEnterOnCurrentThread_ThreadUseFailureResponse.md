# CObjectWithThreadUseDetection::TryEnterOnCurrentThread(ThreadUseFailureResponse)

- ea: `0x18002f840`
- end: `0x18002f9da`
- name: `?TryEnterOnCurrentThread@CObjectWithThreadUseDetection@@IEAAJW4ThreadUseFailureResponse@@@Z`
- size: `410`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `62`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180016350`
- `0x18002f180`
- `0x18002f2f0`
- `0x18002f3e0`
- `0x18002f6d0`
- `0x18002f7c0`
- `0x180031630`
- `0x180031800`
- `0x180031dc0`
- `0x180031e60`
- `0x1800321f0`
- `0x180032340`
- `0x180041460`
- `0x180055ac0`
- `0x180057470`
- `0x180057610`
- `0x18005a8d0`
- `0x18005bc60`
- `0x18005c400`
- `0x18005c6b0`
- `0x18005ccd0`
- `0x180060dd0`
- `0x1800613a0`
- `0x180062eb0`
- `0x1800630e0`
- `0x180063810`
- `0x180064040`
- `0x180064de0`
- `0x180066f20`
- `0x18006d1b0`
- `0x180073e60`
- `0x1800748d0`
- `0x180074fb0`
- `0x180079150`
- `0x1800791d0`
- `0x180079270`
- `0x180079380`
- `0x180079490`
- `0x180079520`
- `0x180079590`
- `0x180079670`
- `0x180079750`
- `0x180079a10`
- `0x180079be0`
- `0x180079d90`
- `0x180079e20`
- `0x18007a0e0`
- `0x18007a210`
- `0x18007a280`
- `0x1800803a0`

## callees

- `0x18002f840`
- `0x18002f9e0`
- `0x18006ed20`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18002f94a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18002f94a`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18002f98f`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x18002f98f`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x18002f8d9`
- `api-ms-win-core-synch-l1-1-0!TryEnterCriticalSection` at `0x18002f8d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f92c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f92c`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18002f8a8`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x18002f8a8`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x18002f9ac`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x18002f9ac`

## string_xrefs

- `0x18002f916`: `onecoreuap\internal\shell\inc\private\cowthreadusedetection.h`

## pseudocode

```c
__int64 __fastcall CObjectWithThreadUseDetection::TryEnterOnCurrentThread(__int64 a1)
{
  int v1; // edi
  int v3; // eax
  unsigned int ApartmentType; // edi
  DWORD CurrentThreadId; // edx
  int v7; // ecx
  int cchValue; // [rsp+20h] [rbp-248h]
  APTTYPE pAptType; // [rsp+30h] [rbp-238h] BYREF
  APTTYPEQUALIFIER pAptQualifier[3]; // [rsp+34h] [rbp-234h] BYREF
  WCHAR Filename[264]; // [rsp+40h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  v1 = *(_DWORD *)(a1 + 44);
  if ( v1 == 2 )
    goto LABEL_6;
  v3 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
  if ( `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess )
    goto LABEL_3;
  if ( GetModuleFileNameW(0, Filename, 0x104u) )
  {
    v7 = (FindStringOrdinal(0x800000u, Filename, -1, L"\\EXPLORER.EXE", -1, 1) != -1) + 1;
    `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = v7;
  }
  else
  {
    v7 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
  }
  if ( v7 != 1 )
    goto LABEL_13;
  if ( v1 != 1 )
  {
LABEL_6:
    if ( *(_DWORD *)(a1 + 40) == -3 )
      goto LABEL_13;
    pAptType = APTTYPE_STA;
    pAptQualifier[0] = APTTYPEQUALIFIER_NONE;
    ApartmentType = CoGetApartmentType(&pAptType, pAptQualifier);
    if ( (ApartmentType & 0x80000000) != 0 )
      goto LABEL_16;
    CurrentThreadId = 0;
    if ( pAptType == APTTYPE_STA )
      goto LABEL_17;
    if ( pAptType != APTTYPE_MTA )
    {
      if ( pAptType == APTTYPE_NA )
      {
        CurrentThreadId = -1;
        goto LABEL_12;
      }
      if ( pAptType == APTTYPE_MAINSTA )
LABEL_17:
        CurrentThreadId = GetCurrentThreadId();
    }
LABEL_12:
    if ( CurrentThreadId == *(_DWORD *)(a1 + 40) )
      goto LABEL_13;
    ApartmentType = -2147417842;
LABEL_16:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xC8,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\cowthreadusedetection.h",
      (const char *)ApartmentType,
      cchValue);
    return ApartmentType;
  }
  if ( !(unsigned int)IsAppCompatModeEnabled(16) )
  {
    v3 = `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess;
LABEL_3:
    if ( v3 != 1 )
      goto LABEL_13;
    goto LABEL_6;
  }
  `_ShouldCheckApartments'::`5'::s_tbEnforceForProcess = 2;
LABEL_13:
  ApartmentType = -2147417842;
  if ( TryEnterCriticalSection((LPCRITICAL_SECTION)a1) )
    return 0;
  return ApartmentType;
}

```

## disassembly

```asm
0x18002f840  mov     [rsp+arg_8], rbx
0x18002f845  push    rdi
0x18002f846  sub     rsp, 260h
0x18002f84d  mov     rax, cs:__security_cookie
0x18002f854  xor     rax, rsp
0x18002f857  mov     [rsp+268h+var_18], rax
0x18002f85f  mov     edi, [rcx+2Ch]
0x18002f862  mov     rbx, rcx
0x18002f865  cmp     edi, 2
0x18002f868  jz      short loc_18002F888
0x18002f86a  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18002f870  test    eax, eax
0x18002f872  jz      loc_18002F93D
0x18002f878  cmp     eax, 1
0x18002f87b  jnz     short loc_18002F8D6
0x18002f87d  jmp     short loc_18002F888
0x18002f87f  cmp     edi, 1
0x18002f882  jz      loc_18002F9A7
0x18002f888  cmp     dword ptr [rbx+28h], 0FFFFFFFDh
0x18002f88c  jz      short loc_18002F8D6
0x18002f88e  lea     rdx, [rsp+268h+pAptQualifier]; pAptQualifier
0x18002f893  mov     [rsp+268h+pAptType], 0
0x18002f89b  lea     rcx, [rsp+268h+pAptType]; pAptType
0x18002f8a0  mov     [rsp+268h+pAptQualifier], 0
0x18002f8a8  call    cs:__imp_CoGetApartmentType
0x18002f8ae  mov     edi, eax
0x18002f8b0  test    eax, eax
0x18002f8b2  js      short loc_18002F90E
0x18002f8b4  mov     ecx, [rsp+268h+pAptType]
0x18002f8b8  xor     edx, edx
0x18002f8ba  test    ecx, ecx
0x18002f8bc  jz      short loc_18002F92C
0x18002f8be  sub     ecx, 1
0x18002f8c1  jz      short loc_18002F8CD
0x18002f8c3  sub     ecx, 1
0x18002f8c6  jz      short loc_18002F936
0x18002f8c8  cmp     ecx, 1
0x18002f8cb  jz      short loc_18002F92C
0x18002f8cd  cmp     edx, [rbx+28h]
0x18002f8d0  jnz     loc_18002F9D0
0x18002f8d6  mov     rcx, rbx; lpCriticalSection
0x18002f8d9  call    cs:__imp_TryEnterCriticalSection
0x18002f8df  xor     ecx, ecx
0x18002f8e1  mov     edi, 8001010Eh
0x18002f8e6  test    eax, eax
0x18002f8e8  cmovnz  edi, ecx
0x18002f8eb  mov     eax, edi
0x18002f8ed  mov     rcx, [rsp+268h+var_18]
0x18002f8f5  xor     rcx, rsp; StackCookie
0x18002f8f8  call    __security_check_cookie
0x18002f8fd  mov     rbx, [rsp+268h+arg_8]
0x18002f905  add     rsp, 260h
0x18002f90c  pop     rdi
0x18002f90d  retn
0x18002f90e  mov     rcx, [rsp+268h]; this
0x18002f916  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18002f91d  mov     r9d, edi; char *
0x18002f920  mov     edx, 0C8h; void *
0x18002f925  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002f92a  jmp     short loc_18002F8EB
0x18002f92c  call    cs:__imp_GetCurrentThreadId
0x18002f932  mov     edx, eax
0x18002f934  jmp     short loc_18002F8CD
0x18002f936  mov     edx, 0FFFFFFFFh
0x18002f93b  jmp     short loc_18002F8CD
0x18002f93d  mov     r8d, 104h; nSize
0x18002f943  lea     rdx, [rsp+268h+Filename]; lpFilename
0x18002f948  xor     ecx, ecx; hModule
0x18002f94a  call    cs:__imp_GetModuleFileNameW
0x18002f950  test    eax, eax
0x18002f952  jnz     short loc_18002F968
0x18002f954  mov     ecx, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18002f95a  cmp     ecx, 1
0x18002f95d  jnz     loc_18002F8D6
0x18002f963  jmp     loc_18002F87F
0x18002f968  mov     [rsp+268h+bIgnoreCase], 1; bIgnoreCase
0x18002f970  lea     r9, StringValue; "\\EXPLORER.EXE"
0x18002f977  mov     r8d, 0FFFFFFFFh; cchSource
0x18002f97d  mov     [rsp+268h+cchValue], 0FFFFFFFFh; cchValue
0x18002f985  lea     rdx, [rsp+268h+Filename]; lpStringSource
0x18002f98a  mov     ecx, 800000h; dwFindStringOrdinalFlags
0x18002f98f  call    cs:__imp_FindStringOrdinal
0x18002f995  xor     ecx, ecx
0x18002f997  cmp     eax, 0FFFFFFFFh
0x18002f99a  setnz   cl
0x18002f99d  inc     ecx
0x18002f99f  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, ecx; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18002f9a5  jmp     short loc_18002F95A
0x18002f9a7  mov     ecx, 10h
0x18002f9ac  call    cs:__imp_IsAppCompatModeEnabled
0x18002f9b2  test    eax, eax
0x18002f9b4  jz      short loc_18002F9C5
0x18002f9b6  mov     cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A, 2; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18002f9c0  jmp     loc_18002F8D6
0x18002f9c5  mov     eax, cs:?s_tbEnforceForProcess@?4??_ShouldCheckApartments@@YA_NW4ApartmentCheckEnum@@@Z@4W4TRIBIT@@A; TRIBIT `_ShouldCheckApartments(ApartmentCheckEnum)'::`5'::s_tbEnforceForProcess
0x18002f9cb  jmp     loc_18002F878
0x18002f9d0  mov     edi, 8001010Eh
0x18002f9d5  jmp     loc_18002F90E
```
