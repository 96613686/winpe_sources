# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180004b98`
- end: `0x180004c0b`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `115`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180003f7c`
- `0x180004c20`

## callees

- `0x180002294`
- `0x180004b98`
- `0x180004efc`
- `0x180005f1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180004c04`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180004c04`

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
        JUMPOUT(0x180004C0ALL);
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
0x180004b98  mov     [rsp+arg_0], rbx
0x180004b9d  push    rdi
0x180004b9e  sub     rsp, 20h
0x180004ba2  mov     eax, [rcx+10h]
0x180004ba5  mov     rdi, rcx
0x180004ba8  test    eax, eax
0x180004baa  jle     short loc_180004BE0
0x180004bac  xor     ebx, ebx
0x180004bae  test    ebx, ebx
0x180004bb0  js      short loc_180004BF5
0x180004bb2  cmp     ebx, eax
0x180004bb4  jge     short loc_180004BF5
0x180004bb6  mov     rcx, [rdi]
0x180004bb9  movsxd  rax, ebx
0x180004bbc  mov     rcx, [rcx+rax*8]; void *
0x180004bc0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004bc5  mov     edx, ebx
0x180004bc7  mov     rcx, rdi
0x180004bca  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180004bcf  mov     rcx, [rax]; void *
0x180004bd2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004bd7  mov     eax, [rdi+10h]
0x180004bda  inc     ebx
0x180004bdc  cmp     ebx, eax
0x180004bde  jl      short loc_180004BAE
0x180004be0  mov     rcx, rdi
0x180004be3  call    ?RemoveAll@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::RemoveAll(void)
0x180004be8  mov     rbx, [rsp+28h+arg_0]
0x180004bed  xor     eax, eax
0x180004bef  add     rsp, 20h
0x180004bf3  pop     rdi
0x180004bf4  retn
0x180004bf5  xor     r9d, r9d; lpArguments
0x180004bf8  xor     r8d, r8d; nNumberOfArguments
0x180004bfb  mov     ecx, 0C000008Ch; dwExceptionCode
0x180004c00  lea     edx, [r9+1]; dwExceptionFlags
0x180004c04  call    cs:__imp_RaiseException
```
