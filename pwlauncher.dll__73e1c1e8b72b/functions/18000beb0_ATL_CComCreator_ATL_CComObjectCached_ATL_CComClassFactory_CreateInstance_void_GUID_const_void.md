# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000beb0`
- end: `0x18000bfd6`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `294`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800016e4`
- `0x180003adc`
- `0x18000beb0`
- `0x180011010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000bfbf`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000bfbf`
- `KERNEL32!DeleteCriticalSection` at `0x18000bfb6`
- `KERNEL32!DeleteCriticalSection` at `0x18000bfb6`

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
0x18000beb0  mov     [rsp+arg_10], r8
0x18000beb5  mov     [rsp+arg_8], rdx
0x18000beba  mov     [rsp+arg_0], rcx
0x18000bebf  push    rbx
0x18000bec0  push    rsi
0x18000bec1  push    r12
0x18000bec3  push    r13
0x18000bec5  push    r14
0x18000bec7  push    r15
0x18000bec9  sub     rsp, 38h
0x18000becd  mov     r15, r8
0x18000bed0  mov     r12, rdx
0x18000bed3  mov     r14, rcx
0x18000bed6  test    r8, r8
0x18000bed9  jnz     short loc_18000BEE5
0x18000bedb  mov     eax, 80004003h
0x18000bee0  jmp     loc_18000BFC7
0x18000bee5  mov     qword ptr [r8], 0
0x18000beec  mov     esi, 8007000Eh
0x18000bef1  mov     [rsp+68h+arg_18], esi
0x18000bef8  mov     [rsp+68h+var_48], 0
0x18000bf01  mov     ecx, 48h ; 'H'; Size
0x18000bf06  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bf0b  mov     rbx, rax
0x18000bf0e  test    rbx, rbx
0x18000bf11  jz      short loc_18000BF38
0x18000bf13  mov     dword ptr [rax+8], 0
0x18000bf1a  xorps   xmm0, xmm0
0x18000bf1d  xor     eax, eax
0x18000bf1f  movups  xmmword ptr [rbx+10h], xmm0
0x18000bf23  movups  xmmword ptr [rbx+20h], xmm0
0x18000bf27  mov     [rbx+30h], rax
0x18000bf2b  mov     [rbx+38h], al
0x18000bf2e  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x18000bf35  mov     [rbx], rax
0x18000bf38  mov     [rsp+68h+var_48], rbx
0x18000bf3d  jmp     short loc_18000BF5D
0x18000bf3f  mov     r15, [rsp+68h+arg_10]
0x18000bf47  mov     r12, [rsp+68h+arg_8]
0x18000bf4c  mov     r14, [rsp+68h+arg_0]
0x18000bf51  mov     esi, [rsp+68h+arg_18]
0x18000bf58  mov     rbx, [rsp+68h+var_48]
0x18000bf5d  test    rbx, rbx
0x18000bf60  jz      short loc_18000BFC5
0x18000bf62  mov     [rbx+40h], r14
0x18000bf66  lea     rcx, [rbx+10h]; this
0x18000bf6a  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000bf6f  mov     esi, eax
0x18000bf71  lea     r14, [rbx+38h]
0x18000bf75  test    eax, eax
0x18000bf77  js      short loc_18000BF97
0x18000bf79  mov     byte ptr [r14], 1
0x18000bf7d  mov     rax, [rbx]
0x18000bf80  mov     r8, r15
0x18000bf83  mov     rdx, r12
0x18000bf86  mov     rcx, rbx
0x18000bf89  mov     rax, [rax]
0x18000bf8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf91  mov     esi, eax
0x18000bf93  test    eax, eax
0x18000bf95  jz      short loc_18000BFC5
0x18000bf97  mov     dword ptr [rbx+8], 0C0000001h
0x18000bf9e  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x18000bfa5  mov     [rbx], rax
0x18000bfa8  cmp     byte ptr [r14], 0
0x18000bfac  jz      short loc_18000BFBC
0x18000bfae  mov     byte ptr [r14], 0
0x18000bfb2  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000bfb6  call    cs:__imp_DeleteCriticalSection
0x18000bfbc  mov     rcx, rbx
0x18000bfbf  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000bfc5  mov     eax, esi
0x18000bfc7  add     rsp, 38h
0x18000bfcb  pop     r15
0x18000bfcd  pop     r14
0x18000bfcf  pop     r13
0x18000bfd1  pop     r12
0x18000bfd3  pop     rsi
0x18000bfd4  pop     rbx
0x18000bfd5  retn
```
