# DllCanUnloadNow

- ea: `0x1800158a0`
- end: `0x1800158c9`
- name: `DllCanUnloadNow`
- size: `41`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008a7c`
- `0x180017010`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 *v0; // rax

  v0 = Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
  return (*(__int64 (__fastcall **)(__int64 *))(*v0 + 24))(v0) != 0;
}

```

## disassembly

```asm
0x1800158a0  sub     rsp, 28h
0x1800158a4  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x1800158a9  mov     rdx, rax
0x1800158ac  mov     rcx, [rax]
0x1800158af  mov     rax, [rcx+18h]
0x1800158b3  mov     rcx, rdx
0x1800158b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158bb  xor     ecx, ecx
0x1800158bd  test    eax, eax
0x1800158bf  setnz   cl
0x1800158c2  mov     eax, ecx
0x1800158c4  add     rsp, 28h
0x1800158c8  retn
```
