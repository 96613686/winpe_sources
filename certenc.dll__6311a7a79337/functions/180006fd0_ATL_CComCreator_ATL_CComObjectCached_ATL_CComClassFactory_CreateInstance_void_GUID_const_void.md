# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006fd0`
- end: `0x180007071`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `161`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001008`
- `0x180001014`
- `0x180006fd0`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000701b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000701b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007054`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007054`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v7; // esi
  char *v8; // rax
  char *v9; // rbx

  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  v7 = -2147024882;
  v8 = (char *)operator new(0x40u);
  v9 = v8;
  if ( v8 )
  {
    *((_DWORD *)v8 + 2) = 0;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v8 + 16));
    *(_QWORD *)v9 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
    *((_QWORD *)v9 + 7) = a1;
    v7 = ((__int64 (__fastcall *)(char *, __int64, _QWORD *))ATL::CComObjectCached<ATL::CComClassFactory>::`vftable')(
           v9,
           a2,
           a3);
    if ( v7 )
    {
      *(_QWORD *)v9 = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
      *((_DWORD *)v9 + 2) = 1;
      DeleteCriticalSection((LPCRITICAL_SECTION)(v9 + 16));
      operator delete(v9);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180006fd0  push    rbx
0x180006fd2  push    rbp
0x180006fd3  push    rsi
0x180006fd4  push    rdi
0x180006fd5  push    r14
0x180006fd7  push    r15
0x180006fd9  sub     rsp, 28h
0x180006fdd  mov     rdi, r8
0x180006fe0  mov     rbp, rdx
0x180006fe3  mov     r14, rcx
0x180006fe6  test    r8, r8
0x180006fe9  jnz     short loc_180006FF2
0x180006feb  mov     eax, 80004003h
0x180006ff0  jmp     short loc_180007064
0x180006ff2  mov     ecx, 40h ; '@'; Size
0x180006ff7  mov     qword ptr [r8], 0
0x180006ffe  mov     esi, 8007000Eh
0x180007003  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007008  mov     rbx, rax
0x18000700b  test    rax, rax
0x18000700e  jz      short loc_180007062
0x180007010  lea     rcx, [rax+10h]; lpCriticalSection
0x180007014  mov     dword ptr [rax+8], 0
0x18000701b  call    cs:__imp_InitializeCriticalSection
0x180007021  lea     r15, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180007028  mov     r8, rdi
0x18000702b  mov     rax, [r15]
0x18000702e  mov     rdx, rbp
0x180007031  mov     [rbx], r15
0x180007034  mov     rcx, rbx
0x180007037  mov     [rbx+38h], r14
0x18000703b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007040  mov     esi, eax
0x180007042  test    eax, eax
0x180007044  jz      short loc_180007062
0x180007046  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000704a  mov     [rbx], r15
0x18000704d  mov     dword ptr [rbx+8], 1
0x180007054  call    cs:__imp_DeleteCriticalSection
0x18000705a  mov     rcx, rbx; Block
0x18000705d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007062  mov     eax, esi
0x180007064  add     rsp, 28h
0x180007068  pop     r15
0x18000706a  pop     r14
0x18000706c  pop     rdi
0x18000706d  pop     rsi
0x18000706e  pop     rbp
0x18000706f  pop     rbx
0x180007070  retn
```
