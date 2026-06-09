# AddMRUData

- ea: `0x180016a10`
- end: `0x180016c2a`
- name: `AddMRUData`
- size: `538`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180016a10`
- `0x1800179c0`
- `0x180017a0c`
- `0x18008e3b0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180016b63`
- `ADVAPI32!RegSetValueExW` at `0x180016bfb`
- `ADVAPI32!RegSetValueExW` at `0x180016b63`
- `ADVAPI32!RegSetValueExW` at `0x180016bfb`
- `KERNEL32!lstrlenW` at `0x180016b8f`
- `KERNEL32!lstrlenW` at `0x180016bcd`
- `KERNEL32!lstrlenW` at `0x180016b8f`
- `KERNEL32!lstrlenW` at `0x180016bcd`
- `KERNEL32!LocalAlloc` at `0x180016aec`
- `KERNEL32!LocalAlloc` at `0x180016aec`
- `KERNEL32!LocalReAlloc` at `0x180016b09`
- `KERNEL32!LocalReAlloc` at `0x180016b09`

## pseudocode

```c
__int64 __fastcall AddMRUData(__int64 a1, void *a2, unsigned int a3)
{
  size_t cbData; // r13
  void *v4; // rax
  HLOCAL *v6; // rbx
  unsigned int v7; // r14d
  unsigned int v8; // ebp
  _QWORD *v9; // rsi
  BOOL v10; // r15d
  unsigned int v11; // esi
  WCHAR v12; // si
  int v13; // eax
  _DWORD *v14; // rax
  char *v15; // rcx
  const BYTE *lpData; // rbx
  HKEY v17; // rcx
  WCHAR *i; // r14
  int v19; // eax
  int v20; // eax
  WCHAR ValueName; // [rsp+70h] [rbp+8h] BYREF
  __int16 v23; // [rsp+72h] [rbp+Ah]
  void *Src; // [rsp+78h] [rbp+10h]

  Src = a2;
  cbData = a3;
  v4 = a2;
  if ( !a1 )
    return 0xFFFFFFFFLL;
  v6 = (HLOCAL *)(a1 + 32);
  v7 = *(_DWORD *)(a1 + 4);
  v8 = 0;
  v9 = (_QWORD *)(a1 + 32);
  v10 = (*(_DWORD *)a1 & 2) == 0;
  if ( !v7 )
  {
LABEL_7:
    if ( (*(_DWORD *)a1 & 0x8000) == 0 )
    {
      v11 = 0;
      if ( v7 )
      {
        while ( *v6 )
        {
          ++v11;
          ++v6;
          if ( v11 >= v7 )
            goto LABEL_11;
        }
        v12 = v11 + 97;
      }
      else
      {
LABEL_11:
        v12 = *(_WORD *)(*(_QWORD *)(a1 + 24) + 2LL * (v7 - 1));
        v6 = (HLOCAL *)(a1 - 744 + 8LL * v12);
      }
      v13 = cbData + 4;
      if ( (int)cbData + 4 >= (unsigned int)cbData )
      {
        v14 = *v6 ? LocalReAlloc(*v6, v13, 0x42u) : LocalAlloc(0x40u, v13);
        if ( v14 )
        {
          *v6 = v14;
          *v14 = cbData;
          v15 = (char *)*v6;
          lpData = (const BYTE *)Src;
          memmove(v15 + 4, Src, cbData);
          v17 = *(HKEY *)(a1 + 16);
          v8 = v12 - 97;
          ValueName = v12;
          v23 = 0;
          RegSetValueExW(v17, &ValueName, 0, 3u, lpData, cbData);
          v10 = 1;
          goto LABEL_20;
        }
      }
    }
    return 0xFFFFFFFFLL;
  }
  while ( !*v9 )
  {
LABEL_6:
    ++v8;
    ++v9;
    if ( v8 >= v7 )
      goto LABEL_7;
  }
  if ( !(unsigned int)MRUIsSameData(a1, *v9, v4, (unsigned int)cbData) )
  {
    v4 = Src;
    goto LABEL_6;
  }
  v12 = v8 + 97;
LABEL_20:
  for ( i = *(WCHAR **)(a1 + 24); *i; ++i )
  {
    if ( *i == v12 )
    {
      if ( i )
      {
        v19 = lstrlenW(i);
        StringCchCopyW(i, v19, i + 1);
      }
      break;
    }
  }
  if ( v8 != -1 )
  {
    memmove((void *)(*(_QWORD *)(a1 + 24) + 2LL), *(const void **)(a1 + 24), 2LL * *(unsigned int *)(a1 + 4));
    **(_WORD **)(a1 + 24) = v12;
  }
  if ( v10 )
  {
    v20 = lstrlenW(*(LPCWSTR *)(a1 + 24));
    RegSetValueExW(*(HKEY *)(a1 + 16), L"MRUList", 0, 1u, *(const BYTE **)(a1 + 24), 2 * v20 + 2);
    *(_DWORD *)a1 &= ~0x1000u;
  }
  else
  {
    *(_DWORD *)a1 |= 0x1000u;
  }
  return v8;
}

