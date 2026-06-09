# CD3D12Device::EnsureChildDevice(IDXGIAdapter *,DXGI_INTERNAL_CHILD_DEVICE_TYPE)

- ea: `0x1800a5ac0`
- end: `0x1800a5c4e`
- name: `?EnsureChildDevice@CD3D12Device@@UEAAJPEAUIDXGIAdapter@@W4DXGI_INTERNAL_CHILD_DEVICE_TYPE@@@Z`
- size: `398`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callees

- `0x180012a20`
- `0x180014750`
- `0x180050b48`
- `0x1800a5ac0`
- `0x1800cb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a5b2b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a5b2b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800a5b10`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800a5b10`

## string_xrefs

- `0x1800a5b24`: `D3D11CreateDevice`
- `0x1800a5b09`: `d3d11.dll`

## pseudocode

```c
__int64 __fastcall CD3D12Device::EnsureChildDevice(__int64 a1, __int64 a2, int a3)
{
  UniqueHMODULE *v6; // rbx
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  int v9; // ebx
  _QWORD v10[2]; // [rsp+60h] [rbp-10h] BYREF
  int v11; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v12; // [rsp+A8h] [rbp+38h] BYREF

  if ( a3 )
    return 2147942487LL;
  if ( a2 )
  {
    v6 = (UniqueHMODULE *)(a1 + 176);
    if ( !*(_QWORD *)(a1 + 176) )
    {
      LibraryW = LoadLibraryW(L"d3d11.dll");
      UniqueHMODULE::attach(v6, LibraryW);
    }
    ProcAddress = GetProcAddress(*(HMODULE *)v6, "D3D11CreateDevice");
    if ( ProcAddress )
    {
      v12 = 0;
      v11 = 45056;
      v9 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, __int64, int *, int, int, __int64 *, _QWORD, _QWORD))ProcAddress)(
             a2,
             0,
             0,
             128,
             &v11,
             1,
             7,
             &v12,
             0,
             0);
      if ( v9 >= 0 )
      {
        (*(void (__fastcall **)(__int64, const GUID *, __int64, const char *))(*(_QWORD *)v12 + 280LL))(
          v12,
          &WKPDID_D3DDebugObjectName,
          36,
          "D3D12 hybrid fullscreen child device");
        v9 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64))v12)(
               v12,
               &GUID_b898d4fd_b5b3_4ffc_8694_0259864ffcf8,
               a1 + 184);
        if ( v9 >= 0 )
        {
          v10[0] = 0;
          v9 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v12)(
                 v12,
                 &GUID_77db970f_6276_48ba_ba28_070143b4392c,
                 v10);
          if ( v9 >= 0 )
            v9 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v10[0] + 96LL))(v10[0], 16);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v10);
        }
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
    return (unsigned int)v9;
  }
  else
  {
    ATL::CComPtrBase<IDXGIIndirectSwapChain>::Release(a1 + 184);
    return 0;
  }
}

