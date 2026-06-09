# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x18006e7f0`
- end: `0x18006e9f9`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `521`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006e760`

## callees

- `0x18006e7f0`
- `0x18025ab2a`
- `0x18025ab80`

## import_xrefs

- `KERNEL32!GetModuleHandleExW` at `0x18006e93b`
- `KERNEL32!GetModuleHandleExW` at `0x18006e93b`
- `KERNEL32!GetLastError` at `0x18006e9d1`
- `KERNEL32!GetLastError` at `0x18006e9d1`
- `KERNEL32!SetLastError` at `0x18006e976`
- `KERNEL32!SetLastError` at `0x18006e976`
- `KERNEL32!DeactivateActCtx` at `0x18006e8fd`
- `KERNEL32!DeactivateActCtx` at `0x18025acfe`
- `KERNEL32!DeactivateActCtx` at `0x18006e8fd`
- `KERNEL32!DeactivateActCtx` at `0x18025acfe`
- `KERNEL32!ActivateActCtx` at `0x18006e89f`
- `KERNEL32!ActivateActCtx` at `0x18006e89f`
- `KERNEL32!LoadLibraryW` at `0x18006e8ef`
- `KERNEL32!LoadLibraryW` at `0x18006e8ef`
- `KERNEL32!FindActCtxSectionStringW` at `0x18006e8de`
- `KERNEL32!FindActCtxSectionStringW` at `0x18006e8de`
- `KERNEL32!CreateActCtxW` at `0x18006e9bc`
- `KERNEL32!CreateActCtxW` at `0x18006e9bc`
- `KERNEL32!GetModuleFileNameW` at `0x18006e95c`
- `KERNEL32!GetModuleFileNameW` at `0x18006e95c`
- `KERNEL32!QueryActCtxW` at `0x18006e87c`
- `KERNEL32!QueryActCtxW` at `0x18006e87c`

## string_xrefs

- `0x18006e8cf`: `Comctl32.dll`
- `0x18006e8e8`: `Comctl32.dll`

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
  tagACTCTX_SECTION_KEYED_DATA ReturnedData; // [rsp+60h] [rbp-298h] BYREF
  WCHAR Filename[264]; // [rsp+D0h] [rbp-228h] BYREF

  *(_OWORD *)hActCtx = 0;
  Cookie = 0;
  if ( WinbaseIsolationAwarePrivateT_UnPgpgk != (HANDLE)-1LL || IsolationAwarePrivateT_SqbjaYRiRY )
    return 1;
  v0 = 0;
  if ( !QueryActCtxW(0x80000010, &WinbaseIsolationAwarePrivateT_UnPgpgk, 0, 1u, hActCtx, 0x10u, 0) )
    return v0;
  ActCtxW = hActCtx[0];
  if ( hActCtx[0] )
  {
LABEL_7:
    WinbaseIsolationAwarePrivateT_UnPgpgk = ActCtxW;
    if ( ActivateActCtx(ActCtxW, &Cookie) )
    {
      memset_0(&ReturnedData, 0, sizeof(ReturnedData));
      ReturnedData.cbSize = 112;
      if ( FindActCtxSectionStringW(0, 0, 2u, L"Comctl32.dll", &ReturnedData) )
        LoadLibraryW(L"Comctl32.dll");
      DeactivateActCtx(0, Cookie);
    }
    return 1;
  }
  memset(&ReturnedData, 0, 56);
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
      ReturnedData.cbSize = 56;
      ReturnedData.ulDataFormatVersion = 136;
      ReturnedData.lpData = Filename;
      *(_QWORD *)&ReturnedData.ulSectionGlobalDataLength = 3;
      *(_QWORD *)&ReturnedData.ulSectionTotalLength = phModule;
      ActCtxW = CreateActCtxW((PCACTCTXW)&ReturnedData);
      hActCtx[0] = ActCtxW;
      if ( ActCtxW != (HANDLE)-1LL )
        goto LABEL_7;
      LastError = GetLastError();
      if ( LastError - 2 <= 1 || LastError - 1812 <= 3 )
      {
        ActCtxW = 0;
        hActCtx[0] = 0;
        goto LABEL_7;
      }
    }
  }
  return v0;
}

```

## disassembly

