# GetDocIdSubKeys

- ea: `0x14005d214`
- end: `0x14005d464`
- name: `GetDocIdSubKeys`
- size: `592`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140058a5c`

## callees

- `0x140003eb4`
- `0x14005d214`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14005d377`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14005d377`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14005d293`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14005d293`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005d41b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005d42f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005d41b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14005d42f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14005d2d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14005d326`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14005d2d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14005d326`
- `OLEAUT32!__imp_SysAllocString` at `0x14005d38c`
- `OLEAUT32!__imp_SysAllocString` at `0x14005d38c`
- `OLEAUT32!__imp_SysFreeString` at `0x14005d3f9`
- `OLEAUT32!__imp_SysFreeString` at `0x14005d3f9`

## pseudocode

```c
__int64 __fastcall GetDocIdSubKeys(HKEY hKey, DWORD *a2, _QWORD *a3)
{
  DWORD v3; // r14d
  LSTATUS v7; // eax
  unsigned int v8; // ebx
  unsigned __int64 v9; // rax
  size_t v10; // rbx
  _QWORD *v11; // rax
  _QWORD *v12; // rsi
  _WORD *v13; // rdi
  DWORD v14; // ecx
  unsigned __int64 v15; // rax
  DWORD v16; // eax
  LSTATUS v17; // eax
  BSTR v18; // rax
  DWORD v19; // eax
  OLECHAR *v20; // rcx
  DWORD cchName[4]; // [rsp+60h] [rbp-10h] BYREF
  DWORD cSubKeys; // [rsp+B0h] [rbp+40h] BYREF
  DWORD v24; // [rsp+C8h] [rbp+58h] BYREF

  v3 = 0;
  cSubKeys = 0;
  v24 = 0;
  if ( !hKey || !a2 || !a3 )
    return (unsigned int)-2147024809;
  *a2 = 0;
  *a3 = 0;
  v7 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &v24, 0, 0, 0, 0, 0, 0);
  v8 = v7;
  if ( v7 )
  {
    if ( v7 > 0 )
      return (unsigned __int16)v7 | 0x80070000;
    return v8;
  }
  v9 = 8LL * cSubKeys;
  if ( v9 > 0xFFFFFFFF )
    return (unsigned int)-2147024362;
  v10 = (unsigned int)v9;
  v11 = CoTaskMemAlloc((unsigned int)v9);
  v12 = v11;
  if ( !v11 )
    return (unsigned int)-2147024882;
  v13 = 0;
  memset_0(v11, 0, v10);
  v14 = v24 + 1;
  if ( v24 + 1 < v24 )
  {
    v24 = -1;
    goto LABEL_23;
  }
  ++v24;
  v15 = 2LL * v14;
  if ( v15 > 0xFFFFFFFF )
  {
LABEL_23:
    v8 = -2147024362;
    goto LABEL_24;
  }
  v13 = CoTaskMemAlloc((unsigned int)v15);
  if ( v13 )
  {
    v16 = cSubKeys;
    if ( !cSubKeys )
    {
LABEL_18:
      *a2 = v16;
      v8 = 0;
      *a3 = v12;
LABEL_29:
      CoTaskMemFree(v13);
      return v8;
    }
    while ( 1 )
    {
      cchName[0] = v24;
      *v13 = 0;
      v17 = RegEnumKeyExW(hKey, v3, v13, cchName, 0, 0, 0, 0);
      v8 = v17;
      if ( v17 )
        break;
      v18 = SysAllocString(v13);
      v12[v3] = v18;
      if ( !v18 )
      {
        v8 = -2147024882;
        v3 = 0;
        goto LABEL_24;
      }
      v16 = cSubKeys;
      if ( ++v3 >= cSubKeys )
        goto LABEL_18;
    }
    v3 = 0;
    if ( v17 > 0 )
      v8 = (unsigned __int16)v17 | 0x80070000;
  }
  else
  {
    v8 = -2147024882;
  }
LABEL_24:
  v19 = cSubKeys;
  if ( cSubKeys )
  {
    do
    {
      v20 = (OLECHAR *)v12[v3];
      if ( v20 )
      {
        SysFreeString(v20);
        v12[v3] = 0;
        v19 = cSubKeys;
      }
      ++v3;
    }
    while ( v3 < v19 );
  }
  CoTaskMemFree(v12);
  if ( v13 )
    goto LABEL_29;
  return v8;
}

