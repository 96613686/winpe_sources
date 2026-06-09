# EnsureBcp47LangsLibraryIsLoaded(void)

- ea: `0x1800ce4d4`
- end: `0x1800ce699`
- name: `?EnsureBcp47LangsLibraryIsLoaded@@YA_NXZ`
- size: `453`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180097ad0`

## callees

- `0x18009c9ac`
- `0x18009ca1c`
- `0x1800ce4d4`
- `0x1800cec68`
- `0x1800cefb8`
- `0x1800cf020`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ce58e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ce5a9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ce5c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ce5df`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ce5fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ce615`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ce630`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ce58e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ce5a9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ce5c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ce5df`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ce5fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ce615`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ce630`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800ce56e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800ce56e`

## string_xrefs

- `0x1800ce565`: `Bcp47Langs.dll`
- `0x1800ce5ec`: `RemoveUserLanguageInputMethods`

## pseudocode

```c
char __fastcall EnsureBcp47LangsLibraryIsLoaded(Tsf3OverrideUtil *a1)
{
  Tsf3OverrideUtil *v1; // rcx
  char v2; // bl
  Tsf3OverrideUtil *v3; // rcx
  char v4; // al
  HMODULE Library; // rax

  v2 = 1;
  if ( Tsf3OverrideUtil::IsRunningOnDesktop(a1) || Tsf3OverrideUtil::IsRunningOnServerSku(v1) )
    goto LABEL_8;
  if ( __TSS0__1__IsRunningOnHub_Tsf3OverrideUtil__YA_NXZ_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer
                                                                            + (unsigned int)tls_index)
                                                                          + 4LL) )
  {
    Init_thread_header(&__TSS0__1__IsRunningOnHub_Tsf3OverrideUtil__YA_NXZ_4HA);
    if ( __TSS0__1__IsRunningOnHub_Tsf3OverrideUtil__YA_NXZ_4HA == -1 )
    {
      `Tsf3OverrideUtil::IsRunningOnHub'::`2'::deviceFamily = Tsf3OverrideUtil::GetDeviceFamily(v3);
      Init_thread_footer(&__TSS0__1__IsRunningOnHub_Tsf3OverrideUtil__YA_NXZ_4HA);
    }
  }
  if ( `Tsf3OverrideUtil::IsRunningOnHub'::`2'::deviceFamily == 6 )
LABEL_8:
    v4 = 1;
  else
    v4 = 0;
  if ( !hBcp47LangsDll )
  {
    if ( !v4 )
      return 0;
    Library = LoadLibraryExW(L"Bcp47Langs.dll", 0, 0);
    hBcp47LangsDll = Library;
    if ( !Library )
      return 0;
    pfnBcp47FromHkl = (__int64)GetProcAddress(Library, "Bcp47FromHkl");
    pfnBcp47BufferFromLcid = (__int64)GetProcAddress(hBcp47LangsDll, "Bcp47BufferFromLcid");
    pfnAppendUserLanguages = (__int64)GetProcAddress(hBcp47LangsDll, "AppendUserLanguages");
    pfnAppendUserLanguageInputMethods = (__int64)GetProcAddress(hBcp47LangsDll, "AppendUserLanguageInputMethods");
    pfnRemoveUserLanguageInputMethods = (__int64)GetProcAddress(hBcp47LangsDll, "RemoveUserLanguageInputMethods");
    pfnGetUserLanguageInputMethods = (__int64)GetProcAddress(hBcp47LangsDll, "GetUserLanguageInputMethods");
    pfnSetUserLanguageInputMethods = (__int64)GetProcAddress(hBcp47LangsDll, "SetUserLanguageInputMethods");
    if ( !hBcp47LangsDll )
      return 0;
  }
  if ( !pfnBcp47FromHkl
    || !pfnBcp47BufferFromLcid
    || !pfnAppendUserLanguages
    || !pfnAppendUserLanguageInputMethods
    || !pfnRemoveUserLanguageInputMethods
    || !pfnGetUserLanguageInputMethods
    || !pfnSetUserLanguageInputMethods )
  {
    return 0;
  }
  return v2;
}

