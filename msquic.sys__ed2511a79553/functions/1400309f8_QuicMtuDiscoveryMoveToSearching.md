# QuicMtuDiscoveryMoveToSearching

- ea: `0x1400309f8`
- end: `0x140030ac8`
- name: `QuicMtuDiscoveryMoveToSearching`
- size: `208`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400300d4`
- `0x140030ad0`
- `0x140030bec`

## callees

- `0x14000d490`
- `0x1400308e4`
- `0x140030940`
- `0x1400309f8`
- `0x14003c8e0`
- `0x14003ec10`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x140030a7d`
- `ntoskrnl!_snprintf_s` at `0x140030a7d`

## string_xrefs

- `0x140030a61`: `Path[%hhu] Mtu Discovery Search Packet Sending with MTU %hu`

## pseudocode

```c
__int64 __fastcall QuicMtuDiscoveryMoveToSearching(__int64 a1, __int64 a2)
{
  unsigned __int16 NextProbeSize; // r10
  __int64 v5; // rcx
  char DstBuf[128]; // [rsp+30h] [rbp-98h] BYREF

  *(_BYTE *)(a1 + 13) &= ~1u;
  *(_BYTE *)(a1 + 12) = 0;
  if ( (*(_BYTE *)(a1 - 23) & 0x40) != 0 )
    NextProbeSize = QuicGetNextProbeSize();
  else
    NextProbeSize = *(_WORD *)(a1 - 8);
  *(_WORD *)(a1 + 10) = NextProbeSize;
  if ( NextProbeSize == *(_WORD *)(a1 - 8) && (*(_BYTE *)(a1 - 23) & 0x40) != 0 )
    return QuicMtuDiscoveryMoveToSearchComplete(a1, a2);
  if ( byte_14005C48B < 0 )
  {
    _snprintf_s(
      DstBuf,
      0x80u,
      0xFFFFFFFFFFFFFFFFuLL,
      "Path[%hhu] Mtu Discovery Search Packet Sending with MTU %hu",
      *(unsigned __int8 *)(a1 - 24),
      NextProbeSize);
    McTemplateU0ps_EtwWriteTransfer(v5, QuicConnLogInfo, a2, DstBuf);
  }
  return QuicSendSetSendFlag(a2 + 3416, 0x80000000LL);
}

```

## disassembly

```asm
0x1400309f8  push    rbx
0x1400309fa  sub     rsp, 0C0h
0x140030a01  mov     rax, cs:__security_cookie
0x140030a08  xor     rax, rsp
0x140030a0b  mov     [rsp+0C8h+var_18], rax
0x140030a13  and     byte ptr [rcx+0Dh], 0FEh
0x140030a17  mov     rbx, rdx
0x140030a1a  mov     byte ptr [rcx+0Ch], 0
0x140030a1e  test    byte ptr [rcx-17h], 40h
0x140030a22  jz      short loc_140030A2F
0x140030a24  call    QuicGetNextProbeSize
0x140030a29  movzx   r10d, ax
0x140030a2d  jmp     short loc_140030A34
0x140030a2f  movzx   r10d, word ptr [rcx-8]
0x140030a34  mov     [rcx+0Ah], r10w
0x140030a39  cmp     r10w, [rcx-8]
0x140030a3e  jnz     short loc_140030A50
0x140030a40  test    byte ptr [rcx-17h], 40h
0x140030a44  jz      short loc_140030A50
0x140030a46  mov     rdx, rbx
0x140030a49  call    QuicMtuDiscoveryMoveToSearchComplete
0x140030a4e  jmp     short loc_140030AAE
0x140030a50  mov     edx, 80h; SizeInBytes
0x140030a55  test    cs:byte_14005C48B, dl
0x140030a5b  jz      short loc_140030A9D
0x140030a5d  movzx   ecx, byte ptr [rcx-18h]
0x140030a61  lea     r9, aPathHhuMtuDisc_2; "Path[%hhu] Mtu Discovery Search Packet "...
0x140030a68  movzx   eax, r10w
0x140030a6c  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140030a70  mov     [rsp+0C8h+var_A0], eax
0x140030a74  mov     [rsp+0C8h+var_A8], ecx
0x140030a78  lea     rcx, [rsp+0C8h+DstBuf]; DstBuf
0x140030a7d  call    cs:__imp__snprintf_s
0x140030a84  nop     dword ptr [rax+rax+00h]
0x140030a89  lea     r9, [rsp+0C8h+DstBuf]
0x140030a8e  mov     r8, rbx
0x140030a91  lea     rdx, QuicConnLogInfo
0x140030a98  call    McTemplateU0ps_EtwWriteTransfer
0x140030a9d  lea     rcx, [rbx+0D58h]
0x140030aa4  mov     edx, 80000000h
0x140030aa9  call    QuicSendSetSendFlag
0x140030aae  mov     rcx, [rsp+0C8h+var_18]
0x140030ab6  xor     rcx, rsp; StackCookie
0x140030ab9  call    __security_check_cookie
0x140030abe  add     rsp, 0C0h
0x140030ac5  pop     rbx
0x140030ac6  retn
```
