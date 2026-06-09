# P<CImpersonate>::~P<CImpersonate>(void)

- ea: `0x18001adf4`
- end: `0x18001ae15`
- name: `??1?$P@VCImpersonate@@@@QEAA@XZ`
- size: `33`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18001b240`
- `0x18001f3e0`
- `0x18001f5c0`
- `0x18001fa40`
- `0x180030339`
- `0x180030393`
- `0x1800303b7`
- `0x1800303ff`
- `0x180030df0`

## callees

- `0x18001adf4`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall P<CImpersonate>::~P<CImpersonate>(__int64 (__fastcall ****a1)(_QWORD, __int64))
{
  __int64 (__fastcall ***v1)(_QWORD, __int64); // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (**v1)(v1, 1);
  return result;
}

```

## disassembly

```asm
0x18001adf4  sub     rsp, 28h
0x18001adf8  mov     rcx, [rcx]
0x18001adfb  test    rcx, rcx
0x18001adfe  jz      short loc_18001AE10
0x18001ae00  mov     rax, [rcx]
0x18001ae03  mov     edx, 1
0x18001ae08  mov     rax, [rax]
0x18001ae0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae10  add     rsp, 28h
0x18001ae14  retn
```
