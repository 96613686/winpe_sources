# ATL::CExpansionVector::ClearReplacements(void)

- ea: `0x180017a24`
- end: `0x180017a97`
- name: `?ClearReplacements@CExpansionVector@ATL@@QEAAJXZ`
- size: `115`
- prototype: `__int64 __fastcall(ATL::CExpansionVector *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180016780`
- `0x180017aa0`

## callees

- `0x1800101c0`
- `0x180017a24`
- `0x18001992c`
- `0x18001ae84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017a90`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017a90`

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
        JUMPOUT(0x180017A96LL);
      }
      operator delete(*(void **)(*(_QWORD *)this + 8LL * i));
      ValueAt = (void **)ATL::CSimpleMap<wchar_t *,wchar_t *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                           this,
                           (unsigned int)i);
      operator delete(*ValueAt);
      v1 = *((_DWORD *)this + 4);
    }
  }
  ATL::CSimpleMap<wchar_t *,wchar_t *,ATL::CExpansionVectorEqualHelper>::RemoveAll(this);
  return 0;
}

```

## disassembly

```asm
0x180017a24  mov     [rsp+arg_0], rbx
0x180017a29  push    rdi
0x180017a2a  sub     rsp, 20h
0x180017a2e  mov     eax, [rcx+10h]
0x180017a31  mov     rdi, rcx
0x180017a34  test    eax, eax
0x180017a36  jle     short loc_180017A6C
0x180017a38  xor     ebx, ebx
0x180017a3a  test    ebx, ebx
0x180017a3c  js      short loc_180017A81
0x180017a3e  cmp     ebx, eax
0x180017a40  jge     short loc_180017A81
0x180017a42  mov     rcx, [rdi]
0x180017a45  movsxd  rax, ebx
0x180017a48  mov     rcx, [rcx+rax*8]; Block
0x180017a4c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180017a51  mov     edx, ebx
0x180017a53  mov     rcx, rdi
0x180017a56  call    ?GetValueAt@?$CSimpleMap@PEA_WPEA_WVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEA_WH@Z; ATL::CSimpleMap<wchar_t *,wchar_t *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x180017a5b  mov     rcx, [rax]; Block
0x180017a5e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180017a63  mov     eax, [rdi+10h]
0x180017a66  inc     ebx
0x180017a68  cmp     ebx, eax
0x180017a6a  jl      short loc_180017A3A
0x180017a6c  mov     rcx, rdi
0x180017a6f  call    ?RemoveAll@?$CSimpleMap@PEA_WPEA_WVCExpansionVectorEqualHelper@ATL@@@ATL@@QEAAXXZ; ATL::CSimpleMap<wchar_t *,wchar_t *,ATL::CExpansionVectorEqualHelper>::RemoveAll(void)
0x180017a74  mov     rbx, [rsp+28h+arg_0]
0x180017a79  xor     eax, eax
0x180017a7b  add     rsp, 20h
0x180017a7f  pop     rdi
0x180017a80  retn
0x180017a81  xor     r9d, r9d; lpArguments
0x180017a84  xor     r8d, r8d; nNumberOfArguments
0x180017a87  mov     ecx, 0C000008Ch; dwExceptionCode
0x180017a8c  lea     edx, [r9+1]; dwExceptionFlags
0x180017a90  call    cs:__imp_RaiseException
```
