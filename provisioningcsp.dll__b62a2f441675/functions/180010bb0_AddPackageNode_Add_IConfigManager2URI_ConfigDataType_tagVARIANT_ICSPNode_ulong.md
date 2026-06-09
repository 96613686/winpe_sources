# AddPackageNode::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)

- ea: `0x180010bb0`
- end: `0x180010e90`
- name: `?Add@AddPackageNode@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z`
- size: `736`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180006974`
- `0x180010a00`
- `0x180010b00`
- `0x180010bb0`
- `0x180038010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180010c6d`
- `msvcrt!_wcsicmp` at `0x180010d74`
- `msvcrt!_wcsicmp` at `0x180010c6d`
- `msvcrt!_wcsicmp` at `0x180010d74`

## string_xrefs

- `0x180010d69`: `Install`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AddPackageNode::Add(__int64 a1, __int64 a2, int a3, __int128 *a4, __int64 a5, _DWORD *a6)
{
  int v10; // edi
  __int64 v11; // rdx
  int v13; // ebx
  __int64 v14; // rdx
  char *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rcx
  char *v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rcx
  wchar_t *String1; // [rsp+20h] [rbp-48h] BYREF
  __int64 v26; // [rsp+28h] [rbp-40h] BYREF
  char v27; // [rsp+30h] [rbp-38h] BYREF
  char v28; // [rsp+38h] [rbp-30h] BYREF
  __int128 v29; // [rsp+40h] [rbp-28h] BYREF
  __int64 v30; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]
  int v32; // [rsp+A8h] [rbp+40h] BYREF

  v32 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a2 + 136LL))(a2, &v32);
  if ( v10 < 0 )
  {
    v11 = 34;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\addpackagenode.cpp",
      (const char *)(unsigned int)v10,
      (int)String1);
    return (unsigned int)v10;
  }
  if ( v32 != 1 )
  {
    v13 = -2147024809;
    v14 = 35;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\addpackagenode.cpp",
      (const char *)(unsigned int)v13,
      (int)String1);
    return (unsigned int)v13;
  }
  String1 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, wchar_t **))(*(_QWORD *)a2 + 88LL))(a2, 0, &String1);
  if ( v10 < 0 )
  {
    v11 = 38;
    goto LABEL_3;
  }
  if ( !_wcsicmp(String1, L"Path") )
  {
    if ( a3 != 1 )
    {
      v13 = -2046820335;
      v14 = 43;
      goto LABEL_6;
    }
    v15 = (char *)Microsoft::WRL::Details::Make<GenericBStrNode,>(&v26);
    v16 = 0;
    if ( &v27 != v15 )
    {
      v16 = *(_QWORD *)v15;
      *(_QWORD *)v15 = 0;
    }
    v17 = *(_QWORD *)(a1 + 24);
    *(_QWORD *)(a1 + 24) = v16;
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v18 = v26;
    if ( v26 )
    {
      v26 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    v19 = *(_QWORD *)(a1 + 24);
    if ( !v19 )
    {
      v13 = -2147024882;
      v14 = 45;
      goto LABEL_6;
    }
    v29 = *a4;
    v30 = *((_QWORD *)a4 + 2);
    v10 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v19 + 88LL))(v19, &v29);
    if ( v10 < 0 )
    {
      v11 = 46;
      goto LABEL_3;
    }
    if ( a5 )
    {
      v13 = (***(__int64 (__fastcall ****)(_QWORD, GUID *))(a1 + 24))(
              *(_QWORD *)(a1 + 24),
              &GUID_8a13633c_797d_46e9_b602_d982b8ec9847);
      if ( v13 < 0 )
      {
        v14 = 49;
        goto LABEL_6;
      }
    }
    goto LABEL_41;
  }
  if ( !_wcsicmp(String1, L"Install") )
  {
    if ( a3 != 5 )
    {
      v13 = -2046820335;
      v14 = 55;
      goto LABEL_6;
    }
    v20 = (char *)Microsoft::WRL::Details::Make<AddPackageInstallNode,Microsoft::WRL::ComPtr<GenericBStrNode> &>(
                    &v26,
                    a1 + 24);
    v21 = 0;
    if ( &v28 != v20 )
    {
      v21 = *(_QWORD *)v20;
      *(_QWORD *)v20 = 0;
    }
    v22 = *(_QWORD *)(a1 + 32);
    *(_QWORD *)(a1 + 32) = v21;
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v23 = v26;
    if ( v26 )
    {
      v26 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    v24 = *(_QWORD *)(a1 + 32);
    if ( !v24 )
    {
      v13 = -2147024882;
      v14 = 57;
      goto LABEL_6;
    }
    v29 = *a4;
    v30 = *((_QWORD *)a4 + 2);
    v10 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v24 + 88LL))(v24, &v29);
    if ( v10 < 0 )
    {
      v11 = 58;
      goto LABEL_3;
    }
    if ( a5 )
    {
      v13 = (***(__int64 (__fastcall ****)(_QWORD, GUID *))(a1 + 32))(
              *(_QWORD *)(a1 + 32),
              &GUID_8a13633c_797d_46e9_b602_d982b8ec9847);
      if ( v13 < 0 )
      {
        v14 = 61;
        goto LABEL_6;
      }
    }
LABEL_41:
    *a6 = 0;
    return 0;
  }
  return 2248146946LL;
}

```

