# AssetElementNode::LoadKnobsStores(IWpxConfig *)

- ea: `0x180026be4`
- end: `0x180026db4`
- name: `?LoadKnobsStores@AssetElementNode@@AEAAXPEAUIWpxConfig@@@Z`
- size: `464`
- prototype: `void __fastcall(AssetElementNode *__hidden this, struct IWpxConfig *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027d6c`

## callees

- `0x1800090e0`
- `0x180024508`
- `0x180026be4`
- `0x180033334`
- `0x18003586a`
- `0x1800358a0`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026cf4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026d3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026cf4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026d3b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180026c69`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180026c69`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180026d08`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180026d08`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180026d24`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180026d24`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180026c32`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180026caa`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180026c32`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180026caa`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall AssetElementNode::LoadKnobsStores(AssetElementNode *this, struct IWpxConfig *a2)
{
  PCWSTR *WindowsProvisioningFolderPath; // rdi
  HRESULT v4; // eax
  WCHAR *FirstFileW; // rbx
  const char *v6; // r9
  HRESULT v7; // eax
  int v8; // eax
  int v9; // [rsp+20h] [rbp-E0h]
  PWSTR v10; // [rsp+30h] [rbp-D0h] BYREF
  PWSTR ppszPathOut[3]; // [rsp+38h] [rbp-C8h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  WindowsProvisioningFolderPath = (PCWSTR *)ProvisioningPaths::GetWindowsProvisioningFolderPath();
  ppszPathOut[0] = 0;
  v4 = PathAllocCombine(*WindowsProvisioningFolderPath, L"*Provisioning.dat", 1u, ppszPathOut);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x89,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetelementnode.cpp",
      (const char *)(unsigned int)v4,
      v9);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = (WCHAR *)FindFirstFileW(ppszPathOut[0], &FindFileData);
  ppszPathOut[1] = FirstFileW;
  if ( FirstFileW == (WCHAR *)-1LL )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x8D,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetelementnode.cpp",
      v6);
  do
  {
    v10 = 0;
    v7 = PathAllocCombine(*WindowsProvisioningFolderPath, FindFileData.cFileName, 1u, &v10);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x91,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetelementnode.cpp",
        (const char *)(unsigned int)v7,
        v9);
    v8 = (**(__int64 (__fastcall ***)(struct IWpxConfig *, PWSTR, __int64))a2)(a2, v10, 1);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x92,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetelementnode.cpp",
        (const char *)(unsigned int)v8,
        v9);
    if ( v10 )
      LocalFree(v10);
  }
  while ( FindNextFileW(FirstFileW, &FindFileData) );
  if ( FirstFileW )
    FindClose(FirstFileW);
  if ( ppszPathOut[0] )
    LocalFree(ppszPathOut[0]);
}

