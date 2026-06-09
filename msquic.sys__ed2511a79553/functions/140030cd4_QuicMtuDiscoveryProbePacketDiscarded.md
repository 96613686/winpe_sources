# QuicMtuDiscoveryProbePacketDiscarded

- ea: `0x140030cd4`
- end: `0x140030e00`
- name: `QuicMtuDiscoveryProbePacketDiscarded`
- size: `300`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14002080c`

## callees

- `0x14000d490`
- `0x140030940`
- `0x140030cd4`
- `0x14003c8e0`
- `0x14003ec10`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x140030d37`
- `ntoskrnl!_snprintf_s` at `0x140030d92`
- `ntoskrnl!_snprintf_s` at `0x140030d37`
- `ntoskrnl!_snprintf_s` at `0x140030d92`

## string_xrefs

- `0x140030d12`: `Path[%hhu] Mtu Discovery Received Out of Order: expected=%u received=%u`
- `0x140030d6e`: `Path[%hhu] Mtu Discovery Packet Discarded: size=%u, probe_count=%u`

## pseudocode

```c
__int64 __fastcall QuicMtuDiscoveryProbePacketDiscarded(__int64 a1, __int64 a2, unsigned __int16 a3)
{
  int v5; // ecx
  __int64 v6; // rcx
  __int64 result; // rax
  unsigned __int8 *v8; // rbx
  __int64 v9; // rcx
  int v10; // edx
  char DstBuf[128]; // [rsp+40h] [rbp-A8h] BYREF

  v5 = *(unsigned __int16 *)(a1 + 10);
  if ( a3 == (_WORD)v5 )
  {
    v8 = (unsigned __int8 *)(a1 + 12);
    if ( byte_14005C48B < 0 )
    {
      _snprintf_s(
        DstBuf,
        0x80u,
        0xFFFFFFFFFFFFFFFFuLL,
        "Path[%hhu] Mtu Discovery Packet Discarded: size=%u, probe_count=%u",
        *(unsigned __int8 *)(a1 - 24),
        v5,
        *v8);
      McTemplateU0ps_EtwWriteTransfer(v9, QuicConnLogInfo, a2, DstBuf);
    }
    v10 = *v8;
    if ( v10 < *(unsigned __int8 *)(a2 + 238) - 1 )
    {
      *v8 = v10 + 1;
      return QuicSendSetSendFlag(a2 + 3416, 0x80000000LL);
    }
    else
    {
      return QuicMtuDiscoveryMoveToSearchComplete(a1, a2);
    }
  }
  else if ( (byte_14005C48C & 1) != 0 )
  {
    _snprintf_s(
      DstBuf,
      0x80u,
      0xFFFFFFFFFFFFFFFFuLL,
      "Path[%hhu] Mtu Discovery Received Out of Order: expected=%u received=%u",
      *(unsigned __int8 *)(a1 - 24),
      v5,
      a3);
    return McTemplateU0ps_EtwWriteTransfer(v6, QuicConnLogVerbose, a2, DstBuf);
  }
  return result;
}

```

## disassembly

```asm
0x140030cd4  push    rbx
0x140030cd6  push    rsi
0x140030cd7  push    rdi
0x140030cd8  sub     rsp, 0D0h
0x140030cdf  mov     rax, cs:__security_cookie
0x140030ce6  xor     rax, rsp
0x140030ce9  mov     [rsp+0E8h+var_28], rax
0x140030cf1  mov     rsi, rcx
0x140030cf4  mov     rdi, rdx
0x140030cf7  movzx   ecx, word ptr [rcx+0Ah]
0x140030cfb  cmp     r8w, cx
0x140030cff  jz      short loc_140030D5C
0x140030d01  test    cs:byte_14005C48C, 1
0x140030d08  jz      loc_140030DE4
0x140030d0e  movzx   edx, byte ptr [rsi-18h]
0x140030d12  lea     r9, aPathHhuMtuDisc; "Path[%hhu] Mtu Discovery Received Out o"...
0x140030d19  movzx   eax, r8w
0x140030d1d  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140030d21  mov     [rsp+0E8h+var_B8], eax
0x140030d25  mov     [rsp+0E8h+var_C0], ecx
0x140030d29  lea     rcx, [rsp+0E8h+DstBuf]; DstBuf
0x140030d2e  mov     [rsp+0E8h+var_C8], edx
0x140030d32  mov     edx, 80h; SizeInBytes
0x140030d37  call    cs:__imp__snprintf_s
0x140030d3e  nop     dword ptr [rax+rax+00h]
0x140030d43  lea     r9, [rsp+0E8h+DstBuf]
0x140030d48  mov     r8, rdi
0x140030d4b  lea     rdx, QuicConnLogVerbose
0x140030d52  call    McTemplateU0ps_EtwWriteTransfer
0x140030d57  jmp     loc_140030DE4
0x140030d5c  mov     al, cs:byte_14005C48B
0x140030d62  lea     rbx, [rsi+0Ch]
0x140030d66  test    al, al
0x140030d68  jns     short loc_140030DB2
0x140030d6a  movzx   edx, byte ptr [rsi-18h]
0x140030d6e  lea     r9, aPathHhuMtuDisc_0; "Path[%hhu] Mtu Discovery Packet Discard"...
0x140030d75  movzx   eax, byte ptr [rbx]
0x140030d78  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x140030d7c  mov     [rsp+0E8h+var_B8], eax
0x140030d80  mov     [rsp+0E8h+var_C0], ecx
0x140030d84  lea     rcx, [rsp+0E8h+DstBuf]; DstBuf
0x140030d89  mov     [rsp+0E8h+var_C8], edx
0x140030d8d  mov     edx, 80h; SizeInBytes
0x140030d92  call    cs:__imp__snprintf_s
0x140030d99  nop     dword ptr [rax+rax+00h]
0x140030d9e  lea     r9, [rsp+0E8h+DstBuf]
0x140030da3  mov     r8, rdi
0x140030da6  lea     rdx, QuicConnLogInfo
0x140030dad  call    McTemplateU0ps_EtwWriteTransfer
0x140030db2  movzx   eax, byte ptr [rdi+0EEh]
0x140030db9  movzx   edx, byte ptr [rbx]
0x140030dbc  dec     eax
0x140030dbe  cmp     edx, eax
0x140030dc0  jl      short loc_140030DCF
0x140030dc2  mov     rdx, rdi
0x140030dc5  mov     rcx, rsi
0x140030dc8  call    QuicMtuDiscoveryMoveToSearchComplete
0x140030dcd  jmp     short loc_140030DE4
0x140030dcf  inc     dl
0x140030dd1  lea     rcx, [rdi+0D58h]
0x140030dd8  mov     [rbx], dl
0x140030dda  mov     edx, 80000000h
0x140030ddf  call    QuicSendSetSendFlag
0x140030de4  mov     rcx, [rsp+0E8h+var_28]
0x140030dec  xor     rcx, rsp; StackCookie
0x140030def  call    __security_check_cookie
0x140030df4  add     rsp, 0D0h
0x140030dfb  pop     rdi
0x140030dfc  pop     rsi
0x140030dfd  pop     rbx
0x140030dfe  retn
```
