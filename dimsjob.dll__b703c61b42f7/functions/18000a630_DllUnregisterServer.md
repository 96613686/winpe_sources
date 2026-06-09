# DllUnregisterServer

- ea: `0x18000a630`
- end: `0x18000a647`
- name: `DllUnregisterServer`
- size: `23`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x180003fd0`
- `0x18000a630`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  CModule *v0; // rcx
  HRESULT result; // eax
  HRESULT *v3; // rbx
  HRESULT *v4; // [rsp+20h] [rbp-18h] BYREF

  try
  {
    CModule::UnregisterServer(v0);
    result = 0;
  }
  catch ( CExcept *v4 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    {
      v3 = v4;
    }
    else
    {
      v3 = v4;
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        WPP_131b2a0d4f85352fb20a93dea1f15849_Traceguids,
        (unsigned int)*v4);
    }
    return *v3;
  }
  CModule::UnregisterServer(v0);
}

```

## disassembly

```asm
0x18000a630  sub     rsp, 38h
0x18000a634  call    ?UnregisterServer@CModule@@QEAAXXZ; CModule::UnregisterServer(void)
0x18000a639  nop
0x18000a63a  xor     eax, eax
0x18000a63c  jmp     short loc_18000A642
0x18000a63e  mov     eax, [rsp+38h+arg_0]
0x18000a642  add     rsp, 38h
0x18000a646  retn
```
