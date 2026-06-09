# QuicStreamTryCompleteShutdown

- ea: `0x14000b710`
- end: `0x14000b772`
- name: `QuicStreamTryCompleteShutdown`
- size: `98`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000b3f4`
- `0x140014630`
- `0x140026530`
- `0x14002e9ac`
- `0x1400456a4`
- `0x140049624`

## callees

- `0x14000b098`
- `0x14000b32c`
- `0x14000b710`
- `0x14000b780`

## pseudocode

```c
__int64 __fastcall QuicStreamTryCompleteShutdown(__int64 a1)
{
  __int64 v1; // rbx
  __int64 result; // rax

  v1 = a1;
  if ( (*(_BYTE *)(a1 + 92) & 0x10) == 0 )
  {
    LOBYTE(a1) = *(_BYTE *)(a1 + 91);
    if ( (a1 & 0x40) == 0 && (*(_BYTE *)(v1 + 90) & 2) != 0 && (a1 & 1) != 0 )
    {
      QuicSendClearStreamSendFlag(a1, v1, 0xFFFF);
      *(_BYTE *)(v1 + 92) |= 0x10u;
      result = QuicStreamIndicateShutdownComplete(v1);
      if ( (*(_BYTE *)(v1 + 93) & 2) == 0 || (*(_BYTE *)(v1 + 92) & 8) != 0 )
        return QuicStreamSetReleaseStream(*(_QWORD *)(v1 + 72) + 2032LL, v1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000b710  push    rbx
0x14000b712  sub     rsp, 20h
0x14000b716  test    byte ptr [rcx+5Ch], 10h
0x14000b71a  mov     rbx, rcx
0x14000b71d  jnz     short loc_14000B76B
0x14000b71f  mov     cl, [rcx+5Bh]
0x14000b722  test    cl, 40h
0x14000b725  jnz     short loc_14000B76B
0x14000b727  test    byte ptr [rbx+5Ah], 2
0x14000b72b  jz      short loc_14000B76B
0x14000b72d  test    cl, 1
0x14000b730  jz      short loc_14000B76B
0x14000b732  mov     r8d, 0FFFFh
0x14000b738  mov     rdx, rbx
0x14000b73b  call    QuicSendClearStreamSendFlag
0x14000b740  or      byte ptr [rbx+5Ch], 10h
0x14000b744  mov     rcx, rbx
0x14000b747  call    QuicStreamIndicateShutdownComplete
0x14000b74c  test    byte ptr [rbx+5Dh], 2
0x14000b750  jz      short loc_14000B758
0x14000b752  test    byte ptr [rbx+5Ch], 8
0x14000b756  jz      short loc_14000B76B
0x14000b758  mov     rcx, [rbx+48h]
0x14000b75c  mov     rdx, rbx
0x14000b75f  add     rcx, 7F0h
0x14000b766  call    QuicStreamSetReleaseStream
0x14000b76b  add     rsp, 20h
0x14000b76f  pop     rbx
0x14000b770  retn
```
