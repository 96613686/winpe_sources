# CopyICINFOTo16bit

- ea: `0x1800070f0`
- end: `0x18000725a`
- name: `CopyICINFOTo16bit`
- size: `362`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1800074a0`
- `0x1800076c4`

## callees

- `0x1800014b0`
- `0x180001d62`
- `0x1800070f0`
- `0x180007260`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x180007151`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x1800071b2`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x180007215`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x180007151`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x1800071b2`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x180007215`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180007163`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180007177`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800071c4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800071d8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180007163`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180007177`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800071c4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800071d8`

## pseudocode

```c
__int64 __fastcall CopyICINFOTo16bit(unsigned int a1, __int64 a2, unsigned int a3)
{
  __int64 v4; // rsi
  __int128 v6; // xmm0
  int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // edx
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rdx
  unsigned int v13; // eax
  unsigned int v14; // edx
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rdx
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v20; // [rsp+24h] [rbp-DCh] BYREF
  int v21; // [rsp+34h] [rbp-CCh]
  CHAR String[16]; // [rsp+38h] [rbp-C8h] BYREF
  CHAR v23[128]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v24[136]; // [rsp+C8h] [rbp-38h] BYREF

  v4 = a1;
  memset_0(&v20, 0, 0x124u);
  v6 = *(_OWORD *)(a2 + 4);
  v19 = *(_DWORD *)a2;
  v7 = *(_DWORD *)(a2 + 20);
  v20 = v6;
  v21 = v7;
  _o_wcstombs(String, a2 + 24, 16);
  if ( String[0] )
  {
    v8 = lstrlenA(String);
    v9 = 11;
    if ( v8 <= 0xB )
      v9 = lstrlenA(String);
    v10 = v9;
    v11 = v9 + 1;
    String[v10] = 91;
    String[v11] = 51;
    v12 = (unsigned int)(v11 + 1);
    String[v12] = 50;
    LODWORD(v12) = v12 + 1;
    String[(unsigned int)v12] = 93;
    String[(unsigned int)(v12 + 1)] = 0;
  }
  _o_wcstombs(v23, a2 + 56, 128);
  if ( v23[0] )
  {
    v13 = lstrlenA(v23);
    v14 = 123;
    if ( v13 <= 0x7B )
      v14 = lstrlenA(v23);
    v15 = v14;
    v16 = v14 + 1;
    v23[v15] = 91;
    v23[v16] = 51;
    v17 = (unsigned int)(v16 + 1);
    v23[v17] = 50;
    LODWORD(v17) = v17 + 1;
    v23[(unsigned int)v17] = 93;
    v23[(unsigned int)(v17 + 1)] = 0;
  }
  _o_wcstombs(v24, a2 + 312, 128);
  v19 = 296;
  if ( a3 >= 0x128 )
    a3 = 296;
  CopyTo16Bit(v4, &v19, a3);
  return a3;
}

```

## disassembly

