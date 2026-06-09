# ApplyTurn(IProvOperations *,_ProvToolCommandSettings const &)

- ea: `0x1400045c8`
- end: `0x1400045e7`
- name: `?ApplyTurn@@YAJPEAUIProvOperations@@AEBU_ProvToolCommandSettings@@@Z`
- size: `31`
- prototype: `__int64 __fastcall(struct IProvOperations *, const struct _ProvToolCommandSettings *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400059ac`

## callees

- `0x1400045c8`
- `0x140010010`

## pseudocode

```c
__int64 __fastcall ApplyTurn(struct IProvOperations *a1, const struct _ProvToolCommandSettings *a2)
{
  __int64 result; // rax
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  try
  {
    result = (*(__int64 (__fastcall **)(struct IProvOperations *))(*(_QWORD *)a1 + 64LL))(a1);
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x10A,
                           (unsigned int)"onecoreuap\\admin\\prov\\provtool\\provtool.cpp",
                           v3);
  }
  return result;
}

```

## disassembly

```asm
0x1400045c8  sub     rsp, 28h
0x1400045cc  mov     rax, [rcx]
0x1400045cf  mov     edx, [rdx+3Ch]
0x1400045d2  mov     rax, [rax+40h]
0x1400045d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400045db  jmp     short loc_1400045E1
0x1400045dd  mov     eax, [rsp+28h+arg_0]
0x1400045e1  add     rsp, 28h
0x1400045e5  retn
```
