# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x1800e3bf0`
- end: `0x1800e3db2`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `450`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800e3db4`

## callees

- `0x1800e3bf0`
- `0x18019a840`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800e3d12`
- `KERNEL32!GetLastError` at `0x1800e3d12`
- `KERNEL32!SetLastError` at `0x1800e3cbb`
- `KERNEL32!SetLastError` at `0x1800e3cbb`
- `KERNEL32!CreateActCtxW` at `0x1800e3d01`
- `KERNEL32!CreateActCtxW` at `0x1800e3d01`
- `KERNEL32!ActivateActCtx` at `0x1800e3d42`
- `KERNEL32!ActivateActCtx` at `0x1800e3d42`
- `KERNEL32!GetModuleHandleExW` at `0x1800e3c82`
- `KERNEL32!GetModuleHandleExW` at `0x1800e3c82`
- `KERNEL32!GetModuleFileNameW` at `0x1800e3ca3`
- `KERNEL32!GetModuleFileNameW` at `0x1800e3ca3`
- `KERNEL32!FindActCtxSectionStringW` at `0x1800e3d6d`
- `KERNEL32!FindActCtxSectionStringW` at `0x1800e3d6d`
- `KERNEL32!DeactivateActCtx` at `0x1800e3d8c`
- `KERNEL32!DeactivateActCtx` at `0x1801a8283`
- `KERNEL32!DeactivateActCtx` at `0x1800e3d8c`
- `KERNEL32!DeactivateActCtx` at `0x1801a8283`
- `KERNEL32!QueryActCtxW` at `0x1800e3c57`
- `KERNEL32!QueryActCtxW` at `0x1800e3c57`
- `KERNEL32!LoadLibraryW` at `0x1800e3d7e`
- `KERNEL32!LoadLibraryW` at `0x1800e3d7e`

## string_xrefs

- `0x1800e3d5e`: `Comctl32.dll`
- `0x1800e3d77`: `Comctl32.dll`

## pseudocode

