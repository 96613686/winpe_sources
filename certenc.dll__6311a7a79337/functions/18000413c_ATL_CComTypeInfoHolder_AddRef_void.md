# ATL::CComTypeInfoHolder::AddRef(void)

- ea: `0x18000413c`
- end: `0x180004168`
- name: `?AddRef@CComTypeInfoHolder@ATL@@QEAAXXZ`
- size: `44`
- prototype: `void __fastcall(ATL::CComTypeInfoHolder *__hidden this)`
- caller_count: `6`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800069b0`
- `0x180006ac0`
- `0x180006bc0`
- `0x180006cd0`
- `0x180006dd0`
- `0x180006ed0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004161`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000414c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000414c`

## pseudocode

```c
void __fastcall ATL::CComTypeInfoHolder::AddRef(ATL::CComTypeInfoHolder *this)
{
  EnterCriticalSection(&CriticalSection);
  ++*((_DWORD *)this + 8);
  LeaveCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x18000413c  push    rbx
0x18000413e  sub     rsp, 20h
0x180004142  mov     rbx, rcx
0x180004145  lea     rcx, CriticalSection; lpCriticalSection
0x18000414c  call    cs:__imp_EnterCriticalSection
0x180004152  inc     dword ptr [rbx+20h]
0x180004155  lea     rcx, CriticalSection
0x18000415c  add     rsp, 20h
0x180004160  pop     rbx
0x180004161  jmp     cs:__imp_LeaveCriticalSection
```
