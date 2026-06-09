# MCICreateCompression

- ea: `0x1800142a8`
- end: `0x18001437b`
- name: `MCICreateCompression`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180013f34`

## callees

- `0x180012328`
- `0x180012414`
- `0x180012578`
- `0x1800142a8`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall MCICreateCompression(
        _DWORD *a1,
        __int64 (__fastcall *a2)(__int64),
        void (__fastcall *a3)(__int64),
        _DWORD *a4,
        __int64 *a5)
{
  __int64 v9; // rbx
  __int64 v11; // rax

  *a5 = 0;
  if ( (unsigned int)(*a1 - 1) > 0x7FFF )
    *a1 = 0x8000;
  v9 = a2(32);
  if ( !v9 )
    return 1;
  v11 = NFMcomp_allocate(a2, 0, 0);
  *(_QWORD *)(v9 + 24) = v11;
  if ( !v11 )
  {
    a3(v9);
    return 1;
  }
  *(_DWORD *)v9 = 1128874829;
  *(_QWORD *)(v9 + 8) = a3;
  *(_DWORD *)(v9 + 16) = *a1;
  *a4 = *a1 + 12;
  if ( (unsigned int)NFMcompress_init(*(_QWORD **)(v9 + 24), (__int64)a2, (__int64)a3, 0, 0, 0) )
  {
    MCIDestroyCompression(v9);
    return 1;
  }
  *a5 = v9;
  return 0;
}

```

## disassembly

```asm
0x1800142a8  push    rbx
0x1800142aa  push    rbp
0x1800142ab  push    rsi
0x1800142ac  push    rdi
0x1800142ad  push    r14
0x1800142af  push    r15
0x1800142b1  sub     rsp, 38h
0x1800142b5  mov     rsi, [rsp+68h+arg_20]
0x1800142bd  mov     r15, r9
0x1800142c0  mov     r14, r8
0x1800142c3  mov     rbp, rdx
0x1800142c6  mov     rdi, rcx
0x1800142c9  mov     qword ptr [rsi], 0
0x1800142d0  mov     eax, [rcx]
0x1800142d2  dec     eax
0x1800142d4  cmp     eax, 7FFFh
0x1800142d9  jbe     short loc_1800142E1
0x1800142db  mov     dword ptr [rcx], 8000h
0x1800142e1  mov     ecx, 20h ; ' '
0x1800142e6  mov     rax, rbp
0x1800142e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142ee  mov     rbx, rax
0x1800142f1  test    rax, rax
0x1800142f4  jnz     short loc_1800142FD
0x1800142f6  mov     eax, 1
0x1800142fb  jmp     short loc_18001436E
0x1800142fd  xor     r8d, r8d
0x180014300  xor     edx, edx
0x180014302  mov     rcx, rbp
0x180014305  call    NFMcomp_allocate
0x18001430a  mov     [rbx+18h], rax
0x18001430e  test    rax, rax
0x180014311  jnz     short loc_180014320
0x180014313  mov     rcx, rbx
0x180014316  mov     rax, r14
0x180014319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001431e  jmp     short loc_1800142F6
0x180014320  mov     dword ptr [rbx], 4349434Dh
0x180014326  xor     r9d, r9d
0x180014329  mov     [rbx+8], r14
0x18001432d  mov     r8, r14
0x180014330  mov     eax, [rdi]
0x180014332  mov     rdx, rbp
0x180014335  mov     [rbx+10h], eax
0x180014338  mov     eax, [rdi]
0x18001433a  add     eax, 0Ch
0x18001433d  mov     [rsp+68h+var_40], 0
0x180014346  mov     [r15], eax
0x180014349  mov     rcx, [rbx+18h]
0x18001434d  mov     [rsp+68h+var_48], 0
0x180014356  call    NFMcompress_init
0x18001435b  test    eax, eax
0x18001435d  jz      short loc_180014369
0x18001435f  mov     rcx, rbx
0x180014362  call    MCIDestroyCompression
0x180014367  jmp     short loc_1800142F6
0x180014369  mov     [rsi], rbx
0x18001436c  xor     eax, eax
0x18001436e  add     rsp, 38h
0x180014372  pop     r15
0x180014374  pop     r14
0x180014376  pop     rdi
0x180014377  pop     rsi
0x180014378  pop     rbp
0x180014379  pop     rbx
0x18001437a  retn
```
