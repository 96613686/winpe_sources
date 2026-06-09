# _attributes_array_t::CopyAll(ulong *,tagHELPER_ATTRIBUTE * *)

- ea: `0x180017c3c`
- end: `0x180017ce3`
- name: `?CopyAll@_attributes_array_t@@QEAAJPEAKPEAPEAUtagHELPER_ATTRIBUTE@@@Z`
- size: `167`
- prototype: `__int64 __fastcall(_attributes_array_t *this, unsigned int *, struct tagHELPER_ATTRIBUTE **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180017f40`

## callees

- `0x18000d188`
- `0x18000d458`
- `0x18000ef4c`
- `0x180017c3c`
- `0x180017cec`

## pseudocode

```c
__int64 __fastcall _attributes_array_t::CopyAll(
        _attributes_array_t *this,
        unsigned int *a2,
        struct tagHELPER_ATTRIBUTE **a3)
{
  unsigned int v6; // edx
  int v7; // edi
  unsigned int v9; // edi
  __int64 v10; // r14
  unsigned int v11; // ebx
  int v12; // [rsp+20h] [rbp-38h] BYREF
  __int64 v13; // [rsp+28h] [rbp-30h]

  if ( !a2 || !a3 )
    return 2147942487LL;
  v6 = *(_DWORD *)this;
  v12 = 0;
  v13 = 0;
  v7 = _attributes_array_t::SetCount((_attributes_array_t *)&v12, v6);
  if ( v7 >= 0 )
  {
    v9 = 0;
    if ( *(_DWORD *)this )
    {
      v10 = v13;
      do
      {
        _attribute_t::Copy(
          (_attribute_t *)(v10 + 144LL * v9),
          (const struct tagHELPER_ATTRIBUTE *)(144LL * v9 + *((_QWORD *)this + 1)));
        ++v9;
      }
      while ( v9 < *(_DWORD *)this );
    }
    v11 = _attributes_array_t::Detach((_attributes_array_t *)&v12, a2, a3);
    _attributes_array_t::FreeAll((_attributes_array_t *)&v12);
    return v11;
  }
  else
  {
    _attributes_array_t::FreeAll((_attributes_array_t *)&v12);
    return (unsigned int)v7;
  }
}

```

## disassembly

```asm
0x180017c3c  push    rbx
0x180017c3e  push    rbp
0x180017c3f  push    rsi
0x180017c40  push    rdi
0x180017c41  push    r14
0x180017c43  sub     rsp, 30h
0x180017c47  xor     r14d, r14d
0x180017c4a  mov     rsi, r8
0x180017c4d  mov     rbp, rdx
0x180017c50  mov     rbx, rcx
0x180017c53  test    rdx, rdx
0x180017c56  jz      short loc_180017CD3
0x180017c58  test    r8, r8
0x180017c5b  jz      short loc_180017CD3
0x180017c5d  mov     edx, [rcx]; unsigned int
0x180017c5f  lea     rcx, [rsp+58h+var_38]; this
0x180017c64  mov     [rsp+58h+var_38], r14d
0x180017c69  mov     [rsp+58h+var_30], r14
0x180017c6e  call    ?SetCount@_attributes_array_t@@QEAAJK@Z; _attributes_array_t::SetCount(ulong)
0x180017c73  mov     edi, eax
0x180017c75  test    eax, eax
0x180017c77  jns     short loc_180017C87
0x180017c79  lea     rcx, [rsp+58h+var_38]; this
0x180017c7e  call    ?FreeAll@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeAll(void)
0x180017c83  mov     eax, edi
0x180017c85  jmp     short loc_180017CD8
0x180017c87  mov     edi, r14d
0x180017c8a  cmp     [rbx], r14d
0x180017c8d  jbe     short loc_180017CB3
0x180017c8f  mov     r14, [rsp+58h+var_30]
0x180017c94  mov     rdx, [rbx+8]
0x180017c98  mov     eax, edi
0x180017c9a  lea     rcx, [rax+rax*8]
0x180017c9e  shl     rcx, 4
0x180017ca2  add     rdx, rcx; struct tagHELPER_ATTRIBUTE *
0x180017ca5  add     rcx, r14; this
0x180017ca8  call    ?Copy@_attribute_t@@QEAAJPEBUtagHELPER_ATTRIBUTE@@@Z; _attribute_t::Copy(tagHELPER_ATTRIBUTE const *)
0x180017cad  inc     edi
0x180017caf  cmp     edi, [rbx]
0x180017cb1  jb      short loc_180017C94
0x180017cb3  mov     r8, rsi; struct tagHELPER_ATTRIBUTE **
0x180017cb6  lea     rcx, [rsp+58h+var_38]; this
0x180017cbb  mov     rdx, rbp; unsigned int *
0x180017cbe  call    ?Detach@_attributes_array_t@@QEAAJPEAKPEAPEAUtagHELPER_ATTRIBUTE@@@Z; _attributes_array_t::Detach(ulong *,tagHELPER_ATTRIBUTE * *)
0x180017cc3  lea     rcx, [rsp+58h+var_38]; this
0x180017cc8  mov     ebx, eax
0x180017cca  call    ?FreeAll@_attributes_array_t@@QEAAXXZ; _attributes_array_t::FreeAll(void)
0x180017ccf  mov     eax, ebx
0x180017cd1  jmp     short loc_180017CD8
0x180017cd3  mov     eax, 80070057h
0x180017cd8  add     rsp, 30h
0x180017cdc  pop     r14
0x180017cde  pop     rdi
0x180017cdf  pop     rsi
0x180017ce0  pop     rbp
0x180017ce1  pop     rbx
0x180017ce2  retn
```
