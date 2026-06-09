# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180003fa0`
- end: `0x180004002`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003fa0`
- `0x18000b010`

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
      return this[8](a2, a3, a4);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180003fa0  sub     rsp, 28h
0x180003fa4  mov     r11, rcx
0x180003fa7  mov     rax, r8
0x180003faa  xor     ecx, ecx
0x180003fac  mov     r10, rdx
0x180003faf  mov     r8d, 80004003h
0x180003fb5  test    r9, r9
0x180003fb8  jz      short loc_180003FFA
0x180003fba  mov     [r9], rcx
0x180003fbd  test    rdx, rdx
0x180003fc0  jz      short loc_180003FE5
0x180003fc2  cmp     [rax], ecx
0x180003fc4  jnz     short loc_180003FDD
0x180003fc6  cmp     [rax+4], ecx
0x180003fc9  jnz     short loc_180003FDD
0x180003fcb  cmp     dword ptr [rax+8], 0C0h
0x180003fd2  jnz     short loc_180003FDD
0x180003fd4  cmp     dword ptr [rax+0Ch], 46000000h
0x180003fdb  jz      short loc_180003FE5
0x180003fdd  mov     r8d, 80040110h
0x180003fe3  jmp     short loc_180003FFA
0x180003fe5  mov     rdx, rax
0x180003fe8  mov     r8, r9
0x180003feb  mov     rax, [r11+40h]
0x180003fef  mov     rcx, r10
0x180003ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ff7  mov     r8d, eax
0x180003ffa  mov     eax, r8d
0x180003ffd  add     rsp, 28h
0x180004001  retn
```
