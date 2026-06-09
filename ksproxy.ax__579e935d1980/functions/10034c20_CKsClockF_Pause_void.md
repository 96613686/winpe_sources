# CKsClockF::Pause(void)

- ea: `0x10034c20`
- end: `0x10034cd8`
- name: `?Pause@CKsClockF@@UAGJXZ`
- size: `184`
- prototype: `int(CKsClockF *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x10034c20`
- `0x10034d89`

## import_xrefs

- `KERNEL32!GetLastError` at `0x10034c54`
- `KERNEL32!GetLastError` at `0x10034c54`
- `KERNEL32!SetEvent` at `0x10034cbf`
- `KERNEL32!SetEvent` at `0x10034cbf`
- `KERNEL32!ResumeThread` at `0x10034ca2`
- `KERNEL32!ResumeThread` at `0x10034ca2`
- `KERNEL32!CreateEventW` at `0x10034c47`
- `KERNEL32!CreateEventW` at `0x10034c47`
- `KERNEL32!CreateThread` at `0x10034c82`
- `KERNEL32!CreateThread` at `0x10034c82`
- `KERNEL32!SetThreadPriority` at `0x10034c92`
- `KERNEL32!SetThreadPriority` at `0x10034c92`

## pseudocode

```c
unsigned int __stdcall CKsClockF::Pause(CKsClockF *this)
{
  IKsObject_vtbl *EventW; // eax
  signed int LastError; // eax
  unsigned int v3; // ecx
  IDistributorNotify_vtbl *v5; // eax
  IDistributorNotify_vtbl *v6; // [esp-4h] [ebp-10h]
  CKsClockF *v7; // [esp+0h] [ebp-Ch]
  enum KSSTATE v8; // [esp+4h] [ebp-8h]
  DWORD ThreadId; // [esp+8h] [ebp-4h] BYREF

  this->m_State = State_Stopped;
  if ( this->m_Thread )
  {
    if ( this->m_Thread == (void *)2 )
    {
      this->m_Thread = (void *)1;
      if ( this->IKsObject::IUnknown::__vftable )
        SetEvent(this->IKsObject::IUnknown::__vftable);
    }
    goto LABEL_15;
  }
  if ( !this->m_cRef )
  {
LABEL_15:
    CKsClockF::SetState(v7, v8);
    return 0;
  }
  if ( this->IKsObject::IUnknown::__vftable
    || (EventW = (IKsObject_vtbl *)CreateEventW(0, 0, 0, 0), (this->IKsObject::IUnknown::__vftable = EventW) != 0) )
  {
    if ( !this->IDistributorNotify::IUnknown::__vftable )
    {
      v5 = (IDistributorNotify_vtbl *)CreateThread(
                                        0,
                                        0,
                                        CKsClockF::ClockThread,
                                        (char *)&this[-1].m_StartTime + 4,
                                        4u,
                                        &ThreadId);
      this->IDistributorNotify::IUnknown::__vftable = v5;
      if ( !v5 )
        goto LABEL_5;
      SetThreadPriority(v5, 2);
    }
    v6 = this->IDistributorNotify::IUnknown::__vftable;
    this->m_Thread = (void *)1;
    ResumeThread(v6);
    goto LABEL_15;
  }
LABEL_5:
  LastError = GetLastError();
  v3 = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    return LastError;
  return v3;
}

```

## disassembly

```asm
0x10034c20  mov     edi, edi
0x10034c22  push    ebp
0x10034c23  mov     ebp, esp
0x10034c25  push    ecx
0x10034c26  push    esi; enum KSSTATE
0x10034c27  mov     esi, [ebp+this]
0x10034c2a  push    edi; this
0x10034c2b  xor     edi, edi
0x10034c2d  mov     [esi+24h], edi
0x10034c30  cmp     [esi+18h], edi
0x10034c33  jnz     short loc_10034CAA
0x10034c35  cmp     [esi+8], edi
0x10034c38  jz      loc_10034CC5
0x10034c3e  cmp     [esi+10h], edi
0x10034c41  jnz     short loc_10034C6C
0x10034c43  push    edi; lpName
0x10034c44  push    edi; bInitialState
0x10034c45  push    edi; bManualReset
0x10034c46  push    edi; lpEventAttributes
0x10034c47  call    ds:__imp__CreateEventW@16; CreateEventW(x,x,x,x)
0x10034c4d  mov     [esi+10h], eax
0x10034c50  test    eax, eax
0x10034c52  jnz     short loc_10034C6C
0x10034c54  call    ds:__imp__GetLastError@0; GetLastError()
0x10034c5a  movzx   ecx, ax
0x10034c5d  or      ecx, 80070000h
0x10034c63  test    eax, eax
0x10034c65  cmovle  ecx, eax
0x10034c68  mov     eax, ecx
0x10034c6a  jmp     short loc_10034CD2
0x10034c6c  cmp     [esi+0Ch], edi
0x10034c6f  jnz     short loc_10034C98
0x10034c71  lea     eax, [ebp+ThreadId]
0x10034c74  push    eax; lpThreadId
0x10034c75  push    4; dwCreationFlags
0x10034c77  lea     eax, [esi-0Ch]
0x10034c7a  push    eax; lpParameter
0x10034c7b  push    offset ?ClockThread@CKsClockF@@CGJPAV1@@Z; lpStartAddress
0x10034c80  push    edi; dwStackSize
0x10034c81  push    edi; lpThreadAttributes
0x10034c82  call    ds:__imp__CreateThread@24; CreateThread(x,x,x,x,x,x)
0x10034c88  mov     [esi+0Ch], eax
0x10034c8b  test    eax, eax
0x10034c8d  jz      short loc_10034C54
0x10034c8f  push    2; nPriority
0x10034c91  push    eax; hThread
0x10034c92  call    ds:__imp__SetThreadPriority@8; SetThreadPriority(x,x)
0x10034c98  push    dword ptr [esi+0Ch]; hThread
0x10034c9b  mov     dword ptr [esi+18h], 1
0x10034ca2  call    ds:__imp__ResumeThread@4; ResumeThread(x)
0x10034ca8  jmp     short loc_10034CC5
0x10034caa  cmp     dword ptr [esi+18h], 2
0x10034cae  jnz     short loc_10034CC5
0x10034cb0  mov     dword ptr [esi+18h], 1
0x10034cb7  cmp     [esi+10h], edi
0x10034cba  jz      short loc_10034CC5
0x10034cbc  push    dword ptr [esi+10h]; hEvent
0x10034cbf  call    ds:__imp__SetEvent@4; SetEvent(x)
0x10034cc5  push    2
0x10034cc7  lea     ecx, [esi-0Ch]
0x10034cca  pop     edx
0x10034ccb  call    ?SetState@CKsClockF@@AAGJW4KSSTATE@@@Z; CKsClockF::SetState(KSSTATE)
0x10034cd0  xor     eax, eax
0x10034cd2  pop     edi
0x10034cd3  pop     esi
0x10034cd4  leave
0x10034cd5  retn    4
```
