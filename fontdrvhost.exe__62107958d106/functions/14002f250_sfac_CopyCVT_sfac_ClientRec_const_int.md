# sfac_CopyCVT(sfac_ClientRec const *,int *)

- ea: `0x14002f250`
- end: `0x14002f396`
- name: `?sfac_CopyCVT@@YAHPEBUsfac_ClientRec@@PEAH@Z`
- size: `326`
- prototype: `__int64 __fastcall(const struct sfac_ClientRec *, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x14002f108`

## callees

- `0x14002f250`
- `0x140072578`
- `0x14007680c`
- `0x140098010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall sfac_CopyCVT(const struct sfac_ClientRec *a1, int *a2)
{
  int *v2; // rsi
  unsigned int v4; // edi
  __int64 v5; // rbp
  __int64 v6; // r8
  int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r14
  unsigned __int64 v11; // rax
  _QWORD v13[11]; // [rsp+30h] [rbp-58h] BYREF

  v2 = a2;
  v4 = *((_DWORD *)a1 + 17);
  v5 = 0;
  v13[0] = 0;
  if ( !v4 )
    goto LABEL_23;
  if ( v4 > 0x7FFFFFFF || (a2 = (int *)*((unsigned int *)a1 + 16), (unsigned int)a2 > 0x7FFFFFFF) )
  {
    SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(a1, a2);
    goto LABEL_22;
  }
  v6 = (*((__int64 (__fastcall **)(_QWORD, int *, _QWORD, _QWORD *))a1 + 1))(*(_QWORD *)a1, a2, v4, v13);
  v5 = v13[0];
  while ( 1 )
  {
    v13[1] = a1;
    v13[2] = v5;
    v7 = 0;
    if ( v4 )
    {
      v4 >>= 1;
      while ( v7 < (int)v4 )
      {
        v8 = v7;
        v9 = *(unsigned __int8 *)(v6 + 2LL * v7 + 1) | (unsigned int)(__int16)(*(unsigned __int8 *)(v6 + 2LL * v7) << 8);
        v2[v7] = v9;
        if ( v7 == 0x7FFFFFFF )
          goto LABEL_22;
        ++v7;
      }
      (*((void (__fastcall **)(_QWORD, int *, _QWORD))a1 + 32))(*(_QWORD *)a1, v2, v4);
      if ( v7 >= 256 )
        break;
    }
    v9 = v7;
    v10 = 256LL - v7;
    v8 = 0xFFFFFFFFLL;
    if ( (unsigned __int64)(v10 + 0x80000000LL) <= 0xFFFFFFFF )
    {
      if ( (int)v10 < 0 )
      {
        if ( 4 * (unsigned __int64)(unsigned int)(v7 - 256) > 0x80000000 )
          goto LABEL_22;
        LODWORD(v11) = 4 * v10;
      }
      else
      {
        v11 = 4LL * (unsigned int)v10;
        if ( v11 > 0x7FFFFFFF )
          goto LABEL_22;
      }
      if ( (v11 & 0x80000000) == 0LL )
      {
        memset_0(&v2[v7], 0, (int)v11);
        break;
      }
    }
LABEL_22:
    SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(v9, v8);
LABEL_23:
    v6 = 0;
  }
  if ( v5 )
    (*((void (__fastcall **)(__int64))a1 + 2))(v5);
  return 0;
}

```

## disassembly

