# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180002f40`
- end: `0x180002fa2`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(unsigned int (__fastcall **this)(struct IUnknown *, const struct _GUID *, void **), struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002f40`
- `0x18000a010`

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
0x180002f40  sub     rsp, 28h
0x180002f44  mov     r11, rcx
0x180002f47  mov     rax, r8
0x180002f4a  xor     ecx, ecx
0x180002f4c  mov     r10, rdx
0x180002f4f  mov     r8d, 80004003h
0x180002f55  test    r9, r9
0x180002f58  jz      short loc_180002F9A
0x180002f5a  mov     [r9], rcx
0x180002f5d  test    rdx, rdx
0x180002f60  jz      short loc_180002F85
0x180002f62  cmp     [rax], ecx
0x180002f64  jnz     short loc_180002F7D
0x180002f66  cmp     [rax+4], ecx
0x180002f69  jnz     short loc_180002F7D
0x180002f6b  cmp     dword ptr [rax+8], 0C0h
0x180002f72  jnz     short loc_180002F7D
0x180002f74  cmp     dword ptr [rax+0Ch], 46000000h
0x180002f7b  jz      short loc_180002F85
0x180002f7d  mov     r8d, 80040110h
0x180002f83  jmp     short loc_180002F9A
0x180002f85  mov     rdx, rax
0x180002f88  mov     r8, r9
0x180002f8b  mov     rax, [r11+40h]
0x180002f8f  mov     rcx, r10
0x180002f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f97  mov     r8d, eax
0x180002f9a  mov     eax, r8d
0x180002f9d  add     rsp, 28h
0x180002fa1  retn
```
