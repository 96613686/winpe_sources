# StackProvider::Load(TargetInfo *)

- ea: `0x1800e846c`
- end: `0x1800e86a0`
- name: `?Load@StackProvider@@QEAAJPEAVTargetInfo@@@Z`
- size: `564`
- prototype: `__int64 __fastcall(StackProvider *__hidden this, struct TargetInfo *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800a1590`

## callees

- `0x1800793cc`
- `0x18008b234`
- `0x1800954c4`
- `0x1800e846c`
- `0x1800e8b30`
- `0x1800f0f40`
- `0x1802424c0`
- `0x180299234`
- `0x18038605c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800e855f`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800e855f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800e85df`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800e85fa`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800e8615`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800e8630`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800e85df`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800e85fa`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800e8615`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800e8630`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e8578`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e858f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e8578`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e858f`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x1800e8544`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x1800e8544`

## string_xrefs

- `0x1800e85c7`: `The call to LoadLibrary(%s) failed, %s\n    "%s"\nPlease check your debugger configuration and/or network access.\n`
- `0x1800e8513`: `Unable to get extension search path, %s\n`
- `0x1800e85d8`: `BeginThreadStackReconstruction`
- `0x1800e8667`: `Stack provider %s.dll does not export all the necessary interfaces\n`
- `0x1800e8625`: `EndThreadStackReconstruction`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StackProvider::Load(StackProvider *this, struct TargetInfo *a2)
{
  __int64 v3; // rcx
  int v5; // eax
  unsigned __int16 *v6; // rax
  HMODULE v7; // rcx
  int *v8; // r8
  unsigned __int16 **v9; // r9
  unsigned int v10; // edi
  signed int LastError; // eax
  const unsigned __int16 *v12; // rbx
  unsigned __int16 *v13; // rax
  FARPROC ProcAddress; // rax
  LPCWSTR lpPath[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v16; // [rsp+40h] [rbp-C0h]
  int v17; // [rsp+44h] [rbp-BCh]
  __int64 v18; // [rsp+48h] [rbp-B8h]
  WCHAR Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF

  v18 = -2;
  FeatureUsageTracker::FeatureUsed(L"StackProvider", L"Load", 1u);
  Buffer[0] = 0;
  if ( *((_QWORD *)this + 5) )
    return 0;
  if ( !StackProvider::s_StackDumpProvidersEnabled )
    ErrOut(L"Stream present, but stack provider is not enabled, \n");
  *((_QWORD *)this + 4) = 0;
  lpPath[0] = 0;
  lpPath[1] = 0;
  v16 = 256;
  v17 = 64;
  v5 = BuildDefaultExtensionSearchPath(v3, lpPath);
  if ( v5 )
  {
    v6 = FormatStatusCode(v5);
    ErrOut(L"Unable to get extension search path, %s\n", v6);
  }
  if ( SearchPathW(lpPath[0], *((LPCWSTR *)this + 6), L".dll", 0x104u, Buffer, 0) )
    *((_QWORD *)this + 5) = LoadLibraryExW(Buffer, 0, 8u);
  v7 = (HMODULE)*((_QWORD *)this + 5);
  if ( v7 )
  {
    *((_QWORD *)this + 1) = GetProcAddress(v7, "BeginThreadStackReconstruction");
    *((_QWORD *)this + 2) = GetProcAddress(*((HMODULE *)this + 5), "ReconstructStack");
    *((_QWORD *)this + 3) = GetProcAddress(*((HMODULE *)this + 5), "FreeStackSymFrames");
    ProcAddress = GetProcAddress(*((HMODULE *)this + 5), "EndThreadStackReconstruction");
    *((_QWORD *)this + 4) = ProcAddress;
    if ( *((_QWORD *)this + 1) && *((_QWORD *)this + 2) && *((_QWORD *)this + 3) && ProcAddress )
    {
      v10 = 0;
    }
    else
    {
      StackProvider::Unload(this);
      ErrOut(L"Stack provider %s.dll does not export all the necessary interfaces\n", *((_QWORD *)this + 6));
      v10 = -2147467259;
    }
  }
  else
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v10 = -2147467259;
    }
    v12 = FormatAnyStatus(v10, 0, v8, v9);
    v13 = FormatStatusCode(v10);
    ErrOut(
      L"The call to LoadLibrary(%s) failed, %s\n"
       "    \"%s\"\n"
       "Please check your debugger configuration and/or network access.\n",
      *((_QWORD *)this + 6),
      v13,
      v12);
  }
  DbsDynamicBuffer::Delete((DbsDynamicBuffer *)lpPath);
  return v10;
}

```

