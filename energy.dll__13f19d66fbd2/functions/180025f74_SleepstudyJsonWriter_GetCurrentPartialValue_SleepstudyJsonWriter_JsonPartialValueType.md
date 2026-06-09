# SleepstudyJsonWriter::GetCurrentPartialValue(SleepstudyJsonWriter::JsonPartialValueType)

- ea: `0x180025f74`
- end: `0x180025fc2`
- name: `?GetCurrentPartialValue@SleepstudyJsonWriter@@AEAAAEAUJsonPartialValue@1@W4JsonPartialValueType@1@@Z`
- size: `78`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800256d0`
- `0x180042f00`

## callees

- `0x180025f74`
- `0x18004a420`
- `0x1800907f0`

## import_xrefs

- `msvcp_win!?flush@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@XZ` at `0x180025f99`
- `msvcp_win!?flush@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@XZ` at `0x180025f99`

## string_xrefs

- `0x180025f9f`: `Attempted invalid operation in JSON stream.`

## pseudocode

```c
_DWORD *__fastcall SleepstudyJsonWriter::GetCurrentPartialValue(__int64 a1, int a2)
{
  __int64 v2; // rax
  _DWORD *result; // rax
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  v2 = *(_QWORD *)(a1 + 288);
  if ( *(_QWORD *)(a1 + 280) == v2 || (result = (_DWORD *)(v2 - 8), *result != a2) )
  {
    std::basic_ostream<unsigned short>::flush(a1 + 16);
    std::logic_error::logic_error((std::logic_error *)pExceptionObject, "Attempted invalid operation in JSON stream.");
    throw (std::logic_error *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x180025f74  sub     rsp, 48h
0x180025f78  mov     rax, [rcx+120h]
0x180025f7f  cmp     [rcx+118h], rax
0x180025f86  jz      short loc_180025F95
0x180025f88  add     rax, 0FFFFFFFFFFFFFFF8h
0x180025f8c  cmp     [rax], edx
0x180025f8e  jnz     short loc_180025F95
0x180025f90  add     rsp, 48h
0x180025f94  retn
0x180025f95  add     rcx, 10h
0x180025f99  call    cs:__imp_?flush@?$basic_ostream@GU?$char_traits@G@std@@@std@@QEAAAEAV12@XZ; std::basic_ostream<ushort>::flush(void)
0x180025f9f  lea     rdx, aAttemptedInval; "Attempted invalid operation in JSON str"...
0x180025fa6  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180025fab  call    ??0logic_error@std@@QEAA@PEBD@Z; std::logic_error::logic_error(char const *)
0x180025fb0  lea     rdx, _TI2?AVlogic_error@std@@; pThrowInfo
0x180025fb7  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180025fbc  call    _CxxThrowException_0
```
