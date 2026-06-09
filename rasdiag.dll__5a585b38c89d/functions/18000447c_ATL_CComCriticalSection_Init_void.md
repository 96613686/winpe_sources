# ATL::CComCriticalSection::Init(void)

- ea: `0x18000447c`
- end: `0x1800044a3`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `39`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001070`
- `0x180001110`
- `0x180001150`
- `0x180001190`
- `0x18000596c`
- `0x1800063dc`
- `0x1800065e0`
- `0x18000837c`
- `0x180009b6c`
- `0x18000aafc`

## callees

- `0x18000447c`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180004480`
- `KERNEL32!InitializeCriticalSection` at `0x180004480`

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
0x18000447c  sub     rsp, 38h
0x180004480  call    cs:__imp_InitializeCriticalSection
0x180004487  nop     dword ptr [rax+rax+00h]
0x18000448c  xor     eax, eax
0x18000448e  mov     [rsp+38h+var_18], eax
0x180004492  jmp     short loc_18000449D
0x180004494  mov     eax, 8007000Eh
0x180004499  mov     [rsp+38h+var_18], eax
0x18000449d  add     rsp, 38h
0x1800044a1  retn
```
