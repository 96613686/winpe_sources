# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactorySingleton<AuditChannel>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000f960`
- end: `0x18000fab1`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@V?$CComClassFactorySingleton@VAuditChannel@@@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `337`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000d98c`
- `0x18000f960`
- `0x18001033c`
- `0x180019010`

## import_xrefs

- `msvcrt!free` at `0x18000fa9a`
- `msvcrt!free` at `0x18000fa9a`
- `KERNEL32!DeleteCriticalSection` at `0x18000fa91`
- `KERNEL32!DeleteCriticalSection` at `0x18000fa91`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactorySingleton<AuditChannel>>>::CreateInstance(
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
  __int64 v11; // rcx
  char *v12; // [rsp+20h] [rbp-48h]

  v3 = a3;
  v4 = a2;
  v5 = a1;
  if ( !a3 )
    return 2147500035LL;
  try
  {
    *a3 = 0;
    v7 = -2147024882;
    v8 = (char *)operator new(0x58u);
    v9 = v8;
    if ( v8 )
    {
      *((_DWORD *)v8 + 2) = 0;
      *((_OWORD *)v8 + 1) = 0;
      *((_OWORD *)v8 + 2) = 0;
      *((_QWORD *)v8 + 6) = 0;
      v8[56] = 0;
      *((_DWORD *)v8 + 18) = 0;
      *((_QWORD *)v8 + 10) = 0;
      *(_QWORD *)v8 = &ATL::CComObjectCached<ATL::CComClassFactorySingleton<AuditChannel>>::`vftable';
    }
    v12 = v8;
  }
  catch ( ... )
  {
    v3 = a3;
    v4 = a2;
    v5 = a1;
    v7 = -2147024882;
    v9 = v12;
  }
  if ( v9 )
  {
    *((_QWORD *)v9 + 8) = v5;
    v7 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v9 + 16));
    v10 = v9 + 56;
    if ( v7 < 0 || (*v10 = 1, (v7 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v9)(v9, v4, v3)) != 0) )
    {
      *((_DWORD *)v9 + 2) = -1073741823;
      *(_QWORD *)v9 = &ATL::CComClassFactorySingleton<AuditChannel>::`vftable';
      v11 = *((_QWORD *)v9 + 10);
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
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
0x18000f960  mov     [rsp+arg_10], r8
0x18000f965  mov     [rsp+arg_8], rdx
0x18000f96a  mov     [rsp+arg_0], rcx
0x18000f96f  push    rbx
0x18000f970  push    rsi
0x18000f971  push    r12
0x18000f973  push    r13
0x18000f975  push    r14
0x18000f977  push    r15
0x18000f979  sub     rsp, 38h
0x18000f97d  mov     r15, r8
0x18000f980  mov     r12, rdx
0x18000f983  mov     r14, rcx
0x18000f986  test    r8, r8
0x18000f989  jnz     short loc_18000F995
0x18000f98b  mov     eax, 80004003h
0x18000f990  jmp     loc_18000FAA2
0x18000f995  mov     qword ptr [r8], 0
0x18000f99c  mov     esi, 8007000Eh
0x18000f9a1  mov     [rsp+68h+arg_18], esi
0x18000f9a8  mov     [rsp+68h+var_48], 0
0x18000f9b1  mov     ecx, 58h ; 'X'; Size
0x18000f9b6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f9bb  mov     rbx, rax
0x18000f9be  test    rbx, rbx
0x18000f9c1  jz      short loc_18000F9EF
0x18000f9c3  mov     dword ptr [rax+8], 0
0x18000f9ca  xorps   xmm0, xmm0
0x18000f9cd  xor     eax, eax
0x18000f9cf  movups  xmmword ptr [rbx+10h], xmm0
0x18000f9d3  movups  xmmword ptr [rbx+20h], xmm0
0x18000f9d7  mov     [rbx+30h], rax
0x18000f9db  mov     [rbx+38h], al
0x18000f9de  mov     [rbx+48h], eax
0x18000f9e1  mov     [rbx+50h], rax
0x18000f9e5  lea     rax, ??_7?$CComObjectCached@V?$CComClassFactorySingleton@VAuditChannel@@@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactorySingleton<AuditChannel>>::`vftable'
0x18000f9ec  mov     [rbx], rax
0x18000f9ef  mov     [rsp+68h+var_48], rbx
0x18000f9f4  jmp     short loc_18000FA14
0x18000f9f6  mov     r15, [rsp+68h+arg_10]
0x18000f9fe  mov     r12, [rsp+68h+arg_8]
0x18000fa03  mov     r14, [rsp+68h+arg_0]
0x18000fa08  mov     esi, [rsp+68h+arg_18]
0x18000fa0f  mov     rbx, [rsp+68h+var_48]
0x18000fa14  test    rbx, rbx
0x18000fa17  jz      loc_18000FAA0
0x18000fa1d  mov     [rbx+40h], r14
0x18000fa21  lea     rcx, [rbx+10h]; this
0x18000fa25  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000fa2a  mov     esi, eax
0x18000fa2c  lea     r14, [rbx+38h]
0x18000fa30  test    eax, eax
0x18000fa32  js      short loc_18000FA52
0x18000fa34  mov     byte ptr [r14], 1
0x18000fa38  mov     rax, [rbx]
0x18000fa3b  mov     r8, r15
0x18000fa3e  mov     rdx, r12
0x18000fa41  mov     rcx, rbx
0x18000fa44  mov     rax, [rax]
0x18000fa47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa4c  mov     esi, eax
0x18000fa4e  test    eax, eax
0x18000fa50  jz      short loc_18000FAA0
0x18000fa52  mov     dword ptr [rbx+8], 0C0000001h
0x18000fa59  lea     rax, ??_7?$CComClassFactorySingleton@VAuditChannel@@@ATL@@6B@; const ATL::CComClassFactorySingleton<AuditChannel>::`vftable'
0x18000fa60  mov     [rbx], rax
0x18000fa63  mov     rcx, [rbx+50h]
0x18000fa67  test    rcx, rcx
0x18000fa6a  jz      short loc_18000FA79
0x18000fa6c  mov     rax, [rcx]
0x18000fa6f  mov     rax, [rax+10h]
0x18000fa73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa78  nop
0x18000fa79  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x18000fa80  mov     [rbx], rax
0x18000fa83  cmp     byte ptr [r14], 0
0x18000fa87  jz      short loc_18000FA97
0x18000fa89  mov     byte ptr [r14], 0
0x18000fa8d  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000fa91  call    cs:__imp_DeleteCriticalSection
0x18000fa97  mov     rcx, rbx; Block
0x18000fa9a  call    cs:__imp_free
0x18000faa0  mov     eax, esi
0x18000faa2  add     rsp, 38h
0x18000faa6  pop     r15
0x18000faa8  pop     r14
0x18000faaa  pop     r13
0x18000faac  pop     r12
0x18000faae  pop     rsi
0x18000faaf  pop     rbx
0x18000fab0  retn
```
