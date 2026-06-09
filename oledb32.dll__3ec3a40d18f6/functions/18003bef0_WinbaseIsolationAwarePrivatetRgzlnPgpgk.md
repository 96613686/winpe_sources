# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x18003bef0`
- end: `0x18003c0ef`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003be64`

## callees

- `0x18003bef0`
- `0x18007e6ca`
- `0x18007e700`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x18003bfd2`
- `KERNEL32!GetModuleFileNameW` at `0x18003bfd2`
- `KERNEL32!GetLastError` at `0x18003c041`
- `KERNEL32!GetLastError` at `0x18003c041`
- `KERNEL32!SetLastError` at `0x18003bfea`
- `KERNEL32!SetLastError` at `0x18003bfea`
- `KERNEL32!DeactivateActCtx` at `0x18003c0c9`
- `KERNEL32!DeactivateActCtx` at `0x180081515`
- `KERNEL32!DeactivateActCtx` at `0x18003c0c9`
- `KERNEL32!DeactivateActCtx` at `0x180081515`
- `KERNEL32!LoadLibraryW` at `0x18003c0bb`
- `KERNEL32!LoadLibraryW` at `0x18003c0bb`
- `KERNEL32!ActivateActCtx` at `0x18003c06f`
- `KERNEL32!ActivateActCtx` at `0x18003c06f`
- `KERNEL32!FindActCtxSectionStringW` at `0x18003c0aa`
- `KERNEL32!FindActCtxSectionStringW` at `0x18003c0aa`
- `KERNEL32!CreateActCtxW` at `0x18003c030`
- `KERNEL32!CreateActCtxW` at `0x18003c030`
- `KERNEL32!GetModuleHandleExW` at `0x18003bfb1`
- `KERNEL32!GetModuleHandleExW` at `0x18003bfb1`
- `KERNEL32!QueryActCtxW` at `0x18003bf64`
- `KERNEL32!QueryActCtxW` at `0x18003bf64`

## string_xrefs

- `0x18003c09b`: `Comctl32.dll`
- `0x18003c0b4`: `Comctl32.dll`

## pseudocode

