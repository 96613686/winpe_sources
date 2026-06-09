# OptimalEncoderOutputBlock

- ea: `0x180005e58`
- end: `0x18000602f`
- name: `OptimalEncoderOutputBlock`
- size: `471`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180002da0`
- `0x18000689c`

## callees

- `0x180003a60`
- `0x180004c30`
- `0x180005a94`
- `0x180005e58`
- `0x180006038`
- `0x180006ad5`

## pseudocode

```c
__int64 __fastcall OptimalEncoderOutputBlock(__int64 a1)
{
  __int64 v2; // rbx
  bool v3; // zf
  __int64 v4; // r15
  __int64 v5; // r12
  _WORD *v6; // rbp
  _WORD *v7; // r14
  __int64 result; // rax
  __int64 v9; // rax

  v2 = *(_QWORD *)(a1 + 88);
  if ( *(_DWORD *)a1 )
  {
    v7 = (_WORD *)(v2 + 555428);
    v6 = (_WORD *)(v2 + 553412);
    v5 = v2 + 541956;
    v4 = v2 + 552548;
  }
  else
  {
    v3 = *(_DWORD *)(a1 + 28) == 0;
    *(_DWORD *)(a1 + 24) = 0;
    if ( v3 )
      return 1;
    v4 = v2 + 552548;
    makeTable(288, 12, v2 + 552548, v2 + 542052, v2 + 550244, v2 + 551396);
    v5 = v2 + 541956;
    makeTable(32, 8, v2 + 541956, v2 + 541188, v2 + 541700, v2 + 541828);
    v6 = (_WORD *)(v2 + 553412);
    makeTree(288, 15, (_WORD *)(v2 + 553412), (_WORD *)(v2 + 554564), v2 + 555140);
    v7 = (_WORD *)(v2 + 555428);
    makeTree(32, 15, (_WORD *)(v2 + 555428), (_WORD *)(v2 + 555556), v2 + 555620);
  }
  result = OptimalEncoderOutputDynamicBlock(a1);
  if ( !(_DWORD)result )
    return result;
  if ( !*(_DWORD *)a1 )
  {
    v9 = *(_QWORD *)(a1 + 88) + 475628LL;
    *(_QWORD *)(v2 + 541164) = 0;
    *(_QWORD *)(v2 + 541176) = v9;
    *(_DWORD *)(a1 + 28) = 0;
    NormaliseFrequencies(v6, v7);
    makeTree(32, 9, v7, (_WORD *)(v2 + 541988), v5);
    makeTree(288, 13, v6, (_WORD *)(v2 + 552836), v4);
    memset_0(v6, 0, 0x480u);
    memset_0(v7, 0, 0x80u);
    result = 1;
    *(_WORD *)(v2 + 553924) = 1;
    return result;
  }
  return 1;
}

