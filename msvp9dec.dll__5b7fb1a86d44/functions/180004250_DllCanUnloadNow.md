# DllCanUnloadNow

- ea: `0x180004250`
- end: `0x180004279`
- name: `DllCanUnloadNow`
- size: `41`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800011c0`
- `0x180006010`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  int *v0; // rax

  v0 = Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
  return (*(__int64 (__fastcall **)(int *))(*(_QWORD *)v0 + 24LL))(v0) != 0;
}

```

## disassembly

```asm
0x180004250  sub     rsp, 28h
0x180004254  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x180004259  mov     rdx, rax
0x18000425c  mov     rcx, [rax]
0x18000425f  mov     rax, [rcx+18h]
0x180004263  mov     rcx, rdx
0x180004266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000426b  xor     ecx, ecx
0x18000426d  test    eax, eax
0x18000426f  setnz   cl
0x180004272  mov     eax, ecx
0x180004274  add     rsp, 28h
0x180004278  retn
```
