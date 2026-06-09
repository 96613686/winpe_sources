# QuicStreamIndicateShutdownComplete

- ea: `0x14000b098`
- end: `0x14000b1f1`
- name: `QuicStreamIndicateShutdownComplete`
- size: `345`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000b60c`
- `0x14000b710`

## callees

- `0x14000b098`
- `0x14000b27c`
- `0x14003c8e0`
- `0x14003ec10`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14000b19f`
- `ntoskrnl!_snprintf_s` at `0x14000b19f`

## string_xrefs

- `0x14000b184`: `Indicating QUIC_STREAM_EVENT_SHUTDOWN_COMPLETE [Shutdown=%hhu, ShutdownByApp=%hhu, ClosedRemotely=%hhu, ErrorCode=0x%llx, CloseStatus=0x%x]`

## pseudocode

```c
__int64 __fastcall QuicStreamIndicateShutdownComplete(__int64 a1)
{
  char v1; // dl
  char v3; // dl
  __int64 v4; // rcx
  char v5; // r9
  unsigned __int8 v6; // r8
  __int64 v7; // r10
  int v8; // r11d
  __int64 v9; // rcx
  __int64 result; // rax
  __int128 v11; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v12; // [rsp+60h] [rbp-A0h]
  int v13; // [rsp+70h] [rbp-90h]
  char DstBuf[128]; // [rsp+80h] [rbp-80h] BYREF

  v1 = *(_BYTE *)(a1 + 92);
  if ( (v1 & 4) == 0 )
  {
    v3 = v1 | 4;
    v13 = 0;
    *(_BYTE *)(a1 + 92) = v3;
    v4 = *(_QWORD *)(a1 + 72);
    v11 = 0;
    v12 = 0;
    LODWORD(v11) = 7;
    v5 = *(_BYTE *)(v4 + 248) & 0x30;
    BYTE8(v11) = v5 != 0;
    BYTE9(v11) = ((v3 & 8) != 0) ^ (((v3 & 8) != 0) ^ (*(_BYTE *)(v4 + 248) >> 6)) & 2;
    v6 = BYTE9(v11) ^ (BYTE9(v11) ^ (*(_BYTE *)(v4 + 248) >> 3)) & 4;
    BYTE9(v11) = v6;
    v7 = *(_QWORD *)(v4 + 1592);
    *(_QWORD *)&v12 = v7;
    v8 = *(_DWORD *)(v4 + 1588);
    DWORD2(v12) = v8;
    if ( (byte_14005C48D & 1) != 0 )
    {
      _snprintf_s(
        DstBuf,
        0x80u,
        0xFFFFFFFFFFFFFFFFuLL,
        "Indicating QUIC_STREAM_EVENT_SHUTDOWN_COMPLETE [Shutdown=%hhu, ShutdownByApp=%hhu, ClosedRemotely=%hhu, ErrorCod"
        "e=0x%llx, CloseStatus=0x%x]",
        v5 != 0,
        (v6 >> 1) & 1,
        (v6 >> 2) & 1,
        v7,
        v8);
      McTemplateU0ps_EtwWriteTransfer(v9, QuicStreamLogVerbose, a1, DstBuf);
    }
    result = QuicStreamIndicateEvent(a1, &v11);
    *(_QWORD *)(a1 + 712) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000b098  mov     [rsp-8+arg_8], rbx
0x14000b09d  push    rbp
0x14000b09e  lea     rbp, [rsp-10h]
0x14000b0a3  sub     rsp, 110h
0x14000b0aa  mov     rax, cs:__security_cookie
0x14000b0b1  xor     rax, rsp
0x14000b0b4  mov     [rbp+10h+var_10], rax
0x14000b0b8  mov     dl, [rcx+5Ch]
0x14000b0bb  mov     r10b, 4
0x14000b0be  mov     rbx, rcx
0x14000b0c1  test    r10b, dl
0x14000b0c4  jnz     loc_14000B1D3
0x14000b0ca  xor     eax, eax
0x14000b0cc  or      dl, r10b
0x14000b0cf  mov     [rsp+110h+var_A0], eax
0x14000b0d3  xorps   xmm0, xmm0
0x14000b0d6  mov     [rcx+5Ch], dl
0x14000b0d9  mov     rcx, [rcx+48h]
0x14000b0dd  movups  [rsp+110h+var_C0], xmm0
0x14000b0e2  mov     al, byte ptr [rsp+110h+var_C0+9]
0x14000b0e6  movups  [rsp+110h+var_B0], xmm0
0x14000b0eb  mov     dword ptr [rsp+110h+var_C0], 7
0x14000b0f3  mov     r9b, [rcx+0F8h]
0x14000b0fa  and     r9b, 30h
0x14000b0fe  setnz   byte ptr [rsp+110h+var_C0+8]
0x14000b103  and     al, 0FEh
0x14000b105  shr     dl, 3
0x14000b108  and     dl, 1
0x14000b10b  or      dl, al
0x14000b10d  mov     al, [rcx+0F8h]
0x14000b113  shr     al, 6
0x14000b116  xor     al, dl
0x14000b118  and     al, 2
0x14000b11a  xor     al, dl
0x14000b11c  mov     byte ptr [rsp+110h+var_C0+9], al
0x14000b120  mov     r8b, [rcx+0F8h]
0x14000b127  shr     r8b, 3
0x14000b12b  xor     r8b, al
0x14000b12e  and     r8b, r10b
0x14000b131  xor     r8b, al
0x14000b134  test    cs:byte_14005C48D, 1
0x14000b13b  mov     byte ptr [rsp+110h+var_C0+9], r8b
0x14000b140  mov     r10, [rcx+638h]
0x14000b147  mov     qword ptr [rsp+110h+var_B0], r10
0x14000b14c  mov     r11d, [rcx+634h]
0x14000b153  mov     dword ptr [rsp+110h+var_B0+8], r11d
0x14000b158  jz      short loc_14000B1BE
0x14000b15a  mov     [rsp+110h+var_D0], r11d
0x14000b15f  xor     eax, eax
0x14000b161  movzx   edx, r8b
0x14000b165  movzx   ecx, r8b
0x14000b169  shr     edx, 2
0x14000b16c  shr     ecx, 1
0x14000b16e  and     edx, 1
0x14000b171  and     ecx, 1
0x14000b174  mov     [rsp+110h+var_D8], r10
0x14000b179  mov     [rsp+110h+var_E0], edx
0x14000b17d  test    r9b, r9b
0x14000b180  mov     [rsp+110h+var_E8], ecx
0x14000b184  lea     r9, aIndicatingQuic_3; "Indicating QUIC_STREAM_EVENT_SHUTDOWN_C"...
0x14000b18b  setnz   al
0x14000b18e  lea     rcx, [rbp+10h+DstBuf]; DstBuf
0x14000b192  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14000b196  mov     [rsp+110h+var_F0], eax
0x14000b19a  mov     edx, 80h; SizeInBytes
0x14000b19f  call    cs:__imp__snprintf_s
0x14000b1a6  nop     dword ptr [rax+rax+00h]
0x14000b1ab  lea     r9, [rbp+10h+DstBuf]
0x14000b1af  mov     r8, rbx
0x14000b1b2  lea     rdx, QuicStreamLogVerbose
0x14000b1b9  call    McTemplateU0ps_EtwWriteTransfer
0x14000b1be  lea     rdx, [rsp+110h+var_C0]
0x14000b1c3  mov     rcx, rbx
0x14000b1c6  call    QuicStreamIndicateEvent
0x14000b1cb  and     qword ptr [rbx+2C8h], 0
0x14000b1d3  mov     rcx, [rbp+10h+var_10]
0x14000b1d7  xor     rcx, rsp; StackCookie
0x14000b1da  call    __security_check_cookie
0x14000b1df  mov     rbx, [rsp+110h+arg_8]
0x14000b1e7  add     rsp, 110h
0x14000b1ee  pop     rbp
0x14000b1ef  retn
```
