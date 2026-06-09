# CError::PostError(long,ulong)

- ea: `0x18002e554`
- end: `0x18002e769`
- name: `?PostError@CError@@QEAAXJK@Z`
- size: `533`
- prototype: `void(CError *__hidden this, int, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180022240`
- `0x18002e770`

## callees

- `0x180002770`
- `0x18002e478`
- `0x18002e554`
- `0x18002f0e0`
- `0x18002f1a0`
- `0x180031010`

## import_xrefs

- `msvcrt!mbstowcs` at `0x18002e655`
- `msvcrt!mbstowcs` at `0x18002e655`
- `ole32!CoCreateInstance` at `0x18002e6c3`
- `ole32!CoCreateInstance` at `0x18002e6c3`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18002e696`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18002e696`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002e727`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002e727`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x18002e5bf`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x18002e5bf`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall CError::PostError(CError *this, int a2, unsigned int a3, unsigned int a4)
{
  char *v7; // rsi
  const char *v8; // rdx
  __int64 v9; // rax
  size_t v10; // r8
  unsigned __int64 v11; // rcx
  __int64 v12; // rax
  void *v13; // rsp
  ICreateErrorInfo **p_pperrinfo; // rbx
  __int64 v15; // [rsp+0h] [rbp-40h] BYREF
  ICreateErrorInfo *pperrinfo; // [rsp+40h] [rbp+0h] BYREF
  IErrorInfo *perrinfo; // [rsp+48h] [rbp+8h] BYREF
  __int64 v18; // [rsp+50h] [rbp+10h] BYREF
  _DWORD v19[2]; // [rsp+58h] [rbp+18h] BYREF
  __int128 v20; // [rsp+60h] [rbp+20h]
  __int128 v21; // [rsp+70h] [rbp+30h] BYREF
  int v22; // [rsp+80h] [rbp+40h]

  pperrinfo = 0;
  perrinfo = 0;
  v18 = 0;
  if ( *((_DWORD *)this + 1033) )
    goto LABEL_16;
  *((_DWORD *)this + 1033) = 1;
  v7 = (char *)this + 32;
  CError::LoadDescription(this, a3, (unsigned __int16 *)this + 16, a4);
  if ( CreateErrorInfo(&pperrinfo) < 0 )
    goto LABEL_14;
  v20 = *((_OWORD *)this + 275);
  v22 = 0;
  v19[1] = a3;
  v19[0] = a2;
  v21 = *((_OWORD *)this + 1);
  ((void (__fastcall *)(ICreateErrorInfo *, __int128 *))pperrinfo->lpVtbl->SetGUID)(pperrinfo, &v21);
  v8 = (const char *)*((_QWORD *)this + 552);
  v9 = -1;
  do
    ++v9;
  while ( v8[v9] );
  v10 = (unsigned int)(v9 + 1);
  v11 = 2LL * (unsigned int)(v9 + 2);
  v12 = v11 + 15;
  if ( v11 + 15 < v11 )
    v12 = 0xFFFFFFFFFFFFFF0LL;
  v13 = alloca(v12 & 0xFFFFFFFFFFFFFFF0uLL);
  p_pperrinfo = &pperrinfo;
  if ( &v15 == (__int64 *)-64LL )
    p_pperrinfo = (ICreateErrorInfo **)&strIn;
  else
    mbstowcs((wchar_t *)&pperrinfo, v8, v10);
  ((void (__fastcall *)(ICreateErrorInfo *, ICreateErrorInfo **))pperrinfo->lpVtbl->SetSource)(pperrinfo, p_pperrinfo);
  ((void (__fastcall *)(ICreateErrorInfo *, char *))pperrinfo->lpVtbl->SetDescription)(pperrinfo, v7);
  if ( !GetErrorInfo(0, &perrinfo)
    || CoCreateInstance(&CLSID_EXTENDEDERRORINFO, 0, 1u, &IID_IErrorInfo, (LPVOID *)&perrinfo) >= 0 )
  {
    if ( ((__int64 (__fastcall *)(IErrorInfo *, GUID *, __int64 *))perrinfo->lpVtbl->QueryInterface)(
           perrinfo,
           &IID_IErrorRecords,
           &v18) >= 0 )
      (*(void (__fastcall **)(__int64, _DWORD *, _QWORD, _QWORD, ICreateErrorInfo *, _DWORD))(*(_QWORD *)v18 + 24LL))(
        v18,
        v19,
        0,
        0,
        pperrinfo,
        0);
LABEL_14:
    if ( perrinfo )
      SetErrorInfo(0, perrinfo);
  }
LABEL_16:
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v18);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&perrinfo);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&pperrinfo);
}

