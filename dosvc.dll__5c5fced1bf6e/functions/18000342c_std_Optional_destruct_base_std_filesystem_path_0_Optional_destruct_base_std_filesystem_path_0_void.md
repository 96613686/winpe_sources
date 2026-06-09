# std::_Optional_destruct_base<std::filesystem::path,0>::~_Optional_destruct_base<std::filesystem::path,0>(void)

- ea: `0x18000342c`
- end: `0x180003440`
- name: `??1?$_Optional_destruct_base@Vpath@filesystem@std@@$0A@@std@@QEAA@XZ`
- size: `20`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003420`
- `0x1800087c0`
- `0x180009c4c`

## callees

- `0x18000342c`
- `0x1800036b4`

## pseudocode

```c
__int64 __fastcall std::_Optional_destruct_base<std::filesystem::path,0>::~_Optional_destruct_base<std::filesystem::path,0>(
        __int64 a1)
{
  __int64 result; // rax

  if ( *(_BYTE *)(a1 + 32) )
    return std::wstring::_Tidy_deallocate(a1);
  return result;
}

```

## disassembly

```asm
0x18000342c  sub     rsp, 28h
0x180003430  cmp     byte ptr [rcx+20h], 0
0x180003434  jz      short loc_18000343B
0x180003436  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000343b  add     rsp, 28h
0x18000343f  retn
```
