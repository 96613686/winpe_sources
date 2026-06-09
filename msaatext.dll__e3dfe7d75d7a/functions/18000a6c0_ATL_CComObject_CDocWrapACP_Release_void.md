# ATL::CComObject<CDocWrapACP>::Release(void)

- ea: `0x18000a6c0`
- end: `0x18000a772`
- name: `?Release@?$CComObject@VCDocWrapACP@@@ATL@@UEAAKXZ`
- size: `178`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000a780`
- `0x18000a790`
- `0x18000a7a0`
- `0x18000a7b0`
- `0x18000a7c0`
- `0x18000a7d0`

## callees

- `0x1800055b4`
- `0x18000a6c0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000a758`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a758`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CDocWrapACP>::Release(_DWORD *a1)
{
  int v1; // edi
  unsigned int v3; // edi

  v1 = a1[20];
  if ( v1 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v3 = v1 - 1;
    a1[20] = v3;
    if ( !v3 )
    {
      _InterlockedIncrement(&dword_180024B28);
      if ( a1 )
      {
        a1[20] = 1;
        *(_QWORD *)a1 = &ATL::CComObject<CDocWrapACP>::`vftable'{for `ITextStoreACP'};
        *((_QWORD *)a1 + 1) = &ATL::CComObject<CDocWrapACP>::`vftable'{for `ITextStoreACPEx'};
        *((_QWORD *)a1 + 2) = &ATL::CComObject<CDocWrapACP>::`vftable'{for `IClonableWrapper'};
        *((_QWORD *)a1 + 3) = &ATL::CComObject<CDocWrapACP>::`vftable'{for `IInternalDocWrap'};
        *((_QWORD *)a1 + 4) = &ATL::CComObject<CDocWrapACP>::`vftable'{for `ICoCreateLocally'};
        *((_QWORD *)a1 + 5) = &ATL::CComObject<CDocWrapACP>::`vftable'{for `CVersionInfo'};
        *((_QWORD *)a1 + 9) = &ATL::CComObject<CDocWrapACP>::`vftable'{for `IServiceProvider'};
        _InterlockedDecrement(&dword_180024B28);
        CDocWrapBase<DocTraitsACP>::~CDocWrapBase<DocTraitsACP>((__int64)a1);
        operator delete(a1);
      }
      _InterlockedDecrement(&dword_180024B28);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000a6c0  mov     [rsp+arg_0], rbx
0x18000a6c5  push    rdi
0x18000a6c6  sub     rsp, 20h
0x18000a6ca  mov     edi, [rcx+50h]
0x18000a6cd  mov     rbx, rcx
0x18000a6d0  cmp     edi, 7FFFFFFFh
0x18000a6d6  jnz     short loc_18000A6E2
0x18000a6d8  mov     edi, 7FFFFFFEh
0x18000a6dd  jmp     loc_18000A765
0x18000a6e2  sub     edi, 1
0x18000a6e5  mov     [rcx+50h], edi
0x18000a6e8  jnz     short loc_18000A765
0x18000a6ea  lock inc cs:dword_180024B28
0x18000a6f1  test    rbx, rbx
0x18000a6f4  jz      short loc_18000A75E
0x18000a6f6  lea     rax, ??_7?$CComObject@VCDocWrapACP@@@ATL@@6BITextStoreACP@@@; const ATL::CComObject<CDocWrapACP>::`vftable'{for `ITextStoreACP'}
0x18000a6fd  mov     dword ptr [rcx+50h], 1
0x18000a704  mov     [rcx], rax
0x18000a707  lea     rax, ??_7?$CComObject@VCDocWrapACP@@@ATL@@6BITextStoreACPEx@@@; const ATL::CComObject<CDocWrapACP>::`vftable'{for `ITextStoreACPEx'}
0x18000a70e  mov     [rcx+8], rax
0x18000a712  lea     rax, ??_7?$CComObject@VCDocWrapACP@@@ATL@@6BIClonableWrapper@@@; const ATL::CComObject<CDocWrapACP>::`vftable'{for `IClonableWrapper'}
0x18000a719  mov     [rcx+10h], rax
0x18000a71d  lea     rax, ??_7?$CComObject@VCDocWrapACP@@@ATL@@6BIInternalDocWrap@@@; const ATL::CComObject<CDocWrapACP>::`vftable'{for `IInternalDocWrap'}
0x18000a724  mov     [rcx+18h], rax
0x18000a728  lea     rax, ??_7?$CComObject@VCDocWrapACP@@@ATL@@6BICoCreateLocally@@@; const ATL::CComObject<CDocWrapACP>::`vftable'{for `ICoCreateLocally'}
0x18000a72f  mov     [rcx+20h], rax
0x18000a733  lea     rax, ??_7?$CComObject@VCDocWrapACP@@@ATL@@6BCVersionInfo@@@; const ATL::CComObject<CDocWrapACP>::`vftable'{for `CVersionInfo'}
0x18000a73a  mov     [rcx+28h], rax
0x18000a73e  lea     rax, ??_7?$CComObject@VCDocWrapACP@@@ATL@@6BIServiceProvider@@@; const ATL::CComObject<CDocWrapACP>::`vftable'{for `IServiceProvider'}
0x18000a745  mov     [rcx+48h], rax
0x18000a749  lock dec cs:dword_180024B28
0x18000a750  call    ??1?$CDocWrapBase@VDocTraitsACP@@@@QEAA@XZ; CDocWrapBase<DocTraitsACP>::~CDocWrapBase<DocTraitsACP>(void)
0x18000a755  mov     rcx, rbx
0x18000a758  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a75e  lock dec cs:dword_180024B28
0x18000a765  mov     rbx, [rsp+28h+arg_0]
0x18000a76a  mov     eax, edi
0x18000a76c  add     rsp, 20h
0x18000a770  pop     rdi
0x18000a771  retn
```
