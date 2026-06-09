# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180002440`
- end: `0x1800024cc`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `140`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800010e0`
- `0x180002440`
- `0x180005010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180002497`
- `KERNEL32!DeleteCriticalSection` at `0x180002497`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactory>::Release(char *Block)
{
  signed __int32 i; // ecx
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)Block + 2);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange((volatile signed __int32 *)Block + 2, i - 1, i);
        i = *((_DWORD *)Block + 2) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    if ( Block )
    {
      *((_DWORD *)Block + 2) = -1073741823;
      *(_QWORD *)Block = &ATL::CComClassFactory::`vftable';
      if ( Block[56] != (_BYTE)v3 )
      {
        Block[56] = v3;
        DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 16));
      }
      operator delete(Block);
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
0x180002440  mov     [rsp+arg_0], rbx
0x180002445  push    rdi
0x180002446  sub     rsp, 20h
0x18000244a  mov     rbx, rcx
0x18000244d  mov     r8d, 7FFFFFFFh
0x180002453  mov     ecx, [rcx+8]
0x180002456  jmp     short loc_180002467
0x180002458  lea     edx, [rcx-1]
0x18000245b  mov     eax, ecx
0x18000245d  lock cmpxchg [rbx+8], edx
0x180002462  jz      short loc_18000246C
0x180002464  mov     ecx, [rbx+8]
0x180002467  cmp     ecx, r8d
0x18000246a  jnz     short loc_180002458
0x18000246c  lea     edi, [rcx-1]
0x18000246f  test    edi, edi
0x180002471  jnz     short loc_1800024A7
0x180002473  test    rbx, rbx
0x180002476  jz      short loc_1800024BF
0x180002478  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x18000247f  mov     dword ptr [rbx+8], 0C0000001h
0x180002486  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000248a  mov     [rbx], rax
0x18000248d  cmp     [rcx+28h], dil
0x180002491  jz      short loc_18000249D
0x180002493  mov     [rcx+28h], dil
0x180002497  call    cs:__imp_DeleteCriticalSection
0x18000249d  mov     rcx, rbx; Block
0x1800024a0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800024a5  jmp     short loc_1800024BF
0x1800024a7  cmp     edi, 1
0x1800024aa  jnz     short loc_1800024BF
0x1800024ac  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800024b3  mov     rdx, [rcx]
0x1800024b6  mov     rax, [rdx+10h]
0x1800024ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024bf  mov     rbx, [rsp+28h+arg_0]
0x1800024c4  mov     eax, edi
0x1800024c6  add     rsp, 20h
0x1800024ca  pop     rdi
0x1800024cb  retn
```
