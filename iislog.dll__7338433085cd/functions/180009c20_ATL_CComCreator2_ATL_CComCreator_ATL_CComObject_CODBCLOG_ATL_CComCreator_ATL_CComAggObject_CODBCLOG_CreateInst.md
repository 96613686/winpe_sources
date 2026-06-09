# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CODBCLOG>>,ATL::CComCreator<ATL::CComAggObject<CODBCLOG>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180009c20`
- end: `0x180009d49`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCODBCLOG@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCODBCLOG@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `297`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001008`
- `0x180001048`
- `0x180009c20`
- `0x18000a6f4`
- `0x18000a774`
- `0x180010010`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CODBCLOG>>,ATL::CComCreator<ATL::CComAggObject<CODBCLOG>>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v6; // ebx
  CODBCLOG *v7; // rax
  CODBCLOG *v8; // rdi
  CODBCLOG *v9; // rcx
  char *v10; // rax

  if ( a1 )
  {
    if ( !a3 )
      return (unsigned int)-2147467261;
    *a3 = 0;
    v6 = -2147024882;
    v10 = (char *)operator new(0x6D0u);
    v8 = (CODBCLOG *)v10;
    if ( v10 )
    {
      *((_DWORD *)v10 + 2) = 0;
      *(_QWORD *)v10 = &ATL::CComAggObject<CODBCLOG>::`vftable';
      CODBCLOG::CODBCLOG((CODBCLOG *)(v10 + 24));
      *((_QWORD *)v8 + 4) = a1;
      *((_QWORD *)v8 + 3) = &ATL::CComContainedObject<CODBCLOG>::`vftable';
      _InterlockedIncrement(&dword_180017A78);
      v6 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v8)(v8, a2, a3);
      if ( v6 )
      {
        *(_QWORD *)v8 = &ATL::CComAggObject<CODBCLOG>::`vftable';
        v9 = (CODBCLOG *)((char *)v8 + 24);
        goto LABEL_11;
      }
    }
  }
  else
  {
    if ( !a3 )
      return (unsigned int)-2147467261;
    *a3 = 0;
    v6 = -2147024882;
    v7 = (CODBCLOG *)operator new(0x6B8u);
    v8 = v7;
    if ( v7 )
    {
      CODBCLOG::CODBCLOG(v7);
      *(_QWORD *)v8 = &ATL::CComObject<CODBCLOG>::`vftable';
      _InterlockedIncrement(&dword_180017A78);
      v6 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v8)(v8, a2, a3);
      if ( v6 )
      {
        *(_QWORD *)v8 = &ATL::CComObject<CODBCLOG>::`vftable';
        v9 = v8;
LABEL_11:
        *((_DWORD *)v8 + 2) = 1;
        _InterlockedDecrement(&dword_180017A78);
        CODBCLOG::~CODBCLOG(v9);
        operator delete(v8);
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180009c20  push    rbx
0x180009c22  push    rbp
0x180009c23  push    rsi
0x180009c24  push    rdi
0x180009c25  push    r12
0x180009c27  push    r14
0x180009c29  sub     rsp, 28h
0x180009c2d  mov     rsi, r8
0x180009c30  mov     r14, rdx
0x180009c33  mov     rbp, rcx
0x180009c36  test    rcx, rcx
0x180009c39  jnz     short loc_180009CAB
0x180009c3b  test    r8, r8
0x180009c3e  jnz     short loc_180009C4A
0x180009c40  mov     ebx, 80004003h
0x180009c45  jmp     loc_180009D3A
0x180009c4a  mov     ecx, 6B8h; Size
0x180009c4f  mov     qword ptr [r8], 0
0x180009c56  mov     ebx, 8007000Eh
0x180009c5b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009c60  mov     rdi, rax
0x180009c63  test    rax, rax
0x180009c66  jz      loc_180009D3A
0x180009c6c  mov     rcx, rax; this
0x180009c6f  call    ??0CODBCLOG@@QEAA@XZ; CODBCLOG::CODBCLOG(void)
0x180009c74  lea     rbp, ??_7?$CComObject@VCODBCLOG@@@ATL@@6B@; const ATL::CComObject<CODBCLOG>::`vftable'
0x180009c7b  mov     [rdi], rbp
0x180009c7e  lock inc cs:dword_180017A78
0x180009c85  mov     rcx, [rdi]
0x180009c88  mov     r8, rsi
0x180009c8b  mov     rdx, r14
0x180009c8e  mov     rax, [rcx]
0x180009c91  mov     rcx, rdi
0x180009c94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c99  mov     ebx, eax
0x180009c9b  test    eax, eax
0x180009c9d  jz      loc_180009D3A
0x180009ca3  mov     [rdi], rbp
0x180009ca6  mov     rcx, rdi
0x180009ca9  jmp     short loc_180009D1F
0x180009cab  test    rsi, rsi
0x180009cae  jz      short loc_180009C40
0x180009cb0  mov     ecx, 6D0h; Size
0x180009cb5  mov     qword ptr [r8], 0
0x180009cbc  mov     ebx, 8007000Eh
0x180009cc1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009cc6  mov     rdi, rax
0x180009cc9  test    rax, rax
0x180009ccc  jz      short loc_180009D3A
0x180009cce  lea     r12, ??_7?$CComAggObject@VCODBCLOG@@@ATL@@6B@; const ATL::CComAggObject<CODBCLOG>::`vftable'
0x180009cd5  mov     dword ptr [rax+8], 0
0x180009cdc  lea     rcx, [rax+18h]; this
0x180009ce0  mov     [rax], r12
0x180009ce3  call    ??0CODBCLOG@@QEAA@XZ; CODBCLOG::CODBCLOG(void)
0x180009ce8  lea     rax, ??_7?$CComContainedObject@VCODBCLOG@@@ATL@@6B@; const ATL::CComContainedObject<CODBCLOG>::`vftable'
0x180009cef  mov     [rdi+20h], rbp
0x180009cf3  mov     [rdi+18h], rax
0x180009cf7  lock inc cs:dword_180017A78
0x180009cfe  mov     rax, [rdi]
0x180009d01  mov     r8, rsi
0x180009d04  mov     rdx, r14
0x180009d07  mov     rcx, rdi
0x180009d0a  mov     rax, [rax]
0x180009d0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d12  mov     ebx, eax
0x180009d14  test    eax, eax
0x180009d16  jz      short loc_180009D3A
0x180009d18  mov     [rdi], r12
0x180009d1b  lea     rcx, [rdi+18h]; this
0x180009d1f  mov     dword ptr [rdi+8], 1
0x180009d26  lock dec cs:dword_180017A78
0x180009d2d  call    ??1CODBCLOG@@IEAA@XZ; CODBCLOG::~CODBCLOG(void)
0x180009d32  mov     rcx, rdi; Block
0x180009d35  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009d3a  mov     eax, ebx
0x180009d3c  add     rsp, 28h
0x180009d40  pop     r14
0x180009d42  pop     r12
0x180009d44  pop     rdi
0x180009d45  pop     rsi
0x180009d46  pop     rbp
0x180009d47  pop     rbx
0x180009d48  retn
```
