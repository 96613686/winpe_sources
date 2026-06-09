# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x180023cac`
- end: `0x180023eab`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800206ec`

## callees

- `0x180002300`
- `0x180002f48`
- `0x180023cac`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180023d8e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180023d8e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180023d6d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180023d6d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023da6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023da6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023dfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023dfd`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180023e77`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180023e77`
- `KERNEL32!ActivateActCtx` at `0x180023e2b`
- `KERNEL32!ActivateActCtx` at `0x180023e2b`
- `KERNEL32!DeactivateActCtx` at `0x180023e85`
- `KERNEL32!DeactivateActCtx` at `0x180039226`
- `KERNEL32!DeactivateActCtx` at `0x180023e85`
- `KERNEL32!DeactivateActCtx` at `0x180039226`
- `KERNEL32!QueryActCtxW` at `0x180023d20`
- `KERNEL32!QueryActCtxW` at `0x180023d20`
- `KERNEL32!FindActCtxSectionStringW` at `0x180023e66`
- `KERNEL32!FindActCtxSectionStringW` at `0x180023e66`
- `KERNEL32!CreateActCtxW` at `0x180023dec`
- `KERNEL32!CreateActCtxW` at `0x180023dec`

## string_xrefs

- `0x180023e57`: `Comctl32.dll`
- `0x180023e70`: `Comctl32.dll`

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
0x180023cac  push    rbx
0x180023cae  sub     rsp, 2F0h
0x180023cb5  mov     rax, cs:__security_cookie
0x180023cbc  xor     rax, rsp
0x180023cbf  mov     [rsp+2F8h+var_18], rax
0x180023cc7  xorps   xmm0, xmm0
0x180023cca  movups  xmmword ptr [rsp+2F8h+hActCtx], xmm0
0x180023ccf  mov     [rsp+2F8h+Cookie], 0
0x180023cd8  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180023cdf  jnz     loc_180023E8B
0x180023ce5  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x180023ced  jnz     loc_180023E8B
0x180023cf3  xor     ebx, ebx
0x180023cf5  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x180023cfa  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x180023d03  lea     rax, [rsp+2F8h+hActCtx]
0x180023d08  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x180023d0d  lea     r9d, [rbx+1]; ulInfoClass
0x180023d11  xor     r8d, r8d; pvSubInstance
0x180023d14  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x180023d1b  mov     ecx, 80000010h; dwFlags
0x180023d20  call    cs:__imp_QueryActCtxW
0x180023d26  test    eax, eax
0x180023d28  jz      loc_180023E90
0x180023d2e  mov     rax, [rsp+2F8h+hActCtx]
0x180023d33  test    rax, rax
0x180023d36  jnz     loc_180023E1C
0x180023d3c  xorps   xmm0, xmm0
0x180023d3f  movups  xmmword ptr [rsp+2F8h+pActCtx], xmm0
0x180023d44  movups  xmmword ptr [rsp+2F8h+pActCtx+10h], xmm0
0x180023d49  movups  xmmword ptr [rsp+2F8h+pActCtx+20h], xmm0
0x180023d51  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x180023d59  mov     [rsp+2F8h+phModule], rax
0x180023d5e  lea     r8, [rsp+2F8h+phModule]; phModule
0x180023d63  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x180023d6a  lea     ecx, [rbx+6]; dwFlags
0x180023d6d  call    cs:__imp_GetModuleHandleExW
0x180023d73  test    eax, eax
0x180023d75  jz      loc_180023E90
0x180023d7b  mov     r8d, 105h; nSize
0x180023d81  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x180023d89  mov     rcx, [rsp+2F8h+phModule]; hModule
0x180023d8e  call    cs:__imp_GetModuleFileNameW
0x180023d94  test    eax, eax
0x180023d96  jz      loc_180023E90
0x180023d9c  cmp     eax, 105h
0x180023da1  jb      short loc_180023DB1
0x180023da3  lea     ecx, [rbx+6Fh]; dwErrCode
0x180023da6  call    cs:__imp_SetLastError
0x180023dac  jmp     loc_180023E90
0x180023db1  mov     dword ptr [rsp+2F8h+pActCtx], 38h ; '8'
0x180023db9  mov     dword ptr [rsp+2F8h+pActCtx+4], 88h
0x180023dc1  lea     rax, [rsp+2F8h+Filename]
0x180023dc9  mov     qword ptr [rsp+2F8h+pActCtx+8], rax
0x180023dce  mov     qword ptr [rsp+2F8h+pActCtx+20h], 3
0x180023dda  mov     rax, [rsp+2F8h+phModule]
0x180023ddf  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x180023de7  lea     rcx, [rsp+2F8h+pActCtx]; pActCtx
0x180023dec  call    cs:__imp_CreateActCtxW
0x180023df2  mov     [rsp+2F8h+hActCtx], rax
0x180023df7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180023dfb  jnz     short loc_180023E1C
0x180023dfd  call    cs:__imp_GetLastError
0x180023e03  lea     ecx, [rax-2]
0x180023e06  cmp     ecx, 1
0x180023e09  jbe     short loc_180023E15
0x180023e0b  add     eax, 0FFFFF8ECh
0x180023e10  cmp     eax, 3
0x180023e13  ja      short loc_180023E90
0x180023e15  xor     eax, eax
0x180023e17  mov     [rsp+2F8h+hActCtx], rax
0x180023e1c  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x180023e23  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x180023e28  mov     rcx, rax; hActCtx
0x180023e2b  call    cs:__imp_ActivateActCtx
0x180023e31  test    eax, eax
0x180023e33  jz      short loc_180023E8B
0x180023e35  mov     ebx, 70h ; 'p'
0x180023e3a  mov     r8d, ebx; Size
0x180023e3d  xor     edx, edx; Val
0x180023e3f  lea     rcx, [rsp+2F8h+pActCtx]; void *
0x180023e44  call    memset_0
0x180023e49  mov     dword ptr [rsp+2F8h+pActCtx], ebx
0x180023e4d  lea     rax, [rsp+2F8h+pActCtx]
0x180023e52  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x180023e57  lea     r9, LibFileName; "Comctl32.dll"
0x180023e5e  xor     edx, edx; lpExtensionGuid
0x180023e60  lea     r8d, [rbx-6Eh]; ulSectionId
0x180023e64  xor     ecx, ecx; dwFlags
0x180023e66  call    cs:__imp_FindActCtxSectionStringW
0x180023e6c  test    eax, eax
0x180023e6e  jz      short loc_180023E7E
0x180023e70  lea     rcx, LibFileName; "Comctl32.dll"
0x180023e77  call    cs:__imp_LoadLibraryW
0x180023e7d  nop
0x180023e7e  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x180023e83  xor     ecx, ecx; dwFlags
0x180023e85  call    cs:__imp_DeactivateActCtx
0x180023e8b  mov     ebx, 1
0x180023e90  mov     eax, ebx
0x180023e92  mov     rcx, [rsp+2F8h+var_18]
0x180023e9a  xor     rcx, rsp; StackCookie
0x180023e9d  call    __security_check_cookie
0x180023ea2  add     rsp, 2F0h
0x180023ea9  pop     rbx
0x180023eaa  retn
0x180039217  push    rbp
0x180039219  sub     rsp, 40h
0x18003921d  mov     rbp, rdx
0x180039220  mov     rdx, [rbp+48h]; ulCookie
0x180039224  xor     ecx, ecx; dwFlags
0x180039226  call    cs:__imp_DeactivateActCtx
0x18003922c  nop
0x18003922d  add     rsp, 40h
0x180039231  pop     rbp
0x180039232  retn
```
