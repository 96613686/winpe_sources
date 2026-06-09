# MachineInfo::GetMaxD3D11FeatureLevel(void)

- ea: `0x18003afb4`
- end: `0x18003b2b1`
- name: `?GetMaxD3D11FeatureLevel@MachineInfo@@CA?AW4D3D_FEATURE_LEVEL@@XZ`
- size: `765`
- prototype: `enum D3D_FEATURE_LEVEL(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003a590`

## callees

- `0x180008dc0`
- `0x180009f14`
- `0x18001daf0`
- `0x18001dcc8`
- `0x18003afb4`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003afee`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003b00f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003afee`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003b00f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b040`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b054`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b040`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b054`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b27c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b296`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b27c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b296`

## string_xrefs

- `0x18003b039`: `CreateDXGIFactory1`
- `0x18003afe7`: `DXGI.dll`
- `0x18003b049`: `D3D11CreateDevice`
- `0x18003b008`: `D3D11.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 MachineInfo::GetMaxD3D11FeatureLevel(void)
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
        else if ( v4(v15, 0, 0, 0, qword_1801B8518, 9, 7, 0, &v16, 0) >= 0 )
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
    JUMPOUT(0x18003B2B0LL);
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
0x18003afb4  push    rbp
0x18003afb6  push    rbx
0x18003afb7  push    rsi
0x18003afb8  push    rdi
0x18003afb9  push    r15
0x18003afbb  lea     rbp, [rsp-0F0h]
0x18003afc3  sub     rsp, 1F0h
0x18003afca  mov     rax, cs:__security_cookie
0x18003afd1  xor     rax, rsp
0x18003afd4  mov     [rbp+110h+var_30], rax
0x18003afdb  xor     ebx, ebx
0x18003afdd  mov     edi, 800h
0x18003afe2  mov     r8d, edi; dwFlags
0x18003afe5  xor     edx, edx; hFile
0x18003afe7  lea     rcx, aDxgiDll_0; "DXGI.dll"
0x18003afee  call    cs:__imp_LoadLibraryExW
0x18003aff4  lea     r15, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x18003affb  mov     [rbp+110h+var_188], r15
0x18003afff  mov     [rbp+110h+hModule], rax
0x18003b003  mov     r8d, edi; dwFlags
0x18003b006  xor     edx, edx; hFile
0x18003b008  lea     rcx, aD3d11Dll; "D3D11.dll"
0x18003b00f  call    cs:__imp_LoadLibraryExW
0x18003b015  mov     [rsp+210h+var_198], r15
0x18003b01a  mov     [rbp+110h+var_190], rax
0x18003b01e  mov     [rsp+210h+var_1A0], rbx
0x18003b023  mov     rcx, [rbp+110h+hModule]; hModule
0x18003b027  test    rcx, rcx
0x18003b02a  jz      loc_18003B203
0x18003b030  test    rax, rax
0x18003b033  jz      loc_18003B203
0x18003b039  lea     rdx, aCreatedxgifact; "CreateDXGIFactory1"
0x18003b040  call    cs:__imp_GetProcAddress
0x18003b046  mov     rdi, rax
0x18003b049  lea     rdx, aD3d11createdev; "D3D11CreateDevice"
0x18003b050  mov     rcx, [rbp+110h+var_190]; hModule
0x18003b054  call    cs:__imp_GetProcAddress
0x18003b05a  mov     rsi, rax
0x18003b05d  test    rdi, rdi
0x18003b060  jz      loc_18003B203
0x18003b066  test    rax, rax
0x18003b069  jz      loc_18003B203
0x18003b06f  mov     rcx, [rsp+210h+var_1A0]
0x18003b074  test    rcx, rcx
0x18003b077  jz      short loc_18003B08B
0x18003b079  mov     [rsp+210h+var_1A0], rbx
0x18003b07e  mov     rax, [rcx]
0x18003b081  mov     rax, [rax+10h]
0x18003b085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b08a  nop
0x18003b08b  lea     rdx, [rsp+210h+var_1A0]
0x18003b090  lea     rcx, _GUID_50c83a1c_e072_4c48_87b0_3630fa36a6d0
0x18003b097  mov     rax, rdi
0x18003b09a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b09f  test    eax, eax
0x18003b0a1  js      loc_18003B203
0x18003b0a7  cmp     [rsp+210h+var_1A0], 0
0x18003b0ad  jz      loc_18003B203
0x18003b0b3  xor     edi, edi
0x18003b0b5  mov     [rsp+210h+var_1B0], 0
0x18003b0be  xor     edx, edx; Val
0x18003b0c0  mov     r8d, 138h; Size
0x18003b0c6  lea     rcx, [rbp+110h+var_170]; void *
0x18003b0ca  call    memset_0
0x18003b0cf  mov     [rsp+210h+var_1A8], 0
0x18003b0d7  mov     rcx, [rsp+210h+var_1A0]
0x18003b0dc  mov     rax, [rcx]
0x18003b0df  lea     r8, [rsp+210h+var_1B0]
0x18003b0e4  mov     edx, edi
0x18003b0e6  mov     rax, [rax+60h]
0x18003b0ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b0ef  test    eax, eax
0x18003b0f1  js      loc_18003B1EC
0x18003b0f7  mov     rcx, [rsp+210h+var_1B0]
0x18003b0fc  test    rcx, rcx
0x18003b0ff  jz      loc_18003B1D3
0x18003b105  mov     rax, [rcx]
0x18003b108  lea     rdx, [rbp+110h+var_170]
0x18003b10c  mov     rax, [rax+50h]
0x18003b110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b115  test    eax, eax
0x18003b117  js      loc_18003B1CE
0x18003b11d  test    [rbp+110h+var_40], 2
0x18003b124  jz      short loc_18003B142
0x18003b126  mov     rcx, [rsp+210h+var_1B0]
0x18003b12b  test    rcx, rcx
0x18003b12e  jz      short loc_18003B13D
0x18003b130  mov     rax, [rcx]
0x18003b133  mov     rax, [rax+10h]
0x18003b137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b13c  nop
0x18003b13d  jmp     loc_18003B1E5
0x18003b142  mov     [rsp+210h+var_1C8], 0
0x18003b14b  lea     rax, [rsp+210h+var_1A8]
0x18003b150  mov     [rsp+210h+var_1D0], rax
0x18003b155  mov     [rsp+210h+var_1D8], 0
0x18003b15e  mov     [rsp+210h+var_1E0], 7
0x18003b166  mov     [rsp+210h+var_1E8], 9
0x18003b16e  lea     rax, qword_1801B8518
0x18003b175  mov     [rsp+210h+var_1F0], rax
0x18003b17a  xor     r9d, r9d
0x18003b17d  xor     r8d, r8d
0x18003b180  xor     edx, edx
0x18003b182  mov     rcx, [rsp+210h+var_1B0]
0x18003b187  mov     rax, rsi
0x18003b18a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b18f  test    eax, eax
0x18003b191  jns     short loc_18003B1AC
0x18003b193  mov     rcx, [rsp+210h+var_1B0]
0x18003b198  test    rcx, rcx
0x18003b19b  jz      short loc_18003B1AA
0x18003b19d  mov     rax, [rcx]
0x18003b1a0  mov     rax, [rax+10h]
0x18003b1a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b1a9  nop
0x18003b1aa  jmp     short loc_18003B1E5
0x18003b1ac  cmp     [rsp+210h+var_1A8], ebx
0x18003b1b0  cmovg   ebx, [rsp+210h+var_1A8]
0x18003b1b5  mov     rcx, [rsp+210h+var_1B0]
0x18003b1ba  test    rcx, rcx
0x18003b1bd  jz      short loc_18003B1CC
0x18003b1bf  mov     rax, [rcx]
0x18003b1c2  mov     rax, [rax+10h]
0x18003b1c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b1cb  nop
0x18003b1cc  jmp     short loc_18003B1E5
0x18003b1ce  mov     rcx, [rsp+210h+var_1B0]
0x18003b1d3  test    rcx, rcx
0x18003b1d6  jz      short loc_18003B1E5
0x18003b1d8  mov     rax, [rcx]
0x18003b1db  mov     rax, [rax+10h]
0x18003b1df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b1e4  nop
0x18003b1e5  inc     edi
0x18003b1e7  jmp     loc_18003B0B5
0x18003b1ec  mov     rcx, [rsp+210h+var_1B0]
0x18003b1f1  test    rcx, rcx
0x18003b1f4  jz      short loc_18003B203
0x18003b1f6  mov     rax, [rcx]
0x18003b1f9  mov     rax, [rax+10h]
0x18003b1fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b202  nop
0x18003b203  mov     rcx, [rsp+210h+var_1A0]
0x18003b208  test    rcx, rcx
0x18003b20b  jz      short loc_18003B223
0x18003b20d  mov     [rsp+210h+var_1A0], 0
0x18003b216  mov     rax, [rcx]
0x18003b219  mov     rax, [rax+10h]
0x18003b21d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b222  nop
0x18003b223  mov     [rsp+210h+var_198], r15
0x18003b228  cmp     [rbp+110h+var_190], 0
0x18003b22d  jz      short loc_18003B245
0x18003b22f  lea     rcx, [rsp+210h+var_198]
0x18003b234  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18003b239  test    al, al
0x18003b23b  jz      short loc_18003B296
0x18003b23d  mov     [rbp+110h+var_190], 0
0x18003b245  mov     [rbp+110h+var_188], r15
0x18003b249  cmp     [rbp+110h+hModule], 0
0x18003b24e  jz      short loc_18003B25D
0x18003b250  lea     rcx, [rbp+110h+var_188]
0x18003b254  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18003b259  test    al, al
0x18003b25b  jz      short loc_18003B27C
0x18003b25d  mov     eax, ebx
0x18003b25f  mov     rcx, [rbp+110h+var_30]
0x18003b266  xor     rcx, rsp; StackCookie
0x18003b269  call    __security_check_cookie
0x18003b26e  add     rsp, 1F0h
0x18003b275  pop     r15
0x18003b277  pop     rdi
0x18003b278  pop     rsi
0x18003b279  pop     rbx
0x18003b27a  pop     rbp
0x18003b27b  retn
0x18003b27c  call    cs:__imp_GetLastError
0x18003b282  test    eax, eax
0x18003b284  jle     short loc_18003B28E
0x18003b286  movzx   eax, ax
0x18003b289  or      eax, 80070000h
0x18003b28e  mov     ecx, eax; this
0x18003b290  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18003b295  nop
0x18003b296  call    cs:__imp_GetLastError
0x18003b29c  nop
0x18003b29d  test    eax, eax
0x18003b29f  jle     short loc_18003B2A9
0x18003b2a1  movzx   eax, ax
0x18003b2a4  or      eax, 80070000h
0x18003b2a9  mov     ecx, eax; this
0x18003b2ab  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
