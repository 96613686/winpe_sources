# LoadWCSSchemaFromResource

- ea: `0x18001c2c8`
- end: `0x18001c45c`
- name: `LoadWCSSchemaFromResource`
- size: `404`
- prototype: `__int64 __fastcall(HMODULE hModule)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001c204`

## callees

- `0x18001c2c8`
- `0x180084010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18001c329`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18001c329`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18001c301`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18001c301`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18001c317`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18001c317`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x18001c2e9`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x18001c2e9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001c36f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001c36f`

## pseudocode

```c
__int64 __fastcall LoadWCSSchemaFromResource(HMODULE hModule, const WCHAR *a2, LPVOID *a3)
{
  HRSRC ResourceW; // rax
  HRSRC v6; // rsi
  DWORD v7; // edi
  HGLOBAL Resource; // rax
  LPVOID v9; // rsi
  HRESULT v10; // ebx
  __int64 v12; // [rsp+30h] [rbp-10h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-8h] BYREF
  int v14; // [rsp+78h] [rbp+38h] BYREF

  ResourceW = FindResourceW(hModule, a2, (LPCWSTR)0x64);
  v6 = ResourceW;
  if ( ResourceW
    && (v7 = SizeofResource(hModule, ResourceW)) != 0
    && (Resource = LoadResource(hModule, v6)) != 0
    && (v9 = LockResource(Resource)) != 0 )
  {
    ppv = 0;
    v12 = 0;
    v14 = 0;
    v10 = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument2, &ppv);
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 560LL))(ppv, 0xFFFFFFFFLL);
      if ( v10 >= 0 )
      {
        v10 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IStream, &v12);
        if ( v10 >= 0 )
        {
          v10 = (*(__int64 (__fastcall **)(__int64, LPVOID, _QWORD, int *))(*(_QWORD *)v12 + 32LL))(v12, v9, v7, &v14);
          if ( v10 >= 0 )
          {
            if ( v7 == v14 )
              v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v12 + 40LL))(v12, 0, 0, 0);
            else
              v10 = -2147467259;
          }
        }
      }
    }
    if ( v12 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      v12 = 0;
    }
    if ( v10 < 0 )
    {
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    else
    {
      *a3 = ppv;
    }
  }
  else
  {
    return (unsigned int)-2147022880;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001c2c8  mov     [rsp-18h+arg_0], rbx
0x18001c2cd  mov     [rsp-18h+arg_8], rsi
0x18001c2d2  push    rbp
0x18001c2d3  push    rdi
0x18001c2d4  push    r14
0x18001c2d6  mov     rbp, rsp
0x18001c2d9  sub     rsp, 40h
0x18001c2dd  mov     r14, r8
0x18001c2e0  mov     rbx, rcx
0x18001c2e3  mov     r8d, 64h ; 'd'; lpType
0x18001c2e9  call    cs:__imp_FindResourceW
0x18001c2ef  mov     rsi, rax
0x18001c2f2  test    rax, rax
0x18001c2f5  jz      loc_18001C442
0x18001c2fb  mov     rdx, rax; hResInfo
0x18001c2fe  mov     rcx, rbx; hModule
0x18001c301  call    cs:__imp_SizeofResource
0x18001c307  mov     edi, eax
0x18001c309  test    eax, eax
0x18001c30b  jz      loc_18001C442
0x18001c311  mov     rdx, rsi; hResInfo
0x18001c314  mov     rcx, rbx; hModule
0x18001c317  call    cs:__imp_LoadResource
0x18001c31d  test    rax, rax
0x18001c320  jz      loc_18001C442
0x18001c326  mov     rcx, rax; hResData
0x18001c329  call    cs:__imp_LockResource
0x18001c32f  mov     rsi, rax
0x18001c332  test    rax, rax
0x18001c335  jz      loc_18001C442
0x18001c33b  xor     edx, edx; pUnkOuter
0x18001c33d  mov     [rbp+var_8], 0
0x18001c345  lea     rax, [rbp+var_8]
0x18001c349  mov     [rbp+var_10], 0
0x18001c351  lea     r9, IID_IXMLDOMDocument2; riid
0x18001c358  mov     [rbp+arg_18], 0
0x18001c35f  lea     rcx, CLSID_DOMDocument60; rclsid
0x18001c366  mov     [rsp+40h+ppv], rax; ppv
0x18001c36b  lea     r8d, [rdx+1]; dwClsContext
0x18001c36f  call    cs:__imp_CoCreateInstance
0x18001c375  mov     ebx, eax
0x18001c377  test    eax, eax
0x18001c379  js      loc_18001C401
0x18001c37f  mov     rcx, [rbp+var_8]
0x18001c383  or      edx, 0FFFFFFFFh
0x18001c386  mov     rax, [rcx]
0x18001c389  mov     rax, [rax+230h]
0x18001c390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c395  mov     ebx, eax
0x18001c397  test    eax, eax
0x18001c399  js      short loc_18001C401
0x18001c39b  mov     rcx, [rbp+var_8]
0x18001c39f  lea     r8, [rbp+var_10]
0x18001c3a3  lea     rdx, IID_IStream
0x18001c3aa  mov     rax, [rcx]
0x18001c3ad  mov     rax, [rax]
0x18001c3b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3b5  mov     ebx, eax
0x18001c3b7  test    eax, eax
0x18001c3b9  js      short loc_18001C401
0x18001c3bb  mov     rcx, [rbp+var_10]
0x18001c3bf  lea     r9, [rbp+arg_18]
0x18001c3c3  mov     r8d, edi
0x18001c3c6  mov     rdx, rsi
0x18001c3c9  mov     rax, [rcx]
0x18001c3cc  mov     rax, [rax+20h]
0x18001c3d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3d5  mov     ebx, eax
0x18001c3d7  test    eax, eax
0x18001c3d9  js      short loc_18001C401
0x18001c3db  cmp     edi, [rbp+arg_18]
0x18001c3de  jz      short loc_18001C3E7
0x18001c3e0  mov     ebx, 80004005h
0x18001c3e5  jmp     short loc_18001C401
0x18001c3e7  mov     rcx, [rbp+var_10]
0x18001c3eb  xor     edx, edx
0x18001c3ed  xor     r9d, r9d
0x18001c3f0  xor     r8d, r8d
0x18001c3f3  mov     rax, [rcx]
0x18001c3f6  mov     rax, [rax+28h]
0x18001c3fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c3ff  mov     ebx, eax
0x18001c401  mov     rcx, [rbp+var_10]
0x18001c405  test    rcx, rcx
0x18001c408  jz      short loc_18001C41E
0x18001c40a  mov     rax, [rcx]
0x18001c40d  mov     rax, [rax+10h]
0x18001c411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c416  mov     [rbp+var_10], 0
0x18001c41e  test    ebx, ebx
0x18001c420  js      short loc_18001C42B
0x18001c422  mov     rax, [rbp+var_8]
0x18001c426  mov     [r14], rax
0x18001c429  jmp     short loc_18001C447
0x18001c42b  mov     rcx, [rbp+var_8]
0x18001c42f  test    rcx, rcx
0x18001c432  jz      short loc_18001C447
0x18001c434  mov     rax, [rcx]
0x18001c437  mov     rax, [rax+10h]
0x18001c43b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c440  jmp     short loc_18001C447
0x18001c442  mov     ebx, 800707E0h
0x18001c447  mov     rsi, [rsp+40h+arg_8]
0x18001c44c  mov     eax, ebx
0x18001c44e  mov     rbx, [rsp+40h+arg_0]
0x18001c453  add     rsp, 40h
0x18001c457  pop     r14
0x18001c459  pop     rdi
0x18001c45a  pop     rbp
0x18001c45b  retn
```
