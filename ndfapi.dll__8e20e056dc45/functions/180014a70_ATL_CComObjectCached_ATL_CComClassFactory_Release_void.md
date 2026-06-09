# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180014a70`
- end: `0x180014afd`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `141`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180014a70`
- `0x180021010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180014ad0`
- `msvcrt!??3@YAXPEAX@Z` at `0x180014ad0`
- `KERNEL32!DeleteCriticalSection` at `0x180014ac7`
- `KERNEL32!DeleteCriticalSection` at `0x180014ac7`

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
0x180014a70  mov     [rsp+arg_0], rbx
0x180014a75  push    rdi
0x180014a76  sub     rsp, 20h
0x180014a7a  mov     rbx, rcx
0x180014a7d  mov     r8d, 7FFFFFFFh
0x180014a83  mov     ecx, [rcx+8]
0x180014a86  jmp     short loc_180014A97
0x180014a88  lea     edx, [rcx-1]
0x180014a8b  mov     eax, ecx
0x180014a8d  lock cmpxchg [rbx+8], edx
0x180014a92  jz      short loc_180014A9C
0x180014a94  mov     ecx, [rbx+8]
0x180014a97  cmp     ecx, r8d
0x180014a9a  jnz     short loc_180014A88
0x180014a9c  lea     edi, [rcx-1]
0x180014a9f  test    edi, edi
0x180014aa1  jnz     short loc_180014AD8
0x180014aa3  test    rbx, rbx
0x180014aa6  jz      short loc_180014AF0
0x180014aa8  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180014aaf  mov     dword ptr [rbx+8], 0C0000001h
0x180014ab6  lea     rcx, [rbx+10h]; lpCriticalSection
0x180014aba  mov     [rbx], rax
0x180014abd  cmp     [rcx+28h], dil
0x180014ac1  jz      short loc_180014ACD
0x180014ac3  mov     [rcx+28h], dil
0x180014ac7  call    cs:__imp_DeleteCriticalSection
0x180014acd  mov     rcx, rbx
0x180014ad0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180014ad6  jmp     short loc_180014AF0
0x180014ad8  cmp     edi, 1
0x180014adb  jnz     short loc_180014AF0
0x180014add  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180014ae4  mov     rdx, [rcx]
0x180014ae7  mov     rax, [rdx+10h]
0x180014aeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014af0  mov     rbx, [rsp+28h+arg_0]
0x180014af5  mov     eax, edi
0x180014af7  add     rsp, 20h
0x180014afb  pop     rdi
0x180014afc  retn
```
