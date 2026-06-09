# CMachineInfoV2::GetMaxD3D11FeatureLevel(void)

- ea: `0x1800b0280`
- end: `0x1800b057d`
- name: `?GetMaxD3D11FeatureLevel@CMachineInfoV2@@CA?AW4D3D_FEATURE_LEVEL@@XZ`
- size: `765`
- prototype: `enum D3D_FEATURE_LEVEL(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800afa40`

## callees

- `0x180008dc0`
- `0x180009f14`
- `0x18001daf0`
- `0x18001dcc8`
- `0x1800b0280`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b02ba`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b02db`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b02ba`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b02db`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b030c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b0320`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b030c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b0320`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0548`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0562`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0548`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0562`

## string_xrefs

- `0x1800b0305`: `CreateDXGIFactory1`
- `0x1800b02b3`: `DXGI.dll`
- `0x1800b0315`: `D3D11CreateDevice`
- `0x1800b02d4`: `D3D11.dll`

## pseudocode

```c
__int64 CMachineInfoV2::GetMaxD3D11FeatureLevel(void)
{
  unsigned int v0; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rdi
  FARPROC v3; // rax
  int (__fastcall *v4)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD, _QWORD, _QWORD); // rsi
  unsigned int i; // edi
  __int64 v6; // rcx
  __int64 v7; // rcx
  signed int v9; // eax
  int v10; // edx
  unsigned int v11; // r8d
  signed int LastError; // eax
  int v13; // edx
  unsigned int v14; // r8d
  __int64 v15; // [rsp+60h] [rbp-A0h] BYREF
  int v16; // [rsp+68h] [rbp-98h] BYREF
  __int64 v17; // [rsp+70h] [rbp-90h] BYREF
  const int *v18; // [rsp+78h] [rbp-88h] BYREF
  HMODULE v19; // [rsp+80h] [rbp-80h]
  const int *v20; // [rsp+88h] [rbp-78h] BYREF
  HMODULE hModule; // [rsp+90h] [rbp-70h]
  _BYTE v22[320]; // [rsp+A0h] [rbp-60h] BYREF

  v0 = 0;
  v20 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  hModule = LoadLibraryExW(L"DXGI.dll", 0, 0x800u);
  Library = LoadLibraryExW(L"D3D11.dll", 0, 0x800u);
  v18 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  v19 = Library;
  v17 = 0;
  if ( !hModule )
    goto LABEL_30;
  if ( !Library )
    goto LABEL_30;
  ProcAddress = GetProcAddress(hModule, "CreateDXGIFactory1");
  v3 = GetProcAddress(v19, "D3D11CreateDevice");
  v4 = (int (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD, _QWORD, _QWORD))v3;
  if ( !ProcAddress
    || !v3
    || ((int (__fastcall *)(GUID *, __int64 *))ProcAddress)(&GUID_50c83a1c_e072_4c48_87b0_3630fa36a6d0, &v17) < 0
    || !v17 )
  {
    goto LABEL_30;
  }
  for ( i = 0; ; ++i )
  {
    v15 = 0;
    memset_0(v22, 0, 0x138u);
    v16 = 0;
    if ( (*(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v17 + 96LL))(v17, i, &v15) < 0 )
      break;
    v6 = v15;
    if ( v15 )
    {
      if ( (*(int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v15 + 80LL))(v15, v22) >= 0 )
      {
        if ( (v22[304] & 2) != 0 )
        {
          if ( v15 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        }
        else if ( v4(v15, 0, 0, 0, qword_1801C1A48, 9, 7, 0, &v16, 0) >= 0 )
        {
          if ( v16 > (int)v0 )
            v0 = v16;
          if ( v15 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        }
        else if ( v15 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        }
        continue;
      }
      v6 = v15;
    }
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
LABEL_30:
  v7 = v17;
  if ( v17 )
  {
    v17 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  v18 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( v19 )
  {
    if ( (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v18) )
    {
      v19 = 0;
      goto LABEL_35;
    }
LABEL_41:
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v13, v14);
    JUMPOUT(0x1800B057CLL);
  }
LABEL_35:
  v20 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( hModule && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v20) )
  {
    v9 = GetLastError();
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v9, v10, v11);
    goto LABEL_41;
  }
  return v0;
}

```

## disassembly

