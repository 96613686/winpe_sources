# TdiDisconnectRequest

- ea: `0x140008ac0`
- end: `0x140008cd5`
- name: `TdiDisconnectRequest`
- size: `533`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400085a0`
- `0x14000877c`

## callees

- `0x140005c38`
- `0x140007488`
- `0x140008ac0`
- `0x1400097f4`
- `0x14000aba8`
- `0x14000ba7c`
- `0x14000d1b4`
- `0x140019cd0`
- `0x14001ea34`
- `0x14001ebd8`
- `0x14001ed50`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008aec`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008c00`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008aec`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008c00`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008b97`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008bbe`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008c5c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008c8a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008b97`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008bbe`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008c5c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008c8a`

## string_xrefs

- `0x140008be3`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`

## pseudocode

```c
__int64 __fastcall TdiDisconnectRequest(__int64 a1, IRP *a2, __int64 a3, unsigned int *a4)
{
  unsigned int v6; // r15d
  KSPIN_LOCK *v7; // rbp
  int v8; // r8d
  int v9; // r9d
  const char *v10; // rdx
  int v11; // edi
  int v12; // edx
  int v13; // r8d
  int v14; // r9d
  __int64 v15; // r13
  int v16; // r15d
  bool v17; // r14
  int v18; // r9d

  if ( a4 )
    v6 = *a4;
  else
    v6 = 2;
  v7 = (KSPIN_LOCK *)(a3 + 48);
  *(_BYTE *)(a3 + 56) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a3 + 48));
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v10 = "Internal";
    if ( a2 )
      v10 = "Request";
    WPP_RECORDER_SF_ssqL(WPP_GLOBAL_Control->DeviceExtension, (_DWORD)v10, v8, v9);
  }
  if ( *(_DWORD *)(a3 + 80) && *(_QWORD *)(a3 + 568) == a3 + 568 )
  {
    v11 = -1073741823;
    if ( a2 && (v11 = IrpList_EnqueueEx(a3 + 568, a2), v11 < 0) )
    {
      KeReleaseSpinLock(v7, *(_BYTE *)(a3 + 56));
    }
    else
    {
      v15 = TdiReferenceChannelLocked(a3, 1313754947);
      KeReleaseSpinLock(v7, *(_BYTE *)(a3 + 56));
      if ( v15 )
      {
        v16 = ChannelDisconnectRequest(v15, v6);
        RefObj_ReleaseEx(v15 + 24, 1313754947, 2264, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
      }
      else
      {
        v16 = 0;
      }
      *(_BYTE *)(a3 + 56) = KeAcquireSpinLockRaiseToDpc(v7);
      if ( v16 == 259 )
      {
        v17 = 0;
        *(_BYTE *)(a3 + 97) = 0;
        if ( !a2 )
        {
          TdiConnStateLocked(a3, 0);
          *(_BYTE *)(a3 + 96) = 0;
        }
      }
      else
      {
        TdiConnStateLocked(a3, 0);
        *(_WORD *)(a3 + 96) = 0;
        a2 = (IRP *)IrpList_Dequeue(a3 + 568);
        v17 = a2 != 0;
      }
      KeReleaseSpinLock(v7, *(_BYTE *)(a3 + 56));
      if ( v17 )
        RfcommCompleteTdiIrp(a2, 0, 0, v18);
      TdiIndicateReceive(a3);
    }
  }
  else
  {
    KeReleaseSpinLock(v7, *(_BYTE *)(a3 + 56));
    v11 = 0;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_Ld(WPP_GLOBAL_Control->DeviceExtension, v12, v13, v14);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140008ac0  push    rbx
0x140008ac2  push    rbp
0x140008ac3  push    rsi
0x140008ac4  push    rdi
0x140008ac5  push    r13
0x140008ac7  push    r14
0x140008ac9  push    r15
0x140008acb  sub     rsp, 50h
0x140008acf  mov     rbx, r8
0x140008ad2  mov     rsi, rdx
0x140008ad5  test    r9, r9
0x140008ad8  jz      short loc_140008ADF
0x140008ada  mov     r15d, [r9]
0x140008add  jmp     short loc_140008AE5
0x140008adf  mov     r15d, 2
0x140008ae5  lea     rbp, [r8+30h]
0x140008ae9  mov     rcx, rbp; SpinLock
0x140008aec  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140008af3  nop     dword ptr [rax+rax+00h]
0x140008af8  mov     [rbx+38h], al
0x140008afb  lea     rax, WPP_RECORDER_INITIALIZED
0x140008b02  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140008b09  jz      short loc_140008B5C
0x140008b0b  test    rsi, rsi
0x140008b0e  lea     rax, aRequest_0; "Request"
0x140008b15  lea     rdx, aInternal; "Internal"
0x140008b1c  cmovnz  rdx, rax
0x140008b20  lea     rcx, aAbortive; "Abortive"
0x140008b27  lea     rax, aGraceful_0; "Graceful"
0x140008b2e  cmp     r15d, 2
0x140008b32  cmovnz  rcx, rax
0x140008b36  mov     eax, [rbx+50h]
0x140008b39  mov     [rsp+88h+var_48], eax
0x140008b3d  mov     [rsp+88h+var_50], rbx
0x140008b42  mov     [rsp+88h+var_58], rdx
0x140008b47  mov     [rsp+88h+var_60], rcx
0x140008b4c  mov     rcx, cs:WPP_GLOBAL_Control
0x140008b53  mov     rcx, [rcx+40h]
0x140008b57  call    WPP_RECORDER_SF_ssqL
0x140008b5c  cmp     dword ptr [rbx+50h], 0
0x140008b60  jz      loc_140008C84
0x140008b66  lea     r14, [rbx+238h]
0x140008b6d  cmp     [r14], r14
0x140008b70  jnz     loc_140008C84
0x140008b76  mov     edi, 0C0000001h
0x140008b7b  test    rsi, rsi
0x140008b7e  jz      short loc_140008BA8
0x140008b80  mov     rdx, rsi
0x140008b83  mov     rcx, r14
0x140008b86  call    IrpList_EnqueueEx
0x140008b8b  mov     edi, eax
0x140008b8d  test    eax, eax
0x140008b8f  jns     short loc_140008BA8
0x140008b91  mov     dl, [rbx+38h]; NewIrql
0x140008b94  mov     rcx, rbp; SpinLock
0x140008b97  call    cs:__imp_KeReleaseSpinLock
0x140008b9e  nop     dword ptr [rax+rax+00h]
0x140008ba3  jmp     loc_140008C98
0x140008ba8  mov     edx, 4E4E4F43h
0x140008bad  mov     rcx, rbx
0x140008bb0  call    TdiReferenceChannelLocked
0x140008bb5  mov     dl, [rbx+38h]; NewIrql
0x140008bb8  mov     rcx, rbp; SpinLock
0x140008bbb  mov     r13, rax
0x140008bbe  call    cs:__imp_KeReleaseSpinLock
0x140008bc5  nop     dword ptr [rax+rax+00h]
0x140008bca  test    r13, r13
0x140008bcd  jz      short loc_140008BFA
0x140008bcf  mov     edx, r15d
0x140008bd2  mov     rcx, r13
0x140008bd5  call    ChannelDisconnectRequest
0x140008bda  lea     rcx, [r13+18h]
0x140008bde  mov     edx, 4E4E4F43h
0x140008be3  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140008bea  mov     r8d, 8D8h
0x140008bf0  mov     r15d, eax
0x140008bf3  call    RefObj_ReleaseEx
0x140008bf8  jmp     short loc_140008BFD
0x140008bfa  xor     r15d, r15d
0x140008bfd  mov     rcx, rbp; SpinLock
0x140008c00  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140008c07  nop     dword ptr [rax+rax+00h]
0x140008c0c  mov     [rbx+38h], al
0x140008c0f  cmp     r15d, 103h
0x140008c16  jz      short loc_140008C3C
0x140008c18  xor     edx, edx
0x140008c1a  mov     rcx, rbx
0x140008c1d  call    TdiConnStateLocked
0x140008c22  mov     rcx, r14
0x140008c25  mov     word ptr [rbx+60h], 0
0x140008c2b  call    IrpList_Dequeue
0x140008c30  test    rax, rax
0x140008c33  mov     rsi, rax
0x140008c36  setnz   r14b
0x140008c3a  jmp     short loc_140008C56
0x140008c3c  xor     r14b, r14b
0x140008c3f  mov     [rbx+61h], r14b
0x140008c43  test    rsi, rsi
0x140008c46  jnz     short loc_140008C56
0x140008c48  xor     edx, edx
0x140008c4a  mov     rcx, rbx
0x140008c4d  call    TdiConnStateLocked
0x140008c52  mov     [rbx+60h], r14b
0x140008c56  mov     dl, [rbx+38h]; NewIrql
0x140008c59  mov     rcx, rbp; SpinLock
0x140008c5c  call    cs:__imp_KeReleaseSpinLock
0x140008c63  nop     dword ptr [rax+rax+00h]
0x140008c68  test    r14b, r14b
0x140008c6b  jz      short loc_140008C7A
0x140008c6d  xor     r8d, r8d
0x140008c70  xor     edx, edx
0x140008c72  mov     rcx, rsi; Irp
0x140008c75  call    RfcommCompleteTdiIrp
0x140008c7a  mov     rcx, rbx
0x140008c7d  call    TdiIndicateReceive
0x140008c82  jmp     short loc_140008C98
0x140008c84  mov     dl, [rbx+38h]; NewIrql
0x140008c87  mov     rcx, rbp; SpinLock
0x140008c8a  call    cs:__imp_KeReleaseSpinLock
0x140008c91  nop     dword ptr [rax+rax+00h]
0x140008c96  xor     edi, edi
0x140008c98  lea     rax, WPP_RECORDER_INITIALIZED
0x140008c9f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140008ca6  jz      short loc_140008CC3
0x140008ca8  mov     rcx, cs:WPP_GLOBAL_Control
0x140008caf  mov     eax, [rbx+50h]
0x140008cb2  mov     dword ptr [rsp+88h+var_58], edi
0x140008cb6  mov     dword ptr [rsp+88h+var_60], eax
0x140008cba  mov     rcx, [rcx+40h]
0x140008cbe  call    WPP_RECORDER_SF_Ld
0x140008cc3  mov     eax, edi
0x140008cc5  add     rsp, 50h
0x140008cc9  pop     r15
0x140008ccb  pop     r14
0x140008ccd  pop     r13
0x140008ccf  pop     rdi
0x140008cd0  pop     rsi
0x140008cd1  pop     rbp
0x140008cd2  pop     rbx
0x140008cd3  retn
```
