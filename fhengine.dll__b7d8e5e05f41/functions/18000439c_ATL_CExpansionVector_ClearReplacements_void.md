# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x18000439c`
- end: `0x180004411`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180003354`
- `0x180004420`

## callees

- `0x18000439c`
- `0x180004e4c`
- `0x180006398`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800043c4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800043d7`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800043c4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800043d7`
- `KERNEL32!RaiseException` at `0x18000440a`
- `KERNEL32!RaiseException` at `0x18000440a`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::ClearReplacements(ATL::CExpansionVector *this)
{
  int v1; // eax
  int i; // ebx
  void **ValueAt; // rax

  v1 = *((_DWORD *)this + 4);
  if ( v1 > 0 )
  {
    for ( i = 0; i < v1; ++i )
    {
      if ( i < 0 || i >= v1 )
      {
        RaiseException(0xC000008C, 1u, 0, 0);
        JUMPOUT(0x180004410LL);
      }
      operator delete[](*(void **)(*(_QWORD *)this + 8LL * i));
      ValueAt = (void **)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                           this,
                           (unsigned int)i);
      operator delete[](*ValueAt);
      v1 = *((_DWORD *)this + 4);
    }
  }
  ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::RemoveAll(this);
  return 0;
}

```

## disassembly

```asm
0x18000439c  mov     [rsp+arg_0], rbx
0x1800043a1  push    rdi
0x1800043a2  sub     rsp, 20h
0x1800043a6  mov     eax, [rcx+10h]
0x1800043a9  mov     rdi, rcx
0x1800043ac  test    eax, eax
0x1800043ae  jle     short loc_1800043E6
0x1800043b0  xor     ebx, ebx
0x1800043b2  test    ebx, ebx
0x1800043b4  js      short loc_1800043FB
0x1800043b6  cmp     ebx, eax
0x1800043b8  jge     short loc_1800043FB
0x1800043ba  mov     rcx, [rdi]
0x1800043bd  movsxd  rax, ebx
0x1800043c0  mov     rcx, [rcx+rax*8]
0x1800043c4  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800043ca  mov     edx, ebx
0x1800043cc  mov     rcx, rdi
0x1800043cf  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x1800043d4  mov     rcx, [rax]
0x1800043d7  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800043dd  mov     eax, [rdi+10h]
0x1800043e0  inc     ebx
0x1800043e2  cmp     ebx, eax
0x1800043e4  jl      short loc_1800043B2
0x1800043e6  mov     rcx, rdi
0x1800043e9  call    ?RemoveAll@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::RemoveAll(void)
0x1800043ee  mov     rbx, [rsp+28h+arg_0]
0x1800043f3  xor     eax, eax
0x1800043f5  add     rsp, 20h
0x1800043f9  pop     rdi
0x1800043fa  retn
0x1800043fb  xor     r9d, r9d; lpArguments
0x1800043fe  xor     r8d, r8d; nNumberOfArguments
0x180004401  mov     ecx, 0C000008Ch; dwExceptionCode
0x180004406  lea     edx, [r9+1]; dwExceptionFlags
0x18000440a  call    cs:__imp_RaiseException
```
