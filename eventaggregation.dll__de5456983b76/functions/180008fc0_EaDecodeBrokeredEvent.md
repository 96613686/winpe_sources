# EaDecodeBrokeredEvent

- ea: `0x180008fc0`
- end: `0x180009067`
- name: `EaDecodeBrokeredEvent`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002e30`
- `0x180003630`
- `0x180008fc0`
- `0x18000b1f8`

## pseudocode

```c
__int64 __fastcall EaDecodeBrokeredEvent(__int64 a1, unsigned __int16 a2, __int64 *a3)
{
  __int64 v4; // rdi
  int v7; // ebx
  USHORT v9; // [rsp+68h] [rbp+20h] BYREF

  v9 = 0;
  v4 = 0;
  v7 = BrpDecodeBrokeredEvent_V1(a1, a2, 0, 0, &v9);
  if ( v7 == -1073741789 )
  {
    v4 = EaLibAllocate(v9);
    if ( !v4 )
      return (unsigned int)-1073741801;
    v7 = BrpDecodeBrokeredEvent_V1(a1, a2, v9, v4, &v9);
  }
  if ( v7 < 0 )
  {
    if ( v4 )
      EaLibFree(v4);
  }
  else
  {
    *a3 = v4;
    return 0;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180008fc0  mov     r11, rsp
0x180008fc3  mov     [r11+8], rbx
0x180008fc7  mov     [r11+10h], rbp
0x180008fcb  push    rsi
0x180008fcc  push    rdi
0x180008fcd  push    r14
0x180008fcf  sub     rsp, 30h
0x180008fd3  xor     eax, eax
0x180008fd5  mov     rsi, r8
0x180008fd8  mov     [rsp+48h+arg_18], ax
0x180008fdd  xor     edi, edi
0x180008fdf  movzx   ebp, dx
0x180008fe2  mov     r14, rcx
0x180008fe5  lea     rax, [r11+20h]
0x180008fe9  xor     r8d, r8d
0x180008fec  xor     r9d, r9d
0x180008fef  mov     [r11-28h], rax
0x180008ff3  call    BrpDecodeBrokeredEvent_V1
0x180008ff8  mov     ebx, eax
0x180008ffa  cmp     eax, 0C0000023h
0x180008fff  jnz     short loc_18000903A
0x180009001  movzx   ecx, [rsp+48h+arg_18]
0x180009006  call    EaLibAllocate
0x18000900b  mov     rdi, rax
0x18000900e  test    rax, rax
0x180009011  jnz     short loc_18000901A
0x180009013  mov     ebx, 0C0000017h
0x180009018  jmp     short loc_180009052
0x18000901a  movzx   r8d, [rsp+48h+arg_18]
0x180009020  lea     rax, [rsp+48h+arg_18]
0x180009025  mov     r9, rdi
0x180009028  mov     [rsp+48h+var_28], rax
0x18000902d  movzx   edx, bp
0x180009030  mov     rcx, r14
0x180009033  call    BrpDecodeBrokeredEvent_V1
0x180009038  mov     ebx, eax
0x18000903a  test    ebx, ebx
0x18000903c  js      short loc_180009045
0x18000903e  mov     [rsi], rdi
0x180009041  xor     ebx, ebx
0x180009043  jmp     short loc_180009052
0x180009045  test    rdi, rdi
0x180009048  jz      short loc_180009052
0x18000904a  mov     rcx, rdi
0x18000904d  call    EaLibFree
0x180009052  mov     rbp, [rsp+48h+arg_8]
0x180009057  mov     eax, ebx
0x180009059  mov     rbx, [rsp+48h+arg_0]
0x18000905e  add     rsp, 30h
0x180009062  pop     r14
0x180009064  pop     rdi
0x180009065  pop     rsi
0x180009066  retn
```
