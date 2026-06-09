# MCIDestroyCompression

- ea: `0x180012578`
- end: `0x1800125d9`
- name: `MCIDestroyCompression`
- size: `97`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014088`
- `0x1800142a8`

## callees

- `0x180012578`
- `0x180012630`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall MCIDestroyCompression(__int64 a1)
{
  void (__fastcall *v3)(__int64); // rdi

  if ( *(_DWORD *)a1 != 1128874829 )
    return 2;
  v3 = *(void (__fastcall **)(__int64))(a1 + 8);
  *(_DWORD *)a1 = 0;
  NFMcompress_uninit(*(_QWORD **)(a1 + 24), (__int64)v3, 0, 0);
  if ( v3 )
    v3(*(_QWORD *)(a1 + 24));
  v3(a1);
  return 0;
}

```

## disassembly

```asm
0x180012578  mov     [rsp+arg_0], rbx
0x18001257d  push    rdi
0x18001257e  sub     rsp, 20h
0x180012582  cmp     dword ptr [rcx], 4349434Dh
0x180012588  mov     rbx, rcx
0x18001258b  jz      short loc_180012594
0x18001258d  mov     eax, 2
0x180012592  jmp     short loc_1800125CE
0x180012594  mov     rdi, [rcx+8]
0x180012598  xor     r9d, r9d
0x18001259b  mov     dword ptr [rcx], 0
0x1800125a1  mov     rdx, rdi
0x1800125a4  mov     rcx, [rcx+18h]
0x1800125a8  xor     r8d, r8d
0x1800125ab  call    NFMcompress_uninit
0x1800125b0  test    rdi, rdi
0x1800125b3  jz      short loc_1800125C1
0x1800125b5  mov     rcx, [rbx+18h]
0x1800125b9  mov     rax, rdi
0x1800125bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125c1  mov     rcx, rbx
0x1800125c4  mov     rax, rdi
0x1800125c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125cc  xor     eax, eax
0x1800125ce  mov     rbx, [rsp+28h+arg_0]
0x1800125d3  add     rsp, 20h
0x1800125d7  pop     rdi
0x1800125d8  retn
```
