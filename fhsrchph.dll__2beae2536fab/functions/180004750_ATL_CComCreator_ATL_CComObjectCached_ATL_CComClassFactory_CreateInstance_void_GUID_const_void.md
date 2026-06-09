# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180004750`
- end: `0x180004876`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `294`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800011c4`
- `0x1800028fc`
- `0x180004750`
- `0x18000c010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000485f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000485f`
- `KERNEL32!DeleteCriticalSection` at `0x180004856`
- `KERNEL32!DeleteCriticalSection` at `0x180004856`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // r15
  __int64 v4; // r12
  __int64 v5; // r14
  int v7; // esi
  char *v8; // rax
  char *v9; // rbx
  _BYTE *v10; // r14
  char *v11; // [rsp+20h] [rbp-48h]

  v3 = a3;
  v4 = a2;
  v5 = a1;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = (char *)operator new(0x48u);
    v9 = v8;
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 0;
      *((_OWORD *)v8 + 1) = 0;
      *((_OWORD *)v8 + 2) = 0;
      *((_QWORD *)v8 + 6) = 0;
      v8[56] = 0;
      *(_QWORD *)v8 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
    }
    v11 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v5 = a1;
    v7 = -2147024882;
    v9 = v11;
  }
  if ( v9 )
  {
    *((_QWORD *)v9 + 8) = v5;
    v7 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v9 + 16));
    v10 = v9 + 56;
    if ( v7 < 0 || (*v10 = 1, (v7 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v9)(v9, v4, v3)) != 0) )
    {
      *((_DWORD *)v9 + 2) = -1073741823;
      *(_QWORD *)v9 = &ATL::CComClassFactory::`vftable';
      if ( *v10 )
      {
        *v10 = 0;
        DeleteCriticalSection((LPCRITICAL_SECTION)(v9 + 16));
      }
      operator delete(v9);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180004750  mov     [rsp+arg_10], r8
0x180004755  mov     [rsp+arg_8], rdx
0x18000475a  mov     [rsp+arg_0], rcx
0x18000475f  push    rbx
0x180004760  push    rsi
0x180004761  push    r12
0x180004763  push    r13
0x180004765  push    r14
0x180004767  push    r15
0x180004769  sub     rsp, 38h
0x18000476d  mov     r15, r8
0x180004770  mov     r12, rdx
0x180004773  mov     r14, rcx
0x180004776  test    r8, r8
0x180004779  jnz     short loc_180004785
0x18000477b  mov     eax, 80004003h
0x180004780  jmp     loc_180004867
0x180004785  mov     qword ptr [r8], 0
0x18000478c  mov     esi, 8007000Eh
0x180004791  mov     [rsp+68h+arg_18], esi
0x180004798  mov     [rsp+68h+var_48], 0
0x1800047a1  mov     ecx, 48h ; 'H'; Size
0x1800047a6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800047ab  mov     rbx, rax
0x1800047ae  test    rbx, rbx
0x1800047b1  jz      short loc_1800047D8
0x1800047b3  mov     dword ptr [rax+8], 0
0x1800047ba  xorps   xmm0, xmm0
0x1800047bd  xor     eax, eax
0x1800047bf  movups  xmmword ptr [rbx+10h], xmm0
0x1800047c3  movups  xmmword ptr [rbx+20h], xmm0
0x1800047c7  mov     [rbx+30h], rax
0x1800047cb  mov     [rbx+38h], al
0x1800047ce  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x1800047d5  mov     [rbx], rax
0x1800047d8  mov     [rsp+68h+var_48], rbx
0x1800047dd  jmp     short loc_1800047FD
0x1800047df  mov     r15, [rsp+68h+arg_10]
0x1800047e7  mov     r12, [rsp+68h+arg_8]
0x1800047ec  mov     r14, [rsp+68h+arg_0]
0x1800047f1  mov     esi, [rsp+68h+arg_18]
0x1800047f8  mov     rbx, [rsp+68h+var_48]
0x1800047fd  test    rbx, rbx
0x180004800  jz      short loc_180004865
0x180004802  mov     [rbx+40h], r14
0x180004806  lea     rcx, [rbx+10h]; this
0x18000480a  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000480f  mov     esi, eax
0x180004811  lea     r14, [rbx+38h]
0x180004815  test    eax, eax
0x180004817  js      short loc_180004837
0x180004819  mov     byte ptr [r14], 1
0x18000481d  mov     rax, [rbx]
0x180004820  mov     r8, r15
0x180004823  mov     rdx, r12
0x180004826  mov     rcx, rbx
0x180004829  mov     rax, [rax]
0x18000482c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004831  mov     esi, eax
0x180004833  test    eax, eax
0x180004835  jz      short loc_180004865
0x180004837  mov     dword ptr [rbx+8], 0C0000001h
0x18000483e  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180004845  mov     [rbx], rax
0x180004848  cmp     byte ptr [r14], 0
0x18000484c  jz      short loc_18000485C
0x18000484e  mov     byte ptr [r14], 0
0x180004852  lea     rcx, [rbx+10h]; lpCriticalSection
0x180004856  call    cs:__imp_DeleteCriticalSection
0x18000485c  mov     rcx, rbx
0x18000485f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004865  mov     eax, esi
0x180004867  add     rsp, 38h
0x18000486b  pop     r15
0x18000486d  pop     r14
0x18000486f  pop     r13
0x180004871  pop     r12
0x180004873  pop     rsi
0x180004874  pop     rbx
0x180004875  retn
```
