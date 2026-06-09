# QuicMtuDiscoveryOnAckedPacket

- ea: `0x140030ad0`
- end: `0x140030be4`
- name: `QuicMtuDiscoveryOnAckedPacket`
- size: `276`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140013550`

## callees

- `0x140030940`
- `0x1400309f8`
- `0x140030ad0`
- `0x14003c8e0`
- `0x14003ec10`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x140030b2f`
- `ntoskrnl!_snprintf_s` at `0x140030b84`
- `ntoskrnl!_snprintf_s` at `0x140030b2f`
- `ntoskrnl!_snprintf_s` at `0x140030b84`

## string_xrefs

- `0x140030b0a`: `Path[%hhu] Mtu Discovery Received Out of Order: expected=%u received=%u`
- `0x140030b63`: `Path[%hhu] MTU updated to %hu bytes`

## pseudocode

```c
char __fastcall QuicMtuDiscoveryOnAckedPacket(__int64 a1, unsigned __int16 a2, __int64 a3)
{
  int v5; // ecx
  __int64 v6; // rcx
  __int64 v8; // rcx
  char DstBuf[128]; // [rsp+40h] [rbp-98h] BYREF

  v5 = *(unsigned __int16 *)(a1 + 10);
  if ( a2 == (_WORD)v5 )
  {
    *(_WORD *)(a1 - 8) = v5;
    if ( byte_14005C48B < 0 )
    {
      _snprintf_s(
        DstBuf,
        0x80u,
        0xFFFFFFFFFFFFFFFFuLL,
        "Path[%hhu] MTU updated to %hu bytes",
        *(unsigned __int8 *)(a1 - 24),
        v5);
      McTemplateU0ps_EtwWriteTransfer(v8, QuicConnLogInfo, a3, DstBuf);
    }
    if ( *(_WORD *)(a1 - 8) == *(_WORD *)(a1 + 8) )
      QuicMtuDiscoveryMoveToSearchComplete(a1, a3);
    else
      QuicMtuDiscoveryMoveToSearching(a1, a3);
    return 1;
  }
  else
  {
    if ( (byte_14005C48C & 1) != 0 )
    {
      _snprintf_s(
        DstBuf,
        0x80u,
        0xFFFFFFFFFFFFFFFFuLL,
        "Path[%hhu] Mtu Discovery Received Out of Order: expected=%u received=%u",
        *(unsigned __int8 *)(a1 - 24),
        v5,
        a2);
      McTemplateU0ps_EtwWriteTransfer(v6, QuicConnLogVerbose, a3, DstBuf);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x140030ad0  mov     [rsp+arg_18], rbx
0x140030ad5  push    rdi
0x140030ad6  sub     rsp, 0D0h
0x140030add  mov     rax, cs:__security_cookie
0x140030ae4  xor     rax, rsp
0x140030ae7  mov     [rsp+0D8h+var_18], rax
0x140030aef  mov     rbx, rcx
0x140030af2  mov     rdi, r8
0x140030af5  movzx   ecx, word ptr [rcx+0Ah]
0x140030af9  cmp     dx, cx
0x140030afc  jz      short loc_140030B53
0x140030afe  test    cs:byte_14005C48C, 1
0x140030b05  jz      short loc_140030B4F
0x140030b07  movzx   eax, dx
0x140030b0a  lea     r9, aPathHhuMtuDisc; "Path[%hhu] Mtu Discovery Received Out o"...
0x140030b11  movzx   edx, byte ptr [rbx-18h]
0x140030b15  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140030b19  mov     [rsp+0D8h+var_A8], eax
0x140030b1d  mov     [rsp+0D8h+var_B0], ecx
0x140030b21  lea     rcx, [rsp+0D8h+DstBuf]; DstBuf
0x140030b26  mov     [rsp+0D8h+var_B8], edx
0x140030b2a  mov     edx, 80h; SizeInBytes
0x140030b2f  call    cs:__imp__snprintf_s
0x140030b36  nop     dword ptr [rax+rax+00h]
0x140030b3b  lea     r9, [rsp+0D8h+DstBuf]
0x140030b40  mov     r8, rdi
0x140030b43  lea     rdx, QuicConnLogVerbose
0x140030b4a  call    McTemplateU0ps_EtwWriteTransfer
0x140030b4f  xor     al, al
0x140030b51  jmp     short loc_140030BC2
0x140030b53  mov     [rbx-8], cx
0x140030b57  mov     al, cs:byte_14005C48B
0x140030b5d  test    al, al
0x140030b5f  jns     short loc_140030BA4
0x140030b61  mov     eax, ecx
0x140030b63  lea     r9, aPathHhuMtuUpda; "Path[%hhu] MTU updated to %hu bytes"
0x140030b6a  movzx   ecx, byte ptr [rbx-18h]
0x140030b6e  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140030b72  mov     [rsp+0D8h+var_B0], eax
0x140030b76  mov     edx, 80h; SizeInBytes
0x140030b7b  mov     [rsp+0D8h+var_B8], ecx
0x140030b7f  lea     rcx, [rsp+0D8h+DstBuf]; DstBuf
0x140030b84  call    cs:__imp__snprintf_s
0x140030b8b  nop     dword ptr [rax+rax+00h]
0x140030b90  lea     r9, [rsp+0D8h+DstBuf]
0x140030b95  mov     r8, rdi
0x140030b98  lea     rdx, QuicConnLogInfo
0x140030b9f  call    McTemplateU0ps_EtwWriteTransfer
0x140030ba4  movzx   eax, word ptr [rbx+8]
0x140030ba8  mov     rdx, rdi
0x140030bab  mov     rcx, rbx
0x140030bae  cmp     [rbx-8], ax
0x140030bb2  jnz     short loc_140030BBB
0x140030bb4  call    QuicMtuDiscoveryMoveToSearchComplete
0x140030bb9  jmp     short loc_140030BC0
0x140030bbb  call    QuicMtuDiscoveryMoveToSearching
0x140030bc0  mov     al, 1
0x140030bc2  mov     rcx, [rsp+0D8h+var_18]
0x140030bca  xor     rcx, rsp; StackCookie
0x140030bcd  call    __security_check_cookie
0x140030bd2  mov     rbx, [rsp+0D8h+arg_18]
0x140030bda  add     rsp, 0D0h
0x140030be1  pop     rdi
0x140030be2  retn
```
