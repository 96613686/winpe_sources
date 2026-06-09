# SureCloseSocket

- ea: `0x18000a038`
- end: `0x18000a122`
- name: `SureCloseSocket`
- size: `234`
- prototype: `void __fastcall(SOCKET s)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003480`
- `0x180007700`
- `0x180009370`
- `0x180009eb8`

## callees

- `0x180002e7c`
- `0x18000a038`

## import_xrefs

- `WS2_32!__imp_closesocket` at `0x18000a0b3`
- `WS2_32!__imp_closesocket` at `0x18000a10c`
- `WS2_32!__imp_closesocket` at `0x18000a0b3`
- `WS2_32!__imp_closesocket` at `0x18000a10c`
- `WS2_32!__imp_setsockopt` at `0x18000a103`
- `WS2_32!__imp_setsockopt` at `0x18000a103`

## pseudocode

```c
void __fastcall SureCloseSocket(SOCKET s)
{
  _QWORD *v2; // rcx
  int optval; // [rsp+40h] [rbp+8h] BYREF

  optval = 0;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( s == -1 )
  {
    if ( v2 != &WPP_GLOBAL_Control && (*((_BYTE *)v2 + 28) & 8) != 0 )
      WPP_SF_(v2[2], 35, &WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids);
  }
  else if ( closesocket(s) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids);
    optval = 1;
    setsockopt(s, 0xFFFF, 128, (const char *)&optval, 4);
    closesocket(s);
  }
}

```

## disassembly

```asm
0x18000a038  mov     [rsp+arg_8], rbx
0x18000a03d  mov     [rsp+arg_10], rbp
0x18000a042  push    rdi
0x18000a043  sub     rsp, 30h
0x18000a047  mov     rbx, rcx
0x18000a04a  mov     [rsp+38h+optval], 0
0x18000a052  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a059  lea     rdi, WPP_GLOBAL_Control
0x18000a060  mov     ebp, 1
0x18000a065  cmp     rcx, rdi
0x18000a068  jz      short loc_18000A08A
0x18000a06a  test    [rcx+1Ch], bpl
0x18000a06e  jz      short loc_18000A08A
0x18000a070  mov     rcx, [rcx+10h]
0x18000a074  lea     edx, [rbp+21h]
0x18000a077  lea     r8, WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids
0x18000a07e  call    WPP_SF_
0x18000a083  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a08a  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000a08e  jnz     short loc_18000A0B0
0x18000a090  cmp     rcx, rdi
0x18000a093  jz      short loc_18000A112
0x18000a095  test    byte ptr [rcx+1Ch], 8
0x18000a099  jz      short loc_18000A112
0x18000a09b  mov     rcx, [rcx+10h]
0x18000a09f  lea     edx, [rbx+24h]
0x18000a0a2  lea     r8, WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids
0x18000a0a9  call    WPP_SF_
0x18000a0ae  jmp     short loc_18000A112
0x18000a0b0  mov     rcx, rbx; s
0x18000a0b3  call    cs:__imp_closesocket
0x18000a0b9  test    eax, eax
0x18000a0bb  jz      short loc_18000A112
0x18000a0bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a0c4  cmp     rcx, rdi
0x18000a0c7  jz      short loc_18000A0E4
0x18000a0c9  test    byte ptr [rcx+1Ch], 8
0x18000a0cd  jz      short loc_18000A0E4
0x18000a0cf  mov     rcx, [rcx+10h]
0x18000a0d3  lea     r8, WPP_a0505a00a2a33285c6050a52698fd03c_Traceguids
0x18000a0da  mov     edx, 24h ; '$'
0x18000a0df  call    WPP_SF_
0x18000a0e4  lea     r9, [rsp+38h+optval]; optval
0x18000a0e9  mov     [rsp+38h+optval], ebp
0x18000a0ed  mov     edx, 0FFFFh; level
0x18000a0f2  mov     [rsp+38h+optlen], 4; optlen
0x18000a0fa  mov     r8d, 80h; optname
0x18000a100  mov     rcx, rbx; s
0x18000a103  call    cs:__imp_setsockopt
0x18000a109  mov     rcx, rbx; s
0x18000a10c  call    cs:__imp_closesocket
0x18000a112  mov     rbx, [rsp+38h+arg_8]
0x18000a117  mov     rbp, [rsp+38h+arg_10]
0x18000a11c  add     rsp, 30h
0x18000a120  pop     rdi
0x18000a121  retn
```
