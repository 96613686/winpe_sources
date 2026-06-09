# QuicConnOnShutdownComplete

- ea: `0x14001d88c`
- end: `0x14001da46`
- name: `QuicConnOnShutdownComplete`
- size: `442`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140014d80`
- `0x14001c52c`
- `0x14002e518`

## callees

- `0x14001c440`
- `0x14001d6b8`
- `0x14001d88c`
- `0x14001dcd0`
- `0x1400200d8`
- `0x1400205b4`
- `0x140020620`
- `0x140022644`
- `0x14002b964`
- `0x14002fdc4`
- `0x14003c8e0`
- `0x14003ec10`
- `0x1400426e8`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14001d9d5`
- `ntoskrnl!_snprintf_s` at `0x14001d9d5`

## string_xrefs

- `0x14001d9c0`: `Indicating QUIC_CONNECTION_EVENT_SHUTDOWN_COMPLETE`

## pseudocode

```c
char __fastcall QuicConnOnShutdownComplete(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  signed __int32 v5; // eax
  char v6; // dl
  char v7; // cl
  char v8; // cl
  __int64 v9; // rcx
  __int128 v11; // [rsp+20h] [rbp-D8h] BYREF
  __int128 v12; // [rsp+30h] [rbp-C8h]
  __int128 v13; // [rsp+40h] [rbp-B8h]
  __int64 v14; // [rsp+50h] [rbp-A8h]
  char DstBuf[128]; // [rsp+60h] [rbp-98h] BYREF

  *(_BYTE *)(a1 + 251) &= ~1u;
  LOBYTE(v5) = *(_BYTE *)(a1 + 249);
  if ( (v5 & 1) == 0 )
  {
    LOBYTE(a4) = *(_BYTE *)(a1 + 250) & 0xBF;
    *(_BYTE *)(a1 + 249) = v5 | 1;
    *(_BYTE *)(a1 + 250) = a4;
    if ( (byte_14005C489 & 0x40) != 0 )
    {
      LOBYTE(a4) = (unsigned __int8)a4 >> 7;
      McTemplateU0pu_EtwWriteTransfer(a1, QuicConnShutdownComplete, a1, a4);
    }
    if ( *(_QWORD *)(a1 + 360) )
    {
      if ( (*(_BYTE *)(a1 + 322) & 0x20) != 0 )
        QuicPathUpdateQeo(a1, (unsigned __int8 *)(a1 + 320), 1);
      QuicBindingRemoveConnection(*(_QWORD *)(a1 + 360), a1);
    }
    QuicTimerWheelRemoveConnection(*(_QWORD *)(a1 + 64) + 88LL, a1);
    QuicLossDetectionUninitialize(a1 + 2632);
    QuicSendUninitialize(a1 + 3416);
    QuicDatagramSendShutdown(a1 + 3552);
    v6 = *(_BYTE *)(a1 + 249);
    if ( (v6 & 0x20) != 0 )
    {
      v7 = *(_BYTE *)(a1 + 250) >> 6;
      LODWORD(v14) = 0;
      v8 = ((*(_BYTE *)(a1 + 248) & 8) != 0) | ~v7 & 2;
      v11 = 0;
      LODWORD(v11) = 3;
      v12 = 0;
      BYTE8(v11) = (2 * (v6 & 2)) | v8;
      v13 = 0;
      if ( (byte_14005C48C & 1) != 0 )
      {
        _snprintf_s(
          DstBuf,
          0x80u,
          0xFFFFFFFFFFFFFFFFuLL,
          "Indicating QUIC_CONNECTION_EVENT_SHUTDOWN_COMPLETE",
          v11,
          v12,
          v13,
          v14);
        McTemplateU0ps_EtwWriteTransfer(v9, QuicConnLogVerbose, a1, DstBuf);
      }
      LOBYTE(v5) = QuicConnIndicateEvent(a1, &v11);
      *(_QWORD *)(a1 + 3608) = 0;
    }
    else
    {
      QuicConnUnregister(a1);
      v5 = _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 240), 0xFFFFFFFF);
      if ( v5 == 1 )
        LOBYTE(v5) = QuicConnFree(a1);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x14001d88c  push    rbx
0x14001d88e  sub     rsp, 0F0h
0x14001d895  mov     rax, cs:__security_cookie
0x14001d89c  xor     rax, rsp
0x14001d89f  mov     [rsp+0F8h+var_18], rax
0x14001d8a7  and     byte ptr [rcx+0FBh], 0FEh
0x14001d8ae  mov     rbx, rcx
0x14001d8b1  mov     al, [rcx+0F9h]
0x14001d8b7  test    al, 1
0x14001d8b9  jnz     loc_14001DA2C
0x14001d8bf  mov     r9b, [rcx+0FAh]
0x14001d8c6  or      al, 1
0x14001d8c8  and     r9b, 0BFh
0x14001d8cc  mov     [rcx+0F9h], al
0x14001d8d2  mov     [rcx+0FAh], r9b
0x14001d8d9  test    cs:byte_14005C489, 40h
0x14001d8e0  jz      short loc_14001D8F5
0x14001d8e2  shr     r9b, 7
0x14001d8e6  lea     rdx, QuicConnShutdownComplete
0x14001d8ed  mov     r8, rcx
0x14001d8f0  call    McTemplateU0pu_EtwWriteTransfer
0x14001d8f5  lea     rdx, [rbx+140h]
0x14001d8fc  cmp     qword ptr [rdx+28h], 0
0x14001d901  jz      short loc_14001D926
0x14001d903  test    byte ptr [rdx+2], 20h
0x14001d907  jz      short loc_14001D917
0x14001d909  mov     r8d, 1
0x14001d90f  mov     rcx, rbx
0x14001d912  call    QuicPathUpdateQeo
0x14001d917  mov     rcx, [rbx+168h]
0x14001d91e  mov     rdx, rbx
0x14001d921  call    QuicBindingRemoveConnection
0x14001d926  mov     rcx, [rbx+40h]
0x14001d92a  mov     rdx, rbx
0x14001d92d  add     rcx, 58h ; 'X'
0x14001d931  call    QuicTimerWheelRemoveConnection
0x14001d936  lea     rcx, [rbx+0A48h]
0x14001d93d  call    QuicLossDetectionUninitialize
0x14001d942  lea     rcx, [rbx+0D58h]
0x14001d949  call    QuicSendUninitialize
0x14001d94e  lea     rcx, [rbx+0DE0h]
0x14001d955  call    QuicDatagramSendShutdown
0x14001d95a  mov     dl, [rbx+0F9h]
0x14001d960  test    dl, 20h
0x14001d963  jz      loc_14001DA0C
0x14001d969  mov     cl, [rbx+0FAh]
0x14001d96f  xor     eax, eax
0x14001d971  shr     cl, 6
0x14001d974  xorps   xmm0, xmm0
0x14001d977  mov     dword ptr [rsp+0F8h+var_A8], eax
0x14001d97b  not     cl
0x14001d97d  mov     al, [rbx+0F8h]
0x14001d983  and     cl, 2
0x14001d986  shr     al, 3
0x14001d989  and     dl, 2
0x14001d98c  and     al, 1
0x14001d98e  add     dl, dl
0x14001d990  or      cl, al
0x14001d992  movups  [rsp+0F8h+var_D8], xmm0
0x14001d997  mov     al, byte ptr [rsp+0F8h+var_D8+8]
0x14001d99b  or      cl, dl
0x14001d99d  and     al, 0F8h
0x14001d99f  mov     dword ptr [rsp+0F8h+var_D8], 3
0x14001d9a7  or      cl, al
0x14001d9a9  test    cs:byte_14005C48C, 1
0x14001d9b0  movups  [rsp+0F8h+var_C8], xmm0
0x14001d9b5  mov     byte ptr [rsp+0F8h+var_D8+8], cl
0x14001d9b9  movups  [rsp+0F8h+var_B8], xmm0
0x14001d9be  jz      short loc_14001D9F5
0x14001d9c0  lea     r9, aIndicatingQuic_4; "Indicating QUIC_CONNECTION_EVENT_SHUTDO"...
0x14001d9c7  or      r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14001d9cb  mov     edx, 80h; SizeInBytes
0x14001d9d0  lea     rcx, [rsp+0F8h+DstBuf]; DstBuf
0x14001d9d5  call    cs:__imp__snprintf_s
0x14001d9dc  nop     dword ptr [rax+rax+00h]
0x14001d9e1  lea     r9, [rsp+0F8h+DstBuf]
0x14001d9e6  mov     r8, rbx
0x14001d9e9  lea     rdx, QuicConnLogVerbose
0x14001d9f0  call    McTemplateU0ps_EtwWriteTransfer
0x14001d9f5  lea     rdx, [rsp+0F8h+var_D8]
0x14001d9fa  mov     rcx, rbx
0x14001d9fd  call    QuicConnIndicateEvent
0x14001da02  and     qword ptr [rbx+0E18h], 0
0x14001da0a  jmp     short loc_14001DA2C
0x14001da0c  mov     rcx, rbx
0x14001da0f  call    QuicConnUnregister
0x14001da14  or      eax, 0FFFFFFFFh
0x14001da17  lock xadd [rbx+0F0h], eax
0x14001da1f  cmp     eax, 1
0x14001da22  jnz     short loc_14001DA2C
0x14001da24  mov     rcx, rbx
0x14001da27  call    QuicConnFree
0x14001da2c  mov     rcx, [rsp+0F8h+var_18]
0x14001da34  xor     rcx, rsp; StackCookie
0x14001da37  call    __security_check_cookie
0x14001da3c  add     rsp, 0F0h
0x14001da43  pop     rbx
0x14001da44  retn
```
