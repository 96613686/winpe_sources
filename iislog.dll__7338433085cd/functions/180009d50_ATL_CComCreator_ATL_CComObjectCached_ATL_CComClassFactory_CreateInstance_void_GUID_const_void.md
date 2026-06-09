# ATL::CComCreator<ATL::CComObjectCached<ATL::CComClassFactory>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180009d50`
- end: `0x180009df1`
- name: `?CreateInstance@?$CComCreator@V?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `161`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001008`
- `0x180001048`
- `0x180009d50`
- `0x180010010`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180009d9b`
- `KERNEL32!InitializeCriticalSection` at `0x180009d9b`
- `KERNEL32!DeleteCriticalSection` at `0x180009dd4`
- `KERNEL32!DeleteCriticalSection` at `0x180009dd4`

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
0x180009d50  push    rbx
0x180009d52  push    rbp
0x180009d53  push    rsi
0x180009d54  push    rdi
0x180009d55  push    r14
0x180009d57  push    r15
0x180009d59  sub     rsp, 28h
0x180009d5d  mov     rdi, r8
0x180009d60  mov     rbp, rdx
0x180009d63  mov     r14, rcx
0x180009d66  test    r8, r8
0x180009d69  jnz     short loc_180009D72
0x180009d6b  mov     eax, 80004003h
0x180009d70  jmp     short loc_180009DE4
0x180009d72  mov     ecx, 40h ; '@'; Size
0x180009d77  mov     qword ptr [r8], 0
0x180009d7e  mov     esi, 8007000Eh
0x180009d83  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009d88  mov     rbx, rax
0x180009d8b  test    rax, rax
0x180009d8e  jz      short loc_180009DE2
0x180009d90  lea     rcx, [rax+10h]; lpCriticalSection
0x180009d94  mov     dword ptr [rax+8], 0
0x180009d9b  call    cs:__imp_InitializeCriticalSection
0x180009da1  lea     r15, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x180009da8  mov     r8, rdi
0x180009dab  mov     rax, [r15]
0x180009dae  mov     rdx, rbp
0x180009db1  mov     [rbx], r15
0x180009db4  mov     rcx, rbx
0x180009db7  mov     [rbx+38h], r14
0x180009dbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dc0  mov     esi, eax
0x180009dc2  test    eax, eax
0x180009dc4  jz      short loc_180009DE2
0x180009dc6  lea     rcx, [rbx+10h]; lpCriticalSection
0x180009dca  mov     [rbx], r15
0x180009dcd  mov     dword ptr [rbx+8], 1
0x180009dd4  call    cs:__imp_DeleteCriticalSection
0x180009dda  mov     rcx, rbx; Block
0x180009ddd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009de2  mov     eax, esi
0x180009de4  add     rsp, 28h
0x180009de8  pop     r15
0x180009dea  pop     r14
0x180009dec  pop     rdi
0x180009ded  pop     rsi
0x180009dee  pop     rbp
0x180009def  pop     rbx
0x180009df0  retn
```
