# ShutdownPrinter

- ea: `0x180006a8c`
- end: `0x180006b10`
- name: `ShutdownPrinter`
- size: `132`
- prototype: `void __fastcall(__int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180005058`
- `0x1800064e4`
- `0x180007700`

## callees

- `0x180002e7c`
- `0x180003ea0`
- `0x180006a8c`

## import_xrefs

- `WINSPOOL!ClosePrinter` at `0x180006ace`
- `WINSPOOL!ClosePrinter` at `0x180006ace`

## pseudocode

```c
void __fastcall ShutdownPrinter(__int64 a1, __int64 a2, __int64 a3)
{
  void *v4; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, a3, *(_QWORD *)(a1 + 96));
  v4 = *(void **)(a1 + 96);
  if ( v4 != (void *)-1LL )
  {
    if ( !ClosePrinter(v4)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids);
    }
    *(_QWORD *)(a1 + 96) = -1;
  }
}

```

## disassembly

```asm
0x180006a8c  mov     [rsp+arg_0], rbx
0x180006a91  push    rdi
0x180006a92  sub     rsp, 20h
0x180006a96  mov     rbx, rcx
0x180006a99  mov     rcx, cs:WPP_GLOBAL_Control
0x180006aa0  lea     rdi, WPP_GLOBAL_Control
0x180006aa7  cmp     rcx, rdi
0x180006aaa  jz      short loc_180006AC4
0x180006aac  test    byte ptr [rcx+1Ch], 1
0x180006ab0  jz      short loc_180006AC4
0x180006ab2  mov     r9, [rbx+60h]
0x180006ab6  mov     edx, 33h ; '3'
0x180006abb  mov     rcx, [rcx+10h]
0x180006abf  call    WPP_SF_q
0x180006ac4  mov     rcx, [rbx+60h]; hPrinter
0x180006ac8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180006acc  jz      short loc_180006B05
0x180006ace  call    cs:__imp_ClosePrinter
0x180006ad4  test    eax, eax
0x180006ad6  jnz     short loc_180006AFD
0x180006ad8  mov     rcx, cs:WPP_GLOBAL_Control
0x180006adf  cmp     rcx, rdi
0x180006ae2  jz      short loc_180006AFD
0x180006ae4  test    byte ptr [rcx+1Ch], 8
0x180006ae8  jz      short loc_180006AFD
0x180006aea  mov     rcx, [rcx+10h]
0x180006aee  lea     edx, [rax+34h]
0x180006af1  lea     r8, WPP_1de051f85a6e387d48ae044532c4d7a0_Traceguids
0x180006af8  call    WPP_SF_
0x180006afd  mov     qword ptr [rbx+60h], 0FFFFFFFFFFFFFFFFh
0x180006b05  mov     rbx, [rsp+28h+arg_0]
0x180006b0a  add     rsp, 20h
0x180006b0e  pop     rdi
0x180006b0f  retn
```