## disassembly

```asm
0x180010bb0  push    rbp
0x180010bb2  push    rbx
0x180010bb3  push    rsi
0x180010bb4  push    rdi
0x180010bb5  push    r14
0x180010bb7  push    r15
0x180010bb9  mov     rbp, rsp
0x180010bbc  sub     rsp, 68h
0x180010bc0  mov     r15, r9
0x180010bc3  mov     esi, r8d
0x180010bc6  mov     r14, rdx
0x180010bc9  mov     rbx, rcx
0x180010bcc  mov     [rbp+arg_8], 0
0x180010bd3  mov     rax, [rdx]
0x180010bd6  lea     rdx, [rbp+arg_8]
0x180010bda  mov     rcx, r14
0x180010bdd  mov     rax, [rax+88h]
0x180010be4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010be9  mov     edi, eax
0x180010beb  test    eax, eax
0x180010bed  jns     short loc_180010C0E
0x180010bef  mov     edx, 22h ; '"'; void *
0x180010bf4  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\prov\\provcsp\\addpa"...
0x180010bfb  mov     r9d, edi; char *
0x180010bfe  mov     rcx, [rbp+30h]; this
0x180010c02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010c07  mov     eax, edi
0x180010c09  jmp     loc_180010E82
0x180010c0e  cmp     [rbp+arg_8], 1
0x180010c12  jz      short loc_180010C38
0x180010c14  mov     ebx, 80070057h
0x180010c19  mov     edx, 23h ; '#'; void *
0x180010c1e  mov     rcx, [rbp+30h]; this
0x180010c22  mov     r9d, ebx; char *
0x180010c25  lea     r8, aOnecoreuapAdmi_28; "onecoreuap\\admin\\prov\\provcsp\\addpa"...
0x180010c2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010c31  mov     eax, ebx
0x180010c33  jmp     loc_180010E82
0x180010c38  mov     [rbp+String1], 0
0x180010c40  mov     rax, [r14]
0x180010c43  lea     r8, [rbp+String1]
0x180010c47  xor     edx, edx
0x180010c49  mov     rcx, r14
0x180010c4c  mov     rax, [rax+58h]
0x180010c50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c55  mov     edi, eax
0x180010c57  test    eax, eax
0x180010c59  jns     short loc_180010C62
0x180010c5b  mov     edx, 26h ; '&'
0x180010c60  jmp     short loc_180010BF4
0x180010c62  lea     rdx, ?gc_wszAddPackagePathNode@@3QBGB; "Path"
0x180010c69  mov     rcx, [rbp+String1]; String1
0x180010c6d  call    cs:__imp__wcsicmp
0x180010c74  nop     dword ptr [rax+rax+00h]
0x180010c79  test    eax, eax
0x180010c7b  jnz     loc_180010D69
0x180010c81  cmp     esi, 1
0x180010c84  jz      short loc_180010C90
0x180010c86  mov     ebx, 86000011h
0x180010c8b  lea     edx, [rax+2Bh]
0x180010c8e  jmp     short loc_180010C1E
0x180010c90  lea     rcx, [rbp+var_40]
0x180010c94  call    ??$Make@VGenericBStrNode@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VGenericBStrNode@@@12@XZ; Microsoft::WRL::Details::Make<GenericBStrNode,>(void)
0x180010c99  xor     ecx, ecx
0x180010c9b  lea     rdx, [rbp+var_38]
0x180010c9f  cmp     rdx, rax
0x180010ca2  jz      short loc_180010CAE
0x180010ca4  mov     rcx, [rax]
0x180010ca7  mov     qword ptr [rax], 0
0x180010cae  mov     rdx, [rbx+18h]
0x180010cb2  mov     [rbx+18h], rcx
0x180010cb6  test    rdx, rdx
0x180010cb9  jz      short loc_180010CCB
0x180010cbb  mov     rax, [rdx]
0x180010cbe  mov     rcx, rdx
0x180010cc1  mov     rax, [rax+10h]
0x180010cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cca  nop
0x180010ccb  mov     rcx, [rbp+var_40]
0x180010ccf  test    rcx, rcx
0x180010cd2  jz      short loc_180010CE9
0x180010cd4  mov     [rbp+var_40], 0
0x180010cdc  mov     rax, [rcx]
0x180010cdf  mov     rax, [rax+10h]
0x180010ce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ce8  nop
0x180010ce9  mov     rcx, [rbx+18h]
0x180010ced  test    rcx, rcx
0x180010cf0  jnz     short loc_180010CFF
0x180010cf2  mov     ebx, 8007000Eh
0x180010cf7  lea     edx, [rcx+2Dh]
0x180010cfa  jmp     loc_180010C1E
0x180010cff  movups  xmm0, xmmword ptr [r15]
0x180010d03  movaps  [rbp+var_28], xmm0
0x180010d07  movsd   xmm1, qword ptr [r15+10h]
0x180010d0d  movsd   [rbp+var_18], xmm1
0x180010d12  mov     rax, [rcx]
0x180010d15  lea     rdx, [rbp+var_28]
0x180010d19  mov     rax, [rax+58h]
0x180010d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d22  mov     edi, eax
0x180010d24  test    eax, eax
0x180010d26  jns     short loc_180010D32
0x180010d28  mov     edx, 2Eh ; '.'
0x180010d2d  jmp     loc_180010BF4
0x180010d32  mov     r8, [rbp+arg_20]
0x180010d36  test    r8, r8
0x180010d39  jz      loc_180010E6F
0x180010d3f  mov     rcx, [rbx+18h]
0x180010d43  mov     rax, [rcx]
0x180010d46  lea     rdx, _GUID_8a13633c_797d_46e9_b602_d982b8ec9847
0x180010d4d  mov     rax, [rax]
0x180010d50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d55  mov     ebx, eax
0x180010d57  test    eax, eax
0x180010d59  jns     loc_180010E6F
0x180010d5f  mov     edx, 31h ; '1'
0x180010d64  jmp     loc_180010C1E
0x180010d69  lea     rdx, ?gc_wszAddPackageInstallNode@@3QBGB; "Install"
0x180010d70  mov     rcx, [rbp+String1]; String1
0x180010d74  call    cs:__imp__wcsicmp
0x180010d7b  nop     dword ptr [rax+rax+00h]
0x180010d80  test    eax, eax
0x180010d82  jnz     loc_180010E7D
0x180010d88  cmp     esi, 5
0x180010d8b  jz      short loc_180010D9A
0x180010d8d  mov     ebx, 86000011h
0x180010d92  lea     edx, [rax+37h]
0x180010d95  jmp     loc_180010C1E
0x180010d9a  lea     rdx, [rbx+18h]
0x180010d9e  lea     rcx, [rbp+var_40]
0x180010da2  call    ??$Make@VAddPackageInstallNode@@AEAV?$ComPtr@VGenericBStrNode@@@WRL@Microsoft@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VAddPackageInstallNode@@@12@AEAV?$ComPtr@VGenericBStrNode@@@12@@Z; Microsoft::WRL::Details::Make<AddPackageInstallNode,Microsoft::WRL::ComPtr<GenericBStrNode> &>(Microsoft::WRL::ComPtr<GenericBStrNode> &)
0x180010da7  xor     ecx, ecx
0x180010da9  lea     rdx, [rbp+var_30]
0x180010dad  cmp     rdx, rax
0x180010db0  jz      short loc_180010DBC
0x180010db2  mov     rcx, [rax]
0x180010db5  mov     qword ptr [rax], 0
0x180010dbc  mov     rdx, [rbx+20h]
0x180010dc0  mov     [rbx+20h], rcx
0x180010dc4  test    rdx, rdx
0x180010dc7  jz      short loc_180010DD9
0x180010dc9  mov     rax, [rdx]
0x180010dcc  mov     rcx, rdx
0x180010dcf  mov     rax, [rax+10h]
0x180010dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010dd8  nop
0x180010dd9  mov     rcx, [rbp+var_40]
0x180010ddd  test    rcx, rcx
0x180010de0  jz      short loc_180010DF7
0x180010de2  mov     [rbp+var_40], 0
0x180010dea  mov     rax, [rcx]
0x180010ded  mov     rax, [rax+10h]
0x180010df1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010df6  nop
0x180010df7  mov     rcx, [rbx+20h]
0x180010dfb  test    rcx, rcx
0x180010dfe  jnz     short loc_180010E0D
0x180010e00  mov     ebx, 8007000Eh
0x180010e05  lea     edx, [rcx+39h]
0x180010e08  jmp     loc_180010C1E
0x180010e0d  movups  xmm0, xmmword ptr [r15]
0x180010e11  movaps  [rbp+var_28], xmm0
0x180010e15  movsd   xmm1, qword ptr [r15+10h]
0x180010e1b  movsd   [rbp+var_18], xmm1
0x180010e20  mov     rax, [rcx]
0x180010e23  lea     rdx, [rbp+var_28]
0x180010e27  mov     rax, [rax+58h]
0x180010e2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e30  mov     edi, eax
0x180010e32  test    eax, eax
0x180010e34  jns     short loc_180010E40
0x180010e36  mov     edx, 3Ah ; ':'
0x180010e3b  jmp     loc_180010BF4
0x180010e40  mov     r8, [rbp+arg_20]
0x180010e44  test    r8, r8
0x180010e47  jz      short loc_180010E6F
0x180010e49  mov     rcx, [rbx+20h]
0x180010e4d  mov     rax, [rcx]
0x180010e50  lea     rdx, _GUID_8a13633c_797d_46e9_b602_d982b8ec9847
0x180010e57  mov     rax, [rax]
0x180010e5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e5f  mov     ebx, eax
0x180010e61  test    eax, eax
0x180010e63  jns     short loc_180010E6F
0x180010e65  mov     edx, 3Dh ; '='
0x180010e6a  jmp     loc_180010C1E
0x180010e6f  mov     rax, [rbp+arg_28]
0x180010e73  mov     dword ptr [rax], 0
0x180010e79  xor     eax, eax
0x180010e7b  jmp     short loc_180010E82
0x180010e7d  mov     eax, 86000002h
0x180010e82  add     rsp, 68h
0x180010e86  pop     r15
0x180010e88  pop     r14
0x180010e8a  pop     rdi
0x180010e8b  pop     rsi
0x180010e8c  pop     rbx
0x180010e8d  pop     rbp
0x180010e8e  retn
```