```c
__int64 WinbaseIsolationAwarePrivatetRgzlnPgpgk()
{
  unsigned int v0; // ebx
  HANDLE ActCtxW; // rax
  DWORD ModuleFileNameW; // eax
  DWORD LastError; // eax
  ULONG_PTR Cookie; // [rsp+40h] [rbp-2B8h] BYREF
  HMODULE phModule; // [rsp+48h] [rbp-2B0h] BYREF
  HANDLE hActCtx[2]; // [rsp+50h] [rbp-2A8h] BYREF
  struct tagACTCTX_SECTION_KEYED_DATA pActCtx; // [rsp+60h] [rbp-298h] BYREF
  WCHAR Filename[264]; // [rsp+D0h] [rbp-228h] BYREF

  v0 = 0;
  Cookie = 0;
  if ( IsolationAwarePrivateT_SqbjaYRiRY || *(_QWORD *)&WinbaseIsolationAwarePrivateT_UnPgpgk != -1 )
    return 1;
  if ( QueryActCtxW(0x80000010, &WinbaseIsolationAwarePrivateT_UnPgpgk, 0, 1u, hActCtx, 0x10u, 0) )
  {
    ActCtxW = hActCtx[0];
    if ( hActCtx[0] )
      goto LABEL_13;
    if ( GetModuleHandleExW(6u, &WinbaseIsolationAwarePrivateT_UnPgpgk, &phModule) )
    {
      ModuleFileNameW = GetModuleFileNameW(phModule, Filename, 0x105u);
      if ( ModuleFileNameW )
      {
        if ( ModuleFileNameW >= 0x105 )
        {
          SetLastError(0x6Fu);
          return v0;
        }
        pActCtx.cbSize = 56;
        pActCtx.ulDataFormatVersion = 136;
        pActCtx.lpData = Filename;
        *(_QWORD *)&pActCtx.ulSectionGlobalDataLength = 3;
        *(_QWORD *)&pActCtx.ulSectionTotalLength = phModule;
        ActCtxW = CreateActCtxW((PCACTCTXW)&pActCtx);
        hActCtx[0] = ActCtxW;
        if ( ActCtxW != (HANDLE)-1LL )
          goto LABEL_13;
        LastError = GetLastError();
        if ( LastError - 1812 <= 3 || LastError - 2 <= 1 )
        {
          ActCtxW = 0;
          hActCtx[0] = 0;
LABEL_13:
          *(_QWORD *)&WinbaseIsolationAwarePrivateT_UnPgpgk = ActCtxW;
          if ( ActivateActCtx(ActCtxW, &Cookie) )
          {
            pActCtx.cbSize = 112;
            if ( FindActCtxSectionStringW(0, 0, 2u, L"Comctl32.dll", &pActCtx) )
              LoadLibraryW(L"Comctl32.dll");
            DeactivateActCtx(0, Cookie);
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
0x1800e3bf0  push    rbx
0x1800e3bf2  sub     rsp, 2F0h
0x1800e3bf9  mov     rax, cs:__security_cookie
0x1800e3c00  xor     rax, rsp
0x1800e3c03  mov     [rsp+2F8h+var_18], rax
0x1800e3c0b  xor     ebx, ebx
0x1800e3c0d  mov     [rsp+2F8h+Cookie], rbx
0x1800e3c12  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, ebx
0x1800e3c18  jnz     loc_1800E3D92
0x1800e3c1e  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x1800e3c26  jnz     loc_1800E3D92
0x1800e3c2c  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x1800e3c31  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x1800e3c3a  lea     rax, [rsp+2F8h+hActCtx]
0x1800e3c3f  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x1800e3c44  lea     r9d, [rbx+1]; ulInfoClass
0x1800e3c48  xor     r8d, r8d; pvSubInstance
0x1800e3c4b  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x1800e3c52  mov     ecx, 80000010h; dwFlags
0x1800e3c57  call    cs:__imp_QueryActCtxW
0x1800e3c5d  test    eax, eax
0x1800e3c5f  jz      loc_1800E3D97
0x1800e3c65  mov     rax, [rsp+2F8h+hActCtx]
0x1800e3c6a  test    rax, rax
0x1800e3c6d  jnz     loc_1800E3D33
0x1800e3c73  lea     r8, [rsp+2F8h+phModule]; phModule
0x1800e3c78  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x1800e3c7f  lea     ecx, [rbx+6]; dwFlags
0x1800e3c82  call    cs:__imp_GetModuleHandleExW
0x1800e3c88  test    eax, eax
0x1800e3c8a  jz      loc_1800E3D97
0x1800e3c90  mov     r8d, 105h; nSize
0x1800e3c96  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x1800e3c9e  mov     rcx, [rsp+2F8h+phModule]; hModule
0x1800e3ca3  call    cs:__imp_GetModuleFileNameW
0x1800e3ca9  test    eax, eax
0x1800e3cab  jz      loc_1800E3D97
0x1800e3cb1  cmp     eax, 105h
0x1800e3cb6  jb      short loc_1800E3CC6
0x1800e3cb8  lea     ecx, [rbx+6Fh]; dwErrCode
0x1800e3cbb  call    cs:__imp_SetLastError
0x1800e3cc1  jmp     loc_1800E3D97
0x1800e3cc6  mov     dword ptr [rsp+2F8h+pActCtx], 38h ; '8'
0x1800e3cce  mov     dword ptr [rsp+2F8h+pActCtx+4], 88h
0x1800e3cd6  lea     rax, [rsp+2F8h+Filename]
0x1800e3cde  mov     qword ptr [rsp+2F8h+pActCtx+8], rax
0x1800e3ce3  mov     qword ptr [rsp+2F8h+pActCtx+20h], 3
0x1800e3cef  mov     rax, [rsp+2F8h+phModule]
0x1800e3cf4  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x1800e3cfc  lea     rcx, [rsp+2F8h+pActCtx]; pActCtx
0x1800e3d01  call    cs:__imp_CreateActCtxW
0x1800e3d07  mov     [rsp+2F8h+hActCtx], rax
0x1800e3d0c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800e3d10  jnz     short loc_1800E3D33
0x1800e3d12  call    cs:__imp_GetLastError
0x1800e3d18  lea     ecx, [rax-714h]
0x1800e3d1e  cmp     ecx, 3
0x1800e3d21  jbe     short loc_1800E3D2B
0x1800e3d23  add     eax, 0FFFFFFFEh
0x1800e3d26  cmp     eax, 1
0x1800e3d29  ja      short loc_1800E3D97
0x1800e3d2b  mov     rax, rbx
0x1800e3d2e  mov     [rsp+2F8h+hActCtx], rbx
0x1800e3d33  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x1800e3d3a  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x1800e3d3f  mov     rcx, rax; hActCtx
0x1800e3d42  call    cs:__imp_ActivateActCtx
0x1800e3d48  test    eax, eax
0x1800e3d4a  jz      short loc_1800E3D92
0x1800e3d4c  mov     dword ptr [rsp+2F8h+pActCtx], 70h ; 'p'
0x1800e3d54  lea     rax, [rsp+2F8h+pActCtx]
0x1800e3d59  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x1800e3d5e  lea     r9, LibFileName; "Comctl32.dll"
0x1800e3d65  xor     edx, edx; lpExtensionGuid
0x1800e3d67  xor     ecx, ecx; dwFlags
0x1800e3d69  lea     r8d, [rdx+2]; ulSectionId
0x1800e3d6d  call    cs:__imp_FindActCtxSectionStringW
0x1800e3d73  test    eax, eax
0x1800e3d75  jz      short loc_1800E3D85
0x1800e3d77  lea     rcx, LibFileName; "Comctl32.dll"
0x1800e3d7e  call    cs:__imp_LoadLibraryW
0x1800e3d84  nop
0x1800e3d85  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x1800e3d8a  xor     ecx, ecx; dwFlags
0x1800e3d8c  call    cs:__imp_DeactivateActCtx
0x1800e3d92  mov     ebx, 1
0x1800e3d97  mov     eax, ebx
0x1800e3d99  mov     rcx, [rsp+2F8h+var_18]
0x1800e3da1  xor     rcx, rsp; StackCookie
0x1800e3da4  call    __security_check_cookie
0x1800e3da9  add     rsp, 2F0h
0x1800e3db0  pop     rbx
0x1800e3db1  retn
0x1801a8274  push    rbp
0x1801a8276  sub     rsp, 40h
0x1801a827a  mov     rbp, rdx
0x1801a827d  mov     rdx, [rbp+40h]; ulCookie
0x1801a8281  xor     ecx, ecx; dwFlags
0x1801a8283  call    cs:__imp_DeactivateActCtx
0x1801a8289  nop
0x1801a828a  add     rsp, 40h
0x1801a828e  pop     rbp
0x1801a828f  retn
```
