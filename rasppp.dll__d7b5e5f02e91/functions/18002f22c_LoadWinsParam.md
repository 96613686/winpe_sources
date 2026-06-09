# LoadWinsParam

- ea: `0x18002f22c`
- end: `0x18002f479`
- name: `LoadWinsParam`
- size: `589`
- prototype: `__int64 __fastcall(HKEY hKey, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002ebd0`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180014b1c`
- `0x18002b0dc`
- `0x18002f22c`
- `0x18002fab4`
- `0x18003230c`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f416`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f440`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f416`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f440`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002f2da`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002f2da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f2ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f2ee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f39e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002f39e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f42c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002f42c`

## string_xrefs

- `0x18002f3ce`: `RegOpenKeyEx(%ws) failed and returned %d`
- `0x18002f3e7`: `RegOpenKeyEx(%ws) failed and returned %d`

## pseudocode

```c
__int64 __fastcall LoadWinsParam(HKEY hKey, __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  size_t v6; // rbx
  wchar_t *v7; // rsi
  DWORD LastError; // eax
  unsigned int v9; // ebx
  unsigned int v10; // eax
  HKEY hKeya; // [rsp+30h] [rbp-D0h] BYREF
  int v13; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v14[2044]; // [rsp+44h] [rbp-BCh] BYREF

  hKeya = 0;
  v13 = 0;
  memset_0(v14, 0, sizeof(v14));
  if ( gIsIphlpEtwTracingAvailable )
  {
    if ( (_QWORD)xmmword_18004D648 )
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gIphlpTemplateFunc)(
        gIphlpEtwContext,
        xmmword_18004D648,
        L"LoadWinsParam");
  }
  else
  {
    TraceHlp("LoadWinsParam");
  }
  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)(*(_QWORD *)(a2 + 8) + 2 * v4) );
  v5 = (unsigned int)(v4 + 7);
  v6 = (unsigned int)v5;
  v7 = (wchar_t *)LocalAlloc(0x40u, 2 * v5);
  if ( v7 )
  {
    StringCchPrintfW(v7, v6, L"%s%s", L"Tcpip_", *(_QWORD *)(a2 + 8));
    v10 = RegOpenKeyExW(hKey, v7, 0, 0x20019u, &hKeya);
    v9 = v10;
    if ( v10 )
    {
      if ( gIsIphlpEtwTracingAvailable )
      {
        if ( qword_18004D640 )
        {
          LOWORD(v13) = 0;
          FormatRRASErrorString((wchar_t *)&v13, L"RegOpenKeyEx(%ws) failed and returned %d", v7, v10);
LABEL_11:
          ((void (__fastcall *)(__int64, __int64, int *))gIphlpTemplateFunc)(gIphlpEtwContext, qword_18004D640, &v13);
        }
      }
      else
      {
        TraceHlp("RegOpenKeyEx(%ws) failed and returned %d");
      }
    }
    else
    {
      RegQueryValueWithAllocW(hKeya, L"NameServerList", 7u, (HLOCAL *)(a2 + 112));
    }
  }
  else
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( gIsIphlpEtwTracingAvailable )
    {
      if ( !qword_18004D640 )
        goto LABEL_19;
      LOWORD(v13) = 0;
      FormatRRASErrorString((wchar_t *)&v13, L"LocalAlloc failed and returned %d", LastError);
      goto LABEL_11;
    }
    TraceHlp("LocalAlloc failed and returned %d");
  }
LABEL_19:
  LocalFree(v7);
  if ( hKeya )
    RegCloseKey(hKeya);
  if ( v9 )
  {
    LocalFree(*(HLOCAL *)(a2 + 112));
    *(_QWORD *)(a2 + 112) = 0;
  }
  return v9;
}

