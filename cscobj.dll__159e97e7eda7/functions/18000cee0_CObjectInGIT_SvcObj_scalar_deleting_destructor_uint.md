# CObjectInGIT_SvcObj::`scalar deleting destructor'(uint)

- ea: `0x18000cee0`
- end: `0x18000cf7e`
- name: `??_GCObjectInGIT_SvcObj@@UEAAPEAXI@Z`
- size: `158`
- prototype: `void *__fastcall(CObjectInGIT_SvcObj *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x18000b7e4`
- `0x18000cee0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000cf2a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000cf2a`

## pseudocode

```c
CObjectInGIT_SvcObj *__fastcall CObjectInGIT_SvcObj::`scalar deleting destructor'(CObjectInGIT_SvcObj *this, char a2)
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
0x18000cee0  mov     r11, rsp
0x18000cee3  mov     [r11+10h], rbx
0x18000cee7  mov     [r11+18h], rsi
0x18000ceeb  push    rdi
0x18000ceec  sub     rsp, 30h
0x18000cef0  mov     edi, [rcx+10h]
0x18000cef3  lea     rax, ??_7CInterfaceInGITBase@@6B@; const CInterfaceInGITBase::`vftable'
0x18000cefa  mov     [rcx], rax
0x18000cefd  mov     esi, edx
0x18000ceff  mov     rbx, rcx
0x18000cf02  test    edi, edi
0x18000cf04  jz      short loc_18000CF58
0x18000cf06  xor     edx, edx; pUnkOuter
0x18000cf08  mov     qword ptr [r11+8], 0
0x18000cf10  lea     rax, [r11+8]
0x18000cf14  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000cf1b  mov     [r11-18h], rax
0x18000cf1f  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000cf26  lea     r8d, [rdx+1]; dwClsContext
0x18000cf2a  call    cs:__imp_CoCreateInstance
0x18000cf30  test    eax, eax
0x18000cf32  js      short loc_18000CF58
0x18000cf34  mov     rcx, [rsp+38h+arg_0]
0x18000cf39  mov     edx, edi
0x18000cf3b  mov     rax, [rcx]
0x18000cf3e  mov     rax, [rax+20h]
0x18000cf42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf47  mov     rcx, [rsp+38h+arg_0]
0x18000cf4c  mov     rax, [rcx]
0x18000cf4f  mov     rax, [rax+10h]
0x18000cf53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf58  test    sil, 1
0x18000cf5c  jz      short loc_18000CF6B
0x18000cf5e  mov     edx, 28h ; '('
0x18000cf63  mov     rcx, rbx; Block
0x18000cf66  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000cf6b  mov     rsi, [rsp+38h+arg_10]
0x18000cf70  mov     rax, rbx
0x18000cf73  mov     rbx, [rsp+38h+arg_8]
0x18000cf78  add     rsp, 30h
0x18000cf7c  pop     rdi
0x18000cf7d  retn
```
