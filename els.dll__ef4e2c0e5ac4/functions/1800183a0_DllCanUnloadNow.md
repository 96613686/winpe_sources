# DllCanUnloadNow

- ea: `0x1800183a0`
- end: `0x1800183cf`
- name: `DllCanUnloadNow`
- size: `47`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800183a0`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x1800183ab`
- `RPCRT4!NdrDllCanUnloadNow` at `0x1800183ab`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT result; // eax

  result = NdrDllCanUnloadNow(&gPFactory);
  if ( !result && (CDll::s_cObjs || CDll::s_cLocks) )
    return 1;
  return result;
}

```

## disassembly

```asm
0x1800183a0  sub     rsp, 28h
0x1800183a4  lea     rcx, gPFactory; pPSFactoryBuffer
0x1800183ab  call    cs:__imp_NdrDllCanUnloadNow
0x1800183b1  test    eax, eax
0x1800183b3  jnz     short loc_1800183CA
0x1800183b5  cmp     cs:?s_cObjs@CDll@@2KA, eax; ulong CDll::s_cObjs
0x1800183bb  jnz     short loc_1800183C5
0x1800183bd  cmp     cs:?s_cLocks@CDll@@2KA, eax; ulong CDll::s_cLocks
0x1800183c3  jz      short loc_1800183CA
0x1800183c5  mov     eax, 1
0x1800183ca  add     rsp, 28h
0x1800183ce  retn
```
