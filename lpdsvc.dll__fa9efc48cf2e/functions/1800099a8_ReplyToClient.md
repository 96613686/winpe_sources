# ReplyToClient

- ea: `0x1800099a8`
- end: `0x180009a4c`
- name: `ReplyToClient`
- size: `164`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003480`
- `0x180007354`

## callees

- `0x180002e7c`
- `0x1800099a8`

## import_xrefs

- `WS2_32!__imp_send` at `0x1800099ff`
- `WS2_32!__imp_send` at `0x1800099ff`

## pseudocode

```c
__int64 __fastcall ReplyToClient(__int64 a1, char a2)
{
  SOCKET v4; // rcx
  int v5; // eax
  unsigned int v6; // ebx
  char buf; // [rsp+38h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids);
  v4 = *(_QWORD *)(a1 + 8);
  buf = a2;
  v5 = send(v4, &buf, 1, 0);
  v6 = v5;
  if ( v5 == 1 )
    return 0;
  if ( v5 == -1
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (unsigned int)(v5 + 39),
      &WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids);
  }
  return v6;
}

```

## disassembly

```asm
0x1800099a8  mov     [rsp+arg_0], rbx
0x1800099ad  mov     [rsp+arg_10], rsi
0x1800099b2  push    rdi
0x1800099b3  sub     rsp, 20h
0x1800099b7  movzx   ebx, dx
0x1800099ba  mov     rdi, rcx
0x1800099bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800099c4  lea     rsi, WPP_GLOBAL_Control
0x1800099cb  cmp     rcx, rsi
0x1800099ce  jz      short loc_1800099EB
0x1800099d0  test    byte ptr [rcx+1Ch], 1
0x1800099d4  jz      short loc_1800099EB
0x1800099d6  mov     rcx, [rcx+10h]
0x1800099da  lea     r8, WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids
0x1800099e1  mov     edx, 25h ; '%'
0x1800099e6  call    WPP_SF_
0x1800099eb  mov     rcx, [rdi+8]; s
0x1800099ef  lea     rdx, [rsp+28h+buf]; buf
0x1800099f4  xor     r9d, r9d; flags
0x1800099f7  mov     [rsp+28h+buf], bl
0x1800099fb  lea     r8d, [r9+1]; len
0x1800099ff  call    cs:__imp_send
0x180009a05  mov     ebx, eax
0x180009a07  cmp     eax, 1
0x180009a0a  jnz     short loc_180009A10
0x180009a0c  xor     eax, eax
0x180009a0e  jmp     short loc_180009A3C
0x180009a10  cmp     ebx, 0FFFFFFFFh
0x180009a13  jnz     short loc_180009A3A
0x180009a15  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a1c  cmp     rcx, rsi
0x180009a1f  jz      short loc_180009A3A
0x180009a21  test    byte ptr [rcx+1Ch], 8
0x180009a25  jz      short loc_180009A3A
0x180009a27  mov     rcx, [rcx+10h]
0x180009a2b  lea     edx, [rbx+27h]
0x180009a2e  lea     r8, WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids
0x180009a35  call    WPP_SF_
0x180009a3a  mov     eax, ebx
0x180009a3c  mov     rbx, [rsp+28h+arg_0]
0x180009a41  mov     rsi, [rsp+28h+arg_10]
0x180009a46  add     rsp, 20h
0x180009a4a  pop     rdi
0x180009a4b  retn
```
