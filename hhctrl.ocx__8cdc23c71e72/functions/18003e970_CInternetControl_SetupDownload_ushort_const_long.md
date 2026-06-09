# CInternetControl::SetupDownload(ushort const *,long)

- ea: `0x18003e970`
- end: `0x18003eae9`
- name: `?SetupDownload@CInternetControl@@QEAAJPEBGJ@Z`
- size: `377`
- prototype: `__int64 __fastcall(CInternetControl *__hidden this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180033690`

## callees

- `0x180001728`
- `0x18003e970`
- `0x180078010`

## import_xrefs

- `ole32!CreateBindCtx` at `0x18003e9b9`
- `ole32!CreateBindCtx` at `0x18003e9b9`
- `urlmon!RegisterBindStatusCallback` at `0x18003ea4c`
- `urlmon!RegisterBindStatusCallback` at `0x18003ea4c`
- `urlmon!CreateURLMoniker` at `0x18003e99f`
- `urlmon!CreateURLMoniker` at `0x18003e99f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CInternetControl::SetupDownload(struct IMonikerVtbl *this, const unsigned __int16 *a2)
{
  HRESULT URLMoniker; // edi
  IBindStatusCallback *v5; // rbx
  IMoniker *v6; // rax
  LPMONIKER ppmk[2]; // [rsp+30h] [rbp-10h] BYREF
  LPBC ppbc; // [rsp+68h] [rbp+28h] BYREF
  __int64 v9; // [rsp+78h] [rbp+38h] BYREF

  if ( !a2 )
    return 2147942487LL;
  ppmk[0] = 0;
  URLMoniker = CreateURLMoniker(0, a2, ppmk);
  ppbc = 0;
  if ( URLMoniker >= 0 )
    URLMoniker = CreateBindCtx(0, &ppbc);
  v5 = 0;
  if ( URLMoniker < 0 )
    goto LABEL_11;
  v6 = (IMoniker *)operator new(0x38u);
  v5 = (IBindStatusCallback *)v6;
  ppmk[1] = v6;
  if ( v6 )
  {
    v6->lpVtbl = (struct IMonikerVtbl *)&CDownloadSink::`vftable';
    v6[2].lpVtbl = this;
    (*((void (__fastcall **)(HRESULT (__stdcall **)(IMoniker *, IStream *, BOOL)))this->Save + 1))(&this->Save);
    LODWORD(v5[3].lpVtbl) = 1;
    v5[1].lpVtbl = 0;
    v5[4].lpVtbl = 0;
    LODWORD(v5[5].lpVtbl) = 0;
    v5[6].lpVtbl = 0;
  }
  else
  {
    v5 = 0;
  }
  if ( v5 )
  {
    ((void (__fastcall *)(IBindStatusCallback *))v5->lpVtbl->AddRef)(v5);
    URLMoniker = RegisterBindStatusCallback(ppbc, v5, 0, 0);
LABEL_11:
    v9 = 0;
    if ( URLMoniker >= 0 )
    {
      URLMoniker = ((__int64 (__fastcall *)(LPMONIKER, LPBC, _QWORD, GUID *, __int64 *))ppmk[0]->lpVtbl->BindToStorage)(
                     ppmk[0],
                     ppbc,
                     0,
                     &IID_IStream,
                     &v9);
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    goto LABEL_14;
  }
  URLMoniker = -2147024882;
  v9 = 0;
LABEL_14:
  if ( ppbc )
    ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
  if ( URLMoniker < 0 )
  {
    if ( v5 )
      ((void (__fastcall *)(IBindStatusCallback *))v5->lpVtbl->Release)(v5);
  }
  return (unsigned int)URLMoniker;
}

