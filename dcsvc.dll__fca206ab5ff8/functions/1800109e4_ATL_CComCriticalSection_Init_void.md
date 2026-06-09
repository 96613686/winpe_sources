# ATL::CComCriticalSection::Init(void)

- ea: `0x1800109e4`
- end: `0x180010a0b`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `39`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800018c0`

## callees

- `0x1800109e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800109ef`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800109ef`

## pseudocode

```c
__int64 __fastcall ATL::CComCriticalSection::Init(ATL::CComCriticalSection *this)
{
  InitializeCriticalSection(&g_csCmRecoveryApi);
  return 0;
}

```

## disassembly

```asm
0x1800109e4  sub     rsp, 38h
0x1800109e8  lea     rcx, ?g_csCmRecoveryApi@@3VCComAutoCriticalSection@ATL@@A; lpCriticalSection
0x1800109ef  call    cs:__imp_InitializeCriticalSection
0x1800109f5  xor     eax, eax
0x1800109f7  mov     [rsp+38h+var_18], eax
0x1800109fb  jmp     short loc_180010A06
0x1800109fd  mov     eax, 8007000Eh
0x180010a02  mov     [rsp+38h+var_18], eax
0x180010a06  add     rsp, 38h
0x180010a0a  retn
```