```

## disassembly

```asm
0x180005e58  push    rbx
0x180005e5a  push    rbp
0x180005e5b  push    rsi
0x180005e5c  push    rdi
0x180005e5d  push    r12
0x180005e5f  push    r14
0x180005e61  push    r15
0x180005e63  sub     rsp, 30h
0x180005e67  cmp     dword ptr [rcx], 0
0x180005e6a  mov     rdi, rcx
0x180005e6d  mov     rbx, [rcx+58h]
0x180005e71  mov     r14d, 120h
0x180005e77  jnz     loc_180005F50
0x180005e7d  cmp     dword ptr [rcx+1Ch], 0
0x180005e81  mov     dword ptr [rcx+18h], 0
0x180005e88  jz      loc_18000601B
0x180005e8e  lea     rcx, [rbx+86564h]
0x180005e95  mov     edx, 0Ch
0x180005e9a  lea     rax, [rbx+869E4h]
0x180005ea1  mov     [rsp+68h+var_40], rax
0x180005ea6  lea     r15, [rbx+86E64h]
0x180005ead  mov     [rsp+68h+var_48], rcx
0x180005eb2  lea     r9, [rbx+84564h]
0x180005eb9  mov     ecx, r14d
0x180005ebc  mov     r8, r15
0x180005ebf  call    makeTable
0x180005ec4  lea     rcx, [rbx+84404h]
0x180005ecb  mov     edx, 8
0x180005ed0  lea     rax, [rbx+84484h]
0x180005ed7  mov     [rsp+68h+var_40], rax
0x180005edc  lea     r12, [rbx+84504h]
0x180005ee3  mov     [rsp+68h+var_48], rcx
0x180005ee8  lea     r9, [rbx+84204h]
0x180005eef  lea     ecx, [rdx+18h]
0x180005ef2  mov     r8, r12
0x180005ef5  call    makeTable
0x180005efa  lea     rax, [rbx+87884h]
0x180005f01  mov     edx, 0Fh
0x180005f06  lea     rbp, [rbx+871C4h]
0x180005f0d  mov     [rsp+68h+var_48], rax
0x180005f12  mov     r8, rbp
0x180005f15  lea     r9, [rbx+87644h]
0x180005f1c  mov     ecx, r14d
0x180005f1f  call    makeTree
0x180005f24  mov     edx, 0Fh
0x180005f29  lea     rax, [rbx+87A64h]
0x180005f30  lea     r14, [rbx+879A4h]
0x180005f37  mov     [rsp+68h+var_48], rax
0x180005f3c  lea     r9, [rbx+87A24h]
0x180005f43  mov     r8, r14
0x180005f46  lea     ecx, [rdx+11h]
0x180005f49  call    makeTree
0x180005f4e  jmp     short loc_180005F6C
0x180005f50  lea     r14, [rbx+879A4h]
0x180005f57  lea     rbp, [rbx+871C4h]
0x180005f5e  lea     r12, [rbx+84504h]
0x180005f65  lea     r15, [rbx+86E64h]
0x180005f6c  mov     rcx, rdi
0x180005f6f  call    OptimalEncoderOutputDynamicBlock
0x180005f74  test    eax, eax
0x180005f76  jz      loc_180006020
0x180005f7c  cmp     dword ptr [rdi], 0
0x180005f7f  jnz     loc_18000601B
0x180005f85  mov     rax, [rdi+58h]
0x180005f89  mov     rdx, r14
0x180005f8c  add     rax, 741ECh
0x180005f92  mov     qword ptr [rbx+841ECh], 0
0x180005f9d  mov     [rbx+841F8h], rax
0x180005fa4  mov     rcx, rbp
0x180005fa7  mov     dword ptr [rdi+1Ch], 0
0x180005fae  call    NormaliseFrequencies
0x180005fb3  mov     edx, 9
0x180005fb8  mov     [rsp+68h+var_48], r12
0x180005fbd  lea     r9, [rbx+84524h]
0x180005fc4  mov     r8, r14
0x180005fc7  lea     ecx, [rdx+17h]
0x180005fca  call    makeTree
0x180005fcf  lea     r9, [rbx+86F84h]
0x180005fd6  mov     [rsp+68h+var_48], r15
0x180005fdb  mov     r8, rbp
0x180005fde  mov     edx, 0Dh
0x180005fe3  mov     ecx, 120h
0x180005fe8  call    makeTree
0x180005fed  xor     edx, edx; Val
0x180005fef  mov     r8d, 480h; Size
0x180005ff5  mov     rcx, rbp; void *
0x180005ff8  call    memset_0
0x180005ffd  xor     edx, edx; Val
0x180005fff  mov     r8d, 80h; Size
0x180006005  mov     rcx, r14; void *
0x180006008  call    memset_0
0x18000600d  mov     eax, 1
0x180006012  mov     [rbx+873C4h], ax
0x180006019  jmp     short loc_180006020
0x18000601b  mov     eax, 1
0x180006020  add     rsp, 30h
0x180006024  pop     r15
0x180006026  pop     r14
0x180006028  pop     r12
0x18000602a  pop     rdi
0x18000602b  pop     rsi
0x18000602c  pop     rbp
0x18000602d  pop     rbx
0x18000602e  retn
```
