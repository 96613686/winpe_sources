# std::optional<std::filesystem::path>::~optional<std::filesystem::path>(void)

- ea: `0x180008df4`
- end: `0x180008e08`
- name: `??1?$optional@Vpath@filesystem@std@@@std@@QEAA@XZ`
- size: `20`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000db32`
- `0x18000dc34`
- `0x18000dc46`

## callees

- `0x180008d88`
- `0x180008df4`

## pseudocode

```c
__int64 __fastcall std::optional<std::filesystem::path>::~optional<std::filesystem::path>(__int64 a1)
{
  __int64 result; // rax

  if ( *(_BYTE *)(a1 + 32) )
    return std::wstring::~wstring((char **)a1);
  return result;
}

```

## disassembly

```asm
0x180008df4  sub     rsp, 28h
0x180008df8  cmp     byte ptr [rcx+20h], 0
0x180008dfc  jz      short loc_180008E03
0x180008dfe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008e03  add     rsp, 28h
0x180008e07  retn
```
