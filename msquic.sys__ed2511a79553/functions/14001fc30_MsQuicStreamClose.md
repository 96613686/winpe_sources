# MsQuicStreamClose

- ea: `0x14001fc30`
- end: `0x14001ffba`
- name: `MsQuicStreamClose`
- size: `906`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x14000b60c`
- `0x14000b780`
- `0x14000c440`
- `0x14000c4b8`
- `0x14001fc30`
- `0x1400262b4`
- `0x140029720`
- `0x1400337e4`
- `0x14003c8e0`
- `0x14003eb54`
- `0x14003ec10`
- `0x140040c2c`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14001fec9`
- `ntoskrnl!_snprintf_s` at `0x14001fec9`
- `ntoskrnl!KeInitializeEvent` at `0x14001fdff`
- `ntoskrnl!KeInitializeEvent` at `0x14001fdff`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001fd04`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001fd04`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001fe58`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001fe58`

## pseudocode

```c
void __fastcall MsQuicStreamClose(__int64 a1, __int64 a2)
{
  __int64 v3; // rdi
  char v4; // si
  __int64 v5; // rax
  __int64 v6; // rcx
  char v7; // al
  char v8; // bp
  char v9; // cl
  __int64 v10; // rcx
  struct _KEVENT Event; // [rsp+30h] [rbp-128h] BYREF
  _DWORD v12[9]; // [rsp+48h] [rbp-110h] BYREF
  __int128 v13; // [rsp+6Ch] [rbp-ECh]
  __int128 v14; // [rsp+80h] [rbp-D8h] BYREF
  __int64 v15; // [rsp+90h] [rbp-C8h]
  _DWORD *v16; // [rsp+98h] [rbp-C0h]
  __int128 v17; // [rsp+A0h] [rbp-B8h]
  __int64 v18; // [rsp+B0h] [rbp-A8h]
  char DstBuf[128]; // [rsp+C0h] [rbp-98h] BYREF

  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0qp_EtwWriteTransfer(a1, a2, 19, a1);
  if ( a1 && *(_DWORD *)a1 == 5 )
  {
    if ( (*(_BYTE *)(a1 + 92) & 0x40) != 0 )
      CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 734, "!Stream->Flags.Freed");
    v3 = *(_QWORD *)(a1 + 72);
    if ( (*(_BYTE *)(v3 + 252) & 0x40) != 0 )
    {
      if ( (*(_BYTE *)(v3 + 249) & 4) != 0 )
      {
        CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 736, "!Connection->State.Freed");
        __int2c();
      }
      if ( (*(_BYTE *)(v3 + 252) & 0x40) != 0 && (*(_BYTE *)(a1 + 92) & 8) != 0 )
      {
        CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 737, "!Stream->Flags.HandleClosed");
        __int2c();
      }
    }
    if ( *(HANDLE *)(v3 + 256) == PsGetCurrentThreadId() )
    {
      v4 = 1;
      if ( (*(_BYTE *)(a1 + 92) & 8) != 0 )
        goto LABEL_45;
    }
    else
    {
      v4 = 0;
    }
    if ( (*(_BYTE *)(a1 + 92) & 8) != 0 )
      CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 750, "!Stream->Flags.HandleClosed");
    if ( (MsQuicLib & 4) != 0 || v4 )
    {
      v7 = *(_BYTE *)(v3 + 251);
      v8 = v7 & 0x20;
      if ( (v7 & 0x20) == 0 )
        *(_BYTE *)(v3 + 251) = v7 | 0x20;
      v9 = *(_BYTE *)(a1 + 92);
      *(_BYTE *)(a1 + 92) = v9 | 8;
      if ( (v9 & 0x10) == 0 )
      {
        if ( (*(_BYTE *)(a1 + 88) & 4) != 0 && (v9 & 4) == 0 && (byte_14005C48C & 0x40) != 0 )
        {
          _snprintf_s(DstBuf, 0x80u, 0xFFFFFFFFFFFFFFFFuLL, "Closing handle without fully shutting down");
          McTemplateU0ps_EtwWriteTransfer(v10, QuicStreamLogWarning, a1, DstBuf);
        }
        QuicStreamShutdown(a1, 14);
        if ( (*(_BYTE *)(a1 + 88) & 4) == 0 )
          *(_BYTE *)(a1 + 92) |= 0x10u;
      }
      if ( (*(_BYTE *)(a1 + 93) & 2) != 0 && (*(_BYTE *)(a1 + 92) & 0x10) != 0 )
        QuicStreamSetReleaseStream(*(_QWORD *)(a1 + 72) + 2032LL, a1);
      *(_QWORD *)(a1 + 712) = 0;
      if ( *(__int64 *)(a1 + 16) <= 0 )
        CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\stream.h", 732, "Stream->RefCount > 0");
      if ( (unsigned __int8)CxPlatRefDecrement(a1 + 16) )
        QuicStreamFree(a1);
      if ( !v8 )
        *(_BYTE *)(v3 + 251) &= ~0x20u;
    }
    else if ( *(_QWORD *)(a1 + 712) || (v5 = QuicOperationAlloc(*(_QWORD *)(v3 + 72), 0)) == 0 )
    {
      v12[0] = 5;
      v18 = 0;
      v15 = 0;
      v16 = v12;
      memset(&Event, 0, sizeof(Event));
      v14 = 0;
      v17 = 0;
      memset(&v12[1], 0, 32);
      v13 = 0;
      KeInitializeEvent(&Event, NotificationEvent, 0);
      *(_QWORD *)&v12[6] = a1;
      *(_QWORD *)&v12[4] = &Event;
      *(_QWORD *)&v12[2] = 0;
      QuicConnQueueOper(v3, &v14);
      if ( (Microsoft_QuicEnableBits & 8) != 0 )
        McTemplateU0_EtwWriteTransfer(v6, QuicApiWaitOperation);
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    }
    else
    {
      **(_DWORD **)(v5 + 24) = 5;
      *(_QWORD *)(*(_QWORD *)(v5 + 24) + 24LL) = a1;
      QuicConnQueueOper(v3, v5);
    }
  }
LABEL_45:
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0_EtwWriteTransfer(a1, QuicApiExit);
}

```