```

## disassembly

```asm
0x14005d214  mov     r11, rsp
0x14005d217  mov     [r11+10h], rbx
0x14005d21b  push    rbp
0x14005d21c  push    rsi
0x14005d21d  push    rdi
0x14005d21e  push    r12
0x14005d220  push    r13
0x14005d222  push    r14
0x14005d224  push    r15
0x14005d226  mov     rbp, rsp
0x14005d229  sub     rsp, 70h
0x14005d22d  xor     r14d, r14d
0x14005d230  mov     r15, r8
0x14005d233  mov     [rbp+cSubKeys], r14d
0x14005d237  mov     r12, rdx
0x14005d23a  mov     [rbp+arg_18], r14d
0x14005d23e  mov     r13, rcx
0x14005d241  test    rcx, rcx
0x14005d244  jz      loc_14005D444
0x14005d24a  test    rdx, rdx
0x14005d24d  jz      loc_14005D444
0x14005d253  test    r8, r8
0x14005d256  jz      loc_14005D444
0x14005d25c  mov     [r11-50h], r14
0x14005d260  lea     rax, [rbp+arg_18]
0x14005d264  mov     [r11-58h], r14
0x14005d268  xor     r9d, r9d; lpReserved
0x14005d26b  mov     [r11-60h], r14
0x14005d26f  mov     [r11-68h], r14
0x14005d273  mov     [r11-70h], r14
0x14005d277  mov     [r11-78h], r14
0x14005d27b  mov     [r11-80h], rax
0x14005d27f  lea     rax, [rbp+cSubKeys]
0x14005d283  mov     [rdx], r14d
0x14005d286  xor     edx, edx; lpClass
0x14005d288  mov     [r8], r14
0x14005d28b  xor     r8d, r8d; lpcchClass
0x14005d28e  mov     [rsp+70h+lpcSubKeys], rax; lpcSubKeys
0x14005d293  call    cs:__imp_RegQueryInfoKeyW
0x14005d29a  nop     dword ptr [rax+rax+00h]
0x14005d29f  mov     ebx, eax
0x14005d2a1  test    eax, eax
0x14005d2a3  jz      short loc_14005D2B9
0x14005d2a5  jle     loc_14005D449
0x14005d2ab  movzx   ebx, ax
0x14005d2ae  or      ebx, 80070000h
0x14005d2b4  jmp     loc_14005D449
0x14005d2b9  mov     eax, [rbp+cSubKeys]
0x14005d2bc  mov     ecx, 0FFFFFFFFh
0x14005d2c1  shl     rax, 3
0x14005d2c5  cmp     rax, rcx
0x14005d2c8  ja      loc_14005D43D
0x14005d2ce  mov     ecx, eax; cb
0x14005d2d0  mov     ebx, eax
0x14005d2d2  call    cs:__imp_CoTaskMemAlloc
0x14005d2d9  nop     dword ptr [rax+rax+00h]
0x14005d2de  mov     rsi, rax
0x14005d2e1  test    rax, rax
0x14005d2e4  jnz     short loc_14005D2F0
0x14005d2e6  mov     ebx, 8007000Eh
0x14005d2eb  jmp     loc_14005D449
0x14005d2f0  mov     r8, rbx; Size
0x14005d2f3  xor     edx, edx; Val
0x14005d2f5  mov     rcx, rsi; void *
0x14005d2f8  mov     rdi, r14
0x14005d2fb  call    memset_0
0x14005d300  mov     eax, [rbp+arg_18]
0x14005d303  lea     ecx, [rax+1]
0x14005d306  cmp     ecx, eax
0x14005d308  jb      loc_14005D3D9
0x14005d30e  mov     eax, ecx
0x14005d310  mov     [rbp+arg_18], ecx
0x14005d313  add     rax, rax
0x14005d316  mov     ecx, 0FFFFFFFFh
0x14005d31b  cmp     rax, rcx
0x14005d31e  ja      loc_14005D3E1
0x14005d324  mov     ecx, eax; cb
0x14005d326  call    cs:__imp_CoTaskMemAlloc
0x14005d32d  nop     dword ptr [rax+rax+00h]
0x14005d332  mov     rdi, rax
0x14005d335  test    rax, rax
0x14005d338  jnz     short loc_14005D344
0x14005d33a  mov     ebx, 8007000Eh
0x14005d33f  jmp     loc_14005D3E6
0x14005d344  mov     eax, [rbp+cSubKeys]
0x14005d347  test    eax, eax
0x14005d349  jz      short loc_14005D3B2
0x14005d34b  mov     eax, [rbp+arg_18]
0x14005d34e  lea     r9, [rbp+cchName]; lpcchName
0x14005d352  mov     [rbp+cchName], eax
0x14005d355  mov     r8, rdi; lpName
0x14005d358  xor     eax, eax
0x14005d35a  mov     edx, r14d; dwIndex
0x14005d35d  mov     [rsp+70h+lpftLastWriteTime], rax; lpftLastWriteTime
0x14005d362  mov     rcx, r13; hKey
0x14005d365  mov     [rsp+70h+lpcchClass], rax; lpcchClass
0x14005d36a  mov     [rsp+70h+lpClass], rax; lpClass
0x14005d36f  mov     [rsp+70h+lpcSubKeys], rax; lpReserved
0x14005d374  mov     [rdi], ax
0x14005d377  call    cs:__imp_RegEnumKeyExW
0x14005d37e  nop     dword ptr [rax+rax+00h]
0x14005d383  mov     ebx, eax
0x14005d385  test    eax, eax
0x14005d387  jnz     short loc_14005D3C7
0x14005d389  mov     rcx, rdi; psz
0x14005d38c  call    cs:__imp_SysAllocString
0x14005d393  nop     dword ptr [rax+rax+00h]
0x14005d398  mov     rcx, rax
0x14005d39b  mov     eax, r14d
0x14005d39e  mov     [rsi+rax*8], rcx
0x14005d3a2  test    rcx, rcx
0x14005d3a5  jz      short loc_14005D3BD
0x14005d3a7  mov     eax, [rbp+cSubKeys]
0x14005d3aa  inc     r14d
0x14005d3ad  cmp     r14d, eax
0x14005d3b0  jb      short loc_14005D34B
0x14005d3b2  mov     [r12], eax
0x14005d3b6  xor     ebx, ebx
0x14005d3b8  mov     [r15], rsi
0x14005d3bb  jmp     short loc_14005D42C
0x14005d3bd  mov     ebx, 8007000Eh
0x14005d3c2  xor     r14d, r14d
0x14005d3c5  jmp     short loc_14005D3E6
0x14005d3c7  xor     r14d, r14d
0x14005d3ca  test    eax, eax
0x14005d3cc  jle     short loc_14005D3E6
0x14005d3ce  movzx   ebx, ax
0x14005d3d1  or      ebx, 80070000h
0x14005d3d7  jmp     short loc_14005D3E6
0x14005d3d9  mov     ecx, 0FFFFFFFFh
0x14005d3de  mov     [rbp+arg_18], ecx
0x14005d3e1  mov     ebx, 80070216h
0x14005d3e6  mov     eax, [rbp+cSubKeys]
0x14005d3e9  test    eax, eax
0x14005d3eb  jz      short loc_14005D418
0x14005d3ed  mov     r15d, r14d
0x14005d3f0  mov     rcx, [rsi+r15*8]; bstrString
0x14005d3f4  test    rcx, rcx
0x14005d3f7  jz      short loc_14005D410
0x14005d3f9  call    cs:__imp_SysFreeString
0x14005d400  nop     dword ptr [rax+rax+00h]
0x14005d405  mov     qword ptr [rsi+r15*8], 0
0x14005d40d  mov     eax, [rbp+cSubKeys]
0x14005d410  inc     r14d
0x14005d413  cmp     r14d, eax
0x14005d416  jb      short loc_14005D3ED
0x14005d418  mov     rcx, rsi; pv
0x14005d41b  call    cs:__imp_CoTaskMemFree
0x14005d422  nop     dword ptr [rax+rax+00h]
0x14005d427  test    rdi, rdi
0x14005d42a  jz      short loc_14005D449
0x14005d42c  mov     rcx, rdi; pv
0x14005d42f  call    cs:__imp_CoTaskMemFree
0x14005d436  nop     dword ptr [rax+rax+00h]
0x14005d43b  jmp     short loc_14005D449
0x14005d43d  mov     ebx, 80070216h
0x14005d442  jmp     short loc_14005D449
0x14005d444  mov     ebx, 80070057h
0x14005d449  mov     eax, ebx
0x14005d44b  mov     rbx, [rsp+70h+arg_8]
0x14005d453  add     rsp, 70h
0x14005d457  pop     r15
0x14005d459  pop     r14
0x14005d45b  pop     r13
0x14005d45d  pop     r12
0x14005d45f  pop     rdi
0x14005d460  pop     rsi
0x14005d461  pop     rbp
0x14005d462  retn
```
