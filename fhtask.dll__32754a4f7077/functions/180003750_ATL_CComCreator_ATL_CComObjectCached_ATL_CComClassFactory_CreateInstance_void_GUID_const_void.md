# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003750`
- end: `0x180003876`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `294`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800011d8`
- `0x180003750`
- `0x1800039cc`
- `0x18000b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000385f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000385f`
- `KERNEL32!DeleteCriticalSection` at `0x180003856`
- `KERNEL32!DeleteCriticalSection` at `0x180003856`

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
0x180003750  mov     [rsp+arg_10], r8
0x180003755  mov     [rsp+arg_8], rdx
0x18000375a  mov     [rsp+arg_0], rcx
0x18000375f  push    rbx
0x180003760  push    rsi
0x180003761  push    r12
0x180003763  push    r13
0x180003765  push    r14
0x180003767  push    r15
0x180003769  sub     rsp, 38h
0x18000376d  mov     r15, r8
0x180003770  mov     r12, rdx
0x180003773  mov     r14, rcx
0x180003776  test    r8, r8
0x180003779  jnz     short loc_180003785
0x18000377b  mov     eax, 80004003h
0x180003780  jmp     loc_180003867
0x180003785  mov     qword ptr [r8], 0
0x18000378c  mov     esi, 8007000Eh
0x180003791  mov     [rsp+68h+arg_18], esi
0x180003798  mov     [rsp+68h+var_48], 0
0x1800037a1  mov     ecx, 48h ; 'H'; Size
0x1800037a6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800037ab  mov     rbx, rax
0x1800037ae  test    rbx, rbx
0x1800037b1  jz      short loc_1800037D8
0x1800037b3  mov     dword ptr [rax+8], 0
0x1800037ba  xorps   xmm0, xmm0
0x1800037bd  xor     eax, eax
0x1800037bf  movups  xmmword ptr [rbx+10h], xmm0
0x1800037c3  movups  xmmword ptr [rbx+20h], xmm0
0x1800037c7  mov     [rbx+30h], rax
0x1800037cb  mov     [rbx+38h], al
0x1800037ce  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x1800037d5  mov     [rbx], rax
0x1800037d8  mov     [rsp+68h+var_48], rbx
0x1800037dd  jmp     short loc_1800037FD
0x1800037df  mov     r15, [rsp+68h+arg_10]
0x1800037e7  mov     r12, [rsp+68h+arg_8]
0x1800037ec  mov     r14, [rsp+68h+arg_0]
0x1800037f1  mov     esi, [rsp+68h+arg_18]
0x1800037f8  mov     rbx, [rsp+68h+var_48]
0x1800037fd  test    rbx, rbx
0x180003800  jz      short loc_180003865
0x180003802  mov     [rbx+40h], r14
0x180003806  lea     rcx, [rbx+10h]; this
0x18000380a  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000380f  mov     esi, eax
0x180003811  lea     r14, [rbx+38h]
0x180003815  test    eax, eax
0x180003817  js      short loc_180003837
0x180003819  mov     byte ptr [r14], 1
0x18000381d  mov     rax, [rbx]
0x180003820  mov     r8, r15
0x180003823  mov     rdx, r12
0x180003826  mov     rcx, rbx
0x180003829  mov     rax, [rax]
0x18000382c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003831  mov     esi, eax
0x180003833  test    eax, eax
0x180003835  jz      short loc_180003865
0x180003837  mov     dword ptr [rbx+8], 0C0000001h
0x18000383e  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180003845  mov     [rbx], rax
0x180003848  cmp     byte ptr [r14], 0
0x18000384c  jz      short loc_18000385C
0x18000384e  mov     byte ptr [r14], 0
0x180003852  lea     rcx, [rbx+10h]; lpCriticalSection
0x180003856  call    cs:__imp_DeleteCriticalSection
0x18000385c  mov     rcx, rbx
0x18000385f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003865  mov     eax, esi
0x180003867  add     rsp, 38h
0x18000386b  pop     r15
0x18000386d  pop     r14
0x18000386f  pop     r13
0x180003871  pop     r12
0x180003873  pop     rsi
0x180003874  pop     rbx
0x180003875  retn
```