```asm
0x1800b0280  push    rbp
0x1800b0282  push    rbx
0x1800b0283  push    rsi
0x1800b0284  push    rdi
0x1800b0285  push    r15
0x1800b0287  lea     rbp, [rsp-0F0h]
0x1800b028f  sub     rsp, 1F0h
0x1800b0296  mov     rax, cs:__security_cookie
0x1800b029d  xor     rax, rsp
0x1800b02a0  mov     [rbp+110h+var_30], rax
0x1800b02a7  xor     ebx, ebx
0x1800b02a9  mov     edi, 800h
0x1800b02ae  mov     r8d, edi; dwFlags
0x1800b02b1  xor     edx, edx; hFile
0x1800b02b3  lea     rcx, aDxgiDll_0; "DXGI.dll"
0x1800b02ba  call    cs:__imp_LoadLibraryExW
0x1800b02c0  lea     r15, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x1800b02c7  mov     [rbp+110h+var_188], r15
0x1800b02cb  mov     [rbp+110h+hModule], rax
0x1800b02cf  mov     r8d, edi; dwFlags
0x1800b02d2  xor     edx, edx; hFile
0x1800b02d4  lea     rcx, aD3d11Dll; "D3D11.dll"
0x1800b02db  call    cs:__imp_LoadLibraryExW
0x1800b02e1  mov     [rsp+210h+var_198], r15
0x1800b02e6  mov     [rbp+110h+var_190], rax
0x1800b02ea  mov     [rsp+210h+var_1A0], rbx
0x1800b02ef  mov     rcx, [rbp+110h+hModule]; hModule
0x1800b02f3  test    rcx, rcx
0x1800b02f6  jz      loc_1800B04CF
0x1800b02fc  test    rax, rax
0x1800b02ff  jz      loc_1800B04CF
0x1800b0305  lea     rdx, aCreatedxgifact; "CreateDXGIFactory1"
0x1800b030c  call    cs:__imp_GetProcAddress
0x1800b0312  mov     rdi, rax
0x1800b0315  lea     rdx, aD3d11createdev; "D3D11CreateDevice"
0x1800b031c  mov     rcx, [rbp+110h+var_190]; hModule
0x1800b0320  call    cs:__imp_GetProcAddress
0x1800b0326  mov     rsi, rax
0x1800b0329  test    rdi, rdi
0x1800b032c  jz      loc_1800B04CF
0x1800b0332  test    rax, rax
0x1800b0335  jz      loc_1800B04CF
0x1800b033b  mov     rcx, [rsp+210h+var_1A0]
0x1800b0340  test    rcx, rcx
0x1800b0343  jz      short loc_1800B0357
0x1800b0345  mov     [rsp+210h+var_1A0], rbx
0x1800b034a  mov     rax, [rcx]
0x1800b034d  mov     rax, [rax+10h]
0x1800b0351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0356  nop
0x1800b0357  lea     rdx, [rsp+210h+var_1A0]
0x1800b035c  lea     rcx, _GUID_50c83a1c_e072_4c48_87b0_3630fa36a6d0
0x1800b0363  mov     rax, rdi
0x1800b0366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b036b  test    eax, eax
0x1800b036d  js      loc_1800B04CF
0x1800b0373  cmp     [rsp+210h+var_1A0], 0
0x1800b0379  jz      loc_1800B04CF
0x1800b037f  xor     edi, edi
0x1800b0381  mov     [rsp+210h+var_1B0], 0
0x1800b038a  xor     edx, edx; Val
0x1800b038c  mov     r8d, 138h; Size
0x1800b0392  lea     rcx, [rbp+110h+var_170]; void *
0x1800b0396  call    memset_0
0x1800b039b  mov     [rsp+210h+var_1A8], 0
0x1800b03a3  mov     rcx, [rsp+210h+var_1A0]
0x1800b03a8  mov     rax, [rcx]
0x1800b03ab  lea     r8, [rsp+210h+var_1B0]
0x1800b03b0  mov     edx, edi
0x1800b03b2  mov     rax, [rax+60h]
0x1800b03b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b03bb  test    eax, eax
0x1800b03bd  js      loc_1800B04B8
0x1800b03c3  mov     rcx, [rsp+210h+var_1B0]
0x1800b03c8  test    rcx, rcx
0x1800b03cb  jz      loc_1800B049F
0x1800b03d1  mov     rax, [rcx]
0x1800b03d4  lea     rdx, [rbp+110h+var_170]
0x1800b03d8  mov     rax, [rax+50h]
0x1800b03dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b03e1  test    eax, eax
0x1800b03e3  js      loc_1800B049A
0x1800b03e9  test    [rbp+110h+var_40], 2
0x1800b03f0  jz      short loc_1800B040E
0x1800b03f2  mov     rcx, [rsp+210h+var_1B0]
0x1800b03f7  test    rcx, rcx
0x1800b03fa  jz      short loc_1800B0409
0x1800b03fc  mov     rax, [rcx]
0x1800b03ff  mov     rax, [rax+10h]
0x1800b0403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0408  nop
0x1800b0409  jmp     loc_1800B04B1
0x1800b040e  mov     [rsp+210h+var_1C8], 0
0x1800b0417  lea     rax, [rsp+210h+var_1A8]
0x1800b041c  mov     [rsp+210h+var_1D0], rax
0x1800b0421  mov     [rsp+210h+var_1D8], 0
0x1800b042a  mov     [rsp+210h+var_1E0], 7
0x1800b0432  mov     [rsp+210h+var_1E8], 9
0x1800b043a  lea     rax, qword_1801C1A48
0x1800b0441  mov     [rsp+210h+var_1F0], rax
0x1800b0446  xor     r9d, r9d
0x1800b0449  xor     r8d, r8d
0x1800b044c  xor     edx, edx
0x1800b044e  mov     rcx, [rsp+210h+var_1B0]
0x1800b0453  mov     rax, rsi
0x1800b0456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b045b  test    eax, eax
0x1800b045d  jns     short loc_1800B0478
0x1800b045f  mov     rcx, [rsp+210h+var_1B0]
0x1800b0464  test    rcx, rcx
0x1800b0467  jz      short loc_1800B0476
0x1800b0469  mov     rax, [rcx]
0x1800b046c  mov     rax, [rax+10h]
0x1800b0470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0475  nop
0x1800b0476  jmp     short loc_1800B04B1
0x1800b0478  cmp     [rsp+210h+var_1A8], ebx
0x1800b047c  cmovg   ebx, [rsp+210h+var_1A8]
0x1800b0481  mov     rcx, [rsp+210h+var_1B0]
0x1800b0486  test    rcx, rcx
0x1800b0489  jz      short loc_1800B0498
0x1800b048b  mov     rax, [rcx]
0x1800b048e  mov     rax, [rax+10h]
0x1800b0492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0497  nop
0x1800b0498  jmp     short loc_1800B04B1
0x1800b049a  mov     rcx, [rsp+210h+var_1B0]
0x1800b049f  test    rcx, rcx
0x1800b04a2  jz      short loc_1800B04B1
0x1800b04a4  mov     rax, [rcx]
0x1800b04a7  mov     rax, [rax+10h]
0x1800b04ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b04b0  nop
0x1800b04b1  inc     edi
0x1800b04b3  jmp     loc_1800B0381
0x1800b04b8  mov     rcx, [rsp+210h+var_1B0]
0x1800b04bd  test    rcx, rcx
0x1800b04c0  jz      short loc_1800B04CF
0x1800b04c2  mov     rax, [rcx]
0x1800b04c5  mov     rax, [rax+10h]
0x1800b04c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b04ce  nop
0x1800b04cf  mov     rcx, [rsp+210h+var_1A0]
0x1800b04d4  test    rcx, rcx
0x1800b04d7  jz      short loc_1800B04EF
0x1800b04d9  mov     [rsp+210h+var_1A0], 0
0x1800b04e2  mov     rax, [rcx]
0x1800b04e5  mov     rax, [rax+10h]
0x1800b04e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b04ee  nop
0x1800b04ef  mov     [rsp+210h+var_198], r15
0x1800b04f4  cmp     [rbp+110h+var_190], 0
0x1800b04f9  jz      short loc_1800B0511
0x1800b04fb  lea     rcx, [rsp+210h+var_198]
0x1800b0500  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800b0505  test    al, al
0x1800b0507  jz      short loc_1800B0562
0x1800b0509  mov     [rbp+110h+var_190], 0
0x1800b0511  mov     [rbp+110h+var_188], r15
0x1800b0515  cmp     [rbp+110h+hModule], 0
0x1800b051a  jz      short loc_1800B0529
0x1800b051c  lea     rcx, [rbp+110h+var_188]
0x1800b0520  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800b0525  test    al, al
0x1800b0527  jz      short loc_1800B0548
0x1800b0529  mov     eax, ebx
0x1800b052b  mov     rcx, [rbp+110h+var_30]
0x1800b0532  xor     rcx, rsp; StackCookie
0x1800b0535  call    __security_check_cookie
0x1800b053a  add     rsp, 1F0h
0x1800b0541  pop     r15
0x1800b0543  pop     rdi
0x1800b0544  pop     rsi
0x1800b0545  pop     rbx
0x1800b0546  pop     rbp
0x1800b0547  retn
0x1800b0548  call    cs:__imp_GetLastError
0x1800b054e  test    eax, eax
0x1800b0550  jle     short loc_1800B055A
0x1800b0552  movzx   eax, ax
0x1800b0555  or      eax, 80070000h
0x1800b055a  mov     ecx, eax; this
0x1800b055c  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800b0561  nop
0x1800b0562  call    cs:__imp_GetLastError
0x1800b0568  nop
0x1800b0569  test    eax, eax
0x1800b056b  jle     short loc_1800B0575
0x1800b056d  movzx   eax, ax
0x1800b0570  or      eax, 80070000h
0x1800b0575  mov     ecx, eax; this
0x1800b0577  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
