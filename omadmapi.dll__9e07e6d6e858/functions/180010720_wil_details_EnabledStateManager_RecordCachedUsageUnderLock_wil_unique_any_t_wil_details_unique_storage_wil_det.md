# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180010720`
- end: `0x1800108d8`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `440`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180008a90`
- `0x180008bd0`
- `0x180010168`

## callees

- `0x1800031b0`
- `0x180010720`
- `0x180013aa8`
- `0x180024010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 (__fastcall *__fastcall wil::details::EnabledStateManager::RecordCachedUsageUnderLock(
        __int64 a1))(_QWORD, __int64, _QWORD, _QWORD)
{
  int *v2; // rbx
  int *v3; // rdi
  __int64 (__fastcall *result)(_QWORD, __int64, _QWORD, _QWORD); // rax
  __int64 v5; // r8
  int v6; // r10d
  unsigned __int32 v7; // ecx
  unsigned __int32 v8; // eax
  char *v9; // rdx
  unsigned __int64 v10; // r8
  __int64 v11; // rdx
  _DWORD v12[2]; // [rsp+30h] [rbp-78h] BYREF
  char v13; // [rsp+38h] [rbp-70h] BYREF

  v2 = *(int **)(a1 + 48);
  v3 = *(int **)(a1 + 56);
  result = (__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))((char *)v3 - (char *)v2);
  if ( (unsigned __int64)((char *)v3 - (char *)v2) >= 0x10 )
  {
    while ( v2 != v3 )
    {
      v5 = *((_QWORD *)v2 + 1);
      v6 = *v2;
      _m_prefetchw((const void *)v5);
      v7 = _InterlockedAnd((volatile signed __int32 *)v5, 0xFFC0401E);
      if ( ((v7 >> 1) & 0xF) != 0 )
      {
        _m_prefetchw((const void *)(v5 + 4));
        v8 = (v7 >> 1) & 0xF & ~_InterlockedOr((volatile signed __int32 *)(v5 + 4), (v7 >> 1) & 0xF);
      }
      else
      {
        v8 = 0;
      }
      if ( (v8 & 1) != 0 )
      {
        v12[0] = v6;
        v12[1] = 65538;
        v9 = &v13;
      }
      else
      {
        v9 = (char *)v12;
      }
      if ( (v8 & 2) != 0 )
      {
        *(_DWORD *)v9 = v6;
        *((_DWORD *)v9 + 1) = 65542;
        v9 += 8;
      }
      if ( (v8 & 4) != 0 )
      {
        *(_DWORD *)v9 = v6;
        *((_DWORD *)v9 + 1) = 65539;
        v9 += 8;
      }
      if ( v8 >= 8 )
      {
        *(_DWORD *)v9 = v6;
        *((_DWORD *)v9 + 1) = 65543;
        v9 += 8;
      }
      v10 = v7 >> 5;
      if ( (v10 & 0x1FF) != 0 )
      {
        *(_DWORD *)v9 = v6;
        *((_WORD *)v9 + 2) = 4 * ((v7 >> 14) & 1);
        LOWORD(v10) = v10 & 0x1FF;
        *((_WORD *)v9 + 3) = v10;
        v9 += 8;
      }
      if ( ((v7 >> 15) & 0x7F) != 0 )
      {
        *(_DWORD *)v9 = v6;
        *((_WORD *)v9 + 2) = 4 * ((v7 >> 22) & 1) + 1;
        *((_WORD *)v9 + 3) = (v7 >> 15) & 0x7F;
        v9 += 8;
      }
      v11 = (v9 - (char *)v12) >> 3;
      if ( v11 > 0 )
        wil::details::WilApi_RecordFeatureUsageReports(
          (wil::details *)v12,
          (struct __WIL_RTL_FEATURE_USAGE_DATA *)v11,
          v10);
      v2 += 4;
    }
    *(_QWORD *)(a1 + 56) = *(_QWORD *)(a1 + 48);
    result = (__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage )
      return (__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))result(0, 254, 0, 0);
    result = (__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage;
    if ( g_wil_details_apiRecordFeatureUsage )
      return (__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))result(0, 254, 0, 0);
  }
  return result;
}

