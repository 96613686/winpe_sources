# DllCanUnloadNow

- ea: `0x18000c860`
- end: `0x18000c8be`
- name: `DllCanUnloadNow`
- size: `94`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000c860`
- `0x180023010`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x18000c8a8`
- `RPCRT4!NdrDllCanUnloadNow` at `0x18000c8a8`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  int v0; // eax
  __int64 v1; // rcx

  if ( (*(unsigned int (__fastcall **)(void *))(gMyDllModule + 24LL))(&gMyDllModule) )
  {
    LODWORD(v1) = 1;
  }
  else
  {
    v0 = (*(__int64 (__fastcall **)(void *))(gMyDllModuleAC + 24LL))(&gMyDllModuleAC);
    v1 = v0 != 0;
    if ( !v0 )
      LODWORD(v1) = NdrDllCanUnloadNow(&gPFactory);
  }
  return v1;
}

```

## disassembly

```asm
0x18000c860  sub     rsp, 28h
0x18000c864  mov     rax, cs:?gMyDllModule@@3VCMyDllModule@@A; CMyDllModule gMyDllModule
0x18000c86b  lea     rcx, ?gMyDllModule@@3VCMyDllModule@@A; CMyDllModule gMyDllModule
0x18000c872  mov     rax, [rax+18h]
0x18000c876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c87b  test    eax, eax
0x18000c87d  jnz     short loc_18000C8B2
0x18000c87f  mov     rax, cs:?gMyDllModuleAC@@3VCMyDllModuleAC@@A; CMyDllModuleAC gMyDllModuleAC
0x18000c886  lea     rcx, ?gMyDllModuleAC@@3VCMyDllModuleAC@@A; CMyDllModuleAC gMyDllModuleAC
0x18000c88d  mov     rax, [rax+18h]
0x18000c891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c896  xor     ecx, ecx
0x18000c898  test    eax, eax
0x18000c89a  setnz   cl
0x18000c89d  test    eax, eax
0x18000c89f  jnz     short loc_18000C8B7
0x18000c8a1  lea     rcx, gPFactory; pPSFactoryBuffer
0x18000c8a8  call    cs:__imp_NdrDllCanUnloadNow
0x18000c8ae  mov     ecx, eax
0x18000c8b0  jmp     short loc_18000C8B7
0x18000c8b2  mov     ecx, 1
0x18000c8b7  mov     eax, ecx
0x18000c8b9  add     rsp, 28h
0x18000c8bd  retn
```
