# CKsClockF::Pause(void)

- ea: `0x18000a350`
- end: `0x18000a470`
- name: `?Pause@CKsClockF@@UEAAJXZ`
- size: `288`
- prototype: `signed int __fastcall(CKsClockF *this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000a350`
- `0x18000a694`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000a3a7`
- `KERNEL32!GetLastError` at `0x18000a3a7`
- `KERNEL32!SetEvent` at `0x18000a448`
- `KERNEL32!SetEvent` at `0x18000a448`
- `KERNEL32!ResumeThread` at `0x18000a424`
- `KERNEL32!ResumeThread` at `0x18000a424`
- `KERNEL32!CreateEventW` at `0x18000a392`
- `KERNEL32!CreateEventW` at `0x18000a392`
- `KERNEL32!CreateThread` at `0x18000a3f0`
- `KERNEL32!CreateThread` at `0x18000a3f0`
- `KERNEL32!SetThreadPriority` at `0x18000a40d`
- `KERNEL32!SetThreadPriority` at `0x18000a40d`

## pseudocode

```c
signed int __fastcall CKsClockF::Pause(CKsClockF *this)
{
  bool v1; // zf
  IKsObject_vtbl *EventW; // rax
  signed int result; // eax
  IDistributorNotify_vtbl *v5; // rax
  IDistributorNotify_vtbl *v6; // rcx
  IKsObject_vtbl *v7; // rcx
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF

  v1 = LODWORD(this->m_Thread) == 0;
  LODWORD(this->m_ClockHandle) = 0;
  if ( !v1 )
  {
    if ( LODWORD(this->m_Thread) == 2 )
    {
      LODWORD(this->m_Thread) = 1;
      v7 = this->IKsObject::IUnknown::__vftable;
      if ( v7 )
        SetEvent(v7);
    }
    goto LABEL_14;
  }
  if ( !*(_QWORD *)&this->m_cRef )
  {
LABEL_14:
    CKsClockF::SetState((CKsClockF *)((char *)this - 24), KSSTATE_PAUSE);
    return 0;
  }
  v1 = this->IKsObject::IUnknown::__vftable == 0;
  ThreadId = 0;
  if ( v1 )
  {
    EventW = (IKsObject_vtbl *)CreateEventW(0, 0, 0, 0);
    this->IKsObject::IUnknown::__vftable = EventW;
    if ( !EventW )
      goto LABEL_5;
  }
  if ( this->IDistributorNotify::IUnknown::__vftable )
  {
LABEL_10:
    v6 = this->IDistributorNotify::IUnknown::__vftable;
    LODWORD(this->m_Thread) = 1;
    ResumeThread(v6);
    goto LABEL_14;
  }
  v5 = (IDistributorNotify_vtbl *)CreateThread(0, 0, CKsClockF::ClockThread, &this[-1].m_State, 4u, &ThreadId);
  this->IDistributorNotify::IUnknown::__vftable = v5;
  if ( v5 )
  {
    SetThreadPriority(v5, 2);
    goto LABEL_10;
  }
LABEL_5:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000a350  mov     [rsp+arg_8], rbx
0x18000a355  push    rdi
0x18000a356  sub     rsp, 30h
0x18000a35a  cmp     dword ptr [rcx+30h], 0
0x18000a35e  mov     rbx, rcx
0x18000a361  mov     dword ptr [rcx+40h], 0
0x18000a368  jnz     loc_18000A432
0x18000a36e  cmp     qword ptr [rcx+10h], 0
0x18000a373  jz      loc_18000A454
0x18000a379  cmp     qword ptr [rcx+20h], 0
0x18000a37e  mov     [rsp+38h+ThreadId], 0
0x18000a386  jnz     short loc_18000A3C8
0x18000a388  xor     r9d, r9d; lpName
0x18000a38b  xor     r8d, r8d; bInitialState
0x18000a38e  xor     edx, edx; bManualReset
0x18000a390  xor     ecx, ecx; lpEventAttributes
0x18000a392  call    cs:__imp_CreateEventW
0x18000a399  nop     dword ptr [rax+rax+00h]
0x18000a39e  mov     [rbx+20h], rax
0x18000a3a2  test    rax, rax
0x18000a3a5  jnz     short loc_18000A3C8
0x18000a3a7  call    cs:__imp_GetLastError
0x18000a3ae  nop     dword ptr [rax+rax+00h]
0x18000a3b3  test    eax, eax
0x18000a3b5  jle     loc_18000A464
0x18000a3bb  movzx   eax, ax
0x18000a3be  or      eax, 80070000h
0x18000a3c3  jmp     loc_18000A464
0x18000a3c8  cmp     qword ptr [rbx+18h], 0
0x18000a3cd  jnz     short loc_18000A419
0x18000a3cf  lea     rax, [rsp+38h+ThreadId]
0x18000a3d4  xor     edx, edx; dwStackSize
0x18000a3d6  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18000a3db  lea     r9, [rbx-18h]; lpParameter
0x18000a3df  lea     r8, ?ClockThread@CKsClockF@@CAJPEAV1@@Z; lpStartAddress
0x18000a3e6  mov     [rsp+38h+dwCreationFlags], 4; dwCreationFlags
0x18000a3ee  xor     ecx, ecx; lpThreadAttributes
0x18000a3f0  call    cs:__imp_CreateThread
0x18000a3f7  nop     dword ptr [rax+rax+00h]
0x18000a3fc  mov     [rbx+18h], rax
0x18000a400  test    rax, rax
0x18000a403  jz      short loc_18000A3A7
0x18000a405  mov     edx, 2; nPriority
0x18000a40a  mov     rcx, rax; hThread
0x18000a40d  call    cs:__imp_SetThreadPriority
0x18000a414  nop     dword ptr [rax+rax+00h]
0x18000a419  mov     rcx, [rbx+18h]; hThread
0x18000a41d  mov     dword ptr [rbx+30h], 1
0x18000a424  call    cs:__imp_ResumeThread
0x18000a42b  nop     dword ptr [rax+rax+00h]
0x18000a430  jmp     short loc_18000A454
0x18000a432  cmp     dword ptr [rcx+30h], 2
0x18000a436  jnz     short loc_18000A454
0x18000a438  mov     dword ptr [rcx+30h], 1
0x18000a43f  mov     rcx, [rcx+20h]; hEvent
0x18000a443  test    rcx, rcx
0x18000a446  jz      short loc_18000A454
0x18000a448  call    cs:__imp_SetEvent
0x18000a44f  nop     dword ptr [rax+rax+00h]
0x18000a454  mov     edx, 2; enum KSSTATE
0x18000a459  lea     rcx, [rbx-18h]; this
0x18000a45d  call    ?SetState@CKsClockF@@AEAAJW4KSSTATE@@@Z; CKsClockF::SetState(KSSTATE)
0x18000a462  xor     eax, eax
0x18000a464  mov     rbx, [rsp+38h+arg_8]
0x18000a469  add     rsp, 30h
0x18000a46d  pop     rdi
0x18000a46e  retn
```
