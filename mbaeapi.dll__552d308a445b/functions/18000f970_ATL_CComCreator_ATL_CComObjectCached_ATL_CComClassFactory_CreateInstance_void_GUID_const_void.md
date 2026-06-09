# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000f970`
- end: `0x18000fa84`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `276`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800028b0`
- `0x1800028ec`
- `0x18000f970`
- `0x18001088c`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fa62`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000fa62`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r14
  __int64 v4; // r12
  __int64 v5; // r15
  _BYTE *v7; // rbx
  int v8; // esi
  _BYTE *v9; // [rsp+20h] [rbp-38h]

  v3 = a3;
  v4 = a2;
  v5 = a1;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v8 = -2147024882;
    v7 = operator new(0x48u);
    *((_DWORD *)v7 + 2) = 0;
    *((_OWORD *)v7 + 1) = 0;
    *((_OWORD *)v7 + 2) = 0;
    *((_QWORD *)v7 + 6) = 0;
    v7[56] = 0;
    *(_QWORD *)v7 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
    v9 = v7;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v5 = a1;
    v8 = -2147024882;
    v7 = v9;
  }
  if ( v7 )
  {
    *((_QWORD *)v7 + 8) = v5;
    v8 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v7 + 16));
    if ( v8 < 0 || (v7[56] = 1, (v8 = (**(__int64 (__fastcall ***)(_BYTE *, __int64, _QWORD *))v7)(v7, v4, v3)) != 0) )
    {
      *((_DWORD *)v7 + 2) = -1073741823;
      *(_QWORD *)v7 = &ATL::CComClassFactory::`vftable';
      if ( v7[56] )
      {
        v7[56] = 0;
        DeleteCriticalSection((LPCRITICAL_SECTION)(v7 + 16));
      }
      operator delete(v7);
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000f970  mov     [rsp+arg_10], r8
0x18000f975  mov     [rsp+arg_8], rdx
0x18000f97a  mov     [rsp+arg_0], rcx
0x18000f97f  push    rbx
0x18000f980  push    rsi
0x18000f981  push    r12
0x18000f983  push    r14
0x18000f985  push    r15
0x18000f987  sub     rsp, 30h
0x18000f98b  mov     r14, r8
0x18000f98e  mov     r12, rdx
0x18000f991  mov     r15, rcx
0x18000f994  test    r8, r8
0x18000f997  jnz     short loc_18000F9A3
0x18000f999  mov     eax, 80004003h
0x18000f99e  jmp     loc_18000FA77
0x18000f9a3  mov     qword ptr [r8], 0
0x18000f9aa  mov     esi, 8007000Eh
0x18000f9af  mov     [rsp+58h+arg_18], esi
0x18000f9b3  mov     [rsp+58h+var_38], 0
0x18000f9bc  mov     ecx, 48h ; 'H'; Size
0x18000f9c1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f9c6  mov     rbx, rax
0x18000f9c9  mov     dword ptr [rax+8], 0
0x18000f9d0  xorps   xmm0, xmm0
0x18000f9d3  xor     eax, eax
0x18000f9d5  movups  xmmword ptr [rbx+10h], xmm0
0x18000f9d9  movups  xmmword ptr [rbx+20h], xmm0
0x18000f9dd  mov     [rbx+30h], rax
0x18000f9e1  mov     [rbx+38h], al
0x18000f9e4  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x18000f9eb  mov     [rbx], rax
0x18000f9ee  mov     [rsp+58h+var_38], rbx
0x18000f9f3  jmp     short loc_18000FA0D
0x18000f9f5  mov     r14, [rsp+58h+arg_10]
0x18000f9fa  mov     r12, [rsp+58h+arg_8]
0x18000f9ff  mov     r15, [rsp+58h+arg_0]
0x18000fa04  mov     esi, [rsp+58h+arg_18]
0x18000fa08  mov     rbx, [rsp+58h+var_38]
0x18000fa0d  test    rbx, rbx
0x18000fa10  jz      short loc_18000FA75
0x18000fa12  mov     [rbx+40h], r15
0x18000fa16  lea     rcx, [rbx+10h]; this
0x18000fa1a  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000fa1f  mov     esi, eax
0x18000fa21  test    eax, eax
0x18000fa23  js      short loc_18000FA43
0x18000fa25  mov     byte ptr [rbx+38h], 1
0x18000fa29  mov     rax, [rbx]
0x18000fa2c  mov     r8, r14
0x18000fa2f  mov     rdx, r12
0x18000fa32  mov     rcx, rbx
0x18000fa35  mov     rax, [rax]
0x18000fa38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa3d  mov     esi, eax
0x18000fa3f  test    eax, eax
0x18000fa41  jz      short loc_18000FA75
0x18000fa43  mov     dword ptr [rbx+8], 0C0000001h
0x18000fa4a  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x18000fa51  mov     [rbx], rax
0x18000fa54  cmp     byte ptr [rbx+38h], 0
0x18000fa58  jz      short loc_18000FA68
0x18000fa5a  mov     byte ptr [rbx+38h], 0
0x18000fa5e  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000fa62  call    cs:__imp_DeleteCriticalSection
0x18000fa68  mov     edx, 48h ; 'H'
0x18000fa6d  mov     rcx, rbx; Block
0x18000fa70  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000fa75  mov     eax, esi
0x18000fa77  add     rsp, 30h
0x18000fa7b  pop     r15
0x18000fa7d  pop     r14
0x18000fa7f  pop     r12
0x18000fa81  pop     rsi
0x18000fa82  pop     rbx
0x18000fa83  retn
```
