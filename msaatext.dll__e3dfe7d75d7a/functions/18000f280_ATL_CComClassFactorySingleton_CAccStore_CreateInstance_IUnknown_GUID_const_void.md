# ATL::CComClassFactorySingleton<CAccStore>::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x18000f280`
- end: `0x18000f2c8`
- name: `?CreateInstance@?$CComClassFactorySingleton@VCAccStore@@@ATL@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000f280`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComClassFactorySingleton<CAccStore>::CreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 result; // rax
  __int64 v5; // rcx

  result = 2147500035LL;
  if ( a4 )
  {
    *a4 = 0;
    if ( a2 )
    {
      return 2147746064LL;
    }
    else
    {
      v5 = a1 + 72;
      result = *(unsigned int *)(v5 + 72);
      if ( !(_DWORD)result )
        return (**(__int64 (__fastcall ***)(__int64, __int64, _QWORD *))v5)(v5, a3, a4);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000f280  sub     rsp, 28h
0x18000f284  mov     r10, r8
0x18000f287  mov     eax, 80004003h
0x18000f28c  test    r9, r9
0x18000f28f  jz      short loc_18000F2C3
0x18000f291  mov     qword ptr [r9], 0
0x18000f298  test    rdx, rdx
0x18000f29b  jz      short loc_18000F2A7
0x18000f29d  mov     eax, 80040110h
0x18000f2a2  add     rsp, 28h
0x18000f2a6  retn
0x18000f2a7  add     rcx, 48h ; 'H'
0x18000f2ab  mov     eax, [rcx+48h]
0x18000f2ae  test    eax, eax
0x18000f2b0  jnz     short loc_18000F2C3
0x18000f2b2  mov     rax, [rcx]
0x18000f2b5  mov     r8, r9
0x18000f2b8  mov     rdx, r10
0x18000f2bb  mov     rax, [rax]
0x18000f2be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2c3  add     rsp, 28h
0x18000f2c7  retn
```