## disassembly

```asm
0x14001fc30  sub     rsp, 158h
0x14001fc37  mov     rax, cs:__security_cookie
0x14001fc3e  xor     rax, rsp
0x14001fc41  mov     [rsp+158h+var_18], rax
0x14001fc49  test    cs:Microsoft_QuicEnableBits, 8
0x14001fc50  mov     [rsp+158h+arg_8], rbx
0x14001fc58  mov     rbx, rcx
0x14001fc5b  jz      short loc_14001FC6B
0x14001fc5d  mov     r9, rcx
0x14001fc60  mov     r8d, 13h
0x14001fc66  call    McTemplateU0qp_EtwWriteTransfer
0x14001fc6b  test    rbx, rbx
0x14001fc6e  jz      loc_14001FF84
0x14001fc74  cmp     dword ptr [rbx], 5
0x14001fc77  jnz     loc_14001FF84
0x14001fc7d  test    byte ptr [rbx+5Ch], 40h
0x14001fc81  mov     [rsp+158h+var_8], rdi
0x14001fc89  jz      short loc_14001FCA3
0x14001fc8b  lea     r8, aStreamFlagsFre; "!Stream->Flags.Freed"
0x14001fc92  mov     edx, 2DEh
0x14001fc97  lea     rcx, aCW1SMsquicSrcC_5; "C:\\__w\\1\\s\\msquic\\src\\core\\api.c"
0x14001fc9e  call    CxPlatLogAssert
0x14001fca3  mov     rdi, [rbx+48h]
0x14001fca7  test    byte ptr [rdi+0FCh], 40h
0x14001fcae  jz      short loc_14001FCFC
0x14001fcb0  test    byte ptr [rdi+0F9h], 4
0x14001fcb7  jz      short loc_14001FCD3
0x14001fcb9  lea     r8, aConnectionStat_2; "!Connection->State.Freed"
0x14001fcc0  mov     edx, 2E0h
0x14001fcc5  lea     rcx, aCW1SMsquicSrcC_5; "C:\\__w\\1\\s\\msquic\\src\\core\\api.c"
0x14001fccc  call    CxPlatLogAssert
0x14001fcd1  int     2Ch; Windows NT - assertion failure
0x14001fcd3  test    byte ptr [rdi+0FCh], 40h
0x14001fcda  jz      short loc_14001FCFC
0x14001fcdc  test    byte ptr [rbx+5Ch], 8
0x14001fce0  jz      short loc_14001FCFC
0x14001fce2  lea     r8, aStreamFlagsHan; "!Stream->Flags.HandleClosed"
0x14001fce9  mov     edx, 2E1h
0x14001fcee  lea     rcx, aCW1SMsquicSrcC_5; "C:\\__w\\1\\s\\msquic\\src\\core\\api.c"
0x14001fcf5  call    CxPlatLogAssert
0x14001fcfa  int     2Ch; Windows NT - assertion failure
0x14001fcfc  mov     [rsp+158h+arg_18], rsi
0x14001fd04  call    cs:__imp_PsGetCurrentThreadId
0x14001fd0b  nop     dword ptr [rax+rax+00h]
0x14001fd10  cmp     [rdi+100h], rax
0x14001fd17  jnz     short loc_14001FD28
0x14001fd19  test    byte ptr [rbx+5Ch], 8
0x14001fd1d  mov     sil, 1
0x14001fd20  jnz     loc_14001FF74
0x14001fd26  jmp     short loc_14001FD2B
0x14001fd28  xor     sil, sil
0x14001fd2b  test    byte ptr [rbx+5Ch], 8
0x14001fd2f  jz      short loc_14001FD49
0x14001fd31  lea     r8, aStreamFlagsHan; "!Stream->Flags.HandleClosed"
0x14001fd38  mov     edx, 2EEh
0x14001fd3d  lea     rcx, aCW1SMsquicSrcC_5; "C:\\__w\\1\\s\\msquic\\src\\core\\api.c"
0x14001fd44  call    CxPlatLogAssert
0x14001fd49  test    cs:MsQuicLib, 4
0x14001fd50  jnz     loc_14001FE69
0x14001fd56  test    sil, sil
0x14001fd59  jnz     loc_14001FE69
0x14001fd5f  cmp     qword ptr [rbx+2C8h], 0
0x14001fd67  jnz     short loc_14001FD9B
0x14001fd69  mov     rcx, [rdi+48h]
0x14001fd6d  xor     edx, edx
0x14001fd6f  call    QuicOperationAlloc
0x14001fd74  test    rax, rax
0x14001fd77  jz      short loc_14001FD9B
0x14001fd79  mov     rcx, [rax+18h]
0x14001fd7d  mov     rdx, rax
0x14001fd80  mov     dword ptr [rcx], 5
0x14001fd86  mov     rcx, [rax+18h]
0x14001fd8a  mov     [rcx+18h], rbx
0x14001fd8e  mov     rcx, rdi
0x14001fd91  call    QuicConnQueueOper
0x14001fd96  jmp     loc_14001FF74
0x14001fd9b  xorps   xmm1, xmm1
0x14001fd9e  mov     qword ptr [rsp+158h+var_110], 5
0x14001fda7  xor     eax, eax
0x14001fda9  lea     rcx, [rsp+158h+Event]; Event
0x14001fdae  xorps   xmm0, xmm0
0x14001fdb1  mov     [rsp+158h+Event.Header.WaitListHead.Blink], rax
0x14001fdb6  mov     [rsp+158h+var_A8], rax
0x14001fdbe  xor     r8d, r8d; State
0x14001fdc1  lea     rax, [rsp+158h+var_110]
0x14001fdc6  xor     edx, edx; Type
0x14001fdc8  movups  [rsp+158h+var_C8], xmm1
0x14001fdd0  mov     qword ptr [rsp+158h+var_C8+8], rax
0x14001fdd8  movups  xmmword ptr [rsp+158h+Event.Header], xmm0
0x14001fddd  movups  [rsp+158h+var_D8], xmm1
0x14001fde5  movups  [rsp+158h+var_B8], xmm1
0x14001fded  movdqu  [rsp+158h+var_110+4], xmm0
0x14001fdf3  movdqu  [rsp+158h+var_FC], xmm1
0x14001fdf9  movdqu  [rsp+158h+var_EC], xmm0
0x14001fdff  call    cs:__imp_KeInitializeEvent
0x14001fe06  nop     dword ptr [rax+rax+00h]
0x14001fe0b  lea     rax, [rsp+158h+Event]
0x14001fe10  mov     qword ptr [rsp+158h+var_FC+4], rbx
0x14001fe15  xor     esi, esi
0x14001fe17  mov     [rsp+58h], rax
0x14001fe1c  lea     rdx, [rsp+158h+var_D8]
0x14001fe24  mov     qword ptr [rsp+158h+var_110+8], rsi
0x14001fe29  mov     rcx, rdi
0x14001fe2c  call    QuicConnQueueOper
0x14001fe31  test    cs:Microsoft_QuicEnableBits, 8
0x14001fe38  jz      short loc_14001FE46
0x14001fe3a  lea     rdx, QuicApiWaitOperation
0x14001fe41  call    McTemplateU0_EtwWriteTransfer
0x14001fe46  xor     r9d, r9d; Alertable
0x14001fe49  mov     [rsp+158h+Timeout], rsi; Timeout
0x14001fe4e  xor     r8d, r8d; WaitMode
0x14001fe51  lea     rcx, [rsp+158h+Event]; Object
0x14001fe56  xor     edx, edx; WaitReason
0x14001fe58  call    cs:__imp_KeWaitForSingleObject
0x14001fe5f  nop     dword ptr [rax+rax+00h]
0x14001fe64  jmp     loc_14001FF74
0x14001fe69  movzx   eax, byte ptr [rdi+0FBh]
0x14001fe70  mov     [rsp+158h+arg_10], rbp
0x14001fe78  movzx   ebp, al
0x14001fe7b  and     bpl, 20h
0x14001fe7f  jnz     short loc_14001FE89
0x14001fe81  or      al, 20h
0x14001fe83  mov     [rdi+0FBh], al
0x14001fe89  movzx   ecx, byte ptr [rbx+5Ch]
0x14001fe8d  movzx   eax, cl
0x14001fe90  or      al, 8
0x14001fe92  mov     [rbx+5Ch], al
0x14001fe95  test    cl, 10h
0x14001fe98  jnz     short loc_14001FF05
0x14001fe9a  test    byte ptr [rbx+58h], 4
0x14001fe9e  jz      short loc_14001FEEC
0x14001fea0  test    cl, 4
0x14001fea3  jnz     short loc_14001FEEC
0x14001fea5  test    cs:byte_14005C48C, 40h
0x14001feac  jz      short loc_14001FEEC
0x14001feae  lea     r9, aClosingHandleW; "Closing handle without fully shutting d"...
0x14001feb5  mov     edx, 80h; SizeInBytes
0x14001feba  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14001fec1  lea     rcx, [rsp+158h+DstBuf]; DstBuf
0x14001fec9  call    cs:__imp__snprintf_s
0x14001fed0  nop     dword ptr [rax+rax+00h]
0x14001fed5  lea     r9, [rsp+158h+DstBuf]
0x14001fedd  mov     r8, rbx
0x14001fee0  lea     rdx, QuicStreamLogWarning
0x14001fee7  call    McTemplateU0ps_EtwWriteTransfer
0x14001feec  xor     r8d, r8d
0x14001feef  mov     rcx, rbx
0x14001fef2  lea     edx, [r8+0Eh]
0x14001fef6  call    QuicStreamShutdown
0x14001fefb  test    byte ptr [rbx+58h], 4
0x14001feff  jnz     short loc_14001FF05
0x14001ff01  or      byte ptr [rbx+5Ch], 10h
0x14001ff05  test    byte ptr [rbx+5Dh], 2
0x14001ff09  jz      short loc_14001FF24
0x14001ff0b  test    byte ptr [rbx+5Ch], 10h
0x14001ff0f  jz      short loc_14001FF24
0x14001ff11  mov     rcx, [rbx+48h]
0x14001ff15  mov     rdx, rbx
0x14001ff18  add     rcx, 7F0h
0x14001ff1f  call    QuicStreamSetReleaseStream
0x14001ff24  xor     esi, esi
0x14001ff26  mov     [rbx+2C8h], rsi
0x14001ff2d  cmp     [rbx+10h], rsi
0x14001ff31  jg      short loc_14001FF4B
0x14001ff33  lea     r8, aStreamRefcount; "Stream->RefCount > 0"
0x14001ff3a  mov     edx, 2DCh
0x14001ff3f  lea     rcx, aCW1SMsquicSrcC_11; "C:\\__w\\1\\s\\msquic\\src\\core\\strea"...
0x14001ff46  call    CxPlatLogAssert
0x14001ff4b  lea     rcx, [rbx+10h]
0x14001ff4f  call    CxPlatRefDecrement
0x14001ff54  test    al, al
0x14001ff56  jz      short loc_14001FF60
0x14001ff58  mov     rcx, rbx
0x14001ff5b  call    QuicStreamFree
0x14001ff60  test    bpl, bpl
0x14001ff63  mov     rbp, [rsp+158h+arg_10]
0x14001ff6b  jnz     short loc_14001FF74
0x14001ff6d  and     byte ptr [rdi+0FBh], 0DFh
0x14001ff74  mov     rsi, [rsp+158h+arg_18]
0x14001ff7c  mov     rdi, [rsp+158h+var_8]
0x14001ff84  test    cs:Microsoft_QuicEnableBits, 8
0x14001ff8b  mov     rbx, [rsp+158h+arg_8]
0x14001ff93  jz      short loc_14001FFA1
0x14001ff95  lea     rdx, QuicApiExit
0x14001ff9c  call    McTemplateU0_EtwWriteTransfer
0x14001ffa1  mov     rcx, [rsp+158h+var_18]
0x14001ffa9  xor     rcx, rsp; StackCookie
0x14001ffac  call    __security_check_cookie
0x14001ffb1  add     rsp, 158h
0x14001ffb8  retn
```
