# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x18001bb30`
- end: `0x18001bd2f`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001ba28`

## callees

- `0x18001bb30`
- `0x18003104a`
- `0x180031070`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001bc12`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001bc12`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001bbf1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001bbf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bc81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bc81`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bc2a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001bc2a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001bcfb`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001bcfb`
- `KERNEL32!QueryActCtxW` at `0x18001bba4`
- `KERNEL32!QueryActCtxW` at `0x18001bba4`
- `KERNEL32!CreateActCtxW` at `0x18001bc70`
- `KERNEL32!CreateActCtxW` at `0x18001bc70`
- `KERNEL32!FindActCtxSectionStringW` at `0x18001bcea`
- `KERNEL32!FindActCtxSectionStringW` at `0x18001bcea`
- `KERNEL32!ActivateActCtx` at `0x18001bcaf`
- `KERNEL32!ActivateActCtx` at `0x18001bcaf`
- `KERNEL32!DeactivateActCtx` at `0x18001bd09`
- `KERNEL32!DeactivateActCtx` at `0x1800314e6`
- `KERNEL32!DeactivateActCtx` at `0x18001bd09`
- `KERNEL32!DeactivateActCtx` at `0x1800314e6`

## string_xrefs

- `0x18001bcdb`: `Comctl32.dll`
- `0x18001bcf4`: `Comctl32.dll`

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
0x18001bb30  push    rbx
0x18001bb32  sub     rsp, 2F0h
0x18001bb39  mov     rax, cs:__security_cookie
0x18001bb40  xor     rax, rsp
0x18001bb43  mov     [rsp+2F8h+var_18], rax
0x18001bb4b  xorps   xmm0, xmm0
0x18001bb4e  movups  xmmword ptr [rsp+2F8h+hActCtx], xmm0
0x18001bb53  mov     [rsp+2F8h+Cookie], 0
0x18001bb5c  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18001bb63  jnz     loc_18001BD0F
0x18001bb69  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x18001bb71  jnz     loc_18001BD0F
0x18001bb77  xor     ebx, ebx
0x18001bb79  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x18001bb7e  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x18001bb87  lea     rax, [rsp+2F8h+hActCtx]
0x18001bb8c  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x18001bb91  lea     r9d, [rbx+1]; ulInfoClass
0x18001bb95  xor     r8d, r8d; pvSubInstance
0x18001bb98  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x18001bb9f  mov     ecx, 80000010h; dwFlags
0x18001bba4  call    cs:__imp_QueryActCtxW
0x18001bbaa  test    eax, eax
0x18001bbac  jz      loc_18001BD14
0x18001bbb2  mov     rax, [rsp+2F8h+hActCtx]
0x18001bbb7  test    rax, rax
0x18001bbba  jnz     loc_18001BCA0
0x18001bbc0  xorps   xmm0, xmm0
0x18001bbc3  movups  xmmword ptr [rsp+2F8h+pActCtx], xmm0
0x18001bbc8  movups  xmmword ptr [rsp+2F8h+pActCtx+10h], xmm0
0x18001bbcd  movups  xmmword ptr [rsp+2F8h+pActCtx+20h], xmm0
0x18001bbd5  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x18001bbdd  mov     [rsp+2F8h+phModule], rax
0x18001bbe2  lea     r8, [rsp+2F8h+phModule]; phModule
0x18001bbe7  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x18001bbee  lea     ecx, [rbx+6]; dwFlags
0x18001bbf1  call    cs:__imp_GetModuleHandleExW
0x18001bbf7  test    eax, eax
0x18001bbf9  jz      loc_18001BD14
0x18001bbff  mov     r8d, 105h; nSize
0x18001bc05  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x18001bc0d  mov     rcx, [rsp+2F8h+phModule]; hModule
0x18001bc12  call    cs:__imp_GetModuleFileNameW
0x18001bc18  test    eax, eax
0x18001bc1a  jz      loc_18001BD14
0x18001bc20  cmp     eax, 105h
0x18001bc25  jb      short loc_18001BC35
0x18001bc27  lea     ecx, [rbx+6Fh]; dwErrCode
0x18001bc2a  call    cs:__imp_SetLastError
0x18001bc30  jmp     loc_18001BD14
0x18001bc35  mov     dword ptr [rsp+2F8h+pActCtx], 38h ; '8'
0x18001bc3d  mov     dword ptr [rsp+2F8h+pActCtx+4], 88h
0x18001bc45  lea     rax, [rsp+2F8h+Filename]
0x18001bc4d  mov     qword ptr [rsp+2F8h+pActCtx+8], rax
0x18001bc52  mov     qword ptr [rsp+2F8h+pActCtx+20h], 3
0x18001bc5e  mov     rax, [rsp+2F8h+phModule]
0x18001bc63  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x18001bc6b  lea     rcx, [rsp+2F8h+pActCtx]; pActCtx
0x18001bc70  call    cs:__imp_CreateActCtxW
0x18001bc76  mov     [rsp+2F8h+hActCtx], rax
0x18001bc7b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001bc7f  jnz     short loc_18001BCA0
0x18001bc81  call    cs:__imp_GetLastError
0x18001bc87  lea     ecx, [rax-2]
0x18001bc8a  cmp     ecx, 1
0x18001bc8d  jbe     short loc_18001BC99
0x18001bc8f  add     eax, 0FFFFF8ECh
0x18001bc94  cmp     eax, 3
0x18001bc97  ja      short loc_18001BD14
0x18001bc99  xor     eax, eax
0x18001bc9b  mov     [rsp+2F8h+hActCtx], rax
0x18001bca0  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x18001bca7  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x18001bcac  mov     rcx, rax; hActCtx
0x18001bcaf  call    cs:__imp_ActivateActCtx
0x18001bcb5  test    eax, eax
0x18001bcb7  jz      short loc_18001BD0F
0x18001bcb9  mov     ebx, 70h ; 'p'
0x18001bcbe  mov     r8d, ebx; Size
0x18001bcc1  xor     edx, edx; Val
0x18001bcc3  lea     rcx, [rsp+2F8h+pActCtx]; void *
0x18001bcc8  call    memset_0
0x18001bccd  mov     dword ptr [rsp+2F8h+pActCtx], ebx
0x18001bcd1  lea     rax, [rsp+2F8h+pActCtx]
0x18001bcd6  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x18001bcdb  lea     r9, LibFileName; "Comctl32.dll"
0x18001bce2  xor     edx, edx; lpExtensionGuid
0x18001bce4  lea     r8d, [rbx-6Eh]; ulSectionId
0x18001bce8  xor     ecx, ecx; dwFlags
0x18001bcea  call    cs:__imp_FindActCtxSectionStringW
0x18001bcf0  test    eax, eax
0x18001bcf2  jz      short loc_18001BD02
0x18001bcf4  lea     rcx, LibFileName; "Comctl32.dll"
0x18001bcfb  call    cs:__imp_LoadLibraryW
0x18001bd01  nop
0x18001bd02  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x18001bd07  xor     ecx, ecx; dwFlags
0x18001bd09  call    cs:__imp_DeactivateActCtx
0x18001bd0f  mov     ebx, 1
0x18001bd14  mov     eax, ebx
0x18001bd16  mov     rcx, [rsp+2F8h+var_18]
0x18001bd1e  xor     rcx, rsp; StackCookie
0x18001bd21  call    __security_check_cookie
0x18001bd26  add     rsp, 2F0h
0x18001bd2d  pop     rbx
0x18001bd2e  retn
0x1800314d7  push    rbp
0x1800314d9  sub     rsp, 40h
0x1800314dd  mov     rbp, rdx
0x1800314e0  mov     rdx, [rbp+48h]; ulCookie
0x1800314e4  xor     ecx, ecx; dwFlags
0x1800314e6  call    cs:__imp_DeactivateActCtx
0x1800314ec  nop
0x1800314ed  add     rsp, 40h
0x1800314f1  pop     rbp
0x1800314f2  retn
```
