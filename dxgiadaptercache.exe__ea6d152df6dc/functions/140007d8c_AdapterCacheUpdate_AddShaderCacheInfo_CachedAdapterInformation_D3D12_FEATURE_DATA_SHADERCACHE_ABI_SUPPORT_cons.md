# AdapterCacheUpdate::AddShaderCacheInfo(CachedAdapterInformation &,D3D12_FEATURE_DATA_SHADERCACHE_ABI_SUPPORT const &)

- ea: `0x140007d8c`
- end: `0x140007f20`
- name: `?AddShaderCacheInfo@AdapterCacheUpdate@@QEAA_NAEAUCachedAdapterInformation@@AEBUD3D12_FEATURE_DATA_SHADERCACHE_ABI_SUPPORT@@@Z`
- size: `404`
- prototype: `bool __fastcall(AdapterCacheUpdate *this, HKEY *, const BYTE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000e174`

## callees

- `0x140007d8c`
- `0x1400103d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140007dd8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140007e0d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140007e3f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140007e72`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140007dd8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140007e0d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140007e3f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140007e72`

## string_xrefs

- `0x140007e68`: `CompilerVersion`

## pseudocode

```c
bool __fastcall AdapterCacheUpdate::AddShaderCacheInfo(AdapterCacheUpdate *this, HKEY *a2, const BYTE *a3)
{
  HKEY v3; // rsi
  __int64 v4; // rax
  const BYTE *v5; // rbx
  unsigned int v7; // eax
  int v8; // r8d
  HKEY *v9; // r15
  unsigned int v10; // eax
  int v11; // r8d
  HKEY *v12; // r14
  unsigned int v13; // eax
  int v14; // r8d
  _QWORD *v15; // rbp
  unsigned int v16; // eax
  int v17; // r8d
  char *v18; // rax
  signed __int64 v19; // rax
  int v20; // edx
  int v21; // ecx
  unsigned int lpData; // [rsp+20h] [rbp-48h]
  unsigned int lpDataa; // [rsp+20h] [rbp-48h]
  unsigned int lpDatab; // [rsp+20h] [rbp-48h]
  unsigned int lpDatac; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v3 = *a2;
  v4 = -1;
  v5 = a3;
  do
    ++v4;
  while ( *(_WORD *)&a3[2 * v4] );
  v7 = RegSetValueExW(v3, L"AdapterFamily", 0, 1u, a3, 2 * v4 + 2);
  if ( v7 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x15D, v8, (const char *)v7, lpData);
  v9 = (HKEY *)(v5 + 256);
  v10 = RegSetValueExW(v3, L"MinimumABISupportVersion", 0, 0xBu, v5 + 256, 8u);
  if ( v10 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x152, v11, (const char *)v10, lpDataa);
  v12 = (HKEY *)(v5 + 264);
  v13 = RegSetValueExW(v3, L"MaximumABISupportVersion", 0, 0xBu, v5 + 264, 8u);
  if ( v13 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x152, v14, (const char *)v13, lpDatab);
  v15 = v5 + 272;
  v16 = RegSetValueExW(v3, L"CompilerVersion", 0, 0xBu, v5 + 272, 8u);
  if ( v16 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x152, v17, (const char *)v16, lpDatac);
  v18 = (char *)(a2 + 5);
  if ( (unsigned __int64)a2[8] > 7 )
    v18 = *(char **)v18;
  v19 = v18 - (char *)v5;
  do
  {
    v20 = *(unsigned __int16 *)&v5[v19];
    v21 = *(unsigned __int16 *)v5 - v20;
    if ( v21 )
      break;
    v5 += 2;
  }
  while ( v20 );
  return v21 || *v9 != a2[9] || *v12 != a2[10] || *v15 != (_QWORD)a2[11];
}

