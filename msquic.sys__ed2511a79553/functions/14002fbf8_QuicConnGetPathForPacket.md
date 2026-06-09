# QuicConnGetPathForPacket

- ea: `0x14002fbf8`
- end: `0x14002fdbe`
- name: `QuicConnGetPathForPacket`
- size: `454`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140015480`

## callees

- `0x140004840`
- `0x1400078c8`
- `0x14002fbf8`
- `0x140035258`
- `0x14003cb00`
- `0x140048c78`

## pseudocode

```c
__int64 __fastcall QuicConnGetPathForPacket(__int64 a1, __int64 a2)
{
  _BYTE *v2; // r15
  unsigned __int8 v3; // r9
  unsigned __int8 v4; // di
  _QWORD *v5; // r14
  __int64 v8; // r11
  char v9; // r9
  __int64 v10; // r10
  __int64 v11; // r10
  unsigned __int8 v12; // di
  __int64 v13; // rsi
  __int64 v14; // rcx
  __int16 v15; // ax
  bool v16; // zf
  __int64 v18; // rax

  v2 = (_BYTE *)(a1 + 275);
  v3 = 0;
  v4 = *(_BYTE *)(a1 + 275);
  v5 = (_QWORD *)(a2 + 8);
  if ( !v4 )
    goto LABEL_22;
  v8 = *v5;
  do
  {
    if ( (unsigned __int8)QuicAddrCompare(v8 + 36, 240LL * v3 + a1 + 404)
      && (unsigned __int8)QuicAddrCompare(v8 + 8, v10 + a1 + 376) )
    {
      return v11 + a1 + 320;
    }
    if ( (*(_BYTE *)(a1 + 250) & 2) == 0 )
      return 0;
    v3 = v9 + 1;
  }
  while ( v3 < v4 );
  v2 = (_BYTE *)(a1 + 275);
  if ( v4 != 4 )
    goto LABEL_22;
  v12 = 3;
  v13 = a1 + 1096;
  do
  {
    if ( (*(_BYTE *)(v13 - 55) & 2) == 0 )
    {
      v14 = *(_QWORD *)(a2 + 8);
      v15 = *(_WORD *)(v14 + 8);
      if ( v15 == *(_WORD *)v13 )
      {
        if ( v15 == 2 )
        {
          v16 = *(_DWORD *)(v14 + 12) == *(_DWORD *)(v13 + 4);
        }
        else
        {
          if ( *(_QWORD *)(v14 + 16) != *(_QWORD *)(v13 + 8) )
            goto LABEL_19;
          v16 = *(_QWORD *)(v14 + 24) == *(_QWORD *)(v13 + 16);
        }
        if ( v16 && (unsigned __int8)QuicAddrCompare(v14 + 36, v13 + 28) )
          QuicPathRemove(a1, v12);
      }
    }
LABEL_19:
    v13 -= 240;
    --v12;
  }
  while ( v12 );
  v2 = (_BYTE *)(a1 + 275);
  v5 = (_QWORD *)(a2 + 8);
  v4 = *(_BYTE *)(a1 + 275);
  if ( v4 == 4 )
    return 0;
LABEL_22:
  if ( v4 > 1u )
    memmove((void *)(a1 + 800), (const void *)(a1 + 560), 240LL * v4 - 240);
  QuicPathInitialize(a1, (unsigned __int8 *)(a1 + 560));
  ++*v2;
  v18 = *(_QWORD *)(a1 + 464);
  if ( !*(_BYTE *)(v18 + 33) )
    *(_QWORD *)(a1 + 704) = v18;
  *(_QWORD *)(a1 + 600) = *(_QWORD *)(a1 + 360);
  QuicCopyRouteInfo(a1 + 608, *v5);
  return a1 + 560;
}

