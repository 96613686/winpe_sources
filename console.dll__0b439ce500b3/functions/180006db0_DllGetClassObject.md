# DllGetClassObject

- ea: `0x180006db0`
- end: `0x180006df1`
- name: `DllGetClassObject`
- size: `65`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800067e0`
- `0x18000693c`

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
0x180006db0  mov     [rsp+arg_0], rbx
0x180006db5  mov     [rsp+arg_8], rsi
0x180006dba  push    rdi
0x180006dbb  sub     rsp, 30h
0x180006dbf  mov     rbx, r8
0x180006dc2  mov     rdi, rdx
0x180006dc5  mov     rsi, rcx
0x180006dc8  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x180006dcd  mov     r9, rdi
0x180006dd0  mov     [rsp+38h+var_18], rbx; PVOID
0x180006dd5  mov     r8, rsi
0x180006dd8  mov     rcx, rax; this
0x180006ddb  call    ??$GetClassObject@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEB_WAEBU_GUID@@2PEAPEAX@Z; Microsoft::WRL::Details::GetClassObject<1>(Microsoft::WRL::Details::ModuleBase *,wchar_t const *,_GUID const &,_GUID const &,void * *)
0x180006de0  mov     rbx, [rsp+38h+arg_0]
0x180006de5  mov     rsi, [rsp+38h+arg_8]
0x180006dea  add     rsp, 30h
0x180006dee  pop     rdi
0x180006def  retn
```
