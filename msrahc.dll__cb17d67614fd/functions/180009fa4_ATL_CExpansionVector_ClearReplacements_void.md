# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180009fa4`
- end: `0x18000a019`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800089e8`
- `0x18000a020`

## callees

- `0x180009fa4`
- `0x18000a850`
- `0x18000bb10`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180009fcc`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009fdf`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009fcc`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009fdf`
- `KERNEL32!RaiseException` at `0x18000a012`
- `KERNEL32!RaiseException` at `0x18000a012`

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
        JUMPOUT(0x18000A018LL);
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
0x180009fa4  mov     [rsp+arg_0], rbx
0x180009fa9  push    rdi
0x180009faa  sub     rsp, 20h
0x180009fae  mov     eax, [rcx+10h]
0x180009fb1  mov     rdi, rcx
0x180009fb4  test    eax, eax
0x180009fb6  jle     short loc_180009FEE
0x180009fb8  xor     ebx, ebx
0x180009fba  test    ebx, ebx
0x180009fbc  js      short loc_18000A003
0x180009fbe  cmp     ebx, eax
0x180009fc0  jge     short loc_18000A003
0x180009fc2  mov     rcx, [rdi]
0x180009fc5  movsxd  rax, ebx
0x180009fc8  mov     rcx, [rcx+rax*8]
0x180009fcc  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180009fd2  mov     edx, ebx
0x180009fd4  mov     rcx, rdi
0x180009fd7  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180009fdc  mov     rcx, [rax]
0x180009fdf  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180009fe5  mov     eax, [rdi+10h]
0x180009fe8  inc     ebx
0x180009fea  cmp     ebx, eax
0x180009fec  jl      short loc_180009FBA
0x180009fee  mov     rcx, rdi
0x180009ff1  call    ?RemoveAll@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::RemoveAll(void)
0x180009ff6  mov     rbx, [rsp+28h+arg_0]
0x180009ffb  xor     eax, eax
0x180009ffd  add     rsp, 20h
0x18000a001  pop     rdi
0x18000a002  retn
0x18000a003  xor     r9d, r9d; lpArguments
0x18000a006  xor     r8d, r8d; nNumberOfArguments
0x18000a009  mov     ecx, 0C000008Ch; dwExceptionCode
0x18000a00e  lea     edx, [r9+1]; dwExceptionFlags
0x18000a012  call    cs:__imp_RaiseException
```
