# wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)

- ea: `0x1800110bc`
- end: `0x1800110db`
- name: `??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ`
- size: `31`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `53`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012d80`
- `0x1800228c8`
- `0x1800228ec`
- `0x18002293c`
- `0x1800229fc`
- `0x180022b90`
- `0x180022ee0`
- `0x180023010`
- `0x1800234b8`
- `0x1800237f8`
- `0x180023be8`
- `0x18002412c`
- `0x180024260`
- `0x180024570`
- `0x1800249d0`
- `0x180024fd0`
- `0x180025090`
- `0x1800253a0`
- `0x1800255dc`
- `0x1800259b0`
- `0x180025be0`
- `0x180025c40`
- `0x180025ea0`
- `0x180026210`
- `0x180026480`
- `0x180026854`
- `0x180026a20`
- `0x180026c80`
- `0x1800270b0`
- `0x1800271a8`
- `0x180027230`
- `0x180027550`
- `0x1800278c0`
- `0x180027ce0`
- `0x1800280c0`
- `0x180028190`
- `0x1800285c8`
- `0x1800287f0`
- `0x18002882c`
- `0x180028a50`
- `0x180028b20`
- `0x180029098`
- `0x180029240`
- `0x18002aadc`
- `0x18002abf0`
- `0x18002ca78`
- `0x18002d240`
- `0x18002d6bc`
- `0x18002d810`
- `0x18002eb50`

## callees

- `0x1800110bc`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(
        __int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x1800110bc  sub     rsp, 28h
0x1800110c0  mov     rcx, [rcx]
0x1800110c3  test    rcx, rcx
0x1800110c6  jz      short loc_1800110D5
0x1800110c8  mov     rax, [rcx]
0x1800110cb  mov     rax, [rax+10h]
0x1800110cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110d4  nop
0x1800110d5  add     rsp, 28h
0x1800110d9  retn
```
