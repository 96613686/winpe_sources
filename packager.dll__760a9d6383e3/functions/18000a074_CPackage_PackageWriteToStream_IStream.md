# CPackage::PackageWriteToStream(IStream *)

- ea: `0x18000a074`
- end: `0x18000a1d2`
- name: `?PackageWriteToStream@CPackage@@IEAAJPEAUIStream@@@Z`
- size: `350`
- prototype: `__int64 __fastcall(CPackage *__hidden this, struct IStream *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180006af0`

## callees

- `0x1800075c4`
- `0x1800080a8`
- `0x180008dcc`
- `0x18000a074`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall CPackage::PackageWriteToStream(CPackage *this, struct IStream *a2)
{
  struct IStreamVtbl *lpVtbl; // rax
  int v5; // eax
  struct IStreamVtbl *v6; // rax
  int v7; // eax
  unsigned int v8; // ecx
  __int16 v10; // [rsp+58h] [rbp+28h] BYREF
  int v11; // [rsp+60h] [rbp+30h] BYREF
  __int64 v12; // [rsp+68h] [rbp+38h] BYREF

  v10 = 0;
  v11 = 0;
  LODWORD(v12) = 0;
  if ( ((int (__fastcall *)(struct IStream *, int *, __int64))a2->lpVtbl->Write)(a2, &v11, 4) < 0 )
    return 2147500037LL;
  lpVtbl = a2->lpVtbl;
  v11 = 0;
  v10 = 2;
  if ( ((int (__fastcall *)(struct IStream *, __int16 *, __int64, _QWORD))lpVtbl->Write)(a2, &v10, 2, 0) < 0 )
    return 2147500037LL;
  v11 += 2;
  if ( (int)CPackage::IconWriteToStream(this, a2, (unsigned int *)&v12) < 0 )
    return 2147500037LL;
  v11 += v12;
  v10 = *((_WORD *)this + 52);
  if ( ((int (__fastcall *)(struct IStream *, __int16 *, __int64, _QWORD))a2->lpVtbl->Write)(a2, &v10, 2, 0) < 0 )
    return 2147500037LL;
  v11 += 2;
  if ( *((_DWORD *)this + 26) == 1 )
  {
    v5 = CPackage::CmlWriteToStream(this, a2, (unsigned int *)&v12);
  }
  else
  {
    if ( *((_DWORD *)this + 26) != 3 )
      goto LABEL_11;
    v5 = CPackage::EmbedWriteToStream(this, a2, (unsigned int *)&v12);
  }
  if ( v5 < 0 )
    return 2147500037LL;
  v11 += v12;
LABEL_11:
  v6 = a2->lpVtbl;
  v12 = 0;
  if ( ((int (__fastcall *)(struct IStream *, _QWORD, _QWORD, _QWORD))v6->Seek)(a2, 0, 0, 0) < 0 )
    return 2147500037LL;
  v7 = ((__int64 (__fastcall *)(struct IStream *, int *, __int64))a2->lpVtbl->Write)(a2, &v11, 4);
  v8 = 0;
  if ( v7 < 0 )
    return (unsigned int)-2147467259;
  return v8;
}

