# DotConnectionCompleteAbort

- ea: `0x1800812c8`
- end: `0x1800813cb`
- name: `DotConnectionCompleteAbort`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800810f8`

## callees

- `0x180046494`
- `0x1800812c8`
- `0x180083954`
- `0x180089274`
- `0x1800a8bd0`
- `0x1800ddfa8`
- `0x1800dfa80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008131d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008131d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008134f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008134f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180081393`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x180081393`

## pseudocode

```c
void __fastcall DotConnectionCompleteAbort(__int64 a1)
{
  int v1; // ebp
  int v3; // esi
  _DWORD *v4; // rdi
  __int64 v5; // rcx
  __int64 v6; // rcx

  v1 = 0;
  v3 = 0;
  v4 = (_DWORD *)(a1 + 116);
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_qD(1035, 73, WPP_e56dd19b1cdc30a42d7776c3f5a09aa5_Traceguids, a1, *v4);
  if ( !*v4 || *v4 == 997 )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 248));
  if ( !*(_DWORD *)(a1 + 80) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v5);
  if ( *(_DWORD *)(a1 + 68) )
  {
    *(_DWORD *)(a1 + 68) = 0;
    v1 = 1;
  }
  if ( *(_DWORD *)(a1 + 76) )
  {
    *(_DWORD *)(a1 + 76) = 0;
    v3 = 1;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 248));
  if ( v1 )
    DotConnectionReleaseOwnRequestRef(a1);
  if ( v3 )
  {
    if ( *(_DWORD *)(a1 + 76) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v6);
    DeRefDnsWinhttpHandle(a1 + 232);
  }
  DotConnectionCleanupBlobs(a1);
  WaitForThreadpoolWorkCallbacks(*(PTP_WORK *)(a1 + 176), 0);
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_q(1035, 74, WPP_e56dd19b1cdc30a42d7776c3f5a09aa5_Traceguids, a1);
}

```

## disassembly

```asm
0x1800812c8  push    rbx
0x1800812ca  push    rbp
0x1800812cb  push    rsi
0x1800812cc  push    rdi
0x1800812cd  sub     rsp, 38h
0x1800812d1  xor     ebp, ebp
0x1800812d3  mov     rbx, rcx
0x1800812d6  xor     esi, esi
0x1800812d8  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800812df  lea     rdi, [rcx+74h]
0x1800812e3  jz      short loc_180081302
0x1800812e5  mov     eax, [rdi]
0x1800812e7  lea     edx, [rbp+49h]
0x1800812ea  mov     ecx, 40Bh
0x1800812ef  mov     [rsp+58h+var_38], eax
0x1800812f3  mov     r9, rbx
0x1800812f6  lea     r8, WPP_e56dd19b1cdc30a42d7776c3f5a09aa5_Traceguids
0x1800812fd  call    WPP_SF_qD
0x180081302  cmp     [rdi], esi
0x180081304  jz      short loc_18008130E
0x180081306  cmp     dword ptr [rdi], 3E5h
0x18008130c  jnz     short loc_180081313
0x18008130e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180081313  lea     rdi, [rbx+0F8h]
0x18008131a  mov     rcx, rdi; lpCriticalSection
0x18008131d  call    cs:__imp_EnterCriticalSection
0x180081324  nop     dword ptr [rax+rax+00h]
0x180081329  cmp     [rbx+50h], esi
0x18008132c  jnz     short loc_180081333
0x18008132e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180081333  mov     eax, 1
0x180081338  cmp     [rbx+44h], esi
0x18008133b  jz      short loc_180081342
0x18008133d  mov     [rbx+44h], esi
0x180081340  mov     ebp, eax
0x180081342  cmp     [rbx+4Ch], esi
0x180081345  jz      short loc_18008134C
0x180081347  mov     [rbx+4Ch], esi
0x18008134a  mov     esi, eax
0x18008134c  mov     rcx, rdi; lpCriticalSection
0x18008134f  call    cs:__imp_LeaveCriticalSection
0x180081356  nop     dword ptr [rax+rax+00h]
0x18008135b  test    ebp, ebp
0x18008135d  jz      short loc_180081367
0x18008135f  mov     rcx, rbx
0x180081362  call    DotConnectionReleaseOwnRequestRef
0x180081367  test    esi, esi
0x180081369  jz      short loc_180081382
0x18008136b  cmp     dword ptr [rbx+4Ch], 0
0x18008136f  jz      short loc_180081376
0x180081371  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180081376  lea     rcx, [rbx+0E8h]
0x18008137d  call    DeRefDnsWinhttpHandle
0x180081382  mov     rcx, rbx
0x180081385  call    DotConnectionCleanupBlobs
0x18008138a  mov     rcx, [rbx+0B0h]; pwk
0x180081391  xor     edx, edx; fCancelPendingCallbacks
0x180081393  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18008139a  nop     dword ptr [rax+rax+00h]
0x18008139f  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800813a6  jz      short loc_1800813C1
0x1800813a8  mov     edx, 4Ah ; 'J'
0x1800813ad  lea     r8, WPP_e56dd19b1cdc30a42d7776c3f5a09aa5_Traceguids
0x1800813b4  mov     ecx, 40Bh
0x1800813b9  mov     r9, rbx
0x1800813bc  call    WPP_SF_q
0x1800813c1  add     rsp, 38h
0x1800813c5  pop     rdi
0x1800813c6  pop     rsi
0x1800813c7  pop     rbp
0x1800813c8  pop     rbx
0x1800813c9  retn
```
