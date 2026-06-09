# MsQuicConnectionClose

- ea: `0x14001d490`
- end: `0x14001d6b0`
- name: `MsQuicConnectionClose`
- size: `544`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x14000c4b8`
- `0x14001c52c`
- `0x14001d490`
- `0x1400200d8`
- `0x1400337e4`
- `0x14003eb54`
- `0x140040c2c`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14001d5c7`
- `ntoskrnl!KeInitializeEvent` at `0x14001d5c7`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001d529`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001d529`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001d613`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001d613`

## pseudocode

```c
void __fastcall MsQuicConnectionClose(__int64 a1, __int64 a2)
{
  char v3; // di
  __int64 v4; // rcx
  char v5; // di
  struct _KEVENT Event; // [rsp+30h] [rbp-39h] BYREF
  __int128 v7; // [rsp+48h] [rbp-21h] BYREF
  __int128 v8; // [rsp+58h] [rbp-11h]
  __int128 v9; // [rsp+68h] [rbp-1h]
  int v10; // [rsp+78h] [rbp+Fh]
  __int128 v11; // [rsp+80h] [rbp+17h] BYREF
  __int64 v12; // [rsp+90h] [rbp+27h]
  __int128 *v13; // [rsp+98h] [rbp+2Fh]
  __int128 v14; // [rsp+A0h] [rbp+37h]
  __int64 v15; // [rsp+B0h] [rbp+47h]

  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0qp_EtwWriteTransfer(a1, a2, 13, a1);
  if ( a1 )
  {
    v3 = 1;
    if ( (unsigned int)(*(_DWORD *)a1 - 3) <= 1 )
    {
      if ( (*(_BYTE *)(a1 + 249) & 4) != 0 )
        CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 144, "!Connection->State.Freed");
      if ( (*(_BYTE *)(a1 + 252) & 0x40) != 0 && (*(_BYTE *)(a1 + 249) & 2) != 0 )
      {
        CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 145, "!Connection->State.HandleClosed");
        __int2c();
      }
      if ( *(HANDLE *)(a1 + 256) == PsGetCurrentThreadId() )
      {
        if ( (*(_BYTE *)(a1 + 249) & 2) != 0 )
          goto LABEL_29;
      }
      else
      {
        v3 = 0;
      }
      if ( (*(_BYTE *)(a1 + 249) & 2) != 0 )
        CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 158, "!Connection->State.HandleClosed");
      if ( (MsQuicLib & 4) != 0 || v3 )
      {
        v5 = *(_BYTE *)(a1 + 251) & 0x20;
        if ( !v5 )
          *(_BYTE *)(a1 + 251) |= 0x20u;
        QuicConnCloseHandle(a1);
        if ( !v5 )
          *(_BYTE *)(a1 + 251) &= ~0x20u;
      }
      else
      {
        v15 = 0;
        v10 = 0;
        v12 = 0;
        v13 = &v7;
        memset(&Event, 0, sizeof(Event));
        v11 = 0;
        v14 = 0;
        v7 = 0;
        v8 = 0;
        v9 = 0;
        KeInitializeEvent(&Event, NotificationEvent, 0);
        *((_QWORD *)&v7 + 1) = 0;
        *(_QWORD *)&v8 = &Event;
        QuicConnQueueOper(a1, &v11);
        if ( (Microsoft_QuicEnableBits & 8) != 0 )
          McTemplateU0_EtwWriteTransfer(v4, QuicApiWaitOperation);
        KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      }
      if ( (*(_BYTE *)(a1 + 249) & 2) == 0 )
        CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\api.c", 203, "Connection->State.HandleClosed");
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 240), 0xFFFFFFFF) == 1 )
        QuicConnFree(a1);
    }
  }
LABEL_29:
  if ( (Microsoft_QuicEnableBits & 8) != 0 )
    McTemplateU0_EtwWriteTransfer(a1, QuicApiExit);
}

```

