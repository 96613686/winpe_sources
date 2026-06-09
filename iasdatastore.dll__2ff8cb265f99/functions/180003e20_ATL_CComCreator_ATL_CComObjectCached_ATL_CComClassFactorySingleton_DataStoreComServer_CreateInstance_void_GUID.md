# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactorySingleton<DataStoreComServer>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003e20`
- end: `0x180003f71`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@V?$CComClassFactorySingleton@VDataStoreComServer@@@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `337`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002310`
- `0x180003e20`
- `0x18000433c`
- `0x180010010`

## import_xrefs

- `msvcrt!free` at `0x180003f5a`
- `msvcrt!free` at `0x180003f5a`
- `KERNEL32!DeleteCriticalSection` at `0x180003f51`
- `KERNEL32!DeleteCriticalSection` at `0x180003f51`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactorySingleton<DataStoreComServer>>>::CreateInstance(
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
      *(_QWORD *)v8 = &ATL::CComObjectCached<ATL::CComClassFactorySingleton<DataStoreComServer>>::`vftable';
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
      *(_QWORD *)v9 = &ATL::CComClassFactorySingleton<DataStoreComServer>::`vftable';
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
0x180003e20  mov     [rsp+arg_10], r8
0x180003e25  mov     [rsp+arg_8], rdx
0x180003e2a  mov     [rsp+arg_0], rcx
0x180003e2f  push    rbx
0x180003e30  push    rsi
0x180003e31  push    r12
0x180003e33  push    r13
0x180003e35  push    r14
0x180003e37  push    r15
0x180003e39  sub     rsp, 38h
0x180003e3d  mov     r15, r8
0x180003e40  mov     r12, rdx
0x180003e43  mov     r14, rcx
0x180003e46  test    r8, r8
0x180003e49  jnz     short loc_180003E55
0x180003e4b  mov     eax, 80004003h
0x180003e50  jmp     loc_180003F62
0x180003e55  mov     qword ptr [r8], 0
0x180003e5c  mov     esi, 8007000Eh
0x180003e61  mov     [rsp+68h+arg_18], esi
0x180003e68  mov     [rsp+68h+var_48], 0
0x180003e71  mov     ecx, 58h ; 'X'; Size
0x180003e76  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003e7b  mov     rbx, rax
0x180003e7e  test    rbx, rbx
0x180003e81  jz      short loc_180003EAF
0x180003e83  mov     dword ptr [rax+8], 0
0x180003e8a  xorps   xmm0, xmm0
0x180003e8d  xor     eax, eax
0x180003e8f  movups  xmmword ptr [rbx+10h], xmm0
0x180003e93  movups  xmmword ptr [rbx+20h], xmm0
0x180003e97  mov     [rbx+30h], rax
0x180003e9b  mov     [rbx+38h], al
0x180003e9e  mov     [rbx+48h], eax
0x180003ea1  mov     [rbx+50h], rax
0x180003ea5  lea     rax, ??_7?$CComObjectCached@V?$CComClassFactorySingleton@VDataStoreComServer@@@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactorySingleton<DataStoreComServer>>::`vftable'
0x180003eac  mov     [rbx], rax
0x180003eaf  mov     [rsp+68h+var_48], rbx
0x180003eb4  jmp     short loc_180003ED4
0x180003eb6  mov     r15, [rsp+68h+arg_10]
0x180003ebe  mov     r12, [rsp+68h+arg_8]
0x180003ec3  mov     r14, [rsp+68h+arg_0]
0x180003ec8  mov     esi, [rsp+68h+arg_18]
0x180003ecf  mov     rbx, [rsp+68h+var_48]
0x180003ed4  test    rbx, rbx
0x180003ed7  jz      loc_180003F60
0x180003edd  mov     [rbx+40h], r14
0x180003ee1  lea     rcx, [rbx+10h]; this
0x180003ee5  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x180003eea  mov     esi, eax
0x180003eec  lea     r14, [rbx+38h]
0x180003ef0  test    eax, eax
0x180003ef2  js      short loc_180003F12
0x180003ef4  mov     byte ptr [r14], 1
0x180003ef8  mov     rax, [rbx]
0x180003efb  mov     r8, r15
0x180003efe  mov     rdx, r12
0x180003f01  mov     rcx, rbx
0x180003f04  mov     rax, [rax]
0x180003f07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f0c  mov     esi, eax
0x180003f0e  test    eax, eax
0x180003f10  jz      short loc_180003F60
0x180003f12  mov     dword ptr [rbx+8], 0C0000001h
0x180003f19  lea     rax, ??_7?$CComClassFactorySingleton@VDataStoreComServer@@@ATL@@6B@; const ATL::CComClassFactorySingleton<DataStoreComServer>::`vftable'
0x180003f20  mov     [rbx], rax
0x180003f23  mov     rcx, [rbx+50h]
0x180003f27  test    rcx, rcx
0x180003f2a  jz      short loc_180003F39
0x180003f2c  mov     rax, [rcx]
0x180003f2f  mov     rax, [rax+10h]
0x180003f33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f38  nop
0x180003f39  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180003f40  mov     [rbx], rax
0x180003f43  cmp     byte ptr [r14], 0
0x180003f47  jz      short loc_180003F57
0x180003f49  mov     byte ptr [r14], 0
0x180003f4d  lea     rcx, [rbx+10h]; lpCriticalSection
0x180003f51  call    cs:__imp_DeleteCriticalSection
0x180003f57  mov     rcx, rbx; Block
0x180003f5a  call    cs:__imp_free
0x180003f60  mov     eax, esi
0x180003f62  add     rsp, 38h
0x180003f66  pop     r15
0x180003f68  pop     r14
0x180003f6a  pop     r13
0x180003f6c  pop     r12
0x180003f6e  pop     rsi
0x180003f6f  pop     rbx
0x180003f70  retn
```
