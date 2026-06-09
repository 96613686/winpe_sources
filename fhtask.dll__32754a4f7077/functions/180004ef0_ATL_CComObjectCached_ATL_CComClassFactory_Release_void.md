# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180004ef0`
- end: `0x180004f7d`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `141`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004ef0`
- `0x18000b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180004f50`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004f50`
- `KERNEL32!DeleteCriticalSection` at `0x180004f47`
- `KERNEL32!DeleteCriticalSection` at `0x180004f47`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::Release(char *a1)
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
      *((_DWORD *)a1 + 2) = -1073741823;
      *(_QWORD *)a1 = &ATL::CComClassFactory::`vftable';
      if ( a1[56] != (_BYTE)v3 )
      {
        a1[56] = v3;
        DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
      }
      operator delete(a1);
    }
  }
  else if ( i == 2 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *, _QWORD, __int64))(*(_QWORD *)ATL::_pAtlModule + 16LL))(
      ATL::_pAtlModule,
      *(_QWORD *)ATL::_pAtlModule,
      0x7FFFFFFF);
  }
  return v3;
}

```

## disassembly

```asm
0x180004ef0  mov     [rsp+arg_0], rbx
0x180004ef5  push    rdi
0x180004ef6  sub     rsp, 20h
0x180004efa  mov     rbx, rcx
0x180004efd  mov     r8d, 7FFFFFFFh
0x180004f03  mov     ecx, [rcx+8]
0x180004f06  jmp     short loc_180004F17
0x180004f08  lea     edx, [rcx-1]
0x180004f0b  mov     eax, ecx
0x180004f0d  lock cmpxchg [rbx+8], edx
0x180004f12  jz      short loc_180004F1C
0x180004f14  mov     ecx, [rbx+8]
0x180004f17  cmp     ecx, r8d
0x180004f1a  jnz     short loc_180004F08
0x180004f1c  lea     edi, [rcx-1]
0x180004f1f  test    edi, edi
0x180004f21  jnz     short loc_180004F58
0x180004f23  test    rbx, rbx
0x180004f26  jz      short loc_180004F70
0x180004f28  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180004f2f  mov     dword ptr [rbx+8], 0C0000001h
0x180004f36  lea     rcx, [rbx+10h]; lpCriticalSection
0x180004f3a  mov     [rbx], rax
0x180004f3d  cmp     [rcx+28h], dil
0x180004f41  jz      short loc_180004F4D
0x180004f43  mov     [rcx+28h], dil
0x180004f47  call    cs:__imp_DeleteCriticalSection
0x180004f4d  mov     rcx, rbx
0x180004f50  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004f56  jmp     short loc_180004F70
0x180004f58  cmp     edi, 1
0x180004f5b  jnz     short loc_180004F70
0x180004f5d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180004f64  mov     rdx, [rcx]
0x180004f67  mov     rax, [rdx+10h]
0x180004f6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f70  mov     rbx, [rsp+28h+arg_0]
0x180004f75  mov     eax, edi
0x180004f77  add     rsp, 20h
0x180004f7b  pop     rdi
0x180004f7c  retn
```
