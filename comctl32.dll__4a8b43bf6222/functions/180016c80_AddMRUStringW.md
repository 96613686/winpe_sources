# AddMRUStringW

- ea: `0x180016c80`
- end: `0x180016ee8`
- name: `AddMRUStringW`
- size: `616`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180016c30`

## callees

- `0x180016c80`
- `0x180017a0c`
- `0x18002fed0`
- `0x18003a470`
- `0x18008e3b0`
- `0x180090020`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180016e00`
- `ADVAPI32!RegSetValueExW` at `0x180016ec1`
- `ADVAPI32!RegSetValueExW` at `0x180016e00`
- `ADVAPI32!RegSetValueExW` at `0x180016ec1`
- `KERNEL32!LocalFree` at `0x180016d3f`
- `KERNEL32!LocalFree` at `0x180016d52`
- `KERNEL32!LocalFree` at `0x180016d3f`
- `KERNEL32!LocalFree` at `0x180016d52`
- `KERNEL32!lstrlenW` at `0x180016dd8`
- `KERNEL32!lstrlenW` at `0x180016e55`
- `KERNEL32!lstrlenW` at `0x180016e93`
- `KERNEL32!lstrlenW` at `0x180016dd8`
- `KERNEL32!lstrlenW` at `0x180016e55`
- `KERNEL32!lstrlenW` at `0x180016e93`

## pseudocode

```c
__int64 __fastcall AddMRUStringW(__int64 a1, const WCHAR *a2)
{
  LPWSTR *v5; // rbx
  unsigned int v6; // r14d
  unsigned int v7; // ebp
  __int64 (__fastcall *v8)(HLOCAL, char *); // rax
  const WCHAR **v9; // rsi
  char v10; // r15
  int v11; // r15d
  void *v12; // rax
  const WCHAR *v13; // rdx
  char *v14; // r13
  int v15; // eax
  unsigned int v16; // esi
  unsigned __int16 v17; // si
  int v18; // eax
  WCHAR *i; // r14
  int v20; // eax
  int v21; // eax
  int ValueName; // [rsp+70h] [rbp+8h] BYREF
  HLOCAL hMem; // [rsp+80h] [rbp+18h]
  __int64 (__fastcall *v24)(HLOCAL, char *); // [rsp+88h] [rbp+20h]

  if ( !a1 )
    return 0xFFFFFFFFLL;
  v5 = (LPWSTR *)(a1 + 32);
  v6 = *(_DWORD *)(a1 + 4);
  v7 = 0;
  v8 = *(__int64 (__fastcall **)(HLOCAL, char *))(a1 + 8);
  v9 = (const WCHAR **)(a1 + 32);
  v10 = ~(unsigned __int8)(*(_DWORD *)a1 >> 1);
  v24 = v8;
  v11 = v10 & 1;
  if ( v6 )
  {
    do
    {
      if ( *v9 )
      {
        if ( (*(_BYTE *)a1 & 4) != 0 )
        {
          v12 = (void *)ProduceAFromW(0, a2);
          v13 = *v9;
          hMem = v12;
          v14 = (char *)ProduceAFromW(0, v13);
          ValueName = v24(hMem, v14);
          if ( (char *)hMem - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            LocalFree(hMem);
          if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
            LocalFree(v14);
          v15 = ValueName;
        }
        else
        {
          v15 = ((__int64 (__fastcall *)(const WCHAR *))v8)(a2);
        }
        if ( !v15 )
        {
          v17 = v7 + 97;
          goto LABEL_24;
        }
        v8 = v24;
      }
      ++v7;
      ++v9;
    }
    while ( v7 < v6 );
    v16 = 0;
    while ( *v5 )
    {
      ++v16;
      ++v5;
      if ( v16 >= v6 )
        goto LABEL_17;
    }
    v17 = v16 + 97;
  }
  else
  {
LABEL_17:
    v17 = *(_WORD *)(*(_QWORD *)(a1 + 24) + 2LL * (v6 - 1));
    v5 = (LPWSTR *)(a1 - 744 + 8LL * v17);
  }
  if ( Str_SetPtrW(v5, a2) )
  {
    v7 = v17 - 97;
    ValueName = v17;
    v18 = lstrlenW(a2);
    RegSetValueExW(*(HKEY *)(a1 + 16), (LPCWSTR)&ValueName, 0, 1u, (const BYTE *)a2, 2 * v18 + 2);
    v11 = 1;
  }
  else
  {
    v7 = -1;
  }
LABEL_24:
  for ( i = *(WCHAR **)(a1 + 24); *i; ++i )
  {
    if ( *i == v17 )
    {
      if ( i )
      {
        v20 = lstrlenW(i);
        StringCchCopyW(i, v20, i + 1);
      }
      break;
    }
  }
  if ( v7 != -1 )
  {
    memmove((void *)(*(_QWORD *)(a1 + 24) + 2LL), *(const void **)(a1 + 24), 2LL * *(unsigned int *)(a1 + 4));
    **(_WORD **)(a1 + 24) = v17;
  }
  if ( v11 )
  {
    v21 = lstrlenW(*(LPCWSTR *)(a1 + 24));
    RegSetValueExW(*(HKEY *)(a1 + 16), L"MRUList", 0, 1u, *(const BYTE **)(a1 + 24), 2 * v21 + 2);
    *(_DWORD *)a1 &= ~0x1000u;
  }
  else
  {
    *(_DWORD *)a1 |= 0x1000u;
  }
  return v7;
}

```

