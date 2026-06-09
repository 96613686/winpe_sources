# SharedSocket::CreateKeepAliveTimer(ulong)

- ea: `0x180027ba8`
- end: `0x180027c47`
- name: `?CreateKeepAliveTimer@SharedSocket@@AEAAKK@Z`
- size: `159`
- prototype: `unsigned int __fastcall(SharedSocket *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180001bc0`
- `0x180012490`

## callees

- `0x1800024bc`
- `0x18000a0a0`
- `0x180027ba8`
- `0x18002a22c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027bc8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027bc8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027c2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027c2f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180027bf4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180027bf4`

## string_xrefs

- `0x180027be6`: `SharedSocket: CreateKeepAliveTimer failed`

## pseudocode

```c
__int64 __fastcall SharedSocket::CreateKeepAliveTimer(struct _RTL_CRITICAL_SECTION *this, int a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  __int64 v5; // rdx
  __int64 v6; // rcx
  unsigned int WakeTimer; // ebx
  ULONGLONG TickCount64; // rax
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rdx

  SharedSocket::DeleteKeepAliveTimer(this);
  v4 = this + 1;
  EnterCriticalSection(this + 1);
  if ( this[2].DebugInfo )
  {
    TickCount64 = GetTickCount64();
    DebugInfo = this[2].DebugInfo;
    *(_QWORD *)&this[6].LockCount = TickCount64;
    WakeTimer = WakeTimer::CreateWakeTimer(
                  60000 * a2,
                  *(unsigned __int16 **)&DebugInfo[1].Type,
                  this,
                  (void (__high *)(void *, struct _CBROKERED_EVENT_ID, void *, void *, unsigned int, unsigned int, enum _BI_ACTIVATION_STATUS *))&SharedSocket::HandleWakeTimerCallback,
                  &this[5].LockSemaphore);
  }
  else
  {
    WakeTimer = 5023;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v6, v5, L"SharedSocket: CreateKeepAliveTimer failed", 5023);
  }
  LeaveCriticalSection(v4);
  return WakeTimer;
}

```

## disassembly

```asm
0x180027ba8  mov     [rsp+arg_0], rbx
0x180027bad  mov     [rsp+arg_8], rsi
0x180027bb2  push    rdi
0x180027bb3  sub     rsp, 30h
0x180027bb7  mov     esi, edx
0x180027bb9  mov     rbx, rcx
0x180027bbc  call    ?DeleteKeepAliveTimer@SharedSocket@@AEAAXXZ; SharedSocket::DeleteKeepAliveTimer(void)
0x180027bc1  lea     rdi, [rbx+28h]
0x180027bc5  mov     rcx, rdi; lpCriticalSection
0x180027bc8  call    cs:__imp_EnterCriticalSection
0x180027bce  cmp     qword ptr [rbx+50h], 0
0x180027bd3  jnz     short loc_180027BF4
0x180027bd5  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180027bdc  mov     ebx, 139Fh
0x180027be1  jz      short loc_180027C2C
0x180027be3  mov     r9d, ebx
0x180027be6  lea     r8, aSharedsocketCr_1; "SharedSocket: CreateKeepAliveTimer fail"...
0x180027bed  call    McTemplateU0zq_EventWriteTransfer
0x180027bf2  jmp     short loc_180027C2C
0x180027bf4  call    cs:__imp_GetTickCount64
0x180027bfa  mov     rdx, [rbx+50h]
0x180027bfe  lea     r9, ?HandleWakeTimerCallback@SharedSocket@@CAXPEAXU_CBROKERED_EVENT_ID@@00KKPEAW4_BI_ACTIVATION_STATUS@@@Z; void (__high *)(void *, struct _CBROKERED_EVENT_ID, void *, void *, unsigned int, unsigned int, enum _BI_ACTIVATION_STATUS *)
0x180027c05  mov     [rbx+0F8h], rax
0x180027c0c  mov     r8, rbx; void *
0x180027c0f  lea     rax, [rbx+0E0h]
0x180027c16  imul    ecx, esi, 0EA60h; unsigned int
0x180027c1c  mov     [rsp+38h+var_18], rax; void **
0x180027c21  mov     rdx, [rdx+30h]; unsigned __int16 *
0x180027c25  call    ?CreateWakeTimer@WakeTimer@@SAKKPEAGPEAXP6AX1U_CBROKERED_EVENT_ID@@11KKPEAW4_BI_ACTIVATION_STATUS@@@ZPEAPEAX@Z; WakeTimer::CreateWakeTimer(ulong,ushort *,void *,void (*)(void *,_CBROKERED_EVENT_ID,void *,void *,ulong,ulong,_BI_ACTIVATION_STATUS *),void * *)
0x180027c2a  mov     ebx, eax
0x180027c2c  mov     rcx, rdi; lpCriticalSection
0x180027c2f  call    cs:__imp_LeaveCriticalSection
0x180027c35  mov     rsi, [rsp+38h+arg_8]
0x180027c3a  mov     eax, ebx
0x180027c3c  mov     rbx, [rsp+38h+arg_0]
0x180027c41  add     rsp, 30h
0x180027c45  pop     rdi
0x180027c46  retn
```
