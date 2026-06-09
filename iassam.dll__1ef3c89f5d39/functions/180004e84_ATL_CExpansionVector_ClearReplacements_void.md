# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180004e84`
- end: `0x180004eee`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `106`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180003144`
- `0x180004f00`

## callees

- `0x180004e84`
- `0x180006b7c`
- `0x1800085e0`
- `0x18000960c`

## import_xrefs

- `msvcrt!free` at `0x180004eac`
- `msvcrt!free` at `0x180004ebf`
- `msvcrt!free` at `0x180004eac`
- `msvcrt!free` at `0x180004ebf`

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
        JUMPOUT(0x180004EEDLL);
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
0x180004e84  mov     [rsp+arg_0], rbx
0x180004e89  push    rdi
0x180004e8a  sub     rsp, 20h
0x180004e8e  mov     eax, [rcx+10h]
0x180004e91  mov     rdi, rcx
0x180004e94  test    eax, eax
0x180004e96  jle     short loc_180004ECE
0x180004e98  xor     ebx, ebx
0x180004e9a  test    ebx, ebx
0x180004e9c  js      short loc_180004EE3
0x180004e9e  cmp     ebx, eax
0x180004ea0  jge     short loc_180004EE3
0x180004ea2  mov     rcx, [rdi]
0x180004ea5  movsxd  rax, ebx
0x180004ea8  mov     rcx, [rcx+rax*8]; Block
0x180004eac  call    cs:__imp_free
0x180004eb2  mov     edx, ebx
0x180004eb4  mov     rcx, rdi
0x180004eb7  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180004ebc  mov     rcx, [rax]; Block
0x180004ebf  call    cs:__imp_free
0x180004ec5  mov     eax, [rdi+10h]
0x180004ec8  inc     ebx
0x180004eca  cmp     ebx, eax
0x180004ecc  jl      short loc_180004E9A
0x180004ece  mov     rcx, rdi
0x180004ed1  call    ?RemoveAll@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::RemoveAll(void)
0x180004ed6  mov     rbx, [rsp+28h+arg_0]
0x180004edb  xor     eax, eax
0x180004edd  add     rsp, 20h
0x180004ee1  pop     rdi
0x180004ee2  retn
0x180004ee3  mov     ecx, 0C000008Ch; unsigned int
0x180004ee8  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
