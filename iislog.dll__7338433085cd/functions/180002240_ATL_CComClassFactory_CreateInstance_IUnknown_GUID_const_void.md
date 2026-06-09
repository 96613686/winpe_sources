# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180002240`
- end: `0x1800022a2`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002240`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall ATL::CComClassFactory::CreateInstance(
        unsigned int (__fastcall **this)(struct IUnknown *, const struct _GUID *, void **),
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  unsigned int v5; // r8d

  v5 = -2147467261;
  if ( a4 )
  {
    *a4 = 0;
    if ( a2
      && (a3->Data1 || *(_DWORD *)&a3->Data2 || *(_DWORD *)a3->Data4 != 192 || *(_DWORD *)&a3->Data4[4] != 1174405120) )
    {
      return (unsigned int)-2147221232;
    }
    else
    {
      return this[7](a2, a3, a4);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180002240  sub     rsp, 28h
0x180002244  mov     r11, rcx
0x180002247  mov     rax, r8
0x18000224a  xor     ecx, ecx
0x18000224c  mov     r10, rdx
0x18000224f  mov     r8d, 80004003h
0x180002255  test    r9, r9
0x180002258  jz      short loc_18000229A
0x18000225a  mov     [r9], rcx
0x18000225d  test    rdx, rdx
0x180002260  jz      short loc_180002285
0x180002262  cmp     [rax], ecx
0x180002264  jnz     short loc_18000227D
0x180002266  cmp     [rax+4], ecx
0x180002269  jnz     short loc_18000227D
0x18000226b  cmp     dword ptr [rax+8], 0C0h
0x180002272  jnz     short loc_18000227D
0x180002274  cmp     dword ptr [rax+0Ch], 46000000h
0x18000227b  jz      short loc_180002285
0x18000227d  mov     r8d, 80040110h
0x180002283  jmp     short loc_18000229A
0x180002285  mov     rdx, rax
0x180002288  mov     r8, r9
0x18000228b  mov     rax, [r11+38h]
0x18000228f  mov     rcx, r10
0x180002292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002297  mov     r8d, eax
0x18000229a  mov     eax, r8d
0x18000229d  add     rsp, 28h
0x1800022a1  retn
```
