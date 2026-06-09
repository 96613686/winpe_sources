# PersistRegStore::GetListOrder(ushort * *,ulong *)

- ea: `0x180027c90`
- end: `0x180027e7b`
- name: `?GetListOrder@PersistRegStore@@UEAAJPEAPEAGPEAK@Z`
- size: `491`
- prototype: `__int64 __fastcall(HKEY *this, unsigned __int16 **, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180027c90`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027d0b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027d87`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027d0b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180027d87`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027e37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027e51`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027e37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027e51`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027d4a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180027d4a`
- `DMCmnUtils!CopyString` at `0x180027dff`
- `DMCmnUtils!CopyString` at `0x180027dff`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PersistRegStore::GetListOrder(HKEY *this, unsigned __int16 **a2, unsigned int *a3)
{
  BYTE *lpData; // rbp
  signed int v7; // edi
  unsigned int v8; // r12d
  LSTATUS v9; // eax
  bool v10; // cc
  const unsigned __int16 *v11; // rbx
  __int64 v12; // rdx
  const unsigned __int16 *v13; // rax
  unsigned __int64 v14; // r14
  unsigned int v15; // ebp
  __int64 v16; // rbx
  DWORD cbData; // [rsp+78h] [rbp+10h] BYREF
  DWORD Type; // [rsp+88h] [rbp+20h] BYREF

  cbData = 0;
  Type = 0;
  lpData = 0;
  if ( !a2 || !a3 )
  {
    v7 = -2147467261;
    goto LABEL_28;
  }
  v8 = *a3;
  if ( !*a3 )
  {
LABEL_27:
    v7 = -2147024809;
    goto LABEL_28;
  }
  *a3 = 0;
  *a2 = 0;
  v7 = 0;
  v9 = RegQueryValueExW(this[2], L"PersistListOrder", 0, &Type, 0, &cbData);
  if ( v9 )
  {
    if ( v9 == 2 )
      goto LABEL_28;
    v10 = v9 <= 0;
    goto LABEL_8;
  }
  if ( Type != 7 )
  {
    v7 = -2147418113;
    goto LABEL_28;
  }
  lpData = (BYTE *)LocalAlloc(0x40u, cbData);
  if ( !lpData )
  {
    v7 = -2147024882;
    goto LABEL_28;
  }
  v9 = RegQueryValueExW(this[2], L"PersistListOrder", 0, &Type, lpData, &cbData);
  v10 = v9 <= 0;
  if ( !v9 )
  {
    v11 = (const unsigned __int16 *)lpData;
    if ( !*(_WORD *)lpData )
      goto LABEL_28;
    while ( v8 > *a3 )
    {
      v12 = 0x7FFFFFFF;
      v13 = v11;
      do
      {
        if ( !*v13 )
          break;
        ++v13;
        --v12;
      }
      while ( v12 );
      v7 = v12 == 0 ? 0x80070057 : 0;
      v14 = (0x7FFFFFFF - v12) & -(__int64)(v12 != 0);
      if ( !v12 )
        goto LABEL_28;
      if ( v14 > 0xFFFFFFFF )
      {
        v7 = -2147024362;
        goto LABEL_28;
      }
      v7 = CopyString(v11, v14, &a2[*a3]);
      if ( v7 >= 0 )
      {
        ++*a3;
        v11 += v14 + 1;
        if ( *v11 )
          continue;
      }
      goto LABEL_28;
    }
    goto LABEL_27;
  }
LABEL_8:
  if ( v10 )
    v7 = v9;
  else
    v7 = (unsigned __int16)v9 | 0x80070000;
LABEL_28:
  LocalFree(lpData);
  if ( v7 < 0 && *a3 )
  {
    v15 = 0;
    do
    {
      v16 = v15;
      LocalFree(a2[v15++]);
      a2[v16] = 0;
    }
    while ( v15 < *a3 );
    *a3 = 0;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180027c90  mov     rax, rsp
0x180027c93  mov     [rax+8], rbx
0x180027c97  push    rbp
0x180027c98  push    rsi
0x180027c99  push    rdi
0x180027c9a  push    r12
0x180027c9c  push    r13
0x180027c9e  push    r14
0x180027ca0  push    r15
0x180027ca2  sub     rsp, 30h
0x180027ca6  xor     r13d, r13d
0x180027ca9  mov     rsi, r8
0x180027cac  mov     [rax+10h], r13d
0x180027cb0  mov     r15, rdx
0x180027cb3  mov     [rax+20h], r13d
0x180027cb7  mov     rbx, rcx
0x180027cba  mov     ebp, r13d
0x180027cbd  test    rdx, rdx
0x180027cc0  jnz     short loc_180027CCC
0x180027cc2  mov     edi, 80004003h
0x180027cc7  jmp     loc_180027E34
0x180027ccc  test    rsi, rsi
0x180027ccf  jz      short loc_180027CC2
0x180027cd1  mov     r12d, [r8]
0x180027cd4  test    r12d, r12d
0x180027cd7  jz      loc_180027E2F
0x180027cdd  mov     [r8], r13d
0x180027ce0  lea     rax, [rsp+68h+cbData]
0x180027ce5  mov     [rdx], r13
0x180027ce8  lea     r9, [rsp+68h+Type]; lpType
0x180027cf0  mov     rcx, [rcx+10h]; hKey
0x180027cf4  lea     rdx, aPersistlistord; "PersistListOrder"
0x180027cfb  mov     [rsp+68h+lpcbData], rax; lpcbData
0x180027d00  xor     r8d, r8d; lpReserved
0x180027d03  mov     [rsp+68h+lpData], r13; lpData
0x180027d08  mov     edi, r13d
0x180027d0b  call    cs:__imp_RegQueryValueExW
0x180027d11  test    eax, eax
0x180027d13  jz      short loc_180027D2D
0x180027d15  cmp     eax, 2
0x180027d18  jz      loc_180027E34
0x180027d1e  test    eax, eax
0x180027d20  jg      loc_180027E1D
0x180027d26  mov     edi, eax
0x180027d28  jmp     loc_180027E34
0x180027d2d  cmp     [rsp+68h+Type], 7
0x180027d35  jz      short loc_180027D41
0x180027d37  mov     edi, 8000FFFFh
0x180027d3c  jmp     loc_180027E34
0x180027d41  mov     edx, [rsp+68h+cbData]; uBytes
0x180027d45  mov     ecx, 40h ; '@'; uFlags
0x180027d4a  call    cs:__imp_LocalAlloc
0x180027d50  mov     rbp, rax
0x180027d53  test    rax, rax
0x180027d56  jnz     short loc_180027D62
0x180027d58  mov     edi, 8007000Eh
0x180027d5d  jmp     loc_180027E34
0x180027d62  mov     rcx, [rbx+10h]; hKey
0x180027d66  lea     rax, [rsp+68h+cbData]
0x180027d6b  mov     [rsp+68h+lpcbData], rax; lpcbData
0x180027d70  lea     r9, [rsp+68h+Type]; lpType
0x180027d78  xor     r8d, r8d; lpReserved
0x180027d7b  mov     [rsp+68h+lpData], rbp; lpData
0x180027d80  lea     rdx, aPersistlistord; "PersistListOrder"
0x180027d87  call    cs:__imp_RegQueryValueExW
0x180027d8d  test    eax, eax
0x180027d8f  jnz     short loc_180027D20
0x180027d91  mov     rbx, rbp
0x180027d94  cmp     [rbp+0], r13w
0x180027d99  jz      loc_180027E34
0x180027d9f  cmp     r12d, [rsi]
0x180027da2  jbe     loc_180027E2F
0x180027da8  mov     edx, 7FFFFFFFh
0x180027dad  mov     rax, rbx
0x180027db0  cmp     [rax], r13w
0x180027db4  jz      short loc_180027DC0
0x180027db6  add     rax, 2
0x180027dba  sub     rdx, 1
0x180027dbe  jnz     short loc_180027DB0
0x180027dc0  mov     rax, rdx
0x180027dc3  mov     ecx, 7FFFFFFFh
0x180027dc8  neg     rax
0x180027dcb  mov     rax, rdx
0x180027dce  sbb     edi, edi
0x180027dd0  sub     rcx, rdx
0x180027dd3  not     edi
0x180027dd5  and     edi, 80070057h
0x180027ddb  neg     rax
0x180027dde  sbb     r14, r14
0x180027de1  and     r14, rcx
0x180027de4  test    rdx, rdx
0x180027de7  jz      short loc_180027E34
0x180027de9  mov     eax, 0FFFFFFFFh
0x180027dee  cmp     r14, rax
0x180027df1  ja      short loc_180027E28
0x180027df3  mov     eax, [rsi]
0x180027df5  mov     edx, r14d
0x180027df8  mov     rcx, rbx
0x180027dfb  lea     r8, [r15+rax*8]
0x180027dff  call    cs:__imp_?CopyString@@YAJPEBGKPEAPEAG@Z; CopyString(ushort const *,ulong,ushort * *)
0x180027e05  mov     edi, eax
0x180027e07  test    eax, eax
0x180027e09  js      short loc_180027E34
0x180027e0b  inc     dword ptr [rsi]
0x180027e0d  lea     rbx, [rbx+r14*2]
0x180027e11  add     rbx, 2
0x180027e15  cmp     [rbx], r13w
0x180027e19  jnz     short loc_180027D9F
0x180027e1b  jmp     short loc_180027E34
0x180027e1d  movzx   edi, ax
0x180027e20  or      edi, 80070000h
0x180027e26  jmp     short loc_180027E34
0x180027e28  mov     edi, 80070216h
0x180027e2d  jmp     short loc_180027E34
0x180027e2f  mov     edi, 80070057h
0x180027e34  mov     rcx, rbp; hMem
0x180027e37  call    cs:__imp_LocalFree
0x180027e3d  test    edi, edi
0x180027e3f  jns     short loc_180027E64
0x180027e41  cmp     [rsi], r13d
0x180027e44  jz      short loc_180027E64
0x180027e46  mov     ebp, r13d
0x180027e49  jbe     short loc_180027E61
0x180027e4b  mov     ebx, ebp
0x180027e4d  mov     rcx, [r15+rbx*8]; hMem
0x180027e51  call    cs:__imp_LocalFree
0x180027e57  inc     ebp
0x180027e59  mov     [r15+rbx*8], r13
0x180027e5d  cmp     ebp, [rsi]
0x180027e5f  jb      short loc_180027E4B
0x180027e61  mov     [rsi], r13d
0x180027e64  mov     rbx, [rsp+68h+arg_0]
0x180027e69  mov     eax, edi
0x180027e6b  add     rsp, 30h
0x180027e6f  pop     r15
0x180027e71  pop     r14
0x180027e73  pop     r13
0x180027e75  pop     r12
0x180027e77  pop     rdi
0x180027e78  pop     rsi
0x180027e79  pop     rbp
0x180027e7a  retn
```
