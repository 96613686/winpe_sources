# NcbCCResetSignalEventId

- ea: `0x180020c24`
- end: `0x180020dd6`
- name: `NcbCCResetSignalEventId`
- size: `434`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180015164`

## callees

- `0x180009740`
- `0x18000a0a0`
- `0x180020c24`

## import_xrefs

- `BrokerLib!BrLockBroker` at `0x180020c5e`
- `BrokerLib!BrLockBroker` at `0x180020c5e`
- `BrokerLib!BrFindBrokeredEvent` at `0x180020caf`
- `BrokerLib!BrFindBrokeredEvent` at `0x180020caf`
- `BrokerLib!BrUnlockBroker` at `0x180020cf0`
- `BrokerLib!BrUnlockBroker` at `0x180020dc1`
- `BrokerLib!BrUnlockBroker` at `0x180020cf0`
- `BrokerLib!BrUnlockBroker` at `0x180020dc1`
- `BrokerLib!BrSignalBrokerEvent` at `0x180020d4b`
- `BrokerLib!BrSignalBrokerEvent` at `0x180020d4b`
- `BrokerLib!BrGetBrokeredAppState2` at `0x180020cdd`
- `BrokerLib!BrGetBrokeredAppState2` at `0x180020cdd`

## string_xrefs

- `0x180020c75`: `NcbCCResetSignalEventId: Failed to get read lock.`
- `0x180020d5d`: `NcbCCResetSignalEventId: BrSignalBrokerEvent`
- `0x180020d79`: `NcbCCResetSignalEventId: BrGetBrokeredAppState`
- `0x180020daa`: `NcbCCResetSignalEventId: BrFindBrokeredEvent`

## pseudocode

```c
__int64 __fastcall NcbCCResetSignalEventId(int a1, int a2, char a3, char a4, __int64 a5, __int128 *a6)
{
  __int64 result; // rax
  __int64 v10; // rdx
  __int64 v11; // rcx
  const wchar_t *v12; // r8
  __int128 *v13; // rsi
  unsigned int BrokeredEvent; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  unsigned int BrokeredAppState2; // edi
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int128 v20; // xmm0
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // [rsp+30h] [rbp-58h] BYREF
  __int64 v24; // [rsp+38h] [rbp-50h] BYREF
  _OWORD v25[4]; // [rsp+40h] [rbp-48h] BYREF
  int v26; // [rsp+90h] [rbp+8h] BYREF

  v26 = a1;
  v24 = 0;
  v23 = 0;
  LOBYTE(v26) = 0;
  result = BrLockBroker(a5, 1);
  if ( (_DWORD)result )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
      return result;
    v12 = L"NcbCCResetSignalEventId: Failed to get read lock.";
    return McTemplateU0z_EventWriteTransfer(v11, v10, v12);
  }
  v13 = a6;
  v25[0] = *a6;
  BrokeredEvent = BrFindBrokeredEvent(a5, v25, 0, 0, &v24);
  if ( BrokeredEvent )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v16, v15, L"NcbCCResetSignalEventId: BrFindBrokeredEvent", BrokeredEvent);
    return BrUnlockBroker(a5, 1);
  }
  else
  {
    BrokeredAppState2 = BrGetBrokeredAppState2(a5, v24, 0, 1, &v26);
    BrUnlockBroker(a5, 1);
    if ( BrokeredAppState2 || !(_BYTE)v26 )
    {
      result = (unsigned int)Microsoft_Windows_Network_Connection_BrokerEnableBits;
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      {
        McTemplateU0zq_EventWriteTransfer(
          v19,
          v18,
          L"NcbCCResetSignalEventId: BrGetBrokeredAppState",
          BrokeredAppState2);
        result = (unsigned int)Microsoft_Windows_Network_Connection_BrokerEnableBits;
        if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        {
          v12 = L"NcbCCResetSignalEventId: Failed to get app state or app is not on lock screen.";
          return McTemplateU0z_EventWriteTransfer(v11, v10, v12);
        }
      }
    }
    else
    {
      v20 = *v13;
      LODWORD(v23) = a2;
      BYTE4(v23) = a3 != 0;
      v25[0] = v20;
      BYTE5(v23) = a4 != 0;
      result = ((__int64 (__fastcall *)(__int64, _OWORD *, _QWORD, __int64 *, int, __int64 *))BrSignalBrokerEvent)(
                 a5,
                 v25,
                 0,
                 CCT_RESET_EVENT_PARSER_CLSID,
                 8,
                 &v23);
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        return McTemplateU0zq_EventWriteTransfer(
                 v22,
                 v21,
                 L"NcbCCResetSignalEventId: BrSignalBrokerEvent",
                 (unsigned int)result);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180020c24  mov     rax, rsp
0x180020c27  mov     [rax+8], ecx
0x180020c2a  push    rsi
0x180020c2b  push    rdi
0x180020c2c  push    r12
0x180020c2e  push    r13
0x180020c30  push    r14
0x180020c32  push    r15
0x180020c34  sub     rsp, 58h
0x180020c38  mov     rcx, [rsp+88h+arg_20]
0x180020c40  xor     edi, edi
0x180020c42  mov     r12d, edx
0x180020c45  mov     [rax-50h], rdi
0x180020c49  mov     r14b, r9b
0x180020c4c  mov     [rax-58h], rdi
0x180020c50  mov     r15b, r8b
0x180020c53  mov     [rax+8], dil
0x180020c57  lea     r13d, [rdi+1]
0x180020c5b  mov     edx, r13d
0x180020c5e  call    cs:__imp_BrLockBroker
0x180020c64  test    eax, eax
0x180020c66  jz      short loc_180020C81
0x180020c68  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, r13b
0x180020c6f  jz      loc_180020DC7
0x180020c75  lea     r8, aNcbccresetsign_0; "NcbCCResetSignalEventId: Failed to get "...
0x180020c7c  jmp     loc_180020D97
0x180020c81  mov     rsi, [rsp+88h+arg_28]
0x180020c89  lea     rax, [rsp+88h+var_50]
0x180020c8e  mov     rcx, [rsp+88h+arg_20]
0x180020c96  lea     rdx, [rsp+88h+var_48]
0x180020c9b  xor     r9d, r9d
0x180020c9e  mov     [rsp+88h+var_68], rax
0x180020ca3  xor     r8d, r8d
0x180020ca6  movaps  xmm0, xmmword ptr [rsi]
0x180020ca9  movdqa  [rsp+88h+var_48], xmm0
0x180020caf  call    cs:__imp_BrFindBrokeredEvent
0x180020cb5  test    eax, eax
0x180020cb7  jnz     loc_180020D9E
0x180020cbd  mov     rdx, [rsp+88h+var_50]
0x180020cc2  lea     rax, [rsp+88h+arg_0]
0x180020cca  mov     rcx, [rsp+88h+arg_20]
0x180020cd2  mov     r9d, r13d
0x180020cd5  xor     r8d, r8d
0x180020cd8  mov     [rsp+88h+var_68], rax
0x180020cdd  call    cs:__imp_BrGetBrokeredAppState2
0x180020ce3  mov     rcx, [rsp+88h+arg_20]
0x180020ceb  mov     edx, r13d
0x180020cee  mov     edi, eax
0x180020cf0  call    cs:__imp_BrUnlockBroker
0x180020cf6  test    edi, edi
0x180020cf8  jnz     short loc_180020D6B
0x180020cfa  cmp     byte ptr [rsp+88h+arg_0], dil
0x180020d02  jz      short loc_180020D6B
0x180020d04  movaps  xmm0, xmmword ptr [rsi]
0x180020d07  lea     rax, [rsp+88h+var_58]
0x180020d0c  mov     rcx, [rsp+88h+arg_20]
0x180020d14  lea     r9, CCT_RESET_EVENT_PARSER_CLSID
0x180020d1b  test    r15b, r15b
0x180020d1e  mov     [rsp+88h+var_60], rax
0x180020d23  lea     rdx, [rsp+88h+var_48]
0x180020d28  mov     [rsp+88h+var_58], r12d
0x180020d2d  setnz   [rsp+88h+var_54]
0x180020d32  movdqa  [rsp+88h+var_48], xmm0
0x180020d38  test    r14b, r14b
0x180020d3b  mov     dword ptr [rsp+88h+var_68], 8
0x180020d43  setnz   [rsp+88h+var_53]
0x180020d48  xor     r8d, r8d
0x180020d4b  call    cs:__imp_BrSignalBrokerEvent
0x180020d51  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, r13b
0x180020d58  jz      short loc_180020DC7
0x180020d5a  mov     r9d, eax
0x180020d5d  lea     r8, aNcbccresetsign_1; "NcbCCResetSignalEventId: BrSignalBroker"...
0x180020d64  call    McTemplateU0zq_EventWriteTransfer
0x180020d69  jmp     short loc_180020DC7
0x180020d6b  mov     eax, cs:Microsoft_Windows_Network_Connection_BrokerEnableBits
0x180020d71  test    r13b, al
0x180020d74  jz      short loc_180020DC7
0x180020d76  mov     r9d, edi
0x180020d79  lea     r8, aNcbccresetsign_2; "NcbCCResetSignalEventId: BrGetBrokeredA"...
0x180020d80  call    McTemplateU0zq_EventWriteTransfer
0x180020d85  mov     eax, cs:Microsoft_Windows_Network_Connection_BrokerEnableBits
0x180020d8b  test    r13b, al
0x180020d8e  jz      short loc_180020DC7
0x180020d90  lea     r8, aNcbccresetsign_4; "NcbCCResetSignalEventId: Failed to get "...
0x180020d97  call    McTemplateU0z_EventWriteTransfer
0x180020d9c  jmp     short loc_180020DC7
0x180020d9e  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, r13b
0x180020da5  jz      short loc_180020DB6
0x180020da7  mov     r9d, eax
0x180020daa  lea     r8, aNcbccresetsign; "NcbCCResetSignalEventId: BrFindBrokered"...
0x180020db1  call    McTemplateU0zq_EventWriteTransfer
0x180020db6  mov     rcx, [rsp+88h+arg_20]
0x180020dbe  mov     edx, r13d
0x180020dc1  call    cs:__imp_BrUnlockBroker
0x180020dc7  add     rsp, 58h
0x180020dcb  pop     r15
0x180020dcd  pop     r14
0x180020dcf  pop     r13
0x180020dd1  pop     r12
0x180020dd3  pop     rdi
0x180020dd4  pop     rsi
0x180020dd5  retn
```
