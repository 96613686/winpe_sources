# CreateAndRegisterClassFactory(void)

- ea: `0x140006a80`
- end: `0x140006b38`
- name: `?CreateAndRegisterClassFactory@@YAJXZ`
- size: `184`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140008b18`

## callees

- `0x140006a80`
- `0x140006b40`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x140006ae7`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x140006ae7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 CreateAndRegisterClassFactory(void)
{
  IUnknown *v0; // rdi
  int v1; // esi
  char *v2; // rsi
  char *v3; // rbx
  char *v5; // [rsp+40h] [rbp+8h] BYREF

  v5 = 0;
  v0 = 0;
  v1 = ATL::CComObject<ServerClassFactoryT<CProvisioningWapDPURemote>>::CreateInstance(&v5);
  if ( v1 < 0 )
  {
    v3 = v5;
  }
  else
  {
    v2 = v5;
    v3 = 0;
    if ( v5 )
    {
      (*(void (__fastcall **)(char *))(*(_QWORD *)v5 + 8LL))(v5);
      v0 = (IUnknown *)v2;
    }
    v1 = CoRegisterClassObject(&GUID_417976b7_917d_4f1e_8f14_c18fccb0b3a8, v0, 4u, 1u, &dwRegister);
  }
  if ( v0 )
    ((void (__fastcall *)(IUnknown *))v0->lpVtbl->Release)(v0);
  if ( v3 )
    (*(void (__fastcall **)(char *))(*(_QWORD *)v3 + 16LL))(v3);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x140006a80  mov     rax, rsp
0x140006a83  mov     [rax+10h], rbx
0x140006a87  mov     [rax+18h], rsi
0x140006a8b  push    rdi
0x140006a8c  sub     rsp, 30h
0x140006a90  mov     qword ptr [rax+8], 0
0x140006a98  xor     edi, edi
0x140006a9a  lea     rcx, [rax+8]
0x140006a9e  call    ?CreateInstance@?$CComObject@V?$ServerClassFactoryT@VCProvisioningWapDPURemote@@@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<ServerClassFactoryT<CProvisioningWapDPURemote>>::CreateInstance(ATL::CComObject<ServerClassFactoryT<CProvisioningWapDPURemote>> * *)
0x140006aa3  mov     esi, eax
0x140006aa5  test    eax, eax
0x140006aa7  js      short loc_140006AF7
0x140006aa9  mov     rsi, [rsp+38h+arg_0]
0x140006aae  xor     ebx, ebx
0x140006ab0  test    rsi, rsi
0x140006ab3  jz      short loc_140006AC7
0x140006ab5  mov     rax, [rsi]
0x140006ab8  mov     rcx, rsi
0x140006abb  mov     rax, [rax+8]
0x140006abf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006ac4  mov     rdi, rsi
0x140006ac7  lea     rax, dwRegister
0x140006ace  mov     [rsp+38h+lpdwRegister], rax; lpdwRegister
0x140006ad3  mov     r9d, 1; flags
0x140006ad9  lea     r8d, [r9+3]; dwClsContext
0x140006add  mov     rdx, rdi; pUnk
0x140006ae0  lea     rcx, _GUID_417976b7_917d_4f1e_8f14_c18fccb0b3a8; rclsid
0x140006ae7  call    cs:__imp_CoRegisterClassObject
0x140006aee  nop     dword ptr [rax+rax+00h]
0x140006af3  mov     esi, eax
0x140006af5  jmp     short loc_140006AFC
0x140006af7  mov     rbx, [rsp+38h+arg_0]
0x140006afc  test    rdi, rdi
0x140006aff  jz      short loc_140006B11
0x140006b01  mov     rax, [rdi]
0x140006b04  mov     rcx, rdi
0x140006b07  mov     rax, [rax+10h]
0x140006b0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006b10  nop
0x140006b11  test    rbx, rbx
0x140006b14  jz      short loc_140006B25
0x140006b16  mov     rax, [rbx]
0x140006b19  mov     rcx, rbx
0x140006b1c  mov     rax, [rax+10h]
0x140006b20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006b25  mov     eax, esi
0x140006b27  mov     rbx, [rsp+38h+arg_8]
0x140006b2c  mov     rsi, [rsp+38h+arg_10]
0x140006b31  add     rsp, 30h
0x140006b35  pop     rdi
0x140006b36  retn
```