```asm
0x18006e7f0  push    rbx
0x18006e7f2  sub     rsp, 2F0h
0x18006e7f9  mov     rax, cs:__security_cookie
0x18006e800  xor     rax, rsp
0x18006e803  mov     [rsp+2F8h+var_18], rax
0x18006e80b  xorps   xmm0, xmm0
0x18006e80e  movups  xmmword ptr [rsp+2F8h+hActCtx], xmm0
0x18006e813  mov     [rsp+2F8h+Cookie], 0
0x18006e81c  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x18006e824  jz      short loc_18006E846
0x18006e826  mov     ebx, 1
0x18006e82b  mov     eax, ebx
0x18006e82d  mov     rcx, [rsp+2F8h+var_18]
0x18006e835  xor     rcx, rsp; StackCookie
0x18006e838  call    __security_check_cookie
0x18006e83d  add     rsp, 2F0h
0x18006e844  pop     rbx
0x18006e845  retn
0x18006e846  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18006e84d  jnz     short loc_18006E826
0x18006e84f  xor     ebx, ebx
0x18006e851  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x18006e856  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x18006e85f  lea     rax, [rsp+2F8h+hActCtx]
0x18006e864  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x18006e869  lea     r9d, [rbx+1]; ulInfoClass
0x18006e86d  xor     r8d, r8d; pvSubInstance
0x18006e870  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x18006e877  mov     ecx, 80000010h; dwFlags
0x18006e87c  call    cs:__imp_QueryActCtxW
0x18006e882  test    eax, eax
0x18006e884  jz      short loc_18006E82B
0x18006e886  mov     rax, [rsp+2F8h+hActCtx]
0x18006e88b  test    rax, rax
0x18006e88e  jz      short loc_18006E908
0x18006e890  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x18006e897  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x18006e89c  mov     rcx, rax; hActCtx
0x18006e89f  call    cs:__imp_ActivateActCtx
0x18006e8a5  test    eax, eax
0x18006e8a7  jz      loc_18006E826
0x18006e8ad  mov     ebx, 70h ; 'p'
0x18006e8b2  mov     r8d, ebx; Size
0x18006e8b5  xor     edx, edx; Val
0x18006e8b7  lea     rcx, [rsp+2F8h+ReturnedData]; void *
0x18006e8bc  call    memset_0
0x18006e8c1  mov     [rsp+2F8h+ReturnedData.cbSize], ebx
0x18006e8c5  lea     rax, [rsp+2F8h+ReturnedData]
0x18006e8ca  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x18006e8cf  lea     r9, LibFileName; "Comctl32.dll"
0x18006e8d6  xor     edx, edx; lpExtensionGuid
0x18006e8d8  lea     r8d, [rbx-6Eh]; ulSectionId
0x18006e8dc  xor     ecx, ecx; dwFlags
0x18006e8de  call    cs:__imp_FindActCtxSectionStringW
0x18006e8e4  test    eax, eax
0x18006e8e6  jz      short loc_18006E8F6
0x18006e8e8  lea     rcx, LibFileName; "Comctl32.dll"
0x18006e8ef  call    cs:__imp_LoadLibraryW
0x18006e8f5  nop
0x18006e8f6  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x18006e8fb  xor     ecx, ecx; dwFlags
0x18006e8fd  call    cs:__imp_DeactivateActCtx
0x18006e903  jmp     loc_18006E826
0x18006e908  xorps   xmm0, xmm0
0x18006e90b  xor     eax, eax
0x18006e90d  movups  xmmword ptr [rsp+2F8h+ReturnedData.cbSize], xmm0
0x18006e912  movups  xmmword ptr [rsp+2F8h+ReturnedData.ulLength], xmm0
0x18006e917  movups  xmmword ptr [rsp+2F8h+ReturnedData.ulSectionGlobalDataLength], xmm0
0x18006e91f  mov     qword ptr [rsp+2F8h+ReturnedData.ulSectionTotalLength], rax
0x18006e927  mov     [rsp+2F8h+phModule], rax
0x18006e92c  lea     r8, [rsp+2F8h+phModule]; phModule
0x18006e931  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x18006e938  lea     ecx, [rax+6]; dwFlags
0x18006e93b  call    cs:__imp_GetModuleHandleExW
0x18006e941  test    eax, eax
0x18006e943  jz      loc_18006E82B
0x18006e949  mov     r8d, 105h; nSize
0x18006e94f  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x18006e957  mov     rcx, [rsp+2F8h+phModule]; hModule
0x18006e95c  call    cs:__imp_GetModuleFileNameW
0x18006e962  test    eax, eax
0x18006e964  jz      loc_18006E82B
0x18006e96a  cmp     eax, 105h
0x18006e96f  jb      short loc_18006E981
0x18006e971  mov     ecx, 6Fh ; 'o'; dwErrCode
0x18006e976  call    cs:__imp_SetLastError
0x18006e97c  jmp     loc_18006E82B
0x18006e981  mov     [rsp+2F8h+ReturnedData.cbSize], 38h ; '8'
0x18006e989  mov     [rsp+2F8h+ReturnedData.ulDataFormatVersion], 88h
0x18006e991  lea     rax, [rsp+2F8h+Filename]
0x18006e999  mov     [rsp+2F8h+ReturnedData.lpData], rax
0x18006e99e  mov     qword ptr [rsp+2F8h+ReturnedData.ulSectionGlobalDataLength], 3
0x18006e9aa  mov     rax, [rsp+2F8h+phModule]
0x18006e9af  mov     qword ptr [rsp+2F8h+ReturnedData.ulSectionTotalLength], rax
0x18006e9b7  lea     rcx, [rsp+2F8h+ReturnedData]; pActCtx
0x18006e9bc  call    cs:__imp_CreateActCtxW
0x18006e9c2  mov     [rsp+2F8h+hActCtx], rax
0x18006e9c7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006e9cb  jnz     loc_18006E890
0x18006e9d1  call    cs:__imp_GetLastError
0x18006e9d7  lea     ecx, [rax-2]
0x18006e9da  cmp     ecx, 1
0x18006e9dd  jbe     short loc_18006E9ED
0x18006e9df  add     eax, 0FFFFF8ECh
0x18006e9e4  cmp     eax, 3
0x18006e9e7  ja      loc_18006E82B
0x18006e9ed  xor     eax, eax
0x18006e9ef  mov     [rsp+2F8h+hActCtx], rax
0x18006e9f4  jmp     loc_18006E890
0x18025acef  push    rbp
0x18025acf1  sub     rsp, 40h
0x18025acf5  mov     rbp, rdx
0x18025acf8  mov     rdx, [rbp+48h]; ulCookie
0x18025acfc  xor     ecx, ecx; dwFlags
0x18025acfe  call    cs:__imp_DeactivateActCtx
0x18025ad04  nop
0x18025ad05  add     rsp, 40h
0x18025ad09  pop     rbp
0x18025ad0a  retn
```
