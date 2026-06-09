# std::tuple<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,HKEY__ *,bool,_DAF_PROVIDER_PATH>::~tuple<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,HKEY__ *,bool,_DAF_PROVIDER_PATH>(void)

- ea: `0x140011aa0`
- end: `0x140011aa9`
- name: `??1?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@_NW4_DAF_PROVIDER_PATH@@@std@@QEAA@XZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14001aeb6`
- `0x14001aefe`

## callees

- `0x1400106b4`

## pseudocode

```c
__int64 __fastcall std::tuple<std::wstring,HKEY__ *,bool,enum _DAF_PROVIDER_PATH>::~tuple<std::wstring,HKEY__ *,bool,enum _DAF_PROVIDER_PATH>(
        __int64 a1)
{
  return std::wstring::~wstring((char **)(a1 + 16));
}

```

## disassembly

```asm
0x140011aa0  add     rcx, 10h
0x140011aa4  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
