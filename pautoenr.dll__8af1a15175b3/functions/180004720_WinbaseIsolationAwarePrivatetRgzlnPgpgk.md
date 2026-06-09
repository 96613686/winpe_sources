# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x180004720`
- end: `0x180004968`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `584`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000765c`

## callees

- `0x180004720`
- `0x180007d20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800048bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800048bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004862`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004862`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180004848`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180004848`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180004827`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180004827`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000494f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000494f`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x180004797`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x180004797`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x1800047dd`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x1800047dd`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000495d`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180007ddf`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000495d`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180007ddf`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x1800048a8`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x1800048a8`
- `api-ms-win-core-sidebyside-l1-1-0!FindActCtxSectionStringW` at `0x18000493e`
- `api-ms-win-core-sidebyside-l1-1-0!FindActCtxSectionStringW` at `0x18000493e`

## string_xrefs

- `0x18000492d`: `Comctl32.dll`
- `0x180004948`: `Comctl32.dll`

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
  if ( IsolationAwarePrivateT_SqbjaYRiRY || *(_QWORD *)&WinbaseIsolationAwarePrivateT_UnPgpgk != -1 )
    return 1;
  v0 = 0;
  if ( !QueryActCtxW(0x80000010, &WinbaseIsolationAwarePrivateT_UnPgpgk, 0, 1u, hActCtx, 0x10u, 0) )
    return v0;
  ActCtxW = hActCtx[0];
  if ( hActCtx[0] )
  {
LABEL_6:
    *(_QWORD *)&WinbaseIsolationAwarePrivateT_UnPgpgk = ActCtxW;
    if ( ActivateActCtx(ActCtxW, &Cookie) )
    {
      memset(&pActCtx, 0, sizeof(pActCtx));
      pActCtx.cbSize = 112;
      if ( FindActCtxSectionStringW(0, 0, 2u, L"Comctl32.dll", &pActCtx) )
        LoadLibraryW(L"Comctl32.dll");
      DeactivateActCtx(0, Cookie);
    }
    return 1;
  }
  memset(&pActCtx, 0, 56);
  phModule = 0;
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
        goto LABEL_6;
      LastError = GetLastError();
      if ( LastError - 2 <= 1 || LastError - 1812 <= 3 )
      {
        ActCtxW = 0;
        hActCtx[0] = 0;
        goto LABEL_6;
      }
    }
  }
  return v0;
}

```

## disassembly

