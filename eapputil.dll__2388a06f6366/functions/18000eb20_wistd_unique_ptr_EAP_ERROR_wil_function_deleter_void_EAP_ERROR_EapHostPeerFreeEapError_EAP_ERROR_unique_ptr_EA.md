# wistd::unique_ptr<_EAP_ERROR,wil::function_deleter<void (*)(_EAP_ERROR *),&EapHostPeerFreeEapError(_EAP_ERROR *)>>::~unique_ptr<_EAP_ERROR,wil::function_deleter<void (*)(_EAP_ERROR *),&EapHostPeerFreeEapError(_EAP_ERROR *)>>(void)

- ea: `0x18000eb20`
- end: `0x18000eb41`
- name: `??1?$unique_ptr@U_EAP_ERROR@@U?$function_deleter@P6AXPEAU_EAP_ERROR@@@Z$1?EapHostPeerFreeEapError@@YAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: `void __fastcall(EAP_ERROR **)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180031473`
- `0x1800314fb`
- `0x18003150d`
- `0x1800315af`

## callees

- `0x18000eb20`

## import_xrefs

- `eappprxy!EapHostPeerFreeEapError` at `0x18000eb36`
- `eappprxy!EapHostPeerFreeEapError` at `0x18000eb36`

## pseudocode

```c
void __fastcall wistd::unique_ptr<_EAP_ERROR,wil::function_deleter<void (*)(_EAP_ERROR *),&void EapHostPeerFreeEapError(_EAP_ERROR *)>>::~unique_ptr<_EAP_ERROR,wil::function_deleter<void (*)(_EAP_ERROR *),&void EapHostPeerFreeEapError(_EAP_ERROR *)>>(
        EAP_ERROR **a1)
{
  EAP_ERROR *v1; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
    EapHostPeerFreeEapError(v1);
}

```

## disassembly

```asm
0x18000eb20  sub     rsp, 28h
0x18000eb24  mov     rax, [rcx]
0x18000eb27  mov     qword ptr [rcx], 0
0x18000eb2e  test    rax, rax
0x18000eb31  jz      short loc_18000EB3C
0x18000eb33  mov     rcx, rax; pEapError
0x18000eb36  call    cs:__imp_EapHostPeerFreeEapError
0x18000eb3c  add     rsp, 28h
0x18000eb40  retn
```
