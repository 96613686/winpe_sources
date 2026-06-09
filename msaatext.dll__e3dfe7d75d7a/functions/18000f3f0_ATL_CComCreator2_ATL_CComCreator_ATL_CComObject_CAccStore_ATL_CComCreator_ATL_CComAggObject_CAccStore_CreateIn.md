# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CAccStore>>,ATL::CComCreator<ATL::CComAggObject<CAccStore>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000f3f0`
- end: `0x18000f580`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCAccStore@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCAccStore@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `400`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001370`
- `0x18000d38c`
- `0x18000d5a4`
- `0x18000f3f0`
- `0x180014010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000f561`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f561`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CAccStore>>,ATL::CComCreator<ATL::CComAggObject<CAccStore>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // edi
  CAccStore *v7; // rax
  CAccStore *v8; // rbx
  int v9; // ecx
  CAccStore *v10; // rcx
  _DWORD *v11; // rax
  _QWORD *v12; // rsi

  if ( !a1 )
  {
    if ( a3 )
    {
      *a3 = 0;
      v6 = -2147024882;
      v7 = (CAccStore *)operator new(0x48u);
      v8 = v7;
      if ( v7 )
      {
        CAccStore::CAccStore(v7);
        *(_QWORD *)v8 = &ATL::CComObject<CAccStore>::`vftable';
        _InterlockedIncrement(&dword_180024B28);
      }
      else
      {
        v8 = 0;
      }
      if ( v8 )
      {
        v9 = *((_DWORD *)v8 + 2);
        if ( v9 != 0x7FFFFFFF )
        {
          *((_DWORD *)v8 + 2) = v9 + 1;
          if ( v9 != 2147483646 )
            *((_DWORD *)v8 + 2) = v9;
        }
        v6 = (**(__int64 (__fastcall ***)(CAccStore *, __int64, _QWORD *))v8)(v8, a2, a3);
        if ( v6 )
        {
          *(_QWORD *)v8 = &ATL::CComObject<CAccStore>::`vftable';
          *((_DWORD *)v8 + 2) = 1;
          _InterlockedDecrement(&dword_180024B28);
          CAccStore::~CAccStore(v8);
          v10 = v8;
LABEL_20:
          operator delete(v10);
          return v6;
        }
      }
      return v6;
    }
    return (unsigned int)-2147467261;
  }
  if ( !a3 )
    return (unsigned int)-2147467261;
  *a3 = 0;
  v6 = -2147024882;
  v11 = operator new(0x58u);
  v12 = v11;
  if ( v11 )
  {
    v11[2] = 0;
    *(_QWORD *)v11 = &ATL::CComAggObject<CAccStore>::`vftable';
    CAccStore::CAccStore((CAccStore *)(v11 + 4));
    v12[2] = &ATL::CComContainedObject<CAccStore>::`vftable';
    v12[3] = a1;
    _InterlockedIncrement(&dword_180024B28);
  }
  else
  {
    v12 = 0;
  }
  if ( v12 )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v12)(v12, a2, a3);
    if ( v6 )
    {
      *v12 = &ATL::CComAggObject<CAccStore>::`vftable';
      *((_DWORD *)v12 + 2) = 1;
      _InterlockedDecrement(&dword_180024B28);
      CAccStore::~CAccStore((CAccStore *)(v12 + 2));
      v10 = (CAccStore *)v12;
      goto LABEL_20;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18000f3f0  mov     [rsp+arg_8], rbx
0x18000f3f5  mov     [rsp+arg_10], rbp
0x18000f3fa  push    rsi
0x18000f3fb  push    rdi
0x18000f3fc  push    r13
0x18000f3fe  push    r14
0x18000f400  push    r15
0x18000f402  sub     rsp, 20h
0x18000f406  mov     r14, r8
0x18000f409  mov     r15, rdx
0x18000f40c  mov     rbp, rcx
0x18000f40f  test    rcx, rcx
0x18000f412  jnz     loc_18000F4BF
0x18000f418  test    r8, r8
0x18000f41b  jz      loc_18000F4C4
0x18000f421  mov     [r8], rcx
0x18000f424  mov     edi, 8007000Eh
0x18000f429  lea     ecx, [rbp+48h]; Size
0x18000f42c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f431  mov     rbx, rax
0x18000f434  mov     [rsp+48h+arg_0], rax
0x18000f439  lea     rsi, ??_7?$CComObject@VCAccStore@@@ATL@@6B@; const ATL::CComObject<CAccStore>::`vftable'
0x18000f440  test    rax, rax
0x18000f443  jz      short loc_18000F459
0x18000f445  mov     rcx, rax; this
0x18000f448  call    ??0CAccStore@@QEAA@XZ; CAccStore::CAccStore(void)
0x18000f44d  mov     [rbx], rsi
0x18000f450  lock inc cs:dword_180024B28
0x18000f457  jmp     short loc_18000F45B
0x18000f459  xor     ebx, ebx
0x18000f45b  test    rbx, rbx
0x18000f45e  jz      loc_18000F567
0x18000f464  mov     ecx, [rbx+8]
0x18000f467  cmp     ecx, 7FFFFFFFh
0x18000f46d  jz      short loc_18000F480
0x18000f46f  lea     eax, [rcx+1]
0x18000f472  mov     [rbx+8], eax
0x18000f475  cmp     ecx, 7FFFFFFEh
0x18000f47b  jz      short loc_18000F480
0x18000f47d  mov     [rbx+8], ecx
0x18000f480  mov     rax, [rbx]
0x18000f483  mov     r8, r14
0x18000f486  mov     rdx, r15
0x18000f489  mov     rcx, rbx
0x18000f48c  mov     rax, [rax]
0x18000f48f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f494  mov     edi, eax
0x18000f496  test    eax, eax
0x18000f498  jz      loc_18000F567
0x18000f49e  mov     [rbx], rsi
0x18000f4a1  mov     dword ptr [rbx+8], 1
0x18000f4a8  lock dec cs:dword_180024B28
0x18000f4af  mov     rcx, rbx; this
0x18000f4b2  call    ??1CAccStore@@QEAA@XZ; CAccStore::~CAccStore(void)
0x18000f4b7  mov     rcx, rbx
0x18000f4ba  jmp     loc_18000F561
0x18000f4bf  test    r14, r14
0x18000f4c2  jnz     short loc_18000F4CE
0x18000f4c4  mov     edi, 80004003h
0x18000f4c9  jmp     loc_18000F567
0x18000f4ce  mov     qword ptr [r8], 0
0x18000f4d5  mov     edi, 8007000Eh
0x18000f4da  mov     ecx, 58h ; 'X'; Size
0x18000f4df  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f4e4  mov     rsi, rax
0x18000f4e7  mov     [rsp+48h+arg_0], rax
0x18000f4ec  lea     r13, ??_7?$CComAggObject@VCAccStore@@@ATL@@6B@; const ATL::CComAggObject<CAccStore>::`vftable'
0x18000f4f3  test    rax, rax
0x18000f4f6  jz      short loc_18000F523
0x18000f4f8  mov     dword ptr [rax+8], 0
0x18000f4ff  mov     [rax], r13
0x18000f502  lea     rcx, [rax+10h]; this
0x18000f506  call    ??0CAccStore@@QEAA@XZ; CAccStore::CAccStore(void)
0x18000f50b  lea     rax, ??_7?$CComContainedObject@VCAccStore@@@ATL@@6B@; const ATL::CComContainedObject<CAccStore>::`vftable'
0x18000f512  mov     [rsi+10h], rax
0x18000f516  mov     [rsi+18h], rbp
0x18000f51a  lock inc cs:dword_180024B28
0x18000f521  jmp     short loc_18000F525
0x18000f523  xor     esi, esi
0x18000f525  test    rsi, rsi
0x18000f528  jz      short loc_18000F567
0x18000f52a  mov     rax, [rsi]
0x18000f52d  mov     r8, r14
0x18000f530  mov     rdx, r15
0x18000f533  mov     rcx, rsi
0x18000f536  mov     rax, [rax]
0x18000f539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f53e  mov     edi, eax
0x18000f540  test    eax, eax
0x18000f542  jz      short loc_18000F567
0x18000f544  mov     [rsi], r13
0x18000f547  mov     dword ptr [rsi+8], 1
0x18000f54e  lock dec cs:dword_180024B28
0x18000f555  lea     rcx, [rsi+10h]; this
0x18000f559  call    ??1CAccStore@@QEAA@XZ; CAccStore::~CAccStore(void)
0x18000f55e  mov     rcx, rsi
0x18000f561  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f567  mov     eax, edi
0x18000f569  mov     rbx, [rsp+48h+arg_8]
0x18000f56e  mov     rbp, [rsp+48h+arg_10]
0x18000f573  add     rsp, 20h
0x18000f577  pop     r15
0x18000f579  pop     r14
0x18000f57b  pop     r13
0x18000f57d  pop     rdi
0x18000f57e  pop     rsi
0x18000f57f  retn
```
