# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180004060`
- end: `0x1800040c2`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004060`
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
      return this[8](a2, a3, a4);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180004060  sub     rsp, 28h
0x180004064  mov     r11, rcx
0x180004067  mov     rax, r8
0x18000406a  xor     ecx, ecx
0x18000406c  mov     r10, rdx
0x18000406f  mov     r8d, 80004003h
0x180004075  test    r9, r9
0x180004078  jz      short loc_1800040BA
0x18000407a  mov     [r9], rcx
0x18000407d  test    rdx, rdx
0x180004080  jz      short loc_1800040A5
0x180004082  cmp     [rax], ecx
0x180004084  jnz     short loc_18000409D
0x180004086  cmp     [rax+4], ecx
0x180004089  jnz     short loc_18000409D
0x18000408b  cmp     dword ptr [rax+8], 0C0h
0x180004092  jnz     short loc_18000409D
0x180004094  cmp     dword ptr [rax+0Ch], 46000000h
0x18000409b  jz      short loc_1800040A5
0x18000409d  mov     r8d, 80040110h
0x1800040a3  jmp     short loc_1800040BA
0x1800040a5  mov     rdx, rax
0x1800040a8  mov     r8, r9
0x1800040ab  mov     rax, [r11+40h]
0x1800040af  mov     rcx, r10
0x1800040b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040b7  mov     r8d, eax
0x1800040ba  mov     eax, r8d
0x1800040bd  add     rsp, 28h
0x1800040c1  retn
```
