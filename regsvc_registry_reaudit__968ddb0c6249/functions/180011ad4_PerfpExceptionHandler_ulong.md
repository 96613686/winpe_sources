# PerfpExceptionHandler(ulong)

- ea: `0x180011ad4`
- end: `0x180011b02`
- name: `?PerfpExceptionHandler@@YAXK@Z`
- size: `46`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000fb6c`
- `0x180011d10`
- `0x18001335c`
- `0x1800136b0`

## callees

- `0x180007fd6`
- `0x180011ad4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011af7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180011af7`

## pseudocode

```c
void __fastcall PerfpExceptionHandler(int a1)
{
  if ( a1 == -1073741571 && !(unsigned int)o__resetstkoflw_0() )
    RaiseException(0xC00000FD, 1u, 0, 0);
}

```

## disassembly

```asm
0x180011ad4  sub     rsp, 28h
0x180011ad8  cmp     ecx, 0C00000FDh
0x180011ade  jnz     short loc_180011AFD
0x180011ae0  call    _o__resetstkoflw_0
0x180011ae5  test    eax, eax
0x180011ae7  jnz     short loc_180011AFD
0x180011ae9  xor     r9d, r9d; lpArguments
0x180011aec  lea     edx, [rax+1]; dwExceptionFlags
0x180011aef  xor     r8d, r8d; nNumberOfArguments
0x180011af2  mov     ecx, 0C00000FDh; dwExceptionCode
0x180011af7  call    cs:__imp_RaiseException
0x180011afd  add     rsp, 28h
0x180011b01  retn
```
