# TDataGetter<tagHELPER_ATTRIBUTE,StoredMatchValue const,std::vector<StoredMatchValue,std::allocator<StoredMatchValue>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<StoredMatchValue>>>,TNDFDeallocator<tagHELPER_ATTRIBUTE *,&FreeHelperAttributes(tagHELPER_ATTRIBUTE *,ulong,int)>,&CopyAndAllocateMatchValue(tagHELPER_ATTRIBUTE *,StoredMatchValue const *)>(tagHELPER_ATTRIBUTE * *,ulong *,std::vector<StoredMatchValue,std::allocator<StoredMatchValue>> &)

- ea: `0x18000bca0`
- end: `0x18000bdee`
- name: `??$TDataGetter@UtagHELPER_ATTRIBUTE@@$$CBUStoredMatchValue@@V?$vector@UStoredMatchValue@@V?$allocator@UStoredMatchValue@@@std@@@std@@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UStoredMatchValue@@@std@@@std@@@4@V?$TNDFDeallocator@PEAUtagHELPER_ATTRIBUTE@@$1?FreeHelperAttributes@@YAXPEAU1@KH@Z@@$1?CopyAndAllocateMatchValue@@YAJPEAU1@PEBU2@@Z@@YAJPEAPEAUtagHELPER_ATTRIBUTE@@PEAKAEAV?$vector@UStoredMatchValue@@V?$allocator@UStoredMatchValue@@@std@@@std@@@Z`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000dc10`

## callees

- `0x18000bca0`
- `0x18000c598`
- `0x18000d134`
- `0x18000d510`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bcf3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000bcf3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TDataGetter<tagHELPER_ATTRIBUTE,StoredMatchValue const,std::vector<StoredMatchValue>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<StoredMatchValue>>>,TNDFDeallocator<tagHELPER_ATTRIBUTE *,&void FreeHelperAttributes(tagHELPER_ATTRIBUTE *,unsigned long,int)>,&long CopyAndAllocateMatchValue(tagHELPER_ATTRIBUTE *,StoredMatchValue const *)>(
        struct tagHELPER_ATTRIBUTE **a1,
        _DWORD *a2,
        const struct StoredMatchValue **a3)
{
  unsigned __int64 v4; // rdi
  SIZE_T v6; // rbx
  struct tagHELPER_ATTRIBUTE *v7; // rax
  struct tagHELPER_ATTRIBUTE *v8; // r15
  int i; // esi
  unsigned int v10; // r12d
  struct tagHELPER_ATTRIBUTE *v11; // rbp
  int MatchValue; // r14d
  const struct StoredMatchValue *v13; // rbx
  __int64 v14; // rax
  int v17; // [rsp+80h] [rbp+18h]

  v4 = 0x4EC4EC4EC4EC4EC5LL * ((a3[1] - *a3) >> 3);
  if ( v4 )
  {
    v6 = 0x4EC4EC4EC4EC4ED0LL * ((a3[1] - *a3) >> 3);
    v7 = (struct tagHELPER_ATTRIBUTE *)CoTaskMemAlloc(v6);
    v8 = v7;
    if ( v7 )
    {
      for ( i = 1; v6; --v6 )
      {
        LOBYTE(v7->pwszName) = 0;
        v7 = (struct tagHELPER_ATTRIBUTE *)((char *)v7 + 1);
      }
      v10 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v4);
      v11 = v8;
      MatchValue = 0;
      v13 = *a3;
      v14 = 0;
      v17 = 0;
      do
      {
        if ( v13 == a3[1] )
          break;
        if ( MatchValue < 0 )
          goto LABEL_13;
        MatchValue = CopyAndAllocateMatchValue(&v8[v14], v13);
        v13 = (const struct StoredMatchValue *)((char *)v13 + 104);
        v14 = (unsigned int)(v17 + 1);
        v17 = v14;
      }
      while ( (unsigned int)v14 < v4 );
      if ( MatchValue >= 0 )
      {
        v11 = 0;
        v10 = 0;
        i = 0;
        *a1 = v8;
        *a2 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v4);
      }
LABEL_13:
      if ( v11 )
        FreeHelperAttributes(v11, v10, i);
      return (unsigned int)MatchValue;
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
0x18000bca0  mov     [rsp+arg_18], rbx
0x18000bca5  mov     [rsp+arg_8], rdx
0x18000bcaa  mov     [rsp+arg_0], rcx
0x18000bcaf  push    rbp
0x18000bcb0  push    rsi
0x18000bcb1  push    rdi
0x18000bcb2  push    r12
0x18000bcb4  push    r13
0x18000bcb6  push    r14
0x18000bcb8  push    r15
0x18000bcba  sub     rsp, 30h
0x18000bcbe  mov     r13, r8
0x18000bcc1  mov     rdi, [r8+8]
0x18000bcc5  sub     rdi, [r8]
0x18000bcc8  sar     rdi, 3
0x18000bccc  mov     rcx, 4EC4EC4EC4EC4EC5h
0x18000bcd6  imul    rdi, rcx
0x18000bcda  test    rdi, rdi
0x18000bcdd  jnz     short loc_18000BCE8
0x18000bcdf  mov     [rdx], edi
0x18000bce1  xor     eax, eax
0x18000bce3  jmp     loc_18000BDD5
0x18000bce8  lea     rbx, [rdi+rdi*8]
0x18000bcec  shl     rbx, 4
0x18000bcf0  mov     rcx, rbx; cb
0x18000bcf3  call    cs:__imp_CoTaskMemAlloc
0x18000bcfa  nop     dword ptr [rax+rax+00h]
0x18000bcff  mov     r15, rax
0x18000bd02  test    rax, rax
0x18000bd05  jnz     short loc_18000BD11
0x18000bd07  mov     eax, 8007000Eh
0x18000bd0c  jmp     loc_18000BDD5
0x18000bd11  mov     esi, 1
0x18000bd16  test    rbx, rbx
0x18000bd19  jz      short loc_18000BD26
0x18000bd1b  mov     byte ptr [rax], 0
0x18000bd1e  add     rax, rsi
0x18000bd21  sub     rbx, rsi
0x18000bd24  jnz     short loc_18000BD1B
0x18000bd26  mov     rcx, rdi
0x18000bd29  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18000bd2e  mov     r12d, eax
0x18000bd31  mov     rbp, r15
0x18000bd34  mov     [rsp+68h+var_48], r15
0x18000bd39  mov     dword ptr [rsp+68h+var_40], eax
0x18000bd3d  mov     dword ptr [rsp+68h+var_40+4], esi
0x18000bd41  xor     r14d, r14d
0x18000bd44  mov     rbx, [r13+0]
0x18000bd48  xor     eax, eax
0x18000bd4a  mov     [rsp+68h+arg_10], eax
0x18000bd51  test    rdi, rdi
0x18000bd54  jz      short loc_18000BD97
0x18000bd56  cmp     rbx, [r13+8]
0x18000bd5a  jz      short loc_18000BD92
0x18000bd5c  test    r14d, r14d
0x18000bd5f  js      short loc_18000BDBF
0x18000bd61  lea     rcx, [rax+rax*8]
0x18000bd65  shl     rcx, 4
0x18000bd69  add     rcx, r15; struct tagHELPER_ATTRIBUTE *
0x18000bd6c  mov     rdx, rbx; struct StoredMatchValue *
0x18000bd6f  call    ?CopyAndAllocateMatchValue@@YAJPEAUtagHELPER_ATTRIBUTE@@PEBUStoredMatchValue@@@Z; CopyAndAllocateMatchValue(tagHELPER_ATTRIBUTE *,StoredMatchValue const *)
0x18000bd74  mov     r14d, eax
0x18000bd77  add     rbx, 68h ; 'h'
0x18000bd7b  mov     eax, [rsp+68h+arg_10]
0x18000bd82  add     eax, esi
0x18000bd84  mov     [rsp+68h+arg_10], eax
0x18000bd8b  mov     ecx, eax
0x18000bd8d  cmp     rcx, rdi
0x18000bd90  jb      short loc_18000BD56
0x18000bd92  test    r14d, r14d
0x18000bd95  js      short loc_18000BDBF
0x18000bd97  xor     ebp, ebp
0x18000bd99  mov     [rsp+68h+var_48], rbp
0x18000bd9e  xor     r12d, r12d
0x18000bda1  mov     [rsp+68h+var_40], r12
0x18000bda6  xor     esi, esi
0x18000bda8  mov     rax, [rsp+68h+arg_0]
0x18000bdad  mov     [rax], r15
0x18000bdb0  mov     rcx, rdi
0x18000bdb3  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18000bdb8  mov     rcx, [rsp+68h+arg_8]
0x18000bdbd  mov     [rcx], eax
0x18000bdbf  test    rbp, rbp
0x18000bdc2  jz      short loc_18000BDD2
0x18000bdc4  mov     r8d, esi; int
0x18000bdc7  mov     edx, r12d; unsigned int
0x18000bdca  mov     rcx, rbp; pv
0x18000bdcd  call    ?FreeHelperAttributes@@YAXPEAUtagHELPER_ATTRIBUTE@@KH@Z; FreeHelperAttributes(tagHELPER_ATTRIBUTE *,ulong,int)
0x18000bdd2  mov     eax, r14d
0x18000bdd5  mov     rbx, [rsp+68h+arg_18]
0x18000bddd  add     rsp, 30h
0x18000bde1  pop     r15
0x18000bde3  pop     r14
0x18000bde5  pop     r13
0x18000bde7  pop     r12
0x18000bde9  pop     rdi
0x18000bdea  pop     rsi
0x18000bdeb  pop     rbp
0x18000bdec  retn
```
