# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CNCSALOG>>,ATL::CComCreator<ATL::CComAggObject<CNCSALOG>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180009ab0`
- end: `0x180009c0e`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCNCSALOG@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCNCSALOG@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `350`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001008`
- `0x180001048`
- `0x18000744c`
- `0x1800075f4`
- `0x180009ab0`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CNCSALOG>>,ATL::CComCreator<ATL::CComAggObject<CNCSALOG>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // ebx
  CNCSALOG *v7; // rax
  CNCSALOG *v8; // rdi
  char *v9; // rax
  _QWORD *v10; // rdi

  if ( a1 )
  {
    if ( !a3 )
      return (unsigned int)-2147467261;
    *a3 = 0;
    v6 = -2147024882;
    v9 = (char *)operator new(0x660u);
    v10 = v9;
    if ( v9 )
    {
      *((_DWORD *)v9 + 2) = 0;
      *(_QWORD *)v9 = &ATL::CComAggObject<CNCSALOG>::`vftable';
      CNCSALOG::CNCSALOG((CNCSALOG *)(v9 + 24));
      v10[4] = a1;
      v10[3] = &ATL::CComContainedObject<CNCSALOG>::`vftable'{for `CLogFileCtrl'};
      v10[54] = &ATL::CComContainedObject<CNCSALOG>::`vftable'{for `CLogScript'};
      _InterlockedIncrement(&dword_180017A78);
      v6 = (*(__int64 (__fastcall **)(_QWORD *, __int64, _QWORD *))*v10)(v10, a2, a3);
      if ( v6 )
      {
        *v10 = &ATL::CComAggObject<CNCSALOG>::`vftable';
        *((_DWORD *)v10 + 2) = 1;
        _InterlockedDecrement(&dword_180017A78);
        CNCSALOG::~CNCSALOG((CNCSALOG *)(v10 + 3));
        operator delete(v10);
      }
    }
  }
  else
  {
    if ( !a3 )
      return (unsigned int)-2147467261;
    *a3 = 0;
    v6 = -2147024882;
    v7 = (CNCSALOG *)operator new(0x648u);
    v8 = v7;
    if ( v7 )
    {
      CNCSALOG::CNCSALOG(v7);
      *(_QWORD *)v8 = &ATL::CComObject<CNCSALOG>::`vftable'{for `CLogFileCtrl'};
      *((_QWORD *)v8 + 51) = &ATL::CComObject<CNCSALOG>::`vftable'{for `CLogScript'};
      _InterlockedIncrement(&dword_180017A78);
      v6 = (**(__int64 (__fastcall ***)(CNCSALOG *, __int64, _QWORD *))v8)(v8, a2, a3);
      if ( v6 )
        (*(void (__fastcall **)(CNCSALOG *, __int64))(*(_QWORD *)v8 + 80LL))(v8, 1);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180009ab0  push    rbx
