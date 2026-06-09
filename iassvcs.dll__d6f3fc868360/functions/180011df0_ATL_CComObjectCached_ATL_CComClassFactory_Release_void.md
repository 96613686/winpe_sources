# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180011df0`
- end: `0x180011e7d`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `141`
- prototype: `__int64 __fastcall(char *Block)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180011df0`
- `0x180019010`

## import_xrefs

- `msvcrt!free` at `0x180011e50`
- `msvcrt!free` at `0x180011e50`
- `KERNEL32!DeleteCriticalSection` at `0x180011e47`
- `KERNEL32!DeleteCriticalSection` at `0x180011e47`

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
  return v3;
}

```

## disassembly

```asm
0x180011df0  mov     [rsp+arg_0], rbx
0x180011df5  push    rdi
0x180011df6  sub     rsp, 20h
0x180011dfa  mov     rbx, rcx
0x180011dfd  mov     r8d, 7FFFFFFFh
0x180011e03  mov     ecx, [rcx+8]
0x180011e06  jmp     short loc_180011E17
0x180011e08  lea     edx, [rcx-1]
0x180011e0b  mov     eax, ecx
0x180011e0d  lock cmpxchg [rbx+8], edx
0x180011e12  jz      short loc_180011E1C
0x180011e14  mov     ecx, [rbx+8]
0x180011e17  cmp     ecx, r8d
0x180011e1a  jnz     short loc_180011E08
0x180011e1c  lea     edi, [rcx-1]
0x180011e1f  test    edi, edi
0x180011e21  jnz     short loc_180011E58
0x180011e23  test    rbx, rbx
0x180011e26  jz      short loc_180011E70
0x180011e28  lea     rax, ??_7CComClassFactory@ATL@@6B@; const ATL::CComClassFactory::`vftable'
0x180011e2f  mov     dword ptr [rbx+8], 0C0000001h
0x180011e36  lea     rcx, [rbx+10h]; lpCriticalSection
0x180011e3a  mov     [rbx], rax
0x180011e3d  cmp     [rcx+28h], dil
0x180011e41  jz      short loc_180011E4D
0x180011e43  mov     [rcx+28h], dil
0x180011e47  call    cs:__imp_DeleteCriticalSection
0x180011e4d  mov     rcx, rbx; Block
0x180011e50  call    cs:__imp_free
0x180011e56  jmp     short loc_180011E70
0x180011e58  cmp     edi, 1
0x180011e5b  jnz     short loc_180011E70
0x180011e5d  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180011e64  mov     rdx, [rcx]
0x180011e67  mov     rax, [rdx+10h]
0x180011e6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e70  mov     rbx, [rsp+28h+arg_0]
0x180011e75  mov     eax, edi
0x180011e77  add     rsp, 20h
0x180011e7b  pop     rdi
0x180011e7c  retn
```
