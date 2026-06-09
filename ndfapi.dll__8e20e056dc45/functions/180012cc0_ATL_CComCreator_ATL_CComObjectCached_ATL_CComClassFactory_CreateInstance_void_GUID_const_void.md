# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180012cc0`
- end: `0x180012de6`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `294`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800018c0`
- `0x1800058fc`
- `0x180012cc0`
- `0x180021010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180012dcf`
- `msvcrt!??3@YAXPEAX@Z` at `0x180012dcf`
- `KERNEL32!DeleteCriticalSection` at `0x180012dc6`
- `KERNEL32!DeleteCriticalSection` at `0x180012dc6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180012cc0  mov     [rsp+arg_10], r8
0x180012cc5  mov     [rsp+arg_8], rdx
0x180012cca  mov     [rsp+arg_0], rcx
0x180012ccf  push    rbx
0x180012cd0  push    rsi
0x180012cd1  push    r12
0x180012cd3  push    r13
0x180012cd5  push    r14
0x180012cd7  push    r15
0x180012cd9  sub     rsp, 38h
0x180012cdd  mov     r15, r8
0x180012ce0  mov     r12, rdx
0x180012ce3  mov     r14, rcx
0x180012ce6  test    r8, r8
0x180012ce9  jnz     short loc_180012CF5
0x180012ceb  mov     eax, 80004003h
0x180012cf0  jmp     loc_180012DD7
0x180012cf5  mov     qword ptr [r8], 0
0x180012cfc  mov     esi, 8007000Eh
0x180012d01  mov     [rsp+68h+arg_18], esi
0x180012d08  mov     [rsp+68h+var_48], 0
0x180012d11  mov     ecx, 48h ; 'H'; Size
0x180012d16  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012d1b  mov     rbx, rax
0x180012d1e  test    rbx, rbx
0x180012d21  jz      short loc_180012D48
0x180012d23  mov     dword ptr [rax+8], 0
0x180012d2a  xorps   xmm0, xmm0
0x180012d2d  xor     eax, eax
0x180012d2f  movups  xmmword ptr [rbx+10h], xmm0
0x180012d33  movups  xmmword ptr [rbx+20h], xmm0
0x180012d37  mov     [rbx+30h], rax
0x180012d3b  mov     [rbx+38h], al
0x180012d3e  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180012d45  mov     [rbx], rax
0x180012d48  mov     [rsp+68h+var_48], rbx
0x180012d4d  jmp     short loc_180012D6D
0x180012d4f  mov     r15, [rsp+68h+arg_10]
0x180012d57  mov     r12, [rsp+68h+arg_8]
0x180012d5c  mov     r14, [rsp+68h+arg_0]
0x180012d61  mov     esi, [rsp+68h+arg_18]
0x180012d68  mov     rbx, [rsp+68h+var_48]
0x180012d6d  test    rbx, rbx
0x180012d70  jz      short loc_180012DD5
0x180012d72  mov     [rbx+40h], r14
0x180012d76  lea     rcx, [rbx+10h]; this
0x180012d7a  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180012d7f  mov     esi, eax
0x180012d81  lea     r14, [rbx+38h]
0x180012d85  test    eax, eax
0x180012d87  js      short loc_180012DA7
0x180012d89  mov     byte ptr [r14], 1
0x180012d8d  mov     rax, [rbx]
0x180012d90  mov     r8, r15
0x180012d93  mov     rdx, r12
0x180012d96  mov     rcx, rbx
0x180012d99  mov     rax, [rax]
0x180012d9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012da1  mov     esi, eax
0x180012da3  test    eax, eax
0x180012da5  jz      short loc_180012DD5
0x180012da7  mov     dword ptr [rbx+8], 0C0000001h
0x180012dae  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180012db5  mov     [rbx], rax
0x180012db8  cmp     byte ptr [r14], 0
0x180012dbc  jz      short loc_180012DCC
0x180012dbe  mov     byte ptr [r14], 0
0x180012dc2  lea     rcx, [rbx+10h]; lpCriticalSection
0x180012dc6  call    cs:__imp_DeleteCriticalSection
0x180012dcc  mov     rcx, rbx
0x180012dcf  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180012dd5  mov     eax, esi
0x180012dd7  add     rsp, 38h
0x180012ddb  pop     r15
0x180012ddd  pop     r14
0x180012ddf  pop     r13
0x180012de1  pop     r12
0x180012de3  pop     rsi
0x180012de4  pop     rbx
0x180012de5  retn
```
