# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180007d10`
- end: `0x180007daa`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `154`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180007d10`
- `0x18000f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180007d76`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007d76`
- `KERNEL32!DeleteCriticalSection` at `0x180007d67`
- `KERNEL32!DeleteCriticalSection` at `0x180007d67`

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
0x180007d10  mov     [rsp+arg_0], rbx
0x180007d15  push    rdi
0x180007d16  sub     rsp, 20h
0x180007d1a  mov     rbx, rcx
0x180007d1d  mov     r8d, 7FFFFFFFh
0x180007d23  mov     ecx, [rcx+8]
0x180007d26  jmp     short loc_180007D37
0x180007d28  lea     edx, [rcx-1]
0x180007d2b  mov     eax, ecx
0x180007d2d  lock cmpxchg [rbx+8], edx
0x180007d32  jz      short loc_180007D3C
0x180007d34  mov     ecx, [rbx+8]
0x180007d37  cmp     ecx, r8d
0x180007d3a  jnz     short loc_180007D28
0x180007d3c  lea     edi, [rcx-1]
0x180007d3f  test    edi, edi
0x180007d41  jnz     short loc_180007D84
0x180007d43  test    rbx, rbx
0x180007d46  jz      short loc_180007D9C
0x180007d48  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180007d4f  mov     dword ptr [rbx+8], 0C0000001h
0x180007d56  lea     rcx, [rbx+10h]; lpCriticalSection
0x180007d5a  mov     [rbx], rax
0x180007d5d  cmp     [rcx+28h], dil
0x180007d61  jz      short loc_180007D73
0x180007d63  mov     [rcx+28h], dil
0x180007d67  call    cs:__imp_DeleteCriticalSection
0x180007d6e  nop     dword ptr [rax+rax+00h]
0x180007d73  mov     rcx, rbx
0x180007d76  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007d7d  nop     dword ptr [rax+rax+00h]
0x180007d82  jmp     short loc_180007D9C
0x180007d84  cmp     edi, 1
0x180007d87  jnz     short loc_180007D9C
0x180007d89  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007d90  mov     rdx, [rcx]
0x180007d93  mov     rax, [rdx+10h]
0x180007d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d9c  mov     rbx, [rsp+28h+arg_0]
0x180007da1  mov     eax, edi
0x180007da3  add     rsp, 20h
0x180007da7  pop     rdi
0x180007da8  retn
```
