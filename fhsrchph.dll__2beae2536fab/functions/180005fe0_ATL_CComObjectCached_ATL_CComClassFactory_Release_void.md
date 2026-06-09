# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180005fe0`
- end: `0x18000606d`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `141`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180005fe0`
- `0x18000c010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006040`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006040`
- `KERNEL32!DeleteCriticalSection` at `0x180006037`
- `KERNEL32!DeleteCriticalSection` at `0x180006037`

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
0x180005fe0  mov     [rsp+arg_0], rbx
0x180005fe5  push    rdi
0x180005fe6  sub     rsp, 20h
0x180005fea  mov     rbx, rcx
0x180005fed  mov     r8d, 7FFFFFFFh
0x180005ff3  mov     ecx, [rcx+8]
0x180005ff6  jmp     short loc_180006007
0x180005ff8  lea     edx, [rcx-1]
0x180005ffb  mov     eax, ecx
0x180005ffd  lock cmpxchg [rbx+8], edx
0x180006002  jz      short loc_18000600C
0x180006004  mov     ecx, [rbx+8]
0x180006007  cmp     ecx, r8d
0x18000600a  jnz     short loc_180005FF8
0x18000600c  lea     edi, [rcx-1]
0x18000600f  test    edi, edi
0x180006011  jnz     short loc_180006048
0x180006013  test    rbx, rbx
0x180006016  jz      short loc_180006060
0x180006018  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x18000601f  mov     dword ptr [rbx+8], 0C0000001h
0x180006026  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000602a  mov     [rbx], rax
0x18000602d  cmp     [rcx+28h], dil
0x180006031  jz      short loc_18000603D
0x180006033  mov     [rcx+28h], dil
0x180006037  call    cs:__imp_DeleteCriticalSection
0x18000603d  mov     rcx, rbx
0x180006040  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006046  jmp     short loc_180006060
0x180006048  cmp     edi, 1
0x18000604b  jnz     short loc_180006060
0x18000604d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006054  mov     rdx, [rcx]
0x180006057  mov     rax, [rdx+10h]
0x18000605b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006060  mov     rbx, [rsp+28h+arg_0]
0x180006065  mov     eax, edi
0x180006067  add     rsp, 20h
0x18000606b  pop     rdi
0x18000606c  retn
```