```

## disassembly

```asm
0x14002fbf8  mov     [rsp+arg_0], rbx
0x14002fbfd  mov     [rsp+arg_8], rbp
0x14002fc02  mov     [rsp+arg_10], rsi
0x14002fc07  push    rdi
0x14002fc08  push    r14
0x14002fc0a  push    r15
0x14002fc0c  sub     rsp, 20h
0x14002fc10  lea     r15, [rcx+113h]
0x14002fc17  xor     r9b, r9b
0x14002fc1a  mov     dil, [r15]
0x14002fc1d  lea     r14, [rdx+8]
0x14002fc21  mov     rbp, rdx
0x14002fc24  mov     rbx, rcx
0x14002fc27  test    dil, dil
0x14002fc2a  jz      loc_14002FD3A
0x14002fc30  mov     r11, [r14]
0x14002fc33  movzx   eax, r9b
0x14002fc37  lea     rdx, [rbx+194h]
0x14002fc3e  imul    r10, rax, 0F0h
0x14002fc45  lea     rcx, [r11+24h]
0x14002fc49  add     rdx, r10
0x14002fc4c  call    QuicAddrCompare
0x14002fc51  test    al, al
0x14002fc53  jz      short loc_14002FC6C
0x14002fc55  lea     rdx, [rbx+178h]
0x14002fc5c  add     rdx, r10
0x14002fc5f  lea     rcx, [r11+8]
0x14002fc63  call    QuicAddrCompare
0x14002fc68  test    al, al
0x14002fc6a  jnz     short loc_14002FCD2
0x14002fc6c  test    byte ptr [rbx+0FAh], 2
0x14002fc73  jz      loc_14002FD36
0x14002fc79  inc     r9b
0x14002fc7c  cmp     r9b, dil
0x14002fc7f  jb      short loc_14002FC33
0x14002fc81  lea     r15, [rbx+113h]
0x14002fc88  cmp     dil, 4
0x14002fc8c  jnz     loc_14002FD3A
0x14002fc92  sub     dil, 1
0x14002fc96  jz      loc_14002FD29
0x14002fc9c  movzx   eax, dil
0x14002fca0  imul    rsi, rax, 0F0h
0x14002fca7  add     rsi, 178h
0x14002fcae  add     rsi, rbx
0x14002fcb1  test    byte ptr [rsi-37h], 2
0x14002fcb5  jnz     short loc_14002FD11
0x14002fcb7  mov     rcx, [rbp+8]
0x14002fcbb  movzx   eax, word ptr [rcx+8]
0x14002fcbf  cmp     ax, [rsi]
0x14002fcc2  jnz     short loc_14002FD11
0x14002fcc4  cmp     ax, 2
0x14002fcc8  jnz     short loc_14002FCE1
0x14002fcca  mov     eax, [rcx+0Ch]
0x14002fccd  cmp     eax, [rsi+4]
0x14002fcd0  jmp     short loc_14002FCF3
0x14002fcd2  lea     rax, [rbx+140h]
0x14002fcd9  add     rax, r10
0x14002fcdc  jmp     loc_14002FDA4
0x14002fce1  mov     rax, [rcx+10h]
0x14002fce5  cmp     rax, [rsi+8]
0x14002fce9  jnz     short loc_14002FD11
0x14002fceb  mov     rax, [rcx+18h]
0x14002fcef  cmp     rax, [rsi+10h]
0x14002fcf3  jnz     short loc_14002FD11
0x14002fcf5  lea     rdx, [rsi+1Ch]
0x14002fcf9  add     rcx, 24h ; '$'
0x14002fcfd  call    QuicAddrCompare
0x14002fd02  test    al, al
0x14002fd04  jz      short loc_14002FD11
0x14002fd06  mov     dl, dil
0x14002fd09  mov     rcx, rbx
0x14002fd0c  call    QuicPathRemove
0x14002fd11  sub     rsi, 0F0h
0x14002fd18  add     dil, 0FFh
0x14002fd1c  jnz     short loc_14002FCB1
0x14002fd1e  lea     r15, [rbx+113h]
0x14002fd25  lea     r14, [rbp+8]
0x14002fd29  mov     dil, [rbx+113h]
0x14002fd30  cmp     dil, 4
0x14002fd34  jnz     short loc_14002FD3A
0x14002fd36  xor     eax, eax
0x14002fd38  jmp     short loc_14002FDA4
0x14002fd3a  lea     rsi, [rbx+230h]
0x14002fd41  cmp     dil, 1
0x14002fd45  jbe     short loc_14002FD68
0x14002fd47  movzx   eax, dil
0x14002fd4b  lea     rcx, [rbx+320h]; void *
0x14002fd52  imul    r8, rax, 0F0h
0x14002fd59  mov     rdx, rsi; Src
0x14002fd5c  sub     r8, 0F0h; Size
0x14002fd63  call    memmove
0x14002fd68  mov     rdx, rsi
0x14002fd6b  mov     rcx, rbx
0x14002fd6e  call    QuicPathInitialize
0x14002fd73  inc     byte ptr [r15]
0x14002fd76  mov     rax, [rbx+1D0h]
0x14002fd7d  cmp     byte ptr [rax+21h], 0
0x14002fd81  jnz     short loc_14002FD8A
0x14002fd83  mov     [rsi+90h], rax
0x14002fd8a  mov     rcx, [rbx+168h]
0x14002fd91  mov     [rsi+28h], rcx
0x14002fd95  lea     rcx, [rsi+30h]
0x14002fd99  mov     rdx, [r14]
0x14002fd9c  call    QuicCopyRouteInfo
0x14002fda1  mov     rax, rsi
0x14002fda4  mov     rbx, [rsp+38h+arg_0]
0x14002fda9  mov     rbp, [rsp+38h+arg_8]
0x14002fdae  mov     rsi, [rsp+38h+arg_10]
0x14002fdb3  add     rsp, 20h
0x14002fdb7  pop     r15
0x14002fdb9  pop     r14
0x14002fdbb  pop     rdi
0x14002fdbc  retn
```
