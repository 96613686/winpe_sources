# DllCanUnloadNow

- ea: `0x180004850`
- end: `0x18000488c`
- name: `DllCanUnloadNow`
- size: `60`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180004850`
- `0x180034010`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x18000485b`
- `RPCRT4!NdrDllCanUnloadNow` at `0x18000485b`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 v0; // rcx

  LODWORD(v0) = NdrDllCanUnloadNow(&gPFactory);
  if ( !(_DWORD)v0 )
    return (*(__int64 (__fastcall **)(void *))(qword_18004B000 + 24LL))(&qword_18004B000) != 0;
  return v0;
}

```

## disassembly

```asm
0x180004850  sub     rsp, 28h
0x180004854  lea     rcx, gPFactory; pPSFactoryBuffer
0x18000485b  call    cs:__imp_NdrDllCanUnloadNow
0x180004861  mov     ecx, eax
0x180004863  test    eax, eax
0x180004865  jnz     short loc_180004885
0x180004867  mov     rax, cs:qword_18004B000
0x18000486e  lea     rcx, qword_18004B000
0x180004875  mov     rax, [rax+18h]
0x180004879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000487e  xor     ecx, ecx
0x180004880  test    eax, eax
0x180004882  setnz   cl
0x180004885  mov     eax, ecx
0x180004887  add     rsp, 28h
0x18000488b  retn
```
