# ATL::CComCreator<ATL::CComObject<CDict>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000fb44`
- end: `0x18000fc54`
- name: `?CreateInstance@?$CComCreator@V?$CComObject@VCDict@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `272`
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
- `0x18000fb44`
- `0x180014010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000fc39`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000fc39`
- `KERNEL32!LoadLibraryExW` at `0x18000fbd5`
- `KERNEL32!LoadLibraryExW` at `0x18000fbd5`

## string_xrefs

- `0x18000fbce`: `OLEACCRC.DLL`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComCreator<ATL::CComObject<CDict>>::CreateInstance(__int64 a1, __int64 a2, _QWORD *a3)
{
  unsigned int v6; // edi
  CDict *v7; // rax
  CDict *v8; // rbx
  int v9; // eax
  HMODULE Library; // rcx
  int v11; // eax

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -2147024882;
  v7 = (CDict *)operator new(0x38u);
  v8 = v7;
  if ( v7 )
  {
    CDict::CDict(v7);
    *(_QWORD *)v8 = &ATL::CComObject<CDict>::`vftable';
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
      *((_DWORD *)v8 + 2) = v9 + 1;
    Library = LoadLibraryExW(L"OLEACCRC.DLL", 0, 2u);
    *((_QWORD *)v8 + 6) = Library;
    v6 = Library == 0 ? 0x80004005 : 0;
    v11 = *((_DWORD *)v8 + 2);
    if ( v11 != 0x7FFFFFFF )
      *((_DWORD *)v8 + 2) = v11 - 1;
    if ( !Library || (v6 = (**(__int64 (__fastcall ***)(CDict *, __int64, _QWORD *))v8)(v8, a2, a3)) != 0 )
    {
      *(_QWORD *)v8 = &ATL::CComObject<CDict>::`vftable';
      *((_DWORD *)v8 + 2) = 1;
      _InterlockedDecrement(&dword_180024B28);
      CDict::~CDict(v8);
      operator delete(v8);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18000fb44  mov     [rsp+arg_8], rbx
0x18000fb49  mov     [rsp+arg_10], rbp
0x18000fb4e  mov     [rsp+arg_0], rcx
0x18000fb53  push    rsi
0x18000fb54  push    rdi
0x18000fb55  push    r15
0x18000fb57  sub     rsp, 20h
0x18000fb5b  mov     rsi, r8
0x18000fb5e  mov     rbp, rdx
0x18000fb61  test    r8, r8
0x18000fb64  jnz     short loc_18000FB70
0x18000fb66  mov     eax, 80004003h
0x18000fb6b  jmp     loc_18000FC41
0x18000fb70  mov     qword ptr [r8], 0
0x18000fb77  mov     edi, 8007000Eh
0x18000fb7c  mov     ecx, 38h ; '8'; Size
0x18000fb81  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fb86  mov     rbx, rax
0x18000fb89  mov     [rsp+38h+arg_0], rax
0x18000fb8e  lea     r15, ??_7?$CComObject@VCDict@@@ATL@@6B@; const ATL::CComObject<CDict>::`vftable'
0x18000fb95  test    rax, rax
0x18000fb98  jz      short loc_18000FBAE
0x18000fb9a  mov     rcx, rax; this
0x18000fb9d  call    ??0CDict@@QEAA@XZ; CDict::CDict(void)
0x18000fba2  mov     [rbx], r15
0x18000fba5  lock inc cs:dword_180024B28
0x18000fbac  jmp     short loc_18000FBB0
0x18000fbae  xor     ebx, ebx
0x18000fbb0  test    rbx, rbx
0x18000fbb3  jz      loc_18000FC3F
0x18000fbb9  mov     eax, [rbx+8]
0x18000fbbc  cmp     eax, 7FFFFFFFh
0x18000fbc1  jz      short loc_18000FBC8
0x18000fbc3  inc     eax
0x18000fbc5  mov     [rbx+8], eax
0x18000fbc8  xor     edx, edx; hFile
0x18000fbca  lea     r8d, [rdx+2]; dwFlags
0x18000fbce  lea     rcx, aOleaccrcDll; "OLEACCRC.DLL"
0x18000fbd5  call    cs:__imp_LoadLibraryExW
0x18000fbdb  mov     rcx, rax
0x18000fbde  mov     [rbx+30h], rax
0x18000fbe2  neg     rax
0x18000fbe5  sbb     edi, edi
0x18000fbe7  not     edi
0x18000fbe9  and     edi, 80004005h
0x18000fbef  mov     eax, [rbx+8]
0x18000fbf2  cmp     eax, 7FFFFFFFh
0x18000fbf7  jz      short loc_18000FBFE
0x18000fbf9  dec     eax
0x18000fbfb  mov     [rbx+8], eax
0x18000fbfe  test    rcx, rcx
0x18000fc01  jz      short loc_18000FC1D
0x18000fc03  mov     rax, [rbx]
0x18000fc06  mov     r8, rsi
0x18000fc09  mov     rdx, rbp
0x18000fc0c  mov     rcx, rbx
0x18000fc0f  mov     rax, [rax]
0x18000fc12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc17  mov     edi, eax
0x18000fc19  test    eax, eax
0x18000fc1b  jz      short loc_18000FC3F
0x18000fc1d  mov     [rbx], r15
0x18000fc20  mov     dword ptr [rbx+8], 1
0x18000fc27  lock dec cs:dword_180024B28
0x18000fc2e  mov     rcx, rbx; this
0x18000fc31  call    ??1CDict@@QEAA@XZ; CDict::~CDict(void)
0x18000fc36  mov     rcx, rbx
0x18000fc39  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000fc3f  mov     eax, edi
0x18000fc41  mov     rbx, [rsp+38h+arg_8]
0x18000fc46  mov     rbp, [rsp+38h+arg_10]
0x18000fc4b  add     rsp, 20h
0x18000fc4f  pop     r15
0x18000fc51  pop     rdi
0x18000fc52  pop     rsi
0x18000fc53  retn
```
