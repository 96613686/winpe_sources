# ATL::CComCriticalSection::Init(void)

- ea: `0x18000a510`
- end: `0x18000a537`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `39`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001800`

## callees

- `0x18000a510`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000a51b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000a51b`

## pseudocode

```c
__int64 __fastcall ATL::CComCriticalSection::Init(ATL::CComCriticalSection *this)
{
  InitializeCriticalSection(&stru_1800186B0);
  return 0;
}

```

## disassembly

```asm
0x18000a510  sub     rsp, 38h
0x18000a514  lea     rcx, stru_1800186B0; lpCriticalSection
0x18000a51b  call    cs:__imp_InitializeCriticalSection
0x18000a521  xor     eax, eax
0x18000a523  mov     [rsp+38h+var_18], eax
0x18000a527  jmp     short loc_18000A532
0x18000a529  mov     eax, 8007000Eh
0x18000a52e  mov     [rsp+38h+var_18], eax
0x18000a532  add     rsp, 38h
0x18000a536  retn
```
