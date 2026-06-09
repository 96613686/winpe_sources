# start_pass_huff_decoder

- ea: `0x1800182c0`
- end: `0x180018490`
- name: `start_pass_huff_decoder`
- size: `464`
- prototype: `__int64 __fastcall(struct jpeg_decompress_struct *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800182c0`
- `0x1800184a0`
- `0x180070010`

## pseudocode

```c
__int64 __fastcall start_pass_huff_decoder(struct jpeg_decompress_struct *a1)
{
  __int64 v1; // rdi
  int v3; // r15d
  int v4; // r12d
  int v5; // eax
  int i; // esi
  __int64 v7; // rax
  __int64 v8; // r8
  __int64 v9; // r14
  int j; // r8d
  __int64 v11; // rdx
  __int64 v12; // r9
  bool v13; // al
  __int64 result; // rax

  v1 = *((_QWORD *)a1 + 70);
  v3 = 0;
  v4 = 0;
  if ( *((_DWORD *)a1 + 123) || *((_DWORD *)a1 + 124) != 63 || *((_DWORD *)a1 + 125) || *((_DWORD *)a1 + 126) )
  {
    *(_DWORD *)(*(_QWORD *)a1 + 40LL) = 122;
    (*(void (__fastcall **)(struct jpeg_decompress_struct *, __int64))(*(_QWORD *)a1 + 8LL))(a1, 0xFFFFFFFFLL);
  }
  v5 = *((_DWORD *)a1 + 100);
  for ( i = 0; i < v5; v5 = *((_DWORD *)a1 + 100) )
  {
    v7 = *((_QWORD *)a1 + i + 51);
    v8 = *(int *)(v7 + 20);
    v9 = *(int *)(v7 + 24);
    if ( *((_BYTE *)a1 + 3448) )
    {
      if ( *((_BYTE *)a1 + 3452) == 1 )
      {
        jpeg_make_d_derived_tbl(a1, 1, v8, (struct d_derived_tbl_tag **)(v1 + 80 + 8 * v8), i);
        jpeg_make_d_derived_tbl(a1, 0, v9, (struct d_derived_tbl_tag **)(v1 + 112 + 8 * v9), i);
        ++v3;
      }
    }
    else if ( !*((_BYTE *)a1 + 3451) )
    {
      jpeg_make_d_derived_tbl(a1, 1, v8, (struct d_derived_tbl_tag **)(v1 + 80 + 8 * v8), i);
      jpeg_make_d_derived_tbl(a1, 0, v9, (struct d_derived_tbl_tag **)(v1 + 112 + 8 * v9), i);
      ++v4;
    }
    *(_DWORD *)(v1 + 4LL * i++ + 56) = 0;
  }
  if ( v3 == v5 )
    *((_BYTE *)a1 + 3450) = 1;
  if ( v4 == v5 )
    *((_BYTE *)a1 + 3451) = 1;
  for ( j = 0; j < *((_DWORD *)a1 + 112); *(_BYTE *)(v11 + v1 + 314) = v13 )
  {
    v11 = j;
    v12 = *((_QWORD *)a1 + *((int *)a1 + j + 113) + 51);
    *(_QWORD *)(v1 + 8LL * j + 144) = *(_QWORD *)(v1 + 8LL * *(int *)(v12 + 20) + 80);
    *(_QWORD *)(v1 + 8LL * j + 224) = *(_QWORD *)(v1 + 8LL * *(int *)(v12 + 24) + 112);
    if ( *(_BYTE *)(v12 + 48) )
    {
      *(_BYTE *)(j + v1 + 304) = 1;
      v13 = *(_DWORD *)(v12 + 36) > 1;
    }
    else
    {
      *(_BYTE *)(j + v1 + 304) = 0;
      v13 = 0;
    }
    ++j;
  }
  *(_DWORD *)(v1 + 48) = 0;
  *(_QWORD *)(v1 + 40) = 0;
  *(_BYTE *)(v1 + 32) = 0;
  result = *((unsigned int *)a1 + 87);
  *(_DWORD *)(v1 + 72) = result;
  return result;
}

```

