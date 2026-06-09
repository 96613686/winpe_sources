# DllCanUnloadNow

- ea: `0x180013490`
- end: `0x1800134d1`
- name: `DllCanUnloadNow`
- size: `65`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180013490`
- `0x18003d010`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x18001349b`
- `RPCRT4!NdrDllCanUnloadNow` at `0x18001349b`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return NdrDllCanUnloadNow(&gPFactory) || (*(__int64 (__fastcall **)(void *))(Module + 24LL))(&Module) != 0;
}

```

## disassembly

```asm
0x180013490  sub     rsp, 28h
0x180013494  lea     rcx, gPFactory; pPSFactoryBuffer
0x18001349b  call    cs:__imp_NdrDllCanUnloadNow
0x1800134a1  test    eax, eax
0x1800134a3  jz      short loc_1800134AC
0x1800134a5  mov     eax, 1
0x1800134aa  jmp     short loc_1800134CC
0x1800134ac  mov     rax, cs:?Module@@3VCComModule@ATL@@A; ATL::CComModule Module
0x1800134b3  lea     rcx, ?Module@@3VCComModule@ATL@@A; ATL::CComModule Module
0x1800134ba  mov     rax, [rax+18h]
0x1800134be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134c3  xor     ecx, ecx
0x1800134c5  test    eax, eax
0x1800134c7  setnz   cl
0x1800134ca  mov     eax, ecx
0x1800134cc  add     rsp, 28h
0x1800134d0  retn
```
