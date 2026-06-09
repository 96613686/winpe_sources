# ATL::CComCriticalSection::Init(void)

- ea: `0x1800085ec`
- end: `0x180008613`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `39`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001150`
- `0x180001240`
- `0x180001310`
- `0x180024f28`

## callees

- `0x1800085ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800085f0`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800085f0`

## pseudocode

```c
__int64 __fastcall ATL::CComCriticalSection::Init(struct _RTL_CRITICAL_SECTION *this)
{
  InitializeCriticalSection(this);
  return 0;
}

```

## disassembly

```asm
0x1800085ec  sub     rsp, 38h
0x1800085f0  call    cs:__imp_InitializeCriticalSection
0x1800085f7  nop     dword ptr [rax+rax+00h]
0x1800085fc  xor     eax, eax
0x1800085fe  mov     [rsp+38h+var_18], eax
0x180008602  jmp     short loc_18000860D
0x180008604  mov     eax, 8007000Eh
0x180008609  mov     [rsp+38h+var_18], eax
0x18000860d  add     rsp, 38h
0x180008611  retn
```