```

## disassembly

```asm
0x1800a5ac0  mov     [rsp-18h+arg_0], rbx
0x1800a5ac5  push    rbp
0x1800a5ac6  push    rsi
0x1800a5ac7  push    rdi
0x1800a5ac8  mov     rbp, rsp
0x1800a5acb  sub     rsp, 70h
0x1800a5acf  mov     rsi, rdx
0x1800a5ad2  mov     rdi, rcx
0x1800a5ad5  test    r8d, r8d
0x1800a5ad8  jz      short loc_1800A5AE4
0x1800a5ada  mov     eax, 80070057h
0x1800a5adf  jmp     loc_1800A5C3E
0x1800a5ae4  test    rsi, rsi
0x1800a5ae7  jnz     short loc_1800A5AFC
0x1800a5ae9  add     rcx, 0B8h
0x1800a5af0  call    ?Release@?$CComPtrBase@UIDXGIIndirectSwapChain@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IDXGIIndirectSwapChain>::Release(void)
0x1800a5af5  xor     eax, eax
0x1800a5af7  jmp     loc_1800A5C3E
0x1800a5afc  lea     rbx, [rcx+0B0h]
0x1800a5b03  cmp     qword ptr [rbx], 0
0x1800a5b07  jnz     short loc_1800A5B21
0x1800a5b09  lea     rcx, aD3d11Dll; "d3d11.dll"
0x1800a5b10  call    cs:__imp_LoadLibraryW
0x1800a5b16  mov     rdx, rax; HINSTANCE
0x1800a5b19  mov     rcx, rbx; this
0x1800a5b1c  call    ?attach@UniqueHMODULE@@QEAAXPEAUHINSTANCE__@@@Z; UniqueHMODULE::attach(HINSTANCE__ *)
0x1800a5b21  mov     rcx, [rbx]; hModule
0x1800a5b24  lea     rdx, aD3d11createdev_0; "D3D11CreateDevice"
0x1800a5b2b  call    cs:__imp_GetProcAddress
0x1800a5b31  test    rax, rax
0x1800a5b34  jz      loc_1800A5C37
0x1800a5b3a  mov     [rsp+70h+var_28], 0
0x1800a5b43  lea     rcx, [rbp+arg_18]
0x1800a5b47  mov     [rsp+70h+var_30], 0
0x1800a5b50  mov     r9d, 80h
0x1800a5b56  mov     [rsp+70h+var_38], rcx
0x1800a5b5b  xor     r8d, r8d
0x1800a5b5e  mov     [rsp+70h+var_40], 7
0x1800a5b66  lea     rcx, [rbp+arg_10]
0x1800a5b6a  mov     [rsp+70h+var_48], 1
0x1800a5b72  xor     edx, edx
0x1800a5b74  mov     [rsp+70h+var_50], rcx
0x1800a5b79  mov     rcx, rsi
0x1800a5b7c  mov     [rbp+arg_18], 0
0x1800a5b84  mov     [rbp+arg_10], 0B000h
0x1800a5b8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5b90  mov     ebx, eax
0x1800a5b92  test    eax, eax
0x1800a5b94  js      loc_1800A5C2C
0x1800a5b9a  mov     rcx, [rbp+arg_18]
0x1800a5b9e  lea     r9, aD3d12HybridFul; "D3D12 hybrid fullscreen child device"
0x1800a5ba5  mov     r8d, 24h ; '$'
0x1800a5bab  lea     rdx, WKPDID_D3DDebugObjectName
0x1800a5bb2  mov     rax, [rcx]
0x1800a5bb5  mov     rax, [rax+118h]
0x1800a5bbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5bc1  mov     rcx, [rbp+arg_18]
0x1800a5bc5  lea     r8, [rdi+0B8h]
0x1800a5bcc  lea     rdx, _GUID_b898d4fd_b5b3_4ffc_8694_0259864ffcf8
0x1800a5bd3  mov     rax, [rcx]
0x1800a5bd6  mov     rax, [rax]
0x1800a5bd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5bde  mov     ebx, eax
0x1800a5be0  test    eax, eax
0x1800a5be2  js      short loc_1800A5C2C
0x1800a5be4  mov     rcx, [rbp+arg_18]
0x1800a5be8  lea     r8, [rbp+var_10]
0x1800a5bec  mov     [rbp+var_10], 0
0x1800a5bf4  lea     rdx, _GUID_77db970f_6276_48ba_ba28_070143b4392c
0x1800a5bfb  mov     rax, [rcx]
0x1800a5bfe  mov     rax, [rax]
0x1800a5c01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5c06  mov     ebx, eax
0x1800a5c08  test    eax, eax
0x1800a5c0a  js      short loc_1800A5C23
0x1800a5c0c  mov     rcx, [rbp+var_10]
0x1800a5c10  mov     edx, 10h
0x1800a5c15  mov     rax, [rcx]
0x1800a5c18  mov     rax, [rax+60h]
0x1800a5c1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5c21  mov     ebx, eax
0x1800a5c23  lea     rcx, [rbp+var_10]
0x1800a5c27  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800a5c2c  lea     rcx, [rbp+arg_18]
0x1800a5c30  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800a5c35  jmp     short loc_1800A5C3C
0x1800a5c37  mov     ebx, 8007000Eh
0x1800a5c3c  mov     eax, ebx
0x1800a5c3e  mov     rbx, [rsp+70h+arg_0]
0x1800a5c46  add     rsp, 70h
0x1800a5c4a  pop     rdi
0x1800a5c4b  pop     rsi
0x1800a5c4c  pop     rbp
0x1800a5c4d  retn
```
