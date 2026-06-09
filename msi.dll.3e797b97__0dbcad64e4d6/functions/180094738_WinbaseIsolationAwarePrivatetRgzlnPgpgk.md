# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x180094738`
- end: `0x180094982`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `586`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180094690`

## callees

- `0x180094738`
- `0x1802651ea`
- `0x180265240`

## import_xrefs

- `KERNEL32!GetModuleHandleExW` at `0x1800948a6`
- `KERNEL32!GetModuleHandleExW` at `0x1800948a6`
- `KERNEL32!GetLastError` at `0x180094954`
- `KERNEL32!GetLastError` at `0x180094954`
- `KERNEL32!SetLastError` at `0x1800948ed`
- `KERNEL32!SetLastError` at `0x1800948ed`
- `KERNEL32!DeactivateActCtx` at `0x180094862`
- `KERNEL32!DeactivateActCtx` at `0x180265408`
- `KERNEL32!DeactivateActCtx` at `0x180094862`
- `KERNEL32!DeactivateActCtx` at `0x180265408`
- `KERNEL32!ActivateActCtx` at `0x1800947f2`
- `KERNEL32!ActivateActCtx` at `0x1800947f2`
- `KERNEL32!LoadLibraryW` at `0x18009484e`
- `KERNEL32!LoadLibraryW` at `0x18009484e`
- `KERNEL32!FindActCtxSectionStringW` at `0x180094837`
- `KERNEL32!FindActCtxSectionStringW` at `0x180094837`
- `KERNEL32!CreateActCtxW` at `0x180094939`
- `KERNEL32!CreateActCtxW` at `0x180094939`
- `KERNEL32!GetModuleFileNameW` at `0x1800948cd`
- `KERNEL32!GetModuleFileNameW` at `0x1800948cd`
- `KERNEL32!QueryActCtxW` at `0x1800947c5`
- `KERNEL32!QueryActCtxW` at `0x1800947c5`

## string_xrefs

- `0x180094828`: `Comctl32.dll`
- `0x180094847`: `Comctl32.dll`

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
0x180094738  push    rbx
0x18009473a  sub     rsp, 2F0h
0x180094741  mov     rax, cs:__security_cookie
0x180094748  xor     rax, rsp
0x18009474b  mov     [rsp+2F8h+var_18], rax
0x180094753  xorps   xmm0, xmm0
0x180094756  movups  xmmword ptr [rsp+2F8h+hActCtx], xmm0
0x18009475b  mov     [rsp+2F8h+Cookie], 0
0x180094764  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x18009476c  jz      short loc_18009478F
0x18009476e  mov     ebx, 1
0x180094773  mov     eax, ebx
0x180094775  mov     rcx, [rsp+2F8h+var_18]
0x18009477d  xor     rcx, rsp; StackCookie
0x180094780  call    __security_check_cookie
0x180094785  add     rsp, 2F0h
0x18009478c  pop     rbx
0x18009478d  retn
0x18009478f  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180094796  jnz     short loc_18009476E
0x180094798  xor     ebx, ebx
0x18009479a  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x18009479f  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x1800947a8  lea     rax, [rsp+2F8h+hActCtx]
0x1800947ad  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x1800947b2  lea     r9d, [rbx+1]; ulInfoClass
0x1800947b6  xor     r8d, r8d; pvSubInstance
0x1800947b9  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x1800947c0  mov     ecx, 80000010h; dwFlags
0x1800947c5  call    cs:__imp_QueryActCtxW
0x1800947cc  nop     dword ptr [rax+rax+00h]
0x1800947d1  test    eax, eax
0x1800947d3  jz      short loc_180094773
0x1800947d5  mov     rax, [rsp+2F8h+hActCtx]
0x1800947da  test    rax, rax
0x1800947dd  jz      loc_180094873
0x1800947e3  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x1800947ea  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x1800947ef  mov     rcx, rax; hActCtx
0x1800947f2  call    cs:__imp_ActivateActCtx
0x1800947f9  nop     dword ptr [rax+rax+00h]
0x1800947fe  test    eax, eax
0x180094800  jz      loc_18009476E
0x180094806  mov     ebx, 70h ; 'p'
0x18009480b  mov     r8d, ebx; Size
0x18009480e  xor     edx, edx; Val
0x180094810  lea     rcx, [rsp+2F8h+ReturnedData]; void *
0x180094815  call    memset_0
0x18009481a  mov     [rsp+2F8h+ReturnedData.cbSize], ebx
0x18009481e  lea     rax, [rsp+2F8h+ReturnedData]
0x180094823  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x180094828  lea     r9, LibFileName; "Comctl32.dll"
0x18009482f  xor     edx, edx; lpExtensionGuid
0x180094831  lea     r8d, [rbx-6Eh]; ulSectionId
0x180094835  xor     ecx, ecx; dwFlags
0x180094837  call    cs:__imp_FindActCtxSectionStringW
0x18009483e  nop     dword ptr [rax+rax+00h]
0x180094843  test    eax, eax
0x180094845  jz      short loc_18009485B
0x180094847  lea     rcx, LibFileName; "Comctl32.dll"
0x18009484e  call    cs:__imp_LoadLibraryW
0x180094855  nop     dword ptr [rax+rax+00h]
0x18009485a  nop
0x18009485b  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x180094860  xor     ecx, ecx; dwFlags
0x180094862  call    cs:__imp_DeactivateActCtx
0x180094869  nop     dword ptr [rax+rax+00h]
0x18009486e  jmp     loc_18009476E
0x180094873  xorps   xmm0, xmm0
0x180094876  xor     eax, eax
0x180094878  movups  xmmword ptr [rsp+2F8h+ReturnedData.cbSize], xmm0
0x18009487d  movups  xmmword ptr [rsp+2F8h+ReturnedData.ulLength], xmm0
0x180094882  movups  xmmword ptr [rsp+2F8h+ReturnedData.ulSectionGlobalDataLength], xmm0
0x18009488a  mov     qword ptr [rsp+2F8h+ReturnedData.ulSectionTotalLength], rax
0x180094892  mov     [rsp+2F8h+phModule], rax
0x180094897  lea     r8, [rsp+2F8h+phModule]; phModule
0x18009489c  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x1800948a3  lea     ecx, [rax+6]; dwFlags
0x1800948a6  call    cs:__imp_GetModuleHandleExW
0x1800948ad  nop     dword ptr [rax+rax+00h]
0x1800948b2  test    eax, eax
0x1800948b4  jz      loc_180094773
0x1800948ba  mov     r8d, 105h; nSize
0x1800948c0  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x1800948c8  mov     rcx, [rsp+2F8h+phModule]; hModule
0x1800948cd  call    cs:__imp_GetModuleFileNameW
0x1800948d4  nop     dword ptr [rax+rax+00h]
0x1800948d9  test    eax, eax
0x1800948db  jz      loc_180094773
0x1800948e1  cmp     eax, 105h
0x1800948e6  jb      short loc_1800948FE
0x1800948e8  mov     ecx, 6Fh ; 'o'; dwErrCode
0x1800948ed  call    cs:__imp_SetLastError
0x1800948f4  nop     dword ptr [rax+rax+00h]
0x1800948f9  jmp     loc_180094773
0x1800948fe  mov     [rsp+2F8h+ReturnedData.cbSize], 38h ; '8'
0x180094906  mov     [rsp+2F8h+ReturnedData.ulDataFormatVersion], 88h
0x18009490e  lea     rax, [rsp+2F8h+Filename]
0x180094916  mov     [rsp+2F8h+ReturnedData.lpData], rax
0x18009491b  mov     qword ptr [rsp+2F8h+ReturnedData.ulSectionGlobalDataLength], 3
0x180094927  mov     rax, [rsp+2F8h+phModule]
0x18009492c  mov     qword ptr [rsp+2F8h+ReturnedData.ulSectionTotalLength], rax
0x180094934  lea     rcx, [rsp+2F8h+ReturnedData]; pActCtx
0x180094939  call    cs:__imp_CreateActCtxW
0x180094940  nop     dword ptr [rax+rax+00h]
0x180094945  mov     [rsp+2F8h+hActCtx], rax
0x18009494a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009494e  jnz     loc_1800947E3
0x180094954  call    cs:__imp_GetLastError
0x18009495b  nop     dword ptr [rax+rax+00h]
0x180094960  lea     ecx, [rax-2]
0x180094963  cmp     ecx, 1
0x180094966  jbe     short loc_180094976
0x180094968  add     eax, 0FFFFF8ECh
0x18009496d  cmp     eax, 3
0x180094970  ja      loc_180094773
0x180094976  xor     eax, eax
0x180094978  mov     [rsp+2F8h+hActCtx], rax
0x18009497d  jmp     loc_1800947E3
0x1802653f9  push    rbp
0x1802653fb  sub     rsp, 40h
0x1802653ff  mov     rbp, rdx
0x180265402  mov     rdx, [rbp+48h]; ulCookie
0x180265406  xor     ecx, ecx; dwFlags
0x180265408  call    cs:__imp_DeactivateActCtx
0x18026540f  nop     dword ptr [rax+rax+00h]
0x180265414  nop
0x180265415  add     rsp, 40h
0x180265419  pop     rbp
0x18026541a  retn
```
