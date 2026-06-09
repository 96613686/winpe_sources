# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x18001cc38`
- end: `0x18001cdfa`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `450`
- prototype: `int __fastcall()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001cdfc`

## callees

- `0x18001cc38`
- `0x1802c4640`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001cd5a`
- `KERNEL32!GetLastError` at `0x18001cd5a`
- `KERNEL32!SetLastError` at `0x18001cd03`
- `KERNEL32!SetLastError` at `0x18001cd03`
- `KERNEL32!DeactivateActCtx` at `0x18001cdd4`
- `KERNEL32!DeactivateActCtx` at `0x1802c74b0`
- `KERNEL32!DeactivateActCtx` at `0x18001cdd4`
- `KERNEL32!DeactivateActCtx` at `0x1802c74b0`
- `KERNEL32!LoadLibraryW` at `0x18001cdc6`
- `KERNEL32!LoadLibraryW` at `0x18001cdc6`
- `KERNEL32!ActivateActCtx` at `0x18001cd8a`
- `KERNEL32!ActivateActCtx` at `0x18001cd8a`
- `KERNEL32!FindActCtxSectionStringW` at `0x18001cdb5`
- `KERNEL32!FindActCtxSectionStringW` at `0x18001cdb5`
- `KERNEL32!CreateActCtxW` at `0x18001cd49`
- `KERNEL32!CreateActCtxW` at `0x18001cd49`
- `KERNEL32!GetModuleFileNameW` at `0x18001cceb`
- `KERNEL32!GetModuleFileNameW` at `0x18001cceb`
- `KERNEL32!GetModuleHandleExW` at `0x18001ccca`
- `KERNEL32!GetModuleHandleExW` at `0x18001ccca`
- `KERNEL32!QueryActCtxW` at `0x18001cc9f`
- `KERNEL32!QueryActCtxW` at `0x18001cc9f`

## string_xrefs

- `0x18001cda6`: `Comctl32.dll`
- `0x18001cdbf`: `Comctl32.dll`

## pseudocode

```c
__int64 __fastcall WinbaseIsolationAwarePrivatetRgzlnPgpgk()
{
  unsigned int v0; // ebx
  void *hActCtx; // rax
  DWORD ModuleFileNameW; // eax
  DWORD LastError; // eax
  unsigned __int64 ulpCookie; // [rsp+40h] [rbp-2B8h] BYREF
  HINSTANCE__ *hmodSelf; // [rsp+48h] [rbp-2B0h] BYREF
  _ACTIVATION_CONTEXT_BASIC_INFORMATION actCtxBasicInfo; // [rsp+50h] [rbp-2A8h] BYREF
  tagACTCTX_SECTION_KEYED_DATA actCtxSectionKeyedData; // [rsp+60h] [rbp-298h] BYREF
  wchar_t rgchFullModulePath[264]; // [rsp+D0h] [rbp-228h] BYREF

  v0 = 0;
  ulpCookie = 0;
  if ( IsolationAwarePrivateT_SqbjaYRiRY || *(_QWORD *)&WinbaseIsolationAwarePrivateT_UnPgpgk != -1 )
    return 1;
  if ( QueryActCtxW(0x80000010, &WinbaseIsolationAwarePrivateT_UnPgpgk, 0, 1u, &actCtxBasicInfo, 0x10u, 0) )
  {
    hActCtx = actCtxBasicInfo.hActCtx;
    if ( actCtxBasicInfo.hActCtx )
      goto LABEL_13;
    if ( GetModuleHandleExW(6u, &WinbaseIsolationAwarePrivateT_UnPgpgk, &hmodSelf) )
    {
      ModuleFileNameW = GetModuleFileNameW(hmodSelf, rgchFullModulePath, 0x105u);
      if ( ModuleFileNameW )
      {
        if ( ModuleFileNameW >= 0x105 )
        {
          SetLastError(0x6Fu);
          return v0;
        }
        actCtxSectionKeyedData.cbSize = 56;
        actCtxSectionKeyedData.ulDataFormatVersion = 136;
        actCtxSectionKeyedData.lpData = rgchFullModulePath;
        *(_QWORD *)&actCtxSectionKeyedData.ulSectionGlobalDataLength = 3;
        *(_QWORD *)&actCtxSectionKeyedData.ulSectionTotalLength = hmodSelf;
        hActCtx = CreateActCtxW((PCACTCTXW)&actCtxSectionKeyedData);
        actCtxBasicInfo.hActCtx = hActCtx;
        if ( hActCtx != (void *)-1LL )
          goto LABEL_13;
        LastError = GetLastError();
        if ( LastError - 1812 <= 3 || LastError - 2 <= 1 )
        {
          hActCtx = 0;
          actCtxBasicInfo.hActCtx = 0;
LABEL_13:
          *(_QWORD *)&WinbaseIsolationAwarePrivateT_UnPgpgk = hActCtx;
          if ( ActivateActCtx(hActCtx, &ulpCookie) )
          {
            actCtxSectionKeyedData.cbSize = 112;
            if ( FindActCtxSectionStringW(0, 0, 2u, L"Comctl32.dll", &actCtxSectionKeyedData) )
              LoadLibraryW(L"Comctl32.dll");
            DeactivateActCtx(0, ulpCookie);
          }
          return 1;
        }
      }
    }
  }
  return v0;
}

