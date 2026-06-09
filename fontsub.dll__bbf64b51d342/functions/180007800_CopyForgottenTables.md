# CopyForgottenTables

- ea: `0x180007800`
- end: `0x1800079af`
- name: `CopyForgottenTables`
- size: `431`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180007fa4`

## callees

- `0x180007800`
- `0x18000f264`
- `0x180011538`
- `0x180011574`
- `0x1800198f8`
- `0x18001a3bc`
- `0x18001a578`
- `0x18001ac90`

## pseudocode

```c
__int64 __fastcall CopyForgottenTables(__int64 a1, __int64 a2, _DWORD *a3)
{
  unsigned int v3; // esi
  unsigned __int16 v7; // di
  __int64 v9; // rbx
  unsigned __int16 v10; // r14
  __int64 v11; // rcx
  unsigned __int16 i; // si
  unsigned int v13; // r8d
  _WORD v14[2]; // [rsp+40h] [rbp-30h] BYREF
  int v15; // [rsp+44h] [rbp-2Ch] BYREF
  char v16; // [rsp+48h] [rbp-28h]
  int v17; // [rsp+4Ch] [rbp-24h] BYREF
  __int64 v18; // [rsp+50h] [rbp-20h] BYREF
  int v19; // [rsp+58h] [rbp-18h]

  v3 = *(_DWORD *)(a2 + 12);
  v18 = 0;
  v19 = 0;
  v15 = 0;
  v16 = 0;
  v14[0] = 0;
  v17 = 0;
  if ( (unsigned __int16)ReadGeneric(a2, (__int64)&v18, 0xCu, (unsigned __int8 *)&OFFSET_TABLE_CONTROL, v3, v14) )
    return 1005;
  v7 = WORD2(v18);
  if ( WORD2(v18) > 0x3E8u )
    return 1006;
  v9 = Mem_Alloc(16LL * WORD2(v18));
  if ( !v9 )
    return 1005;
  v10 = ReadGenericRepeat(a2, v9, (unsigned __int8 *)&DIRECTORY_CONTROL, v3 + v14[0], &v17, v7, 0x10u);
  v11 = v9;
  if ( !v10 )
  {
    SortByOffset(v9, v7);
    for ( i = 0; i < v7; ++i )
    {
      if ( *(_DWORD *)(v9 + 16LL * i + 12) )
        break;
      if ( *(_DWORD *)(v9 + 16LL * i + 8) )
        break;
      v13 = *(_DWORD *)(v9 + 16LL * i);
      if ( v13 != 16843009 )
      {
        v16 = 0;
        v15 = HIBYTE(v13) | ((BYTE2(v13) | ((BYTE1(v13) | ((unsigned __int8)v13 << 8)) << 8)) << 8);
        v10 = CopyTableOver((_QWORD *)a2, a1, (__int64)&v15, a3);
        if ( v10 )
          break;
      }
    }
    v11 = v9;
  }
  Mem_Free(v11);
  return v10;
}

