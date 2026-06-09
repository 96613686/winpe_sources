# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x180051d0c`
- end: `0x180051ecd`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `449`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180051c7c`

## callees

- `0x18003e690`
- `0x180051d0c`

## import_xrefs

- `KERNEL32!GetModuleHandleExW` at `0x180051d9e`
- `KERNEL32!GetModuleHandleExW` at `0x180051d9e`
- `KERNEL32!GetLastError` at `0x180051e2e`
- `KERNEL32!GetLastError` at `0x180051e2e`
- `KERNEL32!GetModuleFileNameW` at `0x180051dbf`
- `KERNEL32!GetModuleFileNameW` at `0x180051dbf`
- `KERNEL32!CreateActCtxW` at `0x180051e1d`
- `KERNEL32!CreateActCtxW` at `0x180051e1d`
- `KERNEL32!ActivateActCtx` at `0x180051e5d`
- `KERNEL32!ActivateActCtx` at `0x180051e5d`
- `KERNEL32!SetLastError` at `0x180051dd7`
- `KERNEL32!SetLastError` at `0x180051dd7`
- `KERNEL32!FindActCtxSectionStringW` at `0x180051e88`
- `KERNEL32!FindActCtxSectionStringW` at `0x180051e88`
- `KERNEL32!DeactivateActCtx` at `0x180051ea7`
- `KERNEL32!DeactivateActCtx` at `0x1801499e7`
- `KERNEL32!DeactivateActCtx` at `0x180051ea7`
- `KERNEL32!DeactivateActCtx` at `0x1801499e7`
- `KERNEL32!QueryActCtxW` at `0x180051d73`
- `KERNEL32!QueryActCtxW` at `0x180051d73`
- `KERNEL32!LoadLibraryW` at `0x180051e99`
- `KERNEL32!LoadLibraryW` at `0x180051e99`

## string_xrefs

- `0x180051e79`: `Comctl32.dll`
- `0x180051e92`: `Comctl32.dll`

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
  if ( IsolationAwarePrivateT_SqbjaYRiRY || WinbaseIsolationAwarePrivateT_UnPgpgk != (HANDLE)-1LL )
    return 1;
  if ( QueryActCtxW(0x80000010, &WinbaseIsolationAwarePrivateT_UnPgpgk, 0, 1u, hActCtx, 0x10u, 0) )
  {
    ActCtxW = hActCtx[0];
    if ( hActCtx[0] )
      goto LABEL_13;
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
0x180051d0c  push    rbx
0x180051d0e  sub     rsp, 2F0h
0x180051d15  mov     rax, cs:__security_cookie
0x180051d1c  xor     rax, rsp
0x180051d1f  mov     [rsp+2F8h+var_18], rax
0x180051d27  xor     ebx, ebx
0x180051d29  mov     [rsp+2F8h+Cookie], rbx
0x180051d2e  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, ebx
0x180051d34  jnz     loc_180051EAD
0x180051d3a  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x180051d42  jnz     loc_180051EAD
0x180051d48  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x180051d4d  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x180051d56  lea     rax, [rsp+2F8h+hActCtx]
0x180051d5b  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x180051d60  lea     r9d, [rbx+1]; ulInfoClass
0x180051d64  xor     r8d, r8d; pvSubInstance
0x180051d67  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x180051d6e  mov     ecx, 80000010h; dwFlags
0x180051d73  call    cs:__imp_QueryActCtxW
0x180051d79  test    eax, eax
0x180051d7b  jz      loc_180051EB2
0x180051d81  mov     rax, [rsp+2F8h+hActCtx]
0x180051d86  test    rax, rax
0x180051d89  jnz     loc_180051E4E
0x180051d8f  lea     r8, [rsp+2F8h+phModule]; phModule
0x180051d94  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x180051d9b  lea     ecx, [rbx+6]; dwFlags
0x180051d9e  call    cs:__imp_GetModuleHandleExW
0x180051da4  test    eax, eax
0x180051da6  jz      loc_180051EB2
0x180051dac  mov     r8d, 105h; nSize
0x180051db2  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x180051dba  mov     rcx, [rsp+2F8h+phModule]; hModule
0x180051dbf  call    cs:__imp_GetModuleFileNameW
0x180051dc5  test    eax, eax
0x180051dc7  jz      loc_180051EB2
0x180051dcd  cmp     eax, 105h
0x180051dd2  jb      short loc_180051DE2
0x180051dd4  lea     ecx, [rbx+6Fh]; dwErrCode
0x180051dd7  call    cs:__imp_SetLastError
0x180051ddd  jmp     loc_180051EB2
0x180051de2  mov     dword ptr [rsp+2F8h+pActCtx], 38h ; '8'
0x180051dea  mov     dword ptr [rsp+2F8h+pActCtx+4], 88h
0x180051df2  lea     rax, [rsp+2F8h+Filename]
0x180051dfa  mov     qword ptr [rsp+2F8h+pActCtx+8], rax
0x180051dff  mov     qword ptr [rsp+2F8h+pActCtx+20h], 3
0x180051e0b  mov     rax, [rsp+2F8h+phModule]
0x180051e10  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x180051e18  lea     rcx, [rsp+2F8h+pActCtx]; pActCtx
0x180051e1d  call    cs:__imp_CreateActCtxW
0x180051e23  mov     [rsp+2F8h+hActCtx], rax
0x180051e28  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180051e2c  jnz     short loc_180051E4E
0x180051e2e  call    cs:__imp_GetLastError
0x180051e34  lea     ecx, [rax-2]
0x180051e37  cmp     ecx, 1
0x180051e3a  jbe     short loc_180051E46
0x180051e3c  add     eax, 0FFFFF8ECh
0x180051e41  cmp     eax, 3
0x180051e44  ja      short loc_180051EB2
0x180051e46  mov     rax, rbx
0x180051e49  mov     [rsp+2F8h+hActCtx], rbx
0x180051e4e  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x180051e55  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x180051e5a  mov     rcx, rax; hActCtx
0x180051e5d  call    cs:__imp_ActivateActCtx
0x180051e63  test    eax, eax
0x180051e65  jz      short loc_180051EAD
0x180051e67  mov     dword ptr [rsp+2F8h+pActCtx], 70h ; 'p'
0x180051e6f  lea     rax, [rsp+2F8h+pActCtx]
0x180051e74  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x180051e79  lea     r9, StringToFind; "Comctl32.dll"
0x180051e80  xor     edx, edx; lpExtensionGuid
0x180051e82  xor     ecx, ecx; dwFlags
0x180051e84  lea     r8d, [rdx+2]; ulSectionId
0x180051e88  call    cs:__imp_FindActCtxSectionStringW
0x180051e8e  test    eax, eax
0x180051e90  jz      short loc_180051EA0
0x180051e92  lea     rcx, StringToFind; "Comctl32.dll"
0x180051e99  call    cs:__imp_LoadLibraryW
0x180051e9f  nop
0x180051ea0  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x180051ea5  xor     ecx, ecx; dwFlags
0x180051ea7  call    cs:__imp_DeactivateActCtx
0x180051ead  mov     ebx, 1
0x180051eb2  mov     eax, ebx
0x180051eb4  mov     rcx, [rsp+2F8h+var_18]
0x180051ebc  xor     rcx, rsp; StackCookie
0x180051ebf  call    __security_check_cookie
0x180051ec4  add     rsp, 2F0h
0x180051ecb  pop     rbx
0x180051ecc  retn
0x1801499d8  push    rbp
0x1801499da  sub     rsp, 40h
0x1801499de  mov     rbp, rdx
0x1801499e1  mov     rdx, [rbp+40h]; ulCookie
0x1801499e5  xor     ecx, ecx; dwFlags
0x1801499e7  call    cs:__imp_DeactivateActCtx
0x1801499ed  nop
0x1801499ee  add     rsp, 40h
0x1801499f2  pop     rbp
0x1801499f3  retn
```
