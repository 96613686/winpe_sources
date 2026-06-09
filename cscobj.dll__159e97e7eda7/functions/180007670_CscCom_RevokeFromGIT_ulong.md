# CscCom_RevokeFromGIT(ulong)

- ea: `0x180007670`
- end: `0x1800076d8`
- name: `?CscCom_RevokeFromGIT@@YAXK@Z`
- size: `104`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009724`

## callees

- `0x180007670`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800076a4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800076a4`

## pseudocode

```c
void __fastcall CscCom_RevokeFromGIT(unsigned int a1)
{
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF

  if ( a1 )
  {
    ppv = 0;
    if ( CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv) >= 0 )
    {
      (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 32LL))(ppv, a1);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
  }
}

```

## disassembly

```asm
0x180007670  test    ecx, ecx
0x180007672  jz      short locret_1800076D7
0x180007674  push    rbx
0x180007675  sub     rsp, 30h
0x180007679  mov     ebx, ecx
0x18000767b  mov     [rsp+38h+arg_8], 0
0x180007684  lea     rax, [rsp+38h+arg_8]
0x180007689  xor     edx, edx; pUnkOuter
0x18000768b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180007692  mov     [rsp+38h+ppv], rax; ppv
0x180007697  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000769e  mov     r8d, 1; dwClsContext
0x1800076a4  call    cs:__imp_CoCreateInstance
0x1800076aa  test    eax, eax
0x1800076ac  js      short loc_1800076D2
0x1800076ae  mov     rcx, [rsp+38h+arg_8]
0x1800076b3  mov     edx, ebx
0x1800076b5  mov     rax, [rcx]
0x1800076b8  mov     rax, [rax+20h]
0x1800076bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076c1  mov     rcx, [rsp+38h+arg_8]
0x1800076c6  mov     rax, [rcx]
0x1800076c9  mov     rax, [rax+10h]
0x1800076cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076d2  add     rsp, 30h
0x1800076d6  pop     rbx
0x1800076d7  retn
```
