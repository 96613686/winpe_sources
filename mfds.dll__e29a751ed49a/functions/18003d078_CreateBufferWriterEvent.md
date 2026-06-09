# CreateBufferWriterEvent

- ea: `0x18003d078`
- end: `0x18003d184`
- name: `CreateBufferWriterEvent`
- size: `268`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180050be0`

## callees

- `0x18003d078`
- `0x18003d18c`
- `0x18003d22c`
- `0x180074160`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18003d140`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18003d140`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003d10f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003d10f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d123`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d123`

## pseudocode

```c
HANDLE CreateBufferWriterEvent()
{
  HANDLE EventW; // rbx
  _QWORD v2[5]; // [rsp+20h] [rbp-19h] BYREF
  LPSECURITY_ATTRIBUTES lpEventAttributes; // [rsp+48h] [rbp+Fh]
  __int64 v4; // [rsp+50h] [rbp+17h]
  char v5; // [rsp+58h] [rbp+1Fh]
  __int128 v6; // [rsp+60h] [rbp+27h]
  int v7; // [rsp+70h] [rbp+37h]
  int v8; // [rsp+74h] [rbp+3Bh]
  int v9; // [rsp+78h] [rbp+3Fh]
  int v10; // [rsp+7Ch] [rbp+43h]

  v2[1] = 0;
  v6 = 0;
  v2[0] = &Mp2DemuxSec::CWriteEventSec::`vftable';
  lpEventAttributes = 0;
  v4 = 0;
  v5 = 0;
  v7 = 11;
  v8 = 18;
  v9 = 19;
  v10 = 20;
  Mp2DemuxSec::CDemuxSec::CreateSids((Mp2DemuxSec::CDemuxSec *)v2);
  (*(void (__fastcall **)(_QWORD *))(v2[0] + 32LL))(v2);
  EventW = CreateEventW(lpEventAttributes, 1, 0, L"Global\\DmCapToggle");
  if ( !EventW && GetLastError() == 5 )
    EventW = OpenEventW(2u, 0, L"Global\\DmCapToggle");
  v2[0] = &Mp2DemuxSec::CDemuxDiagnosticsSec::`vftable';
  Mp2DemuxSec::CDemuxSec::~CDemuxSec((Mp2DemuxSec::CDemuxSec *)v2);
  return EventW;
}

```

## disassembly

```asm
0x18003d078  mov     [rsp-8+arg_0], rbx
0x18003d07d  push    rbp
0x18003d07e  lea     rbp, [rsp-57h]
0x18003d083  sub     rsp, 90h
0x18003d08a  mov     rax, cs:__security_cookie
0x18003d091  xor     rax, rsp
0x18003d094  mov     [rbp+57h+var_10], rax
0x18003d098  xorps   xmm0, xmm0
0x18003d09b  mov     [rbp+57h+var_68], 0
0x18003d0a3  lea     rax, ??_7CWriteEventSec@Mp2DemuxSec@@6B@; const Mp2DemuxSec::CWriteEventSec::`vftable'
0x18003d0aa  movdqa  [rbp+57h+var_30], xmm0
0x18003d0af  lea     rcx, [rbp+57h+var_70]; this
0x18003d0b3  mov     [rbp+57h+var_70], rax
0x18003d0b7  mov     [rbp+57h+lpEventAttributes], 0
0x18003d0bf  mov     [rbp+57h+var_40], 0
0x18003d0c7  mov     [rbp+57h+var_38], 0
0x18003d0cb  mov     [rbp+57h+var_20], 0Bh
0x18003d0d2  mov     [rbp+57h+var_1C], 12h
0x18003d0d9  mov     [rbp+57h+var_18], 13h
0x18003d0e0  mov     [rbp+57h+var_14], 14h
0x18003d0e7  call    ?CreateSids@CDemuxSec@Mp2DemuxSec@@AEAAJXZ; Mp2DemuxSec::CDemuxSec::CreateSids(void)
0x18003d0ec  mov     rax, [rbp+57h+var_70]
0x18003d0f0  lea     rcx, [rbp+57h+var_70]
0x18003d0f4  mov     rax, [rax+20h]
0x18003d0f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d0fd  mov     rcx, [rbp+57h+lpEventAttributes]; lpEventAttributes
0x18003d101  lea     r9, Name; "Global\\DmCapToggle"
0x18003d108  xor     r8d, r8d; bInitialState
0x18003d10b  lea     edx, [r8+1]; bManualReset
0x18003d10f  call    cs:__imp_CreateEventW
0x18003d116  nop     dword ptr [rax+rax+00h]
0x18003d11b  mov     rbx, rax
0x18003d11e  test    rax, rax
0x18003d121  jnz     short loc_18003D14F
0x18003d123  call    cs:__imp_GetLastError
0x18003d12a  nop     dword ptr [rax+rax+00h]
0x18003d12f  cmp     eax, 5
0x18003d132  jnz     short loc_18003D14F
0x18003d134  lea     r8, Name; "Global\\DmCapToggle"
0x18003d13b  xor     edx, edx; bInheritHandle
0x18003d13d  lea     ecx, [rbx+2]; dwDesiredAccess
0x18003d140  call    cs:__imp_OpenEventW
0x18003d147  nop     dword ptr [rax+rax+00h]
0x18003d14c  mov     rbx, rax
0x18003d14f  lea     rax, ??_7CDemuxDiagnosticsSec@Mp2DemuxSec@@6B@; const Mp2DemuxSec::CDemuxDiagnosticsSec::`vftable'
0x18003d156  lea     rcx, [rbp+57h+var_70]; this
0x18003d15a  mov     [rbp+57h+var_70], rax
0x18003d15e  call    ??1CDemuxSec@Mp2DemuxSec@@UEAA@XZ; Mp2DemuxSec::CDemuxSec::~CDemuxSec(void)
0x18003d163  mov     rax, rbx
0x18003d166  mov     rcx, [rbp+57h+var_10]
0x18003d16a  xor     rcx, rsp; StackCookie
0x18003d16d  call    __security_check_cookie
0x18003d172  mov     rbx, [rsp+90h+arg_0]
0x18003d17a  add     rsp, 90h
0x18003d181  pop     rbp
0x18003d182  retn
```