```

## disassembly

```asm
0x180007800  mov     [rsp-38h+arg_18], rbx
0x180007805  push    rbp
0x180007806  push    rsi
0x180007807  push    rdi
0x180007808  push    r12
0x18000780a  push    r13
0x18000780c  push    r14
0x18000780e  push    r15
0x180007810  mov     rbp, rsp
0x180007813  sub     rsp, 70h
0x180007817  mov     rax, cs:__security_cookie
0x18000781e  xor     rax, rsp
0x180007821  mov     [rbp+var_10], rax
0x180007825  mov     esi, [rdx+0Ch]
0x180007828  lea     r9, OFFSET_TABLE_CONTROL
0x18000782f  xor     eax, eax
0x180007831  mov     r15, rdx
0x180007834  mov     r13, r8
0x180007837  mov     [rbp+var_20], rax
0x18000783b  mov     [rbp+var_18], eax
0x18000783e  lea     rdx, [rbp+var_20]
0x180007842  mov     [rbp+var_2C], eax
0x180007845  mov     r12, rcx
0x180007848  lea     r8d, [rax+0Ch]
0x18000784c  mov     [rbp+var_28], al
0x18000784f  lea     rax, [rbp+var_30]
0x180007853  xor     r14d, r14d
0x180007856  mov     [rsp+70h+var_48], rax
0x18000785b  mov     rcx, r15
0x18000785e  mov     dword ptr [rsp+70h+var_50], esi
0x180007862  mov     [rbp+var_30], r14w
0x180007867  mov     [rbp+var_24], r14d
0x18000786b  call    ReadGeneric
0x180007870  test    ax, ax
0x180007873  jnz     loc_180007986
0x180007879  movzx   edi, word ptr [rbp+var_20+4]
0x18000787d  mov     eax, 3E8h
0x180007882  cmp     di, ax
0x180007885  jbe     short loc_180007891
0x180007887  mov     eax, 3EEh
0x18000788c  jmp     loc_18000798B
0x180007891  mov     rcx, rdi
0x180007894  shl     rcx, 4; Size
0x180007898  call    Mem_Alloc
0x18000789d  mov     rbx, rax
0x1800078a0  test    rax, rax
0x1800078a3  jz      loc_180007986
0x1800078a9  movzx   r9d, [rbp+var_30]
0x1800078ae  lea     rax, [rbp+var_24]
0x1800078b2  mov     [rsp+70h+var_40], 10h
0x1800078b9  lea     r8, DIRECTORY_CONTROL
0x1800078c0  add     r9d, esi
0x1800078c3  mov     word ptr [rsp+70h+var_48], di
0x1800078c8  mov     rdx, rbx
0x1800078cb  mov     [rsp+70h+var_50], rax
0x1800078d0  mov     rcx, r15
0x1800078d3  call    ReadGenericRepeat
0x1800078d8  movzx   r14d, ax
0x1800078dc  mov     rcx, rbx
0x1800078df  test    ax, ax
0x1800078e2  jz      short loc_1800078F2
0x1800078e4  call    Mem_Free
0x1800078e9  movzx   eax, r14w
0x1800078ed  jmp     loc_18000798B
0x1800078f2  movzx   edx, di
0x1800078f5  call    SortByOffset
0x1800078fa  xor     r9d, r9d
0x1800078fd  mov     esi, r9d
0x180007900  cmp     r9w, di
0x180007904  jnb     short loc_18000797E
0x180007906  movzx   eax, si
0x180007909  add     rax, rax
0x18000790c  cmp     [rbx+rax*8+0Ch], r9d
0x180007911  jnz     short loc_18000797E
0x180007913  cmp     [rbx+rax*8+8], r9d
0x180007918  jnz     short loc_18000797E
0x18000791a  mov     r8d, [rbx+rax*8]
0x18000791e  cmp     r8d, 1010101h
0x180007925  jz      short loc_180007976
0x180007927  movzx   edx, r8b
0x18000792b  mov     ecx, r8d
0x18000792e  shl     edx, 8
0x180007931  mov     eax, r8d
0x180007934  shr     eax, 8
0x180007937  movzx   eax, al
0x18000793a  or      edx, eax
0x18000793c  shr     ecx, 10h
0x18000793f  shl     edx, 8
0x180007942  movzx   eax, cl
0x180007945  mov     rcx, r15
0x180007948  or      edx, eax
0x18000794a  shr     r8d, 18h
0x18000794e  shl     edx, 8
0x180007951  or      edx, r8d
0x180007954  mov     [rbp+var_28], r9b
0x180007958  mov     [rbp+var_2C], edx
0x18000795b  lea     r8, [rbp+var_2C]
0x18000795f  mov     rdx, r12
0x180007962  mov     r9, r13
0x180007965  call    CopyTableOver
0x18000796a  xor     r9d, r9d
0x18000796d  movzx   r14d, ax
0x180007971  test    ax, ax
0x180007974  jnz     short loc_18000797E
0x180007976  inc     si
0x180007979  cmp     si, di
0x18000797c  jb      short loc_180007906
0x18000797e  mov     rcx, rbx
0x180007981  jmp     loc_1800078E4
0x180007986  mov     eax, 3EDh
0x18000798b  mov     rcx, [rbp+var_10]
0x18000798f  xor     rcx, rsp; StackCookie
0x180007992  call    __security_check_cookie
0x180007997  mov     rbx, [rsp+70h+arg_18]
0x18000799f  add     rsp, 70h
0x1800079a3  pop     r15
0x1800079a5  pop     r14
0x1800079a7  pop     r13
0x1800079a9  pop     r12
0x1800079ab  pop     rdi
0x1800079ac  pop     rsi
0x1800079ad  pop     rbp
0x1800079ae  retn
```
