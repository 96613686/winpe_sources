# CKsPin::ProcessingObjectWork(void)

- ea: `0x180003cb0`
- end: `0x180003f1b`
- name: `?ProcessingObjectWork@CKsPin@@UEAAXXZ`
- size: `619`
- prototype: `void __fastcall(CKsPin *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003cb0`
- `0x18000b7bc`
- `0x180019cb0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x180003ce1`
- `ntoskrnl!KeGetCurrentIrql` at `0x180003ce1`
- `ntoskrnl!KeReleaseMutex` at `0x180003e1f`
- `ntoskrnl!KeReleaseMutex` at `0x180003e1f`
- `ntoskrnl!KeReadStateMutex` at `0x180003e56`
- `ntoskrnl!KeReadStateMutex` at `0x180003e56`
- `ntoskrnl!KeWaitForSingleObject` at `0x180003d0c`
- `ntoskrnl!KeWaitForSingleObject` at `0x180003ed4`
- `ntoskrnl!KeWaitForSingleObject` at `0x180003d0c`
- `ntoskrnl!KeWaitForSingleObject` at `0x180003ed4`

## pseudocode

```c
void __fastcall CKsPin::ProcessingObjectWork(CKsPin *this)
{
  KIRQL CurrentIrql; // al
  struct _KMUTANT *p_m_ProcessOnRelease; // rcx
  struct _LIST_ENTRY **p_Blink; // rbp
  char v5; // bl
  int v6; // eax
  struct _LIST_ENTRY **v7; // rax
  __int64 i; // rcx
  struct _LIST_ENTRY **v9; // rcx
  LARGE_INTEGER Timeout; // [rsp+58h] [rbp+10h] BYREF

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      168,
      (__int64)WPP_9505c27395793143ec5446714e36088f_Traceguids);
  CurrentIrql = KeGetCurrentIrql();
  p_m_ProcessOnRelease = (struct _KMUTANT *)&this->m_ProcessOnRelease;
  if ( CurrentIrql )
  {
    LODWORD(this->m_DispatchSetDeviceState) = 1;
    if ( KeReadStateMutex(p_m_ProcessOnRelease) != 1
      || (Timeout.QuadPart = 0, KeWaitForSingleObject((PVOID)&this->m_ProcessOnRelease, Executive, 0, 0, &Timeout) == 258) )
    {
      LODWORD(this->m_DispatchSetDeviceState) = 2;
      return;
    }
    LODWORD(this->m_DispatchSetDeviceState) = 0;
  }
  else
  {
    KeWaitForSingleObject(p_m_ProcessOnRelease, Executive, 0, 0, 0);
  }
  p_Blink = &this->m_StopEvent.Header.WaitListHead.Blink;
  while ( 1 )
  {
    while ( 1 )
    {
      v5 = 0;
      if ( !*(_DWORD *)p_Blink )
        break;
LABEL_11:
      if ( !v5 )
      {
        v7 = &this->m_StopEvent.Header.WaitListHead.Blink;
        if ( this != (CKsPin *)-1008LL )
        {
          do
          {
            if ( _InterlockedIncrement((volatile signed __int32 *)v7) != 1 )
              break;
            v7 = (struct _LIST_ENTRY **)v7[1];
          }
          while ( v7 );
        }
      }
      if ( _InterlockedCompareExchange((volatile signed __int32 *)&this->m_StopEvent.Header.WaitListHead.Blink, 0, 1) != 1 )
        goto LABEL_24;
      for ( i = *(_QWORD *)&this->m_AndGate.Count; i; i = *(_QWORD *)(i + 8) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)i, 0xFFFFFFFF) != 1 )
          break;
      }
    }
    _InterlockedExchange((volatile __int32 *)&this->m_HandshakeCallback, 0);
    v6 = ((__int64 (__fastcall *)(unsigned __int64 *))this->m_ProcessingWorker)(&this->m_Ext.EventList.SpinLock);
    if ( v6 < 0 || v6 == 259 )
      break;
LABEL_10:
    if ( *(_DWORD *)p_Blink )
      goto LABEL_11;
    if ( v5 )
      goto LABEL_24;
  }
  v9 = &this->m_StopEvent.Header.WaitListHead.Blink;
  if ( this != (CKsPin *)-1008LL )
  {
    do
    {
      if ( _InterlockedIncrement((volatile signed __int32 *)v9) != 1 )
        break;
      v9 = (struct _LIST_ENTRY **)v9[1];
    }
    while ( v9 );
  }
  if ( LODWORD(this->m_HandshakeCallback) )
  {
    v5 = 1;
    goto LABEL_10;
  }
LABEL_24:
  KeReleaseMutex((PRKMUTEX)&this->m_ProcessOnRelease, 0);
  while ( LODWORD(this->m_DispatchSetDeviceState) )
  {
    if ( _InterlockedCompareExchange((volatile signed __int32 *)&this->m_DispatchSetDeviceState, 0, 2) == 2 )
    {
      ((void (__fastcall *)(CKsPin *))this->TransferKsIrp)(this);
      return;
    }
  }
}

```

