# ATL::CComObjectNoLock<ATL::CComClassFactory>::Release(void)

- ea: `0x140002960`
- end: `0x1400029d2`
- name: `?Release@?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@UEAAKXZ`
- size: `114`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001054`
- `0x140002960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400029b7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1400029b7`

## pseudocode

```c
__int64 __fastcall ATL::CComObjectNoLock<ATL::CComClassFactory>::Release(char *Block)
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
  if ( i == 1 && Block )
  {
    *((_DWORD *)Block + 2) = 1;
    *(_QWORD *)Block = &ATL::CComObjectNoLock<ATL::CComClassFactory>::`vftable';
    if ( Block[56] != (_BYTE)v3 )
    {
      Block[56] = v3;
      DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 16));
    }
    operator delete(Block);
  }
  return v3;
}

```

## disassembly

```asm
0x140002960  mov     [rsp+arg_0], rbx
0x140002965  push    rdi
0x140002966  sub     rsp, 20h
0x14000296a  mov     rbx, rcx
0x14000296d  mov     r8d, 7FFFFFFFh
0x140002973  mov     ecx, [rcx+8]
0x140002976  jmp     short loc_140002987
0x140002978  lea     edx, [rcx-1]
0x14000297b  mov     eax, ecx
0x14000297d  lock cmpxchg [rbx+8], edx
0x140002982  jz      short loc_14000298C
0x140002984  mov     ecx, [rbx+8]
0x140002987  cmp     ecx, r8d
0x14000298a  jnz     short loc_140002978
0x14000298c  lea     edi, [rcx-1]
0x14000298f  test    edi, edi
0x140002991  jnz     short loc_1400029C5
0x140002993  test    rbx, rbx
0x140002996  jz      short loc_1400029C5
0x140002998  lea     rax, ??_7?$CComObjectNoLock@VCComClassFactory@ATL@@@ATL@@6B@; const ATL::CComObjectNoLock<ATL::CComClassFactory>::`vftable'
0x14000299f  mov     dword ptr [rbx+8], 1
0x1400029a6  lea     rcx, [rbx+10h]; lpCriticalSection
0x1400029aa  mov     [rbx], rax
0x1400029ad  cmp     [rcx+28h], dil
0x1400029b1  jz      short loc_1400029BD
0x1400029b3  mov     [rcx+28h], dil
0x1400029b7  call    cs:__imp_DeleteCriticalSection
0x1400029bd  mov     rcx, rbx; Block
0x1400029c0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400029c5  mov     rbx, [rsp+28h+arg_0]
0x1400029ca  mov     eax, edi
0x1400029cc  add     rsp, 20h
0x1400029d0  pop     rdi
0x1400029d1  retn
```
