# _hypothesis_builder::AppendAndDetach(ulong,_hypothesis_builder *,ulong *,tagHYPOTHESIS * *)

- ea: `0x180018378`
- end: `0x1800184c0`
- name: `?AppendAndDetach@_hypothesis_builder@@QEAAJKPEAV1@PEAKPEAPEAUtagHYPOTHESIS@@@Z`
- size: `328`
- prototype: `__int64 __fastcall(_hypothesis_builder *this, unsigned int, struct _hypothesis_builder *, unsigned int *, struct tagHYPOTHESIS **)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000fc14`
- `0x180010184`

## callees

- `0x180018378`
- `0x1800184c8`
- `0x180018550`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018435`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018435`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800183de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800183de`

## pseudocode

```c
__int64 __fastcall _hypothesis_builder::AppendAndDetach(
        _hypothesis_builder *this,
        unsigned int a2,
        struct _hypothesis_builder *a3,
        unsigned int *a4,
        struct tagHYPOTHESIS **a5)
{
  struct tagHYPOTHESIS **v5; // r12
  unsigned int v6; // r14d
  __int64 result; // rax
  SIZE_T v12; // rdi
  struct tagHYPOTHESIS *v13; // rax
  struct tagHYPOTHESIS *v14; // rbx
  int v15; // edi
  unsigned int v16; // ebp
  struct tagHYPOTHESIS *v17; // rdi
  unsigned int v18[22]; // [rsp+20h] [rbp-58h] BYREF

  v5 = a5;
  v6 = 0;
  if ( !a5 || !a4 )
    return 2147942487LL;
  if ( !a2 )
    return _hypothesis_builder::Detach(this, a4, a5, a4);
  if ( !a3 )
    return 2147942487LL;
  if ( a2 > 0x7FFFFFE )
    return 2147942934LL;
  v12 = 32LL * (a2 + 1);
  v13 = (struct tagHYPOTHESIS *)CoTaskMemAlloc(v12);
  v14 = v13;
  if ( !v13 )
    return 2147942414LL;
  for ( ; v12; --v12 )
  {
    LOBYTE(v13->pwszClassName) = 0;
    v13 = (struct tagHYPOTHESIS *)((char *)v13 + 1);
  }
  v18[0] = 0;
  LODWORD(a5) = 0;
  v15 = _hypothesis_builder::DetachInPlace(this, v14, (unsigned int *)&a5, v18);
  if ( v15 >= 0 )
  {
    v16 = (unsigned int)a5;
    v17 = (struct tagHYPOTHESIS *)((char *)v14 + v18[0]);
    if ( a2 )
    {
      do
      {
        if ( (int)_hypothesis_builder::DetachInPlace(
                    (struct _hypothesis_builder *)((char *)a3 + 40 * v6),
                    v17,
                    (unsigned int *)&a5,
                    v18) < 0 )
          break;
        ++v6;
        v16 += (unsigned int)a5;
        v17 = (struct tagHYPOTHESIS *)((char *)v17 + v18[0]);
      }
      while ( v6 < a2 );
    }
    *v5 = v14;
    result = 0;
    *a4 = v16;
  }
  else
  {
    CoTaskMemFree(v14);
    return (unsigned int)v15;
  }
  return result;
}

