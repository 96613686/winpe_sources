# std::vector<__MIDL___MIDL_itf_tieringengine_0000_0000_0005,com_allocator<__MIDL___MIDL_itf_tieringengine_0000_0000_0005>>::reserve(unsigned __int64)

- ea: `0x18005efd0`
- end: `0x18005f0dd`
- name: `?reserve@?$vector@U__MIDL___MIDL_itf_tieringengine_0000_0000_0005@@V?$com_allocator@U__MIDL___MIDL_itf_tieringengine_0000_0000_0005@@@@@std@@QEAAX_K@Z`
- size: `269`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005ee80`

## callees

- `0x180043b18`
- `0x18004462d`
- `0x180044645`
- `0x18005b260`
- `0x18005efd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005f033`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18005f033`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f0aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005f0aa`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int64 __fastcall std::vector<__MIDL___MIDL_itf_tieringengine_0000_0000_0005,com_allocator<__MIDL___MIDL_itf_tieringengine_0000_0000_0005>>::reserve(
        __int64 *a1,
        unsigned __int64 a2)
{
  unsigned __int64 result; // rax
  __int64 v4; // r14
  char *v5; // rax
  char *v6; // rdi
  unsigned __int64 v7; // rsi
  _QWORD pExceptionObject[4]; // [rsp+30h] [rbp-38h] BYREF
  char *v9; // [rsp+78h] [rbp+10h] BYREF

  if ( a2 > 0x666666666666666LL )
    std::_Xlength_error("vector<T> too long");
  result = 0xCCCCCCCCCCCCCCCDuLL * ((a1[2] - *a1) >> 3);
  if ( result < a2 )
  {
    v4 = 40 * a2;
    v5 = (char *)CoTaskMemAlloc(40 * a2);
    v6 = v5;
    v9 = v5;
    if ( !v5 )
    {
      v9 = "bad allocation";
      exception::exception((exception *)pExceptionObject, (const char *const *)&v9, 1);
      pExceptionObject[0] = &std::bad_alloc::`vftable';
      throw (std::bad_alloc *)pExceptionObject;
    }
    try
    {
      std::_Uninit_move<__MIDL___MIDL_itf_tieringengine_0000_0000_0005 *,__MIDL___MIDL_itf_tieringengine_0000_0000_0005 *,com_allocator<__MIDL___MIDL_itf_tieringengine_0000_0000_0005>,__MIDL___MIDL_itf_tieringengine_0000_0000_0005>(
        *a1,
        a1[1],
        (__int64)v5);
      v7 = 0xCCCCCCCCCCCCCCCDuLL * ((a1[1] - *a1) >> 3);
      if ( *a1 )
        CoTaskMemFree((LPVOID)*a1);
      a1[2] = (__int64)&v6[v4];
      result = 5 * v7;
      a1[1] = (__int64)&v6[40 * v7];
      *a1 = (__int64)v6;
    }
    catch ( ... )
    {
      CoTaskMemFree(v9);
      throw;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18005efd0  mov     [rsp+arg_0], rbx
0x18005efd5  mov     [rsp+arg_10], rsi
0x18005efda  push    rdi
0x18005efdb  push    r14
0x18005efdd  push    r15
0x18005efdf  sub     rsp, 50h
0x18005efe3  mov     rbx, rcx
0x18005efe6  mov     rax, 666666666666666h
0x18005eff0  cmp     rdx, rax
0x18005eff3  jbe     short loc_18005F002
0x18005eff5  lea     rcx, aVectorTTooLong; "vector<T> too long"
0x18005effc  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18005f002  mov     rax, [rcx+10h]
0x18005f006  sub     rax, [rcx]
0x18005f009  sar     rax, 3
0x18005f00d  mov     r15, 0CCCCCCCCCCCCCCCDh
0x18005f017  imul    rax, r15
0x18005f01b  cmp     rax, rdx
0x18005f01e  jnb     loc_18005F0C7
0x18005f024  lea     rax, [rdx+rdx*4]
0x18005f028  lea     r14, ds:0[rax*8]
0x18005f030  mov     rcx, r14; cb
0x18005f033  call    cs:__imp_CoTaskMemAlloc
0x18005f039  mov     rdi, rax
0x18005f03c  mov     [rsp+68h+arg_8], rax
0x18005f041  test    rax, rax
0x18005f044  jnz     short loc_18005F083
0x18005f046  lea     rax, aBadAllocation; "bad allocation"
0x18005f04d  mov     [rsp+68h+arg_8], rax
0x18005f052  lea     r8d, [rdi+1]; int
0x18005f056  lea     rdx, [rsp+68h+arg_8]; char **
0x18005f05b  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18005f060  call    ??0exception@@QEAA@AEBQEBDH@Z_0; exception::exception(char const * const &,int)
0x18005f065  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18005f06c  mov     [rsp+68h+pExceptionObject], rax
0x18005f071  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18005f078  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18005f07d  call    _CxxThrowException_0
0x18005f083  mov     r8, rdi
0x18005f086  mov     rdx, [rbx+8]
0x18005f08a  mov     rcx, [rbx]
0x18005f08d  call    ??$_Uninit_move@PEAU__MIDL___MIDL_itf_tieringengine_0000_0000_0005@@PEAU1@V?$com_allocator@U__MIDL___MIDL_itf_tieringengine_0000_0000_0005@@@@U1@@std@@YAPEAU__MIDL___MIDL_itf_tieringengine_0000_0000_0005@@PEAU1@00AEAV?$com_allocator@U__MIDL___MIDL_itf_tieringengine_0000_0000_0005@@@@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_move<__MIDL___MIDL_itf_tieringengine_0000_0000_0005 *,__MIDL___MIDL_itf_tieringengine_0000_0000_0005 *,com_allocator<__MIDL___MIDL_itf_tieringengine_0000_0000_0005>,__MIDL___MIDL_itf_tieringengine_0000_0000_0005>(__MIDL___MIDL_itf_tieringengine_0000_0000_0005 *,__MIDL___MIDL_itf_tieringengine_0000_0000_0005 *,__MIDL___MIDL_itf_tieringengine_0000_0000_0005 *,com_allocator<__MIDL___MIDL_itf_tieringengine_0000_0000_0005> &,__MIDL___MIDL_itf_tieringengine_0000_0000_0005 *,std::_Nonscalar_ptr_iterator_tag)
0x18005f092  nop
0x18005f093  mov     rcx, [rbx]; pv
0x18005f096  mov     rsi, [rbx+8]
0x18005f09a  sub     rsi, rcx
0x18005f09d  sar     rsi, 3
0x18005f0a1  imul    rsi, r15
0x18005f0a5  test    rcx, rcx
0x18005f0a8  jz      short loc_18005F0B0
0x18005f0aa  call    cs:__imp_CoTaskMemFree
0x18005f0b0  lea     rax, [r14+rdi]
0x18005f0b4  mov     [rbx+10h], rax
0x18005f0b8  lea     rax, [rsi+rsi*4]
0x18005f0bc  lea     rcx, [rdi+rax*8]
0x18005f0c0  mov     [rbx+8], rcx
0x18005f0c4  mov     [rbx], rdi
0x18005f0c7  lea     r11, [rsp+68h+var_18]
0x18005f0cc  mov     rbx, [r11+20h]
0x18005f0d0  mov     rsi, [r11+30h]
0x18005f0d4  mov     rsp, r11
0x18005f0d7  pop     r15
0x18005f0d9  pop     r14
0x18005f0db  pop     rdi
0x18005f0dc  retn
```
