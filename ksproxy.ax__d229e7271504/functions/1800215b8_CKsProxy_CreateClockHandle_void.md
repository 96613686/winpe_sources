# CKsProxy::CreateClockHandle(void)

- ea: `0x1800215b8`
- end: `0x180021652`
- name: `?CreateClockHandle@CKsProxy@@QEAAJXZ`
- size: `154`
- prototype: `signed int __fastcall(CKsProxy *this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180002f80`
- `0x180020c20`
- `0x180020d70`
- `0x180021278`
- `0x180022da0`

## callees

- `0x18000c9f0`
- `0x1800215b8`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800215f2`
- `KERNEL32!CloseHandle` at `0x1800215f2`
- `ksuser!KsCreateClock` at `0x180021618`
- `ksuser!KsCreateClock` at `0x180021618`

## pseudocode

```c
signed int __fastcall CKsProxy::CreateClockHandle(CKsProxy *this)
{
  struct CBasePin *m_PinClockSource; // rdx
  void *PinHandle; // rdi
  void *m_PinClockHandle; // rcx
  signed int result; // eax
  bool v6; // sf
  $9CC657B7E0AE245246966219C61A944E ClockCreate; // [rsp+30h] [rbp+8h] BYREF

  m_PinClockSource = this->m_PinClockSource;
  if ( !m_PinClockSource )
    return -2147467263;
  PinHandle = (void *)CKsProxy::GetPinHandle(this, m_PinClockSource);
  if ( !PinHandle )
    return -2147467263;
  m_PinClockHandle = this->m_PinClockHandle;
  ClockCreate.CreateFlags = 0;
  if ( m_PinClockHandle )
  {
    CloseHandle(m_PinClockHandle);
    this->m_PinClockHandle = 0;
  }
  result = KsCreateClock(PinHandle, &ClockCreate, &this->m_PinClockHandle);
  v6 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v6 = result < 0;
  }
  if ( v6 )
    this->m_PinClockHandle = 0;
  return result;
}

```

## disassembly

```asm
0x1800215b8  mov     [rsp+arg_8], rbx
0x1800215bd  push    rdi
0x1800215be  sub     rsp, 20h
0x1800215c2  mov     rdx, [rcx+1E0h]; struct CBasePin *
0x1800215c9  mov     rbx, rcx
0x1800215cc  test    rdx, rdx
0x1800215cf  jz      short loc_180021641
0x1800215d1  call    ?GetPinHandle@CKsProxy@@QEAAPEAXPEAVCBasePin@@@Z; CKsProxy::GetPinHandle(CBasePin *)
0x1800215d6  mov     rdi, rax
0x1800215d9  test    rax, rax
0x1800215dc  jz      short loc_180021641
0x1800215de  mov     rcx, [rbx+180h]; hObject
0x1800215e5  mov     [rsp+28h+ClockCreate.CreateFlags], 0
0x1800215ed  test    rcx, rcx
0x1800215f0  jz      short loc_180021609
0x1800215f2  call    cs:__imp_CloseHandle
0x1800215f9  nop     dword ptr [rax+rax+00h]
0x1800215fe  mov     qword ptr [rbx+180h], 0
0x180021609  lea     r8, [rbx+180h]; ClockHandle
0x180021610  mov     rcx, rdi; ConnectionHandle
0x180021613  lea     rdx, [rsp+28h+ClockCreate]; ClockCreate
0x180021618  call    cs:__imp_KsCreateClock
0x18002161f  nop     dword ptr [rax+rax+00h]
0x180021624  test    eax, eax
0x180021626  jle     short loc_180021632
0x180021628  movzx   eax, ax
0x18002162b  or      eax, 80070000h
0x180021630  test    eax, eax
0x180021632  jns     short loc_180021646
0x180021634  mov     qword ptr [rbx+180h], 0
0x18002163f  jmp     short loc_180021646
0x180021641  mov     eax, 80004001h
0x180021646  mov     rbx, [rsp+28h+arg_8]
0x18002164b  add     rsp, 20h
0x18002164f  pop     rdi
0x180021650  retn
```