```

## disassembly

```asm
0x180026be4  push    rbp
0x180026be6  push    rbx
0x180026be7  push    rsi
0x180026be8  push    rdi
0x180026be9  lea     rbp, [rsp-1B8h]
0x180026bf1  sub     rsp, 2B8h
0x180026bf8  mov     rax, cs:__security_cookie
0x180026bff  xor     rax, rsp
0x180026c02  mov     [rbp+1D0h+var_30], rax
0x180026c09  mov     rsi, rdx
0x180026c0c  call    ?GetWindowsProvisioningFolderPath@ProvisioningPaths@@SAAEBVexpanded_wstring@@XZ; ProvisioningPaths::GetWindowsProvisioningFolderPath(void)
0x180026c11  mov     rdi, rax
0x180026c14  mov     [rsp+2D0h+ppszPathOut], 0
0x180026c1d  lea     r9, [rsp+2D0h+ppszPathOut]; ppszPathOut
0x180026c22  mov     r8d, 1; dwFlags
0x180026c28  lea     rdx, pszMore; "*Provisioning.dat"
0x180026c2f  mov     rcx, [rax]; pszPathIn
0x180026c32  call    cs:__imp_PathAllocCombine
0x180026c39  nop     dword ptr [rax+rax+00h]
0x180026c3e  mov     rcx, [rbp+1D8h]; this
0x180026c45  test    eax, eax
0x180026c47  js      loc_180026D8D
0x180026c4d  xor     edx, edx; Val
0x180026c4f  mov     r8d, 250h; Size
0x180026c55  lea     rcx, [rsp+2D0h+FindFileData]; void *
0x180026c5a  call    memset_0
0x180026c5f  lea     rdx, [rsp+2D0h+FindFileData]; lpFindFileData
0x180026c64  mov     rcx, [rsp+2D0h+ppszPathOut]; lpFileName
0x180026c69  call    cs:__imp_FindFirstFileW
0x180026c70  nop     dword ptr [rax+rax+00h]
0x180026c75  mov     rbx, rax
0x180026c78  mov     [rsp+2D0h+var_290], rax
0x180026c7d  mov     rcx, [rbp+1D8h]; this
0x180026c84  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180026c88  jz      loc_180026DA2
0x180026c8e  mov     [rsp+2D0h+var_2A0], 0
0x180026c97  lea     r9, [rsp+2D0h+var_2A0]; ppszPathOut
0x180026c9c  mov     r8d, 1; dwFlags
0x180026ca2  lea     rdx, [rsp+2D0h+FindFileData.cFileName]; pszMore
0x180026ca7  mov     rcx, [rdi]; pszPathIn
0x180026caa  call    cs:__imp_PathAllocCombine
0x180026cb1  nop     dword ptr [rax+rax+00h]
0x180026cb6  mov     rcx, [rbp+1D8h]; this
0x180026cbd  test    eax, eax
0x180026cbf  js      loc_180026D78
0x180026cc5  mov     rax, [rsi]
0x180026cc8  xor     r9d, r9d
0x180026ccb  lea     r8d, [r9+1]
0x180026ccf  mov     rdx, [rsp+2D0h+var_2A0]
0x180026cd4  mov     rcx, rsi
0x180026cd7  mov     rax, [rax]
0x180026cda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026cdf  mov     rcx, [rbp+1D8h]; this
0x180026ce6  test    eax, eax
0x180026ce8  js      short loc_180026D63
0x180026cea  mov     rcx, [rsp+2D0h+var_2A0]; hMem
0x180026cef  test    rcx, rcx
0x180026cf2  jz      short loc_180026D00
0x180026cf4  call    cs:__imp_LocalFree
0x180026cfb  nop     dword ptr [rax+rax+00h]
0x180026d00  lea     rdx, [rsp+2D0h+FindFileData]; lpFindFileData
0x180026d05  mov     rcx, rbx; hFindFile
0x180026d08  call    cs:__imp_FindNextFileW
0x180026d0f  nop     dword ptr [rax+rax+00h]
0x180026d14  test    eax, eax
0x180026d16  jnz     loc_180026C8E
0x180026d1c  test    rbx, rbx
0x180026d1f  jz      short loc_180026D31
0x180026d21  mov     rcx, rbx; hFindFile
0x180026d24  call    cs:__imp_FindClose
0x180026d2b  nop     dword ptr [rax+rax+00h]
0x180026d30  nop
0x180026d31  mov     rcx, [rsp+2D0h+ppszPathOut]; hMem
0x180026d36  test    rcx, rcx
0x180026d39  jz      short loc_180026D47
0x180026d3b  call    cs:__imp_LocalFree
0x180026d42  nop     dword ptr [rax+rax+00h]
0x180026d47  mov     rcx, [rbp+1D0h+var_30]
0x180026d4e  xor     rcx, rsp; StackCookie
0x180026d51  call    __security_check_cookie
0x180026d56  add     rsp, 2B8h
0x180026d5d  pop     rdi
0x180026d5e  pop     rsi
0x180026d5f  pop     rbx
0x180026d60  pop     rbp
0x180026d61  retn
0x180026d63  mov     r9d, eax; char *
0x180026d66  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x180026d6d  mov     edx, 92h; void *
0x180026d72  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180026d78  mov     r9d, eax; char *
0x180026d7b  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x180026d82  mov     edx, 91h; void *
0x180026d87  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180026d8d  mov     r9d, eax; char *
0x180026d90  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x180026d97  mov     edx, 89h; void *
0x180026d9c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180026da2  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x180026da9  mov     edx, 8Dh; void *
0x180026dae  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
