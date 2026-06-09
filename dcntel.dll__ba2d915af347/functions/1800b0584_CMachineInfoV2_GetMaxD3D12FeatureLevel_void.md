# CMachineInfoV2::GetMaxD3D12FeatureLevel(void)

- ea: `0x1800b0584`
- end: `0x1800b0954`
- name: `?GetMaxD3D12FeatureLevel@CMachineInfoV2@@CA?AW4D3D_FEATURE_LEVEL@@XZ`
- size: `976`
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
- `0x1800b0584`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b05be`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b05e1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b05be`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b05e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b0614`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b0629`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b0614`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b0629`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b091f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0939`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b091f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0939`

## string_xrefs

- `0x1800b061d`: `CreateDXGIFactory1`
- `0x1800b05da`: `DXGI.dll`
- `0x1800b060d`: `D3D12CreateDevice`
- `0x1800b05b7`: `D3D12.dll`

## pseudocode

```c
__int64 CMachineInfoV2::GetMaxD3D12FeatureLevel(void)
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
          *((_QWORD *)&v21 + 1) = qword_1801C1A48;
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
    JUMPOUT(0x1800B0953LL);
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
0x1800b0584  push    rbp
0x1800b0586  push    rbx
0x1800b0587  push    rsi
0x1800b0588  push    rdi
0x1800b0589  push    r15
0x1800b058b  lea     rbp, [rsp-0D0h]
0x1800b0593  sub     rsp, 1D0h
0x1800b059a  mov     rax, cs:__security_cookie
0x1800b05a1  xor     rax, rsp
0x1800b05a4  mov     [rbp+0F0h+var_30], rax
0x1800b05ab  xor     ebx, ebx
0x1800b05ad  mov     edi, 800h
0x1800b05b2  mov     r8d, edi; dwFlags
0x1800b05b5  xor     edx, edx; hFile
0x1800b05b7  lea     rcx, aD3d12Dll; "D3D12.dll"
0x1800b05be  call    cs:__imp_LoadLibraryExW
0x1800b05c4  lea     r15, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x1800b05cb  mov     [rsp+1F0h+var_198], r15
0x1800b05d0  mov     [rsp+1F0h+hModule], rax
0x1800b05d5  mov     r8d, edi; dwFlags
0x1800b05d8  xor     edx, edx; hFile
0x1800b05da  lea     rcx, aDxgiDll_0; "DXGI.dll"
0x1800b05e1  call    cs:__imp_LoadLibraryExW
0x1800b05e7  mov     [rsp+1F0h+var_1A8], r15
0x1800b05ec  mov     [rsp+1F0h+var_1A0], rax
0x1800b05f1  mov     [rsp+1F0h+var_1B0], rbx
0x1800b05f6  mov     rcx, [rsp+1F0h+hModule]; hModule
0x1800b05fb  test    rcx, rcx
0x1800b05fe  jz      loc_1800B08A1
0x1800b0604  test    rax, rax
0x1800b0607  jz      loc_1800B08A1
0x1800b060d  lea     rdx, aD3d12createdev; "D3D12CreateDevice"
0x1800b0614  call    cs:__imp_GetProcAddress
0x1800b061a  mov     rsi, rax
0x1800b061d  lea     rdx, aCreatedxgifact; "CreateDXGIFactory1"
0x1800b0624  mov     rcx, [rsp+1F0h+var_1A0]; hModule
0x1800b0629  call    cs:__imp_GetProcAddress
0x1800b062f  mov     rdi, rax
0x1800b0632  test    rsi, rsi
0x1800b0635  jz      loc_1800B08A1
0x1800b063b  test    rax, rax
0x1800b063e  jz      loc_1800B08A1
0x1800b0644  mov     rcx, [rsp+1F0h+var_1B0]
0x1800b0649  test    rcx, rcx
0x1800b064c  jz      short loc_1800B0660
0x1800b064e  mov     [rsp+1F0h+var_1B0], rbx
0x1800b0653  mov     rax, [rcx]
0x1800b0656  mov     rax, [rax+10h]
0x1800b065a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b065f  nop
0x1800b0660  lea     rdx, [rsp+1F0h+var_1B0]
0x1800b0665  lea     rcx, _GUID_50c83a1c_e072_4c48_87b0_3630fa36a6d0
0x1800b066c  mov     rax, rdi
0x1800b066f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0674  test    eax, eax
0x1800b0676  js      loc_1800B08A1
0x1800b067c  cmp     [rsp+1F0h+var_1B0], 0
0x1800b0682  jz      loc_1800B08A1
0x1800b0688  xor     edi, edi
0x1800b068a  mov     [rsp+1F0h+var_1C0], 0
0x1800b0693  mov     [rsp+1F0h+var_1B8], 0
0x1800b069c  xor     edx, edx; Val
0x1800b069e  mov     r8d, 138h; Size
0x1800b06a4  lea     rcx, [rbp+0F0h+var_170]; void *
0x1800b06a8  call    memset_0
0x1800b06ad  xorps   xmm0, xmm0
0x1800b06b0  xor     eax, eax
0x1800b06b2  movups  [rsp+1F0h+var_188], xmm0
0x1800b06b7  mov     [rsp+1F0h+var_178], rax
0x1800b06bc  mov     rcx, [rsp+1F0h+var_1B0]
0x1800b06c1  mov     rax, [rcx]
0x1800b06c4  lea     r8, [rsp+1F0h+var_1C0]
0x1800b06c9  mov     edx, edi
0x1800b06cb  mov     rax, [rax+60h]
0x1800b06cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b06d4  test    eax, eax
0x1800b06d6  js      loc_1800B0873
0x1800b06dc  mov     rcx, [rsp+1F0h+var_1C0]
0x1800b06e1  test    rcx, rcx
0x1800b06e4  jz      loc_1800B0839
0x1800b06ea  mov     rax, [rcx]
0x1800b06ed  lea     rdx, [rbp+0F0h+var_170]
0x1800b06f1  mov     rax, [rax+50h]
0x1800b06f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b06fa  test    eax, eax
0x1800b06fc  js      loc_1800B0834
0x1800b0702  test    [rbp+0F0h+var_40], 2
0x1800b0709  jz      short loc_1800B073E
0x1800b070b  mov     rcx, [rsp+1F0h+var_1B8]
0x1800b0710  test    rcx, rcx
0x1800b0713  jz      short loc_1800B0722
0x1800b0715  mov     rax, [rcx]
0x1800b0718  mov     rax, [rax+10h]
0x1800b071c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0721  nop
0x1800b0722  mov     rcx, [rsp+1F0h+var_1C0]
0x1800b0727  test    rcx, rcx
0x1800b072a  jz      short loc_1800B0739
0x1800b072c  mov     rax, [rcx]
0x1800b072f  mov     rax, [rax+10h]
0x1800b0733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0738  nop
0x1800b0739  jmp     loc_1800B086C
0x1800b073e  lea     r9, [rsp+1F0h+var_1B8]
0x1800b0743  lea     r8, _GUID_189819f1_1db6_4b57_be54_1821339b85f7
0x1800b074a  mov     edx, 0B000h
0x1800b074f  mov     rcx, [rsp+1F0h+var_1C0]
0x1800b0754  mov     rax, rsi
0x1800b0757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b075c  test    eax, eax
0x1800b075e  jns     short loc_1800B0793
0x1800b0760  mov     rcx, [rsp+1F0h+var_1B8]
0x1800b0765  test    rcx, rcx
0x1800b0768  jz      short loc_1800B0777
0x1800b076a  mov     rax, [rcx]
0x1800b076d  mov     rax, [rax+10h]
0x1800b0771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0776  nop
0x1800b0777  mov     rcx, [rsp+1F0h+var_1C0]
0x1800b077c  test    rcx, rcx
0x1800b077f  jz      short loc_1800B078E
0x1800b0781  mov     rax, [rcx]
0x1800b0784  mov     rax, [rax+10h]
0x1800b0788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b078d  nop
0x1800b078e  jmp     loc_1800B086C
0x1800b0793  mov     dword ptr [rsp+1F0h+var_188], 9
0x1800b079b  lea     rax, qword_1801C1A48
0x1800b07a2  mov     qword ptr [rsp+1F0h+var_188+8], rax
0x1800b07a7  mov     rcx, [rsp+1F0h+var_1B8]
0x1800b07ac  mov     rax, [rcx]
0x1800b07af  mov     r9d, 18h
0x1800b07b5  lea     r8, [rsp+1F0h+var_188]
0x1800b07ba  lea     edx, [r9-16h]
0x1800b07be  mov     rax, [rax+68h]
0x1800b07c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b07c7  test    eax, eax
0x1800b07c9  jns     short loc_1800B07FB
0x1800b07cb  mov     rcx, [rsp+1F0h+var_1B8]
0x1800b07d0  test    rcx, rcx
0x1800b07d3  jz      short loc_1800B07E2
0x1800b07d5  mov     rax, [rcx]
0x1800b07d8  mov     rax, [rax+10h]
0x1800b07dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b07e1  nop
0x1800b07e2  mov     rcx, [rsp+1F0h+var_1C0]
0x1800b07e7  test    rcx, rcx
0x1800b07ea  jz      short loc_1800B07F9
0x1800b07ec  mov     rax, [rcx]
0x1800b07ef  mov     rax, [rax+10h]
0x1800b07f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b07f8  nop
0x1800b07f9  jmp     short loc_1800B086C
0x1800b07fb  cmp     dword ptr [rsp+1F0h+var_178], ebx
0x1800b07ff  cmovg   ebx, dword ptr [rsp+1F0h+var_178]
0x1800b0804  mov     rcx, [rsp+1F0h+var_1B8]
0x1800b0809  test    rcx, rcx
0x1800b080c  jz      short loc_1800B081B
0x1800b080e  mov     rax, [rcx]
0x1800b0811  mov     rax, [rax+10h]
0x1800b0815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b081a  nop
0x1800b081b  mov     rcx, [rsp+1F0h+var_1C0]
0x1800b0820  test    rcx, rcx
0x1800b0823  jz      short loc_1800B0832
0x1800b0825  mov     rax, [rcx]
0x1800b0828  mov     rax, [rax+10h]
0x1800b082c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0831  nop
0x1800b0832  jmp     short loc_1800B086C
0x1800b0834  mov     rcx, [rsp+1F0h+var_1C0]
0x1800b0839  mov     rax, [rsp+1F0h+var_1B8]
0x1800b083e  test    rax, rax
0x1800b0841  jz      short loc_1800B085A
0x1800b0843  mov     rcx, [rax]
0x1800b0846  mov     rdx, [rcx+10h]
0x1800b084a  mov     rcx, rax
0x1800b084d  mov     rax, rdx
0x1800b0850  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0855  mov     rcx, [rsp+1F0h+var_1C0]
0x1800b085a  test    rcx, rcx
0x1800b085d  jz      short loc_1800B086C
0x1800b085f  mov     rax, [rcx]
0x1800b0862  mov     rax, [rax+10h]
0x1800b0866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b086b  nop
0x1800b086c  inc     edi
0x1800b086e  jmp     loc_1800B068A
0x1800b0873  mov     rcx, [rsp+1F0h+var_1B8]
0x1800b0878  test    rcx, rcx
0x1800b087b  jz      short loc_1800B088A
0x1800b087d  mov     rax, [rcx]
0x1800b0880  mov     rax, [rax+10h]
0x1800b0884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0889  nop
0x1800b088a  mov     rcx, [rsp+1F0h+var_1C0]
0x1800b088f  test    rcx, rcx
0x1800b0892  jz      short loc_1800B08A1
0x1800b0894  mov     rax, [rcx]
0x1800b0897  mov     rax, [rax+10h]
0x1800b089b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b08a0  nop
0x1800b08a1  mov     rcx, [rsp+1F0h+var_1B0]
0x1800b08a6  test    rcx, rcx
0x1800b08a9  jz      short loc_1800B08C1
0x1800b08ab  mov     [rsp+1F0h+var_1B0], 0
0x1800b08b4  mov     rax, [rcx]
0x1800b08b7  mov     rax, [rax+10h]
0x1800b08bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b08c0  nop
0x1800b08c1  mov     [rsp+1F0h+var_1A8], r15
0x1800b08c6  cmp     [rsp+1F0h+var_1A0], 0
0x1800b08cc  jz      short loc_1800B08E5
0x1800b08ce  lea     rcx, [rsp+1F0h+var_1A8]
0x1800b08d3  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800b08d8  test    al, al
0x1800b08da  jz      short loc_1800B0939
0x1800b08dc  mov     [rsp+1F0h+var_1A0], 0
0x1800b08e5  mov     [rsp+1F0h+var_198], r15
0x1800b08ea  cmp     [rsp+1F0h+hModule], 0
0x1800b08f0  jz      short loc_1800B0900
0x1800b08f2  lea     rcx, [rsp+1F0h+var_198]
0x1800b08f7  call    ?InternalClose@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(void)
0x1800b08fc  test    al, al
0x1800b08fe  jz      short loc_1800B091F
0x1800b0900  mov     eax, ebx
0x1800b0902  mov     rcx, [rbp+0F0h+var_30]
0x1800b0909  xor     rcx, rsp; StackCookie
0x1800b090c  call    __security_check_cookie
0x1800b0911  add     rsp, 1D0h
0x1800b0918  pop     r15
0x1800b091a  pop     rdi
0x1800b091b  pop     rsi
0x1800b091c  pop     rbx
0x1800b091d  pop     rbp
0x1800b091e  retn
0x1800b091f  call    cs:__imp_GetLastError
0x1800b0925  test    eax, eax
0x1800b0927  jle     short loc_1800B0931
0x1800b0929  movzx   eax, ax
0x1800b092c  or      eax, 80070000h
0x1800b0931  mov     ecx, eax; this
0x1800b0933  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800b0938  nop
0x1800b0939  call    cs:__imp_GetLastError
0x1800b093f  nop
0x1800b0940  test    eax, eax
0x1800b0942  jle     short loc_1800B094C
0x1800b0944  movzx   eax, ax
0x1800b0947  or      eax, 80070000h
0x1800b094c  mov     ecx, eax; this
0x1800b094e  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
