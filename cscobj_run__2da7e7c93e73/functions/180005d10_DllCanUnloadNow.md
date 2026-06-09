# DllCanUnloadNow

- ea: `0x180005d10`
- end: `0x180005d42`
- name: `DllCanUnloadNow`
- size: `50`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005d10`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x180005d1b`
- `RPCRT4!NdrDllCanUnloadNow` at `0x180005d1b`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT result; // eax

  result = NdrDllCanUnloadNow(&gPFactory);
  if ( result || g_cServerLocks )
    return 1;
  LOBYTE(result) = g_cRefDll != 0;
  return result;
}

```

## disassembly

```asm
0x180005d10  sub     rsp, 28h
0x180005d14  lea     rcx, gPFactory; pPSFactoryBuffer
0x180005d1b  call    cs:__imp_NdrDllCanUnloadNow
0x180005d21  test    eax, eax
0x180005d23  jnz     short loc_180005D3B
0x180005d25  cmp     cs:?g_cServerLocks@@3JA, eax; long g_cServerLocks
0x180005d2b  jnz     short loc_180005D3B
0x180005d2d  cmp     cs:?g_cRefDll@@3JA, eax; long g_cRefDll
0x180005d33  setnz   al
0x180005d36  add     rsp, 28h
0x180005d3a  retn
0x180005d3b  mov     eax, 1
0x180005d40  jmp     short loc_180005D36
```