```

## disassembly

```asm
0x18001cc38  push    rbx
0x18001cc3a  sub     rsp, 2F0h
0x18001cc41  mov     rax, cs:__security_cookie
0x18001cc48  xor     rax, rsp
0x18001cc4b  mov     [rsp+2F8h+var_18], rax
0x18001cc53  xor     ebx, ebx
0x18001cc55  mov     [rsp+2F8h+ulpCookie], rbx
0x18001cc5a  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, ebx
0x18001cc60  jnz     loc_18001CDDA
0x18001cc66  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x18001cc6e  jnz     loc_18001CDDA
0x18001cc74  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x18001cc79  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x18001cc82  lea     rax, [rsp+2F8h+actCtxBasicInfo]
0x18001cc87  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x18001cc8c  lea     r9d, [rbx+1]; ulInfoClass
0x18001cc90  xor     r8d, r8d; pvSubInstance
0x18001cc93  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x18001cc9a  mov     ecx, 80000010h; dwFlags
0x18001cc9f  call    cs:__imp_QueryActCtxW
0x18001cca5  test    eax, eax
0x18001cca7  jz      $Exit
0x18001ccad  mov     rax, [rsp+2F8h+actCtxBasicInfo.hActCtx]
0x18001ccb2  test    rax, rax
0x18001ccb5  jnz     loc_18001CD7B
0x18001ccbb  lea     r8, [rsp+2F8h+hmodSelf]; phModule
0x18001ccc0  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x18001ccc7  lea     ecx, [rbx+6]; dwFlags
0x18001ccca  call    cs:__imp_GetModuleHandleExW
0x18001ccd0  test    eax, eax
0x18001ccd2  jz      $Exit
0x18001ccd8  mov     r8d, 105h; nSize
0x18001ccde  lea     rdx, [rsp+2F8h+rgchFullModulePath]; lpFilename
0x18001cce6  mov     rcx, [rsp+2F8h+hmodSelf]; hModule
0x18001cceb  call    cs:__imp_GetModuleFileNameW
0x18001ccf1  test    eax, eax
0x18001ccf3  jz      $Exit
0x18001ccf9  cmp     eax, 105h
0x18001ccfe  jb      short loc_18001CD0E
0x18001cd00  lea     ecx, [rbx+6Fh]; dwErrCode
0x18001cd03  call    cs:__imp_SetLastError
0x18001cd09  jmp     $Exit
0x18001cd0e  mov     [rsp+2F8h+actCtxSectionKeyedData.cbSize], 38h ; '8'
0x18001cd16  mov     [rsp+2F8h+actCtxSectionKeyedData.ulDataFormatVersion], 88h
0x18001cd1e  lea     rax, [rsp+2F8h+rgchFullModulePath]
0x18001cd26  mov     [rsp+2F8h+actCtxSectionKeyedData.lpData], rax
0x18001cd2b  mov     qword ptr [rsp+2F8h+actCtxSectionKeyedData.ulSectionGlobalDataLength], 3
0x18001cd37  mov     rax, [rsp+2F8h+hmodSelf]
0x18001cd3c  mov     qword ptr [rsp+2F8h+actCtxSectionKeyedData.ulSectionTotalLength], rax
0x18001cd44  lea     rcx, [rsp+2F8h+actCtxSectionKeyedData]; pActCtx
0x18001cd49  call    cs:__imp_CreateActCtxW
0x18001cd4f  mov     [rsp+2F8h+actCtxBasicInfo.hActCtx], rax
0x18001cd54  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001cd58  jnz     short loc_18001CD7B
0x18001cd5a  call    cs:__imp_GetLastError
0x18001cd60  lea     ecx, [rax-714h]
0x18001cd66  cmp     ecx, 3
0x18001cd69  jbe     short loc_18001CD73
0x18001cd6b  add     eax, 0FFFFFFFEh
0x18001cd6e  cmp     eax, 1
0x18001cd71  ja      short $Exit
0x18001cd73  mov     rax, rbx
0x18001cd76  mov     [rsp+2F8h+actCtxBasicInfo.hActCtx], rbx
0x18001cd7b  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x18001cd82  lea     rdx, [rsp+2F8h+ulpCookie]; lpCookie
0x18001cd87  mov     rcx, rax; hActCtx
0x18001cd8a  call    cs:__imp_ActivateActCtx
0x18001cd90  test    eax, eax
0x18001cd92  jz      short loc_18001CDDA
0x18001cd94  mov     [rsp+2F8h+actCtxSectionKeyedData.cbSize], 70h ; 'p'
0x18001cd9c  lea     rax, [rsp+2F8h+actCtxSectionKeyedData]
0x18001cda1  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x18001cda6  lea     r9, aComctl32Dll; "Comctl32.dll"
0x18001cdad  xor     edx, edx; lpExtensionGuid
0x18001cdaf  xor     ecx, ecx; dwFlags
0x18001cdb1  lea     r8d, [rdx+2]; ulSectionId
0x18001cdb5  call    cs:__imp_FindActCtxSectionStringW
0x18001cdbb  test    eax, eax
0x18001cdbd  jz      short $LN26_0
0x18001cdbf  lea     rcx, aComctl32Dll; "Comctl32.dll"
0x18001cdc6  call    cs:__imp_LoadLibraryW
0x18001cdcc  nop
0x18001cdcd  mov     rdx, [rsp+2F8h+ulpCookie]; ulCookie
0x18001cdd2  xor     ecx, ecx; dwFlags
0x18001cdd4  call    cs:__imp_DeactivateActCtx
0x18001cdda  mov     ebx, 1
0x18001cddf  mov     eax, ebx
0x18001cde1  mov     rcx, [rsp+2F8h+var_18]
0x18001cde9  xor     rcx, rsp; StackCookie
0x18001cdec  call    __security_check_cookie
0x18001cdf1  add     rsp, 2F0h
0x18001cdf8  pop     rbx
0x18001cdf9  retn
0x1802c74a1  push    rbp
0x1802c74a3  sub     rsp, 40h
0x1802c74a7  mov     rbp, rdx
0x1802c74aa  mov     rdx, [rbp+40h]; ulCookie
0x1802c74ae  xor     ecx, ecx; dwFlags
0x1802c74b0  call    cs:__imp_DeactivateActCtx
0x1802c74b6  nop
0x1802c74b7  add     rsp, 40h
0x1802c74bb  pop     rbp
0x1802c74bc  retn
```
