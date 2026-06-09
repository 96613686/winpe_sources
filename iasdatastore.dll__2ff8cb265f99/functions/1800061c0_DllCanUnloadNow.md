# DllCanUnloadNow

- ea: `0x1800061c0`
- end: `0x1800061e3`
- name: `DllCanUnloadNow`
- size: `35`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800061c0`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x1800061cb`
- `RPCRT4!NdrDllCanUnloadNow` at `0x1800061cb`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT result; // eax

  result = NdrDllCanUnloadNow(&gPFactory);
  if ( !result )
    return dword_180019A1C != 0;
  return result;
}

```

## disassembly

```asm
0x1800061c0  sub     rsp, 28h
0x1800061c4  lea     rcx, gPFactory; pPSFactoryBuffer
0x1800061cb  call    cs:__imp_NdrDllCanUnloadNow
0x1800061d1  test    eax, eax
0x1800061d3  jnz     short loc_1800061DE
0x1800061d5  cmp     cs:dword_180019A1C, eax
0x1800061db  setnz   al
0x1800061de  add     rsp, 28h
0x1800061e2  retn
```
