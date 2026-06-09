# ClRtlCleanupNode

- ea: `0x1800a001c`
- end: `0x1800a011e`
- name: `ClRtlCleanupNode`
- size: `258`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003359c`
- `0x1800384b4`
- `0x1800386a0`

## callees

- `0x1800a001c`
- `0x1800b5010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800a010b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800a010b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800a0037`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800a0037`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x1800a00ca`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x1800a00ca`

## pseudocode

```c
__int64 __fastcall ClRtlCleanupNode(WCHAR *a1, __int64 a2, unsigned int a3, unsigned int a4)
{
  unsigned int v7; // eax
  unsigned int v8; // edi
  HRESULT v9; // esi
  COSERVERINFO *p_pServerInfo; // r9
  IUnknown *pItf; // rbx
  MULTI_QI pResults; // [rsp+30h] [rbp-68h] BYREF
  COSERVERINFO pServerInfo; // [rsp+48h] [rbp-50h] BYREF

  v7 = CoInitializeEx(0, 4u);
  v8 = v7;
  if ( v7 == -2147417850 || v7 <= 1 )
  {
    pResults.pItf = 0;
    pResults.hr = 0;
    pResults.pIID = &IID_IClusterCleanup;
    memset(&pServerInfo, 0, sizeof(pServerInfo));
    if ( a1 )
    {
      p_pServerInfo = &pServerInfo;
      pServerInfo.pwszName = a1;
      pServerInfo.pAuthInfo = 0;
      pServerInfo.dwReserved2 = 0;
    }
    else
    {
      p_pServerInfo = 0;
    }
    v9 = CoCreateInstanceEx(&CLSID_ClusterCleanup, 0, a1 != 0 ? 16 : 4, p_pServerInfo, 1u, &pResults);
    if ( v9 >= 0 )
    {
      pItf = pResults.pItf;
      v9 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, _QWORD, _QWORD))pResults.pItf->lpVtbl[1].QueryInterface)(
             pResults.pItf,
             0,
             a3,
             a4);
      ((void (__fastcall *)(IUnknown *))pItf->lpVtbl->Release)(pItf);
    }
    if ( v8 != -2147417850 )
      CoUninitialize();
  }
  else
  {
    return v7;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800a001c  push    rbx
0x1800a001e  push    rbp
0x1800a001f  push    rsi
0x1800a0020  push    rdi
0x1800a0021  push    r14
0x1800a0023  sub     rsp, 70h
0x1800a0027  mov     rbx, rcx
0x1800a002a  mov     edx, 4; dwCoInit
0x1800a002f  xor     ecx, ecx; pvReserved
0x1800a0031  mov     ebp, r9d
0x1800a0034  mov     r14d, r8d
0x1800a0037  call    cs:__imp_CoInitializeEx
0x1800a003d  mov     edi, eax
0x1800a003f  cmp     eax, 80010106h
0x1800a0044  jz      short loc_1800A0052
0x1800a0046  cmp     eax, 1
0x1800a0049  jbe     short loc_1800A0052
0x1800a004b  mov     esi, eax
0x1800a004d  jmp     loc_1800A0111
0x1800a0052  mov     [rsp+98h+var_68.pItf], 0
0x1800a005b  xorps   xmm0, xmm0
0x1800a005e  mov     [rsp+98h+var_68.hr], 0
0x1800a0066  lea     rax, IID_IClusterCleanup
0x1800a006d  mov     [rsp+98h+var_68.pIID], rax
0x1800a0072  movups  xmmword ptr [rsp+98h+pServerInfo.dwReserved1], xmm0
0x1800a0077  movups  xmmword ptr [rsp+98h+pServerInfo.pAuthInfo], xmm0
0x1800a007c  test    rbx, rbx
0x1800a007f  jnz     short loc_1800A0086
0x1800a0081  xor     r9d, r9d
0x1800a0084  jmp     short loc_1800A00A1
0x1800a0086  lea     r9, [rsp+98h+pServerInfo]; pServerInfo
0x1800a008b  mov     [rsp+98h+pServerInfo.pwszName], rbx
0x1800a0090  mov     [rsp+98h+pServerInfo.pAuthInfo], 0
0x1800a0099  mov     [rsp+98h+pServerInfo.dwReserved2], 0
0x1800a00a1  lea     rax, [rsp+98h+var_68]
0x1800a00a6  neg     rbx
0x1800a00a9  mov     [rsp+98h+pResults], rax; pResults
0x1800a00ae  lea     rcx, CLSID_ClusterCleanup; Clsid
0x1800a00b5  sbb     r8d, r8d
0x1800a00b8  mov     [rsp+98h+dwCount], 1; dwCount
0x1800a00c0  and     r8d, 0Ch
0x1800a00c4  xor     edx, edx; punkOuter
0x1800a00c6  add     r8d, 4; dwClsCtx
0x1800a00ca  call    cs:__imp_CoCreateInstanceEx
0x1800a00d0  mov     esi, eax
0x1800a00d2  test    eax, eax
0x1800a00d4  js      short loc_1800A0103
0x1800a00d6  mov     rbx, [rsp+98h+var_68.pItf]
0x1800a00db  mov     r9d, ebp
0x1800a00de  mov     r8d, r14d
0x1800a00e1  xor     edx, edx
0x1800a00e3  mov     rcx, rbx
0x1800a00e6  mov     rax, [rbx]
0x1800a00e9  mov     rax, [rax+18h]
0x1800a00ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a00f2  mov     esi, eax
0x1800a00f4  mov     rax, [rbx]
0x1800a00f7  mov     rcx, rbx
0x1800a00fa  mov     rax, [rax+10h]
0x1800a00fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0103  cmp     edi, 80010106h
0x1800a0109  jz      short loc_1800A0111
0x1800a010b  call    cs:__imp_CoUninitialize
0x1800a0111  mov     eax, esi
0x1800a0113  add     rsp, 70h
0x1800a0117  pop     r14
0x1800a0119  pop     rdi
0x1800a011a  pop     rsi
0x1800a011b  pop     rbp
0x1800a011c  pop     rbx
0x1800a011d  retn
```
