# ATL::CComCreator<ATL::CComAggObject<CDict>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000f7e8`
- end: `0x18000f8f4`
- name: `?CreateInstance@?$CComCreator@V?$CComAggObject@VCDict@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `268`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18000f590`

## callees

- `0x180001370`
- `0x180004544`
- `0x1800047ec`
- `0x18000f7e8`
- `0x180014010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000f8d5`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f8d5`
- `KERNEL32!LoadLibraryExW` at `0x18000f87f`
- `KERNEL32!LoadLibraryExW` at `0x18000f87f`

## string_xrefs

- `0x18000f878`: `OLEACCRC.DLL`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComAggObject<CDict>>::CreateInstance(__int64 a1, __int64 a2, _QWORD *a3)
{
  unsigned int v7; // esi
  char *v8; // rax
  _QWORD *v9; // rdi
  HMODULE Library; // rax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = (char *)operator new(0x48u);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    *(_QWORD *)v8 = &ATL::CComAggObject<CDict>::`vftable';
    CDict::CDict((CDict *)(v8 + 16));
    v9[2] = &ATL::CComContainedObject<CDict>::`vftable';
    v9[3] = a1;
    _InterlockedIncrement(&dword_180024B28);
  }
  else
  {
    v9 = 0;
  }
  if ( v9 )
  {
    Library = LoadLibraryExW(L"OLEACCRC.DLL", 0, 2u);
    v9[8] = Library;
    v7 = Library == 0 ? 0x80004005 : 0;
    if ( !Library || (v7 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v9)(v9, a2, a3)) != 0 )
    {
      *v9 = &ATL::CComAggObject<CDict>::`vftable';
      *((_DWORD *)v9 + 2) = 1;
      _InterlockedDecrement(&dword_180024B28);
      CDict::~CDict((CDict *)(v9 + 2));
      operator delete(v9);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18000f7e8  mov     [rsp+arg_0], rbx
0x18000f7ed  mov     [rsp+arg_8], rbp
0x18000f7f2  push    rsi
0x18000f7f3  push    rdi
0x18000f7f4  push    r12
0x18000f7f6  push    r14
0x18000f7f8  push    r15
0x18000f7fa  sub     rsp, 20h
0x18000f7fe  mov     r14, r8
0x18000f801  mov     r15, rdx
0x18000f804  mov     rbp, rcx
0x18000f807  test    r8, r8
0x18000f80a  jnz     short loc_18000F816
0x18000f80c  mov     eax, 80004003h
0x18000f811  jmp     loc_18000F8DD
0x18000f816  mov     qword ptr [r8], 0
0x18000f81d  mov     esi, 8007000Eh
0x18000f822  mov     ecx, 48h ; 'H'; Size
0x18000f827  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f82c  mov     rdi, rax
0x18000f82f  mov     [rsp+48h+arg_10], rax
0x18000f834  lea     r12, ??_7?$CComAggObject@VCDict@@@ATL@@6B@; const ATL::CComAggObject<CDict>::`vftable'
0x18000f83b  test    rax, rax
0x18000f83e  jz      short loc_18000F86B
0x18000f840  mov     dword ptr [rax+8], 0
0x18000f847  mov     [rax], r12
0x18000f84a  lea     rcx, [rax+10h]; this
0x18000f84e  call    ??0CDict@@QEAA@XZ; CDict::CDict(void)
0x18000f853  lea     rax, ??_7?$CComContainedObject@VCDict@@@ATL@@6B@; const ATL::CComContainedObject<CDict>::`vftable'
0x18000f85a  mov     [rdi+10h], rax
0x18000f85e  mov     [rdi+18h], rbp
0x18000f862  lock inc cs:dword_180024B28
0x18000f869  jmp     short loc_18000F86D
0x18000f86b  xor     edi, edi
0x18000f86d  test    rdi, rdi
0x18000f870  jz      short loc_18000F8DB
0x18000f872  xor     edx, edx; hFile
0x18000f874  lea     r8d, [rdx+2]; dwFlags
0x18000f878  lea     rcx, aOleaccrcDll; "OLEACCRC.DLL"
0x18000f87f  call    cs:__imp_LoadLibraryExW
0x18000f885  mov     rcx, rax
0x18000f888  mov     [rdi+40h], rax
0x18000f88c  neg     rax
0x18000f88f  sbb     esi, esi
0x18000f891  not     esi
0x18000f893  and     esi, 80004005h
0x18000f899  test    rcx, rcx
0x18000f89c  jz      short loc_18000F8B8
0x18000f89e  mov     rax, [rdi]
0x18000f8a1  mov     r8, r14
0x18000f8a4  mov     rdx, r15
0x18000f8a7  mov     rcx, rdi
0x18000f8aa  mov     rax, [rax]
0x18000f8ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8b2  mov     esi, eax
0x18000f8b4  test    eax, eax
0x18000f8b6  jz      short loc_18000F8DB
0x18000f8b8  mov     [rdi], r12
0x18000f8bb  mov     dword ptr [rdi+8], 1
0x18000f8c2  lock dec cs:dword_180024B28
0x18000f8c9  lea     rcx, [rdi+10h]; this
0x18000f8cd  call    ??1CDict@@QEAA@XZ; CDict::~CDict(void)
0x18000f8d2  mov     rcx, rdi
0x18000f8d5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f8db  mov     eax, esi
0x18000f8dd  mov     rbx, [rsp+48h+arg_0]
0x18000f8e2  mov     rbp, [rsp+48h+arg_8]
0x18000f8e7  add     rsp, 20h
0x18000f8eb  pop     r15
0x18000f8ed  pop     r14
0x18000f8ef  pop     r12
0x18000f8f1  pop     rdi
0x18000f8f2  pop     rsi
0x18000f8f3  retn
```
