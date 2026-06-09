# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180004370`
- end: `0x1800043d2`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `98`
- prototype: `__int64 __fastcall(ATL::CComClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004370`
- `0x180013010`

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
0x180004370  sub     rsp, 28h
0x180004374  mov     r11, rcx
0x180004377  mov     rax, r8
0x18000437a  xor     ecx, ecx
0x18000437c  mov     r10, rdx
0x18000437f  mov     r8d, 80004003h
0x180004385  test    r9, r9
0x180004388  jz      short loc_1800043CA
0x18000438a  mov     [r9], rcx
0x18000438d  test    rdx, rdx
0x180004390  jz      short loc_1800043B5
0x180004392  cmp     [rax], ecx
0x180004394  jnz     short loc_1800043AD
0x180004396  cmp     [rax+4], ecx
0x180004399  jnz     short loc_1800043AD
0x18000439b  cmp     dword ptr [rax+8], 0C0h
0x1800043a2  jnz     short loc_1800043AD
0x1800043a4  cmp     dword ptr [rax+0Ch], 46000000h
0x1800043ab  jz      short loc_1800043B5
0x1800043ad  mov     r8d, 80040110h
0x1800043b3  jmp     short loc_1800043CA
0x1800043b5  mov     rdx, rax
0x1800043b8  mov     r8, r9
0x1800043bb  mov     rax, [r11+40h]
0x1800043bf  mov     rcx, r10
0x1800043c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043c7  mov     r8d, eax
0x1800043ca  mov     eax, r8d
0x1800043cd  add     rsp, 28h
0x1800043d1  retn
```
