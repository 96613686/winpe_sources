# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180014314`
- end: `0x18001437e`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `106`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x1800134c8`
- `0x180014390`

## callees

- `0x180014314`
- `0x18001545c`
- `0x180016ad0`
- `0x18001782c`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18001433c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001434f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001433c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18001434f`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::ClearReplacements(ATL::CExpansionVector *this, unsigned int a2)
{
  int v2; // eax
  int i; // ebx
  void **ValueAt; // rax

  v2 = *((_DWORD *)this + 4);
  if ( v2 > 0 )
  {
    for ( i = 0; i < v2; ++i )
    {
      if ( i < 0 || i >= v2 )
      {
        ATL::_AtlRaiseException(0xC000008C, a2);
        JUMPOUT(0x18001437DLL);
      }
      operator delete[](*(void **)(*(_QWORD *)this + 8LL * i));
      ValueAt = (void **)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                           this,
                           (unsigned int)i);
      operator delete[](*ValueAt);
      v2 = *((_DWORD *)this + 4);
    }
  }
  ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::RemoveAll(this);
  return 0;
}

```

## disassembly

```asm
0x180014314  mov     [rsp+arg_0], rbx
0x180014319  push    rdi
0x18001431a  sub     rsp, 20h
0x18001431e  mov     eax, [rcx+10h]
0x180014321  mov     rdi, rcx
0x180014324  test    eax, eax
0x180014326  jle     short loc_18001435E
0x180014328  xor     ebx, ebx
0x18001432a  test    ebx, ebx
0x18001432c  js      short loc_180014373
0x18001432e  cmp     ebx, eax
0x180014330  jge     short loc_180014373
0x180014332  mov     rcx, [rdi]
0x180014335  movsxd  rax, ebx
0x180014338  mov     rcx, [rcx+rax*8]
0x18001433c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180014342  mov     edx, ebx
0x180014344  mov     rcx, rdi
0x180014347  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x18001434c  mov     rcx, [rax]
0x18001434f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180014355  mov     eax, [rdi+10h]
0x180014358  inc     ebx
0x18001435a  cmp     ebx, eax
0x18001435c  jl      short loc_18001432A
0x18001435e  mov     rcx, rdi
0x180014361  call    ?RemoveAll@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::RemoveAll(void)
0x180014366  mov     rbx, [rsp+28h+arg_0]
0x18001436b  xor     eax, eax
0x18001436d  add     rsp, 20h
0x180014371  pop     rdi
0x180014372  retn
0x180014373  mov     ecx, 0C000008Ch; unsigned int
0x180014378  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