```

## disassembly

```asm
0x1800ce4d4  push    rbx
0x1800ce4d6  sub     rsp, 20h
0x1800ce4da  call    ?IsRunningOnDesktop@Tsf3OverrideUtil@@YA_NXZ; Tsf3OverrideUtil::IsRunningOnDesktop(void)
0x1800ce4df  mov     bl, 1
0x1800ce4e1  test    al, al
0x1800ce4e3  jnz     short loc_1800CE54A
0x1800ce4e5  call    ?IsRunningOnServerSku@Tsf3OverrideUtil@@YA_NXZ; Tsf3OverrideUtil::IsRunningOnServerSku(void)
0x1800ce4ea  test    al, al
0x1800ce4ec  jnz     short loc_1800CE54A
0x1800ce4ee  mov     ecx, cs:_tls_index
0x1800ce4f4  mov     rax, gs:58h
0x1800ce4fd  mov     edx, 4
0x1800ce502  mov     rax, [rax+rcx*8]
0x1800ce506  mov     eax, [rdx+rax]
0x1800ce509  cmp     cs:?$TSS0@?1??IsRunningOnHub@Tsf3OverrideUtil@@YA_NXZ@4HA, eax
0x1800ce50f  jle     short loc_1800CE53D
0x1800ce511  lea     rcx, ?$TSS0@?1??IsRunningOnHub@Tsf3OverrideUtil@@YA_NXZ@4HA
0x1800ce518  call    _Init_thread_header
0x1800ce51d  cmp     cs:?$TSS0@?1??IsRunningOnHub@Tsf3OverrideUtil@@YA_NXZ@4HA, 0FFFFFFFFh
0x1800ce524  jnz     short loc_1800CE53D
0x1800ce526  call    ?GetDeviceFamily@Tsf3OverrideUtil@@YAKXZ; Tsf3OverrideUtil::GetDeviceFamily(void)
0x1800ce52b  lea     rcx, ?$TSS0@?1??IsRunningOnHub@Tsf3OverrideUtil@@YA_NXZ@4HA
0x1800ce532  mov     cs:?deviceFamily@?1??IsRunningOnHub@Tsf3OverrideUtil@@YA_NXZ@4KA, eax; ulong `Tsf3OverrideUtil::IsRunningOnHub(void)'::`2'::deviceFamily
0x1800ce538  call    _Init_thread_footer
0x1800ce53d  cmp     cs:?deviceFamily@?1??IsRunningOnHub@Tsf3OverrideUtil@@YA_NXZ@4KA, 6; ulong `Tsf3OverrideUtil::IsRunningOnHub(void)'::`2'::deviceFamily
0x1800ce544  jz      short loc_1800CE54A
0x1800ce546  xor     al, al
0x1800ce548  jmp     short loc_1800CE54C
0x1800ce54a  mov     al, bl
0x1800ce54c  cmp     cs:hBcp47LangsDll, 0
0x1800ce554  jnz     loc_1800CE649
0x1800ce55a  test    al, al
0x1800ce55c  jz      loc_1800CE68F
0x1800ce562  xor     r8d, r8d; dwFlags
0x1800ce565  lea     rcx, aBcp47langsDll_0; "Bcp47Langs.dll"
0x1800ce56c  xor     edx, edx; hFile
0x1800ce56e  call    cs:__imp_LoadLibraryExW
0x1800ce574  mov     cs:hBcp47LangsDll, rax
0x1800ce57b  test    rax, rax
0x1800ce57e  jz      loc_1800CE68F
0x1800ce584  lea     rdx, aBcp47fromhkl; "Bcp47FromHkl"
0x1800ce58b  mov     rcx, rax; hModule
0x1800ce58e  call    cs:__imp_GetProcAddress
0x1800ce594  mov     rcx, cs:hBcp47LangsDll; hModule
0x1800ce59b  lea     rdx, aBcp47bufferfro; "Bcp47BufferFromLcid"
0x1800ce5a2  mov     cs:pfnBcp47FromHkl, rax
0x1800ce5a9  call    cs:__imp_GetProcAddress
0x1800ce5af  mov     rcx, cs:hBcp47LangsDll; hModule
0x1800ce5b6  lea     rdx, aAppenduserlang; "AppendUserLanguages"
0x1800ce5bd  mov     cs:pfnBcp47BufferFromLcid, rax
0x1800ce5c4  call    cs:__imp_GetProcAddress
0x1800ce5ca  mov     rcx, cs:hBcp47LangsDll; hModule
0x1800ce5d1  lea     rdx, aAppenduserlang_0; "AppendUserLanguageInputMethods"
0x1800ce5d8  mov     cs:pfnAppendUserLanguages, rax
0x1800ce5df  call    cs:__imp_GetProcAddress
0x1800ce5e5  mov     rcx, cs:hBcp47LangsDll; hModule
0x1800ce5ec  lea     rdx, aRemoveuserlang; "RemoveUserLanguageInputMethods"
0x1800ce5f3  mov     cs:pfnAppendUserLanguageInputMethods, rax
0x1800ce5fa  call    cs:__imp_GetProcAddress
0x1800ce600  mov     rcx, cs:hBcp47LangsDll; hModule
0x1800ce607  lea     rdx, aGetuserlanguag; "GetUserLanguageInputMethods"
0x1800ce60e  mov     cs:pfnRemoveUserLanguageInputMethods, rax
0x1800ce615  call    cs:__imp_GetProcAddress
0x1800ce61b  mov     rcx, cs:hBcp47LangsDll; hModule
0x1800ce622  lea     rdx, aSetuserlanguag; "SetUserLanguageInputMethods"
0x1800ce629  mov     cs:pfnGetUserLanguageInputMethods, rax
0x1800ce630  call    cs:__imp_GetProcAddress
0x1800ce636  mov     cs:pfnSetUserLanguageInputMethods, rax
0x1800ce63d  mov     rax, cs:hBcp47LangsDll
0x1800ce644  test    rax, rax
0x1800ce647  jz      short loc_1800CE68F
0x1800ce649  cmp     cs:pfnBcp47FromHkl, 0
0x1800ce651  jz      short loc_1800CE68F
0x1800ce653  cmp     cs:pfnBcp47BufferFromLcid, 0
0x1800ce65b  jz      short loc_1800CE68F
0x1800ce65d  cmp     cs:pfnAppendUserLanguages, 0
0x1800ce665  jz      short loc_1800CE68F
0x1800ce667  cmp     cs:pfnAppendUserLanguageInputMethods, 0
0x1800ce66f  jz      short loc_1800CE68F
0x1800ce671  cmp     cs:pfnRemoveUserLanguageInputMethods, 0
0x1800ce679  jz      short loc_1800CE68F
0x1800ce67b  cmp     cs:pfnGetUserLanguageInputMethods, 0
0x1800ce683  jz      short loc_1800CE68F
0x1800ce685  cmp     cs:pfnSetUserLanguageInputMethods, 0
0x1800ce68d  jnz     short loc_1800CE691
0x1800ce68f  xor     bl, bl
0x1800ce691  mov     al, bl
0x1800ce693  add     rsp, 20h
0x1800ce697  pop     rbx
0x1800ce698  retn
```