```

## disassembly

```asm
0x18003e970  mov     [rsp-18h+arg_0], rbx
0x18003e975  push    rbp
0x18003e976  push    rsi
0x18003e977  push    rdi
0x18003e978  mov     rbp, rsp
0x18003e97b  sub     rsp, 40h
0x18003e97f  mov     rsi, rcx
0x18003e982  test    rdx, rdx
0x18003e985  jnz     short loc_18003E991
0x18003e987  mov     eax, 80070057h
0x18003e98c  jmp     loc_18003EACD
0x18003e991  mov     [rbp+ppmk], 0
0x18003e999  lea     r8, [rbp+ppmk]; ppmk
0x18003e99d  xor     ecx, ecx; pMkCtx
0x18003e99f  call    cs:__imp_CreateURLMoniker
0x18003e9a5  mov     edi, eax
0x18003e9a7  mov     [rbp+ppbc], 0
0x18003e9af  test    eax, eax
0x18003e9b1  js      short loc_18003E9C1
0x18003e9b3  lea     rdx, [rbp+ppbc]; ppbc
0x18003e9b7  xor     ecx, ecx; reserved
0x18003e9b9  call    cs:__imp_CreateBindCtx
0x18003e9bf  mov     edi, eax
0x18003e9c1  xor     ebx, ebx
0x18003e9c3  test    edi, edi
0x18003e9c5  js      loc_18003EA54
0x18003e9cb  lea     ecx, [rbx+38h]; Size
0x18003e9ce  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003e9d3  mov     rbx, rax
0x18003e9d6  mov     [rbp+var_8], rax
0x18003e9da  test    rax, rax
0x18003e9dd  jz      short loc_18003EA25
0x18003e9df  lea     rax, ??_7CDownloadSink@@6B@; const CDownloadSink::`vftable'
0x18003e9e6  mov     [rbx], rax
0x18003e9e9  mov     [rbx+10h], rsi
0x18003e9ed  lea     rcx, [rsi+30h]
0x18003e9f1  mov     rax, [rcx]
0x18003e9f4  mov     rax, [rax+8]
0x18003e9f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e9fd  mov     dword ptr [rbx+18h], 1
0x18003ea04  mov     qword ptr [rbx+8], 0
0x18003ea0c  mov     qword ptr [rbx+20h], 0
0x18003ea14  mov     dword ptr [rbx+28h], 0
0x18003ea1b  mov     qword ptr [rbx+30h], 0
0x18003ea23  jmp     short loc_18003EA27
0x18003ea25  xor     ebx, ebx
0x18003ea27  test    rbx, rbx
0x18003ea2a  jz      loc_18003EADA
0x18003ea30  mov     rax, [rbx]
0x18003ea33  mov     rcx, rbx
0x18003ea36  mov     rax, [rax+8]
0x18003ea3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ea3f  xor     r9d, r9d; dwReserved
0x18003ea42  xor     r8d, r8d; ppBSCBPrev
0x18003ea45  mov     rdx, rbx; pBSCb
0x18003ea48  mov     rcx, [rbp+ppbc]; pBC
0x18003ea4c  call    cs:__imp_RegisterBindStatusCallback
0x18003ea52  mov     edi, eax
0x18003ea54  mov     [rbp+arg_18], 0
0x18003ea5c  test    edi, edi
0x18003ea5e  js      short loc_18003EA9E
0x18003ea60  mov     rcx, [rbp+ppmk]
0x18003ea64  mov     rax, [rcx]
0x18003ea67  lea     rdx, [rbp+arg_18]
0x18003ea6b  mov     [rsp+40h+var_20], rdx
0x18003ea70  lea     r9, IID_IStream
0x18003ea77  xor     r8d, r8d
0x18003ea7a  mov     rdx, [rbp+ppbc]
0x18003ea7e  mov     rax, [rax+48h]
0x18003ea82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ea87  mov     edi, eax
0x18003ea89  mov     rcx, [rbp+arg_18]
0x18003ea8d  test    rcx, rcx
0x18003ea90  jz      short loc_18003EA9E
0x18003ea92  mov     rax, [rcx]
0x18003ea95  mov     rax, [rax+10h]
0x18003ea99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ea9e  mov     rcx, [rbp+ppbc]
0x18003eaa2  test    rcx, rcx
0x18003eaa5  jz      short loc_18003EAB3
0x18003eaa7  mov     rax, [rcx]
0x18003eaaa  mov     rax, [rax+10h]
0x18003eaae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eab3  test    edi, edi
0x18003eab5  jns     short loc_18003EACB
0x18003eab7  test    rbx, rbx
0x18003eaba  jz      short loc_18003EACB
0x18003eabc  mov     rax, [rbx]
0x18003eabf  mov     rcx, rbx
0x18003eac2  mov     rax, [rax+10h]
0x18003eac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eacb  mov     eax, edi
0x18003eacd  mov     rbx, [rsp+40h+arg_0]
0x18003ead2  add     rsp, 40h
0x18003ead6  pop     rdi
0x18003ead7  pop     rsi
0x18003ead8  pop     rbp
0x18003ead9  retn
0x18003eada  mov     edi, 8007000Eh
0x18003eadf  mov     [rbp+arg_18], 0
0x18003eae7  jmp     short loc_18003EA9E
```
