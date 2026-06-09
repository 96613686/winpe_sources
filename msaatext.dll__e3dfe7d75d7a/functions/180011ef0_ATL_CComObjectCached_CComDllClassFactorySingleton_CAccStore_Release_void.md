# ATL::CComObjectCached<CComDllClassFactorySingleton<CAccStore>>::Release(void)

- ea: `0x180011ef0`
- end: `0x180011f9b`
- name: `?Release@?$CComObjectCached@V?$CComDllClassFactorySingleton@VCAccStore@@@@@ATL@@UEAAKXZ`
- size: `171`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x18000d5a4`
- `0x180011ef0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180011f7a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180011f7a`
- `KERNEL32!DeleteCriticalSection` at `0x180011f4a`
- `KERNEL32!DeleteCriticalSection` at `0x180011f71`
- `KERNEL32!DeleteCriticalSection` at `0x180011f4a`
- `KERNEL32!DeleteCriticalSection` at `0x180011f71`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<CComDllClassFactorySingleton<CAccStore>>::Release(char *a1)
{
  signed __int32 i; // ecx
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 2);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange((volatile signed __int32 *)a1 + 2, i - 1, i);
        i = *((_DWORD *)a1 + 2) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    if ( a1 )
    {
      *((_DWORD *)a1 + 2) = 1;
      *(_QWORD *)a1 = &ATL::CComObjectCached<CComDllClassFactorySingleton<CAccStore>>::`vftable';
      if ( a1[200] != (_BYTE)v3 )
      {
        a1[200] = v3;
        DeleteCriticalSection((LPCRITICAL_SECTION)a1 + 4);
      }
      *((_QWORD *)a1 + 9) = &ATL::CComObjectGlobal<CAccStore>::`vftable';
      CAccStore::~CAccStore((CAccStore *)(a1 + 72));
      if ( a1[56] )
      {
        a1[56] = 0;
        DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
      }
      operator delete(a1);
    }
  }
  else if ( i == 2 )
  {
    _InterlockedDecrement(&dword_180024B28);
  }
  return v3;
}

```

## disassembly

```asm
0x180011ef0  mov     [rsp+arg_0], rbx
0x180011ef5  push    rdi
0x180011ef6  sub     rsp, 20h
0x180011efa  mov     rbx, rcx
0x180011efd  mov     r8d, 7FFFFFFFh
0x180011f03  mov     ecx, [rcx+8]
0x180011f06  jmp     short loc_180011F17
0x180011f08  lea     edx, [rcx-1]
0x180011f0b  mov     eax, ecx
0x180011f0d  lock cmpxchg [rbx+8], edx
0x180011f12  jz      short loc_180011F1C
0x180011f14  mov     ecx, [rbx+8]
0x180011f17  cmp     ecx, r8d
0x180011f1a  jnz     short loc_180011F08
0x180011f1c  lea     edi, [rcx-1]
0x180011f1f  test    edi, edi
0x180011f21  jnz     short loc_180011F82
0x180011f23  test    rbx, rbx
0x180011f26  jz      short loc_180011F8E
0x180011f28  lea     rax, ??_7?$CComObjectCached@V?$CComDllClassFactorySingleton@VCAccStore@@@@@ATL@@6B@; const ATL::CComObjectCached<CComDllClassFactorySingleton<CAccStore>>::`vftable'
0x180011f2f  mov     dword ptr [rbx+8], 1
0x180011f36  lea     rcx, [rbx+0A0h]; lpCriticalSection
0x180011f3d  mov     [rbx], rax
0x180011f40  cmp     [rcx+28h], dil
0x180011f44  jz      short loc_180011F50
0x180011f46  mov     [rcx+28h], dil
0x180011f4a  call    cs:__imp_DeleteCriticalSection
0x180011f50  lea     rcx, [rbx+48h]; this
0x180011f54  lea     rax, ??_7?$CComObjectGlobal@VCAccStore@@@ATL@@6B@; const ATL::CComObjectGlobal<CAccStore>::`vftable'
0x180011f5b  mov     [rcx], rax
0x180011f5e  call    ??1CAccStore@@QEAA@XZ; CAccStore::~CAccStore(void)
0x180011f63  lea     rcx, [rbx+10h]; lpCriticalSection
0x180011f67  cmp     byte ptr [rcx+28h], 0
0x180011f6b  jz      short loc_180011F77
0x180011f6d  mov     byte ptr [rcx+28h], 0
0x180011f71  call    cs:__imp_DeleteCriticalSection
0x180011f77  mov     rcx, rbx
0x180011f7a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180011f80  jmp     short loc_180011F8E
0x180011f82  cmp     edi, 1
0x180011f85  jnz     short loc_180011F8E
0x180011f87  lock dec cs:dword_180024B28
0x180011f8e  mov     rbx, [rsp+28h+arg_0]
0x180011f93  mov     eax, edi
0x180011f95  add     rsp, 20h
0x180011f99  pop     rdi
0x180011f9a  retn
```
