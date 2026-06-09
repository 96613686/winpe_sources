# LCICreateCompression

- ea: `0x180016cc0`
- end: `0x180016daf`
- name: `LCICreateCompression`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180013f34`

## callees

- `0x180016cc0`
- `0x180016e08`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall LCICreateCompression(
        _DWORD *a1,
        _DWORD *a2,
        __int64 (__fastcall *a3)(__int64),
        void (__fastcall *a4)(__int64),
        _DWORD *a5,
        __int64 *a6)
{
  __int64 v10; // rax
  __int64 v11; // rbx
  __int64 result; // rax
  __int64 v13; // rax
  unsigned int v14; // ebp

  *a6 = 0;
  v10 = a3(40);
  v11 = v10;
  if ( !v10 )
    return 1;
  *(_DWORD *)(v10 + 28) = 12000000;
  v13 = a3(17336);
  *(_QWORD *)(v11 + 32) = v13;
  if ( !v13 )
  {
    a4(v11);
    return 1;
  }
  v14 = LZX_EncodeInit(v13, *a2, a2[1], (_DWORD)a3, (__int64)a4);
  if ( v14 )
  {
    a4(*(_QWORD *)(v11 + 32));
    a4(v11);
    return v14;
  }
  else
  {
    *(_QWORD *)(v11 + 8) = a3;
    *(_QWORD *)(v11 + 16) = a4;
    *(_DWORD *)(v11 + 24) = *a1;
    *(_DWORD *)v11 = 1128874828;
    *a5 = *a1 + 6144;
    result = 0;
    *a6 = v11;
  }
  return result;
}

```

## disassembly

```asm
0x180016cc0  push    rbx
0x180016cc2  push    rbp
0x180016cc3  push    rsi
0x180016cc4  push    rdi
0x180016cc5  push    r14
0x180016cc7  push    r15
0x180016cc9  sub     rsp, 48h
0x180016ccd  mov     r15, [rsp+78h+arg_28]
0x180016cd5  mov     r14, rcx
0x180016cd8  mov     ecx, 28h ; '('
0x180016cdd  mov     rax, r8
0x180016ce0  mov     rdi, r9
0x180016ce3  mov     rsi, r8
0x180016ce6  mov     rbp, rdx
0x180016ce9  mov     qword ptr [r15], 0
0x180016cf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cf5  mov     rbx, rax
0x180016cf8  test    rax, rax
0x180016cfb  jnz     short loc_180016D07
0x180016cfd  mov     eax, 1
0x180016d02  jmp     loc_180016DA2
0x180016d07  mov     dword ptr [rax+1Ch], 0B71B00h
0x180016d0e  mov     ecx, 43B8h
0x180016d13  mov     rax, rsi
0x180016d16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d1b  mov     [rbx+20h], rax
0x180016d1f  mov     rcx, rax
0x180016d22  test    rax, rax
0x180016d25  jnz     short loc_180016D34
0x180016d27  mov     rcx, rbx
0x180016d2a  mov     rax, rdi
0x180016d2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d32  jmp     short loc_180016CFD
0x180016d34  mov     rax, [rsp+78h+arg_38]
0x180016d3c  mov     r9, rsi
0x180016d3f  mov     r8d, [rbp+4]
0x180016d43  mov     edx, [rbp+0]
0x180016d46  mov     [rsp+78h+var_48], rax
0x180016d4b  mov     [rsp+78h+var_58], rdi
0x180016d50  call    LZX_EncodeInit
0x180016d55  mov     ebp, eax
0x180016d57  test    eax, eax
0x180016d59  jz      short loc_180016D76
0x180016d5b  mov     rcx, [rbx+20h]
0x180016d5f  mov     rax, rdi
0x180016d62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d67  mov     rcx, rbx
0x180016d6a  mov     rax, rdi
0x180016d6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d72  mov     eax, ebp
0x180016d74  jmp     short loc_180016DA2
0x180016d76  mov     [rbx+8], rsi
0x180016d7a  mov     [rbx+10h], rdi
0x180016d7e  mov     eax, [r14]
0x180016d81  mov     [rbx+18h], eax
0x180016d84  mov     rax, [rsp+78h+arg_20]
0x180016d8c  mov     dword ptr [rbx], 4349434Ch
0x180016d92  mov     ecx, [r14]
0x180016d95  add     ecx, 1800h
0x180016d9b  mov     [rax], ecx
0x180016d9d  xor     eax, eax
0x180016d9f  mov     [r15], rbx
0x180016da2  add     rsp, 48h
0x180016da6  pop     r15
0x180016da8  pop     r14
0x180016daa  pop     rdi
0x180016dab  pop     rsi
0x180016dac  pop     rbp
0x180016dad  pop     rbx
0x180016dae  retn
```
