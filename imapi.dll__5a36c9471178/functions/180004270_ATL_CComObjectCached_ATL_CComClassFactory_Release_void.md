# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180004270`
- end: `0x1800042fc`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `140`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001144`
- `0x180004270`
- `0x180019010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800042c7`
- `KERNEL32!DeleteCriticalSection` at `0x1800042c7`

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
0x180004270  mov     [rsp+arg_0], rbx
0x180004275  push    rdi
0x180004276  sub     rsp, 20h
0x18000427a  mov     rbx, rcx
0x18000427d  mov     r8d, 7FFFFFFFh
0x180004283  mov     ecx, [rcx+8]
0x180004286  jmp     short loc_180004297
0x180004288  lea     edx, [rcx-1]
0x18000428b  mov     eax, ecx
0x18000428d  lock cmpxchg [rbx+8], edx
0x180004292  jz      short loc_18000429C
0x180004294  mov     ecx, [rbx+8]
0x180004297  cmp     ecx, r8d
0x18000429a  jnz     short loc_180004288
0x18000429c  lea     edi, [rcx-1]
0x18000429f  test    edi, edi
0x1800042a1  jnz     short loc_1800042D7
0x1800042a3  test    rbx, rbx
0x1800042a6  jz      short loc_1800042EF
0x1800042a8  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x1800042af  mov     dword ptr [rbx+8], 0C0000001h
0x1800042b6  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800042ba  mov     [rbx], rax
0x1800042bd  cmp     [rcx+28h], dil
0x1800042c1  jz      short loc_1800042CD
0x1800042c3  mov     [rcx+28h], dil
0x1800042c7  call    cs:__imp_DeleteCriticalSection
0x1800042cd  mov     rcx, rbx; Block
0x1800042d0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800042d5  jmp     short loc_1800042EF
0x1800042d7  cmp     edi, 1
0x1800042da  jnz     short loc_1800042EF
0x1800042dc  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800042e3  mov     rdx, [rcx]
0x1800042e6  mov     rax, [rdx+10h]
0x1800042ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042ef  mov     rbx, [rsp+28h+arg_0]
0x1800042f4  mov     eax, edi
0x1800042f6  add     rsp, 20h
0x1800042fa  pop     rdi
0x1800042fb  retn
```
