# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x1800125c0`
- end: `0x180012651`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `145`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800028b0`
- `0x1800125c0`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012617`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012617`

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
0x1800125c0  mov     [rsp+arg_0], rbx
0x1800125c5  push    rdi
0x1800125c6  sub     rsp, 20h
0x1800125ca  mov     rbx, rcx
0x1800125cd  mov     r8d, 7FFFFFFFh
0x1800125d3  mov     ecx, [rcx+8]
0x1800125d6  jmp     short loc_1800125E7
0x1800125d8  lea     edx, [rcx-1]
0x1800125db  mov     eax, ecx
0x1800125dd  lock cmpxchg [rbx+8], edx
0x1800125e2  jz      short loc_1800125EC
0x1800125e4  mov     ecx, [rbx+8]
0x1800125e7  cmp     ecx, r8d
0x1800125ea  jnz     short loc_1800125D8
0x1800125ec  lea     edi, [rcx-1]
0x1800125ef  test    edi, edi
0x1800125f1  jnz     short loc_18001262C
0x1800125f3  test    rbx, rbx
0x1800125f6  jz      short loc_180012644
0x1800125f8  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x1800125ff  mov     dword ptr [rbx+8], 0C0000001h
0x180012606  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001260a  mov     [rbx], rax
0x18001260d  cmp     [rcx+28h], dil
0x180012611  jz      short loc_18001261D
0x180012613  mov     [rcx+28h], dil
0x180012617  call    cs:__imp_DeleteCriticalSection
0x18001261d  mov     edx, 48h ; 'H'
0x180012622  mov     rcx, rbx; Block
0x180012625  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001262a  jmp     short loc_180012644
0x18001262c  cmp     edi, 1
0x18001262f  jnz     short loc_180012644
0x180012631  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180012638  mov     rdx, [rcx]
0x18001263b  mov     rax, [rdx+10h]
0x18001263f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012644  mov     rbx, [rsp+28h+arg_0]
0x180012649  mov     eax, edi
0x18001264b  add     rsp, 20h
0x18001264f  pop     rdi
0x180012650  retn
```