```asm
0x14002f250  push    rbx
0x14002f252  push    rbp
0x14002f253  push    rsi
0x14002f254  push    rdi
0x14002f255  push    r14
0x14002f257  push    r15
0x14002f259  sub     rsp, 58h
0x14002f25d  mov     rsi, rdx
0x14002f260  mov     r15, rcx
0x14002f263  mov     edi, [rcx+44h]
0x14002f266  xor     ebp, ebp
0x14002f268  mov     [rsp+88h+var_58], rbp
0x14002f26d  test    edi, edi
0x14002f26f  jz      loc_14002F380
0x14002f275  cmp     edi, 7FFFFFFFh
0x14002f27b  ja      loc_14002F374
0x14002f281  mov     edx, [rcx+40h]
0x14002f284  cmp     edx, 7FFFFFFFh
0x14002f28a  ja      loc_14002F374
0x14002f290  lea     r9, [rsp+88h+var_58]
0x14002f295  mov     r8d, edi
0x14002f298  mov     rcx, [rcx]
0x14002f29b  mov     rax, [r15+8]
0x14002f29f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f2a4  mov     r8, rax
0x14002f2a7  mov     rbp, [rsp+88h+var_58]
0x14002f2ac  mov     [rsp+88h+var_50], r15
0x14002f2b1  mov     [rsp+88h+var_48], rbp
0x14002f2b6  xor     ebx, ebx
0x14002f2b8  mov     r14d, 100h
0x14002f2be  test    edi, edi
0x14002f2c0  jz      short loc_14002F30C
0x14002f2c2  shr     edi, 1
0x14002f2c4  cmp     ebx, edi
0x14002f2c6  jge     short loc_14002F2F2
0x14002f2c8  movsxd  rdx, ebx
0x14002f2cb  movzx   eax, byte ptr [r8+rdx*2]
0x14002f2d0  shl     ax, 8
0x14002f2d4  movsx   ecx, ax
0x14002f2d7  movzx   eax, byte ptr [r8+rdx*2+1]
0x14002f2dd  or      ecx, eax
0x14002f2df  mov     [rsi+rdx*4], ecx
0x14002f2e2  cmp     ebx, 7FFFFFFFh
0x14002f2e8  jz      loc_14002F37A
0x14002f2ee  inc     ebx
0x14002f2f0  jmp     short loc_14002F2C4
0x14002f2f2  mov     r8d, edi
0x14002f2f5  mov     rdx, rsi
0x14002f2f8  mov     rcx, [r15]
0x14002f2fb  mov     rax, [r15+100h]
0x14002f302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f307  cmp     ebx, r14d
0x14002f30a  jge     short loc_14002F34D
0x14002f30c  movsxd  rcx, ebx
0x14002f30f  sub     r14, rcx
0x14002f312  mov     r8d, 80000000h
0x14002f318  lea     rax, [r14+r8]
0x14002f31c  mov     edx, 0FFFFFFFFh
0x14002f321  cmp     rax, rdx
0x14002f324  ja      short loc_14002F37A
0x14002f326  test    r14d, r14d
0x14002f329  js      short loc_14002F361
0x14002f32b  mov     eax, r14d
0x14002f32e  shl     rax, 2
0x14002f332  cmp     rax, 7FFFFFFFh
0x14002f338  ja      short loc_14002F37A
0x14002f33a  test    eax, eax
0x14002f33c  js      short loc_14002F37A
0x14002f33e  movsxd  r8, eax; Size
0x14002f341  lea     rcx, [rsi+rcx*4]; void *
0x14002f345  xor     edx, edx; Val
0x14002f347  call    memset_0
0x14002f34c  nop
0x14002f34d  test    rbp, rbp
0x14002f350  jnz     short loc_14002F388
0x14002f352  xor     eax, eax
0x14002f354  add     rsp, 58h
0x14002f358  pop     r15
0x14002f35a  pop     r14
0x14002f35c  pop     rdi
0x14002f35d  pop     rsi
0x14002f35e  pop     rbp
0x14002f35f  pop     rbx
0x14002f360  retn
0x14002f361  neg     r14d
0x14002f364  mov     eax, r14d
0x14002f367  shl     rax, 2
0x14002f36b  cmp     rax, r8
0x14002f36e  ja      short loc_14002F37A
0x14002f370  neg     eax
0x14002f372  jmp     short loc_14002F33A
0x14002f374  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@SAXXZ; SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(void)
0x14002f379  nop
0x14002f37a  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntRasterizerException@@@@SAXXZ; SafeIntExceptionHandler<SafeIntRasterizerException>::SafeIntOnOverflow(void)
0x14002f37f  nop
0x14002f380  xor     r8d, r8d
0x14002f383  jmp     loc_14002F2AC
0x14002f388  mov     rcx, rbp
0x14002f38b  mov     rax, [r15+10h]
0x14002f38f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f394  jmp     short loc_14002F352
```
