# DllGetClassObject

- ea: `0x18000c580`
- end: `0x18000c5d6`
- name: `DllGetClassObject`
- size: `86`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180008778`
- `0x18000a090`
- `0x18000a65c`
- `0x18000c580`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  Microsoft::WRL::Details *v6; // rax
  ATL::CComModule *v7; // rcx

  v6 = (Microsoft::WRL::Details *)Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create();
  if ( (int)Microsoft::WRL::Details::GetClassObject<1>(v6, ppv) >= 0 )
    return 0;
  else
    return ATL::CComModule::GetClassObject(v7, rclsid, riid, ppv);
}

```

## disassembly

```asm
0x18000c580  mov     [rsp+arg_0], rbx
0x18000c585  mov     [rsp+arg_8], rsi
0x18000c58a  push    rdi
0x18000c58b  sub     rsp, 30h
0x18000c58f  mov     rbx, r8
0x18000c592  mov     rdi, rdx
0x18000c595  mov     rsi, rcx
0x18000c598  call    ?Create@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@SAAEAV?$DefaultModule@$00@Details@23@XZ; Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::Create(void)
0x18000c59d  mov     r9, rdi
0x18000c5a0  mov     [rsp+38h+var_18], rbx; PVOID
0x18000c5a5  mov     r8, rsi
0x18000c5a8  mov     rcx, rax; this
0x18000c5ab  call    ??$GetClassObject@$00@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBGAEBU_GUID@@2PEAPEAX@Z; Microsoft::WRL::Details::GetClassObject<1>(Microsoft::WRL::Details::ModuleBase *,ushort const *,_GUID const &,_GUID const &,void * *)
0x18000c5b0  test    eax, eax
0x18000c5b2  jns     short loc_18000C5C4
0x18000c5b4  mov     r9, rbx; void **
0x18000c5b7  mov     r8, rdi; struct _GUID *
0x18000c5ba  mov     rdx, rsi; struct _GUID *
0x18000c5bd  call    ?GetClassObject@CComModule@ATL@@QEAAJAEBU_GUID@@0PEAPEAX@Z; ATL::CComModule::GetClassObject(_GUID const &,_GUID const &,void * *)
0x18000c5c2  jmp     short loc_18000C5C6
0x18000c5c4  xor     eax, eax
0x18000c5c6  mov     rbx, [rsp+38h+arg_0]
0x18000c5cb  mov     rsi, [rsp+38h+arg_8]
0x18000c5d0  add     rsp, 30h
0x18000c5d4  pop     rdi
0x18000c5d5  retn
```
