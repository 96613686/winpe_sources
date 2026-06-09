# DllCanUnloadNow

- ea: `0x18000c530`
- end: `0x18000c572`
- name: `DllCanUnloadNow`
- size: `66`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000a090`
- `0x18000bd98`
- `0x18000c530`
- `0x18001c010`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 *v0; // rax
  struct Microsoft::WRL::Details::ModuleBase *v1; // rdx
  bool v2; // r9
  bool v3; // bl
  HRESULT result; // eax

  v0 = Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
  v3 = Microsoft::WRL::Details::TerminateMap((Microsoft::WRL::Details *)v0, v1, 0, v2);
  result = (*(__int64 (__fastcall **)(__int64 *))(g_AtlModule + 24))(&g_AtlModule);
  if ( !v3 || result )
    return 1;
  return result;
}

```

## disassembly

```asm
0x18000c530  push    rbx
0x18000c532  sub     rsp, 20h
0x18000c536  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x18000c53b  xor     r8d, r8d; unsigned __int16 *
0x18000c53e  mov     rcx, rax; this
0x18000c541  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x18000c546  mov     rcx, cs:?g_AtlModule@@3VCComModule@ATL@@A; ATL::CComModule g_AtlModule
0x18000c54d  mov     bl, al
0x18000c54f  mov     rax, [rcx+18h]
0x18000c553  lea     rcx, ?g_AtlModule@@3VCComModule@ATL@@A; ATL::CComModule g_AtlModule
0x18000c55a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c55f  test    bl, bl
0x18000c561  jz      short loc_18000C567
0x18000c563  test    eax, eax
0x18000c565  jz      short loc_18000C56C
0x18000c567  mov     eax, 1
0x18000c56c  add     rsp, 20h
0x18000c570  pop     rbx
0x18000c571  retn
```
