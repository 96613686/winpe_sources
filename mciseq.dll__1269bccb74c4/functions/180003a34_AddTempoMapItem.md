# AddTempoMapItem

- ea: `0x180003a34`
- end: `0x180003ace`
- name: `AddTempoMapItem`
- size: `154`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180003fdc`
- `0x180004ef0`

## callees

- `0x18000128c`
- `0x1800012fc`
- `0x180003a34`

## pseudocode

```c
__int64 __fastcall AddTempoMapItem(__int64 a1, unsigned int a2, unsigned int a3)
{
  _DWORD *v3; // rdi
  __int64 v6; // rcx
  __int64 i; // r8
  __int64 v9; // r8
  __int64 result; // rax
  unsigned int *v11; // r9
  unsigned int v12; // edx

  v3 = 0;
  v6 = *(unsigned int *)(a1 + 188);
  for ( i = (qword_18000A628[2 * (unsigned int)v6] + 16) & -(__int64)(qword_18000A628[2 * (unsigned int)v6] != 0);
        i;
        i = v9 + 16 )
  {
    v3 = (_DWORD *)i;
    v9 = *(_QWORD *)(i - 16);
    if ( !v9 )
      break;
  }
  result = List_Allocate(v6);
  if ( result )
  {
    List_Attach_Tail(*(unsigned int *)(a1 + 188), result);
    v11[1] = a3;
    v11[2] = a2;
    if ( v3 )
      v12 = *v3 + v3[2] * (a3 - v3[1]) / 0x3E8;
    else
      v12 = 0;
    *v11 = v12;
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180003a34  push    rbx
0x180003a36  push    rbp
0x180003a37  push    rsi
0x180003a38  push    rdi
0x180003a39  sub     rsp, 28h
0x180003a3d  xor     edi, edi
0x180003a3f  lea     r9, qword_18000A628
0x180003a46  mov     ebx, r8d
0x180003a49  mov     rsi, rcx
0x180003a4c  mov     ecx, [rcx+0BCh]
0x180003a52  mov     ebp, edx
0x180003a54  mov     eax, ecx
0x180003a56  add     rax, rax
0x180003a59  mov     r9, [r9+rax*8]
0x180003a5d  lea     rax, [r9+10h]
0x180003a61  neg     r9
0x180003a64  sbb     r8, r8
0x180003a67  and     r8, rax
0x180003a6a  jz      short loc_180003A7E
0x180003a6c  mov     rdi, r8
0x180003a6f  mov     r8, [r8-10h]
0x180003a73  test    r8, r8
0x180003a76  jz      short loc_180003A7E
0x180003a78  add     r8, 10h
0x180003a7c  jnz     short loc_180003A6C
0x180003a7e  call    List_Allocate
0x180003a83  mov     r9, rax
0x180003a86  test    rax, rax
0x180003a89  jz      short loc_180003AC5
0x180003a8b  mov     ecx, [rsi+0BCh]
0x180003a91  mov     rdx, r9
0x180003a94  call    List_Attach_Tail
0x180003a99  mov     [r9+4], ebx
0x180003a9d  mov     [r9+8], ebp
0x180003aa1  test    rdi, rdi
0x180003aa4  jnz     short loc_180003AAA
0x180003aa6  xor     edx, edx
0x180003aa8  jmp     short loc_180003ABD
0x180003aaa  sub     ebx, [rdi+4]
0x180003aad  mov     eax, 10624DD3h
0x180003ab2  imul    ebx, [rdi+8]
0x180003ab6  mul     ebx
0x180003ab8  shr     edx, 6
0x180003abb  add     edx, [rdi]
0x180003abd  mov     [r9], edx
0x180003ac0  mov     eax, 1
0x180003ac5  add     rsp, 28h
0x180003ac9  pop     rdi
0x180003aca  pop     rsi
0x180003acb  pop     rbp
0x180003acc  pop     rbx
0x180003acd  retn
```
