# ATL::CComCreator<ATL::CComObject<CAccServerDocMgr>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000fa4c`
- end: `0x18000fb3c`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCAccServerDocMgr@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `240`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000f2f0`

## callees

- `0x180001370`
- `0x18000cac8`
- `0x18000fa4c`
- `0x180014010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000fb21`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000fb21`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CAccServerDocMgr>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // esi
  CAccServerDocMgr *v7; // rax
  CAccServerDocMgr *v8; // rbx
  int v9; // ecx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = (CAccServerDocMgr *)operator new(0x28u);
  v8 = v7;
  if ( v7 )
  {
    *((_DWORD *)v7 + 2) = 0;
    *((_QWORD *)v7 + 2) = 0;
    *((_QWORD *)v7 + 3) = 0;
    *((_QWORD *)v7 + 4) = 0;
    *(_QWORD *)v7 = &ATL::CComObject<CAccServerDocMgr>::`vftable';
    _InterlockedIncrement(&dword_180024B28);
    v9 = *((_DWORD *)v7 + 2);
    if ( v9 != 0x7FFFFFFF )
    {
      *((_DWORD *)v7 + 2) = v9 + 1;
      if ( v9 != 2147483646 )
        *((_DWORD *)v7 + 2) = v9;
    }
    v6 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v7)(v7, a2, a3);
    if ( v6 )
    {
      *(_QWORD *)v8 = &ATL::CComObject<CAccServerDocMgr>::`vftable';
      *((_DWORD *)v8 + 2) = 1;
      _InterlockedDecrement(&dword_180024B28);
      CAccServerDocMgr::~CAccServerDocMgr(v8);
      operator delete(v8);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18000fa4c  mov     [rsp+arg_8], rbx
0x18000fa51  mov     [rsp+arg_10], rbp
0x18000fa56  push    rsi
0x18000fa57  push    rdi
0x18000fa58  push    r15
0x18000fa5a  sub     rsp, 20h
0x18000fa5e  mov     rdi, r8
0x18000fa61  mov     rbp, rdx
0x18000fa64  test    r8, r8
0x18000fa67  jnz     short loc_18000FA73
0x18000fa69  mov     eax, 80004003h
0x18000fa6e  jmp     loc_18000FB29
0x18000fa73  mov     ecx, 28h ; '('; Size
0x18000fa78  mov     qword ptr [r8], 0
0x18000fa7f  mov     esi, 8007000Eh
0x18000fa84  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fa89  mov     [rsp+38h+arg_0], rax
0x18000fa8e  mov     rbx, rax
0x18000fa91  test    rax, rax
0x18000fa94  jz      loc_18000FB27
0x18000fa9a  mov     dword ptr [rax+8], 0
0x18000faa1  lea     r15, ??_7?$CComObject@VCAccServerDocMgr@@@ATL@@6B@; const ATL::CComObject<CAccServerDocMgr>::`vftable'
0x18000faa8  mov     qword ptr [rax+10h], 0
0x18000fab0  mov     qword ptr [rax+18h], 0
0x18000fab8  mov     qword ptr [rax+20h], 0
0x18000fac0  mov     [rax], r15
0x18000fac3  lock inc cs:dword_180024B28
0x18000faca  test    rax, rax
0x18000facd  jz      short loc_18000FB27
0x18000facf  mov     ecx, [rax+8]
0x18000fad2  cmp     ecx, 7FFFFFFFh
0x18000fad8  jz      short loc_18000FAEB
0x18000fada  lea     eax, [rcx+1]
0x18000fadd  mov     [rbx+8], eax
0x18000fae0  cmp     ecx, 7FFFFFFEh
0x18000fae6  jz      short loc_18000FAEB
0x18000fae8  mov     [rbx+8], ecx
0x18000faeb  mov     rax, [rbx]
0x18000faee  mov     r8, rdi
0x18000faf1  mov     rdx, rbp
0x18000faf4  mov     rcx, rbx
0x18000faf7  mov     rax, [rax]
0x18000fafa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000faff  mov     esi, eax
0x18000fb01  test    eax, eax
0x18000fb03  jz      short loc_18000FB27
0x18000fb05  mov     [rbx], r15
0x18000fb08  mov     rcx, rbx; this
0x18000fb0b  mov     dword ptr [rbx+8], 1
0x18000fb12  lock dec cs:dword_180024B28
0x18000fb19  call    ??1CAccServerDocMgr@@QEAA@XZ; CAccServerDocMgr::~CAccServerDocMgr(void)
0x18000fb1e  mov     rcx, rbx
0x18000fb21  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000fb27  mov     eax, esi
0x18000fb29  mov     rbx, [rsp+38h+arg_8]
0x18000fb2e  mov     rbp, [rsp+38h+arg_10]
0x18000fb33  add     rsp, 20h
0x18000fb37  pop     r15
0x18000fb39  pop     rdi
0x18000fb3a  pop     rsi
0x18000fb3b  retn
```
