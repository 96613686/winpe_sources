# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x18000c390`
- end: `0x18000c41d`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `141`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000c390`
- `0x180011010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000c3f0`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c3f0`
- `KERNEL32!DeleteCriticalSection` at `0x18000c3e7`
- `KERNEL32!DeleteCriticalSection` at `0x18000c3e7`

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
0x18000c390  mov     [rsp+arg_0], rbx
0x18000c395  push    rdi
0x18000c396  sub     rsp, 20h
0x18000c39a  mov     rbx, rcx
0x18000c39d  mov     r8d, 7FFFFFFFh
0x18000c3a3  mov     ecx, [rcx+8]
0x18000c3a6  jmp     short loc_18000C3B7
0x18000c3a8  lea     edx, [rcx-1]
0x18000c3ab  mov     eax, ecx
0x18000c3ad  lock cmpxchg [rbx+8], edx
0x18000c3b2  jz      short loc_18000C3BC
0x18000c3b4  mov     ecx, [rbx+8]
0x18000c3b7  cmp     ecx, r8d
0x18000c3ba  jnz     short loc_18000C3A8
0x18000c3bc  lea     edi, [rcx-1]
0x18000c3bf  test    edi, edi
0x18000c3c1  jnz     short loc_18000C3F8
0x18000c3c3  test    rbx, rbx
0x18000c3c6  jz      short loc_18000C410
0x18000c3c8  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x18000c3cf  mov     dword ptr [rbx+8], 0C0000001h
0x18000c3d6  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000c3da  mov     [rbx], rax
0x18000c3dd  cmp     [rcx+28h], dil
0x18000c3e1  jz      short loc_18000C3ED
0x18000c3e3  mov     [rcx+28h], dil
0x18000c3e7  call    cs:__imp_DeleteCriticalSection
0x18000c3ed  mov     rcx, rbx
0x18000c3f0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000c3f6  jmp     short loc_18000C410
0x18000c3f8  cmp     edi, 1
0x18000c3fb  jnz     short loc_18000C410
0x18000c3fd  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000c404  mov     rdx, [rcx]
0x18000c407  mov     rax, [rdx+10h]
0x18000c40b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c410  mov     rbx, [rsp+28h+arg_0]
0x18000c415  mov     eax, edi
0x18000c417  add     rsp, 20h
0x18000c41b  pop     rdi
0x18000c41c  retn
```
