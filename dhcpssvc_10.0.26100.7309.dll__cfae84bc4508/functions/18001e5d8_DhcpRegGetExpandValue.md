# DhcpRegGetExpandValue

- ea: `0x18001e5d8`
- end: `0x18001e820`
- name: `DhcpRegGetExpandValue`
- size: `584`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001d818`
- `0x18006691c`

## callees

- `0x18001e5d8`
- `0x18001e828`
- `0x18008f540`
- `0x1800cc9b2`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18001e734`
- `ADVAPI32!RegSetValueExW` at `0x18001e734`
- `KERNEL32!HeapAlloc` at `0x18001e676`
- `KERNEL32!HeapAlloc` at `0x18001e6cc`
- `KERNEL32!HeapAlloc` at `0x18001e676`
- `KERNEL32!HeapAlloc` at `0x18001e6cc`
- `KERNEL32!ExpandEnvironmentStringsA` at `0x18001e753`
- `KERNEL32!ExpandEnvironmentStringsA` at `0x18001e753`
- `KERNEL32!GetLastError` at `0x18001e77e`
- `KERNEL32!GetLastError` at `0x18001e77e`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18001e6ee`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18001e6ee`
- `KERNEL32!HeapFree` at `0x18001e7a2`
- `KERNEL32!HeapFree` at `0x18001e7bf`
- `KERNEL32!HeapFree` at `0x18001e7dc`
- `KERNEL32!HeapFree` at `0x18001e7f9`
- `KERNEL32!HeapFree` at `0x18001e7a2`
- `KERNEL32!HeapFree` at `0x18001e7bf`
- `KERNEL32!HeapFree` at `0x18001e7dc`
- `KERNEL32!HeapFree` at `0x18001e7f9`

## string_xrefs

- `0x18001e691`: `DatabasePath`
- `0x18001e6a4`: `BackupDatabasePath`

## pseudocode

```c
__int64 __fastcall DhcpRegGetExpandValue(LPCWSTR lpValueName, DWORD a2, CHAR **a3)
{
  CHAR *v4; // r14
  CHAR *v5; // rbp
  BYTE *lpData; // r15
  DWORD Value; // ebx
  __int64 v8; // rax
  __int64 v9; // r12
  __int64 v10; // rdi
  DWORD v11; // edi
  WCHAR *v12; // rax
  DWORD v13; // eax
  DWORD v14; // eax

  *a3 = 0;
  v4 = 0;
  v5 = 0;
  lpData = 0;
  Value = DhcpRegGetValue(DhcpGlobalRegParam, lpValueName);
  if ( !Value )
  {
    v8 = DhcpUnicodeToOem(0);
    v4 = (CHAR *)v8;
    if ( !v8 )
    {
      Value = 8;
      goto LABEL_20;
    }
    v9 = -1;
    v10 = -1;
    do
      ++v10;
    while ( *(_BYTE *)(v8 + v10) );
    v11 = v10 + 261;
    v5 = (CHAR *)HeapAlloc(gDhcpHeap, 8u, v11);
    if ( !v5 )
      goto LABEL_7;
    if ( wcscmp_0(lpValueName, L"DatabasePath") && wcscmp_0(lpValueName, L"BackupDatabasePath") )
      goto LABEL_15;
    v12 = (WCHAR *)HeapAlloc(gDhcpHeap, 8u, 2LL * v11);
    lpData = (BYTE *)v12;
    if ( !v12 )
    {
LABEL_7:
      Value = 8;
      goto LABEL_20;
    }
    v13 = ExpandEnvironmentStringsW(0, v12, v11);
    if ( !v13 )
    {
LABEL_19:
      Value = GetLastError();
      goto LABEL_20;
    }
    if ( v13 > v11 )
    {
LABEL_18:
      Value = 208;
      goto LABEL_20;
    }
    do
      ++v9;
    while ( *(_WORD *)&lpData[2 * v9] );
    Value = RegSetValueExW(DhcpGlobalRegParam, lpValueName, 0, a2, lpData, 2 * v9 + 2);
    if ( !Value )
    {
LABEL_15:
      v14 = ExpandEnvironmentStringsA(v4, v5, v11);
      if ( v14 )
      {
        if ( v14 <= v11 )
        {
          *a3 = v5;
          v5 = 0;
          goto LABEL_20;
        }
        goto LABEL_18;
      }
      goto LABEL_19;
    }
  }
LABEL_20:
  if ( v4 )
    HeapFree(gDhcpHeap, 0, v4);
  if ( v5 )
    HeapFree(gDhcpHeap, 0, v5);
  if ( lpData )
    HeapFree(gDhcpHeap, 0, lpData);
  return Value;
}

```

