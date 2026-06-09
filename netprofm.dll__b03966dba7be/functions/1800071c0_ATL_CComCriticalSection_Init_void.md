# ATL::CComCriticalSection::Init(void)

- ea: `0x1800071c0`
- end: `0x1800071e0`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `11`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800016f0`
- `0x1800070a4`
- `0x180007138`
- `0x1800150c8`
- `0x180015104`
- `0x180017154`
- `0x180017254`
- `0x180017380`
- `0x180017464`
- `0x180017528`
- `0x180021dd0`

## callees

- `0x1800071c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800071c4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800071c4`

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
0x1800071c0  sub     rsp, 38h
0x1800071c4  call    cs:__imp_InitializeCriticalSection
0x1800071ca  xor     eax, eax
0x1800071cc  mov     [rsp+38h+var_18], eax
0x1800071d0  jmp     short loc_1800071DB
0x1800071d2  mov     eax, 8007000Eh
0x1800071d7  mov     [rsp+38h+var_18], eax
0x1800071db  add     rsp, 38h
0x1800071df  retn
```
