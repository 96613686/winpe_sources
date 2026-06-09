# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CHHCollectionWrapper>>,ATL::CComCreator<ATL::CComAggObject<CHHCollectionWrapper>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180003a40`
- end: `0x180003b27`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCHHCollectionWrapper@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCHHCollectionWrapper@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `231`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180001140`
- `0x180003a40`
- `0x180003d60`
- `0x18000b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180003b12`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003b12`
- `hhsetup!??0CCollection@@QEAA@XZ` at `0x180003ab5`
- `hhsetup!??0CCollection@@QEAA@XZ` at `0x180003ab5`
- `hhsetup!??1CCollection@@QEAA@XZ` at `0x180003b09`
- `hhsetup!??1CCollection@@QEAA@XZ` at `0x180003b09`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CHHCollectionWrapper>>,ATL::CComCreator<ATL::CComAggObject<CHHCollectionWrapper>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // edi
  char *v7; // rax
  _QWORD *v8; // rbx

  if ( a1 )
  {
    if ( a3 )
    {
      *a3 = 0;
      v6 = -2147024882;
      v7 = (char *)operator new(0x410u);
      v8 = v7;
      if ( v7 )
      {
        *((_DWORD *)v7 + 2) = 0;
        *(_QWORD *)v7 = &ATL::CComAggObject<CHHCollectionWrapper>::`vftable';
        *((_DWORD *)v7 + 6) = 0;
        CCollection::CCollection((CCollection *)(v7 + 32));
        v8[2] = &ATL::CComContainedObject<CHHCollectionWrapper>::`vftable';
        v8[3] = a1;
        _InterlockedIncrement(&dword_180012EE8);
      }
      else
      {
        v8 = 0;
      }
      if ( v8 )
      {
        v6 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v8)(v8, a2, a3);
        if ( v6 )
        {
          *v8 = &ATL::CComAggObject<CHHCollectionWrapper>::`vftable';
          *((_DWORD *)v8 + 2) = 1;
          _InterlockedDecrement(&dword_180012EE8);
          CCollection::~CCollection((CCollection *)(v8 + 4));
          operator delete(v8);
        }
      }
    }
    else
    {
      return (unsigned int)-2147467261;
    }
  }
  else
  {
    return (unsigned int)ATL::CComCreator<ATL::CComObject<CHHCollectionWrapper>>::CreateInstance();
  }
  return v6;
}

```

## disassembly

```asm
0x180003a40  push    rbx
0x180003a42  push    rbp
0x180003a43  push    rsi
0x180003a44  push    rdi
0x180003a45  push    r12
0x180003a47  push    r14
0x180003a49  sub     rsp, 28h
0x180003a4d  mov     rsi, r8
0x180003a50  mov     r14, rdx
0x180003a53  mov     rbp, rcx
0x180003a56  test    rcx, rcx
0x180003a59  jnz     short loc_180003A67
0x180003a5b  call    ?CreateInstance@?$CComCreator@V?$CComObject@VCHHCollectionWrapper@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CHHCollectionWrapper>>::CreateInstance(void *,_GUID const &,void * *)
0x180003a60  mov     edi, eax
0x180003a62  jmp     loc_180003B18
0x180003a67  test    rsi, rsi
0x180003a6a  jnz     short loc_180003A76
0x180003a6c  mov     edi, 80004003h
0x180003a71  jmp     loc_180003B18
0x180003a76  mov     qword ptr [r8], 0
0x180003a7d  mov     edi, 8007000Eh
0x180003a82  mov     ecx, 410h; Size
0x180003a87  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003a8c  mov     rbx, rax
0x180003a8f  mov     [rsp+58h+arg_0], rax
0x180003a94  lea     r12, ??_7?$CComAggObject@VCHHCollectionWrapper@@@ATL@@6B@; const ATL::CComAggObject<CHHCollectionWrapper>::`vftable'
0x180003a9b  test    rax, rax
0x180003a9e  jz      short loc_180003AD3
0x180003aa0  mov     dword ptr [rax+8], 0
0x180003aa7  mov     [rax], r12
0x180003aaa  mov     dword ptr [rax+18h], 0
0x180003ab1  lea     rcx, [rax+20h]
0x180003ab5  call    cs:__imp_??0CCollection@@QEAA@XZ; CCollection::CCollection(void)
0x180003abb  lea     rax, ??_7?$CComContainedObject@VCHHCollectionWrapper@@@ATL@@6B@; const ATL::CComContainedObject<CHHCollectionWrapper>::`vftable'
0x180003ac2  mov     [rbx+10h], rax
0x180003ac6  mov     [rbx+18h], rbp
0x180003aca  lock inc cs:dword_180012EE8
0x180003ad1  jmp     short loc_180003AD5
0x180003ad3  xor     ebx, ebx
0x180003ad5  test    rbx, rbx
0x180003ad8  jz      short loc_180003B18
0x180003ada  mov     rax, [rbx]
0x180003add  mov     r8, rsi
0x180003ae0  mov     rdx, r14
0x180003ae3  mov     rcx, rbx
0x180003ae6  mov     rax, [rax]
0x180003ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003aee  mov     edi, eax
0x180003af0  test    eax, eax
0x180003af2  jz      short loc_180003B18
0x180003af4  mov     [rbx], r12
0x180003af7  mov     dword ptr [rbx+8], 1
0x180003afe  lock dec cs:dword_180012EE8
0x180003b05  lea     rcx, [rbx+20h]
0x180003b09  call    cs:__imp_??1CCollection@@QEAA@XZ; CCollection::~CCollection(void)
0x180003b0f  mov     rcx, rbx
0x180003b12  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003b18  mov     eax, edi
0x180003b1a  add     rsp, 28h
0x180003b1e  pop     r14
0x180003b20  pop     r12
0x180003b22  pop     rdi
0x180003b23  pop     rsi
0x180003b24  pop     rbp
0x180003b25  pop     rbx
0x180003b26  retn
```