```

## disassembly

```asm
0x18000a074  mov     [rsp-18h+arg_0], rbx
0x18000a079  push    rbp
0x18000a07a  push    rdi
0x18000a07b  push    r14
0x18000a07d  mov     rbp, rsp
0x18000a080  sub     rsp, 30h
0x18000a084  xor     eax, eax
0x18000a086  mov     rbx, rdx
0x18000a089  mov     [rbp+arg_8], ax
0x18000a08d  xor     r9d, r9d
0x18000a090  mov     [rbp+arg_10], eax
0x18000a093  mov     rdi, rcx
0x18000a096  mov     dword ptr [rbp+arg_18], eax
0x18000a099  mov     rcx, rbx
0x18000a09c  mov     rax, [rdx]
0x18000a09f  lea     rdx, [rbp+arg_10]
0x18000a0a3  lea     r8d, [r9+4]
0x18000a0a7  mov     rax, [rax+20h]
0x18000a0ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0b0  test    eax, eax
0x18000a0b2  js      loc_18000A1BF
0x18000a0b8  mov     rax, [rbx]
0x18000a0bb  lea     rdx, [rbp+arg_8]
0x18000a0bf  mov     r14d, 2
0x18000a0c5  mov     [rbp+arg_10], 0
0x18000a0cc  xor     r9d, r9d
0x18000a0cf  mov     [rbp+arg_8], r14w
0x18000a0d4  mov     r8d, r14d
0x18000a0d7  mov     rcx, rbx
0x18000a0da  mov     rax, [rax+20h]
0x18000a0de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0e3  test    eax, eax
0x18000a0e5  js      loc_18000A1BF
0x18000a0eb  add     [rbp+arg_10], r14d
0x18000a0ef  lea     r8, [rbp+arg_18]; unsigned int *
0x18000a0f3  mov     rdx, rbx; struct IStream *
0x18000a0f6  mov     rcx, rdi; this
0x18000a0f9  call    ?IconWriteToStream@CPackage@@IEAAJPEAUIStream@@PEAK@Z; CPackage::IconWriteToStream(IStream *,ulong *)
0x18000a0fe  test    eax, eax
0x18000a100  js      loc_18000A1BF
0x18000a106  mov     eax, dword ptr [rbp+arg_18]
0x18000a109  lea     rdx, [rbp+arg_8]
0x18000a10d  add     [rbp+arg_10], eax
0x18000a110  xor     r9d, r9d
0x18000a113  movzx   eax, word ptr [rdi+68h]
0x18000a117  mov     r8d, r14d
0x18000a11a  mov     [rbp+arg_8], ax
0x18000a11e  mov     rcx, rbx
0x18000a121  mov     rax, [rbx]
0x18000a124  mov     rax, [rax+20h]
0x18000a128  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a12d  test    eax, eax
0x18000a12f  js      loc_18000A1BF
0x18000a135  add     [rbp+arg_10], r14d
0x18000a139  mov     ecx, [rdi+68h]
0x18000a13c  sub     ecx, 1
0x18000a13f  jz      short loc_18000A157
0x18000a141  cmp     ecx, r14d
0x18000a144  jnz     short loc_18000A170
0x18000a146  lea     r8, [rbp+arg_18]; unsigned int *
0x18000a14a  mov     rdx, rbx; struct IStream *
0x18000a14d  mov     rcx, rdi; this
0x18000a150  call    ?EmbedWriteToStream@CPackage@@IEAAJPEAUIStream@@PEAK@Z; CPackage::EmbedWriteToStream(IStream *,ulong *)
0x18000a155  jmp     short loc_18000A166
0x18000a157  lea     r8, [rbp+arg_18]; unsigned int *
0x18000a15b  mov     rdx, rbx; struct IStream *
0x18000a15e  mov     rcx, rdi; this
0x18000a161  call    ?CmlWriteToStream@CPackage@@IEAAJPEAUIStream@@PEAK@Z; CPackage::CmlWriteToStream(IStream *,ulong *)
0x18000a166  test    eax, eax
0x18000a168  js      short loc_18000A1BF
0x18000a16a  mov     eax, dword ptr [rbp+arg_18]
0x18000a16d  add     [rbp+arg_10], eax
0x18000a170  mov     rax, [rbx]
0x18000a173  xor     r9d, r9d
0x18000a176  mov     [rbp+arg_18], 0
0x18000a17e  xor     r8d, r8d
0x18000a181  mov     rdx, [rbp+arg_18]
0x18000a185  mov     rcx, rbx
0x18000a188  mov     rax, [rax+28h]
0x18000a18c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a191  test    eax, eax
0x18000a193  js      short loc_18000A1BF
0x18000a195  mov     rax, [rbx]
0x18000a198  lea     rdx, [rbp+arg_10]
0x18000a19c  xor     r9d, r9d
0x18000a19f  mov     rcx, rbx
0x18000a1a2  mov     rax, [rax+20h]
0x18000a1a6  lea     r8d, [r9+4]
0x18000a1aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1af  xor     ecx, ecx
0x18000a1b1  mov     edx, 80004005h
0x18000a1b6  test    eax, eax
0x18000a1b8  cmovs   ecx, edx
0x18000a1bb  mov     eax, ecx
0x18000a1bd  jmp     short loc_18000A1C4
0x18000a1bf  mov     eax, 80004005h
0x18000a1c4  mov     rbx, [rsp+30h+arg_0]
0x18000a1c9  add     rsp, 30h
0x18000a1cd  pop     r14
0x18000a1cf  pop     rdi
0x18000a1d0  pop     rbp
0x18000a1d1  retn
```
