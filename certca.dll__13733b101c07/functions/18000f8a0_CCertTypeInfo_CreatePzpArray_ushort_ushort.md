# CCertTypeInfo::CreatePzpArray(ushort * *,ushort * * *)

- ea: `0x18000f8a0`
- end: `0x18000fab1`
- name: `?CreatePzpArray@CCertTypeInfo@@SAJPEAPEAGPEAPEAPEAG@Z`
- size: `529`
- prototype: `__int64 __fastcall(unsigned __int16 **, HLOCAL *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180002ef0`

## callees

- `0x180005f00`
- `0x180008610`
- `0x18000f8a0`
- `0x1800382c0`
- `0x180038380`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f9cd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f9cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fa75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000fa75`

## pseudocode

```c
__int64 __fastcall CCertTypeInfo::CreatePzpArray(unsigned __int16 **a1, HLOCAL *a2)
{
  int v3; // edx
  unsigned __int64 v5; // r12
  unsigned __int64 v6; // rsi
  unsigned int v7; // ebx
  __int64 v8; // rcx
  unsigned __int16 *v9; // rax
  _QWORD *v10; // r8
  __int64 v11; // rcx
  unsigned int v12; // edx
  unsigned int v13; // edx
  unsigned __int64 v14; // rcx
  __int64 v15; // rax
  unsigned __int16 **v16; // rax
  unsigned __int16 **v17; // r10
  unsigned __int16 **v18; // r11
  int v19; // ebp
  unsigned __int16 *v20; // r15
  __int64 v21; // rsi
  __int64 v22; // rdx
  _QWORD v24[1024]; // [rsp+30h] [rbp-2048h] BYREF

  *a2 = 0;
  v3 = 0;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  while ( 1 )
  {
    v8 = v3;
    v9 = a1[v8];
    if ( !v9 )
      break;
    if ( v6 >= 0x400 )
    {
      v7 = -2147024809;
      v13 = 552207144;
LABEL_31:
      CSPrintErrorLineFileData2(0, v13, v7, 0);
      goto LABEL_32;
    }
    v10 = &v24[v8];
    v11 = 4096;
    do
    {
      if ( !*v9 )
        break;
      ++v9;
      --v11;
    }
    while ( v11 );
    v7 = -2147024809;
    if ( v11 )
      v7 = 0;
    if ( v10 )
    {
      if ( !v11 )
        goto LABEL_14;
      ++v3;
      v5 += 4096 - v11 + 1;
      *v10 = 4096 - v11;
      ++v6;
    }
    else
    {
      if ( !v11 )
      {
LABEL_14:
        v12 = 552469288;
LABEL_27:
        CSPrintErrorLineFileData2(0, v12, v7, 0);
        if ( (v7 & 0x80000000) == 0 )
          return v7;
LABEL_32:
        LocalFree(*a2);
        *a2 = 0;
        return v7;
      }
      ++v3;
      v5 += MEMORY[0] + 1LL;
      ++v6;
    }
  }
  if ( v6 + 1 < v6
    || (v14 = 8 * (v6 + 1), !is_mul_ok(v6 + 1, 8u))
    || (v15 = 2 * v5, !is_mul_ok(2u, v5))
    || v15 + v14 < v14 )
  {
    v7 = -2147024362;
    v13 = 553124648;
    goto LABEL_31;
  }
  v16 = (unsigned __int16 **)LocalAlloc(0, v15 + v14);
  *a2 = v16;
  v17 = v16;
  if ( !v16 )
  {
    v7 = -2147024882;
    v13 = 553648936;
    goto LABEL_31;
  }
  v18 = &v16[v6];
  v19 = 0;
  v20 = (unsigned __int16 *)(v18 + 1);
  while ( 1 )
  {
    v21 = v19;
    if ( !a1[v21] )
      break;
    v17[v21] = v20;
    v7 = StringCchCopyW(v20, v5, a1[v21]);
    if ( v7 )
    {
      v12 = 554369832;
      goto LABEL_27;
    }
    v22 = v24[v19];
    v5 += -1 - v22;
    v20 += v22 + 1;
    ++v19;
  }
  *v18 = 0;
  return v7;
}