## disassembly

```asm
0x1800182c0  push    rbx
0x1800182c2  push    rbp
0x1800182c3  push    rsi
0x1800182c4  push    rdi
0x1800182c5  push    r12
0x1800182c7  push    r13
0x1800182c9  push    r14
0x1800182cb  push    r15
0x1800182cd  sub     rsp, 38h
0x1800182d1  mov     rdi, [rcx+230h]
0x1800182d8  xor     r13d, r13d
0x1800182db  mov     rbx, rcx
0x1800182de  mov     r15d, r13d
0x1800182e1  mov     r12d, r13d
0x1800182e4  cmp     [rcx+1ECh], r13d
0x1800182eb  jnz     short loc_180018308
0x1800182ed  cmp     dword ptr [rcx+1F0h], 3Fh ; '?'
0x1800182f4  jnz     short loc_180018308
0x1800182f6  cmp     [rcx+1F4h], r13d
0x1800182fd  jnz     short loc_180018308
0x1800182ff  cmp     [rcx+1F8h], r13d
0x180018306  jz      short loc_180018321
0x180018308  mov     rax, [rcx]
0x18001830b  or      edx, 0FFFFFFFFh
0x18001830e  mov     dword ptr [rax+28h], 7Ah ; 'z'
0x180018315  mov     rax, [rcx]
0x180018318  mov     rax, [rax+8]
0x18001831c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018321  mov     eax, [rbx+190h]
0x180018327  mov     esi, r13d
0x18001832a  test    eax, eax
0x18001832c  jle     loc_1800183DB
0x180018332  movsxd  rbp, esi
0x180018335  mov     rax, [rbx+rbp*8+198h]
0x18001833d  movsxd  r8, dword ptr [rax+14h]; int
0x180018341  movsxd  r14, dword ptr [rax+18h]
0x180018345  cmp     [rbx+0D78h], r13b
0x18001834c  jz      short loc_18001838B
0x18001834e  cmp     byte ptr [rbx+0D7Ch], 1
0x180018355  jnz     short loc_1800183C6
0x180018357  lea     rax, [rdi+50h]
0x18001835b  mov     [rsp+78h+var_58], esi; int
0x18001835f  lea     r9, [rax+r8*8]; struct d_derived_tbl_tag **
0x180018363  mov     dl, 1; unsigned __int8
0x180018365  mov     rcx, rbx; struct jpeg_decompress_struct *
0x180018368  call    ?jpeg_make_d_derived_tbl@@YAXPEAUjpeg_decompress_struct@@EHPEAPEAUd_derived_tbl_tag@@H@Z; jpeg_make_d_derived_tbl(jpeg_decompress_struct *,uchar,int,d_derived_tbl_tag * *,int)
0x18001836d  lea     rax, [rdi+70h]
0x180018371  mov     [rsp+78h+var_58], esi; int
0x180018375  lea     r9, [rax+r14*8]; struct d_derived_tbl_tag **
0x180018379  mov     r8d, r14d; int
0x18001837c  xor     edx, edx; unsigned __int8
0x18001837e  mov     rcx, rbx; struct jpeg_decompress_struct *
0x180018381  call    ?jpeg_make_d_derived_tbl@@YAXPEAUjpeg_decompress_struct@@EHPEAPEAUd_derived_tbl_tag@@H@Z; jpeg_make_d_derived_tbl(jpeg_decompress_struct *,uchar,int,d_derived_tbl_tag * *,int)
0x180018386  inc     r15d
0x180018389  jmp     short loc_1800183C6
0x18001838b  cmp     [rbx+0D7Bh], r13b
0x180018392  jnz     short loc_1800183C6
0x180018394  lea     rax, [rdi+50h]
0x180018398  mov     [rsp+78h+var_58], esi; int
0x18001839c  lea     r9, [rax+r8*8]; struct d_derived_tbl_tag **
0x1800183a0  mov     dl, 1; unsigned __int8
0x1800183a2  mov     rcx, rbx; struct jpeg_decompress_struct *
0x1800183a5  call    ?jpeg_make_d_derived_tbl@@YAXPEAUjpeg_decompress_struct@@EHPEAPEAUd_derived_tbl_tag@@H@Z; jpeg_make_d_derived_tbl(jpeg_decompress_struct *,uchar,int,d_derived_tbl_tag * *,int)
0x1800183aa  lea     rax, [rdi+70h]
0x1800183ae  mov     [rsp+78h+var_58], esi; int
0x1800183b2  lea     r9, [rax+r14*8]; struct d_derived_tbl_tag **
0x1800183b6  mov     r8d, r14d; int
0x1800183b9  xor     edx, edx; unsigned __int8
0x1800183bb  mov     rcx, rbx; struct jpeg_decompress_struct *
0x1800183be  call    ?jpeg_make_d_derived_tbl@@YAXPEAUjpeg_decompress_struct@@EHPEAPEAUd_derived_tbl_tag@@H@Z; jpeg_make_d_derived_tbl(jpeg_decompress_struct *,uchar,int,d_derived_tbl_tag * *,int)
0x1800183c3  inc     r12d
0x1800183c6  mov     [rdi+rbp*4+38h], r13d
0x1800183cb  inc     esi
0x1800183cd  mov     eax, [rbx+190h]
0x1800183d3  cmp     esi, eax
0x1800183d5  jl      loc_180018332
0x1800183db  cmp     r15d, eax
0x1800183de  jnz     short loc_1800183E7
0x1800183e0  mov     byte ptr [rbx+0D7Ah], 1
0x1800183e7  cmp     r12d, eax
0x1800183ea  jnz     short loc_1800183F3
0x1800183ec  mov     byte ptr [rbx+0D7Bh], 1
0x1800183f3  mov     r8d, r13d
0x1800183f6  cmp     [rbx+1C0h], r13d
0x1800183fd  jle     short loc_18001846A
0x1800183ff  movsxd  rdx, r8d
0x180018402  movsxd  rax, dword ptr [rbx+rdx*4+1C4h]
0x18001840a  mov     r9, [rbx+rax*8+198h]
0x180018412  movsxd  rax, dword ptr [r9+14h]
0x180018416  mov     rcx, [rdi+rax*8+50h]
0x18001841b  mov     [rdi+rdx*8+90h], rcx
0x180018423  movsxd  rax, dword ptr [r9+18h]
0x180018427  mov     rcx, [rdi+rax*8+70h]
0x18001842c  mov     [rdi+rdx*8+0E0h], rcx
0x180018434  cmp     [r9+30h], r13b
0x180018438  jz      short loc_18001844C
0x18001843a  mov     byte ptr [rdx+rdi+130h], 1
0x180018442  cmp     dword ptr [r9+24h], 1
0x180018447  setnle  al
0x18001844a  jmp     short loc_180018457
0x18001844c  mov     [rdx+rdi+130h], r13b
0x180018454  mov     al, r13b
0x180018457  inc     r8d
0x18001845a  mov     [rdx+rdi+13Ah], al
0x180018461  cmp     r8d, [rbx+1C0h]
0x180018468  jl      short loc_1800183FF
0x18001846a  mov     [rdi+30h], r13d
0x18001846e  mov     [rdi+28h], r13
0x180018472  mov     [rdi+20h], r13b
0x180018476  mov     eax, [rbx+15Ch]
0x18001847c  mov     [rdi+48h], eax
0x18001847f  add     rsp, 38h
0x180018483  pop     r15
0x180018485  pop     r14
0x180018487  pop     r13
0x180018489  pop     r12
0x18001848b  pop     rdi
0x18001848c  pop     rsi
0x18001848d  pop     rbp
0x18001848e  pop     rbx
0x18001848f  retn
```