```

## disassembly

```asm
0x180018378  push    rbx
0x18001837a  push    rbp
0x18001837b  push    rsi
0x18001837c  push    rdi
0x18001837d  push    r12
0x18001837f  push    r13
0x180018381  push    r14
0x180018383  push    r15
0x180018385  sub     rsp, 38h
0x180018389  mov     r12, [rsp+78h+arg_20]
0x180018391  xor     r14d, r14d
0x180018394  mov     r15, r9
0x180018397  mov     r13, r8
0x18001839a  mov     esi, edx
0x18001839c  mov     rbp, rcx
0x18001839f  test    r12, r12
0x1800183a2  jz      loc_1800184AA
0x1800183a8  test    r9, r9
0x1800183ab  jz      loc_1800184AA
0x1800183b1  test    edx, edx
0x1800183b3  jz      loc_18001849D
0x1800183b9  test    r8, r8
0x1800183bc  jz      loc_1800184AA
0x1800183c2  cmp     edx, 7FFFFFEh
0x1800183c8  jbe     short loc_1800183D4
0x1800183ca  mov     eax, 80070216h
0x1800183cf  jmp     loc_1800184AF
0x1800183d4  lea     edi, [rdx+1]
0x1800183d7  shl     rdi, 5
0x1800183db  mov     rcx, rdi; cb
0x1800183de  call    cs:__imp_CoTaskMemAlloc
0x1800183e4  mov     rbx, rax
0x1800183e7  test    rax, rax
0x1800183ea  jnz     short loc_1800183F6
0x1800183ec  mov     eax, 8007000Eh
0x1800183f1  jmp     loc_1800184AF
0x1800183f6  test    rdi, rdi
0x1800183f9  jz      short loc_180018407
0x1800183fb  mov     [rax], r14b
0x1800183fe  inc     rax
0x180018401  sub     rdi, 1
0x180018405  jnz     short loc_1800183FB
0x180018407  lea     r9, [rsp+78h+var_58]; unsigned int *
0x18001840c  mov     [rsp+78h+var_58], r14d
0x180018411  lea     r8, [rsp+78h+arg_20]; unsigned int *
0x180018419  mov     dword ptr [rsp+78h+arg_20], r14d
0x180018421  mov     rdx, rbx; struct tagHYPOTHESIS *
0x180018424  mov     rcx, rbp; this
0x180018427  call    ?DetachInPlace@_hypothesis_builder@@IEAAJAEAUtagHYPOTHESIS@@PEAK1@Z; _hypothesis_builder::DetachInPlace(tagHYPOTHESIS &,ulong *,ulong *)
0x18001842c  mov     edi, eax
0x18001842e  test    eax, eax
0x180018430  jns     short loc_18001843F
0x180018432  mov     rcx, rbx; pv
0x180018435  call    cs:__imp_CoTaskMemFree
0x18001843b  mov     eax, edi
0x18001843d  jmp     short loc_1800184AF
0x18001843f  mov     edi, [rsp+78h+var_58]
0x180018443  mov     ebp, dword ptr [rsp+78h+arg_20]
0x18001844a  add     rdi, rbx
0x18001844d  test    esi, esi
0x18001844f  jz      short loc_180018492
0x180018451  mov     eax, r14d
0x180018454  lea     r9, [rsp+78h+var_58]; unsigned int *
0x180018459  lea     r8, [rsp+78h+arg_20]; unsigned int *
0x180018461  mov     rdx, rdi; struct tagHYPOTHESIS *
0x180018464  lea     rcx, [rax+rax*4]
0x180018468  lea     rcx, ds:0[rcx*8]
0x180018470  add     rcx, r13; this
0x180018473  call    ?DetachInPlace@_hypothesis_builder@@IEAAJAEAUtagHYPOTHESIS@@PEAK1@Z; _hypothesis_builder::DetachInPlace(tagHYPOTHESIS &,ulong *,ulong *)
0x180018478  test    eax, eax
0x18001847a  js      short loc_180018492
0x18001847c  mov     eax, [rsp+78h+var_58]
0x180018480  inc     r14d
0x180018483  add     ebp, dword ptr [rsp+78h+arg_20]
0x18001848a  add     rdi, rax
0x18001848d  cmp     r14d, esi
0x180018490  jb      short loc_180018451
0x180018492  mov     [r12], rbx
0x180018496  xor     eax, eax
0x180018498  mov     [r15], ebp
0x18001849b  jmp     short loc_1800184AF
0x18001849d  mov     r8, r12; struct tagHYPOTHESIS **
0x1800184a0  mov     rdx, r15; unsigned int *
0x1800184a3  call    ?Detach@_hypothesis_builder@@QEAAJPEAKPEAPEAUtagHYPOTHESIS@@0@Z; _hypothesis_builder::Detach(ulong *,tagHYPOTHESIS * *,ulong *)
0x1800184a8  jmp     short loc_1800184AF
0x1800184aa  mov     eax, 80070057h
0x1800184af  add     rsp, 38h
0x1800184b3  pop     r15
0x1800184b5  pop     r14
0x1800184b7  pop     r13
0x1800184b9  pop     r12
0x1800184bb  pop     rdi
0x1800184bc  pop     rsi
0x1800184bd  pop     rbp
0x1800184be  pop     rbx
0x1800184bf  retn
```
