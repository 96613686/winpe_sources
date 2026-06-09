# DisplayInfo::CDisplayInfoInternal::GetPrimaryGraphicsAdapterInformation(DXGI_ADAPTER_DESC1 *)

- ea: `0x180020c68`
- end: `0x180021027`
- name: `?GetPrimaryGraphicsAdapterInformation@CDisplayInfoInternal@DisplayInfo@@AEAA_NPEAUDXGI_ADAPTER_DESC1@@@Z`
- size: `959`
- prototype: `bool(DisplayInfo::CDisplayInfoInternal *__hidden this, struct DXGI_ADAPTER_DESC1 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001e62c`
- `0x1800a03b0`

## callees

- `0x180008dc0`
- `0x180009f14`
- `0x18001daf0`
- `0x18001dcc8`
- `0x180020c68`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180020cb7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180020cb7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020ce4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020ce4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020fd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020ff3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002100d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020fd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020ff3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002100d`

## string_xrefs

- `0x180020cda`: `CreateDXGIFactory1`
- `0x180020cb0`: `Dxgi.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
char __fastcall DisplayInfo::CDisplayInfoInternal::GetPrimaryGraphicsAdapterInformation(
        DisplayInfo::CDisplayInfoInternal *this,
        struct DXGI_ADAPTER_DESC1 *a2)
{
  struct DXGI_ADAPTER_DESC1 *v2; // rbx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v5; // rcx
  char v6; // si
  unsigned int v7; // r15d
  __int64 v8; // rdi
  int (__fastcall *v9)(__int64, _QWORD, __int64 *); // r14
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  _OWORD *v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  signed int v20; // eax
  int v21; // edx
  unsigned int v22; // r8d
  signed int LastError; // eax
  int v24; // edx
  unsigned int v25; // r8d
  signed int v26; // eax
  int v27; // edx
  unsigned int v28; // r8d
  __int64 v29; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v30; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v31; // [rsp+30h] [rbp-D0h] BYREF
  const int *v32; // [rsp+38h] [rbp-C8h] BYREF
  HMODULE v33; // [rsp+40h] [rbp-C0h]
  _BYTE v34[64]; // [rsp+50h] [rbp-B0h] BYREF
  int v35; // [rsp+90h] [rbp-70h]
  int v36; // [rsp+94h] [rbp-6Ch]
  int v37; // [rsp+A0h] [rbp-60h]
  _BYTE v38[320]; // [rsp+B0h] [rbp-50h] BYREF

  v2 = a2;
  memset_0(a2, 0, sizeof(struct DXGI_ADAPTER_DESC1));
  Library = LoadLibraryExW(L"Dxgi.dll", 0, 0x800u);
  v32 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  v33 = Library;
  if ( !Library )
    return 0;
  ProcAddress = GetProcAddress(Library, "CreateDXGIFactory1");
  if ( !ProcAddress )
  {
    v32 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
    if ( v33 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v32) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v24, v25);
      __debugbreak();
    }
    return 0;
  }
  v31 = 0;
  v30 = 0;
  if ( ((int (__fastcall *)(GUID *, __int64 *))ProcAddress)(&GUID_770aae78_f26f_4dba_a829_253c83d1b387, &v31) < 0 )
  {
    v5 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    v32 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
    if ( v33 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v32) )
    {
      v26 = GetLastError();
      if ( v26 > 0 )
        v26 = (unsigned __int16)v26 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v26, v27, v28);
      JUMPOUT(0x180021026LL);
    }
    return 0;
  }
  v6 = 0;
  v7 = 0;
  while ( 1 )
  {
    v8 = v31;
    v9 = *(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v31 + 96LL);
    v10 = v30;
    if ( v30 )
    {
      v30 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    if ( v9(v8, v7, &v30) < 0 )
      break;
    ++v7;
    v29 = 0;
    memset_0(v34, 0, 0x60u);
    if ( (*(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v30 + 56LL))(v30, 0, &v29) >= 0 )
    {
      if ( (*(int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v29 + 56LL))(v29, v34) >= 0 )
      {
        if ( v37 && !v36 && !v35 )
        {
          memset_0(v38, 0, 0x138u);
          if ( (*(int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v30 + 80LL))(v30, v38) >= 0 )
          {
            v6 = 1;
            v14 = v38;
            v15 = 2;
            do
            {
              *(_OWORD *)v2->Description = *v14;
              *(_OWORD *)&v2->Description[8] = v14[1];
              *(_OWORD *)&v2->Description[16] = v14[2];
              *(_OWORD *)&v2->Description[24] = v14[3];
              *(_OWORD *)&v2->Description[32] = v14[4];
              *(_OWORD *)&v2->Description[40] = v14[5];
              *(_OWORD *)&v2->Description[48] = v14[6];
              *(_OWORD *)&v2->Description[56] = v14[7];
              v2 = (struct DXGI_ADAPTER_DESC1 *)((char *)v2 + 128);
              v14 += 8;
              --v15;
            }
            while ( v15 );
            *(_OWORD *)v2->Description = *v14;
            *(_OWORD *)&v2->Description[8] = v14[1];
            *(_OWORD *)&v2->Description[16] = v14[2];
            *(_QWORD *)&v2->Description[24] = *((_QWORD *)v14 + 6);
          }
          v16 = v29;
          if ( v29 )
          {
            v29 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
          }
          break;
        }
        v13 = v29;
        if ( v29 )
        {
          v29 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
        }
      }
      else
      {
        v12 = v29;
        if ( v29 )
        {
          v29 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        }
      }
    }
    else
    {
      v11 = v29;
      if ( v29 )
      {
        v29 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      }
    }
  }
  v17 = v30;
  if ( v30 )
  {
    v30 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  v18 = v31;
  if ( v31 )
  {
    v31 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  v32 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( v33 && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v32) )
  {
    v20 = GetLastError();
    if ( v20 > 0 )
      v20 = (unsigned __int16)v20 | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v20, v21, v22);
    __debugbreak();
  }
  return v6;
}

