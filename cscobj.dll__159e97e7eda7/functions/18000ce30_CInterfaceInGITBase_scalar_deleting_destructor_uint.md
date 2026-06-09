# CInterfaceInGITBase::`scalar deleting destructor'(uint)

- ea: `0x18000ce30`
- end: `0x18000cece`
- name: `??_GCInterfaceInGITBase@@UEAAPEAXI@Z`
- size: `158`
- prototype: `void *__fastcall(CInterfaceInGITBase *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x18000b7e4`
- `0x18000ce30`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000ce7a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000ce7a`

## pseudocode

```c
CInterfaceInGITBase *__fastcall CInterfaceInGITBase::`scalar deleting destructor'(CInterfaceInGITBase *this, char a2)
{
  unsigned int v2; // edi
  LPVOID v6; // [rsp+40h] [rbp+8h] BYREF

  v2 = *((_DWORD *)this + 4);
  *(_QWORD *)this = &CInterfaceInGITBase::`vftable';
  if ( v2 )
  {
    v6 = 0;
    if ( CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &v6) >= 0 )
    {
      (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v6 + 32LL))(v6, v2);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000ce30  mov     r11, rsp
0x18000ce33  mov     [r11+10h], rbx
0x18000ce37  mov     [r11+18h], rsi
0x18000ce3b  push    rdi
0x18000ce3c  sub     rsp, 30h
0x18000ce40  mov     edi, [rcx+10h]
0x18000ce43  lea     rax, ??_7CInterfaceInGITBase@@6B@; const CInterfaceInGITBase::`vftable'
0x18000ce4a  mov     [rcx], rax
0x18000ce4d  mov     esi, edx
0x18000ce4f  mov     rbx, rcx
0x18000ce52  test    edi, edi
0x18000ce54  jz      short loc_18000CEA8
0x18000ce56  xor     edx, edx; pUnkOuter
0x18000ce58  mov     qword ptr [r11+8], 0
0x18000ce60  lea     rax, [r11+8]
0x18000ce64  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000ce6b  mov     [r11-18h], rax
0x18000ce6f  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000ce76  lea     r8d, [rdx+1]; dwClsContext
0x18000ce7a  call    cs:__imp_CoCreateInstance
0x18000ce80  test    eax, eax
0x18000ce82  js      short loc_18000CEA8
0x18000ce84  mov     rcx, [rsp+38h+arg_0]
0x18000ce89  mov     edx, edi
0x18000ce8b  mov     rax, [rcx]
0x18000ce8e  mov     rax, [rax+20h]
0x18000ce92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce97  mov     rcx, [rsp+38h+arg_0]
0x18000ce9c  mov     rax, [rcx]
0x18000ce9f  mov     rax, [rax+10h]
0x18000cea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cea8  test    sil, 1
0x18000ceac  jz      short loc_18000CEBB
0x18000ceae  mov     edx, 18h
0x18000ceb3  mov     rcx, rbx; Block
0x18000ceb6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000cebb  mov     rsi, [rsp+38h+arg_10]
0x18000cec0  mov     rax, rbx
0x18000cec3  mov     rbx, [rsp+38h+arg_8]
0x18000cec8  add     rsp, 30h
0x18000cecc  pop     rdi
0x18000cecd  retn
```
