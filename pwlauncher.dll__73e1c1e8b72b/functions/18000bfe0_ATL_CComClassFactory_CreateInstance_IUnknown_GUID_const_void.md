# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000bfe0`
- end: `0x18000c042`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(unsigned int (__fastcall **this)(struct IUnknown *, const struct _GUID *, void **), struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000bfe0`
- `0x180011010`

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
0x18000bfe0  sub     rsp, 28h
0x18000bfe4  mov     r11, rcx
0x18000bfe7  mov     rax, r8
0x18000bfea  xor     ecx, ecx
0x18000bfec  mov     r10, rdx
0x18000bfef  mov     r8d, 80004003h
0x18000bff5  test    r9, r9
0x18000bff8  jz      short loc_18000C03A
0x18000bffa  mov     [r9], rcx
0x18000bffd  test    rdx, rdx
0x18000c000  jz      short loc_18000C025
0x18000c002  cmp     [rax], ecx
0x18000c004  jnz     short loc_18000C01D
0x18000c006  cmp     [rax+4], ecx
0x18000c009  jnz     short loc_18000C01D
0x18000c00b  cmp     dword ptr [rax+8], 0C0h
0x18000c012  jnz     short loc_18000C01D
0x18000c014  cmp     dword ptr [rax+0Ch], 46000000h
0x18000c01b  jz      short loc_18000C025
0x18000c01d  mov     r8d, 80040110h
0x18000c023  jmp     short loc_18000C03A
0x18000c025  mov     rdx, rax
0x18000c028  mov     r8, r9
0x18000c02b  mov     rax, [r11+40h]
0x18000c02f  mov     rcx, r10
0x18000c032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c037  mov     r8d, eax
0x18000c03a  mov     eax, r8d
0x18000c03d  add     rsp, 28h
0x18000c041  retn
```