```asm
0x1800070f0  mov     [rsp-8+arg_18], rbx
0x1800070f5  push    rbp
0x1800070f6  push    rsi
0x1800070f7  push    rdi
0x1800070f8  lea     rbp, [rsp-60h]
0x1800070fd  sub     rsp, 160h
0x180007104  mov     rax, cs:__security_cookie
0x18000710b  xor     rax, rsp
0x18000710e  mov     [rbp+70h+var_20], rax
0x180007112  mov     ebx, r8d
0x180007115  mov     esi, ecx
0x180007117  mov     rdi, rdx
0x18000711a  lea     rcx, [rsp+170h+var_14C]; void *
0x18000711f  xor     edx, edx; Val
0x180007121  mov     r8d, 124h; Size
0x180007127  call    memset_0
0x18000712c  mov     eax, [rdi]
0x18000712e  lea     rdx, [rdi+18h]
0x180007132  movups  xmm0, xmmword ptr [rdi+4]
0x180007136  mov     [rsp+170h+var_150], eax
0x18000713a  lea     rcx, [rsp+170h+String]
0x18000713f  mov     eax, [rdi+14h]
0x180007142  mov     r8d, 10h
0x180007148  movups  [rsp+170h+var_14C], xmm0
0x18000714d  mov     [rsp+170h+var_13C], eax
0x180007151  call    cs:__imp__o_wcstombs
0x180007157  cmp     [rsp+170h+String], 0
0x18000715c  jz      short loc_1800071A3
0x18000715e  lea     rcx, [rsp+170h+String]; lpString
0x180007163  call    cs:__imp_lstrlenA
0x180007169  mov     edx, 0Bh
0x18000716e  cmp     eax, edx
0x180007170  ja      short loc_18000717F
0x180007172  lea     rcx, [rsp+170h+String]; lpString
0x180007177  call    cs:__imp_lstrlenA
0x18000717d  mov     edx, eax
0x18000717f  mov     ecx, edx
0x180007181  inc     edx
0x180007183  mov     [rsp+rcx+170h+String], 5Bh ; '['
0x180007188  mov     [rsp+rdx+170h+String], 33h ; '3'
0x18000718d  inc     edx
0x18000718f  mov     [rsp+rdx+170h+String], 32h ; '2'
0x180007194  inc     edx
0x180007196  lea     eax, [rdx+1]
0x180007199  mov     [rsp+rdx+170h+String], 5Dh ; ']'
0x18000719e  mov     [rsp+rax+170h+String], 0
0x1800071a3  lea     rdx, [rdi+38h]
0x1800071a7  mov     r8d, 80h
0x1800071ad  lea     rcx, [rsp+170h+var_128]
0x1800071b2  call    cs:__imp__o_wcstombs
0x1800071b8  cmp     [rsp+170h+var_128], 0
0x1800071bd  jz      short loc_180007204
0x1800071bf  lea     rcx, [rsp+170h+var_128]; lpString
0x1800071c4  call    cs:__imp_lstrlenA
0x1800071ca  mov     edx, 7Bh ; '{'
0x1800071cf  cmp     eax, edx
0x1800071d1  ja      short loc_1800071E0
0x1800071d3  lea     rcx, [rsp+170h+var_128]; lpString
0x1800071d8  call    cs:__imp_lstrlenA
0x1800071de  mov     edx, eax
0x1800071e0  mov     ecx, edx
0x1800071e2  inc     edx
0x1800071e4  mov     [rsp+rcx+170h+var_128], 5Bh ; '['
0x1800071e9  mov     [rsp+rdx+170h+var_128], 33h ; '3'
0x1800071ee  inc     edx
0x1800071f0  mov     [rsp+rdx+170h+var_128], 32h ; '2'
0x1800071f5  inc     edx
0x1800071f7  lea     eax, [rdx+1]
0x1800071fa  mov     [rsp+rdx+170h+var_128], 5Dh ; ']'
0x1800071ff  mov     [rsp+rax+170h+var_128], 0
0x180007204  lea     rdx, [rdi+138h]
0x18000720b  mov     r8d, 80h
0x180007211  lea     rcx, [rbp+70h+var_A8]
0x180007215  call    cs:__imp__o_wcstombs
0x18000721b  mov     eax, 128h
0x180007220  lea     rdx, [rsp+170h+var_150]
0x180007225  cmp     ebx, eax
0x180007227  mov     [rsp+170h+var_150], eax
0x18000722b  mov     rcx, rsi
0x18000722e  cmovnb  ebx, eax
0x180007231  mov     r8d, ebx
0x180007234  call    CopyTo16Bit
0x180007239  mov     eax, ebx
0x18000723b  mov     rcx, [rbp+70h+var_20]
0x18000723f  xor     rcx, rsp; StackCookie
0x180007242  call    __security_check_cookie
0x180007247  mov     rbx, [rsp+170h+arg_18]
0x18000724f  add     rsp, 160h
0x180007256  pop     rdi
0x180007257  pop     rsi
0x180007258  pop     rbp
0x180007259  retn
```
