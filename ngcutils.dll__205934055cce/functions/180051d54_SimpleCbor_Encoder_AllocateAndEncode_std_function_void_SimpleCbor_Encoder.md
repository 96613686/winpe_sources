# SimpleCbor::Encoder::AllocateAndEncode(std::function<void (SimpleCbor::Encoder &)>)

- ea: `0x180051d54`
- end: `0x180051e95`
- name: `?AllocateAndEncode@Encoder@SimpleCbor@@SA?AV?$vector@EV?$allocator@E@std@@@std@@V?$function@$$A6AXAEAVEncoder@SimpleCbor@@@Z@4@@Z`
- size: `321`
- prototype: ``
- caller_count: `6`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001b8f0`
- `0x18001bd40`
- `0x18001c130`
- `0x18001c300`
- `0x18001c4e0`
- `0x18001c6c0`

## callees

- `0x180003520`
- `0x18000cfcc`
- `0x1800514c0`
- `0x180051d54`
- `0x1800529c8`
- `0x180052a34`
- `0x180053d30`
- `0x180054748`
- `0x180061010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180051e8e`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180051e8e`

## string_xrefs

- `0x180051d7d`: `onecore\ds\security\cbor\inc\simplecbor\SimpleCbor.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SimpleCbor::Encoder::AllocateAndEncode(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  __int64 v5; // rcx
  void *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v10; // [rsp+30h] [rbp-19h] BYREF
  const char *v11; // [rsp+38h] [rbp-11h]
  void *v12[5]; // [rsp+40h] [rbp-9h] BYREF
  _BYTE v13[56]; // [rsp+68h] [rbp+1Fh] BYREF

  v10 = 395;
  v11 = "onecore\\ds\\security\\cbor\\inc\\simplecbor\\SimpleCbor.h";
  SimpleCbor::Encoder::Encoder(v12, a2, &v10);
  v4 = *(_QWORD *)(a2 + 56);
  if ( !v4 )
    goto LABEL_8;
  (*(void (__fastcall **)(__int64, void **))(*(_QWORD *)v4 + 16LL))(v4, v12);
  v10 = 398;
  v11 = "onecore\\ds\\security\\cbor\\inc\\simplecbor\\SimpleCbor.h";
  if ( !(unsigned __int8)SimpleCbor::Encoder::ExtraBytesNeeded(v12, &v10) )
    goto LABEL_5;
  v10 = 400;
  v11 = "onecore\\ds\\security\\cbor\\inc\\simplecbor\\SimpleCbor.h";
  SimpleCbor::Encoder::ResetAndGrowBufferToRequiredSize(v12, &v10);
  v5 = *(_QWORD *)(a2 + 56);
  if ( !v5 )
  {
LABEL_8:
    std::_Xbad_function_call();
    JUMPOUT(0x180051E95LL);
  }
  (*(void (__fastcall **)(__int64, void **))(*(_QWORD *)v5 + 16LL))(v5, v12);
LABEL_5:
  v10 = 404;
  v11 = "onecore\\ds\\security\\cbor\\inc\\simplecbor\\SimpleCbor.h";
  SimpleCbor::Encoder::FinalizeEncoding(v12, a1, &v10);
  std::vector<unsigned char>::~vector<unsigned char>(v13);
  std::deque<CborEncoder>::_Tidy(v12);
  v6 = v12[0];
  v12[0] = 0;
  operator delete(v6, 0x10u);
  v8 = *(_QWORD *)(a2 + 56);
  if ( v8 )
  {
    LOBYTE(v7) = v8 != a2;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 32LL))(v8, v7);
    *(_QWORD *)(a2 + 56) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180051d54  mov     [rsp-8+arg_8], rdx
0x180051d59  push    rbp
0x180051d5a  push    rbx
0x180051d5b  push    rdi
0x180051d5c  push    r14
0x180051d5e  lea     rbp, [rsp-3Fh]
0x180051d63  sub     rsp, 88h
0x180051d6a  mov     rbx, rdx
0x180051d6d  mov     rdi, rcx
0x180051d70  mov     [rbp+57h+var_70], 18Bh
0x180051d77  mov     eax, [rbp+57h+var_6C]
0x180051d7a  mov     [rbp+57h+var_6C], eax
0x180051d7d  lea     r14, aOnecoreDsSecur_1; "onecore\\ds\\security\\cbor\\inc\\simpl"...
0x180051d84  mov     [rbp+57h+var_68], r14
0x180051d88  lea     r8, [rbp+57h+var_70]
0x180051d8c  lea     rcx, [rbp+57h+var_60]
0x180051d90  call    ??0Encoder@SimpleCbor@@QEAA@_KUslim_source_location@impl@1@@Z; SimpleCbor::Encoder::Encoder(unsigned __int64,SimpleCbor::impl::slim_source_location)
0x180051d95  nop
0x180051d96  mov     rcx, [rbx+38h]
0x180051d9a  test    rcx, rcx
0x180051d9d  jz      loc_180051E8E
0x180051da3  mov     rax, [rcx]
0x180051da6  lea     rdx, [rbp+57h+var_60]
0x180051daa  mov     rax, [rax+10h]
0x180051dae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051db3  mov     [rbp+57h+var_70], 18Eh
0x180051dba  mov     eax, [rbp+57h+var_6C]
0x180051dbd  mov     [rbp+57h+var_6C], eax
0x180051dc0  mov     [rbp+57h+var_68], r14
0x180051dc4  lea     rdx, [rbp+57h+var_70]
0x180051dc8  lea     rcx, [rbp+57h+var_60]
0x180051dcc  call    ?ExtraBytesNeeded@Encoder@SimpleCbor@@QEAA_NUslim_source_location@impl@2@@Z; SimpleCbor::Encoder::ExtraBytesNeeded(SimpleCbor::impl::slim_source_location)
0x180051dd1  test    al, al
0x180051dd3  jz      short loc_180051E10
0x180051dd5  mov     [rbp+57h+var_70], 190h
0x180051ddc  mov     eax, [rbp+57h+var_6C]
0x180051ddf  mov     [rbp+57h+var_6C], eax
0x180051de2  mov     [rbp+57h+var_68], r14
0x180051de6  lea     rdx, [rbp+57h+var_70]
0x180051dea  lea     rcx, [rbp+57h+var_60]
0x180051dee  call    ?ResetAndGrowBufferToRequiredSize@Encoder@SimpleCbor@@QEAAXUslim_source_location@impl@2@@Z; SimpleCbor::Encoder::ResetAndGrowBufferToRequiredSize(SimpleCbor::impl::slim_source_location)
0x180051df3  mov     rcx, [rbx+38h]
0x180051df7  test    rcx, rcx
0x180051dfa  jz      loc_180051E8E
0x180051e00  mov     rax, [rcx]
0x180051e03  lea     rdx, [rbp+57h+var_60]
0x180051e07  mov     rax, [rax+10h]
0x180051e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051e10  mov     [rbp+57h+var_70], 194h
0x180051e17  mov     eax, [rbp+57h+var_6C]
0x180051e1a  mov     [rbp+57h+var_6C], eax
0x180051e1d  mov     [rbp+57h+var_68], r14
0x180051e21  lea     r8, [rbp+57h+var_70]
0x180051e25  mov     rdx, rdi
0x180051e28  lea     rcx, [rbp+57h+var_60]
0x180051e2c  call    ?FinalizeEncoding@Encoder@SimpleCbor@@QEAA?AV?$vector@EV?$allocator@E@std@@@std@@Uslim_source_location@impl@2@@Z; SimpleCbor::Encoder::FinalizeEncoding(SimpleCbor::impl::slim_source_location)
0x180051e31  nop
0x180051e32  lea     rcx, [rbp+57h+var_38]
0x180051e36  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180051e3b  lea     rcx, [rbp+57h+var_60]
0x180051e3f  call    ?_Tidy@?$deque@UCborEncoder@@V?$allocator@UCborEncoder@@@std@@@std@@AEAAXXZ; std::deque<CborEncoder>::_Tidy(void)
0x180051e44  mov     rcx, [rbp+57h+var_60]; void *
0x180051e48  mov     [rbp+57h+var_60], 0
0x180051e50  mov     edx, 10h; unsigned __int64
0x180051e55  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180051e5a  nop
0x180051e5b  mov     rcx, [rbx+38h]
0x180051e5f  test    rcx, rcx
0x180051e62  jz      short loc_180051E7E
0x180051e64  mov     rax, [rcx]
0x180051e67  cmp     rcx, rbx
0x180051e6a  setnz   dl
0x180051e6d  mov     rax, [rax+20h]
0x180051e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051e76  mov     qword ptr [rbx+38h], 0
0x180051e7e  mov     rax, rdi
0x180051e81  add     rsp, 88h
0x180051e88  pop     r14
0x180051e8a  pop     rdi
0x180051e8b  pop     rbx
0x180051e8c  pop     rbp
0x180051e8d  retn
0x180051e8e  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180051e94  nop
```
