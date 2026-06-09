# DllCanUnloadNow

- ea: `0x1800043b0`
- end: `0x1800043ec`
- name: `DllCanUnloadNow`
- size: `60`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800043b0`
- `0x180005010`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x1800043bb`
- `RPCRT4!NdrDllCanUnloadNow` at `0x1800043bb`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 v0; // rcx

  LODWORD(v0) = NdrDllCanUnloadNow(&gPFactory);
  if ( !(_DWORD)v0 )
    return (*(__int64 (__fastcall **)(void *))(qword_180009780 + 24LL))(&qword_180009780) != 0;
  return v0;
}

```

## disassembly

```asm
0x1800043b0  sub     rsp, 28h
0x1800043b4  lea     rcx, gPFactory; pPSFactoryBuffer
0x1800043bb  call    cs:__imp_NdrDllCanUnloadNow
0x1800043c1  mov     ecx, eax
0x1800043c3  test    eax, eax
0x1800043c5  jnz     short loc_1800043E5
0x1800043c7  mov     rax, cs:qword_180009780
0x1800043ce  lea     rcx, qword_180009780
0x1800043d5  mov     rax, [rax+18h]
0x1800043d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043de  xor     ecx, ecx
0x1800043e0  test    eax, eax
0x1800043e2  setnz   cl
0x1800043e5  mov     eax, ecx
0x1800043e7  add     rsp, 28h
0x1800043eb  retn
```
