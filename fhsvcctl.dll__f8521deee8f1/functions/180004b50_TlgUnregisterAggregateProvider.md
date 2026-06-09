# TlgUnregisterAggregateProvider

- ea: `0x180004b50`
- end: `0x180004c8b`
- name: `TlgUnregisterAggregateProvider`
- size: `315`
- prototype: `ULONG()`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800020c0`

## callees

- `0x180003bdc`
- `0x18000444c`
- `0x180004b50`

## import_xrefs

- `ADVAPI32!EventUnregister` at `0x180004be4`
- `ADVAPI32!EventUnregister` at `0x180004c58`
- `ADVAPI32!EventUnregister` at `0x180004c7f`
- `ADVAPI32!EventUnregister` at `0x180004be4`
- `ADVAPI32!EventUnregister` at `0x180004c58`
- `ADVAPI32!EventUnregister` at `0x180004c7f`
- `KERNEL32!HeapFree` at `0x180004c19`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180004bb5`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180004bb5`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180004b71`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180004b71`
- `KERNEL32!GetProcessHeap` at `0x180004c06`
- `KERNEL32!GetProcessHeap` at `0x180004c06`

## pseudocode

```c
ULONG TlgUnregisterAggregateProvider()
{
  __int64 v0; // r8
  __int64 v1; // r9
  __int64 v2; // rdi
  __int64 *v3; // rcx
  __int64 *v4; // rax
  REGHANDLE v5; // rcx
  ULONG result; // eax
  HANDLE ProcessHeap; // rax
  REGHANDLE v8; // rcx
  REGHANDLE v9; // rcx

  if ( (void (__fastcall *)(const struct _GUID *, __int64, char, __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, _QWORD *))qword_18000A030 == TlgAggregateInternalRegisteredProviderEtwCallback )
  {
    AcquireSRWLockExclusive(&SRWLock);
    v2 = qword_18000A730;
    if ( qword_18000A730 )
    {
      v3 = &qword_18000A730;
      while ( 1 )
      {
        v4 = (__int64 *)(v2 + 336);
        if ( *(int **)(v2 + 328) == &dword_18000A008 )
          break;
        v2 = *v4;
        v3 = v4;
        if ( !*v4 )
          goto LABEL_6;
      }
      *v3 = *v4;
      LookUpTableFlushComplete((const __m128i *)v2, (__int64)&dword_18000A008, v0, v1);
      if ( !qword_18000A730 )
      {
        v8 = qword_18000A060;
        dword_18000A040 = 0;
        qword_18000A060 = 0;
        EventUnregister(v8);
      }
    }
    else
    {
LABEL_6:
      v2 = 0;
    }
    ReleaseSRWLockExclusive(&SRWLock);
    if ( v2 )
      CancelTimerCallbacksAndDeleteTimer(v2);
    v5 = RegHandle;
    dword_18000A008 = 0;
    RegHandle = 0;
    result = EventUnregister(v5);
    qword_18000A030 = 0;
    if ( v2 )
    {
      CancelTimerCallbacksAndDeleteTimer(v2);
      ProcessHeap = GetProcessHeap();
      return HeapFree(ProcessHeap, 0, (LPVOID)v2);
    }
  }
  else
  {
    v9 = RegHandle;
    dword_18000A008 = 0;
    RegHandle = 0;
    return EventUnregister(v9);
  }
  return result;
}

```

## disassembly

```asm
0x180004b50  push    rdi
0x180004b52  sub     rsp, 20h
0x180004b56  lea     rax, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x180004b5d  cmp     cs:qword_18000A030, rax
0x180004b64  jnz     loc_180004C63
0x180004b6a  lea     rcx, SRWLock; SRWLock
0x180004b71  call    cs:__imp_AcquireSRWLockExclusive
0x180004b77  mov     rdi, cs:qword_18000A730
0x180004b7e  test    rdi, rdi
0x180004b81  jz      short loc_180004BAC
0x180004b83  lea     rcx, qword_18000A730
0x180004b8a  lea     rdx, dword_18000A008
0x180004b91  lea     rax, [rdi+150h]
0x180004b98  cmp     [rdi+148h], rdx
0x180004b9f  jz      short loc_180004C20
0x180004ba1  mov     rdi, [rax]
0x180004ba4  mov     rcx, rax
0x180004ba7  test    rdi, rdi
0x180004baa  jnz     short loc_180004B8A
0x180004bac  xor     edi, edi
0x180004bae  lea     rcx, SRWLock; SRWLock
0x180004bb5  call    cs:__imp_ReleaseSRWLockExclusive
0x180004bbb  test    rdi, rdi
0x180004bbe  jz      short loc_180004BC8
0x180004bc0  mov     rcx, rdi
0x180004bc3  call    CancelTimerCallbacksAndDeleteTimer
0x180004bc8  mov     rcx, cs:RegHandle; RegHandle
0x180004bcf  mov     cs:dword_18000A008, 0
0x180004bd9  mov     cs:RegHandle, 0
0x180004be4  call    cs:__imp_EventUnregister
0x180004bea  mov     cs:qword_18000A030, 0
0x180004bf5  test    rdi, rdi
0x180004bf8  jz      loc_180004C85
0x180004bfe  mov     rcx, rdi
0x180004c01  call    CancelTimerCallbacksAndDeleteTimer
0x180004c06  call    cs:__imp_GetProcessHeap
0x180004c0c  mov     r8, rdi
0x180004c0f  xor     edx, edx
0x180004c11  mov     rcx, rax
0x180004c14  add     rsp, 20h
0x180004c18  pop     rdi
0x180004c19  jmp     cs:__imp_HeapFree
0x180004c20  mov     rax, [rax]
0x180004c23  mov     [rcx], rax
0x180004c26  mov     rcx, rdi
0x180004c29  call    LookUpTableFlushComplete
0x180004c2e  cmp     cs:qword_18000A730, 0
0x180004c36  jnz     loc_180004BAE
0x180004c3c  mov     rcx, cs:qword_18000A060; RegHandle
0x180004c43  mov     cs:dword_18000A040, 0
0x180004c4d  mov     cs:qword_18000A060, 0
0x180004c58  call    cs:__imp_EventUnregister
0x180004c5e  jmp     loc_180004BAE
0x180004c63  mov     rcx, cs:RegHandle; RegHandle
0x180004c6a  mov     cs:dword_18000A008, 0
0x180004c74  mov     cs:RegHandle, 0
0x180004c7f  call    cs:__imp_EventUnregister
0x180004c85  add     rsp, 20h
0x180004c89  pop     rdi
0x180004c8a  retn
```
