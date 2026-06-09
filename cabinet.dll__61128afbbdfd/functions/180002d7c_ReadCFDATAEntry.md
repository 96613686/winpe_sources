# ReadCFDATAEntry

- ea: `0x180002d7c`
- end: `0x180002e49`
- name: `ReadCFDATAEntry`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800039b8`

## callees

- `0x180002d7c`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall ReadCFDATAEntry(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _DWORD *a5)
{
  _DWORD *v5; // rsi
  unsigned int v10; // eax
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // rcx
  unsigned int (__fastcall *v14)(__int64, __int64, __int64, _DWORD **, __int64); // rax
  int v15; // ebx
  _DWORD *v17; // rcx
  int v18; // eax

  v5 = a5;
  LODWORD(a5) = 0;
  *v5 = 0;
  v10 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _DWORD **, __int64))(a1 + 48))(
          *(_QWORD *)(a3 + 104),
          a2,
          *(unsigned int *)(a1 + 2848),
          &a5,
          a4);
  if ( *(_DWORD *)(a1 + 2848) != v10 )
  {
    if ( *(_DWORD *)(a1 + 2848) >= v10 )
      return 0;
    goto LABEL_5;
  }
  v11 = *(unsigned __int16 *)(a2 + 4);
  if ( (unsigned int)v11 <= *(_DWORD *)(a3 + 660) )
  {
    v12 = *(_QWORD *)(a3 + 688);
    v13 = *(_QWORD *)(a3 + 104);
    v14 = *(unsigned int (__fastcall **)(__int64, __int64, __int64, _DWORD **, __int64))(a1 + 48);
    v15 = *(unsigned __int16 *)(a2 + 4);
    LODWORD(a5) = 0;
    if ( v15 == v14(v13, v12, v11, &a5, a4) )
      return 1;
LABEL_5:
    v17 = *(_DWORD **)(a3 + 88);
    v18 = (int)a5;
    *v17 = 4;
    v17[1] = v18;
    v17[2] = 1;
  }
  *v5 = 1;
  return 0;
}

```

## disassembly

```asm
0x180002d7c  mov     rax, rsp
0x180002d7f  push    rbx
0x180002d80  push    rbp
0x180002d81  push    rsi
0x180002d82  push    rdi
0x180002d83  push    r14
0x180002d85  sub     rsp, 30h
0x180002d89  mov     rsi, [rsp+58h+arg_20]
0x180002d91  mov     rdi, r8
0x180002d94  mov     rbp, rcx
0x180002d97  mov     [rax-38h], r9
0x180002d9b  mov     r14, r9
0x180002d9e  mov     dword ptr [rax+28h], 0
0x180002da5  lea     r9, [rax+28h]
0x180002da9  mov     rbx, rdx
0x180002dac  mov     dword ptr [rsi], 0
0x180002db2  mov     r8d, [rcx+0B20h]
0x180002db9  mov     rcx, [rdi+68h]
0x180002dbd  mov     rax, [rbp+30h]
0x180002dc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dc6  cmp     [rbp+0B20h], eax
0x180002dcc  jnz     short loc_180002E45
0x180002dce  movzx   r8d, word ptr [rbx+4]
0x180002dd3  cmp     r8d, [rdi+294h]
0x180002dda  ja      short loc_180002E32
0x180002ddc  mov     rdx, [rdi+2B0h]
0x180002de3  lea     r9, [rsp+58h+arg_20]
0x180002deb  mov     rcx, [rdi+68h]
0x180002def  mov     rax, [rbp+30h]
0x180002df3  movzx   ebx, word ptr [rbx+4]
0x180002df7  mov     dword ptr [rsp+58h+arg_20], 0
0x180002e02  mov     [rsp+58h+var_38], r14
0x180002e07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e0c  cmp     ebx, eax
0x180002e0e  jnz     short loc_180002E17
0x180002e10  mov     eax, 1
0x180002e15  jmp     short loc_180002E3A
0x180002e17  mov     rcx, [rdi+58h]
0x180002e1b  mov     eax, dword ptr [rsp+58h+arg_20]
0x180002e22  mov     dword ptr [rcx], 4
0x180002e28  mov     [rcx+4], eax
0x180002e2b  mov     dword ptr [rcx+8], 1
0x180002e32  mov     dword ptr [rsi], 1
0x180002e38  xor     eax, eax
0x180002e3a  add     rsp, 30h
0x180002e3e  pop     r14
0x180002e40  pop     rdi
0x180002e41  pop     rsi
0x180002e42  pop     rbp
0x180002e43  pop     rbx
0x180002e44  retn
0x180002e45  jnb     short loc_180002E38
0x180002e47  jmp     short loc_180002E17
```
