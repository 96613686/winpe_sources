# DllCanUnloadNow

- ea: `0x180006d80`
- end: `0x180006da0`
- name: `DllCanUnloadNow`
- size: `32`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000693c`
- `0x180006c28`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 *v0; // rax
  struct Microsoft::WRL::Details::ModuleBase *v1; // rdx
  bool v2; // r9

  v0 = Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
  return !Microsoft::WRL::Details::TerminateMap((Microsoft::WRL::Details *)v0, v1, 0, v2);
}

```

## disassembly

```asm
0x180006d80  sub     rsp, 28h
0x180006d84  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x180006d89  xor     r8d, r8d; wchar_t *
0x180006d8c  mov     rcx, rax; this
0x180006d8f  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEB_W_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,wchar_t const *,bool)
0x180006d94  movzx   eax, al
0x180006d97  xor     eax, 1
0x180006d9a  add     rsp, 28h
0x180006d9e  retn
```
