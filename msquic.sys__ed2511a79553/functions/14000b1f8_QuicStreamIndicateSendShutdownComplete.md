# QuicStreamIndicateSendShutdownComplete

- ea: `0x14000b1f8`
- end: `0x14000b275`
- name: `QuicStreamIndicateSendShutdownComplete`
- size: `125`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000b3f4`
- `0x14000b60c`
- `0x140014630`
- `0x14002e9ac`
- `0x1400456a4`

## callees

- `0x14000b1f8`
- `0x14000b27c`
- `0x14003c8e0`
- `0x14003ec10`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14003d875`
- `ntoskrnl!_snprintf_s` at `0x14003d875`

## string_xrefs

- `0x14003d860`: `Indicating QUIC_STREAM_EVENT_SEND_SHUTDOWN_COMPLETE`

## pseudocode

```c
char __fastcall QuicStreamIndicateSendShutdownComplete(__int64 a1, char a2)
{
  char result; // al
  __int64 v4; // rcx
  __int128 v5; // [rsp+20h] [rbp-C8h] BYREF
  __int128 v6; // [rsp+30h] [rbp-B8h]
  __int64 v7; // [rsp+40h] [rbp-A8h]
  char DstBuf[128]; // [rsp+50h] [rbp-98h] BYREF

  result = *(_BYTE *)(a1 + 92);
  if ( (result & 2) == 0 )
  {
    *(_BYTE *)(a1 + 92) = result | 2;
    v5 = 0;
    LODWORD(v7) = 0;
    v6 = 0;
    LODWORD(v5) = 6;
    BYTE8(v5) = a2;
    if ( (byte_14005C48D & 1) != 0 )
    {
      _snprintf_s(
        DstBuf,
        0x80u,
        0xFFFFFFFFFFFFFFFFuLL,
        "Indicating QUIC_STREAM_EVENT_SEND_SHUTDOWN_COMPLETE",
        v5,
        v6,
        v7);
      McTemplateU0ps_EtwWriteTransfer(v4, QuicStreamLogVerbose, a1, DstBuf);
    }
    return QuicStreamIndicateEvent(a1, &v5);
  }
  return result;
}

```

## disassembly

```asm
0x14000b1f8  push    rbx
0x14000b1fa  sub     rsp, 0E0h
0x14000b201  mov     rax, cs:__security_cookie
0x14000b208  xor     rax, rsp
0x14000b20b  mov     [rsp+0E8h+var_18], rax
0x14000b213  mov     al, [rcx+5Ch]
0x14000b216  mov     rbx, rcx
0x14000b219  test    al, 2
0x14000b21b  jnz     short loc_14000B25B
0x14000b21d  or      al, 2
0x14000b21f  xorps   xmm0, xmm0
0x14000b222  mov     [rcx+5Ch], al
0x14000b225  xor     eax, eax
0x14000b227  test    cs:byte_14005C48D, 1
0x14000b22e  movups  [rsp+0E8h+var_C8], xmm0
0x14000b233  mov     dword ptr [rsp+0E8h+var_A8], eax
0x14000b237  movups  [rsp+0E8h+var_B8], xmm0
0x14000b23c  mov     dword ptr [rsp+0E8h+var_C8], 6
0x14000b244  mov     byte ptr [rsp+0E8h+var_C8+8], dl
0x14000b248  jnz     loc_14003D860
0x14000b24e  lea     rdx, [rsp+0E8h+var_C8]
0x14000b253  mov     rcx, rbx
0x14000b256  call    QuicStreamIndicateEvent
0x14000b25b  mov     rcx, [rsp+0E8h+var_18]
0x14000b263  xor     rcx, rsp; StackCookie
0x14000b266  call    __security_check_cookie
0x14000b26b  add     rsp, 0E0h
0x14000b272  pop     rbx
0x14000b273  retn
0x14003d860  lea     r9, aIndicatingQuic_6; "Indicating QUIC_STREAM_EVENT_SEND_SHUTD"...
0x14003d867  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14003d86b  mov     edx, 80h; SizeInBytes
0x14003d870  lea     rcx, [rsp+0E8h+DstBuf]; DstBuf
0x14003d875  call    cs:__imp__snprintf_s
0x14003d87c  nop     dword ptr [rax+rax+00h]
0x14003d881  lea     r9, [rsp+0E8h+DstBuf]
0x14003d886  mov     r8, rbx
0x14003d889  lea     rdx, QuicStreamLogVerbose
0x14003d890  call    McTemplateU0ps_EtwWriteTransfer
0x14003d895  nop
0x14003d896  jmp     loc_14000B24E
```
