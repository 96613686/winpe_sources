# ATL::CComCriticalSection::Init(void)

- ea: `0x1800044cc`
- end: `0x1800044ec`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001600`
- `0x180001660`
- `0x180001720`
- `0x180007860`
- `0x18000a2f4`
- `0x1800168d8`
- `0x1800169d0`

## callees

- `0x1800044cc`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x1800044d0`
- `KERNEL32!InitializeCriticalSection` at `0x1800044d0`

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
0x1800044cc  sub     rsp, 38h
0x1800044d0  call    cs:__imp_InitializeCriticalSection
0x1800044d6  xor     eax, eax
0x1800044d8  mov     [rsp+38h+var_18], eax
0x1800044dc  jmp     short loc_1800044E7
0x1800044de  mov     eax, 8007000Eh
0x1800044e3  mov     [rsp+38h+var_18], eax
0x1800044e7  add     rsp, 38h
0x1800044eb  retn
```
