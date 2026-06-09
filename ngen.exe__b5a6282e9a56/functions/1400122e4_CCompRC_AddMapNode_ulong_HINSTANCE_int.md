# CCompRC::AddMapNode(ulong,HINSTANCE__ *,int)

- ea: `0x1400122e4`
- end: `0x14001244f`
- name: `?AddMapNode@CCompRC@@AEAAJKPEAUHINSTANCE__@@H@Z`
- size: `363`
- prototype: `__int64 __fastcall(CCompRC *this, const struct NoThrow *, HINSTANCE, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400124f8`

## callees

- `0x14000a0d4`
- `0x14000a10c`
- `0x1400122e4`
- `0x140013f04`

## pseudocode

```c
__int64 __fastcall CCompRC::AddMapNode(CCompRC *this, const struct NoThrow *a2, HINSTANCE a3, int a4)
{
  char *v4; // r10
  int v7; // ebp
  char *v9; // rax
  __int64 v10; // rcx
  _DWORD *v11; // rax
  int v12; // edx
  int v13; // ecx
  _DWORD *v14; // rax
  unsigned __int64 v15; // rsi
  unsigned __int128 v16; // rax
  _DWORD *v17; // rax
  void *v18; // rbx
  _DWORD *v19; // rax
  __int64 v20; // rax
  __int64 v21; // rcx

  v4 = (char *)*((_QWORD *)this + 3);
  v7 = (int)a2;
  if ( !v4 )
  {
    v9 = (char *)operator new[](0xA8u, a2);
    v4 = v9;
    if ( v9 )
    {
      v10 = 7;
      v11 = v9 + 16;
      do
      {
        *((_QWORD *)v11 - 1) = 0;
        *v11 = 0;
        v11 += 6;
        --v10;
      }
      while ( v10 );
    }
    else
    {
      v4 = 0;
    }
    *((_QWORD *)this + 3) = v4;
    if ( !v4 )
      return 2147942414LL;
    *((_DWORD *)this + 8) = 7;
  }
  v12 = *((_DWORD *)this + 8);
  v13 = 0;
  if ( v12 > 0 )
  {
    v14 = v4 + 16;
    while ( *((_QWORD *)v14 - 1) || *v14 )
    {
      ++v13;
      v14 += 6;
      if ( v13 >= v12 )
        goto LABEL_14;
    }
    v21 = 3LL * v13;
    if ( a4 )
      *(_DWORD *)&v4[8 * v21 + 16] = 1;
    else
      *(_QWORD *)&v4[8 * v21 + 8] = a3;
    *(_DWORD *)&v4[8 * v21] = v7;
    return 0;
  }
LABEL_14:
  v15 = v12 + 5;
  v16 = v15 * (unsigned __int128)0x18uLL;
  if ( !is_mul_ok(v15, 0x18u) )
    *(_QWORD *)&v16 = -1;
  v17 = operator new[](v16, *((const struct NoThrow **)&v16 + 1));
  v18 = v17;
  if ( v17 )
  {
    if ( v15 )
    {
      v19 = v17 + 4;
      do
      {
        *((_QWORD *)v19 - 1) = 0;
        *v19 = 0;
        v19 += 6;
        --v15;
      }
      while ( v15 );
    }
    memcpy_0(v18, *((const void **)this + 3), 24LL * *((int *)this + 8));
    operator delete(*((void **)this + 3));
    v20 = *((int *)this + 8);
    *((_QWORD *)this + 3) = v18;
    if ( a4 )
      *((_DWORD *)v18 + 6 * v20 + 4) = 1;
    else
      *((_QWORD *)v18 + 3 * v20 + 1) = a3;
    *((_DWORD *)v18 + 6 * v20) = v7;
    *((_DWORD *)this + 8) += 5;
    return 0;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x1400122e4  mov     [rsp+arg_0], rbx
0x1400122e9  mov     [rsp+arg_8], rbp
0x1400122ee  mov     [rsp+arg_10], rsi
0x1400122f3  push    rdi
0x1400122f4  push    r14
0x1400122f6  push    r15
0x1400122f8  sub     rsp, 20h
0x1400122fc  mov     r10, [rcx+18h]
0x140012300  mov     r15d, r9d
0x140012303  mov     r14, r8
0x140012306  mov     ebp, edx
0x140012308  mov     rdi, rcx
0x14001230b  test    r10, r10
0x14001230e  jnz     short loc_140012354
0x140012310  mov     ecx, 0A8h; dwBytes
0x140012315  call    ??_U@YAPEAX_KAEBUNoThrow@@@Z; operator new[](unsigned __int64,NoThrow const &)
0x14001231a  mov     r10, rax
0x14001231d  mov     edx, 7
0x140012322  test    rax, rax
0x140012325  jz      short loc_140012341
0x140012327  mov     ecx, edx
0x140012329  add     rax, 10h
0x14001232d  and     qword ptr [rax-8], 0
0x140012332  and     dword ptr [rax], 0
0x140012335  lea     rax, [rax+18h]
0x140012339  sub     rcx, 1
0x14001233d  jnz     short loc_14001232D
0x14001233f  jmp     short loc_140012344
0x140012341  xor     r10d, r10d
0x140012344  mov     [rdi+18h], r10
0x140012348  test    r10, r10
0x14001234b  jz      loc_140012431
0x140012351  mov     [rdi+20h], edx
0x140012354  mov     edx, [rdi+20h]; struct NoThrow *
0x140012357  xor     ecx, ecx
0x140012359  test    edx, edx
0x14001235b  jle     short loc_14001237B
0x14001235d  lea     rax, [r10+10h]
0x140012361  cmp     qword ptr [rax-8], 0
0x140012366  jnz     short loc_140012371
0x140012368  cmp     dword ptr [rax], 0
0x14001236b  jz      loc_1400123FF
0x140012371  inc     ecx
0x140012373  add     rax, 18h
0x140012377  cmp     ecx, edx
0x140012379  jl      short loc_140012361
0x14001237b  lea     eax, [rdx+5]
0x14001237e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140012385  movsxd  rsi, eax
0x140012388  mov     eax, 18h
0x14001238d  mul     rsi
0x140012390  cmovo   rax, rcx
0x140012394  mov     rcx, rax; dwBytes
0x140012397  call    ??_U@YAPEAX_KAEBUNoThrow@@@Z; operator new[](unsigned __int64,NoThrow const &)
0x14001239c  mov     rbx, rax
0x14001239f  test    rax, rax
0x1400123a2  jz      loc_140012431
0x1400123a8  test    rsi, rsi
0x1400123ab  jz      short loc_1400123C3
0x1400123ad  add     rax, 10h
0x1400123b1  and     qword ptr [rax-8], 0
0x1400123b6  and     dword ptr [rax], 0
0x1400123b9  lea     rax, [rax+18h]
0x1400123bd  sub     rsi, 1
0x1400123c1  jnz     short loc_1400123B1
0x1400123c3  movsxd  rax, dword ptr [rdi+20h]
0x1400123c7  mov     rcx, rbx; void *
0x1400123ca  mov     rdx, [rdi+18h]; Src
0x1400123ce  lea     r8, [rax+rax*2]
0x1400123d2  shl     r8, 3; Size
0x1400123d6  call    memcpy_0
0x1400123db  mov     rcx, [rdi+18h]; lpMem
0x1400123df  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400123e4  movsxd  rax, dword ptr [rdi+20h]
0x1400123e8  mov     [rdi+18h], rbx
0x1400123ec  lea     rcx, [rax+rax*2]
0x1400123f0  test    r15d, r15d
0x1400123f3  jz      short loc_140012423
0x1400123f5  mov     dword ptr [rbx+rcx*8+10h], 1
0x1400123fd  jmp     short loc_140012428
0x1400123ff  movsxd  rax, ecx
0x140012402  lea     rcx, [rax+rax*2]
0x140012406  test    r15d, r15d
0x140012409  jz      short loc_140012416
0x14001240b  mov     dword ptr [r10+rcx*8+10h], 1
0x140012414  jmp     short loc_14001241B
0x140012416  mov     [r10+rcx*8+8], r14
0x14001241b  mov     [r10+rcx*8], ebp
0x14001241f  xor     eax, eax
0x140012421  jmp     short loc_140012436
0x140012423  mov     [rbx+rcx*8+8], r14
0x140012428  mov     [rbx+rcx*8], ebp
0x14001242b  add     dword ptr [rdi+20h], 5
0x14001242f  jmp     short loc_14001241F
0x140012431  mov     eax, 8007000Eh
0x140012436  mov     rbx, [rsp+38h+arg_0]
0x14001243b  mov     rbp, [rsp+38h+arg_8]
0x140012440  mov     rsi, [rsp+38h+arg_10]
0x140012445  add     rsp, 20h
0x140012449  pop     r15
0x14001244b  pop     r14
0x14001244d  pop     rdi
0x14001244e  retn
```
