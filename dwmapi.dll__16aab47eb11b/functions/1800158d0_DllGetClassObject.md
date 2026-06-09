# DllGetClassObject

- ea: `0x1800158d0`
- end: `0x180015910`
- name: `DllGetClassObject`
- size: `64`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180008a7c`
- `0x180015558`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  __int64 *v4; // rax

  v4 = Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
  return Microsoft::WRL::Details::GetClassObject<1>((Microsoft::WRL::Details *)v4, ppv);
}

```

## disassembly

```asm
0x1800158d0  mov     [rsp+arg_0], rbx
0x1800158d5  mov     [rsp+arg_8], rsi
0x1800158da  push    rdi
0x1800158db  sub     rsp, 30h
0x1800158df  mov     rbx, r8
0x1800158e2  mov     rdi, rdx
0x1800158e5  mov     rsi, rcx
0x1800158e8  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x1800158ed  mov     r9, rdi
0x1800158f0  mov     [rsp+38h+var_18], rbx; PVOID
0x1800158f5  mov     r8, rsi
0x1800158f8  mov     rcx, rax; this
0x1800158fb  call    ??$GetClassObject@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGAEBU_GUID@@2PEAPEAX@Z; Microsoft::WRL::Details::GetClassObject<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,_GUID const &,_GUID const &,void * *)
0x180015900  mov     rbx, [rsp+38h+arg_0]
0x180015905  mov     rsi, [rsp+38h+arg_8]
0x18001590a  add     rsp, 30h
0x18001590e  pop     rdi
0x18001590f  retn
```