```

## disassembly

```asm
0x180010720  push    rbx
0x180010722  push    rbp
0x180010723  push    rsi
0x180010724  push    rdi
0x180010725  push    r14
0x180010727  push    r15
0x180010729  sub     rsp, 78h
0x18001072d  mov     rax, cs:__security_cookie
0x180010734  xor     rax, rsp
0x180010737  mov     [rsp+0A8h+var_48], rax
0x18001073c  mov     rsi, rcx
0x18001073f  mov     rbx, [rcx+30h]
0x180010743  mov     rdi, [rcx+38h]
0x180010747  mov     rax, rdi
0x18001074a  sub     rax, rbx
0x18001074d  cmp     rax, 10h
0x180010751  jb      loc_1800108BD
0x180010757  mov     ebp, 1
0x18001075c  lea     r14d, [rbp+1]
0x180010760  mov     r15d, 1FFh
0x180010766  cmp     rbx, rdi
0x180010769  jz      loc_18001088A
0x18001076f  mov     r8, [rbx+8]
0x180010773  mov     r10d, [rbx]
0x180010776  prefetchw byte ptr [r8]
0x18001077a  mov     eax, [r8]
0x18001077d  mov     ecx, eax
0x18001077f  and     ecx, 0FFC0401Eh
0x180010785  lock cmpxchg [r8], ecx
0x18001078a  jnz     short loc_18001077D
0x18001078c  mov     ecx, eax
0x18001078e  mov     r9d, eax
0x180010791  shr     r9d, 1
0x180010794  and     r9d, 0Fh
0x180010798  jz      short loc_1800107B7
0x18001079a  prefetchw byte ptr [r8+4]
0x18001079f  mov     eax, [r8+4]
0x1800107a3  mov     edx, eax
0x1800107a5  or      edx, r9d
0x1800107a8  lock cmpxchg [r8+4], edx
0x1800107ae  jnz     short loc_1800107A3
0x1800107b0  not     eax
0x1800107b2  and     eax, r9d
0x1800107b5  jmp     short loc_1800107BA
0x1800107b7  mov     eax, r9d
0x1800107ba  test    bpl, al
0x1800107bd  jz      short loc_1800107D3
0x1800107bf  mov     [rsp+0A8h+var_78], r10d
0x1800107c4  mov     [rsp+0A8h+var_74], 10002h
0x1800107cc  lea     rdx, [rsp+0A8h+var_70]
0x1800107d1  jmp     short loc_1800107D8
0x1800107d3  lea     rdx, [rsp+0A8h+var_78]
0x1800107d8  test    r14b, al
0x1800107db  jz      short loc_1800107EB
0x1800107dd  mov     [rdx], r10d
0x1800107e0  mov     dword ptr [rdx+4], 10006h
0x1800107e7  add     rdx, 8
0x1800107eb  test    al, 4
0x1800107ed  jz      short loc_1800107FD
0x1800107ef  mov     [rdx], r10d
0x1800107f2  mov     dword ptr [rdx+4], 10003h
0x1800107f9  add     rdx, 8
0x1800107fd  cmp     eax, 8
0x180010800  jb      short loc_180010810
0x180010802  mov     [rdx], r10d
0x180010805  mov     dword ptr [rdx+4], 10007h
0x18001080c  add     rdx, 8
0x180010810  mov     r8d, ecx
0x180010813  shr     r8d, 5
0x180010817  test    r15d, r8d
0x18001081a  jz      short loc_18001083C
0x18001081c  mov     [rdx], r10d
0x18001081f  mov     eax, ecx
0x180010821  shr     eax, 0Eh
0x180010824  and     ax, bp
0x180010827  shl     ax, 2
0x18001082b  mov     [rdx+4], ax
0x18001082f  and     r8w, r15w; unsigned __int64
0x180010833  mov     [rdx+6], r8w
0x180010838  add     rdx, 8
0x18001083c  mov     eax, ecx
0x18001083e  shr     eax, 0Fh
0x180010841  test    al, 7Fh
0x180010843  jz      short loc_180010865
0x180010845  mov     [rdx], r10d
0x180010848  shr     ecx, 16h
0x18001084b  and     cx, bp
0x18001084e  shl     cx, 2
0x180010852  add     cx, bp
0x180010855  mov     [rdx+4], cx
0x180010859  and     ax, 7Fh
0x18001085d  mov     [rdx+6], ax
0x180010861  add     rdx, 8
0x180010865  lea     rax, [rsp+0A8h+var_78]
0x18001086a  sub     rdx, rax
0x18001086d  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180010871  test    rdx, rdx
0x180010874  jle     short loc_180010881
0x180010876  lea     rcx, [rsp+0A8h+var_78]; this
0x18001087b  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180010880  nop
0x180010881  add     rbx, 10h
0x180010885  jmp     loc_180010766
0x18001088a  mov     rax, [rsi+30h]
0x18001088e  mov     [rsi+38h], rax
0x180010892  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180010899  test    rax, rax
0x18001089c  jnz     short loc_1800108AA
0x18001089e  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1800108a5  test    rax, rax
0x1800108a8  jz      short loc_1800108BD
0x1800108aa  xor     r9d, r9d
0x1800108ad  xor     r8d, r8d
0x1800108b0  mov     edx, 0FEh
0x1800108b5  xor     ecx, ecx
0x1800108b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108bc  nop
0x1800108bd  mov     rcx, [rsp+0A8h+var_48]
0x1800108c2  xor     rcx, rsp; StackCookie
0x1800108c5  call    __security_check_cookie
0x1800108ca  add     rsp, 78h
0x1800108ce  pop     r15
0x1800108d0  pop     r14
0x1800108d2  pop     rdi
0x1800108d3  pop     rsi
0x1800108d4  pop     rbp
0x1800108d5  pop     rbx
0x1800108d6  retn
```
