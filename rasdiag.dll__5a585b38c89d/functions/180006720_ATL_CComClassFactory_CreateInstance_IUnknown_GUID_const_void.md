# ATL::CComClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180006720`
- end: `0x180006783`
- name: `?CreateInstance@CComClassFactory@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `99`
- prototype: `__int64 __fastcall(unsigned int (__fastcall **this)(struct IUnknown *, const struct _GUID *, void **), struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180006720`
- `0x18000f010`

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
0x180006720  sub     rsp, 28h
0x180006724  mov     r11, rcx
0x180006727  mov     rax, r8
0x18000672a  xor     ecx, ecx
0x18000672c  mov     r10, rdx
0x18000672f  mov     r8d, 80004003h
0x180006735  test    r9, r9
0x180006738  jz      short loc_18000677A
0x18000673a  mov     [r9], rcx
0x18000673d  test    rdx, rdx
0x180006740  jz      short loc_180006765
0x180006742  cmp     [rax], ecx
0x180006744  jnz     short loc_18000675D
0x180006746  cmp     [rax+4], ecx
0x180006749  jnz     short loc_18000675D
0x18000674b  cmp     dword ptr [rax+8], 0C0h
0x180006752  jnz     short loc_18000675D
0x180006754  cmp     dword ptr [rax+0Ch], 46000000h
0x18000675b  jz      short loc_180006765
0x18000675d  mov     r8d, 80040110h
0x180006763  jmp     short loc_18000677A
0x180006765  mov     rdx, rax
0x180006768  mov     r8, r9
0x18000676b  mov     rax, [r11+40h]
0x18000676f  mov     rcx, r10
0x180006772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006777  mov     r8d, eax
0x18000677a  mov     eax, r8d
0x18000677d  add     rsp, 28h
0x180006781  retn
```
