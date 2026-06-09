# ATL::CComCreator<ATL::CComObjectCached<CComDllClassFactorySingleton<CAccStore>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000fd50`
- end: `0x18000fee4`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@V?$CComDllClassFactorySingleton@VCAccStore@@@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `404`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001370`
- `0x18000d38c`
- `0x18000d5a4`
- `0x18000fd50`
- `0x18001017c`
- `0x180014010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000fec5`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000fec5`
- `KERNEL32!DeleteCriticalSection` at `0x18000fe95`
- `KERNEL32!DeleteCriticalSection` at `0x18000febc`
- `KERNEL32!DeleteCriticalSection` at `0x18000fe95`
- `KERNEL32!DeleteCriticalSection` at `0x18000febc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<CComDllClassFactorySingleton<CAccStore>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v7; // esi
  char *v8; // rax
  char *v9; // rdi
  int v10; // eax
  _BYTE *v11; // r14

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = (char *)operator new(0xD0u);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *((_OWORD *)v8 + 1) = 0;
    *((_OWORD *)v8 + 2) = 0;
    *((_QWORD *)v8 + 6) = 0;
    v8[56] = 0;
    *(_QWORD *)v8 = &ATL::CComClassFactorySingleton<CAccStore>::`vftable';
    CAccStore::CAccStore((CAccStore *)(v8 + 72));
    *((_DWORD *)v9 + 36) = 0;
    *((_QWORD *)v9 + 9) = &ATL::CComContainedObjectGlobal<CAccStore>::`vftable';
    *((_QWORD *)v9 + 19) = v9;
    *(_QWORD *)v9 = &ATL::CComObjectCached<CComDllClassFactorySingleton<CAccStore>>::`vftable';
    *((_OWORD *)v9 + 10) = 0;
    *((_OWORD *)v9 + 11) = 0;
    *((_QWORD *)v9 + 24) = 0;
    v9[200] = 0;
  }
  else
  {
    v9 = 0;
  }
  if ( v9 )
  {
    *((_QWORD *)v9 + 8) = a1;
    v10 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v9 + 16));
    v11 = v9 + 56;
    if ( v10 >= 0 )
    {
      *v11 = 1;
      v10 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v9 + 160));
      if ( v10 >= 0 )
        v9[200] = 1;
    }
    v7 = 0;
    if ( v10 < 0 )
      v7 = v10;
    if ( v7 || (v7 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v9)(v9, a2, a3)) != 0 )
    {
      *(_QWORD *)v9 = &ATL::CComObjectCached<CComDllClassFactorySingleton<CAccStore>>::`vftable';
      *((_DWORD *)v9 + 2) = 1;
      if ( v9[200] )
      {
        v9[200] = 0;
        DeleteCriticalSection((LPCRITICAL_SECTION)v9 + 4);
      }
      *((_QWORD *)v9 + 9) = &ATL::CComObjectGlobal<CAccStore>::`vftable';
      CAccStore::~CAccStore((CAccStore *)(v9 + 72));
      if ( *v11 )
      {
        *v11 = 0;
        DeleteCriticalSection((LPCRITICAL_SECTION)(v9 + 16));
      }
      operator delete(v9);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18000fd50  mov     [rsp+arg_0], rbx
0x18000fd55  mov     [rsp+arg_8], rbp
0x18000fd5a  push    rsi
0x18000fd5b  push    rdi
0x18000fd5c  push    r12
0x18000fd5e  push    r14
0x18000fd60  push    r15
0x18000fd62  sub     rsp, 20h
0x18000fd66  mov     r15, r8
0x18000fd69  mov     r12, rdx
0x18000fd6c  mov     rbp, rcx
0x18000fd6f  test    r8, r8
0x18000fd72  jnz     short loc_18000FD7E
0x18000fd74  mov     eax, 80004003h
0x18000fd79  jmp     loc_18000FECD
0x18000fd7e  mov     qword ptr [r8], 0
0x18000fd85  mov     esi, 8007000Eh
0x18000fd8a  mov     ecx, 0D0h; Size
0x18000fd8f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fd94  mov     rdi, rax
0x18000fd97  mov     [rsp+48h+arg_10], rax
0x18000fd9c  lea     r14, ??_7?$CComObjectCached@V?$CComDllClassFactorySingleton@VCAccStore@@@@@ATL@@6B@; const ATL::CComObjectCached<CComDllClassFactorySingleton<CAccStore>>::`vftable'
0x18000fda3  test    rax, rax
0x18000fda6  jz      short loc_18000FE17
0x18000fda8  mov     dword ptr [rax+8], 0
0x18000fdaf  xorps   xmm0, xmm0
0x18000fdb2  xor     eax, eax
0x18000fdb4  movups  xmmword ptr [rdi+10h], xmm0
0x18000fdb8  movups  xmmword ptr [rdi+20h], xmm0
0x18000fdbc  mov     [rdi+30h], rax
0x18000fdc0  mov     [rdi+38h], al
0x18000fdc3  lea     rax, ??_7?$CComClassFactorySingleton@VCAccStore@@@ATL@@6B@; const ATL::CComClassFactorySingleton<CAccStore>::`vftable'
0x18000fdca  mov     [rdi], rax
0x18000fdcd  lea     rcx, [rdi+48h]; this
0x18000fdd1  call    ??0CAccStore@@QEAA@XZ; CAccStore::CAccStore(void)
0x18000fdd6  mov     dword ptr [rdi+90h], 0
0x18000fde0  lea     rax, ??_7?$CComContainedObjectGlobal@VCAccStore@@@ATL@@6B@; const ATL::CComContainedObjectGlobal<CAccStore>::`vftable'
0x18000fde7  mov     [rdi+48h], rax
0x18000fdeb  mov     [rdi+98h], rdi
0x18000fdf2  mov     [rdi], r14
0x18000fdf5  xorps   xmm0, xmm0
0x18000fdf8  xor     eax, eax
0x18000fdfa  movups  xmmword ptr [rdi+0A0h], xmm0
0x18000fe01  movups  xmmword ptr [rdi+0B0h], xmm0
0x18000fe08  mov     [rdi+0C0h], rax
0x18000fe0f  mov     [rdi+0C8h], al
0x18000fe15  jmp     short loc_18000FE19
0x18000fe17  xor     edi, edi
0x18000fe19  test    rdi, rdi
0x18000fe1c  jz      loc_18000FECB
0x18000fe22  mov     [rdi+40h], rbp
0x18000fe26  lea     rcx, [rdi+10h]; this
0x18000fe2a  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000fe2f  lea     rbx, [rdi+0A0h]
0x18000fe36  lea     r14, [rdi+38h]
0x18000fe3a  test    eax, eax
0x18000fe3c  js      short loc_18000FE52
0x18000fe3e  mov     byte ptr [r14], 1
0x18000fe42  mov     rcx, rbx; this
0x18000fe45  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x18000fe4a  test    eax, eax
0x18000fe4c  js      short loc_18000FE52
0x18000fe4e  mov     byte ptr [rbx+28h], 1
0x18000fe52  xor     esi, esi
0x18000fe54  test    eax, eax
0x18000fe56  cmovs   esi, eax
0x18000fe59  test    esi, esi
0x18000fe5b  jnz     short loc_18000FE77
0x18000fe5d  mov     rax, [rdi]
0x18000fe60  mov     r8, r15
0x18000fe63  mov     rdx, r12
0x18000fe66  mov     rcx, rdi
0x18000fe69  mov     rax, [rax]
0x18000fe6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe71  mov     esi, eax
0x18000fe73  test    eax, eax
0x18000fe75  jz      short loc_18000FECB
0x18000fe77  lea     rax, ??_7?$CComObjectCached@V?$CComDllClassFactorySingleton@VCAccStore@@@@@ATL@@6B@; const ATL::CComObjectCached<CComDllClassFactorySingleton<CAccStore>>::`vftable'
0x18000fe7e  mov     [rdi], rax
0x18000fe81  mov     dword ptr [rdi+8], 1
0x18000fe88  cmp     byte ptr [rbx+28h], 0
0x18000fe8c  jz      short loc_18000FE9B
0x18000fe8e  mov     byte ptr [rbx+28h], 0
0x18000fe92  mov     rcx, rbx; lpCriticalSection
0x18000fe95  call    cs:__imp_DeleteCriticalSection
0x18000fe9b  lea     rcx, [rdi+48h]; this
0x18000fe9f  lea     rax, ??_7?$CComObjectGlobal@VCAccStore@@@ATL@@6B@; const ATL::CComObjectGlobal<CAccStore>::`vftable'
0x18000fea6  mov     [rcx], rax
0x18000fea9  call    ??1CAccStore@@QEAA@XZ; CAccStore::~CAccStore(void)
0x18000feae  cmp     byte ptr [r14], 0
0x18000feb2  jz      short loc_18000FEC2
0x18000feb4  mov     byte ptr [r14], 0
0x18000feb8  lea     rcx, [rdi+10h]; lpCriticalSection
0x18000febc  call    cs:__imp_DeleteCriticalSection
0x18000fec2  mov     rcx, rdi
0x18000fec5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000fecb  mov     eax, esi
0x18000fecd  mov     rbx, [rsp+48h+arg_0]
0x18000fed2  mov     rbp, [rsp+48h+arg_8]
0x18000fed7  add     rsp, 20h
0x18000fedb  pop     r15
0x18000fedd  pop     r14
0x18000fedf  pop     r12
0x18000fee1  pop     rdi
0x18000fee2  pop     rsi
0x18000fee3  retn
```
