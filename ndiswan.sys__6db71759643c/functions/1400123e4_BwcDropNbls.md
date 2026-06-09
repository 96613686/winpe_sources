# BwcDropNbls

- ea: `0x1400123e4`
- end: `0x140012479`
- name: `BwcDropNbls`
- size: `149`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140002974`
- `0x140012570`
- `0x140013080`
- `0x140013570`

## callees

- `0x14000917c`
- `0x1400123e4`
- `0x140015d84`

## pseudocode

```c
__int64 *__fastcall BwcDropNbls(__int64 a1, PVOID a2, _QWORD *a3, _QWORD *a4)
{
  __int64 v4; // r10
  __int64 *result; // rax
  __int64 v7; // rsi
  __int64 v8; // rbp
  _QWORD *v9; // rbx
  _QWORD *v10; // [rsp+58h] [rbp+10h] BYREF
  __int64 v11; // [rsp+60h] [rbp+18h] BYREF
  __int64 *v12; // [rsp+68h] [rbp+20h] BYREF

  v4 = 0;
  result = &v11;
  v11 = 0;
  *a4 = 0;
  if ( !a2 )
    a2 = BwcVirtualLine;
  v12 = &v11;
  if ( a3 )
  {
    v7 = (__int64)a2 + 8;
    v8 = a1 + 40;
    do
    {
      v9 = (_QWORD *)*a3;
      v10 = 0;
      *a3 = 0;
      result = (__int64 *)QosTbcSendNetBufferListComplete(v8, v7, (__int64)a3, (__int64)a4, &v10);
      if ( v10 )
        result = BwcNblAppendNblsMoveLast(&v12, v10);
      a3 = v9;
    }
    while ( v9 );
    v4 = v11;
  }
  *a4 = v4;
  return result;
}

```

## disassembly

```asm
0x1400123e4  mov     r11, rsp
0x1400123e7  mov     [r11+8], rbx
0x1400123eb  push    rbp
0x1400123ec  push    rsi
0x1400123ed  push    rdi
0x1400123ee  sub     rsp, 30h
0x1400123f2  xor     r10d, r10d
0x1400123f5  lea     rax, [r11+18h]
0x1400123f9  test    rdx, rdx
0x1400123fc  mov     [r11+18h], r10
0x140012400  mov     rdi, r9
0x140012403  mov     [r9], r10
0x140012406  cmovz   rdx, cs:BwcVirtualLine
0x14001240e  mov     [r11+20h], rax
0x140012412  test    r8, r8
0x140012415  jz      short loc_140012468
0x140012417  lea     rsi, [rdx+8]
0x14001241b  lea     rbp, [rcx+28h]
0x14001241f  mov     rbx, [r8]
0x140012422  lea     rax, [rsp+48h+arg_8]
0x140012427  mov     rdx, rsi
0x14001242a  mov     [rsp+48h+var_28], rax
0x14001242f  mov     rcx, rbp
0x140012432  mov     [rsp+48h+arg_8], 0
0x14001243b  mov     qword ptr [r8], 0
0x140012442  call    QosTbcSendNetBufferListComplete
0x140012447  mov     rdx, [rsp+48h+arg_8]
0x14001244c  test    rdx, rdx
0x14001244f  jz      short loc_14001245B
0x140012451  lea     rcx, [rsp+48h+arg_18]
0x140012456  call    BwcNblAppendNblsMoveLast
0x14001245b  mov     r8, rbx
0x14001245e  test    rbx, rbx
0x140012461  jnz     short loc_14001241F
0x140012463  mov     r10, [rsp+48h+arg_10]
0x140012468  mov     rbx, [rsp+48h+arg_0]
0x14001246d  mov     [rdi], r10
0x140012470  add     rsp, 30h
0x140012474  pop     rdi
0x140012475  pop     rsi
0x140012476  pop     rbp
0x140012477  retn
```
