# ATL::CComCreator<ATL::CComObjectCached<MapsBackgroundTransferClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180002e00`
- end: `0x180002ee8`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VMapsBackgroundTransferClassFactory@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `232`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000224c`
- `0x180002b28`
- `0x180002e00`
- `0x18000303c`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<MapsBackgroundTransferClassFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  __int64 v4; // r15
  __int64 v5; // r14
  _BYTE *v7; // rbx
  int v8; // edi
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
    *(_QWORD *)v7 = &ATL::CComObjectCached<MapsBackgroundTransferClassFactory>::`vftable';
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
      ATL::CComObjectCached<MapsBackgroundTransferClassFactory>::`scalar deleting destructor'(v7);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180002e00  mov     [rsp+arg_10], r8
0x180002e05  mov     [rsp+arg_8], rdx
0x180002e0a  mov     [rsp+arg_0], rcx
0x180002e0f  push    rbx
0x180002e10  push    rsi
0x180002e11  push    rdi
0x180002e12  push    r14
0x180002e14  push    r15
0x180002e16  sub     rsp, 30h
0x180002e1a  mov     rsi, r8
0x180002e1d  mov     r15, rdx
0x180002e20  mov     r14, rcx
0x180002e23  test    r8, r8
0x180002e26  jnz     short loc_180002E32
0x180002e28  mov     eax, 80004003h
0x180002e2d  jmp     loc_180002EDC
0x180002e32  mov     qword ptr [r8], 0
0x180002e39  mov     edi, 8007000Eh
0x180002e3e  mov     [rsp+58h+arg_18], edi
0x180002e42  mov     [rsp+58h+var_38], 0
0x180002e4b  mov     ecx, 48h ; 'H'; Size
0x180002e50  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002e55  mov     rbx, rax
0x180002e58  mov     dword ptr [rax+8], 0
0x180002e5f  xorps   xmm0, xmm0
0x180002e62  xor     eax, eax
0x180002e64  movups  xmmword ptr [rbx+10h], xmm0
0x180002e68  movups  xmmword ptr [rbx+20h], xmm0
0x180002e6c  mov     [rbx+30h], rax
0x180002e70  mov     [rbx+38h], al
0x180002e73  lea     rax, ??_7?$CComObjectCached@VMapsBackgroundTransferClassFactory@@@ATL@@6B@; const ATL::CComObjectCached<MapsBackgroundTransferClassFactory>::`vftable'
0x180002e7a  mov     [rbx], rax
0x180002e7d  mov     [rsp+58h+var_38], rbx
0x180002e82  jmp     short loc_180002E9C
0x180002e84  mov     rsi, [rsp+58h+arg_10]
0x180002e89  mov     r15, [rsp+58h+arg_8]
0x180002e8e  mov     r14, [rsp+58h+arg_0]
0x180002e93  mov     edi, [rsp+58h+arg_18]
0x180002e97  mov     rbx, [rsp+58h+var_38]
0x180002e9c  test    rbx, rbx
0x180002e9f  jz      short loc_180002EDA
0x180002ea1  mov     [rbx+40h], r14
0x180002ea5  lea     rcx, [rbx+10h]; this
0x180002ea9  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180002eae  mov     edi, eax
0x180002eb0  test    eax, eax
0x180002eb2  js      short loc_180002ED2
0x180002eb4  mov     byte ptr [rbx+38h], 1
0x180002eb8  mov     rax, [rbx]
0x180002ebb  mov     r8, rsi
0x180002ebe  mov     rdx, r15
0x180002ec1  mov     rcx, rbx
0x180002ec4  mov     rax, [rax]
0x180002ec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ecc  mov     edi, eax
0x180002ece  test    eax, eax
0x180002ed0  jz      short loc_180002EDA
0x180002ed2  mov     rcx, rbx; Block
0x180002ed5  call    ??_G?$CComObjectCached@VMapsBackgroundTransferClassFactory@@@ATL@@QEAAPEAXI@Z; ATL::CComObjectCached<MapsBackgroundTransferClassFactory>::`scalar deleting destructor'(uint)
0x180002eda  mov     eax, edi
0x180002edc  add     rsp, 30h
0x180002ee0  pop     r15
0x180002ee2  pop     r14
0x180002ee4  pop     rdi
0x180002ee5  pop     rsi
0x180002ee6  pop     rbx
0x180002ee7  retn
```
