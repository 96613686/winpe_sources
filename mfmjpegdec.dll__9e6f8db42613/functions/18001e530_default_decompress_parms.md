# default_decompress_parms

- ea: `0x18001e530`
- end: `0x18001e6bf`
- name: `default_decompress_parms`
- size: `399`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001daa4`

## callees

- `0x18001e530`
- `0x180070010`

## pseudocode

```c
__int64 __fastcall default_decompress_parms(__int64 a1)
{
  int v2; // ecx
  int v3; // ecx
  char v4; // al
  __int64 v5; // rdx
  int v6; // r8d
  int v7; // ecx
  int v8; // edx
  _DWORD *v9; // rax
  __int64 result; // rax

  v2 = *(_DWORD *)(a1 + 56) - 1;
  if ( !v2 )
  {
    *(_DWORD *)(a1 + 60) = 1;
    *(_DWORD *)(a1 + 64) = 1;
    goto LABEL_29;
  }
  v3 = v2 - 2;
  if ( !v3 )
  {
    if ( *(_BYTE *)(a1 + 352) )
      goto LABEL_22;
    if ( *(_BYTE *)(a1 + 360) )
    {
      if ( *(_BYTE *)(a1 + 361) )
      {
        if ( *(_BYTE *)(a1 + 361) != 1 )
        {
          v5 = 0xFFFFFFFFLL;
          *(_DWORD *)(*(_QWORD *)a1 + 40LL) = 114;
          *(_DWORD *)(*(_QWORD *)a1 + 44LL) = *(unsigned __int8 *)(a1 + 361);
LABEL_21:
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 8LL))(a1, v5);
        }
LABEL_22:
        *(_DWORD *)(a1 + 60) = 3;
LABEL_23:
        *(_DWORD *)(a1 + 64) = 2;
        goto LABEL_29;
      }
LABEL_27:
      *(_DWORD *)(a1 + 60) = 2;
      goto LABEL_23;
    }
    v6 = *(_DWORD *)(a1 + 600);
    v7 = *(_DWORD *)(a1 + 696);
    v8 = *(_DWORD *)(a1 + 792);
    if ( v6 == 1 )
    {
      if ( v7 == 2 && v8 == 3 )
        goto LABEL_22;
    }
    else if ( v6 == 82 && v7 == 71 && v8 == 66 )
    {
      goto LABEL_27;
    }
    v9 = *(_DWORD **)a1;
    v9[13] = v8;
    v5 = 1;
    v9[11] = v6;
    v9[12] = v7;
    *(_DWORD *)(*(_QWORD *)a1 + 40LL) = 111;
    goto LABEL_21;
  }
  if ( v3 == 1 )
  {
    if ( *(_BYTE *)(a1 + 360) && (v4 = *(_BYTE *)(a1 + 361)) != 0 )
    {
      if ( v4 != 2 )
      {
        *(_DWORD *)(*(_QWORD *)a1 + 40LL) = 114;
        *(_DWORD *)(*(_QWORD *)a1 + 44LL) = *(unsigned __int8 *)(a1 + 361);
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 8LL))(a1, 0xFFFFFFFFLL);
      }
      *(_DWORD *)(a1 + 60) = 5;
    }
    else
    {
      *(_DWORD *)(a1 + 60) = 4;
    }
    *(_DWORD *)(a1 + 64) = 4;
  }
  else
  {
    *(_QWORD *)(a1 + 60) = 0;
  }
LABEL_29:
  result = 0x3FF0000000000000LL;
  *(_DWORD *)(a1 + 68) = 1;
  *(_QWORD *)(a1 + 80) = 0x3FF0000000000000LL;
  *(_DWORD *)(a1 + 72) = 1;
  *(_WORD *)(a1 + 88) = 0;
  *(_DWORD *)(a1 + 92) = 0;
  *(_WORD *)(a1 + 96) = 257;
  *(_BYTE *)(a1 + 98) = 0;
  *(_DWORD *)(a1 + 100) = 2;
  *(_BYTE *)(a1 + 104) = 1;
  *(_DWORD *)(a1 + 108) = 256;
  *(_QWORD *)(a1 + 144) = 0;
  *(_WORD *)(a1 + 112) = 0;
  *(_BYTE *)(a1 + 114) = 0;
  return result;
}

