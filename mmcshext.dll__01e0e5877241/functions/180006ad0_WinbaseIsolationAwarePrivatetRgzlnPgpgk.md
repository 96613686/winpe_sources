# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x180006ad0`
- end: `0x180006cd0`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `512`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006a44`

## callees

- `0x180006ad0`
- `0x18000a582`
- `0x18000a5b0`

## import_xrefs

- `KERNEL32!QueryActCtxW` at `0x180006b44`
- `KERNEL32!QueryActCtxW` at `0x180006b44`
- `KERNEL32!GetModuleHandleExW` at `0x180006b91`
- `KERNEL32!GetModuleHandleExW` at `0x180006b91`
- `KERNEL32!GetModuleFileNameW` at `0x180006bb2`
- `KERNEL32!GetModuleFileNameW` at `0x180006bb2`
- `KERNEL32!SetLastError` at `0x180006bca`
- `KERNEL32!SetLastError` at `0x180006bca`
- `KERNEL32!CreateActCtxW` at `0x180006c10`
- `KERNEL32!CreateActCtxW` at `0x180006c10`
- `KERNEL32!FindActCtxSectionStringW` at `0x180006c8b`
- `KERNEL32!FindActCtxSectionStringW` at `0x180006c8b`
- `KERNEL32!LoadLibraryW` at `0x180006c9c`
- `KERNEL32!LoadLibraryW` at `0x180006c9c`
- `KERNEL32!DeactivateActCtx` at `0x180006caa`
- `KERNEL32!DeactivateActCtx` at `0x18000ac2f`
- `KERNEL32!DeactivateActCtx` at `0x180006caa`
- `KERNEL32!DeactivateActCtx` at `0x18000ac2f`
- `KERNEL32!ActivateActCtx` at `0x180006c50`
- `KERNEL32!ActivateActCtx` at `0x180006c50`
- `KERNEL32!GetLastError` at `0x180006c21`
- `KERNEL32!GetLastError` at `0x180006c21`

## string_xrefs

- `0x180006c7c`: `Comctl32.dll`
- `0x180006c95`: `Comctl32.dll`

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
        if ( LastError - 1812 <= 3 || LastError - 2 <= 1 )
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
0x180006ad0  push    rbx
0x180006ad2  sub     rsp, 2F0h
0x180006ad9  mov     rax, cs:__security_cookie
0x180006ae0  xor     rax, rsp
0x180006ae3  mov     [rsp+2F8h+var_18], rax
0x180006aeb  xorps   xmm0, xmm0
0x180006aee  movups  xmmword ptr [rsp+2F8h+hActCtx], xmm0
0x180006af3  mov     [rsp+2F8h+Cookie], 0
0x180006afc  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180006b03  jnz     loc_180006CB0
0x180006b09  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x180006b11  jnz     loc_180006CB0
0x180006b17  xor     ebx, ebx
0x180006b19  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x180006b1e  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x180006b27  lea     rax, [rsp+2F8h+hActCtx]
0x180006b2c  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x180006b31  lea     r9d, [rbx+1]; ulInfoClass
0x180006b35  xor     r8d, r8d; pvSubInstance
0x180006b38  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x180006b3f  mov     ecx, 80000010h; dwFlags
0x180006b44  call    cs:__imp_QueryActCtxW
0x180006b4a  test    eax, eax
0x180006b4c  jz      loc_180006CB5
0x180006b52  mov     rax, [rsp+2F8h+hActCtx]
0x180006b57  test    rax, rax
0x180006b5a  jnz     loc_180006C41
0x180006b60  xorps   xmm0, xmm0
0x180006b63  movups  xmmword ptr [rsp+2F8h+pActCtx], xmm0
0x180006b68  movups  xmmword ptr [rsp+2F8h+pActCtx+10h], xmm0
0x180006b6d  movups  xmmword ptr [rsp+2F8h+pActCtx+20h], xmm0
0x180006b75  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x180006b7d  mov     [rsp+2F8h+phModule], rax
0x180006b82  lea     r8, [rsp+2F8h+phModule]; phModule
0x180006b87  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x180006b8e  lea     ecx, [rbx+6]; dwFlags
0x180006b91  call    cs:__imp_GetModuleHandleExW
0x180006b97  test    eax, eax
0x180006b99  jz      loc_180006CB5
0x180006b9f  mov     r8d, 105h; nSize
0x180006ba5  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x180006bad  mov     rcx, [rsp+2F8h+phModule]; hModule
0x180006bb2  call    cs:__imp_GetModuleFileNameW
0x180006bb8  test    eax, eax
0x180006bba  jz      loc_180006CB5
0x180006bc0  cmp     eax, 105h
0x180006bc5  jb      short loc_180006BD5
0x180006bc7  lea     ecx, [rbx+6Fh]; dwErrCode
0x180006bca  call    cs:__imp_SetLastError
0x180006bd0  jmp     loc_180006CB5
0x180006bd5  mov     dword ptr [rsp+2F8h+pActCtx], 38h ; '8'
0x180006bdd  mov     dword ptr [rsp+2F8h+pActCtx+4], 88h
0x180006be5  lea     rax, [rsp+2F8h+Filename]
0x180006bed  mov     qword ptr [rsp+2F8h+pActCtx+8], rax
0x180006bf2  mov     qword ptr [rsp+2F8h+pActCtx+20h], 3
0x180006bfe  mov     rax, [rsp+2F8h+phModule]
0x180006c03  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x180006c0b  lea     rcx, [rsp+2F8h+pActCtx]; pActCtx
0x180006c10  call    cs:__imp_CreateActCtxW
0x180006c16  mov     [rsp+2F8h+hActCtx], rax
0x180006c1b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180006c1f  jnz     short loc_180006C41
0x180006c21  call    cs:__imp_GetLastError
0x180006c27  lea     ecx, [rax-714h]
0x180006c2d  cmp     ecx, 3
0x180006c30  jbe     short loc_180006C3A
0x180006c32  add     eax, 0FFFFFFFEh
0x180006c35  cmp     eax, 1
0x180006c38  ja      short loc_180006CB5
0x180006c3a  xor     eax, eax
0x180006c3c  mov     [rsp+2F8h+hActCtx], rax
0x180006c41  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x180006c48  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x180006c4d  mov     rcx, rax; hActCtx
0x180006c50  call    cs:__imp_ActivateActCtx
0x180006c56  test    eax, eax
0x180006c58  jz      short loc_180006CB0
0x180006c5a  mov     ebx, 70h ; 'p'
0x180006c5f  mov     r8d, ebx; Size
0x180006c62  xor     edx, edx; Val
0x180006c64  lea     rcx, [rsp+2F8h+pActCtx]; void *
0x180006c69  call    memset_0
0x180006c6e  mov     dword ptr [rsp+2F8h+pActCtx], ebx
0x180006c72  lea     rax, [rsp+2F8h+pActCtx]
0x180006c77  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x180006c7c  lea     r9, LibFileName; "Comctl32.dll"
0x180006c83  xor     edx, edx; lpExtensionGuid
0x180006c85  lea     r8d, [rbx-6Eh]; ulSectionId
0x180006c89  xor     ecx, ecx; dwFlags
0x180006c8b  call    cs:__imp_FindActCtxSectionStringW
0x180006c91  test    eax, eax
0x180006c93  jz      short loc_180006CA3
0x180006c95  lea     rcx, LibFileName; "Comctl32.dll"
0x180006c9c  call    cs:__imp_LoadLibraryW
0x180006ca2  nop
0x180006ca3  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x180006ca8  xor     ecx, ecx; dwFlags
0x180006caa  call    cs:__imp_DeactivateActCtx
0x180006cb0  mov     ebx, 1
0x180006cb5  mov     eax, ebx
0x180006cb7  mov     rcx, [rsp+2F8h+var_18]
0x180006cbf  xor     rcx, rsp; StackCookie
0x180006cc2  call    __security_check_cookie
0x180006cc7  add     rsp, 2F0h
0x180006cce  pop     rbx
0x180006ccf  retn
0x18000ac20  push    rbp
0x18000ac22  sub     rsp, 40h
0x18000ac26  mov     rbp, rdx
0x18000ac29  mov     rdx, [rbp+48h]; ulCookie
0x18000ac2d  xor     ecx, ecx; dwFlags
0x18000ac2f  call    cs:__imp_DeactivateActCtx
0x18000ac35  nop
0x18000ac36  add     rsp, 40h
0x18000ac3a  pop     rbp
0x18000ac3b  retn
```