## disassembly

```asm
0x14001d490  mov     [rsp-8+arg_0], rbx
0x14001d495  mov     [rsp-8+arg_8], rdi
0x14001d49a  push    rbp
0x14001d49b  lea     rbp, [rsp-57h]
0x14001d4a0  sub     rsp, 0C0h
0x14001d4a7  test    cs:Microsoft_QuicEnableBits, 8
0x14001d4ae  mov     rbx, rcx
0x14001d4b1  jz      short loc_14001D4C1
0x14001d4b3  mov     r9, rcx
0x14001d4b6  mov     r8d, 0Dh
0x14001d4bc  call    McTemplateU0qp_EtwWriteTransfer
0x14001d4c1  test    rbx, rbx
0x14001d4c4  jz      loc_14001D685
0x14001d4ca  mov     eax, [rbx]
0x14001d4cc  mov     edi, 1
0x14001d4d1  sub     eax, 3
0x14001d4d4  cmp     eax, edi
0x14001d4d6  ja      loc_14001D685
0x14001d4dc  test    byte ptr [rbx+0F9h], 4
0x14001d4e3  jz      short loc_14001D4FD
0x14001d4e5  lea     r8, aConnectionStat_2; "!Connection->State.Freed"
0x14001d4ec  mov     edx, 90h
0x14001d4f1  lea     rcx, aCW1SMsquicSrcC_5; "C:\\__w\\1\\s\\msquic\\src\\core\\api.c"
0x14001d4f8  call    CxPlatLogAssert
0x14001d4fd  test    byte ptr [rbx+0FCh], 40h
0x14001d504  jz      short loc_14001D529
0x14001d506  test    byte ptr [rbx+0F9h], 2
0x14001d50d  jz      short loc_14001D529
0x14001d50f  lea     r8, aConnectionStat_0; "!Connection->State.HandleClosed"
0x14001d516  mov     edx, 91h
0x14001d51b  lea     rcx, aCW1SMsquicSrcC_5; "C:\\__w\\1\\s\\msquic\\src\\core\\api.c"
0x14001d522  call    CxPlatLogAssert
0x14001d527  int     2Ch; Windows NT - assertion failure
0x14001d529  call    cs:__imp_PsGetCurrentThreadId
0x14001d530  nop     dword ptr [rax+rax+00h]
0x14001d535  cmp     [rbx+100h], rax
0x14001d53c  jnz     short loc_14001D54D
0x14001d53e  test    byte ptr [rbx+0F9h], 2
0x14001d545  jnz     loc_14001D685
0x14001d54b  jmp     short loc_14001D550
0x14001d54d  xor     dil, dil
0x14001d550  test    byte ptr [rbx+0F9h], 2
0x14001d557  jz      short loc_14001D571
0x14001d559  lea     r8, aConnectionStat_0; "!Connection->State.HandleClosed"
0x14001d560  mov     edx, 9Eh
0x14001d565  lea     rcx, aCW1SMsquicSrcC_5; "C:\\__w\\1\\s\\msquic\\src\\core\\api.c"
0x14001d56c  call    CxPlatLogAssert
0x14001d571  test    cs:MsQuicLib, 4
0x14001d578  jnz     loc_14001D621
0x14001d57e  test    dil, dil
0x14001d581  jnz     loc_14001D621
0x14001d587  xor     eax, eax
0x14001d589  lea     rcx, [rbp+57h+Event]; Event
0x14001d58d  xorps   xmm0, xmm0
0x14001d590  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x14001d594  xorps   xmm1, xmm1
0x14001d597  mov     [rbp+57h+var_10], rax
0x14001d59b  mov     [rbp+57h+var_48], eax
0x14001d59e  xor     r8d, r8d; State
0x14001d5a1  lea     rax, [rbp+57h+var_78]
0x14001d5a5  xor     edx, edx; Type
0x14001d5a7  movups  [rbp+57h+var_30], xmm1
0x14001d5ab  mov     qword ptr [rbp+57h+var_30+8], rax
0x14001d5af  movups  xmmword ptr [rbp+57h+Event.Header], xmm0
0x14001d5b3  movups  [rbp+57h+var_40], xmm1
0x14001d5b7  movups  [rbp+57h+var_20], xmm1
0x14001d5bb  movups  [rbp+57h+var_78], xmm0
0x14001d5bf  movups  [rbp+57h+var_68], xmm0
0x14001d5c3  movups  [rbp+57h+var_58], xmm0
0x14001d5c7  call    cs:__imp_KeInitializeEvent
0x14001d5ce  nop     dword ptr [rax+rax+00h]
0x14001d5d3  and     qword ptr [rbp+57h+var_78+8], 0
0x14001d5d8  lea     rax, [rbp+57h+Event]
0x14001d5dc  lea     rdx, [rbp+57h+var_40]
0x14001d5e0  mov     qword ptr [rbp+57h+var_68], rax
0x14001d5e4  mov     rcx, rbx
0x14001d5e7  call    QuicConnQueueOper
0x14001d5ec  test    cs:Microsoft_QuicEnableBits, 8
0x14001d5f3  jz      short loc_14001D601
0x14001d5f5  lea     rdx, QuicApiWaitOperation
0x14001d5fc  call    McTemplateU0_EtwWriteTransfer
0x14001d601  and     [rsp+0C0h+var_A0], 0
0x14001d607  lea     rcx, [rbp+57h+Event]; Object
0x14001d60b  xor     r9d, r9d; Alertable
0x14001d60e  xor     r8d, r8d; WaitMode
0x14001d611  xor     edx, edx; WaitReason
0x14001d613  call    cs:__imp_KeWaitForSingleObject
0x14001d61a  nop     dword ptr [rax+rax+00h]
0x14001d61f  jmp     short loc_14001D64C
0x14001d621  mov     al, [rbx+0FBh]
0x14001d627  mov     dil, al
0x14001d62a  and     dil, 20h
0x14001d62e  jnz     short loc_14001D638
0x14001d630  or      al, 20h
0x14001d632  mov     [rbx+0FBh], al
0x14001d638  mov     rcx, rbx
0x14001d63b  call    QuicConnCloseHandle
0x14001d640  test    dil, dil
0x14001d643  jnz     short loc_14001D64C
0x14001d645  and     byte ptr [rbx+0FBh], 0DFh
0x14001d64c  test    byte ptr [rbx+0F9h], 2
0x14001d653  jnz     short loc_14001D66D
0x14001d655  lea     r8, aConnectionStat_1; "Connection->State.HandleClosed"
0x14001d65c  mov     edx, 0CBh
0x14001d661  lea     rcx, aCW1SMsquicSrcC_5; "C:\\__w\\1\\s\\msquic\\src\\core\\api.c"
0x14001d668  call    CxPlatLogAssert
0x14001d66d  or      eax, 0FFFFFFFFh
0x14001d670  lock xadd [rbx+0F0h], eax
0x14001d678  cmp     eax, 1
0x14001d67b  jnz     short loc_14001D685
0x14001d67d  mov     rcx, rbx
0x14001d680  call    QuicConnFree
0x14001d685  test    cs:Microsoft_QuicEnableBits, 8
0x14001d68c  jz      short loc_14001D69A
0x14001d68e  lea     rdx, QuicApiExit
0x14001d695  call    McTemplateU0_EtwWriteTransfer
0x14001d69a  lea     r11, [rsp+0C0h+var_s0]
0x14001d6a2  mov     rbx, [r11+10h]
0x14001d6a6  mov     rdi, [r11+18h]
0x14001d6aa  mov     rsp, r11
0x14001d6ad  pop     rbp
0x14001d6ae  retn
```