```

## disassembly

```asm
0x140007d8c  push    rbx
0x140007d8e  push    rbp
0x140007d8f  push    rsi
0x140007d90  push    rdi
0x140007d91  push    r12
0x140007d93  push    r14
0x140007d95  push    r15
0x140007d97  sub     rsp, 30h
0x140007d9b  mov     rsi, [rdx]
0x140007d9e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140007da2  xor     r12d, r12d
0x140007da5  mov     rbx, r8
0x140007da8  mov     rdi, rdx
0x140007dab  inc     rax
0x140007dae  cmp     [r8+rax*2], r12w
0x140007db3  jnz     short loc_140007DAB
0x140007db5  lea     eax, ds:2[rax*2]
0x140007dbc  mov     r9d, 1; dwType
0x140007dc2  mov     [rsp+68h+cbData], eax; cbData
0x140007dc6  lea     rdx, aAdapterfamily; "AdapterFamily"
0x140007dcd  xor     r8d, r8d; Reserved
0x140007dd0  mov     [rsp+68h+lpData], rbx; unsigned int
0x140007dd5  mov     rcx, rsi; hKey
0x140007dd8  call    cs:__imp_RegSetValueExW
0x140007dde  test    eax, eax
0x140007de0  jnz     loc_140007EE7
0x140007de6  lea     ebp, [rax+0Bh]
0x140007de9  mov     [rsp+68h+cbData], 8; cbData
0x140007df1  lea     r15, [rbx+100h]
0x140007df8  mov     r9d, ebp; dwType
0x140007dfb  xor     r8d, r8d; Reserved
0x140007dfe  mov     [rsp+68h+lpData], r15; unsigned int
0x140007e03  lea     rdx, aMinimumabisupp; "MinimumABISupportVersion"
0x140007e0a  mov     rcx, rsi; hKey
0x140007e0d  call    cs:__imp_RegSetValueExW
0x140007e13  test    eax, eax
0x140007e15  jnz     loc_140007EFA
0x140007e1b  lea     r14, [rbx+108h]
0x140007e22  mov     [rsp+68h+cbData], 8; cbData
0x140007e2a  mov     r9d, ebp; dwType
0x140007e2d  mov     [rsp+68h+lpData], r14; unsigned int
0x140007e32  xor     r8d, r8d; Reserved
0x140007e35  lea     rdx, aMaximumabisupp; "MaximumABISupportVersion"
0x140007e3c  mov     rcx, rsi; hKey
0x140007e3f  call    cs:__imp_RegSetValueExW
0x140007e45  test    eax, eax
0x140007e47  jnz     loc_140007F0D
0x140007e4d  lea     rbp, [rbx+110h]
0x140007e54  mov     [rsp+68h+cbData], 8; cbData
0x140007e5c  lea     r9d, [rax+0Bh]; dwType
0x140007e60  mov     [rsp+68h+lpData], rbp; unsigned int
0x140007e65  xor     r8d, r8d; Reserved
0x140007e68  lea     rdx, aCompilerversio; "CompilerVersion"
0x140007e6f  mov     rcx, rsi; hKey
0x140007e72  call    cs:__imp_RegSetValueExW
0x140007e78  test    eax, eax
0x140007e7a  jnz     short loc_140007ED4
0x140007e7c  lea     rax, [rdi+28h]
0x140007e80  cmp     qword ptr [rax+18h], 7
0x140007e85  jbe     short loc_140007E8A
0x140007e87  mov     rax, [rax]
0x140007e8a  sub     rax, rbx
0x140007e8d  movzx   ecx, word ptr [rbx]
0x140007e90  movzx   edx, word ptr [rbx+rax]
0x140007e94  sub     ecx, edx
0x140007e96  jnz     short loc_140007EA0
0x140007e98  add     rbx, 2
0x140007e9c  test    edx, edx
0x140007e9e  jnz     short loc_140007E8D
0x140007ea0  test    ecx, ecx
0x140007ea2  jnz     short loc_140007EC3
0x140007ea4  mov     rax, [rdi+48h]
0x140007ea8  cmp     [r15], rax
0x140007eab  jnz     short loc_140007EC3
0x140007ead  mov     rax, [rdi+50h]
0x140007eb1  cmp     [r14], rax
0x140007eb4  jnz     short loc_140007EC3
0x140007eb6  mov     rax, [rdi+58h]
0x140007eba  cmp     [rbp+0], rax
0x140007ebe  setnz   al
0x140007ec1  jmp     short loc_140007EC5
0x140007ec3  mov     al, 1
0x140007ec5  add     rsp, 30h
0x140007ec9  pop     r15
0x140007ecb  pop     r14
0x140007ecd  pop     r12
0x140007ecf  pop     rdi
0x140007ed0  pop     rsi
0x140007ed1  pop     rbp
0x140007ed2  pop     rbx
0x140007ed3  retn
0x140007ed4  mov     rcx, [rsp+68h]; this
0x140007ed9  mov     r9d, eax; char *
0x140007edc  mov     edx, 152h; void *
0x140007ee1  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x140007ee7  mov     rcx, [rsp+68h]; this
0x140007eec  mov     r9d, eax; char *
0x140007eef  mov     edx, 15Dh; void *
0x140007ef4  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x140007efa  mov     rcx, [rsp+68h]; this
0x140007eff  mov     r9d, eax; char *
0x140007f02  mov     edx, 152h; void *
0x140007f07  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x140007f0d  mov     rcx, [rsp+68h]; this
0x140007f12  mov     r9d, eax; char *
0x140007f15  mov     edx, 152h; void *
0x140007f1a  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
