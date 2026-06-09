# GenerateSstpMessageWithStatus

- ea: `0x1400185f8`
- end: `0x140018690`
- name: `GenerateSstpMessageWithStatus`
- size: `152`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140016414`
- `0x1400165a0`
- `0x14001707c`

## callees

- `0x140018114`
- `0x1400185f8`

## pseudocode

```c
char __fastcall GenerateSstpMessageWithStatus(
        __int16 a1,
        char a2,
        unsigned int a3,
        _WORD *a4,
        __int16 a5,
        unsigned __int16 *a6)
{
  unsigned __int16 *v6; // rbx
  __int64 v8; // r9
  unsigned __int16 v9; // ax
  char result; // al
  __int64 v11; // [rsp+30h] [rbp-18h] BYREF

  v6 = a6;
  *a4 = 272;
  a4[2] = __ROR2__(a1, 8);
  a5 = 0;
  *v6 = 8;
  v11 = 0;
  BYTE3(v11) = a2;
  a4[3] = 256;
  v8 = *v6;
  v9 = 4095 - *v6;
  HIDWORD(v11) = _byteswap_ulong(a3);
  result = GenerateSstpAttribute(2, &v11, 8u, (__int64)a4 + v8, v9, &a5);
  if ( result )
  {
    *v6 += a5;
    a4[1] = __ROR2__(*v6, 8);
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x1400185f8  mov     r11, rsp
0x1400185fb  mov     [r11+8], rbx
0x1400185ff  push    rdi
0x140018600  sub     rsp, 40h
0x140018604  mov     rbx, [rsp+48h+arg_28]
0x140018609  xor     eax, eax
0x14001860b  ror     cx, 8
0x14001860f  mov     rdi, r9
0x140018612  mov     word ptr [r9], 110h
0x140018618  mov     [r9+4], cx
0x14001861d  lea     ecx, [rax+8]
0x140018620  mov     [rsp+48h+arg_20], ax
0x140018625  mov     [rbx], cx
0x140018628  mov     [r11-18h], rax
0x14001862c  bswap   r8d
0x14001862f  mov     [rsp+48h+var_15], dl
0x140018633  mov     eax, 0FFFh
0x140018638  mov     word ptr [r9+6], 100h
0x14001863f  lea     rdx, [r11-18h]
0x140018643  movzx   r9d, word ptr [rbx]
0x140018647  sub     ax, r9w
0x14001864b  mov     [r11-14h], r8d
0x14001864f  mov     r8d, ecx
0x140018652  add     r9, rdi
0x140018655  lea     rcx, [r11+28h]
0x140018659  mov     [r11-20h], rcx
0x14001865d  mov     [rsp+48h+var_28], ax
0x140018662  lea     ecx, [r8-6]
0x140018666  call    GenerateSstpAttribute
0x14001866b  test    al, al
0x14001866d  jz      short loc_140018684
0x14001866f  movzx   eax, [rsp+48h+arg_20]
0x140018674  add     [rbx], ax
0x140018677  movzx   eax, word ptr [rbx]
0x14001867a  ror     ax, 8
0x14001867e  mov     [rdi+2], ax
0x140018682  mov     al, 1
0x140018684  mov     rbx, [rsp+48h+arg_0]
0x140018689  add     rsp, 40h
0x14001868d  pop     rdi
0x14001868e  retn
```
