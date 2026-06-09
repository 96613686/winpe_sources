# QuicMtuDiscoveryPeerValidated

- ea: `0x140030bec`
- end: `0x140030ccb`
- name: `QuicMtuDiscoveryPeerValidated`
- size: `223`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1400099b4`
- `0x14002157c`

## callees

- `0x140030844`
- `0x1400309f8`
- `0x140030bec`
- `0x14003c8e0`
- `0x14003ec10`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x140030c7a`
- `ntoskrnl!_snprintf_s` at `0x140030c7a`

## string_xrefs

- `0x140030c73`: `Path[%hhu] Mtu Discovery Initialized: max_mtu=%u, cur/min_mtu=%u`

## pseudocode

```c
__int64 __fastcall QuicMtuDiscoveryPeerValidated(__int64 a1, __int64 a2)
{
  unsigned __int16 MaxMtuForPath; // ax
  char v5; // cl
  __int64 v6; // rcx
  char DstBuf[128]; // [rsp+40h] [rbp-98h] BYREF

  MaxMtuForPath = QuicConnGetMaxMtuForPath(a2, a1 - 24);
  v5 = *(_BYTE *)(a1 + 13);
  *(_WORD *)(a1 + 8) = MaxMtuForPath;
  *(_BYTE *)(a1 + 13) = v5 & 0xFD | (*(_WORD *)(a1 - 8) >= 0x5DCu ? 2 : 0);
  if ( byte_14005C48B < 0 )
  {
    _snprintf_s(
      DstBuf,
      0x80u,
      0xFFFFFFFFFFFFFFFFuLL,
      "Path[%hhu] Mtu Discovery Initialized: max_mtu=%u, cur/min_mtu=%u",
      *(unsigned __int8 *)(a1 - 24),
      MaxMtuForPath,
      *(unsigned __int16 *)(a1 - 8));
    McTemplateU0ps_EtwWriteTransfer(v6, (const EVENT_DESCRIPTOR *)QuicConnLogInfo, a2, DstBuf);
  }
  return QuicMtuDiscoveryMoveToSearching(a1, a2);
}

```

## disassembly

```asm
0x140030bec  mov     [rsp+arg_10], rbx
0x140030bf1  mov     [rsp+arg_18], rsi
0x140030bf6  push    rdi
0x140030bf7  sub     rsp, 0D0h
0x140030bfe  mov     rax, cs:__security_cookie
0x140030c05  xor     rax, rsp
0x140030c08  mov     [rsp+0D8h+var_18], rax
0x140030c10  mov     rdi, rdx
0x140030c13  mov     rbx, rcx
0x140030c16  lea     rdx, [rcx-18h]
0x140030c1a  mov     rcx, rdi
0x140030c1d  call    QuicConnGetMaxMtuForPath
0x140030c22  mov     cl, [rbx+0Dh]
0x140030c25  movzx   r8d, ax
0x140030c29  mov     eax, 5DCh
0x140030c2e  mov     [rbx+8], r8w
0x140030c33  cmp     [rbx-8], ax
0x140030c37  sbb     dl, dl
0x140030c39  and     cl, 0FDh
0x140030c3c  not     dl
0x140030c3e  and     dl, 2
0x140030c41  or      dl, cl
0x140030c43  mov     [rbx+0Dh], dl
0x140030c46  mov     edx, 80h; SizeInBytes
0x140030c4b  test    cs:byte_14005C48B, dl
0x140030c51  jz      short loc_140030C9A
0x140030c53  movzx   r9d, byte ptr [rbx-18h]
0x140030c58  lea     rcx, [rsp+0D8h+DstBuf]; DstBuf
0x140030c5d  movzx   eax, word ptr [rbx-8]
0x140030c61  mov     [rsp+0D8h+var_A8], eax
0x140030c65  mov     [rsp+0D8h+var_B0], r8d
0x140030c6a  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140030c6e  mov     [rsp+0D8h+var_B8], r9d
0x140030c73  lea     r9, aPathHhuMtuDisc_3; "Path[%hhu] Mtu Discovery Initialized: m"...
0x140030c7a  call    cs:__imp__snprintf_s
0x140030c81  nop     dword ptr [rax+rax+00h]
0x140030c86  lea     r9, [rsp+0D8h+DstBuf]
0x140030c8b  mov     r8, rdi
0x140030c8e  lea     rdx, QuicConnLogInfo
0x140030c95  call    McTemplateU0ps_EtwWriteTransfer
0x140030c9a  mov     rdx, rdi
0x140030c9d  mov     rcx, rbx
0x140030ca0  call    QuicMtuDiscoveryMoveToSearching
0x140030ca5  mov     rcx, [rsp+0D8h+var_18]
0x140030cad  xor     rcx, rsp; StackCookie
0x140030cb0  call    __security_check_cookie
0x140030cb5  lea     r11, [rsp+0D8h+var_8]
0x140030cbd  mov     rbx, [r11+20h]
0x140030cc1  mov     rsi, [r11+28h]
0x140030cc5  mov     rsp, r11
0x140030cc8  pop     rdi
0x140030cc9  retn
```
