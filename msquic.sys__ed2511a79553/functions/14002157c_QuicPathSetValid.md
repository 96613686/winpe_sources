# QuicPathSetValid

- ea: `0x14002157c`
- end: `0x14002165e`
- name: `QuicPathSetValid`
- size: `226`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1400108c0`
- `0x140012630`
- `0x140015b70`

## callees

- `0x14002157c`
- `0x140021664`
- `0x140030bec`
- `0x14003c8e0`
- `0x14003ec10`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x1400215fe`
- `ntoskrnl!_snprintf_s` at `0x1400215fe`

## string_xrefs

- `0x1400215ac`: `Initial Token`
- `0x1400215cf`: `Path Response`
- `0x1400215e0`: `Path[%hhu] Validated (%s)`

## pseudocode

```c
__int64 __fastcall QuicPathSetValid(__int64 a1, unsigned __int8 *a2, int a3)
{
  __int64 v6; // rcx
  __int64 result; // rax
  _QWORD v8[4]; // [rsp+30h] [rbp-C8h]
  char DstBuf[128]; // [rsp+50h] [rbp-A8h] BYREF

  if ( (a2[1] & 0x20) == 0 )
  {
    v8[0] = "Initial Token";
    v8[1] = "Handshake Packet";
    v8[2] = "Path Response";
    if ( byte_14005C48B < 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Path[%hhu] Validated (%s)", *a2, (const char *)v8[a3]);
      McTemplateU0ps_EtwWriteTransfer(v6, QuicConnLogInfo, a1, DstBuf);
    }
    a2[1] |= 0x20u;
    result = QuicPathSetAllowance(a1, a2, 0xFFFFFFFFLL);
    if ( a3 == 2 )
      return QuicMtuDiscoveryPeerValidated(a2 + 24, a1);
  }
  return result;
}

```

## disassembly

```asm
0x14002157c  push    rbx
0x14002157e  push    rsi
0x14002157f  push    rdi
0x140021580  sub     rsp, 0E0h
0x140021587  mov     rax, cs:__security_cookie
0x14002158e  xor     rax, rsp
0x140021591  mov     [rsp+0F8h+var_28], rax
0x140021599  test    byte ptr [rdx+1], 20h
0x14002159d  mov     rbx, rdx
0x1400215a0  movsxd  rsi, r8d
0x1400215a3  mov     rdi, rcx
0x1400215a6  jnz     loc_140021642
0x1400215ac  lea     rax, aInitialToken; "Initial Token"
0x1400215b3  mov     edx, 80h; SizeInBytes
0x1400215b8  test    cs:byte_14005C48B, dl
0x1400215be  mov     [rsp+0F8h+var_C8], rax
0x1400215c3  lea     rax, aHandshakePacke; "Handshake Packet"
0x1400215ca  mov     [rsp+0F8h+var_C0], rax
0x1400215cf  lea     rax, aPathResponse; "Path Response"
0x1400215d6  mov     [rsp+0F8h+var_B8], rax
0x1400215db  jz      short loc_14002161E
0x1400215dd  movzx   ecx, byte ptr [rbx]
0x1400215e0  lea     r9, aPathHhuValidat; "Path[%hhu] Validated (%s)"
0x1400215e7  mov     rax, [rsp+rsi*8+0F8h+var_C8]
0x1400215ec  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1400215f0  mov     [rsp+0F8h+var_D0], rax
0x1400215f5  mov     [rsp+0F8h+var_D8], ecx
0x1400215f9  lea     rcx, [rsp+0F8h+DstBuf]; DstBuf
0x1400215fe  call    cs:__imp__snprintf_s
0x140021605  nop     dword ptr [rax+rax+00h]
0x14002160a  lea     r9, [rsp+0F8h+DstBuf]
0x14002160f  mov     r8, rdi
0x140021612  lea     rdx, QuicConnLogInfo
0x140021619  call    McTemplateU0ps_EtwWriteTransfer
0x14002161e  or      byte ptr [rbx+1], 20h
0x140021622  or      r8d, 0FFFFFFFFh
0x140021626  mov     rdx, rbx
0x140021629  mov     rcx, rdi
0x14002162c  call    QuicPathSetAllowance
0x140021631  cmp     esi, 2
0x140021634  jnz     short loc_140021642
0x140021636  lea     rcx, [rbx+18h]
0x14002163a  mov     rdx, rdi
0x14002163d  call    QuicMtuDiscoveryPeerValidated
0x140021642  mov     rcx, [rsp+0F8h+var_28]
0x14002164a  xor     rcx, rsp; StackCookie
0x14002164d  call    __security_check_cookie
0x140021652  add     rsp, 0E0h
0x140021659  pop     rdi
0x14002165a  pop     rsi
0x14002165b  pop     rbx
0x14002165c  retn
```
