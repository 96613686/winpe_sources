# TDataGetter<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0002,StoredHelperAttributeInfo const,std::vector<StoredHelperAttributeInfo,std::allocator<StoredHelperAttributeInfo>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<StoredHelperAttributeInfo>>>,TNDFDeallocator<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0002 *,&FreeHelperAttributeInfoExs(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0002 *,ulong,int)>,&CopyAndAllocateAttributeInfo(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0002 *,StoredHelperAttributeInfo const *)>(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0002 * *,ulong *,std::vector<StoredHelperAttributeInfo,std::allocator<StoredHelperAttributeInfo>> &)

- ea: `0x18000b90c`
- end: `0x18000ba5a`
- name: `??$TDataGetter@U__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0002@@$$CBUStoredHelperAttributeInfo@@V?$vector@UStoredHelperAttributeInfo@@V?$allocator@UStoredHelperAttributeInfo@@@std@@@std@@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UStoredHelperAttributeInfo@@@std@@@std@@@4@V?$TNDFDeallocator@PEAU__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0002@@$1?FreeHelperAttributeInfoExs@@YAXPEAU1@KH@Z@@$1?CopyAndAllocateAttributeInfo@@YAJPEAU1@PEBU2@@Z@@YAJPEAPEAU__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0002@@PEAKAEAV?$vector@UStoredHelperAttributeInfo@@V?$allocator@UStoredHelperAttributeInfo@@@std@@@std@@@Z`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d820`

## callees

- `0x18000b90c`
- `0x18000c598`
- `0x18000cfe4`
- `0x18000d46c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b95e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b95e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TDataGetter<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0002,StoredHelperAttributeInfo const,std::vector<StoredHelperAttributeInfo>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<StoredHelperAttributeInfo>>>,TNDFDeallocator<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0002 *,&void FreeHelperAttributeInfoExs(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0002 *,unsigned long,int)>,&long CopyAndAllocateAttributeInfo(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0002 *,StoredHelperAttributeInfo const *)>(
        LPVOID **a1,
        _DWORD *a2,
        const struct StoredHelperAttributeInfo **a3)
{
  unsigned __int64 v4; // rdi
  SIZE_T v6; // rbx
  LPVOID *v7; // rax
  LPVOID *v8; // r15
  int i; // esi
  unsigned int v10; // r12d
  LPVOID *v11; // rbp
  int AttributeInfo; // r14d
  const struct StoredHelperAttributeInfo *v13; // rbx
  unsigned int v14; // eax
  unsigned int v17; // [rsp+80h] [rbp+18h]

  v4 = 0xF0F0F0F0F0F0F0F1uLL * ((a3[1] - *a3) >> 3);
  if ( v4 )
  {
    v6 = 0x1E1E1E1E1E1E1E20LL * ((a3[1] - *a3) >> 3);
    v7 = (LPVOID *)CoTaskMemAlloc(v6);
    v8 = v7;
    if ( v7 )
    {
      for ( i = 1; v6; --v6 )
      {
        *(_BYTE *)v7 = 0;
        v7 = (LPVOID *)((char *)v7 + 1);
      }
      v10 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v4);
      v11 = v8;
      AttributeInfo = 0;
      v13 = *a3;
      v14 = 0;
      v17 = 0;
      do
      {
        if ( v13 == a3[1] )
          break;
        if ( AttributeInfo < 0 )
          goto LABEL_13;
        AttributeInfo = CopyAndAllocateAttributeInfo((unsigned __int16 **)&v8[4 * v14], v13);
        v13 = (const struct StoredHelperAttributeInfo *)((char *)v13 + 136);
        v14 = v17 + 1;
        v17 = v14;
      }
      while ( v14 < v4 );
      if ( AttributeInfo >= 0 )
      {
        v11 = 0;
        v10 = 0;
        i = 0;
        *a1 = v8;
        *a2 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v4);
      }
LABEL_13:
      if ( v11 )
        FreeHelperAttributeInfoExs(v11, v10, i);
      return (unsigned int)AttributeInfo;
    }
    else
    {
      return 2147942414LL;
    }
  }
  else
  {
    *a2 = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x18000b90c  mov     [rsp+arg_18], rbx
0x18000b911  mov     [rsp+arg_8], rdx
0x18000b916  mov     [rsp+arg_0], rcx
0x18000b91b  push    rbp
0x18000b91c  push    rsi
0x18000b91d  push    rdi
0x18000b91e  push    r12
0x18000b920  push    r13
0x18000b922  push    r14
0x18000b924  push    r15
0x18000b926  sub     rsp, 30h
0x18000b92a  mov     r13, r8
0x18000b92d  mov     rdi, [r8+8]
0x18000b931  sub     rdi, [r8]
0x18000b934  sar     rdi, 3
0x18000b938  mov     rcx, 0F0F0F0F0F0F0F0F1h
0x18000b942  imul    rdi, rcx
0x18000b946  test    rdi, rdi
0x18000b949  jnz     short loc_18000B954
0x18000b94b  mov     [rdx], edi
0x18000b94d  xor     eax, eax
0x18000b94f  jmp     loc_18000BA41
0x18000b954  mov     rbx, rdi
0x18000b957  shl     rbx, 5
0x18000b95b  mov     rcx, rbx; cb
0x18000b95e  call    cs:__imp_CoTaskMemAlloc
0x18000b965  nop     dword ptr [rax+rax+00h]
0x18000b96a  mov     r15, rax
0x18000b96d  test    rax, rax
0x18000b970  jnz     short loc_18000B97C
0x18000b972  mov     eax, 8007000Eh
0x18000b977  jmp     loc_18000BA41
0x18000b97c  mov     esi, 1
0x18000b981  test    rbx, rbx
0x18000b984  jz      short loc_18000B991
0x18000b986  mov     byte ptr [rax], 0
0x18000b989  add     rax, rsi
0x18000b98c  sub     rbx, rsi
0x18000b98f  jnz     short loc_18000B986
0x18000b991  mov     rcx, rdi
0x18000b994  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18000b999  mov     r12d, eax
0x18000b99c  mov     rbp, r15
0x18000b99f  mov     [rsp+68h+var_48], r15
0x18000b9a4  mov     dword ptr [rsp+68h+var_40], eax
0x18000b9a8  mov     dword ptr [rsp+68h+var_40+4], esi
0x18000b9ac  xor     r14d, r14d
0x18000b9af  mov     rbx, [r13+0]
0x18000b9b3  xor     eax, eax
0x18000b9b5  mov     [rsp+68h+arg_10], eax
0x18000b9bc  test    rdi, rdi
0x18000b9bf  jz      short loc_18000BA03
0x18000b9c1  cmp     rbx, [r13+8]
0x18000b9c5  jz      short loc_18000B9FE
0x18000b9c7  test    r14d, r14d
0x18000b9ca  js      short loc_18000BA2B
0x18000b9cc  mov     ecx, eax
0x18000b9ce  shl     rcx, 5
0x18000b9d2  add     rcx, r15; unsigned __int16 **
0x18000b9d5  mov     rdx, rbx; struct StoredHelperAttributeInfo *
0x18000b9d8  call    ?CopyAndAllocateAttributeInfo@@YAJPEAU__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0002@@PEBUStoredHelperAttributeInfo@@@Z; CopyAndAllocateAttributeInfo(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0002 *,StoredHelperAttributeInfo const *)
0x18000b9dd  mov     r14d, eax
0x18000b9e0  add     rbx, 88h
0x18000b9e7  mov     eax, [rsp+68h+arg_10]
0x18000b9ee  add     eax, esi
0x18000b9f0  mov     [rsp+68h+arg_10], eax
0x18000b9f7  mov     ecx, eax
0x18000b9f9  cmp     rcx, rdi
0x18000b9fc  jb      short loc_18000B9C1
0x18000b9fe  test    r14d, r14d
0x18000ba01  js      short loc_18000BA2B
0x18000ba03  xor     ebp, ebp
0x18000ba05  mov     [rsp+68h+var_48], rbp
0x18000ba0a  xor     r12d, r12d
0x18000ba0d  mov     [rsp+68h+var_40], r12
0x18000ba12  xor     esi, esi
0x18000ba14  mov     rax, [rsp+68h+arg_0]
0x18000ba19  mov     [rax], r15
0x18000ba1c  mov     rcx, rdi
0x18000ba1f  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18000ba24  mov     rcx, [rsp+68h+arg_8]
0x18000ba29  mov     [rcx], eax
0x18000ba2b  test    rbp, rbp
0x18000ba2e  jz      short loc_18000BA3E
0x18000ba30  mov     r8d, esi; int
0x18000ba33  mov     edx, r12d; unsigned int
0x18000ba36  mov     rcx, rbp; pv
0x18000ba39  call    ?FreeHelperAttributeInfoExs@@YAXPEAU__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0002@@KH@Z; FreeHelperAttributeInfoExs(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0002 *,ulong,int)
0x18000ba3e  mov     eax, r14d
0x18000ba41  mov     rbx, [rsp+68h+arg_18]
0x18000ba49  add     rsp, 30h
0x18000ba4d  pop     r15
0x18000ba4f  pop     r14
0x18000ba51  pop     r13
0x18000ba53  pop     r12
0x18000ba55  pop     rdi
0x18000ba56  pop     rsi
0x18000ba57  pop     rbp
0x18000ba58  retn
```