## disassembly

```asm
0x1800e846c  push    rbp
0x1800e846e  push    rbx
0x1800e846f  push    rsi
0x1800e8470  push    rdi
0x1800e8471  lea     rbp, [rsp-178h]
0x1800e8479  sub     rsp, 278h
0x1800e8480  mov     [rsp+290h+var_248], 0FFFFFFFFFFFFFFFEh
0x1800e8489  mov     rax, cs:__security_cookie
0x1800e8490  xor     rax, rsp
0x1800e8493  mov     [rbp+190h+var_30], rax
0x1800e849a  mov     rsi, rcx
0x1800e849d  mov     r8d, 1; unsigned int
0x1800e84a3  lea     rdx, aLoad; "Load"
0x1800e84aa  lea     rcx, aStackprovider_0; "StackProvider"
0x1800e84b1  call    ?FeatureUsed@FeatureUsageTracker@@SAXQEBG0K@Z; FeatureUsageTracker::FeatureUsed(ushort const * const,ushort const * const,ulong)
0x1800e84b6  xor     ebx, ebx
0x1800e84b8  mov     [rsp+290h+Buffer], bx
0x1800e84bd  cmp     [rsi+28h], rbx
0x1800e84c1  jz      short loc_1800E84CA
0x1800e84c3  xor     eax, eax
0x1800e84c5  jmp     loc_1800E8684
0x1800e84ca  cmp     cs:?s_StackDumpProvidersEnabled@StackProvider@@0_NA, bl; bool StackProvider::s_StackDumpProvidersEnabled
0x1800e84d0  jnz     short loc_1800E84DE
0x1800e84d2  lea     rcx, aStreamPresentB; "Stream present, but stack provider is n"...
0x1800e84d9  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800e84de  mov     [rsi+20h], rbx
0x1800e84e2  mov     [rsp+290h+lpPath], rbx
0x1800e84e7  mov     [rsp+290h+var_258], rbx
0x1800e84ec  mov     [rsp+290h+var_250], 100h
0x1800e84f3  mov     [rsp+290h+var_24C], 40h ; '@'
0x1800e84fb  lea     rdx, [rsp+290h+lpPath]
0x1800e8500  call    ?BuildDefaultExtensionSearchPath@@YAJPEAVTargetInfo@@PEAV?$DbsDynamicString@G@@@Z; BuildDefaultExtensionSearchPath(TargetInfo *,DbsDynamicString<ushort> *)
0x1800e8505  test    eax, eax
0x1800e8507  jz      short loc_1800E851F
0x1800e8509  mov     ecx, eax; int
0x1800e850b  call    ?FormatStatusCode@@YAPEAGJ@Z; FormatStatusCode(long)
0x1800e8510  mov     rdx, rax
0x1800e8513  lea     rcx, aUnableToGetExt; "Unable to get extension search path, %s"...
0x1800e851a  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800e851f  mov     [rsp+290h+lpFilePart], rbx; lpFilePart
0x1800e8524  lea     rax, [rsp+290h+Buffer]
0x1800e8529  mov     [rsp+290h+lpBuffer], rax; lpBuffer
0x1800e852e  mov     r9d, 104h; nBufferLength
0x1800e8534  lea     r8, Extension; ".dll"
0x1800e853b  mov     rdx, [rsi+30h]; lpFileName
0x1800e853f  mov     rcx, [rsp+290h+lpPath]; lpPath
0x1800e8544  call    cs:__imp_SearchPathW
0x1800e854b  nop     dword ptr [rax+rax+00h]
0x1800e8550  test    eax, eax
0x1800e8552  jz      short loc_1800E856F
0x1800e8554  xor     edx, edx; hFile
0x1800e8556  lea     r8d, [rdx+8]; dwFlags
0x1800e855a  lea     rcx, [rsp+290h+Buffer]; lpLibFileName
0x1800e855f  call    cs:__imp_LoadLibraryExW
0x1800e8566  nop     dword ptr [rax+rax+00h]
0x1800e856b  mov     [rsi+28h], rax
0x1800e856f  mov     rcx, [rsi+28h]; hModule
0x1800e8573  test    rcx, rcx
0x1800e8576  jnz     short loc_1800E85D8
0x1800e8578  call    cs:__imp_GetLastError
0x1800e857f  nop     dword ptr [rax+rax+00h]
0x1800e8584  test    eax, eax
0x1800e8586  jnz     short loc_1800E858F
0x1800e8588  mov     edi, 80004005h
0x1800e858d  jmp     short loc_1800E85AA
0x1800e858f  call    cs:__imp_GetLastError
0x1800e8596  nop     dword ptr [rax+rax+00h]
0x1800e859b  mov     edi, eax
0x1800e859d  test    eax, eax
0x1800e859f  jle     short loc_1800E85AA
0x1800e85a1  movzx   edi, ax
0x1800e85a4  or      edi, 80070000h
0x1800e85aa  xor     edx, edx; Arguments
0x1800e85ac  mov     ecx, edi; dwMessageId
0x1800e85ae  call    ?FormatAnyStatus@@YAPEBGJPEAXPEAHPEAPEAG@Z; FormatAnyStatus(long,void *,int *,ushort * *)
0x1800e85b3  mov     rbx, rax
0x1800e85b6  mov     ecx, edi; int
0x1800e85b8  call    ?FormatStatusCode@@YAPEAGJ@Z; FormatStatusCode(long)
0x1800e85bd  mov     r9, rbx
0x1800e85c0  mov     r8, rax
0x1800e85c3  mov     rdx, [rsi+30h]
0x1800e85c7  lea     rcx, aTheCallToLoadl; "The call to LoadLibrary(%s) failed, %s"...
0x1800e85ce  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800e85d3  jmp     loc_1800E8678
0x1800e85d8  lea     rdx, aBeginthreadsta; "BeginThreadStackReconstruction"
0x1800e85df  call    cs:__imp_GetProcAddress
0x1800e85e6  nop     dword ptr [rax+rax+00h]
0x1800e85eb  mov     [rsi+8], rax
0x1800e85ef  lea     rdx, aReconstructsta_0; "ReconstructStack"
0x1800e85f6  mov     rcx, [rsi+28h]; hModule
0x1800e85fa  call    cs:__imp_GetProcAddress
0x1800e8601  nop     dword ptr [rax+rax+00h]
0x1800e8606  mov     [rsi+10h], rax
0x1800e860a  lea     rdx, aFreestacksymfr; "FreeStackSymFrames"
0x1800e8611  mov     rcx, [rsi+28h]; hModule
0x1800e8615  call    cs:__imp_GetProcAddress
0x1800e861c  nop     dword ptr [rax+rax+00h]
0x1800e8621  mov     [rsi+18h], rax
0x1800e8625  lea     rdx, aEndthreadstack; "EndThreadStackReconstruction"
0x1800e862c  mov     rcx, [rsi+28h]; hModule
0x1800e8630  call    cs:__imp_GetProcAddress
0x1800e8637  nop     dword ptr [rax+rax+00h]
0x1800e863c  mov     [rsi+20h], rax
0x1800e8640  cmp     [rsi+8], rbx
0x1800e8644  jz      short loc_1800E865B
0x1800e8646  cmp     [rsi+10h], rbx
0x1800e864a  jz      short loc_1800E865B
0x1800e864c  cmp     [rsi+18h], rbx
0x1800e8650  jz      short loc_1800E865B
0x1800e8652  test    rax, rax
0x1800e8655  jz      short loc_1800E865B
0x1800e8657  mov     edi, ebx
0x1800e8659  jmp     short loc_1800E8678
0x1800e865b  mov     rcx, rsi; this
0x1800e865e  call    ?Unload@StackProvider@@QEAAXXZ; StackProvider::Unload(void)
0x1800e8663  mov     rdx, [rsi+30h]
0x1800e8667  lea     rcx, aStackProviderS; "Stack provider %s.dll does not export a"...
0x1800e866e  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800e8673  mov     edi, 80004005h
0x1800e8678  lea     rcx, [rsp+290h+lpPath]; this
0x1800e867d  call    ?Delete@DbsDynamicBuffer@@QEAAXXZ; DbsDynamicBuffer::Delete(void)
0x1800e8682  mov     eax, edi
0x1800e8684  mov     rcx, [rbp+190h+var_30]
0x1800e868b  xor     rcx, rsp; StackCookie
0x1800e868e  call    __security_check_cookie
0x1800e8693  add     rsp, 278h
0x1800e869a  pop     rdi
0x1800e869b  pop     rsi
0x1800e869c  pop     rbx
0x1800e869d  pop     rbp
0x1800e869e  retn
```
