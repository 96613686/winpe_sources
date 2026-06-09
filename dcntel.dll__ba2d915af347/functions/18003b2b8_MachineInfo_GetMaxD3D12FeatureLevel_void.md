# MachineInfo::GetMaxD3D12FeatureLevel(void)

- ea: `0x18003b2b8`
- end: `0x18003b688`
- name: `?GetMaxD3D12FeatureLevel@MachineInfo@@CA?AW4D3D_FEATURE_LEVEL@@XZ`
- size: `976`
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
- `0x18003b2b8`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003b2f2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003b315`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003b2f2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003b315`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b348`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b35d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b348`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b35d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b653`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b66d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b653`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b66d`

## string_xrefs

- `0x18003b351`: `CreateDXGIFactory1`
- `0x18003b30e`: `DXGI.dll`
- `0x18003b341`: `D3D12CreateDevice`
- `0x18003b2eb`: `D3D12.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 MachineInfo::GetMaxD3D12FeatureLevel(void)
{
  int v0; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rsi
  FARPROC v3; // rax
  unsigned int i; // edi
  __int64 v5; // rcx
  __int64 v6; // rcx
  signed int v8; // eax
  int v9; // edx
  unsigned int v10; // r8d
  signed int LastError; // eax
  int v12; // edx
  unsigned int v13; // r8d
  __int64 v14; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v15; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v16; // [rsp+40h] [rbp-C0h] BYREF
  const int *v17; // [rsp+48h] [rbp-B8h] BYREF
  HMODULE v18; // [rsp+50h] [rbp-B0h]
  const int *v19; // [rsp+58h] [rbp-A8h] BYREF
  HMODULE hModule; // [rsp+60h] [rbp-A0h]
  __int128 v21; // [rsp+68h] [rbp-98h] BYREF
  __int64 v22; // [rsp+78h] [rbp-88h]
  _BYTE v23[320]; // [rsp+80h] [rbp-80h] BYREF

  v0 = 0;
  v19 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  hModule = LoadLibraryExW(L"D3D12.dll", 0, 0x800u);
  Library = LoadLibraryExW(L"DXGI.dll", 0, 0x800u);
  v17 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  v18 = Library;
  v16 = 0;
  if ( !hModule )
    goto LABEL_46;
  if ( !Library )
    goto LABEL_46;
  ProcAddress = GetProcAddress(hModule, "D3D12CreateDevice");
  v3 = GetProcAddress(v18, "CreateDXGIFactory1");
  if ( !ProcAddress
    || !v3
    || ((int (__fastcall *)(GUID *, __int64 *))v3)(&GUID_50c83a1c_e072_4c48_87b0_3630fa36a6d0, &v16) < 0
    || !v16 )
  {
    goto LABEL_46;
  }
  for ( i = 0; ; ++i )
  {
    v14 = 0;
    v15 = 0;
    memset_0(v23, 0, 0x138u);
    v21 = 0;
    v22 = 0;
    if ( (*(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v16 + 96LL))(v16, i, &v14) < 0 )
      break;
    v5 = v14;
    if ( v14 )
    {
      if ( (*(int (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v14 + 80LL))(v14, v23) >= 0 )
      {
        if ( (v23[304] & 2) != 0 )
        {
          if ( v15 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
          if ( v14 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        }
        else if ( ((int (__fastcall *)(__int64, __int64, GUID *, __int64 *))ProcAddress)(
                    v14,
                    45056,
                    &GUID_189819f1_1db6_4b57_be54_1821339b85f7,
                    &v15) >= 0 )
        {
          LODWORD(v21) = 9;
          *((_QWORD *)&v21 + 1) = qword_1801B8518;
          if ( (*(int (__fastcall **)(__int64, __int64, __int128 *))(*(_QWORD *)v15 + 104LL))(v15, 2, &v21) >= 0 )
          {
            if ( (int)v22 > v0 )
              v0 = v22;
            if ( v15 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
            if ( v14 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
          }
          else
          {
            if ( v15 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
            if ( v14 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
          }
        }
        else
        {
          if ( v15 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
          if ( v14 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        }
        continue;
      }
      v5 = v14;
    }
    if ( v15 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      v5 = v14;
    }
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
LABEL_46:
  v6 = v16;
  if ( v16 )
  {
    v16 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  v17 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( v18 )
  {
    if ( (unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v17) )
    {
      v18 = 0;
      goto LABEL_51;
    }
LABEL_57:
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v12, v13);
    JUMPOUT(0x18003B687LL);
  }
LABEL_51:
  v19 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( hModule && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v19) )
  {
    v8 = GetLastError();
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v8, v9, v10);
    goto LABEL_57;
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x18003b2b8  push    rbp
0x18003b2ba  push    rbx
0x18003b2bb  push    rsi
0x18003b2bc  push    rdi
0x18003b2bd  push    r15
0x18003b2bf  lea     rbp, [rsp-0D0h]
0x18003b2c7  sub     rsp, 1D0h
0x18003b2ce  mov     rax, cs:__security_cookie
0x18003b2d5  xor     rax, rsp
0x18003b2d8  mov     [rbp+0F0h+var_30], rax
0x18003b2df  xor     ebx, ebx
0x18003b2e1  mov     edi, 800h
0x18003b2e6  mov     r8d, edi; dwFlags
0x18003b2e9  xor     edx, edx; hFile
0x18003b2eb  lea     rcx, aD3d12Dll; "D3D12.dll"
0x18003b2f2  call    cs:__imp_LoadLibraryExW
0x18003b2f8  lea     r15, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x18003b2ff  mov     [rsp+1F0h+var_198], r15
0x18003b304  mov     [rsp+1F0h+hModule], rax
0x18003b309  mov     r8d, edi; dwFlags
0x18003b30c  xor     edx, edx; hFile
0x18003b30e  lea     rcx, aDxgiDll_0; "DXGI.dll"
0x18003b315  call    cs:__imp_LoadLibraryExW
0x18003b31b  mov     [rsp+1F0h+var_1A8], r15
0x18003b320  mov     [rsp+1F0h+var_1A0], rax
0x18003b325  mov     [rsp+1F0h+var_1B0], rbx
0x18003b32a  mov     rcx, [rsp+1F0h+hModule]; hModule
0x18003b32f  test    rcx, rcx
0x18003b332  jz      loc_18003B5D5
0x18003b338  test    rax, rax
0x18003b33b  jz      loc_18003B5D5
0x18003b341  lea     rdx, aD3d12createdev; "D3D12CreateDevice"
0x18003b348  call    cs:__imp_GetProcAddress
0x18003b34e  mov     rsi, rax
0x18003b351  lea     rdx, aCreatedxgifact; "CreateDXGIFactory1"
0x18003b358  mov     rcx, [rsp+1F0h+var_1A0]; hModule
0x18003b35d  call    cs:__imp_GetProcAddress
0x18003b363  mov     rdi, rax
0x18003b366  test    rsi, rsi
0x18003b369  jz      loc_18003B5D5
0x18003b36f  test    rax, rax
0x18003b372  jz      loc_18003B5D5
0x18003b378  mov     rcx, [rsp+1F0h+var_1B0]
0x18003b37d  test    rcx, rcx
0x18003b380  jz      short loc_18003B394
0x18003b382  mov     [rsp+1F0h+var_1B0], rbx
0x18003b387  mov     rax, [rcx]
0x18003b38a  mov     rax, [rax+10h]
0x18003b38e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b393  nop
0x18003b394  lea     rdx, [rsp+1F0h+var_1B0]
0x18003b399  lea     rcx, _GUID_50c83a1c_e072_4c48_87b0_3630fa36a6d0
0x18003b3a0  mov     rax, rdi
0x18003b3a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b3a8  test    eax, eax
0x18003b3aa  js      loc_18003B5D5
0x18003b3b0  cmp     [rsp+1F0h+var_1B0], 0
0x18003b3b6  jz      loc_18003B5D5
0x18003b3bc  xor     edi, edi
0x18003b3be  mov     [rsp+1F0h+var_1C0], 0
0x18003b3c7  mov     [rsp+1F0h+var_1B8], 0
0x18003b3d0  xor     edx, edx; Val
0x18003b3d2  mov     r8d, 138h; Size
0x18003b3d8  lea     rcx, [rbp+0F0h+var_170]; void *
0x18003b3dc  call    memset_0
0x18003b3e1  xorps   xmm0, xmm0
0x18003b3e4  xor     eax, eax
0x18003b3e6  movups  [rsp+1F0h+var_188], xmm0
0x18003b3eb  mov     [rsp+1F0h+var_178], rax
0x18003b3f0  mov     rcx, [rsp+1F0h+var_1B0]
0x18003b3f5  mov     rax, [rcx]
0x18003b3f8  lea     r8, [rsp+1F0h+var_1C0]
0x18003b3fd  mov     edx, edi
0x18003b3ff  mov     rax, [rax+60h]
0x18003b403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b408  test    eax, eax
0x18003b40a  js      loc_18003B5A7
0x18003b410  mov     rcx, [rsp+1F0h+var_1C0]
0x18003b415  test    rcx, rcx
0x18003b418  jz      loc_18003B56D
0x18003b41e  mov     rax, [rcx]
0x18003b421  lea     rdx, [rbp+0F0h+var_170]
0x18003b425  mov     rax, [rax+50h]
0x18003b429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b42e  test    eax, eax
0x18003b430  js      loc_18003B568
0x18003b436  test    [rbp+0F0h+var_40], 2
0x18003b43d  jz      short loc_18003B472
0x18003b43f  mov     rcx, [rsp+1F0h+var_1B8]
0x18003b444  test    rcx, rcx
0x18003b447  jz      short loc_18003B456
0x18003b449  mov     rax, [rcx]
0x18003b44c  mov     rax, [rax+10h]
0x18003b450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b455  nop
0x18003b456  mov     rcx, [rsp+1F0h+var_1C0]
0x18003b45b  test    rcx, rcx
0x18003b45e  jz      short loc_18003B46D
0x18003b460  mov     rax, [rcx]
0x18003b463  mov     rax, [rax+10h]
0x18003b467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b46c  nop
0x18003b46d  jmp     loc_18003B5A0
0x18003b472  lea     r9, [rsp+1F0h+var_1B8]
0x18003b477  lea     r8, _GUID_189819f1_1db6_4b57_be54_1821339b85f7
0x18003b47e  mov     edx, 0B000h
0x18003b483  mov     rcx, [rsp+1F0h+var_1C0]
0x18003b488  mov     rax, rsi
0x18003b48b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b490  test    eax, eax
0x18003b492  jns     short loc_18003B4C7
0x18003b494  mov     rcx, [rsp+1F0h+var_1B8]
0x18003b499  test    rcx, rcx
0x18003b49c  jz      short loc_18003B4AB
0x18003b49e  mov     rax, [rcx]
0x18003b4a1  mov     rax, [rax+10h]
0x18003b4a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b4aa  nop
0x18003b4ab  mov     rcx, [rsp+1F0h+var_1C0]
0x18003b4b0  test    rcx, rcx
0x18003b4b3  jz      short loc_18003B4C2
0x18003b4b5  mov     rax, [rcx]
0x18003b4b8  mov     rax, [rax+10h]
0x18003b4bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b4c1  nop
0x18003b4c2  jmp     loc_18003B5A0
0x18003b4c7  mov     dword ptr [rsp+1F0h+var_188], 9
0x18003b4cf  lea     rax, qword_1801B8518
0x18003b4d6  mov     qword ptr [rsp+1F0h+var_188+8], rax
0x18003b4db  mov     rcx, [rsp+1F0h+var_1B8]
0x18003b4e0  mov     rax, [rcx]
0x18003b4e3  mov     r9d, 18h
0x18003b4e9  lea     r8, [rsp+1F0h+var_188]
0x18003b4ee  lea     edx, [r9-16h]
0x18003b4f2  mov     rax, [rax+68h]
0x18003b4f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b4fb  test    eax, eax
0x18003b4fd  jns     short loc_18003B52F
0x18003b4ff  mov     rcx, [rsp+1F0h+var_1B8]
0x18003b504  test    rcx, rcx
0x18003b507  jz      short loc_18003B516
0x18003b509  mov     rax, [rcx]
0x18003b50c  mov     rax, [rax+10h]
0x18003b510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b515  nop
0x18003b516  mov     rcx, [rsp+1F0h+var_1C0]
0x18003b51b  test    rcx, rcx
0x18003b51e  jz      short loc_18003B52D
0x18003b520  mov     rax, [rcx]
0x18003b523  mov     rax, [rax+10h]
0x18003b527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b52c  nop
0x18003b52d  jmp     short loc_18003B5A0
0x18003b52f  cmp     dword ptr [rsp+1F0h+var_178], ebx
0x18003b533  cmovg   ebx, dword ptr [rsp+1F0h+var_178]
0x18003b538  mov     rcx, [rsp+1F0h+var_1B8]
0x18003b53d  test    rcx, rcx
0x18003b540  jz      short loc_18003B54F
0x18003b542  mov     rax, [rcx]
0x18003b545  mov     rax, [rax+10h]
0x18003b549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b54e  nop
0x18003b54f  mov     rcx, [rsp+1F0h+var_1C0]
0x18003b554  test    rcx, rcx
0x18003b557  jz      short loc_18003B566
0x18003b559  mov     rax, [rcx]
0x18003b55c  mov     rax, [rax+10h]
0x18003b560  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b565  nop
0x18003b566  jmp     short loc_18003B5A0
0x18003b568  mov     rcx, [rsp+1F0h+var_1C0]
0x18003b56d  mov     rax, [rsp+1F0h+var_1B8]
0x18003b572  test    rax, rax
0x18003b575  jz      short loc_18003B58E
0x18003b577  mov     rcx, [rax]
0x18003b57a  mov     rdx, [rcx+10h]
0x18003b57e  mov     rcx, rax
0x18003b581  mov     rax, rdx
0x18003b584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b589  mov     rcx, [rsp+1F0h+var_1C0]
0x18003b58e  test    rcx, rcx
0x18003b591  jz      short loc_18003B5A0
0x18003b593  mov     rax, [rcx]
0x18003b596  mov     rax, [rax+10h]
0x18003b59a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b59f  nop
0x18003b5a0  inc     edi
0x18003b5a2  jmp     loc_18003B3BE
0x18003b5a7  mov     rcx, [rsp+1F0h+var_1B8]
0x18003b5ac  test    rcx, rcx
0x18003b5af  jz      short loc_18003B5BE
0x18003b5b1  mov     rax, [rcx]
0x18003b5b4  mov     rax, [rax+10h]
0x18003b5b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b5bd  nop
0x18003b5be  mov     rcx, [rsp+1F0h+var_1C0]
0x18003b5c3  test    rcx, rcx
0x18003b5c6  jz      short loc_18003B5D5
0x18003b5c8  mov     rax, [rcx]
0x18003b5cb  mov     rax, [rax+10h]
0x18003b5cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b5d4  nop
0x18003b5d5  mov     rcx, [rsp+1F0h+var_1B0]
0x18003b5da  test    rcx, rcx
0x18003b5dd  jz      short loc_18003B5F5
0x18003b5df  mov     [rsp+1F0h+var_1B0], 0
0x18003b5e8  mov     rax, [rcx]
0x18003b5eb  mov     rax, [rax+10h]
0x18003b5ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b5f4  nop
0x18003b5f5  mov     [rsp+1F0h+var_1A8], r15
0x18003b5fa  cmp     [rsp+1F0h+var_1A0], 0
0x18003b600  jz      short loc_18003B619
0x18003b602  lea     rcx, [rsp+1F0h+var_1A8]
0x18003b607  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18003b60c  test    al, al
0x18003b60e  jz      short loc_18003B66D
0x18003b610  mov     [rsp+1F0h+var_1A0], 0
0x18003b619  mov     [rsp+1F0h+var_198], r15
0x18003b61e  cmp     [rsp+1F0h+hModule], 0
0x18003b624  jz      short loc_18003B634
0x18003b626  lea     rcx, [rsp+1F0h+var_198]
0x18003b62b  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x18003b630  test    al, al
0x18003b632  jz      short loc_18003B653
0x18003b634  mov     eax, ebx
0x18003b636  mov     rcx, [rbp+0F0h+var_30]
0x18003b63d  xor     rcx, rsp; StackCookie
0x18003b640  call    __security_check_cookie
0x18003b645  add     rsp, 1D0h
0x18003b64c  pop     r15
0x18003b64e  pop     rdi
0x18003b64f  pop     rsi
0x18003b650  pop     rbx
0x18003b651  pop     rbp
0x18003b652  retn
0x18003b653  call    cs:__imp_GetLastError
0x18003b659  test    eax, eax
0x18003b65b  jle     short loc_18003B665
0x18003b65d  movzx   eax, ax
0x18003b660  or      eax, 80070000h
0x18003b665  mov     ecx, eax; this
0x18003b667  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18003b66c  nop
0x18003b66d  call    cs:__imp_GetLastError
0x18003b673  nop
0x18003b674  test    eax, eax
0x18003b676  jle     short loc_18003B680
0x18003b678  movzx   eax, ax
0x18003b67b  or      eax, 80070000h
0x18003b680  mov     ecx, eax; this
0x18003b682  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
