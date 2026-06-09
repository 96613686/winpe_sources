# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CAccServerDocMgr>>,ATL::CComCreator<ATL::CComAggObject<CAccServerDocMgr>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000f2f0`
- end: `0x18000f3dd`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCAccServerDocMgr@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCAccServerDocMgr@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `237`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001370`
- `0x18000cac8`
- `0x18000f2f0`
- `0x18000fa4c`
- `0x180014010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000f3c8`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f3c8`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CAccServerDocMgr>>,ATL::CComCreator<ATL::CComAggObject<CAccServerDocMgr>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // edi
  _QWORD *v7; // rax
  _DWORD *v8; // rbx

  if ( a1 )
  {
    if ( a3 )
    {
      *a3 = 0;
      v6 = -2147024882;
      v7 = operator new(0x38u);
      v8 = v7;
      if ( v7 )
      {
        *((_DWORD *)v7 + 2) = 0;
        *v7 = &ATL::CComAggObject<CAccServerDocMgr>::`vftable';
        v7[4] = 0;
        v7[5] = 0;
        v7[6] = 0;
        v7[2] = &ATL::CComContainedObject<CAccServerDocMgr>::`vftable';
        v7[3] = a1;
        _InterlockedIncrement(&dword_180024B28);
        v6 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v7)(v7, a2, a3);
        if ( v6 )
        {
          *(_QWORD *)v8 = &ATL::CComAggObject<CAccServerDocMgr>::`vftable';
          v8[2] = 1;
          _InterlockedDecrement(&dword_180024B28);
          CAccServerDocMgr::~CAccServerDocMgr((CAccServerDocMgr *)(v8 + 4));
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
    return (unsigned int)ATL::CComCreator<ATL::CComObject<CAccServerDocMgr>>::CreateInstance();
  }
  return v6;
}

```

## disassembly

```asm
0x18000f2f0  push    rbx
0x18000f2f2  push    rbp
0x18000f2f3  push    rsi
0x18000f2f4  push    rdi
0x18000f2f5  push    r12
0x18000f2f7  push    r14
0x18000f2f9  sub     rsp, 28h
0x18000f2fd  mov     rsi, r8
0x18000f300  mov     r14, rdx
0x18000f303  mov     rbp, rcx
0x18000f306  test    rcx, rcx
0x18000f309  jnz     short loc_18000F317
0x18000f30b  call    ?CreateInstance@?$CComCreator@V?$CComObject@VCAccServerDocMgr@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CAccServerDocMgr>>::CreateInstance(void *,_GUID const &,void * *)
0x18000f310  mov     edi, eax
0x18000f312  jmp     loc_18000F3CE
0x18000f317  test    rsi, rsi
0x18000f31a  jnz     short loc_18000F326
0x18000f31c  mov     edi, 80004003h
0x18000f321  jmp     loc_18000F3CE
0x18000f326  mov     ecx, 38h ; '8'; Size
0x18000f32b  mov     qword ptr [r8], 0
0x18000f332  mov     edi, 8007000Eh
0x18000f337  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f33c  mov     [rsp+58h+arg_0], rax
0x18000f341  mov     rbx, rax
0x18000f344  test    rax, rax
0x18000f347  jz      loc_18000F3CE
0x18000f34d  mov     dword ptr [rax+8], 0
0x18000f354  lea     r12, ??_7?$CComAggObject@VCAccServerDocMgr@@@ATL@@6B@; const ATL::CComAggObject<CAccServerDocMgr>::`vftable'
0x18000f35b  mov     [rax], r12
0x18000f35e  mov     qword ptr [rax+20h], 0
0x18000f366  mov     qword ptr [rax+28h], 0
0x18000f36e  mov     qword ptr [rax+30h], 0
0x18000f376  lea     rax, ??_7?$CComContainedObject@VCAccServerDocMgr@@@ATL@@6B@; const ATL::CComContainedObject<CAccServerDocMgr>::`vftable'
0x18000f37d  mov     [rbx+10h], rax
0x18000f381  mov     [rbx+18h], rbp
0x18000f385  lock inc cs:dword_180024B28
0x18000f38c  test    rbx, rbx
0x18000f38f  jz      short loc_18000F3CE
0x18000f391  mov     rax, [rbx]
0x18000f394  mov     r8, rsi
0x18000f397  mov     rdx, r14
0x18000f39a  mov     rcx, rbx
0x18000f39d  mov     rax, [rax]
0x18000f3a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3a5  mov     edi, eax
0x18000f3a7  test    eax, eax
0x18000f3a9  jz      short loc_18000F3CE
0x18000f3ab  mov     [rbx], r12
0x18000f3ae  lea     rcx, [rbx+10h]; this
0x18000f3b2  mov     dword ptr [rbx+8], 1
0x18000f3b9  lock dec cs:dword_180024B28
0x18000f3c0  call    ??1CAccServerDocMgr@@QEAA@XZ; CAccServerDocMgr::~CAccServerDocMgr(void)
0x18000f3c5  mov     rcx, rbx
0x18000f3c8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f3ce  mov     eax, edi
0x18000f3d0  add     rsp, 28h
0x18000f3d4  pop     r14
0x18000f3d6  pop     r12
0x18000f3d8  pop     rdi
0x18000f3d9  pop     rsi
0x18000f3da  pop     rbp
0x18000f3db  pop     rbx
0x18000f3dc  retn
```
