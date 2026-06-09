# ATL::CComObjectCached<ATL::CComClassFactorySingleton<AuditChannel>>::Release(void)

- ea: `0x180011c70`
- end: `0x180011d1d`
- name: `?Release@?$CComObjectCached@V?$CComClassFactorySingleton@VAuditChannel@@@ATL@@@ATL@@UEAAKXZ`
- size: `173`
- prototype: `__int64 __fastcall(char *Block, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180011c70`
- `0x180019010`

## import_xrefs

- `msvcrt!free` at `0x180011cf0`
- `msvcrt!free` at `0x180011cf0`
- `KERNEL32!DeleteCriticalSection` at `0x180011ce7`
- `KERNEL32!DeleteCriticalSection` at `0x180011ce7`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectCached<ATL::CComClassFactorySingleton<AuditChannel>>::Release(
        char *Block,
        __int64 a2)
{
  signed __int32 i; // ecx
  unsigned __int32 v4; // edi
  __int64 v5; // rcx

  for ( i = *((_DWORD *)Block + 2); i != 0x7FFFFFFF; i = *((_DWORD *)Block + 2) )
  {
    a2 = (unsigned int)(i - 1);
    if ( i == _InterlockedCompareExchange((volatile signed __int32 *)Block + 2, a2, i) )
      break;
  }
  v4 = i - 1;
  if ( i == 1 )
  {
    if ( Block )
    {
      *((_DWORD *)Block + 2) = -1073741823;
      *(_QWORD *)Block = &ATL::CComClassFactorySingleton<AuditChannel>::`vftable';
      v5 = *((_QWORD *)Block + 10);
      if ( v5 )
        (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v5 + 16LL))(v5, a2, 0x7FFFFFFF);
      *(_QWORD *)Block = &ATL::CComClassFactory::`vftable';
      if ( Block[56] )
      {
        Block[56] = 0;
        DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 16));
      }
      free(Block);
    }
  }
  else if ( i == 2 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *, _QWORD, __int64))(*(_QWORD *)ATL::_pAtlModule + 16LL))(
      ATL::_pAtlModule,
      *(_QWORD *)ATL::_pAtlModule,
      0x7FFFFFFF);
  }
  return v4;
}

```

## disassembly

```asm
0x180011c70  mov     [rsp+arg_0], rbx
0x180011c75  push    rdi
0x180011c76  sub     rsp, 20h
0x180011c7a  mov     rbx, rcx
0x180011c7d  mov     ecx, [rcx+8]
0x180011c80  mov     r8d, 7FFFFFFFh
0x180011c86  jmp     short loc_180011C97
0x180011c88  lea     edx, [rcx-1]
0x180011c8b  mov     eax, ecx
0x180011c8d  lock cmpxchg [rbx+8], edx
0x180011c92  jz      short loc_180011C9C
0x180011c94  mov     ecx, [rbx+8]
0x180011c97  cmp     ecx, r8d
0x180011c9a  jnz     short loc_180011C88
0x180011c9c  lea     edi, [rcx-1]
0x180011c9f  test    edi, edi
0x180011ca1  jnz     short loc_180011CF8
0x180011ca3  test    rbx, rbx
0x180011ca6  jz      short loc_180011D10
0x180011ca8  mov     dword ptr [rbx+8], 0C0000001h
0x180011caf  lea     rax, ??_7?$CComClassFactorySingleton@VAuditChannel@@@ATL@@6B@; const ATL::CComClassFactorySingleton<AuditChannel>::`vftable'
0x180011cb6  mov     [rbx], rax
0x180011cb9  mov     rcx, [rbx+50h]
0x180011cbd  test    rcx, rcx
0x180011cc0  jz      short loc_180011CCF
0x180011cc2  mov     rax, [rcx]
0x180011cc5  mov     rax, [rax+10h]
0x180011cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cce  nop
0x180011ccf  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180011cd6  mov     [rbx], rax
0x180011cd9  lea     rcx, [rbx+10h]; lpCriticalSection
0x180011cdd  cmp     byte ptr [rcx+28h], 0
0x180011ce1  jz      short loc_180011CED
0x180011ce3  mov     byte ptr [rcx+28h], 0
0x180011ce7  call    cs:__imp_DeleteCriticalSection
0x180011ced  mov     rcx, rbx; Block
0x180011cf0  call    cs:__imp_free
0x180011cf6  jmp     short loc_180011D10
0x180011cf8  cmp     edi, 1
0x180011cfb  jnz     short loc_180011D10
0x180011cfd  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180011d04  mov     rdx, [rcx]
0x180011d07  mov     rax, [rdx+10h]
0x180011d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d10  mov     eax, edi
0x180011d12  mov     rbx, [rsp+28h+arg_0]
0x180011d17  add     rsp, 20h
0x180011d1b  pop     rdi
0x180011d1c  retn
```
