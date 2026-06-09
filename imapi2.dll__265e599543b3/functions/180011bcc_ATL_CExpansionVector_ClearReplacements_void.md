# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180011bcc`
- end: `0x180011c3f`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `115`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180011108`
- `0x180011c50`

## callees

- `0x18000fdbc`
- `0x180011bcc`
- `0x18001203c`
- `0x180013844`

## import_xrefs

- `KERNEL32!RaiseException` at `0x180011c38`
- `KERNEL32!RaiseException` at `0x180011c38`

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
        JUMPOUT(0x180011C3ELL);
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
0x180011bcc  mov     [rsp+arg_0], rbx
0x180011bd1  push    rdi
0x180011bd2  sub     rsp, 20h
0x180011bd6  mov     eax, [rcx+10h]
0x180011bd9  mov     rdi, rcx
0x180011bdc  test    eax, eax
0x180011bde  jle     short loc_180011C14
0x180011be0  xor     ebx, ebx
0x180011be2  test    ebx, ebx
0x180011be4  js      short loc_180011C29
0x180011be6  cmp     ebx, eax
0x180011be8  jge     short loc_180011C29
0x180011bea  mov     rcx, [rdi]
0x180011bed  movsxd  rax, ebx
0x180011bf0  mov     rcx, [rcx+rax*8]; Block
0x180011bf4  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180011bf9  mov     edx, ebx
0x180011bfb  mov     rcx, rdi
0x180011bfe  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180011c03  mov     rcx, [rax]; Block
0x180011c06  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180011c0b  mov     eax, [rdi+10h]
0x180011c0e  inc     ebx
0x180011c10  cmp     ebx, eax
0x180011c12  jl      short loc_180011BE2
0x180011c14  mov     rcx, rdi
0x180011c17  call    ?RemoveAll@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::RemoveAll(void)
0x180011c1c  mov     rbx, [rsp+28h+arg_0]
0x180011c21  xor     eax, eax
0x180011c23  add     rsp, 20h
0x180011c27  pop     rdi
0x180011c28  retn
0x180011c29  xor     r9d, r9d; lpArguments
0x180011c2c  xor     r8d, r8d; nNumberOfArguments
0x180011c2f  mov     ecx, 0C000008Ch; dwExceptionCode
0x180011c34  lea     edx, [r9+1]; dwExceptionFlags
0x180011c38  call    cs:__imp_RaiseException
```
