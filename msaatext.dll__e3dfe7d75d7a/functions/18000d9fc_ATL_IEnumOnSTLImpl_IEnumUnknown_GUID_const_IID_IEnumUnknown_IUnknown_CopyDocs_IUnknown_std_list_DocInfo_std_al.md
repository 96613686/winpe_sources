# ATL::IEnumOnSTLImpl<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,CopyDocs<IUnknown>,std::list<DocInfo *,std::allocator<DocInfo *>>,ATL::CComEnumOnSTL<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,CopyDocs<IUnknown>,std::list<DocInfo *,std::allocator<DocInfo *>>,ATL::CComSingleThreadModel>>::Next(ulong,IUnknown * *,ulong *)

- ea: `0x18000d9fc`
- end: `0x18000da9d`
- name: `?Next@?$IEnumOnSTLImpl@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$CopyDocs@UIUnknown@@@@V?$list@PEAUDocInfo@@V?$allocator@PEAUDocInfo@@@std@@@std@@V?$CComEnumOnSTL@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$CopyDocs@UIUnknown@@@@V?$list@PEAUDocInfo@@V?$allocator@PEAUDocInfo@@@std@@@std@@VCComSingleThreadModel@ATL@@@ATL@@@ATL@@UEAAJKPEAPEAUIUnknown@@PEAK@Z`
- size: `161`
- prototype: `__int64 __fastcall(__int64, unsigned int, _QWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000d9f0`

## callees

- `0x18000d9fc`
- `0x180014010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::IEnumOnSTLImpl<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,CopyDocs<IUnknown>,std::list<DocInfo *>,ATL::CComEnumOnSTL<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,CopyDocs<IUnknown>,std::list<DocInfo *>,ATL::CComSingleThreadModel>>::Next(
        __int64 a1,
        unsigned int a2,
        _QWORD *a3,
        unsigned int *a4)
{
  _QWORD *v5; // r14
  unsigned int i; // edi
  __int64 v10; // rcx
  __int64 v11; // rcx

  v5 = a3;
  if ( !a3 || a2 != 1 && !a4 )
    return 2147500035LL;
  if ( a4 )
    *a4 = 0;
  if ( !*(_QWORD *)(a1 + 16) )
    return 2147500037LL;
  for ( i = 0; ; ++i )
  {
    v10 = *(_QWORD *)(a1 + 24);
    if ( v10 == **(_QWORD **)(a1 + 16) || i >= a2 )
      break;
    v11 = *(_QWORD *)(*(_QWORD *)(v10 + 16) + 8LL);
    *v5 = v11;
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
    ++v5;
    *(_QWORD *)(a1 + 24) = **(_QWORD **)(a1 + 24);
  }
  if ( a4 )
    *a4 = i;
  return i < a2;
}

```

## disassembly

```asm
0x18000d9fc  push    rbx
0x18000d9fe  push    rbp
0x18000d9ff  push    rsi
0x18000da00  push    rdi
0x18000da01  push    r14
0x18000da03  sub     rsp, 20h
0x18000da07  mov     rbx, r9
0x18000da0a  mov     r14, r8
0x18000da0d  mov     ebp, edx
0x18000da0f  mov     rsi, rcx
0x18000da12  test    r8, r8
0x18000da15  jz      short loc_18000DA8D
0x18000da17  cmp     edx, 1
0x18000da1a  jz      short loc_18000DA21
0x18000da1c  test    rbx, rbx
0x18000da1f  jz      short loc_18000DA8D
0x18000da21  test    rbx, rbx
0x18000da24  jz      short loc_18000DA2D
0x18000da26  mov     dword ptr [r9], 0
0x18000da2d  cmp     qword ptr [rcx+10h], 0
0x18000da32  jnz     short loc_18000DA3B
0x18000da34  mov     eax, 80004005h
0x18000da39  jmp     short loc_18000DA92
0x18000da3b  xor     edi, edi
0x18000da3d  mov     rax, [rsi+10h]
0x18000da41  mov     rcx, [rsi+18h]
0x18000da45  cmp     rcx, [rax]
0x18000da48  jz      short loc_18000DA7D
0x18000da4a  cmp     edi, ebp
0x18000da4c  jnb     short loc_18000DA7D
0x18000da4e  mov     rax, [rcx+10h]
0x18000da52  mov     rcx, [rax+8]
0x18000da56  mov     [r14], rcx
0x18000da59  test    rcx, rcx
0x18000da5c  jz      short loc_18000DA6A
0x18000da5e  mov     rax, [rcx]
0x18000da61  mov     rax, [rax+8]
0x18000da65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da6a  mov     rax, [rsi+18h]
0x18000da6e  add     r14, 8
0x18000da72  inc     edi
0x18000da74  mov     rcx, [rax]
0x18000da77  mov     [rsi+18h], rcx
0x18000da7b  jmp     short loc_18000DA3D
0x18000da7d  test    rbx, rbx
0x18000da80  jz      short loc_18000DA84
0x18000da82  mov     [rbx], edi
0x18000da84  xor     eax, eax
0x18000da86  cmp     edi, ebp
0x18000da88  setb    al
0x18000da8b  jmp     short loc_18000DA92
0x18000da8d  mov     eax, 80004003h
0x18000da92  add     rsp, 20h
0x18000da96  pop     r14
0x18000da98  pop     rdi
0x18000da99  pop     rsi
0x18000da9a  pop     rbp
0x18000da9b  pop     rbx
0x18000da9c  retn
```