```

## disassembly

```asm
0x180020c68  push    rbp
0x180020c6a  push    rbx
0x180020c6b  push    rsi
0x180020c6c  push    rdi
0x180020c6d  push    r12
0x180020c6f  push    r13
0x180020c71  push    r14
0x180020c73  push    r15
0x180020c75  lea     rbp, [rsp-108h]
0x180020c7d  sub     rsp, 208h
0x180020c84  mov     rax, cs:__security_cookie
0x180020c8b  xor     rax, rsp
0x180020c8e  mov     [rbp+140h+var_50], rax
0x180020c95  mov     rbx, rdx
0x180020c98  xor     edx, edx; Val
0x180020c9a  mov     r8d, 138h; Size
0x180020ca0  mov     rcx, rbx; void *
0x180020ca3  call    memset_0
0x180020ca8  xor     edx, edx; hFile
0x180020caa  mov     r8d, 800h; dwFlags
0x180020cb0  lea     rcx, aDxgiDll; "Dxgi.dll"
0x180020cb7  call    cs:__imp_LoadLibraryExW
0x180020cbd  lea     r13, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x180020cc4  mov     [rsp+240h+var_208], r13
0x180020cc9  mov     [rsp+240h+var_200], rax
0x180020cce  xor     r12d, r12d
0x180020cd1  test    rax, rax
0x180020cd4  jz      loc_180020FB4
0x180020cda  lea     rdx, aCreatedxgifact; "CreateDXGIFactory1"
0x180020ce1  mov     rcx, rax; hModule
0x180020ce4  call    cs:__imp_GetProcAddress
0x180020cea  test    rax, rax
0x180020ced  jnz     short loc_180020D16
0x180020cef  mov     [rsp+240h+var_208], r13
0x180020cf4  cmp     [rsp+240h+var_200], r12
0x180020cf9  jz      loc_180020FB4
0x180020cff  lea     rcx, [rsp+240h+var_208]
0x180020d04  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x180020d09  test    al, al
0x180020d0b  jz      loc_180020FF3
0x180020d11  jmp     loc_180020FB4
0x180020d16  mov     [rsp+240h+var_210], r12
0x180020d1b  mov     [rsp+240h+var_218], r12
0x180020d20  lea     rdx, [rsp+240h+var_210]
0x180020d25  lea     rcx, _GUID_770aae78_f26f_4dba_a829_253c83d1b387
0x180020d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d31  test    eax, eax
0x180020d33  jns     short loc_180020D94
0x180020d35  mov     rcx, [rsp+240h+var_218]
0x180020d3a  test    rcx, rcx
0x180020d3d  jz      short loc_180020D51
0x180020d3f  mov     [rsp+240h+var_218], r12
0x180020d44  mov     rax, [rcx]
0x180020d47  mov     rax, [rax+10h]
0x180020d4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d50  nop
0x180020d51  mov     rcx, [rsp+240h+var_210]
0x180020d56  test    rcx, rcx
0x180020d59  jz      short loc_180020D6D
0x180020d5b  mov     [rsp+240h+var_210], r12
0x180020d60  mov     rax, [rcx]
0x180020d63  mov     rax, [rax+10h]
0x180020d67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d6c  nop
0x180020d6d  mov     [rsp+240h+var_208], r13
0x180020d72  cmp     [rsp+240h+var_200], r12
0x180020d77  jz      loc_180020FB4
0x180020d7d  lea     rcx, [rsp+240h+var_208]
0x180020d82  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x180020d87  test    al, al
0x180020d89  jz      loc_18002100D
0x180020d8f  jmp     loc_180020FB4
0x180020d94  mov     sil, r12b
0x180020d97  mov     r15d, r12d
0x180020d9a  mov     rdi, [rsp+240h+var_210]
0x180020d9f  mov     rax, [rdi]
0x180020da2  mov     r14, [rax+60h]
0x180020da6  mov     rcx, [rsp+240h+var_218]
0x180020dab  test    rcx, rcx
0x180020dae  jz      short loc_180020DC2
0x180020db0  mov     [rsp+240h+var_218], r12
0x180020db5  mov     rax, [rcx]
0x180020db8  mov     rax, [rax+10h]
0x180020dbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020dc1  nop
0x180020dc2  lea     r8, [rsp+240h+var_218]
0x180020dc7  mov     edx, r15d
0x180020dca  mov     rcx, rdi
0x180020dcd  mov     rax, r14
0x180020dd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020dd5  test    eax, eax
0x180020dd7  js      loc_180020F5D
0x180020ddd  inc     r15d
0x180020de0  mov     [rsp+240h+var_220], r12
0x180020de5  xor     edx, edx; Val
0x180020de7  lea     r8d, [rdx+60h]; Size
0x180020deb  lea     rcx, [rsp+240h+var_1F0]; void *
0x180020df0  call    memset_0
0x180020df5  mov     rcx, [rsp+240h+var_218]
0x180020dfa  mov     rax, [rcx]
0x180020dfd  lea     r8, [rsp+240h+var_220]
0x180020e02  xor     edx, edx
0x180020e04  mov     rax, [rax+38h]
0x180020e08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e0d  test    eax, eax
0x180020e0f  jns     short loc_180020E32
0x180020e11  mov     rcx, [rsp+240h+var_220]
0x180020e16  test    rcx, rcx
0x180020e19  jz      short loc_180020E2D
0x180020e1b  mov     [rsp+240h+var_220], r12
0x180020e20  mov     rax, [rcx]
0x180020e23  mov     rax, [rax+10h]
0x180020e27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e2c  nop
0x180020e2d  jmp     loc_180020D9A
0x180020e32  mov     rcx, [rsp+240h+var_220]
0x180020e37  mov     rax, [rcx]
0x180020e3a  lea     rdx, [rsp+240h+var_1F0]
0x180020e3f  mov     rax, [rax+38h]
0x180020e43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e48  test    eax, eax
0x180020e4a  jns     short loc_180020E6D
0x180020e4c  mov     rcx, [rsp+240h+var_220]
0x180020e51  test    rcx, rcx
0x180020e54  jz      short loc_180020E68
0x180020e56  mov     [rsp+240h+var_220], r12
0x180020e5b  mov     rax, [rcx]
0x180020e5e  mov     rax, [rax+10h]
0x180020e62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e67  nop
0x180020e68  jmp     loc_180020D9A
0x180020e6d  cmp     [rbp+140h+var_1A0], r12d
0x180020e71  jz      short loc_180020E7F
0x180020e73  cmp     [rbp+140h+var_1AC], r12d
0x180020e77  jnz     short loc_180020E7F
0x180020e79  cmp     [rbp+140h+var_1B0], r12d
0x180020e7d  jz      short loc_180020EA0
0x180020e7f  mov     rcx, [rsp+240h+var_220]
0x180020e84  test    rcx, rcx
0x180020e87  jz      short loc_180020E9B
0x180020e89  mov     [rsp+240h+var_220], r12
0x180020e8e  mov     rax, [rcx]
0x180020e91  mov     rax, [rax+10h]
0x180020e95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020e9a  nop
0x180020e9b  jmp     loc_180020D9A
0x180020ea0  xor     edx, edx; Val
0x180020ea2  mov     r8d, 138h; Size
0x180020ea8  lea     rcx, [rbp+140h+var_190]; void *
0x180020eac  call    memset_0
0x180020eb1  mov     rcx, [rsp+240h+var_218]
0x180020eb6  mov     rax, [rcx]
0x180020eb9  lea     rdx, [rbp+140h+var_190]
0x180020ebd  mov     rax, [rax+50h]
0x180020ec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ec6  test    eax, eax
0x180020ec8  js      short loc_180020F41
0x180020eca  mov     sil, 1
0x180020ecd  lea     rax, [rbp+140h+var_190]
0x180020ed1  mov     ecx, 2
0x180020ed6  lea     edx, [rcx+7Eh]
0x180020ed9  movups  xmm0, xmmword ptr [rax]
0x180020edc  movups  xmmword ptr [rbx], xmm0
0x180020edf  movups  xmm1, xmmword ptr [rax+10h]
0x180020ee3  movups  xmmword ptr [rbx+10h], xmm1
0x180020ee7  movups  xmm0, xmmword ptr [rax+20h]
0x180020eeb  movups  xmmword ptr [rbx+20h], xmm0
0x180020eef  movups  xmm1, xmmword ptr [rax+30h]
0x180020ef3  movups  xmmword ptr [rbx+30h], xmm1
0x180020ef7  movups  xmm0, xmmword ptr [rax+40h]
0x180020efb  movups  xmmword ptr [rbx+40h], xmm0
0x180020eff  movups  xmm1, xmmword ptr [rax+50h]
0x180020f03  movups  xmmword ptr [rbx+50h], xmm1
0x180020f07  movups  xmm0, xmmword ptr [rax+60h]
0x180020f0b  movups  xmmword ptr [rbx+60h], xmm0
0x180020f0f  movups  xmm1, xmmword ptr [rax+70h]
0x180020f13  movups  xmmword ptr [rbx+70h], xmm1
0x180020f17  add     rbx, rdx
0x180020f1a  add     rax, rdx
0x180020f1d  sub     rcx, 1
0x180020f21  jnz     short loc_180020ED9
0x180020f23  movups  xmm0, xmmword ptr [rax]
0x180020f26  movups  xmmword ptr [rbx], xmm0
0x180020f29  movups  xmm1, xmmword ptr [rax+10h]
0x180020f2d  movups  xmmword ptr [rbx+10h], xmm1
0x180020f31  movups  xmm0, xmmword ptr [rax+20h]
0x180020f35  movups  xmmword ptr [rbx+20h], xmm0
0x180020f39  mov     rax, [rax+30h]
0x180020f3d  mov     [rbx+30h], rax
0x180020f41  mov     rcx, [rsp+240h+var_220]
0x180020f46  test    rcx, rcx
0x180020f49  jz      short loc_180020F5D
0x180020f4b  mov     [rsp+240h+var_220], r12
0x180020f50  mov     rax, [rcx]
0x180020f53  mov     rax, [rax+10h]
0x180020f57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f5c  nop
0x180020f5d  mov     rcx, [rsp+240h+var_218]
0x180020f62  test    rcx, rcx
0x180020f65  jz      short loc_180020F79
0x180020f67  mov     [rsp+240h+var_218], r12
0x180020f6c  mov     rax, [rcx]
0x180020f6f  mov     rax, [rax+10h]
0x180020f73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f78  nop
0x180020f79  mov     rcx, [rsp+240h+var_210]
0x180020f7e  test    rcx, rcx
0x180020f81  jz      short loc_180020F95
0x180020f83  mov     [rsp+240h+var_210], r12
0x180020f88  mov     rax, [rcx]
0x180020f8b  mov     rax, [rax+10h]
0x180020f8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f94  nop
0x180020f95  mov     [rsp+240h+var_208], r13
0x180020f9a  cmp     [rsp+240h+var_200], r12
0x180020f9f  jz      short loc_180020FAF
0x180020fa1  lea     rcx, [rsp+240h+var_208]
0x180020fa6  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x180020fab  test    al, al
0x180020fad  jz      short loc_180020FD9
0x180020faf  mov     al, sil
0x180020fb2  jmp     short loc_180020FB6
0x180020fb4  xor     al, al
0x180020fb6  mov     rcx, [rbp+140h+var_50]
0x180020fbd  xor     rcx, rsp; StackCookie
0x180020fc0  call    __security_check_cookie
0x180020fc5  add     rsp, 208h
0x180020fcc  pop     r15
0x180020fce  pop     r14
0x180020fd0  pop     r13
0x180020fd2  pop     r12
0x180020fd4  pop     rdi
0x180020fd5  pop     rsi
0x180020fd6  pop     rbx
0x180020fd7  pop     rbp
0x180020fd8  retn
0x180020fd9  call    cs:__imp_GetLastError
0x180020fdf  test    eax, eax
0x180020fe1  jle     short loc_180020FEB
0x180020fe3  movzx   eax, ax
0x180020fe6  or      eax, 80070000h
0x180020feb  mov     ecx, eax; this
0x180020fed  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180020ff2  int     3; Trap to Debugger
0x180020ff3  call    cs:__imp_GetLastError
0x180020ff9  test    eax, eax
0x180020ffb  jle     short loc_180021005
0x180020ffd  movzx   eax, ax
0x180021000  or      eax, 80070000h
0x180021005  mov     ecx, eax; this
0x180021007  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18002100c  int     3; Trap to Debugger
0x18002100d  call    cs:__imp_GetLastError
0x180021013  test    eax, eax
0x180021015  jle     short loc_18002101F
0x180021017  movzx   eax, ax
0x18002101a  or      eax, 80070000h
0x18002101f  mov     ecx, eax; this
0x180021021  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