```

## disassembly

```asm
0x18002f22c  mov     [rsp-8+arg_10], rbx
0x18002f231  push    rbp
0x18002f232  push    rsi
0x18002f233  push    rdi
0x18002f234  push    r14
0x18002f236  push    r15
0x18002f238  lea     rbp, [rsp-750h]
0x18002f240  sub     rsp, 850h
0x18002f247  mov     rax, cs:__security_cookie
0x18002f24e  xor     rax, rsp
0x18002f251  mov     [rbp+770h+var_30], rax
0x18002f258  mov     rdi, rdx
0x18002f25b  mov     r14, rcx
0x18002f25e  xor     r15d, r15d
0x18002f261  lea     rcx, [rsp+870h+var_82C]; void *
0x18002f266  xor     edx, edx; Val
0x18002f268  mov     [rsp+870h+hKey], r15
0x18002f26d  mov     r8d, 7FCh; Size
0x18002f273  mov     [rsp+870h+var_830], r15d
0x18002f278  call    memset_0
0x18002f27d  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18002f284  jz      short loc_18002F2AE
0x18002f286  mov     rdx, qword ptr cs:xmmword_18004D648
0x18002f28d  test    rdx, rdx
0x18002f290  jz      short loc_18002F2BA
0x18002f292  mov     rcx, cs:gIphlpEtwContext
0x18002f299  lea     r8, aLoadwinsparam_0; "LoadWinsParam"
0x18002f2a0  mov     rax, cs:gIphlpTemplateFunc
0x18002f2a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f2ac  jmp     short loc_18002F2BA
0x18002f2ae  lea     rcx, aLoadwinsparam; "LoadWinsParam"
0x18002f2b5  call    TraceHlp
0x18002f2ba  mov     rcx, [rdi+8]
0x18002f2be  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002f2c2  inc     rax
0x18002f2c5  cmp     [rcx+rax*2], r15w
0x18002f2ca  jnz     short loc_18002F2C2
0x18002f2cc  add     eax, 7
0x18002f2cf  mov     ecx, 40h ; '@'; uFlags
0x18002f2d4  mov     ebx, eax
0x18002f2d6  lea     rdx, [rax+rax]; uBytes
0x18002f2da  call    cs:__imp_LocalAlloc
0x18002f2e1  nop     dword ptr [rax+rax+00h]
0x18002f2e6  mov     rsi, rax
0x18002f2e9  test    rax, rax
0x18002f2ec  jnz     short loc_18002F363
0x18002f2ee  call    cs:__imp_GetLastError
0x18002f2f5  nop     dword ptr [rax+rax+00h]
0x18002f2fa  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18002f301  mov     ebx, eax
0x18002f303  jz      short loc_18002F350
0x18002f305  cmp     cs:qword_18004D640, r15
0x18002f30c  jz      loc_18002F413
0x18002f312  mov     r8d, eax
0x18002f315  mov     word ptr [rsp+870h+var_830], r15w
0x18002f31b  lea     rdx, aLocalallocFail_1; "LocalAlloc failed and returned %d"
0x18002f322  lea     rcx, [rsp+870h+var_830]
0x18002f327  call    FormatRRASErrorString
0x18002f32c  mov     rdx, cs:qword_18004D640
0x18002f333  lea     r8, [rsp+870h+var_830]
0x18002f338  mov     rcx, cs:gIphlpEtwContext
0x18002f33f  mov     rax, cs:gIphlpTemplateFunc
0x18002f346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f34b  jmp     loc_18002F413
0x18002f350  mov     edx, eax
0x18002f352  lea     rcx, aLocalallocFail; "LocalAlloc failed and returned %d"
0x18002f359  call    TraceHlp
0x18002f35e  jmp     loc_18002F413
0x18002f363  mov     rax, [rdi+8]
0x18002f367  lea     r9, aTcpip; "Tcpip_"
0x18002f36e  lea     r8, aSS_0; "%s%s"
0x18002f375  mov     [rsp+870h+phkResult], rax
0x18002f37a  mov     rdx, rbx; cchDest
0x18002f37d  mov     rcx, rsi; pszDest
0x18002f380  call    StringCchPrintfW
0x18002f385  lea     rax, [rsp+870h+hKey]
0x18002f38a  mov     r9d, 20019h; samDesired
0x18002f390  xor     r8d, r8d; ulOptions
0x18002f393  mov     [rsp+870h+phkResult], rax; phkResult
0x18002f398  mov     rdx, rsi; lpSubKey
0x18002f39b  mov     rcx, r14; hKey
0x18002f39e  call    cs:__imp_RegOpenKeyExW
0x18002f3a5  nop     dword ptr [rax+rax+00h]
0x18002f3aa  mov     ebx, eax
0x18002f3ac  test    eax, eax
0x18002f3ae  jz      short loc_18002F3F8
0x18002f3b0  cmp     cs:gIsIphlpEtwTracingAvailable, r15d
0x18002f3b7  jz      short loc_18002F3E4
0x18002f3b9  cmp     cs:qword_18004D640, r15
0x18002f3c0  jz      short loc_18002F413
0x18002f3c2  mov     r9d, eax
0x18002f3c5  mov     word ptr [rsp+870h+var_830], r15w
0x18002f3cb  mov     r8, rsi
0x18002f3ce  lea     rdx, aRegopenkeyexWs; "RegOpenKeyEx(%ws) failed and returned %"...
0x18002f3d5  lea     rcx, [rsp+870h+var_830]
0x18002f3da  call    FormatRRASErrorString
0x18002f3df  jmp     loc_18002F32C
0x18002f3e4  mov     r8d, eax
0x18002f3e7  lea     rcx, aRegopenkeyexWs_2; "RegOpenKeyEx(%ws) failed and returned %"...
0x18002f3ee  mov     rdx, rsi
0x18002f3f1  call    TraceHlp
0x18002f3f6  jmp     short loc_18002F413
0x18002f3f8  mov     rcx, [rsp+870h+hKey]; hKey
0x18002f3fd  lea     r9, [rdi+70h]
0x18002f401  mov     r8d, 7
0x18002f407  lea     rdx, aNameserverlist; "NameServerList"
0x18002f40e  call    RegQueryValueWithAllocW
0x18002f413  mov     rcx, rsi; hMem
0x18002f416  call    cs:__imp_LocalFree
0x18002f41d  nop     dword ptr [rax+rax+00h]
0x18002f422  mov     rcx, [rsp+870h+hKey]; hKey
0x18002f427  test    rcx, rcx
0x18002f42a  jz      short loc_18002F438
0x18002f42c  call    cs:__imp_RegCloseKey
0x18002f433  nop     dword ptr [rax+rax+00h]
0x18002f438  test    ebx, ebx
0x18002f43a  jz      short loc_18002F450
0x18002f43c  mov     rcx, [rdi+70h]; hMem
0x18002f440  call    cs:__imp_LocalFree
0x18002f447  nop     dword ptr [rax+rax+00h]
0x18002f44c  mov     [rdi+70h], r15
0x18002f450  mov     eax, ebx
0x18002f452  mov     rcx, [rbp+770h+var_30]
0x18002f459  xor     rcx, rsp; StackCookie
0x18002f45c  call    __security_check_cookie
0x18002f461  mov     rbx, [rsp+870h+arg_10]
0x18002f469  add     rsp, 850h
0x18002f470  pop     r15
0x18002f472  pop     r14
0x18002f474  pop     rdi
0x18002f475  pop     rsi
0x18002f476  pop     rbp
0x18002f477  retn
```