```

## disassembly

```asm
0x18002e554  push    rbp
0x18002e556  push    rbx
0x18002e557  push    rsi
0x18002e558  push    rdi
0x18002e559  push    r14
0x18002e55b  sub     rsp, 90h
0x18002e562  lea     rbp, [rsp+40h]
0x18002e567  mov     rax, cs:__security_cookie
0x18002e56e  xor     rax, rbp
0x18002e571  mov     [rbp+70h+var_28], rax
0x18002e575  mov     edi, r8d
0x18002e578  mov     r14d, edx
0x18002e57b  mov     rbx, rcx
0x18002e57e  mov     [rbp+70h+pperrinfo], 0
0x18002e586  mov     [rbp+70h+perrinfo], 0
0x18002e58e  mov     [rbp+70h+var_60], 0
0x18002e596  cmp     dword ptr [rcx+1024h], 0
0x18002e59d  jnz     loc_18002E734
0x18002e5a3  mov     dword ptr [rcx+1024h], 1
0x18002e5ad  lea     rsi, [rcx+20h]
0x18002e5b1  mov     r8, rsi; unsigned __int16 *
0x18002e5b4  mov     edx, edi; unsigned int
0x18002e5b6  call    ?LoadDescription@CError@@IEAAXKPEAGK@Z; CError::LoadDescription(ulong,ushort *,ulong)
0x18002e5bb  lea     rcx, [rbp+70h+pperrinfo]; pperrinfo
0x18002e5bf  call    cs:__imp_CreateErrorInfo
0x18002e5c6  nop     dword ptr [rax+rax+00h]
0x18002e5cb  test    eax, eax
0x18002e5cd  js      loc_18002E71C
0x18002e5d3  movups  xmm0, xmmword ptr [rbx+1130h]
0x18002e5da  movdqu  [rbp+70h+var_50], xmm0
0x18002e5df  mov     [rbp+70h+var_30], 0
0x18002e5e6  mov     [rbp+70h+var_54], edi
0x18002e5e9  mov     [rbp+70h+var_58], r14d
0x18002e5ed  movups  xmm0, xmmword ptr [rbx+10h]
0x18002e5f1  movdqu  [rbp+70h+var_40], xmm0
0x18002e5f6  mov     rcx, [rbp+70h+pperrinfo]
0x18002e5fa  mov     rax, [rcx]
0x18002e5fd  lea     rdx, [rbp+70h+var_40]
0x18002e601  mov     rax, [rax+18h]
0x18002e605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e60a  mov     rdx, [rbx+1140h]
0x18002e611  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002e615  inc     rax
0x18002e618  cmp     byte ptr [rdx+rax], 0
0x18002e61c  jnz     short loc_18002E615
0x18002e61e  lea     r8d, [rax+1]
0x18002e622  lea     ecx, [r8+1]
0x18002e626  add     rcx, rcx
0x18002e629  lea     rax, [rcx+0Fh]
0x18002e62d  cmp     rax, rcx
0x18002e630  ja      short loc_18002E63C
0x18002e632  mov     rax, 0FFFFFFFFFFFFFF0h
0x18002e63c  and     rax, 0FFFFFFFFFFFFFFF0h
0x18002e640  call    _alloca_probe
0x18002e645  sub     rsp, rax
0x18002e648  lea     rbx, [rsp+0B0h+pperrinfo]
0x18002e64d  test    rbx, rbx
0x18002e650  jz      short loc_18002E663
0x18002e652  mov     rcx, rbx; Dest
0x18002e655  call    cs:__imp_mbstowcs
0x18002e65c  nop     dword ptr [rax+rax+00h]
0x18002e661  jmp     short loc_18002E66A
0x18002e663  lea     rbx, strIn
0x18002e66a  mov     rcx, [rbp+70h+pperrinfo]
0x18002e66e  mov     rax, [rcx]
0x18002e671  mov     rdx, rbx
0x18002e674  mov     rax, [rax+20h]
0x18002e678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e67d  mov     rcx, [rbp+70h+pperrinfo]
0x18002e681  mov     rax, [rcx]
0x18002e684  mov     rdx, rsi
0x18002e687  mov     rax, [rax+28h]
0x18002e68b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e690  lea     rdx, [rbp+70h+perrinfo]; pperrinfo
0x18002e694  xor     ecx, ecx; dwReserved
0x18002e696  call    cs:__imp_GetErrorInfo
0x18002e69d  nop     dword ptr [rax+rax+00h]
0x18002e6a2  test    eax, eax
0x18002e6a4  jz      short loc_18002E6D3
0x18002e6a6  lea     rax, [rbp+70h+perrinfo]
0x18002e6aa  mov     [rsp+0B0h+ppv], rax; ppv
0x18002e6af  lea     r9, IID_IErrorInfo; riid
0x18002e6b6  xor     edx, edx; pUnkOuter
0x18002e6b8  lea     r8d, [rdx+1]; dwClsContext
0x18002e6bc  lea     rcx, CLSID_EXTENDEDERRORINFO; rclsid
0x18002e6c3  call    cs:__imp_CoCreateInstance
0x18002e6ca  nop     dword ptr [rax+rax+00h]
0x18002e6cf  test    eax, eax
0x18002e6d1  js      short loc_18002E734
0x18002e6d3  mov     rcx, [rbp+70h+perrinfo]
0x18002e6d7  mov     rax, [rcx]
0x18002e6da  lea     r8, [rbp+70h+var_60]
0x18002e6de  lea     rdx, IID_IErrorRecords
0x18002e6e5  mov     rax, [rax]
0x18002e6e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e6ed  test    eax, eax
0x18002e6ef  js      short loc_18002E71C
0x18002e6f1  mov     rcx, [rbp+70h+var_60]
0x18002e6f5  mov     rax, [rcx]
0x18002e6f8  mov     [rsp+0B0h+var_88], 0
0x18002e700  mov     rdx, [rbp+70h+pperrinfo]
0x18002e704  mov     [rsp+0B0h+ppv], rdx
0x18002e709  xor     r9d, r9d
0x18002e70c  xor     r8d, r8d
0x18002e70f  lea     rdx, [rbp+70h+var_58]
0x18002e713  mov     rax, [rax+18h]
0x18002e717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e71c  mov     rdx, [rbp+70h+perrinfo]; perrinfo
0x18002e720  test    rdx, rdx
0x18002e723  jz      short loc_18002E734
0x18002e725  xor     ecx, ecx; dwReserved
0x18002e727  call    cs:__imp_SetErrorInfo
0x18002e72e  nop     dword ptr [rax+rax+00h]
0x18002e733  nop
0x18002e734  lea     rcx, [rbp+70h+var_60]
0x18002e738  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18002e73d  nop
0x18002e73e  lea     rcx, [rbp+70h+perrinfo]
0x18002e742  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18002e747  nop
0x18002e748  lea     rcx, [rbp+70h+pperrinfo]
0x18002e74c  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x18002e751  mov     rcx, [rbp+70h+var_28]
0x18002e755  xor     rcx, rbp; StackCookie
0x18002e758  call    __security_check_cookie
0x18002e75d  lea     rsp, [rbp+50h]
0x18002e761  pop     r14
0x18002e763  pop     rdi
0x18002e764  pop     rsi
0x18002e765  pop     rbx
0x18002e766  pop     rbp
0x18002e767  retn
```
