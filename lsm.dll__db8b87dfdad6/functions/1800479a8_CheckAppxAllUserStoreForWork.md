# CheckAppxAllUserStoreForWork

- ea: `0x1800479a8`
- end: `0x180047a8b`
- name: `CheckAppxAllUserStoreForWork`
- size: `227`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180017520`

## callees

- `0x1800479a8`
- `0x18006f284`
- `0x180097010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180047a7b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180047a7b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800479fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180047a51`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800479fa`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180047a51`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800479c4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800479c4`

## string_xrefs

- `0x1800479b5`: `AppxDeploymentClient.dll`
- `0x1800479f0`: `ClientExistsAnyPackageToBeInstalledForUser`
- `0x180047a29`: `clientcore\termsrv\newsvc\rdsappx\lsmplugin\rdsappxplugin.cpp`

## pseudocode

```c
__int64 __fastcall CheckAppxAllUserStoreForWork(__int64 a1)
{
  unsigned int v2; // ebx
  HMODULE Library; // rdi
  FARPROC ProcAddress; // rax
  int v5; // eax
  FARPROC v6; // rax
  int v8; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned int v10; // [rsp+48h] [rbp+10h] BYREF
  unsigned int v11; // [rsp+50h] [rbp+18h] BYREF
  unsigned int v12; // [rsp+58h] [rbp+20h] BYREF

  v2 = 0;
  Library = LoadLibraryExW(L"AppxDeploymentClient.dll", 0, 0x800u);
  if ( Library )
  {
    v10 = 0;
    if ( pfn_GetProfileType )
      pfn_GetProfileType(&v10);
    ProcAddress = GetProcAddress(Library, "ClientExistsAnyPackageToBeInstalledForUser");
    v11 = 0;
    if ( ProcAddress )
    {
      v5 = ((__int64 (__fastcall *)(__int64, bool, unsigned int *))ProcAddress)(a1, (v10 & 5) != 0, &v11);
      if ( v5 >= 0 )
      {
        v2 = v11;
        if ( v11 )
        {
LABEL_11:
          FreeLibrary(Library);
          return v2;
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2F,
          (unsigned int)"clientcore\\termsrv\\newsvc\\rdsappx\\lsmplugin\\rdsappxplugin.cpp",
          (const char *)(unsigned int)v5,
          v8);
      }
    }
    v6 = GetProcAddress(Library, "ExistPackagesPendingDeferredRemovalForUser");
    if ( v6 )
    {
      v12 = 0;
      if ( ((int (__fastcall *)(__int64, unsigned int *))v6)(a1, &v12) >= 0 )
        v2 = v12;
    }
    goto LABEL_11;
  }
  return v2;
}

```

## disassembly

```asm
0x1800479a8  push    rbx
0x1800479aa  push    rsi
0x1800479ab  push    rdi; int
0x1800479ac  sub     rsp, 20h
0x1800479b0  mov     rsi, rcx
0x1800479b3  xor     edx, edx; hFile
0x1800479b5  lea     rcx, aAppxdeployment; "AppxDeploymentClient.dll"
0x1800479bc  mov     r8d, 800h; dwFlags
0x1800479c2  xor     ebx, ebx
0x1800479c4  call    cs:__imp_LoadLibraryExW
0x1800479ca  mov     rdi, rax
0x1800479cd  test    rax, rax
0x1800479d0  jz      loc_180047A81
0x1800479d6  mov     rax, cs:?pfn_GetProfileType@@3P6AHPEAK@ZEA; int (*pfn_GetProfileType)(ulong *)
0x1800479dd  mov     [rsp+38h+arg_8], ebx
0x1800479e1  test    rax, rax
0x1800479e4  jz      short loc_1800479F0
0x1800479e6  lea     rcx, [rsp+38h+arg_8]
0x1800479eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800479f0  lea     rdx, aClientexistsan; "ClientExistsAnyPackageToBeInstalledForU"...
0x1800479f7  mov     rcx, rdi; hModule
0x1800479fa  call    cs:__imp_GetProcAddress
0x180047a00  mov     [rsp+38h+arg_10], ebx
0x180047a04  test    rax, rax
0x180047a07  jz      short loc_180047A47
0x180047a09  test    byte ptr [rsp+38h+arg_8], 5
0x180047a0e  lea     r8, [rsp+38h+arg_10]
0x180047a13  mov     edx, ebx
0x180047a15  mov     rcx, rsi
0x180047a18  setnz   dl
0x180047a1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047a20  test    eax, eax
0x180047a22  jns     short loc_180047A3F
0x180047a24  mov     rcx, [rsp+38h]; this
0x180047a29  lea     r8, aClientcoreTerm_4; "clientcore\\termsrv\\newsvc\\rdsappx\\l"...
0x180047a30  mov     r9d, eax; char *
0x180047a33  mov     edx, 2Fh ; '/'; void *
0x180047a38  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180047a3d  jmp     short loc_180047A47
0x180047a3f  mov     ebx, [rsp+38h+arg_10]
0x180047a43  test    ebx, ebx
0x180047a45  jnz     short loc_180047A78
0x180047a47  lea     rdx, aExistpackagesp; "ExistPackagesPendingDeferredRemovalForU"...
0x180047a4e  mov     rcx, rdi; hModule
0x180047a51  call    cs:__imp_GetProcAddress
0x180047a57  test    rax, rax
0x180047a5a  jz      short loc_180047A78
0x180047a5c  lea     rdx, [rsp+38h+arg_18]
0x180047a61  mov     [rsp+38h+arg_18], 0
0x180047a69  mov     rcx, rsi
0x180047a6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047a71  test    eax, eax
0x180047a73  cmovns  ebx, [rsp+38h+arg_18]
0x180047a78  mov     rcx, rdi; hLibModule
0x180047a7b  call    cs:__imp_FreeLibrary
0x180047a81  mov     eax, ebx
0x180047a83  add     rsp, 20h
0x180047a87  pop     rdi
0x180047a88  pop     rsi
0x180047a89  pop     rbx
0x180047a8a  retn
```