```c
__int64 WinbaseIsolationAwarePrivatetRgzlnPgpgk()
{
  unsigned int v0; // ebx
  HANDLE ActCtxW; // rax
  DWORD ModuleFileNameW; // eax
  DWORD LastError; // eax
  HMODULE phModule; // [rsp+40h] [rbp-2B8h] BYREF
  ULONG_PTR Cookie; // [rsp+48h] [rbp-2B0h] BYREF
  HANDLE hActCtx[2]; // [rsp+50h] [rbp-2A8h] BYREF
  struct tagACTCTX_SECTION_KEYED_DATA pActCtx; // [rsp+60h] [rbp-298h] BYREF
  WCHAR Filename[264]; // [rsp+D0h] [rbp-228h] BYREF

  *(_OWORD *)hActCtx = 0;
  Cookie = 0;
  if ( IsolationAwarePrivateT_SqbjaYRiRY || WinbaseIsolationAwarePrivateT_UnPgpgk != (HANDLE)-1LL )
    return 1;
  v0 = 0;
  if ( QueryActCtxW(0x80000010, &WinbaseIsolationAwarePrivateT_UnPgpgk, 0, 1u, hActCtx, 0x10u, 0) )
  {
    ActCtxW = hActCtx[0];
    if ( hActCtx[0] )
      goto LABEL_13;
    memset(&pActCtx, 0, 56);
    phModule = 0;
    if ( GetModuleHandleExW(6u, (LPCWSTR)&WinbaseIsolationAwarePrivateT_UnPgpgk, &phModule) )
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
        if ( LastError - 2 <= 1 || LastError - 1812 <= 3 )
        {
          ActCtxW = 0;
          hActCtx[0] = 0;
LABEL_13:
          WinbaseIsolationAwarePrivateT_UnPgpgk = ActCtxW;
          if ( ActivateActCtx(ActCtxW, &Cookie) )
          {
            memset_0(&pActCtx, 0, sizeof(pActCtx));
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
0x18003bef0  push    rbx
0x18003bef2  sub     rsp, 2F0h
0x18003bef9  mov     rax, cs:__security_cookie
0x18003bf00  xor     rax, rsp
0x18003bf03  mov     [rsp+2F8h+var_18], rax
0x18003bf0b  xorps   xmm0, xmm0
0x18003bf0e  movups  xmmword ptr [rsp+2F8h+hActCtx], xmm0
0x18003bf13  mov     [rsp+2F8h+Cookie], 0
0x18003bf1c  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18003bf23  jnz     loc_18003C0CF
0x18003bf29  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x18003bf31  jnz     loc_18003C0CF
0x18003bf37  xor     ebx, ebx
0x18003bf39  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x18003bf3e  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x18003bf47  lea     rax, [rsp+2F8h+hActCtx]
0x18003bf4c  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x18003bf51  lea     r9d, [rbx+1]; ulInfoClass
0x18003bf55  xor     r8d, r8d; pvSubInstance
0x18003bf58  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x18003bf5f  mov     ecx, 80000010h; dwFlags
0x18003bf64  call    cs:__imp_QueryActCtxW
0x18003bf6a  test    eax, eax
0x18003bf6c  jz      loc_18003C0D4
0x18003bf72  mov     rax, [rsp+2F8h+hActCtx]
0x18003bf77  test    rax, rax
0x18003bf7a  jnz     loc_18003C060
0x18003bf80  xorps   xmm0, xmm0
0x18003bf83  movups  xmmword ptr [rsp+2F8h+pActCtx], xmm0
0x18003bf88  movups  xmmword ptr [rsp+2F8h+pActCtx+10h], xmm0
0x18003bf8d  movups  xmmword ptr [rsp+2F8h+pActCtx+20h], xmm0
0x18003bf95  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x18003bf9d  mov     [rsp+2F8h+phModule], rax
0x18003bfa2  lea     r8, [rsp+2F8h+phModule]; phModule
0x18003bfa7  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x18003bfae  lea     ecx, [rbx+6]; dwFlags
0x18003bfb1  call    cs:__imp_GetModuleHandleExW
0x18003bfb7  test    eax, eax
0x18003bfb9  jz      loc_18003C0D4
0x18003bfbf  mov     r8d, 105h; nSize
0x18003bfc5  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x18003bfcd  mov     rcx, [rsp+2F8h+phModule]; hModule
0x18003bfd2  call    cs:__imp_GetModuleFileNameW
0x18003bfd8  test    eax, eax
0x18003bfda  jz      loc_18003C0D4
0x18003bfe0  cmp     eax, 105h
0x18003bfe5  jb      short loc_18003BFF5
0x18003bfe7  lea     ecx, [rbx+6Fh]; dwErrCode
0x18003bfea  call    cs:__imp_SetLastError
0x18003bff0  jmp     loc_18003C0D4
0x18003bff5  mov     dword ptr [rsp+2F8h+pActCtx], 38h ; '8'
0x18003bffd  mov     dword ptr [rsp+2F8h+pActCtx+4], 88h
0x18003c005  lea     rax, [rsp+2F8h+Filename]
0x18003c00d  mov     qword ptr [rsp+2F8h+pActCtx+8], rax
0x18003c012  mov     qword ptr [rsp+2F8h+pActCtx+20h], 3
0x18003c01e  mov     rax, [rsp+2F8h+phModule]
0x18003c023  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x18003c02b  lea     rcx, [rsp+2F8h+pActCtx]; pActCtx
0x18003c030  call    cs:__imp_CreateActCtxW
0x18003c036  mov     [rsp+2F8h+hActCtx], rax
0x18003c03b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003c03f  jnz     short loc_18003C060
0x18003c041  call    cs:__imp_GetLastError
0x18003c047  lea     ecx, [rax-2]
0x18003c04a  cmp     ecx, 1
0x18003c04d  jbe     short loc_18003C059
0x18003c04f  add     eax, 0FFFFF8ECh
0x18003c054  cmp     eax, 3
0x18003c057  ja      short loc_18003C0D4
0x18003c059  xor     eax, eax
0x18003c05b  mov     [rsp+2F8h+hActCtx], rax
0x18003c060  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x18003c067  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x18003c06c  mov     rcx, rax; hActCtx
0x18003c06f  call    cs:__imp_ActivateActCtx
0x18003c075  test    eax, eax
0x18003c077  jz      short loc_18003C0CF
0x18003c079  mov     ebx, 70h ; 'p'
0x18003c07e  mov     r8d, ebx; Size
0x18003c081  xor     edx, edx; Val
0x18003c083  lea     rcx, [rsp+2F8h+pActCtx]; void *
0x18003c088  call    memset_0
0x18003c08d  mov     dword ptr [rsp+2F8h+pActCtx], ebx
0x18003c091  lea     rax, [rsp+2F8h+pActCtx]
0x18003c096  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x18003c09b  lea     r9, StringToFind; "Comctl32.dll"
0x18003c0a2  xor     edx, edx; lpExtensionGuid
0x18003c0a4  lea     r8d, [rbx-6Eh]; ulSectionId
0x18003c0a8  xor     ecx, ecx; dwFlags
0x18003c0aa  call    cs:__imp_FindActCtxSectionStringW
0x18003c0b0  test    eax, eax
0x18003c0b2  jz      short loc_18003C0C2
0x18003c0b4  lea     rcx, StringToFind; "Comctl32.dll"
0x18003c0bb  call    cs:__imp_LoadLibraryW
0x18003c0c1  nop
0x18003c0c2  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x18003c0c7  xor     ecx, ecx; dwFlags
0x18003c0c9  call    cs:__imp_DeactivateActCtx
0x18003c0cf  mov     ebx, 1
0x18003c0d4  mov     eax, ebx
0x18003c0d6  mov     rcx, [rsp+2F8h+var_18]
0x18003c0de  xor     rcx, rsp; StackCookie
0x18003c0e1  call    __security_check_cookie
0x18003c0e6  add     rsp, 2F0h
0x18003c0ed  pop     rbx
0x18003c0ee  retn
0x180081506  push    rbp
0x180081508  sub     rsp, 40h
0x18008150c  mov     rbp, rdx
0x18008150f  mov     rdx, [rbp+48h]; ulCookie
0x180081513  xor     ecx, ecx; dwFlags
0x180081515  call    cs:__imp_DeactivateActCtx
0x18008151b  nop
0x18008151c  add     rsp, 40h
0x180081520  pop     rbp
0x180081521  retn
```
