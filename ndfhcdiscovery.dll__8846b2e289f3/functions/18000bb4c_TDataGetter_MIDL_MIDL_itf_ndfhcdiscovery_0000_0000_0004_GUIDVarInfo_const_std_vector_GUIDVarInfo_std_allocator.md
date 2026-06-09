# TDataGetter<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004,GUIDVarInfo const,std::vector<GUIDVarInfo,std::allocator<GUIDVarInfo>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<GUIDVarInfo>>>,TNDFDeallocator<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 *,&FreeHelperBasicRootCauseInfos(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 *,ulong,int)>,&TCopyAndAllocateGUIDVarInfo<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004>(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 *,GUIDVarInfo const *)>(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 * *,ulong *,std::vector<GUIDVarInfo,std::allocator<GUIDVarInfo>> &)

- ea: `0x18000bb4c`
- end: `0x18000bc97`
- name: `??$TDataGetter@U__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004@@$$CBUGUIDVarInfo@@V?$vector@UGUIDVarInfo@@V?$allocator@UGUIDVarInfo@@@std@@@std@@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UGUIDVarInfo@@@std@@@std@@@4@V?$TNDFDeallocator@PEAU__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004@@$1?FreeHelperBasicRootCauseInfos@@YAXPEAU1@KH@Z@@$1??$TCopyAndAllocateGUIDVarInfo@U__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004@@@@YAJPEAU1@PEBU2@@Z@@YAJPEAPEAU__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004@@PEAKAEAV?$vector@UGUIDVarInfo@@V?$allocator@UGUIDVarInfo@@@std@@@std@@@Z`
- size: `331`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000deb0`
- `0x18000df80`
- `0x18000e130`

## callees

- `0x18000b6fc`
- `0x18000bb4c`
- `0x18000c598`
- `0x18000d5d8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bb9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bb9e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TDataGetter<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004,GUIDVarInfo const,std::vector<GUIDVarInfo>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<GUIDVarInfo>>>,TNDFDeallocator<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 *,&void FreeHelperBasicRootCauseInfos(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 *,unsigned long,int)>,&long TCopyAndAllocateGUIDVarInfo<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004>(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 *,GUIDVarInfo const *)>(
        LPVOID **a1,
        _DWORD *a2,
        __int64 *a3)
{
  unsigned __int64 v4; // rdi
  SIZE_T v6; // rbx
  LPVOID *v7; // rax
  LPVOID *v8; // r15
  int i; // esi
  unsigned int v10; // r12d
  LPVOID *v11; // rbp
  int GUIDVar; // r14d
  __int64 v13; // rbx
  unsigned int v14; // eax
  unsigned int v17; // [rsp+80h] [rbp+18h]

  v4 = 0xCCCCCCCCCCCCCCCDuLL * ((a3[1] - *a3) >> 4);
  if ( v4 )
  {
    v6 = 0x99999999999999A0uLL * ((a3[1] - *a3) >> 4);
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
      GUIDVar = 0;
      v13 = *a3;
      v14 = 0;
      v17 = 0;
      do
      {
        if ( v13 == a3[1] )
          break;
        if ( GUIDVar < 0 )
          goto LABEL_13;
        GUIDVar = TCopyAndAllocateGUIDVarInfo<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004>(&v8[4 * v14], v13);
        v13 += 80;
        v14 = v17 + 1;
        v17 = v14;
      }
      while ( v14 < v4 );
      if ( GUIDVar >= 0 )
      {
        v11 = 0;
        v10 = 0;
        i = 0;
        *a1 = v8;
        *a2 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v4);
      }
LABEL_13:
      if ( v11 )
        FreeHelperBasicRootCauseInfos(v11, v10, i);
      return (unsigned int)GUIDVar;
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
0x18000bb4c  mov     [rsp+arg_18], rbx
0x18000bb51  mov     [rsp+arg_8], rdx
0x18000bb56  mov     [rsp+arg_0], rcx
0x18000bb5b  push    rbp
0x18000bb5c  push    rsi
0x18000bb5d  push    rdi
0x18000bb5e  push    r12
0x18000bb60  push    r13
0x18000bb62  push    r14
0x18000bb64  push    r15
0x18000bb66  sub     rsp, 30h
0x18000bb6a  mov     r13, r8
0x18000bb6d  mov     rdi, [r8+8]
0x18000bb71  sub     rdi, [r8]
0x18000bb74  sar     rdi, 4
0x18000bb78  mov     rcx, 0CCCCCCCCCCCCCCCDh
0x18000bb82  imul    rdi, rcx
0x18000bb86  test    rdi, rdi
0x18000bb89  jnz     short loc_18000BB94
0x18000bb8b  mov     [rdx], edi
0x18000bb8d  xor     eax, eax
0x18000bb8f  jmp     loc_18000BC7E
0x18000bb94  mov     rbx, rdi
0x18000bb97  shl     rbx, 5
0x18000bb9b  mov     rcx, rbx; cb
0x18000bb9e  call    cs:__imp_CoTaskMemAlloc
0x18000bba5  nop     dword ptr [rax+rax+00h]
0x18000bbaa  mov     r15, rax
0x18000bbad  test    rax, rax
0x18000bbb0  jnz     short loc_18000BBBC
0x18000bbb2  mov     eax, 8007000Eh
0x18000bbb7  jmp     loc_18000BC7E
0x18000bbbc  mov     esi, 1
0x18000bbc1  test    rbx, rbx
0x18000bbc4  jz      short loc_18000BBD1
0x18000bbc6  mov     byte ptr [rax], 0
0x18000bbc9  add     rax, rsi
0x18000bbcc  sub     rbx, rsi
0x18000bbcf  jnz     short loc_18000BBC6
0x18000bbd1  mov     rcx, rdi
0x18000bbd4  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18000bbd9  mov     r12d, eax
0x18000bbdc  mov     rbp, r15
0x18000bbdf  mov     [rsp+68h+var_48], r15
0x18000bbe4  mov     dword ptr [rsp+68h+var_40], eax
0x18000bbe8  mov     dword ptr [rsp+68h+var_40+4], esi
0x18000bbec  xor     r14d, r14d
0x18000bbef  mov     rbx, [r13+0]
0x18000bbf3  xor     eax, eax
0x18000bbf5  mov     [rsp+68h+arg_10], eax
0x18000bbfc  test    rdi, rdi
0x18000bbff  jz      short loc_18000BC40
0x18000bc01  cmp     rbx, [r13+8]
0x18000bc05  jz      short loc_18000BC3B
0x18000bc07  test    r14d, r14d
0x18000bc0a  js      short loc_18000BC68
0x18000bc0c  mov     ecx, eax
0x18000bc0e  shl     rcx, 5
0x18000bc12  add     rcx, r15
0x18000bc15  mov     rdx, rbx
0x18000bc18  call    ??$TCopyAndAllocateGUIDVarInfo@U__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004@@@@YAJPEAU__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004@@PEBUGUIDVarInfo@@@Z; TCopyAndAllocateGUIDVarInfo<__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004>(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 *,GUIDVarInfo const *)
0x18000bc1d  mov     r14d, eax
0x18000bc20  add     rbx, 50h ; 'P'
0x18000bc24  mov     eax, [rsp+68h+arg_10]
0x18000bc2b  add     eax, esi
0x18000bc2d  mov     [rsp+68h+arg_10], eax
0x18000bc34  mov     ecx, eax
0x18000bc36  cmp     rcx, rdi
0x18000bc39  jb      short loc_18000BC01
0x18000bc3b  test    r14d, r14d
0x18000bc3e  js      short loc_18000BC68
0x18000bc40  xor     ebp, ebp
0x18000bc42  mov     [rsp+68h+var_48], rbp
0x18000bc47  xor     r12d, r12d
0x18000bc4a  mov     [rsp+68h+var_40], r12
0x18000bc4f  xor     esi, esi
0x18000bc51  mov     rax, [rsp+68h+arg_0]
0x18000bc56  mov     [rax], r15
0x18000bc59  mov     rcx, rdi
0x18000bc5c  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18000bc61  mov     rcx, [rsp+68h+arg_8]
0x18000bc66  mov     [rcx], eax
0x18000bc68  test    rbp, rbp
0x18000bc6b  jz      short loc_18000BC7B
0x18000bc6d  mov     r8d, esi; int
0x18000bc70  mov     edx, r12d; unsigned int
0x18000bc73  mov     rcx, rbp; pv
0x18000bc76  call    ?FreeHelperBasicRootCauseInfos@@YAXPEAU__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004@@KH@Z; FreeHelperBasicRootCauseInfos(__MIDL___MIDL_itf_ndfhcdiscovery_0000_0000_0004 *,ulong,int)
0x18000bc7b  mov     eax, r14d
0x18000bc7e  mov     rbx, [rsp+68h+arg_18]
0x18000bc86  add     rsp, 30h
0x18000bc8a  pop     r15
0x18000bc8c  pop     r14
0x18000bc8e  pop     r13
0x18000bc90  pop     r12
0x18000bc92  pop     rdi
0x18000bc93  pop     rsi
0x18000bc94  pop     rbp
0x18000bc95  retn
```
