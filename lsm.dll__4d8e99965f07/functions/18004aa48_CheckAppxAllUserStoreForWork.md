# CheckAppxAllUserStoreForWork

- ea: `0x18004aa48`
- end: `0x18004ab44`
- name: `CheckAppxAllUserStoreForWork`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18000b3d0`

## callees

- `0x18004aa48`
- `0x180073268`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004ab2d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18004ab2d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004aaa0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004aafd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004aaa0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004aafd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004aa64`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004aa64`

## string_xrefs

- `0x18004aa55`: `AppxDeploymentClient.dll`
- `0x18004aad5`: `clientcore\termsrv\newsvc\rdsappx\lsmplugin\rdsappxplugin.cpp`
- `0x18004aa96`: `ClientExistsAnyPackageToBeInstalledForUser`

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
0x18004aa48  push    rbx
0x18004aa4a  push    rsi
0x18004aa4b  push    rdi; int
0x18004aa4c  sub     rsp, 20h
0x18004aa50  mov     rsi, rcx
0x18004aa53  xor     edx, edx; hFile
0x18004aa55  lea     rcx, aAppxdeployment; "AppxDeploymentClient.dll"
0x18004aa5c  mov     r8d, 800h; dwFlags
0x18004aa62  xor     ebx, ebx
0x18004aa64  call    cs:__imp_LoadLibraryExW
0x18004aa6b  nop     dword ptr [rax+rax+00h]
0x18004aa70  mov     rdi, rax
0x18004aa73  test    rax, rax
0x18004aa76  jz      loc_18004AB39
0x18004aa7c  mov     rax, cs:?pfn_GetProfileType@@3P6AHPEAK@ZEA; int (*pfn_GetProfileType)(ulong *)
0x18004aa83  mov     [rsp+38h+arg_8], ebx
0x18004aa87  test    rax, rax
0x18004aa8a  jz      short loc_18004AA96
0x18004aa8c  lea     rcx, [rsp+38h+arg_8]
0x18004aa91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aa96  lea     rdx, aClientexistsan; "ClientExistsAnyPackageToBeInstalledForU"...
0x18004aa9d  mov     rcx, rdi; hModule
0x18004aaa0  call    cs:__imp_GetProcAddress
0x18004aaa7  nop     dword ptr [rax+rax+00h]
0x18004aaac  mov     [rsp+38h+arg_10], ebx
0x18004aab0  test    rax, rax
0x18004aab3  jz      short loc_18004AAF3
0x18004aab5  test    byte ptr [rsp+38h+arg_8], 5
0x18004aaba  lea     r8, [rsp+38h+arg_10]
0x18004aabf  mov     edx, ebx
0x18004aac1  mov     rcx, rsi
0x18004aac4  setnz   dl
0x18004aac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aacc  test    eax, eax
0x18004aace  jns     short loc_18004AAEB
0x18004aad0  mov     rcx, [rsp+38h]; this
0x18004aad5  lea     r8, aClientcoreTerm_4; "clientcore\\termsrv\\newsvc\\rdsappx\\l"...
0x18004aadc  mov     r9d, eax; char *
0x18004aadf  mov     edx, 2Fh ; '/'; void *
0x18004aae4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004aae9  jmp     short loc_18004AAF3
0x18004aaeb  mov     ebx, [rsp+38h+arg_10]
0x18004aaef  test    ebx, ebx
0x18004aaf1  jnz     short loc_18004AB2A
0x18004aaf3  lea     rdx, aExistpackagesp; "ExistPackagesPendingDeferredRemovalForU"...
0x18004aafa  mov     rcx, rdi; hModule
0x18004aafd  call    cs:__imp_GetProcAddress
0x18004ab04  nop     dword ptr [rax+rax+00h]
0x18004ab09  test    rax, rax
0x18004ab0c  jz      short loc_18004AB2A
0x18004ab0e  lea     rdx, [rsp+38h+arg_18]
0x18004ab13  mov     [rsp+38h+arg_18], 0
0x18004ab1b  mov     rcx, rsi
0x18004ab1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ab23  test    eax, eax
0x18004ab25  cmovns  ebx, [rsp+38h+arg_18]
0x18004ab2a  mov     rcx, rdi; hLibModule
0x18004ab2d  call    cs:__imp_FreeLibrary
0x18004ab34  nop     dword ptr [rax+rax+00h]
0x18004ab39  mov     eax, ebx
0x18004ab3b  add     rsp, 20h
0x18004ab3f  pop     rdi
0x18004ab40  pop     rsi
0x18004ab41  pop     rbx
0x18004ab42  retn
```
