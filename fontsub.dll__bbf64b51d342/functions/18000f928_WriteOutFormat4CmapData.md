# WriteOutFormat4CmapData

- ea: `0x18000f928`
- end: `0x18000fad1`
- name: `WriteOutFormat4CmapData`
- size: `425`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a8dc`
- `0x1800118bc`

## callees

- `0x18000f928`
- `0x18001a808`
- `0x18001aadc`

## pseudocode

```c
__int16 __fastcall WriteOutFormat4CmapData(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned __int16 a5,
        unsigned __int16 a6,
        unsigned int a7,
        _DWORD *a8)
{
  __int16 result; // ax
  unsigned __int16 v12; // bx
  unsigned int v13; // edi
  int v14; // ebp
  int v15; // ebx
  unsigned __int16 i; // di
  int v17; // ebx
  unsigned __int16 j; // di
  int v19; // ebx
  unsigned __int16 k; // di
  int v21; // ebx
  unsigned __int16 m; // di
  unsigned __int16 v23[36]; // [rsp+30h] [rbp-48h] BYREF

  v23[0] = 0;
  result = WriteGeneric((__int64)a1, a2, 0xEu, (unsigned __int8 *)&CMAP_FORMAT4_CONTROL, a7, v23);
  if ( !result )
  {
    v12 = 0;
    v13 = a7 + v23[0];
    while ( v12 < a5 )
    {
      result = WriteWord(a1, *(_WORD *)(a3 + 8LL * v12), v13 + 2 * v12);
      if ( result )
        return result;
      ++v12;
    }
    v14 = 2 * a5;
    result = WriteWord(a1, 0, v13 + v14);
    if ( !result )
    {
      v15 = v13 + v14 + 2;
      for ( i = 0; i < a5; ++i )
      {
        result = WriteWord(a1, *(_WORD *)(a3 + 8LL * i + 2), v15 + 2 * (unsigned int)i);
        if ( result )
          return result;
      }
      v17 = v14 + v15;
      for ( j = 0; j < a5; ++j )
      {
        result = WriteWord(a1, *(_WORD *)(a3 + 8LL * j + 4), v17 + 2 * (unsigned int)j);
        if ( result )
          return result;
      }
      v19 = v14 + v17;
      for ( k = 0; k < a5; ++k )
      {
        result = WriteWord(a1, *(_WORD *)(a3 + 8LL * k + 6), v19 + 2 * (unsigned int)k);
        if ( result )
          return result;
      }
      v21 = v14 + v19;
      for ( m = 0; m < a6; ++m )
      {
        result = WriteWord(a1, *(_WORD *)(a4 + 2LL * m), v21 + 2 * (unsigned int)m);
        if ( result )
          return result;
      }
      *a8 = v21 + 2 * a6 - a7;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000f928  push    rbx
0x18000f92a  push    rbp
0x18000f92b  push    rdi
0x18000f92c  push    r12
0x18000f92e  push    r13
0x18000f930  push    r14
0x18000f932  push    r15
0x18000f934  sub     rsp, 40h
0x18000f938  mov     r12d, [rsp+78h+arg_30]
0x18000f940  lea     rax, [rsp+78h+var_48]
0x18000f945  xor     ebp, ebp
0x18000f947  mov     [rsp+78h+var_50], rax
0x18000f94c  mov     r13, r9
0x18000f94f  mov     [rsp+78h+var_48], bp
0x18000f954  mov     r15, r8
0x18000f957  mov     [rsp+78h+var_58], r12d
0x18000f95c  lea     r9, CMAP_FORMAT4_CONTROL
0x18000f963  mov     r14, rcx
0x18000f966  lea     r8d, [rbp+0Eh]
0x18000f96a  call    WriteGeneric
0x18000f96f  test    ax, ax
0x18000f972  jnz     loc_18000FAC1
0x18000f978  movzx   edi, [rsp+78h+var_48]
0x18000f97d  mov     ebx, ebp
0x18000f97f  add     edi, r12d
0x18000f982  mov     rcx, r14
0x18000f985  cmp     bx, [rsp+78h+arg_20]
0x18000f98d  jnb     short loc_18000F9B1
0x18000f98f  movzx   eax, bx
0x18000f992  movzx   edx, bx
0x18000f995  lea     r8d, [rdi+rax*2]
0x18000f999  movzx   edx, word ptr [r15+rdx*8]
0x18000f99e  call    WriteWord
0x18000f9a3  test    ax, ax
0x18000f9a6  jnz     loc_18000FAC1
0x18000f9ac  inc     bx
0x18000f9af  jmp     short loc_18000F982
0x18000f9b1  movzx   eax, [rsp+78h+arg_20]
0x18000f9b9  xor     edx, edx
0x18000f9bb  add     eax, eax
0x18000f9bd  mov     ebp, eax
0x18000f9bf  lea     ebx, [rdi+rax]
0x18000f9c2  mov     r8d, ebx
0x18000f9c5  call    WriteWord
0x18000f9ca  xor     edx, edx
0x18000f9cc  test    ax, ax
0x18000f9cf  jnz     loc_18000FAC1
0x18000f9d5  add     ebx, 2
0x18000f9d8  mov     edi, edx
0x18000f9da  cmp     di, [rsp+78h+arg_20]
0x18000f9e2  jnb     short loc_18000FA0C
0x18000f9e4  movzx   eax, di
0x18000f9e7  mov     rcx, r14
0x18000f9ea  movzx   edx, di
0x18000f9ed  lea     r8d, [rbx+rax*2]
0x18000f9f1  movzx   edx, word ptr [r15+rdx*8+2]
0x18000f9f7  call    WriteWord
0x18000f9fc  xor     edx, edx
0x18000f9fe  test    ax, ax
0x18000fa01  jnz     loc_18000FAC1
0x18000fa07  inc     di
0x18000fa0a  jmp     short loc_18000F9DA
0x18000fa0c  add     ebx, ebp
0x18000fa0e  mov     edi, edx
0x18000fa10  cmp     di, [rsp+78h+arg_20]
0x18000fa18  jnb     short loc_18000FA42
0x18000fa1a  movzx   eax, di
0x18000fa1d  mov     rcx, r14
0x18000fa20  movzx   edx, di
0x18000fa23  lea     r8d, [rbx+rax*2]
0x18000fa27  movzx   edx, word ptr [r15+rdx*8+4]
0x18000fa2d  call    WriteWord
0x18000fa32  xor     edx, edx
0x18000fa34  test    ax, ax
0x18000fa37  jnz     loc_18000FAC1
0x18000fa3d  inc     di
0x18000fa40  jmp     short loc_18000FA10
0x18000fa42  add     ebx, ebp
0x18000fa44  mov     edi, edx
0x18000fa46  cmp     di, [rsp+78h+arg_20]
0x18000fa4e  jnb     short loc_18000FA74
0x18000fa50  movzx   eax, di
0x18000fa53  mov     rcx, r14
0x18000fa56  movzx   edx, di
0x18000fa59  lea     r8d, [rbx+rax*2]
0x18000fa5d  movzx   edx, word ptr [r15+rdx*8+6]
0x18000fa63  call    WriteWord
0x18000fa68  xor     edx, edx
0x18000fa6a  test    ax, ax
0x18000fa6d  jnz     short loc_18000FAC1
0x18000fa6f  inc     di
0x18000fa72  jmp     short loc_18000FA46
0x18000fa74  add     ebx, ebp
0x18000fa76  mov     edi, edx
0x18000fa78  cmp     di, [rsp+78h+arg_28]
0x18000fa80  jnb     short loc_18000FAA6
0x18000fa82  movzx   eax, di
0x18000fa85  mov     rcx, r14
0x18000fa88  movzx   edx, di
0x18000fa8b  lea     r8d, [rbx+rax*2]
0x18000fa8f  movzx   edx, word ptr [r13+rdx*2+0]
0x18000fa95  call    WriteWord
0x18000fa9a  xor     edx, edx
0x18000fa9c  test    ax, ax
0x18000fa9f  jnz     short loc_18000FAC1
0x18000faa1  inc     di
0x18000faa4  jmp     short loc_18000FA78
0x18000faa6  mov     rax, [rsp+78h+arg_38]
0x18000faae  movzx   ecx, [rsp+78h+arg_28]
0x18000fab6  add     ecx, ecx
0x18000fab8  sub     ecx, r12d
0x18000fabb  add     ecx, ebx
0x18000fabd  mov     [rax], ecx
0x18000fabf  mov     eax, edx
0x18000fac1  add     rsp, 40h
0x18000fac5  pop     r15
0x18000fac7  pop     r14
0x18000fac9  pop     r13
0x18000facb  pop     r12
0x18000facd  pop     rdi
0x18000face  pop     rbp
0x18000facf  pop     rbx
0x18000fad0  retn
```
