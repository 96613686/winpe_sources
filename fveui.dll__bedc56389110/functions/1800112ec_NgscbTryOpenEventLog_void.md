# NgscbTryOpenEventLog(void)

- ea: `0x1800112ec`
- end: `0x18001138a`
- name: `?NgscbTryOpenEventLog@@YAXXZ`
- size: `158`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000fbc0`

## callees

- `0x1800037a0`
- `0x1800112ec`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001137f`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001137f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180011300`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180011300`
- `ADVAPI32!EventRegister` at `0x180011321`
- `ADVAPI32!EventRegister` at `0x180011321`

## pseudocode

```c
void NgscbTryOpenEventLog(void)
{
  ULONG v0; // eax
  ULONGLONG RegHandle; // [rsp+30h] [rbp+8h] BYREF

  RegHandle = 0;
  AcquireSRWLockExclusive(&g_FveApiProviderEvtLock);
  if ( !g_FveApiProviderRefCount )
  {
    v0 = EventRegister(&FVEAPI_Provider, 0, 0, &RegHandle);
    if ( v0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_fdbaa957ea32373b347160d97d74c1eb_Traceguids, v0);
    }
    else
    {
      g_HstiEventLog = RegHandle;
    }
  }
  ++g_FveApiProviderRefCount;
  ReleaseSRWLockExclusive(&g_FveApiProviderEvtLock);
}

```

## disassembly

```asm
0x1800112ec  sub     rsp, 28h
0x1800112f0  lea     rcx, ?g_FveApiProviderEvtLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x1800112f7  mov     [rsp+28h+RegHandle], 0
0x180011300  call    cs:__imp_AcquireSRWLockExclusive
0x180011306  mov     eax, cs:?g_FveApiProviderRefCount@@3KC; ulong volatile g_FveApiProviderRefCount
0x18001130c  test    eax, eax
0x18001130e  jnz     short loc_18001136A
0x180011310  lea     r9, [rsp+28h+RegHandle]; RegHandle
0x180011315  xor     r8d, r8d; CallbackContext
0x180011318  xor     edx, edx; EnableCallback
0x18001131a  lea     rcx, FVEAPI_Provider; ProviderId
0x180011321  call    cs:__imp_EventRegister
0x180011327  test    eax, eax
0x180011329  jz      short loc_18001135E
0x18001132b  mov     rcx, cs:WPP_GLOBAL_Control
0x180011332  lea     rdx, WPP_GLOBAL_Control
0x180011339  cmp     rcx, rdx
0x18001133c  jz      short loc_18001136A
0x18001133e  test    byte ptr [rcx+1Ch], 2
0x180011342  jz      short loc_18001136A
0x180011344  mov     rcx, [rcx+10h]
0x180011348  lea     r8, WPP_fdbaa957ea32373b347160d97d74c1eb_Traceguids
0x18001134f  mov     edx, 0Ah
0x180011354  mov     r9d, eax
0x180011357  call    WPP_SF_d
0x18001135c  jmp     short loc_18001136A
0x18001135e  mov     rax, [rsp+28h+RegHandle]
0x180011363  mov     cs:?g_HstiEventLog@@3_KA, rax; unsigned __int64 g_HstiEventLog
0x18001136a  mov     eax, cs:?g_FveApiProviderRefCount@@3KC; ulong volatile g_FveApiProviderRefCount
0x180011370  lea     rcx, ?g_FveApiProviderEvtLock@@3U_RTL_SRWLOCK@@A; SRWLock
0x180011377  inc     eax
0x180011379  mov     cs:?g_FveApiProviderRefCount@@3KC, eax; ulong volatile g_FveApiProviderRefCount
0x18001137f  call    cs:__imp_ReleaseSRWLockExclusive
0x180011385  add     rsp, 28h
0x180011389  retn
```