## disassembly

```asm
0x18001e5d8  mov     rax, rsp
0x18001e5db  mov     [rax+8], rbx
0x18001e5df  mov     [rax+18h], r8
0x18001e5e3  mov     [rax+10h], edx
0x18001e5e6  push    rbp
0x18001e5e7  push    rsi
0x18001e5e8  push    rdi
0x18001e5e9  push    r12
0x18001e5eb  push    r13
0x18001e5ed  push    r14
0x18001e5ef  push    r15
0x18001e5f1  sub     rsp, 40h
0x18001e5f5  xor     esi, esi
0x18001e5f7  lea     r9, [rax+20h]
0x18001e5fb  mov     [r8], rsi
0x18001e5fe  mov     r13, rcx
0x18001e601  mov     r8d, edx
0x18001e604  mov     [rax+20h], rsi
0x18001e608  mov     rdx, rcx; lpValueName
0x18001e60b  mov     r14d, esi
0x18001e60e  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x18001e615  mov     ebp, esi
0x18001e617  mov     r15d, esi
0x18001e61a  call    DhcpRegGetValue
0x18001e61f  mov     ebx, eax
0x18001e621  test    eax, eax
0x18001e623  jnz     loc_18001E78C
0x18001e629  mov     rcx, [rsp+78h+lpSrc]; SourceString
0x18001e631  xor     edx, edx
0x18001e633  call    DhcpUnicodeToOem
0x18001e638  mov     r14, rax
0x18001e63b  test    rax, rax
0x18001e63e  jnz     short loc_18001E648
0x18001e640  lea     ebx, [rsi+8]
0x18001e643  jmp     loc_18001E78C
0x18001e648  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001e64c  mov     rdi, r12
0x18001e64f  inc     rdi
0x18001e652  cmp     [rax+rdi], sil
0x18001e656  jnz     short loc_18001E64F
0x18001e658  mov     rcx, cs:gDhcpHeap; hHeap
0x18001e65f  add     edi, 105h
0x18001e665  mov     eax, edi
0x18001e667  mov     esi, 8
0x18001e66c  mov     r8d, edi; dwBytes
0x18001e66f  mov     edx, esi; dwFlags
0x18001e671  mov     [rsp+78h+var_48], rax
0x18001e676  call    cs:__imp_HeapAlloc
0x18001e67d  nop     dword ptr [rax+rax+00h]
0x18001e682  mov     rbp, rax
0x18001e685  test    rax, rax
0x18001e688  jnz     short loc_18001E691
0x18001e68a  mov     ebx, esi
0x18001e68c  jmp     loc_18001E78C
0x18001e691  lea     rdx, aDatabasepath; "DatabasePath"
0x18001e698  mov     rcx, r13; String1
0x18001e69b  call    wcscmp_0
0x18001e6a0  test    eax, eax
0x18001e6a2  jz      short loc_18001E6BB
0x18001e6a4  lea     rdx, aBackupdatabase; "BackupDatabasePath"
0x18001e6ab  mov     rcx, r13; String1
0x18001e6ae  call    wcscmp_0
0x18001e6b3  test    eax, eax
0x18001e6b5  jnz     loc_18001E748
0x18001e6bb  mov     r8, [rsp+78h+var_48]
0x18001e6c0  mov     edx, esi; dwFlags
0x18001e6c2  mov     rcx, cs:gDhcpHeap; hHeap
0x18001e6c9  add     r8, r8; dwBytes
0x18001e6cc  call    cs:__imp_HeapAlloc
0x18001e6d3  nop     dword ptr [rax+rax+00h]
0x18001e6d8  mov     r15, rax
0x18001e6db  test    rax, rax
0x18001e6de  jz      short loc_18001E68A
0x18001e6e0  mov     rcx, [rsp+78h+lpSrc]; lpSrc
0x18001e6e8  mov     r8d, edi; nSize
0x18001e6eb  mov     rdx, rax; lpDst
0x18001e6ee  call    cs:__imp_ExpandEnvironmentStringsW
0x18001e6f5  nop     dword ptr [rax+rax+00h]
0x18001e6fa  xor     esi, esi
0x18001e6fc  test    eax, eax
0x18001e6fe  jz      short loc_18001E77E
0x18001e700  cmp     eax, edi
0x18001e702  ja      short loc_18001E777
0x18001e704  inc     r12
0x18001e707  cmp     [r15+r12*2], si
0x18001e70c  jnz     short loc_18001E704
0x18001e70e  mov     r9d, [rsp+78h+dwType]; dwType
0x18001e716  lea     eax, ds:2[r12*2]
0x18001e71e  mov     rcx, cs:DhcpGlobalRegParam; hKey
0x18001e725  xor     r8d, r8d; Reserved
0x18001e728  mov     [rsp+78h+cbData], eax; cbData
0x18001e72c  mov     rdx, r13; lpValueName
0x18001e72f  mov     [rsp+78h+lpData], r15; lpData
0x18001e734  call    cs:__imp_RegSetValueExW
0x18001e73b  nop     dword ptr [rax+rax+00h]
0x18001e740  mov     ebx, eax
0x18001e742  test    eax, eax
0x18001e744  jnz     short loc_18001E78C
0x18001e746  jmp     short loc_18001E74A
0x18001e748  xor     esi, esi
0x18001e74a  mov     r8d, edi; nSize
0x18001e74d  mov     rdx, rbp; lpDst
0x18001e750  mov     rcx, r14; lpSrc
0x18001e753  call    cs:__imp_ExpandEnvironmentStringsA
0x18001e75a  nop     dword ptr [rax+rax+00h]
0x18001e75f  test    eax, eax
0x18001e761  jz      short loc_18001E77E
0x18001e763  cmp     eax, edi
0x18001e765  ja      short loc_18001E777
0x18001e767  mov     rax, [rsp+78h+arg_10]
0x18001e76f  mov     [rax], rbp
0x18001e772  mov     rbp, rsi
0x18001e775  jmp     short loc_18001E78C
0x18001e777  mov     ebx, 0D0h
0x18001e77c  jmp     short loc_18001E78C
0x18001e77e  call    cs:__imp_GetLastError
0x18001e785  nop     dword ptr [rax+rax+00h]
0x18001e78a  mov     ebx, eax
0x18001e78c  mov     r8, [rsp+78h+lpSrc]; lpMem
0x18001e794  test    r8, r8
0x18001e797  jz      short loc_18001E7AE
0x18001e799  mov     rcx, cs:gDhcpHeap; hHeap
0x18001e7a0  xor     edx, edx; dwFlags
0x18001e7a2  call    cs:__imp_HeapFree
0x18001e7a9  nop     dword ptr [rax+rax+00h]
0x18001e7ae  test    r14, r14
0x18001e7b1  jz      short loc_18001E7CB
0x18001e7b3  mov     rcx, cs:gDhcpHeap; hHeap
0x18001e7ba  mov     r8, r14; lpMem
0x18001e7bd  xor     edx, edx; dwFlags
0x18001e7bf  call    cs:__imp_HeapFree
0x18001e7c6  nop     dword ptr [rax+rax+00h]
0x18001e7cb  test    rbp, rbp
0x18001e7ce  jz      short loc_18001E7E8
0x18001e7d0  mov     rcx, cs:gDhcpHeap; hHeap
0x18001e7d7  mov     r8, rbp; lpMem
0x18001e7da  xor     edx, edx; dwFlags
0x18001e7dc  call    cs:__imp_HeapFree
0x18001e7e3  nop     dword ptr [rax+rax+00h]
0x18001e7e8  test    r15, r15
0x18001e7eb  jz      short loc_18001E805
0x18001e7ed  mov     rcx, cs:gDhcpHeap; hHeap
0x18001e7f4  mov     r8, r15; lpMem
0x18001e7f7  xor     edx, edx; dwFlags
0x18001e7f9  call    cs:__imp_HeapFree
0x18001e800  nop     dword ptr [rax+rax+00h]
0x18001e805  mov     eax, ebx
0x18001e807  mov     rbx, [rsp+78h+arg_0]
0x18001e80f  add     rsp, 40h
0x18001e813  pop     r15
0x18001e815  pop     r14
0x18001e817  pop     r13
0x18001e819  pop     r12
0x18001e81b  pop     rdi
0x18001e81c  pop     rsi
0x18001e81d  pop     rbp
0x18001e81e  retn
```
