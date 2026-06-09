# MDIDestroyDecompressionGlobal

- ea: `0x1800088c0`
- end: `0x180008952`
- name: `MDIDestroyDecompressionGlobal`
- size: `146`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000847c`

## callees

- `0x1800088c0`
- `0x180008dc8`
- `0x180009400`
- `0x180015d3c`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall MDIDestroyDecompressionGlobal(__int64 a1)
{
  _QWORD *v2; // rax
  int v3; // eax

  switch ( *(_WORD *)(a1 + 266) & 0xF )
  {
    case 0:
LABEL_9:
      (*(void (__fastcall **)(_QWORD))(a1 + 8))(*(_QWORD *)(a1 + 112));
      (*(void (__fastcall **)(_QWORD))(a1 + 8))(*(_QWORD *)(a1 + 120));
      return 1;
    case 1:
      v3 = MDIDestroyDecompression(*(_QWORD *)(a1 + 96));
      goto LABEL_8;
    case 2:
      v3 = QDIDestroyDecompression(*(_QWORD *)(a1 + 96));
LABEL_8:
      if ( v3 )
      {
        v2 = *(_QWORD **)a1;
        **(_QWORD **)a1 = 7;
        goto LABEL_14;
      }
      goto LABEL_9;
    case 3:
      v3 = LDIDestroyDecompression(*(_QWORD *)(a1 + 96));
      goto LABEL_8;
    case 15:
      return 1;
  }
  v2 = *(_QWORD **)a1;
  **(_QWORD **)a1 = 6;
LABEL_14:
  *((_DWORD *)v2 + 2) = 1;
  return 0;
}

```

## disassembly

```asm
0x1800088c0  push    rbx
0x1800088c2  sub     rsp, 20h
0x1800088c6  movzx   edx, word ptr [rcx+10Ah]
0x1800088cd  mov     rbx, rcx
0x1800088d0  and     edx, 0Fh
0x1800088d3  jz      short loc_180008902
0x1800088d5  sub     edx, 1
0x1800088d8  jz      short loc_180008927
0x1800088da  sub     edx, 1
0x1800088dd  jz      short loc_180008932
0x1800088df  sub     edx, 1
0x1800088e2  jz      short loc_1800088F5
0x1800088e4  cmp     edx, 0Ch
0x1800088e7  jz      short loc_18000891C
0x1800088e9  mov     rax, [rcx]
0x1800088ec  mov     qword ptr [rax], 6
0x1800088f3  jmp     short loc_180008947
0x1800088f5  mov     rcx, [rcx+60h]
0x1800088f9  call    LDIDestroyDecompression
0x1800088fe  test    eax, eax
0x180008900  jnz     short loc_18000893D
0x180008902  mov     rcx, [rbx+70h]
0x180008906  mov     rax, [rbx+8]
0x18000890a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000890f  mov     rcx, [rbx+78h]
0x180008913  mov     rax, [rbx+8]
0x180008917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000891c  mov     eax, 1
0x180008921  add     rsp, 20h
0x180008925  pop     rbx
0x180008926  retn
0x180008927  mov     rcx, [rcx+60h]
0x18000892b  call    MDIDestroyDecompression
0x180008930  jmp     short loc_1800088FE
0x180008932  mov     rcx, [rcx+60h]
0x180008936  call    QDIDestroyDecompression
0x18000893b  jmp     short loc_1800088FE
0x18000893d  mov     rax, [rbx]
0x180008940  mov     qword ptr [rax], 7
0x180008947  mov     dword ptr [rax+8], 1
0x18000894e  xor     eax, eax
0x180008950  jmp     short loc_180008921
```
