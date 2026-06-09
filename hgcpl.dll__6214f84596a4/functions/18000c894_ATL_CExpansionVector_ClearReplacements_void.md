# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x18000c894`
- end: `0x18000c907`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `115`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000bd2c`
- `0x18000c910`

## callees

- `0x18000bd88`
- `0x18000c894`
- `0x18000cdec`
- `0x18000dd68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000c900`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000c900`

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
        JUMPOUT(0x18000C906LL);
      }
      operator delete(*(void **)(*(_QWORD *)this + 8LL * i));
      ValueAt = (void **)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                           this,
                           (unsigned int)i);
      operator delete(*ValueAt);
      v1 = *((_DWORD *)this + 4);
    }
  }
  ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::RemoveAll(this);
  return 0;
}

```

## disassembly

```asm
0x18000c894  mov     [rsp+arg_0], rbx
0x18000c899  push    rdi
0x18000c89a  sub     rsp, 20h
0x18000c89e  mov     eax, [rcx+10h]
0x18000c8a1  mov     rdi, rcx
0x18000c8a4  test    eax, eax
0x18000c8a6  jle     short loc_18000C8DC
0x18000c8a8  xor     ebx, ebx
0x18000c8aa  test    ebx, ebx
0x18000c8ac  js      short loc_18000C8F1
0x18000c8ae  cmp     ebx, eax
0x18000c8b0  jge     short loc_18000C8F1
0x18000c8b2  mov     rcx, [rdi]
0x18000c8b5  movsxd  rax, ebx
0x18000c8b8  mov     rcx, [rcx+rax*8]; lpMem
0x18000c8bc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c8c1  mov     edx, ebx
0x18000c8c3  mov     rcx, rdi
0x18000c8c6  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x18000c8cb  mov     rcx, [rax]; lpMem
0x18000c8ce  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000c8d3  mov     eax, [rdi+10h]
0x18000c8d6  inc     ebx
0x18000c8d8  cmp     ebx, eax
0x18000c8da  jl      short loc_18000C8AA
0x18000c8dc  mov     rcx, rdi
0x18000c8df  call    ?RemoveAll@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::RemoveAll(void)
0x18000c8e4  mov     rbx, [rsp+28h+arg_0]
0x18000c8e9  xor     eax, eax
0x18000c8eb  add     rsp, 20h
0x18000c8ef  pop     rdi
0x18000c8f0  retn
0x18000c8f1  xor     r9d, r9d; lpArguments
0x18000c8f4  xor     r8d, r8d; nNumberOfArguments
0x18000c8f7  mov     ecx, 0C000008Ch; dwExceptionCode
0x18000c8fc  lea     edx, [r9+1]; dwExceptionFlags
0x18000c900  call    cs:__imp_RaiseException
```
