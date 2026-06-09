# ATL::CComObjectCached<ATL::CComClassFactory>::Release(void)

- ea: `0x1800043c0`
- end: `0x180004454`
- name: `?Release@?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `148`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800012d0`
- `0x1800043c0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180004417`
- `KERNEL32!DeleteCriticalSection` at `0x18000442b`
- `KERNEL32!DeleteCriticalSection` at `0x180004417`
- `KERNEL32!DeleteCriticalSection` at `0x18000442b`

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
      if ( Block[112] != (_BYTE)v3 )
      {
        Block[112] = v3;
        DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 72));
      }
      if ( Block[56] )
      {
        Block[56] = 0;
        DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 16));
      }
      operator delete(Block);
    }
  }
  else if ( i == 2 )
  {
    _InterlockedDecrement(&dword_18001EB58);
  }
  return v3;
}

```

## disassembly

```asm
0x1800043c0  mov     [rsp+arg_0], rbx
0x1800043c5  push    rdi
0x1800043c6  sub     rsp, 20h
0x1800043ca  mov     rbx, rcx
0x1800043cd  mov     r8d, 7FFFFFFFh
0x1800043d3  mov     ecx, [rcx+8]
0x1800043d6  jmp     short loc_1800043E7
0x1800043d8  lea     edx, [rcx-1]
0x1800043db  mov     eax, ecx
0x1800043dd  lock cmpxchg [rbx+8], edx
0x1800043e2  jz      short loc_1800043EC
0x1800043e4  mov     ecx, [rbx+8]
0x1800043e7  cmp     ecx, r8d
0x1800043ea  jnz     short loc_1800043D8
0x1800043ec  lea     edi, [rcx-1]
0x1800043ef  test    edi, edi
0x1800043f1  jnz     short loc_18000443B
0x1800043f3  test    rbx, rbx
0x1800043f6  jz      short loc_180004447
0x1800043f8  lea     rax, ??_7?$CComObjectCached@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectCached<ATL::CComClassFactory>::`vftable'
0x1800043ff  mov     dword ptr [rbx+8], 1
0x180004406  lea     rcx, [rbx+48h]; lpCriticalSection
0x18000440a  mov     [rbx], rax
0x18000440d  cmp     [rcx+28h], dil
0x180004411  jz      short loc_18000441D
0x180004413  mov     [rcx+28h], dil
0x180004417  call    cs:__imp_DeleteCriticalSection
0x18000441d  lea     rcx, [rbx+10h]; lpCriticalSection
0x180004421  cmp     byte ptr [rcx+28h], 0
0x180004425  jz      short loc_180004431
0x180004427  mov     byte ptr [rcx+28h], 0
0x18000442b  call    cs:__imp_DeleteCriticalSection
0x180004431  mov     rcx, rbx; Block
0x180004434  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004439  jmp     short loc_180004447
0x18000443b  cmp     edi, 1
0x18000443e  jnz     short loc_180004447
0x180004440  lock dec cs:dword_18001EB58
0x180004447  mov     rbx, [rsp+28h+arg_0]
0x18000444c  mov     eax, edi
0x18000444e  add     rsp, 20h
0x180004452  pop     rdi
0x180004453  retn
```