0x180009ab2  push    rbp
0x180009ab3  push    rsi
0x180009ab4  push    rdi
0x180009ab5  push    r12
0x180009ab7  push    r14
0x180009ab9  sub     rsp, 28h
0x180009abd  mov     rsi, r8
0x180009ac0  mov     r14, rdx
0x180009ac3  mov     rbp, rcx
0x180009ac6  test    rcx, rcx
0x180009ac9  jnz     loc_180009B5E
0x180009acf  test    r8, r8
0x180009ad2  jnz     short loc_180009ADE
0x180009ad4  mov     ebx, 80004003h
0x180009ad9  jmp     loc_180009BFF
0x180009ade  mov     ecx, 648h; Size
0x180009ae3  mov     qword ptr [r8], 0
0x180009aea  mov     ebx, 8007000Eh
0x180009aef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009af4  mov     rdi, rax
0x180009af7  test    rax, rax
0x180009afa  jz      loc_180009BFF
0x180009b00  mov     rcx, rax; this
0x180009b03  call    ??0CNCSALOG@@QEAA@XZ; CNCSALOG::CNCSALOG(void)
0x180009b08  lea     rax, ??_7?$CComObject@VCNCSALOG@@@ATL@@6BCLogFileCtrl@@@; const ATL::CComObject<CNCSALOG>::`vftable'{for `CLogFileCtrl'}
0x180009b0f  mov     [rdi], rax
0x180009b12  lea     rax, ??_7?$CComObject@VCNCSALOG@@@ATL@@6BCLogScript@@@; const ATL::CComObject<CNCSALOG>::`vftable'{for `CLogScript'}
0x180009b19  mov     [rdi+198h], rax
0x180009b20  lock inc cs:dword_180017A78
0x180009b27  mov     rcx, [rdi]
0x180009b2a  mov     r8, rsi
0x180009b2d  mov     rdx, r14
0x180009b30  mov     rax, [rcx]
0x180009b33  mov     rcx, rdi
0x180009b36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b3b  mov     ebx, eax
0x180009b3d  test    eax, eax
0x180009b3f  jz      loc_180009BFF
0x180009b45  mov     rax, [rdi]
0x180009b48  mov     edx, 1
0x180009b4d  mov     rcx, rdi
0x180009b50  mov     rax, [rax+50h]
0x180009b54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b59  jmp     loc_180009BFF
0x180009b5e  test    rsi, rsi
0x180009b61  jz      loc_180009AD4
0x180009b67  mov     ecx, 660h; Size
0x180009b6c  mov     qword ptr [r8], 0
0x180009b73  mov     ebx, 8007000Eh
0x180009b78  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009b7d  mov     rdi, rax
0x180009b80  test    rax, rax
0x180009b83  jz      short loc_180009BFF
0x180009b85  lea     r12, ??_7?$CComAggObject@VCNCSALOG@@@ATL@@6B@; const ATL::CComAggObject<CNCSALOG>::`vftable'
0x180009b8c  mov     dword ptr [rax+8], 0
0x180009b93  lea     rcx, [rax+18h]; this
0x180009b97  mov     [rax], r12
0x180009b9a  call    ??0CNCSALOG@@QEAA@XZ; CNCSALOG::CNCSALOG(void)
0x180009b9f  lea     rax, ??_7?$CComContainedObject@VCNCSALOG@@@ATL@@6BCLogFileCtrl@@@; const ATL::CComContainedObject<CNCSALOG>::`vftable'{for `CLogFileCtrl'}
0x180009ba6  mov     [rdi+20h], rbp
0x180009baa  mov     [rdi+18h], rax
0x180009bae  lea     rax, ??_7?$CComContainedObject@VCNCSALOG@@@ATL@@6BCLogScript@@@; const ATL::CComContainedObject<CNCSALOG>::`vftable'{for `CLogScript'}
0x180009bb5  mov     [rdi+1B0h], rax
0x180009bbc  lock inc cs:dword_180017A78
0x180009bc3  mov     rax, [rdi]
0x180009bc6  mov     r8, rsi
0x180009bc9  mov     rdx, r14
0x180009bcc  mov     rcx, rdi
0x180009bcf  mov     rax, [rax]
0x180009bd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bd7  mov     ebx, eax
0x180009bd9  test    eax, eax
0x180009bdb  jz      short loc_180009BFF
0x180009bdd  mov     [rdi], r12
0x180009be0  lea     rcx, [rdi+18h]; this
0x180009be4  mov     dword ptr [rdi+8], 1
0x180009beb  lock dec cs:dword_180017A78
0x180009bf2  call    ??1CNCSALOG@@MEAA@XZ; CNCSALOG::~CNCSALOG(void)
0x180009bf7  mov     rcx, rdi; Block
0x180009bfa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009bff  mov     eax, ebx
0x180009c01  add     rsp, 28h
0x180009c05  pop     r14
0x180009c07  pop     r12
0x180009c09  pop     rdi
0x180009c0a  pop     rsi
0x180009c0b  pop     rbp
0x180009c0c  pop     rbx
0x180009c0d  retn
```
