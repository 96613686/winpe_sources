# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180008850`
- end: `0x1800088dd`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180008850`
- `0x180012010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800088b0`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800088b0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800088a7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800088a7`

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
0x180008850  mov     [rsp+arg_0], rbx
0x180008855  push    rdi
0x180008856  sub     rsp, 20h
0x18000885a  mov     rbx, rcx
0x18000885d  mov     r8d, 7FFFFFFFh
0x180008863  mov     ecx, [rcx+8]
0x180008866  jmp     short loc_180008877
0x180008868  lea     edx, [rcx-1]
0x18000886b  mov     eax, ecx
0x18000886d  lock cmpxchg [rbx+8], edx
0x180008872  jz      short loc_18000887C
0x180008874  mov     ecx, [rbx+8]
0x180008877  cmp     ecx, r8d
0x18000887a  jnz     short loc_180008868
0x18000887c  lea     edi, [rcx-1]
0x18000887f  test    edi, edi
0x180008881  jnz     short loc_1800088B8
0x180008883  test    rbx, rbx
0x180008886  jz      short loc_1800088D0
0x180008888  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x18000888f  mov     dword ptr [rbx+8], 0C0000001h
0x180008896  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000889a  mov     [rbx], rax
0x18000889d  cmp     [rcx+28h], dil
0x1800088a1  jz      short loc_1800088AD
0x1800088a3  mov     [rcx+28h], dil
0x1800088a7  call    cs:__imp_DeleteCriticalSection
0x1800088ad  mov     rcx, rbx
0x1800088b0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800088b6  jmp     short loc_1800088D0
0x1800088b8  cmp     edi, 1
0x1800088bb  jnz     short loc_1800088D0
0x1800088bd  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800088c4  mov     rdx, [rcx]
0x1800088c7  mov     rax, [rdx+10h]
0x1800088cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088d0  mov     rbx, [rsp+28h+arg_0]
0x1800088d5  mov     eax, edi
0x1800088d7  add     rsp, 20h
0x1800088db  pop     rdi
0x1800088dc  retn
```