## disassembly

```asm
0x180003cb0  push    rsi
0x180003cb2  push    rdi
0x180003cb3  sub     rsp, 38h
0x180003cb7  mov     rdi, rcx
0x180003cba  lea     rax, WPP_RECORDER_INITIALIZED
0x180003cc1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180003cc8  jz      short loc_180003CDC
0x180003cca  mov     rcx, cs:WPP_GLOBAL_Control
0x180003cd1  cmp     word ptr [rcx+48h], 0
0x180003cd6  jnz     loc_180003EF3
0x180003cdc  mov     [rsp+48h+var_18], r14
0x180003ce1  call    cs:__imp_KeGetCurrentIrql
0x180003ce8  nop     dword ptr [rax+rax+00h]
0x180003ced  lea     rcx, [rdi+480h]; Mutex
0x180003cf4  test    al, al
0x180003cf6  jnz     loc_180003E4C
0x180003cfc  xor     r14d, r14d
0x180003cff  xor     r9d, r9d; Alertable
0x180003d02  xor     r8d, r8d; WaitMode
0x180003d05  mov     [rsp+48h+Timeout], r14; Timeout
0x180003d0a  xor     edx, edx; WaitReason
0x180003d0c  call    cs:__imp_KeWaitForSingleObject
0x180003d13  nop     dword ptr [rax+rax+00h]
0x180003d18  mov     [rsp+48h+arg_0], rbx
0x180003d1d  mov     [rsp+48h+arg_10], rbp
0x180003d22  lea     rbp, [rdi+3F0h]
0x180003d29  xor     bl, bl
0x180003d2b  cmp     dword ptr [rbp+0], 0
0x180003d2f  jnz     short loc_180003D6A
0x180003d31  mov     eax, r14d
0x180003d34  lea     rcx, [rdi+0F8h]
0x180003d3b  xchg    eax, [rdi+4C0h]
0x180003d41  mov     rax, [rdi+450h]
0x180003d48  call    _guard_dispatch_icall
0x180003d4d  test    eax, eax
0x180003d4f  js      loc_180003DE0
0x180003d55  cmp     eax, 103h
0x180003d5a  jz      loc_180003DE0
0x180003d60  cmp     dword ptr [rbp+0], 0
0x180003d64  jz      loc_180003E9F
0x180003d6a  test    bl, bl
0x180003d6c  jnz     short loc_180003D99
0x180003d6e  lea     rax, [rdi+3F0h]
0x180003d75  test    rax, rax
0x180003d78  jz      short loc_180003D99
0x180003d7a  nop     word ptr [rax+rax+00h]
0x180003d80  mov     ecx, 1
0x180003d85  lock xadd [rax], ecx
0x180003d89  inc     ecx
0x180003d8b  cmp     ecx, 1
0x180003d8e  jnz     short loc_180003D99
0x180003d90  mov     rax, [rax+8]
0x180003d94  test    rax, rax
0x180003d97  jnz     short loc_180003D80
0x180003d99  mov     eax, 1
0x180003d9e  lock cmpxchg [rdi+3F0h], r14d
0x180003da7  jnz     short loc_180003E16
0x180003da9  mov     rcx, [rdi+3F8h]
0x180003db0  test    rcx, rcx
0x180003db3  jz      loc_180003D29
0x180003db9  nop     dword ptr [rax+00000000h]
0x180003dc0  mov     eax, 0FFFFFFFFh
0x180003dc5  lock xadd [rcx], eax
0x180003dc9  cmp     eax, 1
0x180003dcc  jnz     loc_180003D29
0x180003dd2  mov     rcx, [rcx+8]
0x180003dd6  test    rcx, rcx
0x180003dd9  jnz     short loc_180003DC0
0x180003ddb  jmp     loc_180003D29
0x180003de0  mov     rcx, rbp
0x180003de3  test    rbp, rbp
0x180003de6  jz      short loc_180003E09
0x180003de8  nop     dword ptr [rax+rax+00000000h]
0x180003df0  mov     eax, 1
0x180003df5  lock xadd [rcx], eax
0x180003df9  inc     eax
0x180003dfb  cmp     eax, 1
0x180003dfe  jnz     short loc_180003E09
0x180003e00  mov     rcx, [rcx+8]
0x180003e04  test    rcx, rcx
0x180003e07  jnz     short loc_180003DF0
0x180003e09  cmp     dword ptr [rdi+4C0h], 0
0x180003e10  jnz     loc_180003EAC
0x180003e16  xor     edx, edx; Wait
0x180003e18  lea     rcx, [rdi+480h]; Mutex
0x180003e1f  call    cs:__imp_KeReleaseMutex
0x180003e26  nop     dword ptr [rax+rax+00h]
0x180003e2b  mov     rbp, [rsp+48h+arg_10]
0x180003e30  mov     rbx, [rsp+48h+arg_0]
0x180003e35  mov     eax, [rdi+478h]
0x180003e3b  test    eax, eax
0x180003e3d  jnz     short loc_180003E7E
0x180003e3f  mov     r14, [rsp+48h+var_18]
0x180003e44  add     rsp, 38h
0x180003e48  pop     rdi
0x180003e49  pop     rsi
0x180003e4a  retn
0x180003e4c  mov     dword ptr [rdi+478h], 1
0x180003e56  call    cs:__imp_KeReadStateMutex
0x180003e5d  nop     dword ptr [rax+rax+00h]
0x180003e62  cmp     eax, 1
0x180003e65  jz      short loc_180003EB3
0x180003e67  mov     r14, [rsp+48h+var_18]
0x180003e6c  mov     dword ptr [rdi+478h], 2
0x180003e76  add     rsp, 38h
0x180003e7a  pop     rdi
0x180003e7b  pop     rsi
0x180003e7c  retn
0x180003e7e  mov     eax, 2
0x180003e83  lock cmpxchg [rdi+478h], r14d
0x180003e8c  jnz     short loc_180003E35
0x180003e8e  mov     rax, [rdi]
0x180003e91  mov     rcx, rdi
0x180003e94  mov     rax, [rax+18h]
0x180003e98  call    _guard_dispatch_icall
0x180003e9d  jmp     short loc_180003E3F
0x180003e9f  test    bl, bl
0x180003ea1  jnz     loc_180003E16
0x180003ea7  jmp     loc_180003D29
0x180003eac  mov     bl, 1
0x180003eae  jmp     loc_180003D60
0x180003eb3  lea     rax, [rsp+48h+arg_8]
0x180003eb8  xor     r14d, r14d
0x180003ebb  xor     r9d, r9d; Alertable
0x180003ebe  mov     qword ptr [rsp+48h+arg_8], r14
0x180003ec3  xor     r8d, r8d; WaitMode
0x180003ec6  mov     [rsp+48h+Timeout], rax; Timeout
0x180003ecb  xor     edx, edx; WaitReason
0x180003ecd  lea     rcx, [rdi+480h]; Object
0x180003ed4  call    cs:__imp_KeWaitForSingleObject
0x180003edb  nop     dword ptr [rax+rax+00h]
0x180003ee0  cmp     eax, 102h
0x180003ee5  jz      short loc_180003E67
0x180003ee7  mov     [rdi+478h], r14d
0x180003eee  jmp     loc_180003D18
0x180003ef3  mov     rcx, [rcx+40h]
0x180003ef7  lea     rax, WPP_9505c27395793143ec5446714e36088f_Traceguids
0x180003efe  mov     r9d, 0A8h
0x180003f04  mov     [rsp+48h+Timeout], rax
0x180003f09  mov     r8d, 1
0x180003f0f  mov     dl, 5
0x180003f11  call    WPP_RECORDER_SF_
0x180003f16  jmp     loc_180003CDC
```