## disassembly

```asm
0x180016c80  mov     [rsp+arg_8], rbx
0x180016c85  push    rbp
0x180016c86  push    rsi
0x180016c87  push    rdi
0x180016c88  push    r12
0x180016c8a  push    r13
0x180016c8c  push    r14
0x180016c8e  push    r15
0x180016c90  sub     rsp, 30h
0x180016c94  xor     r13d, r13d
0x180016c97  mov     r12, rdx
0x180016c9a  mov     rdi, rcx
0x180016c9d  test    rcx, rcx
0x180016ca0  jnz     short loc_180016CAA
0x180016ca2  or      eax, 0FFFFFFFFh
0x180016ca5  jmp     loc_180016ED3
0x180016caa  mov     r15d, [rcx]
0x180016cad  lea     rbx, [rcx+20h]
0x180016cb1  mov     r14d, [rcx+4]
0x180016cb5  mov     ebp, r13d
0x180016cb8  mov     rax, [rcx+8]
0x180016cbc  mov     rsi, rbx
0x180016cbf  shr     r15d, 1
0x180016cc2  not     r15d
0x180016cc5  mov     [rsp+68h+arg_18], rax
0x180016ccd  and     r15d, 1
0x180016cd1  test    r14d, r14d
0x180016cd4  jz      loc_180016D95
0x180016cda  mov     rdx, [rsi]
0x180016cdd  test    rdx, rdx
0x180016ce0  jz      loc_180016D6F
0x180016ce6  test    byte ptr [rdi], 4
0x180016ce9  jz      loc_180016E0E
0x180016cef  mov     rdx, r12; lpWideCharStr
0x180016cf2  xor     ecx, ecx; CodePage
0x180016cf4  call    ProduceAFromW
0x180016cf9  mov     rdx, [rsi]; lpWideCharStr
0x180016cfc  xor     ecx, ecx; CodePage
0x180016cfe  mov     [rsp+68h+hMem], rax
0x180016d06  call    ProduceAFromW
0x180016d0b  mov     rcx, [rsp+68h+hMem]
0x180016d13  mov     r13, rax
0x180016d16  mov     rdx, rax
0x180016d19  mov     rax, [rsp+68h+arg_18]
0x180016d21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d26  mov     [rsp+68h+ValueName], eax
0x180016d2a  mov     rax, [rsp+68h+hMem]
0x180016d32  lea     rcx, [rax-1]
0x180016d36  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180016d3a  ja      short loc_180016D45
0x180016d3c  mov     rcx, rax; hMem
0x180016d3f  call    cs:__imp_LocalFree
0x180016d45  lea     rcx, [r13-1]
0x180016d49  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180016d4d  ja      short loc_180016D58
0x180016d4f  mov     rcx, r13; hMem
0x180016d52  call    cs:__imp_LocalFree
0x180016d58  mov     eax, [rsp+68h+ValueName]
0x180016d5c  xor     r13d, r13d
0x180016d5f  test    eax, eax
0x180016d61  jz      loc_180016E1B
0x180016d67  mov     rax, [rsp+68h+arg_18]
0x180016d6f  inc     ebp
0x180016d71  add     rsi, 8
0x180016d75  cmp     ebp, r14d
0x180016d78  jb      loc_180016CDA
0x180016d7e  mov     esi, r13d
0x180016d81  cmp     [rbx], r13
0x180016d84  jz      loc_180016E24
0x180016d8a  inc     esi
0x180016d8c  add     rbx, 8
0x180016d90  cmp     esi, r14d
0x180016d93  jb      short loc_180016D81
0x180016d95  mov     rax, [rdi+18h]
0x180016d99  lea     ecx, [r14-1]
0x180016d9d  lea     rbx, [rdi-2E8h]
0x180016da4  mov     r14d, 61h ; 'a'
0x180016daa  movzx   edx, word ptr [rax+rcx*2]
0x180016dae  movzx   esi, dx
0x180016db1  lea     rbx, [rbx+rdx*8]
0x180016db5  mov     rdx, r12; psz
0x180016db8  mov     rcx, rbx; ppsz
0x180016dbb  call    Str_SetPtrW
0x180016dc0  test    eax, eax
0x180016dc2  jz      short loc_180016E30
0x180016dc4  movzx   ebp, si
0x180016dc7  mov     rcx, r12; lpString
0x180016dca  sub     ebp, r14d
0x180016dcd  mov     word ptr [rsp+68h+ValueName], si
0x180016dd2  mov     word ptr [rsp+68h+ValueName+2], r13w
0x180016dd8  call    cs:__imp_lstrlenW
0x180016dde  mov     rcx, [rdi+10h]; hKey
0x180016de2  lea     rdx, [rsp+68h+ValueName]; lpValueName
0x180016de7  mov     r9d, 1; dwType
0x180016ded  xor     r8d, r8d; Reserved
0x180016df0  lea     eax, ds:2[rax*2]
0x180016df7  mov     [rsp+68h+cbData], eax; cbData
0x180016dfb  mov     [rsp+68h+lpData], r12; lpData
0x180016e00  call    cs:__imp_RegSetValueExW
0x180016e06  mov     r15d, 1
0x180016e0c  jmp     short loc_180016E33
0x180016e0e  mov     rcx, r12
0x180016e11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e16  jmp     loc_180016D5F
0x180016e1b  mov     esi, 61h ; 'a'
0x180016e20  add     esi, ebp
0x180016e22  jmp     short loc_180016E33
0x180016e24  mov     r14d, 61h ; 'a'
0x180016e2a  add     si, r14w
0x180016e2e  jmp     short loc_180016DB5
0x180016e30  or      ebp, 0FFFFFFFFh
0x180016e33  mov     r14, [rdi+18h]
0x180016e37  jmp     short loc_180016E42
0x180016e39  cmp     ax, si
0x180016e3c  jz      short loc_180016E4D
0x180016e3e  add     r14, 2
0x180016e42  movzx   eax, word ptr [r14]
0x180016e46  test    ax, ax
0x180016e49  jnz     short loc_180016E39
0x180016e4b  jmp     short loc_180016E6A
0x180016e4d  test    r14, r14
0x180016e50  jz      short loc_180016E6A
0x180016e52  mov     rcx, r14; lpString
0x180016e55  call    cs:__imp_lstrlenW
0x180016e5b  movsxd  rdx, eax; cchDest
0x180016e5e  lea     r8, [r14+2]; pszSrc
0x180016e62  mov     rcx, r14; pszDest
0x180016e65  call    StringCchCopyW
0x180016e6a  cmp     ebp, 0FFFFFFFFh
0x180016e6d  jz      short loc_180016E8A
0x180016e6f  mov     rdx, [rdi+18h]; Src
0x180016e73  mov     r8d, [rdi+4]
0x180016e77  add     r8, r8; Size
0x180016e7a  lea     rcx, [rdx+2]; void *
0x180016e7e  call    memmove
0x180016e83  mov     rax, [rdi+18h]
0x180016e87  mov     [rax], si
0x180016e8a  test    r15d, r15d
0x180016e8d  jz      short loc_180016ECD
0x180016e8f  mov     rcx, [rdi+18h]; lpString
0x180016e93  call    cs:__imp_lstrlenW
0x180016e99  mov     rcx, [rdi+10h]; hKey
0x180016e9d  lea     rdx, ValueName; "MRUList"
0x180016ea4  mov     r9d, 1; dwType
0x180016eaa  xor     r8d, r8d; Reserved
0x180016ead  lea     eax, ds:2[rax*2]
0x180016eb4  mov     [rsp+68h+cbData], eax; cbData
0x180016eb8  mov     rax, [rdi+18h]
0x180016ebc  mov     [rsp+68h+lpData], rax; lpData
0x180016ec1  call    cs:__imp_RegSetValueExW
0x180016ec7  btr     dword ptr [rdi], 0Ch
0x180016ecb  jmp     short loc_180016ED1
0x180016ecd  bts     dword ptr [rdi], 0Ch
0x180016ed1  mov     eax, ebp
0x180016ed3  mov     rbx, [rsp+68h+arg_8]
0x180016ed8  add     rsp, 30h
0x180016edc  pop     r15
0x180016ede  pop     r14
0x180016ee0  pop     r13
0x180016ee2  pop     r12
0x180016ee4  pop     rdi
0x180016ee5  pop     rsi
0x180016ee6  pop     rbp
0x180016ee7  retn
```
