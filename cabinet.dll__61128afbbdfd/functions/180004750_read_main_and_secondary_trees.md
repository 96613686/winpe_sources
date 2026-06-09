# read_main_and_secondary_trees

- ea: `0x180004750`
- end: `0x18000484f`
- name: `read_main_and_secondary_trees`
- size: `255`
- prototype: `_BOOL8 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000548c`

## callees

- `0x180004750`
- `0x1800059b0`
- `0x180006910`

## pseudocode

```c
_BOOL8 __fastcall read_main_and_secondary_trees(__int64 a1)
{
  __int64 v1; // rdi
  unsigned int v3; // edx

  v1 = a1 + 2588;
  if ( !(unsigned int)ReadRepTree(a1, 256, a1 + 11044, a1 + 2588)
    || !(unsigned int)ReadRepTree(a1, 8 * (unsigned int)*(unsigned __int8 *)(a1 + 11973), a1 + 11300, v1 + 256) )
  {
    return 0;
  }
  v3 = 672;
  if ( 8 * (unsigned int)*(unsigned __int8 *)(a1 + 11973) + 256 < 0x2A0 )
    v3 = 8 * *(unsigned __int8 *)(a1 + 11973) + 256;
  return (unsigned int)make_table(a1 + 28, v3, v1, 0xAu, (char *)(a1 + 28), a1 + 3648)
      && (unsigned int)ReadRepTree(a1, 249, a1 + 11716, a1 + 3260)
      && (unsigned int)make_table(a1 + 2076, 0xF9u, a1 + 3260, 8u, (char *)(a1 + 2076), a1 + 9024) != 0;
}

```

## disassembly

```asm
0x180004750  mov     [rsp+arg_0], rbx
0x180004755  mov     [rsp+arg_8], rsi
0x18000475a  push    rdi
0x18000475b  sub     rsp, 30h
0x18000475f  lea     rdi, [rcx+0A1Ch]
0x180004766  mov     edx, 100h
0x18000476b  mov     r9, rdi
0x18000476e  lea     r8, [rcx+2B24h]
0x180004775  mov     rbx, rcx
0x180004778  call    ReadRepTree
0x18000477d  test    eax, eax
0x18000477f  jz      loc_18000484B
0x180004785  movzx   edx, byte ptr [rbx+2EC5h]
0x18000478c  lea     r9, [rdi+100h]
0x180004793  shl     edx, 3
0x180004796  lea     r8, [rbx+2C24h]
0x18000479d  mov     rcx, rbx
0x1800047a0  call    ReadRepTree
0x1800047a5  test    eax, eax
0x1800047a7  jz      loc_18000484B
0x1800047ad  movzx   eax, byte ptr [rbx+2EC5h]
0x1800047b4  lea     rcx, [rbx+1Ch]; int
0x1800047b8  mov     edx, 2A0h
0x1800047bd  mov     r9b, 0Ah; int
0x1800047c0  mov     r8, rdi; int
0x1800047c3  lea     eax, ds:100h[rax*8]
0x1800047ca  cmp     eax, edx
0x1800047cc  cmovb   edx, eax; int
0x1800047cf  lea     rax, [rbx+0E40h]
0x1800047d6  mov     [rsp+38h+var_10], rax; __int64
0x1800047db  mov     [rsp+38h+var_18], rcx; void *
0x1800047e0  call    make_table
0x1800047e5  test    eax, eax
0x1800047e7  jz      short loc_18000484B
0x1800047e9  lea     rdi, [rbx+0CBCh]
0x1800047f0  mov     esi, 0F9h
0x1800047f5  mov     r9, rdi
0x1800047f8  lea     r8, [rbx+2DC4h]
0x1800047ff  mov     edx, esi
0x180004801  mov     rcx, rbx
0x180004804  call    ReadRepTree
0x180004809  test    eax, eax
0x18000480b  jz      short loc_18000484B
0x18000480d  lea     rax, [rbx+2340h]
0x180004814  mov     r9b, 8; int
0x180004817  lea     rcx, [rbx+81Ch]; int
0x18000481e  mov     [rsp+38h+var_10], rax; __int64
0x180004823  mov     r8, rdi; int
0x180004826  mov     [rsp+38h+var_18], rcx; void *
0x18000482b  mov     edx, esi; int
0x18000482d  call    make_table
0x180004832  xor     ecx, ecx
0x180004834  test    eax, eax
0x180004836  setnz   cl
0x180004839  mov     eax, ecx
0x18000483b  mov     rbx, [rsp+38h+arg_0]
0x180004840  mov     rsi, [rsp+38h+arg_8]
0x180004845  add     rsp, 30h
0x180004849  pop     rdi
0x18000484a  retn
0x18000484b  xor     eax, eax
0x18000484d  jmp     short loc_18000483B
```
