# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x1800099d4`
- end: `0x180009a47`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `115`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180008cf0`
- `0x180009a50`

## callees

- `0x18000124c`
- `0x1800099d4`
- `0x18000a3bc`
- `0x18000b4d0`

## import_xrefs

- `KERNEL32!RaiseException` at `0x180009a40`
- `KERNEL32!RaiseException` at `0x180009a40`

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
        JUMPOUT(0x180009A46LL);
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
0x1800099d4  mov     [rsp+arg_0], rbx
0x1800099d9  push    rdi
0x1800099da  sub     rsp, 20h
0x1800099de  mov     eax, [rcx+10h]
0x1800099e1  mov     rdi, rcx
0x1800099e4  test    eax, eax
0x1800099e6  jle     short loc_180009A1C
0x1800099e8  xor     ebx, ebx
0x1800099ea  test    ebx, ebx
0x1800099ec  js      short loc_180009A31
0x1800099ee  cmp     ebx, eax
0x1800099f0  jge     short loc_180009A31
0x1800099f2  mov     rcx, [rdi]
0x1800099f5  movsxd  rax, ebx
0x1800099f8  mov     rcx, [rcx+rax*8]; Block
0x1800099fc  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180009a01  mov     edx, ebx
0x180009a03  mov     rcx, rdi
0x180009a06  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180009a0b  mov     rcx, [rax]; Block
0x180009a0e  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180009a13  mov     eax, [rdi+10h]
0x180009a16  inc     ebx
0x180009a18  cmp     ebx, eax
0x180009a1a  jl      short loc_1800099EA
0x180009a1c  mov     rcx, rdi
0x180009a1f  call    ?RemoveAll@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::RemoveAll(void)
0x180009a24  mov     rbx, [rsp+28h+arg_0]
0x180009a29  xor     eax, eax
0x180009a2b  add     rsp, 20h
0x180009a2f  pop     rdi
0x180009a30  retn
0x180009a31  xor     r9d, r9d; lpArguments
0x180009a34  xor     r8d, r8d; nNumberOfArguments
0x180009a37  mov     ecx, 0C000008Ch; dwExceptionCode
0x180009a3c  lea     edx, [r9+1]; dwExceptionFlags
0x180009a40  call    cs:__imp_RaiseException
```