```

## disassembly

```asm
0x180016a10  mov     [rsp+arg_10], rbx
0x180016a15  mov     [rsp+Src], rdx
0x180016a1a  push    rbp
0x180016a1b  push    rsi
0x180016a1c  push    rdi
0x180016a1d  push    r12
0x180016a1f  push    r13
0x180016a21  push    r14
0x180016a23  push    r15
0x180016a25  sub     rsp, 30h
0x180016a29  mov     r13d, r8d
0x180016a2c  mov     rax, rdx
0x180016a2f  xor     r8d, r8d
0x180016a32  mov     rdi, rcx
0x180016a35  test    rcx, rcx
0x180016a38  jz      loc_180016C0F
0x180016a3e  mov     r15d, [rcx]
0x180016a41  lea     rbx, [rcx+20h]
0x180016a45  mov     r14d, [rcx+4]
0x180016a49  mov     ebp, r8d
0x180016a4c  shr     r15d, 1
0x180016a4f  mov     rsi, rbx
0x180016a52  not     r15d
0x180016a55  and     r15d, 1
0x180016a59  test    r14d, r14d
0x180016a5c  jz      short loc_180016A8B
0x180016a5e  mov     rdx, [rsi]
0x180016a61  test    rdx, rdx
0x180016a64  jz      short loc_180016A80
0x180016a66  mov     r9d, r13d
0x180016a69  mov     r8, rax
0x180016a6c  mov     rcx, rdi
0x180016a6f  call    MRUIsSameData
0x180016a74  xor     r8d, r8d
0x180016a77  test    eax, eax
0x180016a79  jnz     short loc_180016AF4
0x180016a7b  mov     rax, [rsp+68h+Src]
0x180016a80  inc     ebp
0x180016a82  add     rsi, 8
0x180016a86  cmp     ebp, r14d
0x180016a89  jb      short loc_180016A5E
0x180016a8b  test    dword ptr [rdi], 8000h
0x180016a91  jnz     loc_180016C0F
0x180016a97  mov     esi, r8d
0x180016a9a  mov     r12d, 61h ; 'a'
0x180016aa0  test    r14d, r14d
0x180016aa3  jz      short loc_180016AB5
0x180016aa5  cmp     [rbx], r8
0x180016aa8  jz      short loc_180016AFD
0x180016aaa  inc     esi
0x180016aac  add     rbx, 8
0x180016ab0  cmp     esi, r14d
0x180016ab3  jb      short loc_180016AA5
0x180016ab5  mov     rax, [rdi+18h]
0x180016ab9  lea     ecx, [r14-1]
0x180016abd  lea     rbx, [rdi-2E8h]
0x180016ac4  movzx   edx, word ptr [rax+rcx*2]
0x180016ac8  movzx   esi, dx
0x180016acb  lea     rbx, [rbx+rdx*8]
0x180016acf  lea     eax, [r13+4]
0x180016ad3  cmp     eax, r13d
0x180016ad6  jb      loc_180016C0F
0x180016adc  mov     rcx, [rbx]; hMem
0x180016adf  movsxd  rdx, eax; uBytes
0x180016ae2  test    rcx, rcx
0x180016ae5  jnz     short loc_180016B03
0x180016ae7  mov     ecx, 40h ; '@'; uFlags
0x180016aec  call    cs:__imp_LocalAlloc
0x180016af2  jmp     short loc_180016B0F
0x180016af4  mov     esi, 61h ; 'a'
0x180016af9  add     esi, ebp
0x180016afb  jmp     short loc_180016B6D
0x180016afd  add     si, r12w
0x180016b01  jmp     short loc_180016ACF
0x180016b03  mov     r8d, 42h ; 'B'; uFlags
0x180016b09  call    cs:__imp_LocalReAlloc
0x180016b0f  xor     r14d, r14d
0x180016b12  test    rax, rax
0x180016b15  jz      loc_180016C0F
0x180016b1b  mov     [rbx], rax
0x180016b1e  mov     r8, r13; Size
0x180016b21  mov     [rax], r13d
0x180016b24  mov     rcx, [rbx]
0x180016b27  mov     rbx, [rsp+68h+Src]
0x180016b2c  add     rcx, 4; void *
0x180016b30  mov     rdx, rbx; Src
0x180016b33  call    memmove
0x180016b38  mov     rcx, [rdi+10h]; hKey
0x180016b3c  lea     r9d, [r14+3]; dwType
0x180016b40  movzx   ebp, si
0x180016b43  lea     rdx, [rsp+68h+ValueName]; lpValueName
0x180016b48  sub     ebp, r12d
0x180016b4b  mov     [rsp+68h+cbData], r13d; cbData
0x180016b50  xor     r8d, r8d; Reserved
0x180016b53  mov     [rsp+68h+ValueName], si
0x180016b58  mov     [rsp+68h+arg_2], r14w
0x180016b5e  mov     [rsp+68h+lpData], rbx; lpData
0x180016b63  call    cs:__imp_RegSetValueExW
0x180016b69  lea     r15d, [r14+1]
0x180016b6d  mov     r14, [rdi+18h]
0x180016b71  jmp     short loc_180016B7C
0x180016b73  cmp     ax, si
0x180016b76  jz      short loc_180016B87
0x180016b78  add     r14, 2
0x180016b7c  movzx   eax, word ptr [r14]
0x180016b80  test    ax, ax
0x180016b83  jnz     short loc_180016B73
0x180016b85  jmp     short loc_180016BA4
0x180016b87  test    r14, r14
0x180016b8a  jz      short loc_180016BA4
0x180016b8c  mov     rcx, r14; lpString
0x180016b8f  call    cs:__imp_lstrlenW
0x180016b95  movsxd  rdx, eax; cchDest
0x180016b98  lea     r8, [r14+2]; pszSrc
0x180016b9c  mov     rcx, r14; pszDest
0x180016b9f  call    StringCchCopyW
0x180016ba4  cmp     ebp, 0FFFFFFFFh
0x180016ba7  jz      short loc_180016BC4
0x180016ba9  mov     rdx, [rdi+18h]; Src
0x180016bad  mov     r8d, [rdi+4]
0x180016bb1  add     r8, r8; Size
0x180016bb4  lea     rcx, [rdx+2]; void *
0x180016bb8  call    memmove
0x180016bbd  mov     rax, [rdi+18h]
0x180016bc1  mov     [rax], si
0x180016bc4  test    r15d, r15d
0x180016bc7  jz      short loc_180016C07
0x180016bc9  mov     rcx, [rdi+18h]; lpString
0x180016bcd  call    cs:__imp_lstrlenW
0x180016bd3  mov     rcx, [rdi+10h]; hKey
0x180016bd7  lea     rdx, ValueName; "MRUList"
0x180016bde  mov     r9d, 1; dwType
0x180016be4  xor     r8d, r8d; Reserved
0x180016be7  lea     eax, ds:2[rax*2]
0x180016bee  mov     [rsp+68h+cbData], eax; cbData
0x180016bf2  mov     rax, [rdi+18h]
0x180016bf6  mov     [rsp+68h+lpData], rax; lpData
0x180016bfb  call    cs:__imp_RegSetValueExW
0x180016c01  btr     dword ptr [rdi], 0Ch
0x180016c05  jmp     short loc_180016C0B
0x180016c07  bts     dword ptr [rdi], 0Ch
0x180016c0b  mov     eax, ebp
0x180016c0d  jmp     short loc_180016C12
0x180016c0f  or      eax, 0FFFFFFFFh
0x180016c12  mov     rbx, [rsp+68h+arg_10]
0x180016c1a  add     rsp, 30h
0x180016c1e  pop     r15
0x180016c20  pop     r14
0x180016c22  pop     r13
0x180016c24  pop     r12
0x180016c26  pop     rdi
0x180016c27  pop     rsi
0x180016c28  pop     rbp
0x180016c29  retn
```
