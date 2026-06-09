# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x140007bf8`
- end: `0x140007cd9`
- name: `??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z`
- size: `225`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `54`
- callee_count: `5`
- tags: ``

## callers

- `0x140006818`
- `0x140007d8c`
- `0x1400083f0`
- `0x140008a5c`
- `0x140009034`
- `0x140009518`
- `0x140009898`
- `0x14000a610`
- `0x14000ab04`
- `0x14000b0fc`
- `0x14000c13c`
- `0x14000c384`
- `0x14000c8cc`
- `0x14000d134`
- `0x14000d384`
- `0x14000d9a8`
- `0x14000e328`
- `0x14000e8cc`
- `0x14000ea0c`
- `0x14000f1b8`
- `0x14000f2ac`
- `0x14000f5f0`
- `0x14001366c`
- `0x14001413c`
- `0x140014ea4`
- `0x140015b18`
- `0x140015dfc`
- `0x140016a04`
- `0x1400175f8`
- `0x140017cb0`
- `0x140019e24`
- `0x14001a28c`
- `0x14001b3f0`
- `0x14001b9fc`
- `0x14001df0c`
- `0x140022188`
- `0x140022564`
- `0x14002266c`
- `0x140022714`
- `0x140022998`
- `0x140022b14`
- `0x140022bd8`
- `0x1400231f8`
- `0x1400249f0`
- `0x1400251d4`
- `0x140025e48`
- `0x140026800`
- `0x140026f30`
- `0x140027534`
- `0x140029854`

## callees

- `0x140005e1c`
- `0x1400061dc`
- `0x1400062b8`
- `0x140007bf8`
- `0x140030010`

## pseudocode

```c
_QWORD *__fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
        _QWORD *a1,
        _QWORD *a2)
{
  __int64 v2; // rbp
  volatile signed __int32 *v4; // rdi
  volatile signed __int32 *v5; // rbx
  __int64 (__fastcall ***v6)(_QWORD, _QWORD, __int64); // rax
  _DWORD *v7; // r14

  v2 = *a2;
  v4 = (volatile signed __int32 *)(*a1 - 24LL);
  v5 = (volatile signed __int32 *)(*a2 - 24LL);
  if ( v5 != v4 )
  {
    if ( *((int *)v4 + 4) >= 0 && *(_QWORD *)v5 == *(_QWORD *)v4 )
    {
      v6 = (__int64 (__fastcall ***)(_QWORD, _QWORD, __int64))(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v5 + 32LL))(*(_QWORD *)v5);
      if ( *((int *)v5 + 4) >= 0 && v6 == *(__int64 (__fastcall ****)(_QWORD, _QWORD, __int64))v5 )
      {
        _InterlockedIncrement(v5 + 4);
      }
      else
      {
        v7 = v5 + 2;
        v5 = (volatile signed __int32 *)(**v6)(v6, *((unsigned int *)v5 + 2), 2);
        if ( !v5 )
          ATL::CSimpleStringT<char,0>::ThrowMemoryException();
        *((_DWORD *)v5 + 2) = *v7;
        ATL::CSimpleStringT<unsigned short,0>::CopyChars(v5 + 6, *v7 + 1, v2);
      }
      if ( _InterlockedExchangeAdd(v4 + 4, 0xFFFFFFFF) <= 1 )
        (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v4 + 8LL))(*(_QWORD *)v4, v4);
      *a1 = v5 + 6;
    }
    else
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(a1, *a2, *(unsigned int *)(v2 - 16));
    }
  }
  return a1;
}

```

## disassembly

```asm
0x140007bf8  push    rbx
0x140007bfa  push    rbp
0x140007bfb  push    rsi
0x140007bfc  push    rdi
0x140007bfd  push    r14
0x140007bff  sub     rsp, 20h
0x140007c03  mov     rbp, [rdx]
0x140007c06  mov     rsi, rcx
0x140007c09  mov     rdi, [rcx]
0x140007c0c  add     rdi, 0FFFFFFFFFFFFFFE8h
0x140007c10  lea     rbx, [rbp-18h]
0x140007c14  cmp     rbx, rdi
0x140007c17  jz      loc_140007CC5
0x140007c1d  cmp     dword ptr [rdi+10h], 0
0x140007c21  jl      loc_140007CB6
0x140007c27  mov     rcx, [rbx]
0x140007c2a  cmp     rcx, [rdi]
0x140007c2d  jnz     loc_140007CB6
0x140007c33  mov     rax, [rcx]
0x140007c36  mov     rax, [rax+20h]
0x140007c3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007c3f  cmp     dword ptr [rbx+10h], 0
0x140007c43  mov     rcx, rax
0x140007c46  jl      short loc_140007C53
0x140007c48  cmp     rax, [rbx]
0x140007c4b  jnz     short loc_140007C53
0x140007c4d  lock inc dword ptr [rbx+10h]
0x140007c51  jmp     short loc_140007C8E
0x140007c53  mov     rax, [rax]
0x140007c56  lea     r14, [rbx+8]
0x140007c5a  mov     edx, [r14]
0x140007c5d  mov     r8d, 2
0x140007c63  mov     rax, [rax]
0x140007c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007c6b  mov     rbx, rax
0x140007c6e  test    rax, rax
0x140007c71  jz      short loc_140007CD3
0x140007c73  mov     eax, [r14]
0x140007c76  lea     rcx, [rbx+18h]
0x140007c7a  mov     [rbx+8], eax
0x140007c7d  mov     r8, rbp
0x140007c80  mov     r9d, [r14]
0x140007c83  inc     r9d
0x140007c86  movsxd  rdx, r9d
0x140007c89  call    ?CopyChars@?$CSimpleStringT@G$0A@@ATL@@SAXPEAG_KPEBGH@Z; ATL::CSimpleStringT<ushort,0>::CopyChars(ushort *,unsigned __int64,ushort const *,int)
0x140007c8e  or      eax, 0FFFFFFFFh
0x140007c91  lock xadd [rdi+10h], eax
0x140007c96  sub     eax, 1
0x140007c99  jg      short loc_140007CAD
0x140007c9b  mov     rcx, [rdi]
0x140007c9e  mov     rdx, rdi
0x140007ca1  mov     rax, [rcx]
0x140007ca4  mov     rax, [rax+8]
0x140007ca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007cad  lea     rax, [rbx+18h]
0x140007cb1  mov     [rsi], rax
0x140007cb4  jmp     short loc_140007CC5
0x140007cb6  mov     r8d, [rbp-10h]
0x140007cba  mov     rdx, rbp
0x140007cbd  mov     rcx, rsi
0x140007cc0  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140007cc5  mov     rax, rsi
0x140007cc8  add     rsp, 20h
0x140007ccc  pop     r14
0x140007cce  pop     rdi
0x140007ccf  pop     rsi
0x140007cd0  pop     rbp
0x140007cd1  pop     rbx
0x140007cd2  retn
0x140007cd3  call    ?ThrowMemoryException@?$CSimpleStringT@D$0A@@ATL@@KAXXZ; ATL::CSimpleStringT<char,0>::ThrowMemoryException(void)
```
