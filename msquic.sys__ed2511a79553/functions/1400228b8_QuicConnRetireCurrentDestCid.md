# QuicConnRetireCurrentDestCid

- ea: `0x1400228b8`
- end: `0x140022949`
- name: `QuicConnRetireCurrentDestCid`
- size: `145`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140001d6c`
- `0x140013200`
- `0x140016210`

## callees

- `0x1400228b8`
- `0x140022a9c`
- `0x140022b44`
- `0x14003c8e0`
- `0x14003ec10`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14003e5a4`
- `ntoskrnl!_snprintf_s` at `0x14003e5e8`
- `ntoskrnl!_snprintf_s` at `0x14003e5a4`
- `ntoskrnl!_snprintf_s` at `0x14003e5e8`

## string_xrefs

- `0x14003e5d3`: `Can't retire current CID because we don't have a replacement`

## pseudocode

```c
char __fastcall QuicConnRetireCurrentDestCid(__int64 a1, __int64 a2)
{
  __int64 UnusedDestCid; // rdi
  __int64 v5; // r8
  __int64 v7; // rcx
  __int64 v8; // rcx
  char DstBuf[128]; // [rsp+20h] [rbp-98h] BYREF

  if ( !*(_BYTE *)(*(_QWORD *)(a2 + 144) + 33LL) )
  {
    if ( (byte_14005C48C & 1) != 0 )
    {
      _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Can't retire current CID because it's zero length");
      McTemplateU0ps_EtwWriteTransfer(v7, (const EVENT_DESCRIPTOR *)QuicConnLogVerbose, a1, DstBuf);
    }
    return 1;
  }
  UnusedDestCid = QuicConnGetUnusedDestCid(a1);
  if ( UnusedDestCid )
  {
    QuicConnRetireCid(a1, v5);
    *(_QWORD *)(a2 + 144) = UnusedDestCid;
    *(_BYTE *)(UnusedDestCid + 32) |= 8u;
    ++*(_DWORD *)(a1 + 3852);
    return 1;
  }
  if ( (byte_14005C48B & 0x40) != 0 )
  {
    _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Can't retire current CID because we don't have a replacement");
    McTemplateU0ps_EtwWriteTransfer(v8, (const EVENT_DESCRIPTOR *)QuicConnLogWarning, a1, DstBuf);
  }
  return 0;
}

```

## disassembly

```asm
0x1400228b8  mov     [rsp+arg_10], rbx
0x1400228bd  mov     [rsp+arg_18], rsi
0x1400228c2  push    rdi
0x1400228c3  sub     rsp, 0B0h
0x1400228ca  mov     rax, cs:__security_cookie
0x1400228d1  xor     rax, rsp
0x1400228d4  mov     [rsp+0B8h+var_18], rax
0x1400228dc  mov     r8, [rdx+90h]
0x1400228e3  mov     rsi, rdx
0x1400228e6  mov     rbx, rcx
0x1400228e9  cmp     byte ptr [r8+21h], 0
0x1400228ee  jz      loc_14003E582
0x1400228f4  call    QuicConnGetUnusedDestCid
0x1400228f9  mov     rdi, rax
0x1400228fc  test    rax, rax
0x1400228ff  jz      loc_14003E5CA
0x140022905  mov     rdx, r8
0x140022908  mov     rcx, rbx
0x14002290b  call    QuicConnRetireCid
0x140022910  mov     [rsi+90h], rdi
0x140022917  or      byte ptr [rdi+20h], 8
0x14002291b  inc     dword ptr [rbx+0F0Ch]
0x140022921  mov     al, 1
0x140022923  mov     rcx, [rsp+0B8h+var_18]
0x14002292b  xor     rcx, rsp; StackCookie
0x14002292e  call    __security_check_cookie
0x140022933  lea     r11, [rsp+0B8h+var_8]
0x14002293b  mov     rbx, [r11+20h]
0x14002293f  mov     rsi, [r11+28h]
0x140022943  mov     rsp, r11
0x140022946  pop     rdi
0x140022947  retn
0x14003e582  test    cs:byte_14005C48C, 1
0x14003e589  jz      loc_140022921
0x14003e58f  lea     r9, aCanTRetireCurr_0; "Can't retire current CID because it's z"...
0x14003e596  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14003e59a  mov     edx, 80h; SizeInBytes
0x14003e59f  lea     rcx, [rsp+0B8h+DstBuf]; DstBuf
0x14003e5a4  call    cs:__imp__snprintf_s
0x14003e5ab  nop     dword ptr [rax+rax+00h]
0x14003e5b0  lea     r9, [rsp+0B8h+DstBuf]
0x14003e5b5  mov     r8, rbx
0x14003e5b8  lea     rdx, QuicConnLogVerbose
0x14003e5bf  call    McTemplateU0ps_EtwWriteTransfer
0x14003e5c4  nop
0x14003e5c5  jmp     loc_140022921
0x14003e5ca  test    cs:byte_14005C48B, 40h
0x14003e5d1  jz      short loc_14003E608
0x14003e5d3  lea     r9, aCanTRetireCurr; "Can't retire current CID because we don"...
0x14003e5da  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14003e5de  mov     edx, 80h; SizeInBytes
0x14003e5e3  lea     rcx, [rsp+0B8h+DstBuf]; DstBuf
0x14003e5e8  call    cs:__imp__snprintf_s
0x14003e5ef  nop     dword ptr [rax+rax+00h]
0x14003e5f4  lea     r9, [rsp+0B8h+DstBuf]
0x14003e5f9  mov     r8, rbx
0x14003e5fc  lea     rdx, QuicConnLogWarning
0x14003e603  call    McTemplateU0ps_EtwWriteTransfer
0x14003e608  xor     al, al
0x14003e60a  jmp     loc_140022923
```
