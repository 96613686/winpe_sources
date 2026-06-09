# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x18000a4a0`
- end: `0x18000a516`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `118`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001048`
- `0x18000a4a0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000a4ed`
- `KERNEL32!DeleteCriticalSection` at `0x18000a4ed`

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
      *((_DWORD *)Block + 2) = 1;
      *(_QWORD *)Block = &ATL::CComObjectCached<ATL::CComClassFactory>::`vftable';
      DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 16));
      operator delete(Block);
    }
  }
  else if ( i == 2 )
  {
    _InterlockedDecrement(&dword_180017A78);
  }
  return v3;
}

```

## disassembly

```asm
0x18000a4a0  mov     [rsp+arg_0], rbx
0x18000a4a5  push    rdi
0x18000a4a6  sub     rsp, 20h
0x18000a4aa  mov     rbx, rcx
0x18000a4ad  mov     r8d, 7FFFFFFFh
0x18000a4b3  mov     ecx, [rcx+8]
0x18000a4b6  jmp     short loc_18000A4C7
0x18000a4b8  lea     edx, [rcx-1]
0x18000a4bb  mov     eax, ecx
0x18000a4bd  lock cmpxchg [rbx+8], edx
0x18000a4c2  jz      short loc_18000A4CC
0x18000a4c4  mov     ecx, [rbx+8]
0x18000a4c7  cmp     ecx, r8d
0x18000a4ca  jnz     short loc_18000A4B8
0x18000a4cc  lea     edi, [rcx-1]
0x18000a4cf  test    edi, edi
0x18000a4d1  jnz     short loc_18000A4FD
0x18000a4d3  test    rbx, rbx
0x18000a4d6  jz      short loc_18000A509
0x18000a4d8  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x18000a4df  mov     dword ptr [rbx+8], 1
0x18000a4e6  lea     rcx, [rbx+10h]; lpCriticalSection
0x18000a4ea  mov     [rbx], rax
0x18000a4ed  call    cs:__imp_DeleteCriticalSection
0x18000a4f3  mov     rcx, rbx; Block
0x18000a4f6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a4fb  jmp     short loc_18000A509
0x18000a4fd  cmp     edi, 1
0x18000a500  jnz     short loc_18000A509
0x18000a502  lock dec cs:dword_180017A78
0x18000a509  mov     rbx, [rsp+28h+arg_0]
0x18000a50e  mov     eax, edi
0x18000a510  add     rsp, 20h
0x18000a514  pop     rdi
0x18000a515  retn
```
