# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x180007690`
- end: `0x180007706`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `118`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001008`
- `0x180007690`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800076dd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800076dd`

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
    _InterlockedDecrement(&dword_18000F8D8);
  }
  return v3;
}

```

## disassembly

```asm
0x180007690  mov     [rsp+arg_0], rbx
0x180007695  push    rdi
0x180007696  sub     rsp, 20h
0x18000769a  mov     rbx, rcx
0x18000769d  mov     r8d, 7FFFFFFFh
0x1800076a3  mov     ecx, [rcx+8]
0x1800076a6  jmp     short loc_1800076B7
0x1800076a8  lea     edx, [rcx-1]
0x1800076ab  mov     eax, ecx
0x1800076ad  lock cmpxchg [rbx+8], edx
0x1800076b2  jz      short loc_1800076BC
0x1800076b4  mov     ecx, [rbx+8]
0x1800076b7  cmp     ecx, r8d
0x1800076ba  jnz     short loc_1800076A8
0x1800076bc  lea     edi, [rcx-1]
0x1800076bf  test    edi, edi
0x1800076c1  jnz     short loc_1800076ED
0x1800076c3  test    rbx, rbx
0x1800076c6  jz      short loc_1800076F9
0x1800076c8  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x1800076cf  mov     dword ptr [rbx+8], 1
0x1800076d6  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800076da  mov     [rbx], rax
0x1800076dd  call    cs:__imp_DeleteCriticalSection
0x1800076e3  mov     rcx, rbx; Block
0x1800076e6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800076eb  jmp     short loc_1800076F9
0x1800076ed  cmp     edi, 1
0x1800076f0  jnz     short loc_1800076F9
0x1800076f2  lock dec cs:dword_18000F8D8
0x1800076f9  mov     rbx, [rsp+28h+arg_0]
0x1800076fe  mov     eax, edi
0x180007700  add     rsp, 20h
0x180007704  pop     rdi
0x180007705  retn
```
