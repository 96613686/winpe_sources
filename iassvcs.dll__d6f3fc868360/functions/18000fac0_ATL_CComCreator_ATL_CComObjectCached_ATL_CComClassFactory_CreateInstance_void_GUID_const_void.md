# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000fac0`
- end: `0x18000fbe6`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `294`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000d98c`
- `0x18000fac0`
- `0x18001033c`
- `0x180019010`

## import_xrefs

- `msvcrt!free` at `0x18000fbcf`
- `msvcrt!free` at `0x18000fbcf`
- `KERNEL32!DeleteCriticalSection` at `0x18000fbc6`
- `KERNEL32!DeleteCriticalSection` at `0x18000fbc6`

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
      free(v9);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000fac0  mov     [rsp+arg_10], r8
0x18000fac5  mov     [rsp+arg_8], rdx
0x18000faca  mov     [rsp+arg_0], rcx
0x18000facf  push    rbx
0x18000fad0  push    rsi
0x18000fad1  push    r12
0x18000fad3  push    r13
0x18000fad5  push    r14
0x18000fad7  push    r15
0x18000fad9  sub     rsp, 38h
0x18000fadd  mov     r15, r8
0x18000fae0  mov     r12, rdx
0x18000fae3  mov     r14, rcx
0x18000fae6  test    r8, r8
0x18000fae9  jnz     short loc_18000FAF5
0x18000faeb  mov     eax, 80004003h
0x18000faf0  jmp     loc_18000FBD7
0x18000faf5  mov     qword ptr [r8], 0
0x18000fafc  mov     esi, 8007000Eh
0x18000fb01  mov     [rsp+68h+arg_18], esi
0x18000fb08  mov     [rsp+68h+var_48], 0
0x18000fb11  mov     ecx, 48h ; 'H'; Size
0x18000fb16  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fb1b  mov     rbx, rax
0x18000fb1e  test    rbx, rbx
0x18000fb21  jz      short loc_18000FB48
0x18000fb23  mov     dword ptr [rax+8], 0
0x18000fb2a  xorps   xmm0, xmm0
0x18000fb2d  xor     eax, eax
0x18000fb2f  movups  xmmword ptr [rbx+10h], xmm0
0x18000fb33  movups  xmmword ptr [rbx+20h], xmm0
0x18000fb37  mov     [rbx+30h], rax
0x18000fb3b  mov     [rbx+38h], al
0x18000fb3e  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x18000fb45  mov     [rbx], rax
0x18000fb48  mov     [rsp+68h+var_48], rbx
0x18000fb4d  jmp     short loc_18000FB6D
0x18000fb4f  mov     r15, [rsp+68h+arg_10]
0x18000fb57  mov     r12, [rsp+68h+arg_8]
0x18000fb5c  mov     r14, [rsp+68h+arg_0]
0x18000fb61  mov     esi, [rsp+68h+arg_18]
0x18000fb68  mov     rbx, [rsp+68h+var_48]
0x18000fb6d  test    rbx, rbx
0x18000fb70  jz      short loc_18000FBD5
0x18000fb72  mov     [rbx+40h], r14
0x18000fb76  lea     rcx, [rbx+10h]; this
0x18000fb7a  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000fb7f  mov     esi, eax
0x18000fb81  lea     r14, [rbx+38h]
0x18000fb85  test    eax, eax
0x18000fb87  js      short loc_18000FBA7
0x18000fb89  mov     byte ptr [r14], 1
0x18000fb8d  mov     rax, [rbx]
0x18000fb90  mov     r8, r15
0x18000fb93  mov     rdx, r12
0x18000fb96  mov     rcx, rbx
0x18000fb99  mov     rax, [rax]
0x18000fb9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fba1  mov     esi, eax
0x18000fba3  test    eax, eax
0x18000fba5  jz      short loc_18000FBD5
0x18000fba7  mov     dword ptr [rbx+8], 0C0000001h
0x18000fbae  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x18000fbb5  mov     [rbx], rax
0x18000fbb8  cmp     byte ptr [r14], 0
0x18000fbbc  jz      short loc_18000FBCC
0x18000fbbe  mov     byte ptr [r14], 0
0x18000fbc2  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000fbc6  call    cs:__imp_DeleteCriticalSection
0x18000fbcc  mov     rcx, rbx; Block
0x18000fbcf  call    cs:__imp_free
0x18000fbd5  mov     eax, esi
0x18000fbd7  add     rsp, 38h
0x18000fbdb  pop     r15
0x18000fbdd  pop     r14
0x18000fbdf  pop     r13
0x18000fbe1  pop     r12
0x18000fbe3  pop     rsi
0x18000fbe4  pop     rbx
0x18000fbe5  retn
```
