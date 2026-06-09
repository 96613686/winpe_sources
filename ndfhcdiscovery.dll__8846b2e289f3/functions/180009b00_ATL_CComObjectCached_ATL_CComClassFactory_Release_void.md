# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180009b00`
- end: `0x180009b9a`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `154`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180009b00`
- `0x180015010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180009b66`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009b66`
- `KERNEL32!DeleteCriticalSection` at `0x180009b57`
- `KERNEL32!DeleteCriticalSection` at `0x180009b57`

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
    (*(void (__fastcall **)(ATL::CAtlModule *, _QWORD, __int64))(*(_QWORD *)ATL::_pAtlModule + 16LL))(
      ATL::_pAtlModule,
      *(_QWORD *)ATL::_pAtlModule,
      0x7FFFFFFF);
  }
  return v3;
}

```

## disassembly

```asm
0x180009b00  mov     [rsp+arg_0], rbx
0x180009b05  push    rdi
0x180009b06  sub     rsp, 20h
0x180009b0a  mov     rbx, rcx
0x180009b0d  mov     r8d, 7FFFFFFFh
0x180009b13  mov     ecx, [rcx+8]
0x180009b16  jmp     short loc_180009B27
0x180009b18  lea     edx, [rcx-1]
0x180009b1b  mov     eax, ecx
0x180009b1d  lock cmpxchg [rbx+8], edx
0x180009b22  jz      short loc_180009B2C
0x180009b24  mov     ecx, [rbx+8]
0x180009b27  cmp     ecx, r8d
0x180009b2a  jnz     short loc_180009B18
0x180009b2c  lea     edi, [rcx-1]
0x180009b2f  test    edi, edi
0x180009b31  jnz     short loc_180009B74
0x180009b33  test    rbx, rbx
0x180009b36  jz      short loc_180009B8C
0x180009b38  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180009b3f  mov     dword ptr [rbx+8], 0C0000001h
0x180009b46  lea     rcx, [rbx+10h]; lpCriticalSection
0x180009b4a  mov     [rbx], rax
0x180009b4d  cmp     [rcx+28h], dil
0x180009b51  jz      short loc_180009B63
0x180009b53  mov     [rcx+28h], dil
0x180009b57  call    cs:__imp_DeleteCriticalSection
0x180009b5e  nop     dword ptr [rax+rax+00h]
0x180009b63  mov     rcx, rbx
0x180009b66  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180009b6d  nop     dword ptr [rax+rax+00h]
0x180009b72  jmp     short loc_180009B8C
0x180009b74  cmp     edi, 1
0x180009b77  jnz     short loc_180009B8C
0x180009b79  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180009b80  mov     rdx, [rcx]
0x180009b83  mov     rax, [rdx+10h]
0x180009b87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b8c  mov     rbx, [rsp+28h+arg_0]
0x180009b91  mov     eax, edi
0x180009b93  add     rsp, 20h
0x180009b97  pop     rdi
0x180009b98  retn
```
