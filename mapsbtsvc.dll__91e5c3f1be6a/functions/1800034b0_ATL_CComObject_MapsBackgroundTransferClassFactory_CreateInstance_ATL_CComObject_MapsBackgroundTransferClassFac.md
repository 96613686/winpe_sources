# ATL::CComObject<MapsBackgroundTransferClassFactory>::CreateInstance(ATL::CComObject<MapsBackgroundTransferClassFactory> * *)

- ea: `0x1800034b0`
- end: `0x180003596`
- name: `?CreateInstance@?$CComObject@VMapsBackgroundTransferClassFactory@@@ATL@@SAJPEAPEAV12@@Z`
- size: `230`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180003730`

## callees

- `0x18000224c`
- `0x18000303c`
- `0x1800034b0`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<MapsBackgroundTransferClassFactory>::CreateInstance(_QWORD *a1)
{
  _QWORD *v1; // r14
  int v3; // esi
  _DWORD *v4; // rdi
  _DWORD *v6; // [rsp+50h] [rbp+18h]

  v1 = a1;
  if ( !a1 )
    return 2147500035LL;
  try
  {
    *a1 = 0;
    v3 = -2147024882;
    v4 = operator new(0x48u);
    v4[2] = 0;
    *((_OWORD *)v4 + 1) = 0;
    *((_OWORD *)v4 + 2) = 0;
    *((_QWORD *)v4 + 6) = 0;
    *((_BYTE *)v4 + 56) = 0;
    *(_QWORD *)v4 = &ATL::CComObject<MapsBackgroundTransferClassFactory>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    v6 = v4;
  }
  catch ( ... )
  {
    v1 = a1;
    v3 = -2147024882;
    v4 = v6;
  }
  if ( v4 )
  {
    *((_QWORD *)v4 + 8) = 0;
    v3 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v4 + 4));
    if ( v3 < 0 )
    {
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v4 + 40LL))(v4, 1);
      v4 = 0;
    }
    else
    {
      *((_BYTE *)v4 + 56) = 1;
      v3 = 0;
    }
  }
  *v1 = v4;
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800034b0  mov     [rsp+arg_18], rsi
0x1800034b5  mov     [rsp+arg_0], rcx
0x1800034ba  push    rdi
0x1800034bb  push    r14
0x1800034bd  push    r15
0x1800034bf  sub     rsp, 20h
0x1800034c3  mov     r14, rcx
0x1800034c6  test    rcx, rcx
0x1800034c9  jnz     short loc_1800034D5
0x1800034cb  mov     eax, 80004003h
0x1800034d0  jmp     loc_180003587
0x1800034d5  mov     qword ptr [rcx], 0
0x1800034dc  mov     esi, 8007000Eh
0x1800034e1  mov     [rsp+38h+arg_8], esi
0x1800034e5  mov     [rsp+38h+arg_10], 0
0x1800034ee  mov     ecx, 48h ; 'H'; Size
0x1800034f3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800034f8  mov     rdi, rax
0x1800034fb  mov     dword ptr [rax+8], 0
0x180003502  xorps   xmm0, xmm0
0x180003505  xor     eax, eax
0x180003507  movups  xmmword ptr [rdi+10h], xmm0
0x18000350b  movups  xmmword ptr [rdi+20h], xmm0
0x18000350f  mov     [rdi+30h], rax
0x180003513  mov     [rdi+38h], al
0x180003516  lea     rax, ??_7?$CComObject@VMapsBackgroundTransferClassFactory@@@ATL@@6B@; const ATL::CComObject<MapsBackgroundTransferClassFactory>::`vftable'
0x18000351d  mov     [rdi], rax
0x180003520  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003527  mov     rax, [rcx]
0x18000352a  mov     rax, [rax+8]
0x18000352e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003533  mov     [rsp+38h+arg_10], rdi
0x180003538  jmp     short loc_180003548
0x18000353a  mov     r14, [rsp+38h+arg_0]
0x18000353f  mov     esi, [rsp+38h+arg_8]
0x180003543  mov     rdi, [rsp+38h+arg_10]
0x180003548  test    rdi, rdi
0x18000354b  jz      short loc_180003582
0x18000354d  mov     qword ptr [rdi+40h], 0
0x180003555  lea     rcx, [rdi+10h]; this
0x180003559  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000355e  mov     esi, eax
0x180003560  test    eax, eax
0x180003562  js      short loc_18000356C
0x180003564  mov     byte ptr [rdi+38h], 1
0x180003568  xor     esi, esi
0x18000356a  jmp     short loc_180003582
0x18000356c  mov     rdx, [rdi]
0x18000356f  mov     rax, [rdx+28h]
0x180003573  mov     edx, 1
0x180003578  mov     rcx, rdi
0x18000357b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003580  xor     edi, edi
0x180003582  mov     [r14], rdi
0x180003585  mov     eax, esi
0x180003587  mov     rsi, [rsp+38h+arg_18]
0x18000358c  add     rsp, 20h
0x180003590  pop     r15
0x180003592  pop     r14
0x180003594  pop     rdi
0x180003595  retn
```