```asm
0x180004720  mov     [rsp+arg_0], rbx
0x180004725  push    rdi
0x180004726  sub     rsp, 2F0h
0x18000472d  mov     rax, cs:__security_cookie
0x180004734  xor     rax, rsp
0x180004737  mov     [rsp+2F8h+var_18], rax
0x18000473f  xorps   xmm0, xmm0
0x180004742  movups  xmmword ptr [rsp+2F8h+hActCtx], xmm0
0x180004747  xor     edi, edi
0x180004749  mov     [rsp+2F8h+Cookie], rdi
0x18000474e  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, edi
0x180004754  jnz     loc_1800047EB
0x18000475a  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x180004762  jnz     loc_1800047EB
0x180004768  mov     ebx, edi
0x18000476a  mov     [rsp+2F8h+pcbWrittenOrRequired], rdi; pcbWrittenOrRequired
0x18000476f  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x180004778  lea     rax, [rsp+2F8h+hActCtx]
0x18000477d  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x180004782  mov     r9d, 1; ulInfoClass
0x180004788  xor     r8d, r8d; pvSubInstance
0x18000478b  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x180004792  mov     ecx, 80000010h; dwFlags
0x180004797  call    cs:__imp_QueryActCtxW
0x18000479d  test    eax, eax
0x18000479f  jnz     short loc_1800047C4
0x1800047a1  mov     eax, ebx
0x1800047a3  mov     rcx, [rsp+2F8h+var_18]
0x1800047ab  xor     rcx, rsp; StackCookie
0x1800047ae  call    __security_check_cookie
0x1800047b3  mov     rbx, [rsp+2F8h+arg_0]
0x1800047bb  add     rsp, 2F0h
0x1800047c2  pop     rdi
0x1800047c3  retn
0x1800047c4  mov     rax, [rsp+2F8h+hActCtx]
0x1800047c9  test    rax, rax
0x1800047cc  jz      short loc_1800047F2
0x1800047ce  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x1800047d5  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x1800047da  mov     rcx, rax; hActCtx
0x1800047dd  call    cs:__imp_ActivateActCtx
0x1800047e3  test    eax, eax
0x1800047e5  jnz     loc_1800048E6
0x1800047eb  mov     ebx, 1
0x1800047f0  jmp     short loc_1800047A1
0x1800047f2  xorps   xmm0, xmm0
0x1800047f5  xor     eax, eax
0x1800047f7  movups  xmmword ptr [rsp+2F8h+pActCtx.cbSize], xmm0
0x1800047fc  movups  xmmword ptr [rsp+2F8h+pActCtx.wProcessorArchitecture], xmm0
0x180004801  movups  xmmword ptr [rsp+2F8h+pActCtx.lpResourceName], xmm0
0x180004809  mov     [rsp+2F8h+pActCtx.hModule], rax
0x180004811  mov     [rsp+2F8h+phModule], rdi
0x180004816  lea     r8, [rsp+2F8h+phModule]; phModule
0x18000481b  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x180004822  mov     ecx, 6; dwFlags
0x180004827  call    cs:__imp_GetModuleHandleExW
0x18000482d  test    eax, eax
0x18000482f  jz      loc_1800047A1
0x180004835  mov     r8d, 105h; nSize
0x18000483b  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x180004843  mov     rcx, [rsp+2F8h+phModule]; hModule
0x180004848  call    cs:__imp_GetModuleFileNameW
0x18000484e  test    eax, eax
0x180004850  jz      loc_1800047A1
0x180004856  cmp     eax, 105h
0x18000485b  jb      short loc_18000486D
0x18000485d  mov     ecx, 6Fh ; 'o'; dwErrCode
0x180004862  call    cs:__imp_SetLastError
0x180004868  jmp     loc_1800047A1
0x18000486d  mov     [rsp+2F8h+pActCtx.cbSize], 38h ; '8'
0x180004875  mov     [rsp+2F8h+pActCtx.dwFlags], 88h
0x18000487d  lea     rax, [rsp+2F8h+Filename]
0x180004885  mov     [rsp+2F8h+pActCtx.lpSource], rax
0x18000488a  mov     [rsp+2F8h+pActCtx.lpResourceName], 3
0x180004896  mov     rax, [rsp+2F8h+phModule]
0x18000489b  mov     [rsp+2F8h+pActCtx.hModule], rax
0x1800048a3  lea     rcx, [rsp+2F8h+pActCtx]; pActCtx
0x1800048a8  call    cs:__imp_CreateActCtxW
0x1800048ae  mov     [rsp+2F8h+hActCtx], rax
0x1800048b3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800048b7  jnz     loc_1800047CE
0x1800048bd  call    cs:__imp_GetLastError
0x1800048c3  lea     ecx, [rax-2]
0x1800048c6  cmp     ecx, 1
0x1800048c9  jbe     short loc_1800048D9
0x1800048cb  add     eax, 0FFFFF8ECh
0x1800048d0  cmp     eax, 3
0x1800048d3  ja      loc_1800047A1
0x1800048d9  mov     rax, rdi
0x1800048dc  mov     [rsp+2F8h+hActCtx], rax
0x1800048e1  jmp     loc_1800047CE
0x1800048e6  xorps   xmm0, xmm0
0x1800048e9  movups  xmmword ptr [rsp+2F8h+pActCtx.cbSize], xmm0
0x1800048ee  movups  xmmword ptr [rsp+2F8h+pActCtx.wProcessorArchitecture], xmm0
0x1800048f3  movups  xmmword ptr [rsp+2F8h+pActCtx.lpResourceName], xmm0
0x1800048fb  movups  xmmword ptr [rsp+2F8h+pActCtx.hModule], xmm0
0x180004903  movups  [rsp+2F8h+var_258], xmm0
0x18000490b  movups  [rsp+2F8h+var_248], xmm0
0x180004913  movups  [rsp+2F8h+var_238], xmm0
0x18000491b  mov     [rsp+2F8h+pActCtx.cbSize], 70h ; 'p'
0x180004923  lea     rax, [rsp+2F8h+pActCtx]
0x180004928  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x18000492d  lea     r9, LibFileName; "Comctl32.dll"
0x180004934  xor     edx, edx; lpExtensionGuid
0x180004936  mov     r8d, 2; ulSectionId
0x18000493c  xor     ecx, ecx; dwFlags
0x18000493e  call    cs:__imp_FindActCtxSectionStringW
0x180004944  test    eax, eax
0x180004946  jz      short loc_180004956
0x180004948  lea     rcx, LibFileName; "Comctl32.dll"
0x18000494f  call    cs:__imp_LoadLibraryW
0x180004955  nop
0x180004956  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x18000495b  xor     ecx, ecx; dwFlags
0x18000495d  call    cs:__imp_DeactivateActCtx
0x180004963  jmp     loc_1800047EB
0x180007dd0  push    rbp
0x180007dd2  sub     rsp, 40h
0x180007dd6  mov     rbp, rdx
0x180007dd9  mov     rdx, [rbp+48h]; ulCookie
0x180007ddd  xor     ecx, ecx; dwFlags
0x180007ddf  call    cs:__imp_DeactivateActCtx
0x180007de5  nop
0x180007de6  add     rsp, 40h
0x180007dea  pop     rbp
0x180007deb  retn
```
