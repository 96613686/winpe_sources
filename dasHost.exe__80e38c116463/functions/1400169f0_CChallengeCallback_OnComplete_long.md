# CChallengeCallback::OnComplete(long)

- ea: `0x1400169f0`
- end: `0x140016a4b`
- name: `?OnComplete@CChallengeCallback@@UEAAJJ@Z`
- size: `91`
- prototype: `__int64 __fastcall(CChallengeCallback *this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140009328`
- `0x1400169f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140016a33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140016a33`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140016a08`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140016a08`

## pseudocode

```c
__int64 __fastcall CChallengeCallback::OnComplete(CChallengeCallback *this, int a2)
{
  int v4; // r8d
  RTL_SRWLOCK *v5; // rcx
  unsigned int v6; // ebx

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v5 = (RTL_SRWLOCK *)*((_QWORD *)this + 5);
  if ( v5 )
  {
    v6 = DevicePresenceChallengeOnCompleteStub(v5, a2, v4);
    *((_QWORD *)this + 5) = 0;
  }
  else
  {
    v6 = -2147467259;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  return v6;
}

```

## disassembly

```asm
0x1400169f0  mov     [rsp+arg_0], rbx
0x1400169f5  mov     [rsp+arg_8], rsi
0x1400169fa  push    rdi
0x1400169fb  sub     rsp, 20h
0x1400169ff  mov     rsi, rcx
0x140016a02  mov     ebx, edx
0x140016a04  add     rcx, 30h ; '0'; lpCriticalSection
0x140016a08  call    cs:__imp_EnterCriticalSection
0x140016a0e  mov     rcx, [rsi+28h]; void *
0x140016a12  test    rcx, rcx
0x140016a15  jz      short loc_140016A2A
0x140016a17  mov     edx, ebx; int
0x140016a19  call    ?DevicePresenceChallengeOnCompleteStub@@YAJPEAXJ@Z; DevicePresenceChallengeOnCompleteStub(void *,long)
0x140016a1e  mov     ebx, eax
0x140016a20  mov     qword ptr [rsi+28h], 0
0x140016a28  jmp     short loc_140016A2F
0x140016a2a  mov     ebx, 80004005h
0x140016a2f  lea     rcx, [rsi+30h]; lpCriticalSection
0x140016a33  call    cs:__imp_LeaveCriticalSection
0x140016a39  mov     rsi, [rsp+28h+arg_8]
0x140016a3e  mov     eax, ebx
0x140016a40  mov     rbx, [rsp+28h+arg_0]
0x140016a45  add     rsp, 20h
0x140016a49  pop     rdi
0x140016a4a  retn
```
