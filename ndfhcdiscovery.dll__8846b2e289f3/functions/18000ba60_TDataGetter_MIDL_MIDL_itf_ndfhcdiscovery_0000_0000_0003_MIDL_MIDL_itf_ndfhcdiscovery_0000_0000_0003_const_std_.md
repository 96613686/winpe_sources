# TDataGetter<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003,__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003 const,std::vector<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003,std::allocator<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003>>>,TNDFDeallocator<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003 *,&FreeProviders(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003 *,ulong,int)>,&CopyProvider(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003 *,__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003 const *)>(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003 * *,ulong *,std::vector<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003,std::allocator<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003>> &)

- ea: `0x18000ba60`
- end: `0x18000bb43`
- name: `??$TDataGetter@U__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003@@$$CBU1@V?$vector@U__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003@@V?$allocator@U__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003@@@std@@@std@@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@U__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003@@@std@@@std@@@3@V?$TNDFDeallocator@PEAU__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003@@$1?FreeProviders@@YAXPEAU1@KH@Z@@$1?CopyProvider@@YAJPEAU1@PEBU1@@Z@@YAJPEAPEAU__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003@@PEAKAEAV?$vector@U__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003@@V?$allocator@U__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003@@@std@@@std@@@Z`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000de10`

## callees

- `0x18000ba60`
- `0x18000c598`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ba97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ba97`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TDataGetter<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003,__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003 const,std::vector<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003>>>,TNDFDeallocator<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003 *,&void FreeProviders(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003 *,unsigned long,int)>,&long CopyProvider(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003 *,__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0003 const *)>(
        _QWORD *a1,
        _DWORD *a2,
        _QWORD *a3)
{
  unsigned __int64 v6; // rbx
  __int64 v7; // rdi
  _BYTE *v8; // rax
  _BYTE *v9; // rsi
  _OWORD *v11; // rax
  unsigned int i; // ecx
  __int64 v13; // rdx

  v6 = (__int64)(a3[1] - *a3) >> 5;
  if ( v6 )
  {
    v7 = 32 * v6;
    v8 = CoTaskMemAlloc(32 * v6);
    v9 = v8;
    if ( !v8 )
      return 2147942414LL;
    for ( ; v7; --v7 )
      *v8++ = 0;
    wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v6);
    v11 = (_OWORD *)*a3;
    for ( i = 0; i < v6; ++i )
    {
      if ( v11 == (_OWORD *)a3[1] )
        break;
      v13 = 32LL * i;
      *(_OWORD *)&v9[v13] = *v11;
      *(_OWORD *)&v9[v13 + 16] = v11[1];
      v11 += 2;
    }
    *a1 = v9;
    *a2 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v6);
  }
  else
  {
    *a2 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x18000ba60  push    rbx
0x18000ba62  push    rbp
0x18000ba63  push    rsi
0x18000ba64  push    rdi
0x18000ba65  push    r14
0x18000ba67  push    r15
0x18000ba69  sub     rsp, 38h
0x18000ba6d  mov     r14, r8
0x18000ba70  mov     r15, rdx
0x18000ba73  mov     rbp, rcx
0x18000ba76  mov     rbx, [r8+8]
0x18000ba7a  sub     rbx, [r8]
0x18000ba7d  sar     rbx, 5
0x18000ba81  test    rbx, rbx
0x18000ba84  jnz     short loc_18000BA8D
0x18000ba86  mov     [rdx], ebx
0x18000ba88  jmp     loc_18000BB33
0x18000ba8d  mov     rdi, rbx
0x18000ba90  shl     rdi, 5
0x18000ba94  mov     rcx, rdi; cb
0x18000ba97  call    cs:__imp_CoTaskMemAlloc
0x18000ba9e  nop     dword ptr [rax+rax+00h]
0x18000baa3  mov     rsi, rax
0x18000baa6  test    rax, rax
0x18000baa9  jnz     short loc_18000BAB5
0x18000baab  mov     eax, 8007000Eh
0x18000bab0  jmp     loc_18000BB35
0x18000bab5  test    rdi, rdi
0x18000bab8  jz      short loc_18000BAC6
0x18000baba  mov     byte ptr [rax], 0
0x18000babd  inc     rax
0x18000bac0  sub     rdi, 1
0x18000bac4  jnz     short loc_18000BABA
0x18000bac6  mov     rcx, rbx
0x18000bac9  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18000bace  mov     [rsp+68h+var_48], rsi
0x18000bad3  mov     dword ptr [rsp+68h+var_40], eax
0x18000bad7  mov     dword ptr [rsp+68h+var_40+4], 1
0x18000badf  mov     rax, [r14]
0x18000bae2  xor     ecx, ecx
0x18000bae4  test    rbx, rbx
0x18000bae7  jz      short loc_18000BB12
0x18000bae9  cmp     rax, [r14+8]
0x18000baed  jz      short loc_18000BB12
0x18000baef  mov     edx, ecx
0x18000baf1  shl     rdx, 5
0x18000baf5  movups  xmm0, xmmword ptr [rax]
0x18000baf8  movups  xmmword ptr [rdx+rsi], xmm0
0x18000bafc  movups  xmm1, xmmword ptr [rax+10h]
0x18000bb00  movups  xmmword ptr [rdx+rsi+10h], xmm1
0x18000bb05  add     rax, 20h ; ' '
0x18000bb09  inc     ecx
0x18000bb0b  mov     edx, ecx
0x18000bb0d  cmp     rdx, rbx
0x18000bb10  jb      short loc_18000BAE9
0x18000bb12  mov     [rsp+68h+var_48], 0
0x18000bb1b  mov     [rsp+68h+var_40], 0
0x18000bb24  mov     [rbp+0], rsi
0x18000bb28  mov     rcx, rbx
0x18000bb2b  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18000bb30  mov     [r15], eax
0x18000bb33  xor     eax, eax
0x18000bb35  add     rsp, 38h
0x18000bb39  pop     r15
0x18000bb3b  pop     r14
0x18000bb3d  pop     rdi
0x18000bb3e  pop     rsi
0x18000bb3f  pop     rbp
0x18000bb40  pop     rbx
0x18000bb41  retn
```
