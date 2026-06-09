# ATL::CComCriticalSection::Init(void)

- ea: `0x1800058fc`
- end: `0x18000591c`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `15`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800016e0`
- `0x1800017a0`
- `0x1800017e0`
- `0x180001820`
- `0x180006c60`
- `0x180011fb8`
- `0x180012114`
- `0x180012260`
- `0x180012384`
- `0x1800124a4`
- `0x1800125e4`
- `0x180012704`
- `0x18001281c`
- `0x18001295c`
- `0x180012cc0`

## callees

- `0x1800058fc`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180005900`
- `KERNEL32!InitializeCriticalSection` at `0x180005900`

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
0x1800058fc  sub     rsp, 38h
0x180005900  call    cs:__imp_InitializeCriticalSection
0x180005906  xor     eax, eax
0x180005908  mov     [rsp+38h+var_18], eax
0x18000590c  jmp     short loc_180005917
0x18000590e  mov     eax, 8007000Eh
0x180005913  mov     [rsp+38h+var_18], eax
0x180005917  add     rsp, 38h
0x18000591b  retn
```