```

## disassembly

```asm
0x18000f8a0  push    rbx
0x18000f8a2  push    rsi
0x18000f8a3  push    rdi
0x18000f8a4  push    r12
0x18000f8a6  push    r13
0x18000f8a8  push    r14
0x18000f8aa  mov     eax, 2048h
0x18000f8af  call    _alloca_probe
0x18000f8b4  sub     rsp, rax
0x18000f8b7  mov     rax, cs:__security_cookie
0x18000f8be  xor     rax, rsp
0x18000f8c1  mov     [rsp+2078h+var_48], rax
0x18000f8c9  xor     r13d, r13d
0x18000f8cc  mov     [rsp+2078h+arg_10], rbp
0x18000f8d4  mov     [rdx], r13
0x18000f8d7  mov     rdi, rdx
0x18000f8da  mov     edx, r13d
0x18000f8dd  mov     [rsp+2078h+var_38], r15
0x18000f8e5  mov     r14, rcx
0x18000f8e8  mov     r12d, r13d
0x18000f8eb  mov     esi, r13d
0x18000f8ee  mov     ebx, r13d
0x18000f8f1  movsxd  rax, edx
0x18000f8f4  lea     rcx, ds:0[rax*8]
0x18000f8fc  mov     rax, [r14+rax*8]
0x18000f900  test    rax, rax
0x18000f903  jz      loc_18000F989
0x18000f909  cmp     rsi, 400h
0x18000f910  jnb     short loc_18000F97A
0x18000f912  lea     r8, [rsp+2078h+var_2048]
0x18000f917  add     r8, rcx
0x18000f91a  mov     ecx, 1000h
0x18000f91f  nop
0x18000f920  cmp     [rax], r13w
0x18000f924  jz      short loc_18000F930
0x18000f926  add     rax, 2
0x18000f92a  sub     rcx, 1
0x18000f92e  jnz     short loc_18000F920
0x18000f930  test    rcx, rcx
0x18000f933  mov     ebx, 80070057h
0x18000f938  cmovnz  ebx, r13d
0x18000f93c  test    r8, r8
0x18000f93f  jz      short loc_18000F95E
0x18000f941  test    rcx, rcx
0x18000f944  jz      short loc_18000F970
0x18000f946  inc     r12
0x18000f949  mov     eax, 1000h
0x18000f94e  sub     rax, rcx
0x18000f951  inc     edx
0x18000f953  add     r12, rax
0x18000f956  mov     [r8], rax
0x18000f959  inc     rsi
0x18000f95c  jmp     short loc_18000F8F1
0x18000f95e  test    rcx, rcx
0x18000f961  jz      short loc_18000F970
0x18000f963  inc     r12
0x18000f966  inc     edx
0x18000f968  add     r12, [r8]
0x18000f96b  inc     rsi
0x18000f96e  jmp     short loc_18000F8F1
0x18000f970  mov     edx, 20EE0328h
0x18000f975  jmp     loc_18000FA42
0x18000f97a  mov     ebx, 80070057h
0x18000f97f  mov     edx, 20EA0328h
0x18000f984  jmp     loc_18000FA65
0x18000f989  lea     rcx, [rsi+1]
0x18000f98d  cmp     rcx, rsi
0x18000f990  jb      loc_18000FA5B
0x18000f996  mov     eax, 8
0x18000f99b  mul     rcx
0x18000f99e  mov     rcx, rax
0x18000f9a1  test    rdx, rdx
0x18000f9a4  jnz     loc_18000FA5B
0x18000f9aa  mov     edx, 2
0x18000f9af  mov     rax, r12
0x18000f9b2  mul     rdx
0x18000f9b5  test    rdx, rdx
0x18000f9b8  jnz     loc_18000FA5B
0x18000f9be  lea     rdx, [rax+rcx]; uBytes
0x18000f9c2  cmp     rdx, rcx
0x18000f9c5  jb      loc_18000FA5B
0x18000f9cb  xor     ecx, ecx; uFlags
0x18000f9cd  call    cs:__imp_LocalAlloc
0x18000f9d3  mov     [rdi], rax
0x18000f9d6  mov     r10, rax
0x18000f9d9  test    rax, rax
0x18000f9dc  jnz     short loc_18000F9EA
0x18000f9de  mov     ebx, 8007000Eh
0x18000f9e3  mov     edx, 21000328h
0x18000f9e8  jmp     short loc_18000FA65
0x18000f9ea  lea     r11, [rax+rsi*8]
0x18000f9ee  mov     ebp, r13d
0x18000f9f1  lea     r15, [r11+8]
0x18000f9f5  movsxd  rax, ebp
0x18000f9f8  lea     rsi, ds:0[rax*8]
0x18000fa00  cmp     [rsi+r14], r13
0x18000fa04  jz      short loc_18000FA56
0x18000fa06  mov     [rsi+r10], r15
0x18000fa0a  mov     rdx, r12; unsigned __int64
0x18000fa0d  mov     r8, [rsi+r14]; unsigned __int16 *
0x18000fa11  mov     rcx, r15; unsigned __int16 *
0x18000fa14  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000fa19  mov     ebx, eax
0x18000fa1b  test    eax, eax
0x18000fa1d  jnz     short loc_18000FA3D
0x18000fa1f  mov     rdx, [rsp+rsi+2078h+var_2048]
0x18000fa24  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000fa2b  sub     rcx, rdx
0x18000fa2e  add     r12, rcx
0x18000fa31  lea     r15, [r15+rdx*2]
0x18000fa35  add     r15, 2
0x18000fa39  inc     ebp
0x18000fa3b  jmp     short loc_18000F9F5
0x18000fa3d  mov     edx, 210B0328h; unsigned int
0x18000fa42  mov     r9d, r13d; int
0x18000fa45  mov     rcx, r13; unsigned __int16 *
0x18000fa48  mov     r8d, ebx; int
0x18000fa4b  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000fa50  test    ebx, ebx
0x18000fa52  js      short loc_18000FA72
0x18000fa54  jmp     short loc_18000FA7E
0x18000fa56  mov     [r11], r13
0x18000fa59  jmp     short loc_18000FA7E
0x18000fa5b  mov     ebx, 80070216h
0x18000fa60  mov     edx, 20F80328h; unsigned int
0x18000fa65  xor     r9d, r9d; int
0x18000fa68  mov     r8d, ebx; int
0x18000fa6b  xor     ecx, ecx; unsigned __int16 *
0x18000fa6d  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000fa72  mov     rcx, [rdi]; hMem
0x18000fa75  call    cs:__imp_LocalFree
0x18000fa7b  mov     [rdi], r13
0x18000fa7e  mov     r15, [rsp+2078h+var_38]
0x18000fa86  mov     eax, ebx
0x18000fa88  mov     rbp, [rsp+2078h+arg_10]
0x18000fa90  mov     rcx, [rsp+2078h+var_48]
0x18000fa98  xor     rcx, rsp; StackCookie
0x18000fa9b  call    __security_check_cookie
0x18000faa0  add     rsp, 2048h
0x18000faa7  pop     r14
0x18000faa9  pop     r13
0x18000faab  pop     r12
0x18000faad  pop     rdi
0x18000faae  pop     rsi
0x18000faaf  pop     rbx
0x18000fab0  retn
```