```

## disassembly

```asm
0x18001e530  push    rbx
0x18001e532  push    rbp
0x18001e533  push    rsi
0x18001e534  push    rdi
0x18001e535  sub     rsp, 28h
0x18001e539  mov     esi, 1
0x18001e53e  mov     rbx, rcx
0x18001e541  mov     ecx, [rcx+38h]
0x18001e544  xor     edi, edi
0x18001e546  lea     ebp, [rsi+1]
0x18001e549  sub     ecx, esi
0x18001e54b  jz      loc_18001E66E
0x18001e551  sub     ecx, ebp
0x18001e553  jz      short loc_18001E5BF
0x18001e555  cmp     ecx, esi
0x18001e557  jz      short loc_18001E562
0x18001e559  mov     [rbx+3Ch], rdi
0x18001e55d  jmp     loc_18001E674
0x18001e562  cmp     [rbx+168h], dil
0x18001e569  jz      short loc_18001E5AC
0x18001e56b  mov     al, [rbx+169h]
0x18001e571  test    al, al
0x18001e573  jz      short loc_18001E5AC
0x18001e575  cmp     al, bpl
0x18001e578  jz      short loc_18001E5A3
0x18001e57a  mov     rax, [rbx]
0x18001e57d  or      edx, 0FFFFFFFFh
0x18001e580  mov     dword ptr [rax+28h], 72h ; 'r'
0x18001e587  mov     rax, [rbx]
0x18001e58a  movzx   ecx, byte ptr [rbx+169h]
0x18001e591  mov     [rax+2Ch], ecx
0x18001e594  mov     rcx, rbx
0x18001e597  mov     rax, [rbx]
0x18001e59a  mov     rax, [rax+8]
0x18001e59e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e5a3  mov     dword ptr [rbx+3Ch], 5
0x18001e5aa  jmp     short loc_18001E5B3
0x18001e5ac  mov     dword ptr [rbx+3Ch], 4
0x18001e5b3  mov     dword ptr [rbx+40h], 4
0x18001e5ba  jmp     loc_18001E674
0x18001e5bf  cmp     [rbx+160h], dil
0x18001e5c6  jnz     loc_18001E64D
0x18001e5cc  cmp     [rbx+168h], dil
0x18001e5d3  jz      short loc_18001E604
0x18001e5d5  movzx   ecx, byte ptr [rbx+169h]
0x18001e5dc  test    ecx, ecx
0x18001e5de  jz      loc_18001E669
0x18001e5e4  cmp     ecx, esi
0x18001e5e6  jz      short loc_18001E64D
0x18001e5e8  mov     rax, [rbx]
0x18001e5eb  or      edx, 0FFFFFFFFh
0x18001e5ee  mov     dword ptr [rax+28h], 72h ; 'r'
0x18001e5f5  mov     rax, [rbx]
0x18001e5f8  movzx   ecx, byte ptr [rbx+169h]
0x18001e5ff  mov     [rax+2Ch], ecx
0x18001e602  jmp     short loc_18001E63E
0x18001e604  mov     r8d, [rbx+258h]
0x18001e60b  mov     ecx, [rbx+2B8h]
0x18001e611  mov     edx, [rbx+318h]
0x18001e617  cmp     r8d, esi
0x18001e61a  jnz     short loc_18001E659
0x18001e61c  cmp     ecx, ebp
0x18001e61e  jnz     short loc_18001E625
0x18001e620  cmp     edx, 3
0x18001e623  jz      short loc_18001E64D
0x18001e625  mov     rax, [rbx]
0x18001e628  mov     [rax+34h], edx
0x18001e62b  mov     edx, esi
0x18001e62d  mov     [rax+2Ch], r8d
0x18001e631  mov     [rax+30h], ecx
0x18001e634  mov     rax, [rbx]
0x18001e637  mov     dword ptr [rax+28h], 6Fh ; 'o'
0x18001e63e  mov     rax, [rbx]
0x18001e641  mov     rcx, rbx
0x18001e644  mov     rax, [rax+8]
0x18001e648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e64d  mov     dword ptr [rbx+3Ch], 3
0x18001e654  mov     [rbx+40h], ebp
0x18001e657  jmp     short loc_18001E674
0x18001e659  cmp     r8d, 52h ; 'R'
0x18001e65d  jnz     short loc_18001E625
0x18001e65f  cmp     ecx, 47h ; 'G'
0x18001e662  jnz     short loc_18001E625
0x18001e664  cmp     edx, 42h ; 'B'
0x18001e667  jnz     short loc_18001E625
0x18001e669  mov     [rbx+3Ch], ebp
0x18001e66c  jmp     short loc_18001E654
0x18001e66e  mov     [rbx+3Ch], esi
0x18001e671  mov     [rbx+40h], esi
0x18001e674  mov     rax, 3FF0000000000000h
0x18001e67e  mov     [rbx+44h], esi
0x18001e681  mov     [rbx+50h], rax
0x18001e685  mov     [rbx+48h], esi
0x18001e688  mov     [rbx+58h], di
0x18001e68c  mov     [rbx+5Ch], edi
0x18001e68f  mov     word ptr [rbx+60h], 101h
0x18001e695  mov     [rbx+62h], dil
0x18001e699  mov     [rbx+64h], ebp
0x18001e69c  mov     [rbx+68h], sil
0x18001e6a0  mov     dword ptr [rbx+6Ch], 100h
0x18001e6a7  mov     [rbx+90h], rdi
0x18001e6ae  mov     [rbx+70h], di
0x18001e6b2  mov     [rbx+72h], dil
0x18001e6b6  add     rsp, 28h
0x18001e6ba  pop     rdi
0x18001e6bb  pop     rsi
0x18001e6bc  pop     rbp
0x18001e6bd  pop     rbx
0x18001e6be  retn
```
