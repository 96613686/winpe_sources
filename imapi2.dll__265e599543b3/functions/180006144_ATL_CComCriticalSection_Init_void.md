# ATL::CComCriticalSection::Init(void)

- ea: `0x180006144`
- end: `0x180006164`
- name: `?Init@CComCriticalSection@ATL@@QEAAJXZ`
- size: `32`
- prototype: `__int64 __fastcall(ATL::CComCriticalSection *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180005990`
- `0x180005fa4`
- `0x180006050`
- `0x1800060b0`
- `0x18000eec0`
- `0x1800168d4`

## callees

- `0x180006144`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180006148`
- `KERNEL32!InitializeCriticalSection` at `0x180006148`

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
0x180006144  sub     rsp, 38h
0x180006148  call    cs:__imp_InitializeCriticalSection
0x18000614e  xor     eax, eax
0x180006150  mov     [rsp+38h+var_18], eax
0x180006154  jmp     short loc_18000615F
0x180006156  mov     eax, 8007000Eh
0x18000615b  mov     [rsp+38h+var_18], eax
0x18000615f  add     rsp, 38h
0x180006163  retn
0x1800499ff  push    rbp
0x180049a01  sub     rsp, 20h
0x180049a05  mov     rbp, rdx
0x180049a08  mov     rax, [rcx]
0x180049a0b  xor     ecx, ecx
0x180049a0d  cmp     dword ptr [rax], 0C0000017h
0x180049a13  setz    cl
0x180049a16  mov     eax, ecx
0x180049a18  add     rsp, 20h
0x180049a1c  pop     rbp
0x180049a1d  retn
```
