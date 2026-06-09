# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x18000f9ac`
- end: `0x18000fa16`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `106`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000e3dc`
- `0x18000fa20`

## callees

- `0x18000f9ac`
- `0x180010364`
- `0x1800118a0`
- `0x18001236c`

## import_xrefs

- `msvcrt!free` at `0x18000f9d4`
- `msvcrt!free` at `0x18000f9e7`
- `msvcrt!free` at `0x18000f9d4`
- `msvcrt!free` at `0x18000f9e7`

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
        JUMPOUT(0x18000FA15LL);
      }
      free(*(void **)(*(_QWORD *)this + 8LL * i));
      ValueAt = (void **)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                           this,
                           (unsigned int)i);
      free(*ValueAt);
      v2 = *((_DWORD *)this + 4);
    }
  }
  ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::RemoveAll(this);
  return 0;
}

```

## disassembly

```asm
0x18000f9ac  mov     [rsp+arg_0], rbx
0x18000f9b1  push    rdi
0x18000f9b2  sub     rsp, 20h
0x18000f9b6  mov     eax, [rcx+10h]
0x18000f9b9  mov     rdi, rcx
0x18000f9bc  test    eax, eax
0x18000f9be  jle     short loc_18000F9F6
0x18000f9c0  xor     ebx, ebx
0x18000f9c2  test    ebx, ebx
0x18000f9c4  js      short loc_18000FA0B
0x18000f9c6  cmp     ebx, eax
0x18000f9c8  jge     short loc_18000FA0B
0x18000f9ca  mov     rcx, [rdi]
0x18000f9cd  movsxd  rax, ebx
0x18000f9d0  mov     rcx, [rcx+rax*8]; Block
0x18000f9d4  call    cs:__imp_free
0x18000f9da  mov     edx, ebx
0x18000f9dc  mov     rcx, rdi
0x18000f9df  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x18000f9e4  mov     rcx, [rax]; Block
0x18000f9e7  call    cs:__imp_free
0x18000f9ed  mov     eax, [rdi+10h]
0x18000f9f0  inc     ebx
0x18000f9f2  cmp     ebx, eax
0x18000f9f4  jl      short loc_18000F9C2
0x18000f9f6  mov     rcx, rdi
0x18000f9f9  call    ?RemoveAll@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::RemoveAll(void)
0x18000f9fe  mov     rbx, [rsp+28h+arg_0]
0x18000fa03  xor     eax, eax
0x18000fa05  add     rsp, 20h
0x18000fa09  pop     rdi
0x18000fa0a  retn
0x18000fa0b  mov     ecx, 0C000008Ch; unsigned int
0x18000fa10  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
