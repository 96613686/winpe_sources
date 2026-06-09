# TransportOpen

- ea: `0x140018f2c`
- end: `0x140018feb`
- name: `TransportOpen`
- size: `191`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140002e80`
- `0x14000faa0`

## callees

- `0x140003050`
- `0x140003080`
- `0x140018f2c`
- `0x140019358`

## pseudocode

```c
__int64 __fastcall TransportOpen(__int64 a1, char a2)
{
  unsigned int v4; // edi

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_a728e4467e48347853f982ed07c6e2da_Traceguids);
  }
  if ( a2 )
  {
    v4 = WskOpen(a1 + 40, a2);
    if ( !v4 )
      *(_DWORD *)(a1 + 80) |= 2u;
  }
  else
  {
    v4 = WskOpen(a1, 0);
    if ( !v4 )
      *(_DWORD *)(a1 + 80) |= 1u;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_a728e4467e48347853f982ed07c6e2da_Traceguids, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x140018f2c  mov     [rsp+arg_0], rbx
0x140018f31  mov     [rsp+arg_8], rsi
0x140018f36  push    rdi
0x140018f37  sub     rsp, 20h
0x140018f3b  mov     dil, dl
0x140018f3e  mov     rbx, rcx
0x140018f41  mov     rcx, cs:WPP_GLOBAL_Control
0x140018f48  lea     rsi, WPP_GLOBAL_Control
0x140018f4f  cmp     rcx, rsi
0x140018f52  jz      short loc_140018F76
0x140018f54  mov     eax, [rcx+2Ch]
0x140018f57  test    al, 40h
0x140018f59  jz      short loc_140018F76
0x140018f5b  cmp     byte ptr [rcx+29h], 4
0x140018f5f  jb      short loc_140018F76
0x140018f61  mov     rcx, [rcx+18h]
0x140018f65  lea     r8, WPP_a728e4467e48347853f982ed07c6e2da_Traceguids
0x140018f6c  mov     edx, 0Ah
0x140018f71  call    WPP_SF_
0x140018f76  test    dil, dil
0x140018f79  jnz     short loc_140018F91
0x140018f7b  xor     edx, edx
0x140018f7d  mov     rcx, rbx
0x140018f80  call    WskOpen
0x140018f85  mov     edi, eax
0x140018f87  test    eax, eax
0x140018f89  jnz     short loc_140018FA7
0x140018f8b  or      dword ptr [rbx+50h], 1
0x140018f8f  jmp     short loc_140018FA7
0x140018f91  lea     rcx, [rbx+28h]
0x140018f95  mov     dl, dil
0x140018f98  call    WskOpen
0x140018f9d  mov     edi, eax
0x140018f9f  test    eax, eax
0x140018fa1  jnz     short loc_140018FA7
0x140018fa3  or      dword ptr [rbx+50h], 2
0x140018fa7  mov     rcx, cs:WPP_GLOBAL_Control
0x140018fae  cmp     rcx, rsi
0x140018fb1  jz      short loc_140018FD8
0x140018fb3  mov     eax, [rcx+2Ch]
0x140018fb6  test    al, 40h
0x140018fb8  jz      short loc_140018FD8
0x140018fba  cmp     byte ptr [rcx+29h], 4
0x140018fbe  jb      short loc_140018FD8
0x140018fc0  mov     rcx, [rcx+18h]
0x140018fc4  lea     r8, WPP_a728e4467e48347853f982ed07c6e2da_Traceguids
0x140018fcb  mov     edx, 0Bh
0x140018fd0  mov     r9d, edi
0x140018fd3  call    WPP_SF_d
0x140018fd8  mov     rbx, [rsp+28h+arg_0]
0x140018fdd  mov     eax, edi
0x140018fdf  mov     rsi, [rsp+28h+arg_8]
0x140018fe4  add     rsp, 20h
0x140018fe8  pop     rdi
0x140018fe9  retn
```
