# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x140002fb0`
- end: `0x140003012`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140002fb0`
- `0x140007010`

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
0x140002fb0  sub     rsp, 28h
0x140002fb4  mov     r11, rcx
0x140002fb7  mov     rax, r8
0x140002fba  xor     ecx, ecx
0x140002fbc  mov     r10, rdx
0x140002fbf  mov     r8d, 80004003h
0x140002fc5  test    r9, r9
0x140002fc8  jz      short loc_14000300A
0x140002fca  mov     [r9], rcx
0x140002fcd  test    rdx, rdx
0x140002fd0  jz      short loc_140002FF5
0x140002fd2  cmp     [rax], ecx
0x140002fd4  jnz     short loc_140002FED
0x140002fd6  cmp     [rax+4], ecx
0x140002fd9  jnz     short loc_140002FED
0x140002fdb  cmp     dword ptr [rax+8], 0C0h
0x140002fe2  jnz     short loc_140002FED
0x140002fe4  cmp     dword ptr [rax+0Ch], 46000000h
0x140002feb  jz      short loc_140002FF5
0x140002fed  mov     r8d, 80040110h
0x140002ff3  jmp     short loc_14000300A
0x140002ff5  mov     rdx, rax
0x140002ff8  mov     r8, r9
0x140002ffb  mov     rax, [r11+40h]
0x140002fff  mov     rcx, r10
0x140003002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003007  mov     r8d, eax
0x14000300a  mov     eax, r8d
0x14000300d  add     rsp, 28h
0x140003011  retn
```
