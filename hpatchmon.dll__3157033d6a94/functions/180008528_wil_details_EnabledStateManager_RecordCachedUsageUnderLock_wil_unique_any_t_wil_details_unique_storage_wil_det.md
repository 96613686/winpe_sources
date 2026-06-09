# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180008528`
- end: `0x1800086df`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: `__int64 (__fastcall *__fastcall(__int64))(_QWORD, __int64, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180003090`
- `0x1800031d0`
- `0x180007f1c`

## callees

- `0x180002270`
- `0x180008528`
- `0x18000c2e4`
- `0x180015010`

## pseudocode

```c
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

  v2 = *(int **)(a1 + 32);
  v3 = *(int **)(a1 + 40);
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
    *(_QWORD *)(a1 + 40) = *(_QWORD *)(a1 + 32);
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
0x180008528  push    rbx
0x18000852a  push    rbp
0x18000852b  push    rsi
0x18000852c  push    rdi
0x18000852d  push    r14
0x18000852f  push    r15
0x180008531  sub     rsp, 78h
0x180008535  mov     rax, cs:__security_cookie
0x18000853c  xor     rax, rsp
0x18000853f  mov     [rsp+0A8h+var_48], rax
0x180008544  mov     rsi, rcx
0x180008547  mov     rbx, [rcx+20h]
0x18000854b  mov     rdi, [rcx+28h]
0x18000854f  mov     rax, rdi
0x180008552  sub     rax, rbx
0x180008555  cmp     rax, 10h
0x180008559  jb      loc_1800086C5
0x18000855f  mov     ebp, 1
0x180008564  lea     r14d, [rbp+1]
0x180008568  mov     r15d, 1FFh
0x18000856e  cmp     rbx, rdi
0x180008571  jz      loc_180008692
0x180008577  mov     r8, [rbx+8]
0x18000857b  mov     r10d, [rbx]
0x18000857e  prefetchw byte ptr [r8]
0x180008582  mov     eax, [r8]
0x180008585  mov     ecx, eax
0x180008587  and     ecx, 0FFC0401Eh
0x18000858d  lock cmpxchg [r8], ecx
0x180008592  jnz     short loc_180008585
0x180008594  mov     ecx, eax
0x180008596  mov     r9d, eax
0x180008599  shr     r9d, 1
0x18000859c  and     r9d, 0Fh
0x1800085a0  jz      short loc_1800085BF
0x1800085a2  prefetchw byte ptr [r8+4]
0x1800085a7  mov     eax, [r8+4]
0x1800085ab  mov     edx, eax
0x1800085ad  or      edx, r9d
0x1800085b0  lock cmpxchg [r8+4], edx
0x1800085b6  jnz     short loc_1800085AB
0x1800085b8  not     eax
0x1800085ba  and     eax, r9d
0x1800085bd  jmp     short loc_1800085C2
0x1800085bf  mov     eax, r9d
0x1800085c2  test    bpl, al
0x1800085c5  jz      short loc_1800085DB
0x1800085c7  mov     [rsp+0A8h+var_78], r10d
0x1800085cc  mov     [rsp+0A8h+var_74], 10002h
0x1800085d4  lea     rdx, [rsp+0A8h+var_70]
0x1800085d9  jmp     short loc_1800085E0
0x1800085db  lea     rdx, [rsp+0A8h+var_78]
0x1800085e0  test    r14b, al
0x1800085e3  jz      short loc_1800085F3
0x1800085e5  mov     [rdx], r10d
0x1800085e8  mov     dword ptr [rdx+4], 10006h
0x1800085ef  add     rdx, 8
0x1800085f3  test    al, 4
0x1800085f5  jz      short loc_180008605
0x1800085f7  mov     [rdx], r10d
0x1800085fa  mov     dword ptr [rdx+4], 10003h
0x180008601  add     rdx, 8
0x180008605  cmp     eax, 8
0x180008608  jb      short loc_180008618
0x18000860a  mov     [rdx], r10d
0x18000860d  mov     dword ptr [rdx+4], 10007h
0x180008614  add     rdx, 8
0x180008618  mov     r8d, ecx
0x18000861b  shr     r8d, 5
0x18000861f  test    r15d, r8d
0x180008622  jz      short loc_180008644
0x180008624  mov     [rdx], r10d
0x180008627  mov     eax, ecx
0x180008629  shr     eax, 0Eh
0x18000862c  and     ax, bp
0x18000862f  shl     ax, 2
0x180008633  mov     [rdx+4], ax
0x180008637  and     r8w, r15w; unsigned __int64
0x18000863b  mov     [rdx+6], r8w
0x180008640  add     rdx, 8
0x180008644  mov     eax, ecx
0x180008646  shr     eax, 0Fh
0x180008649  test    al, 7Fh
0x18000864b  jz      short loc_18000866D
0x18000864d  mov     [rdx], r10d
0x180008650  shr     ecx, 16h
0x180008653  and     cx, bp
0x180008656  shl     cx, 2
0x18000865a  add     cx, bp
0x18000865d  mov     [rdx+4], cx
0x180008661  and     ax, 7Fh
0x180008665  mov     [rdx+6], ax
0x180008669  add     rdx, 8
0x18000866d  lea     rax, [rsp+0A8h+var_78]
0x180008672  sub     rdx, rax
0x180008675  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180008679  test    rdx, rdx
0x18000867c  jle     short loc_180008689
0x18000867e  lea     rcx, [rsp+0A8h+var_78]; this
0x180008683  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180008688  nop
0x180008689  add     rbx, 10h
0x18000868d  jmp     loc_18000856E
0x180008692  mov     rax, [rsi+20h]
0x180008696  mov     [rsi+28h], rax
0x18000869a  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1800086a1  test    rax, rax
0x1800086a4  jnz     short loc_1800086B2
0x1800086a6  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1800086ad  test    rax, rax
0x1800086b0  jz      short loc_1800086C5
0x1800086b2  xor     r9d, r9d
0x1800086b5  xor     r8d, r8d
0x1800086b8  mov     edx, 0FEh
0x1800086bd  xor     ecx, ecx
0x1800086bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086c4  nop
0x1800086c5  mov     rcx, [rsp+0A8h+var_48]
0x1800086ca  xor     rcx, rsp; StackCookie
0x1800086cd  call    __security_check_cookie
0x1800086d2  add     rsp, 78h
0x1800086d6  pop     r15
0x1800086d8  pop     r14
0x1800086da  pop     rdi
0x1800086db  pop     rsi
0x1800086dc  pop     rbp
0x1800086dd  pop     rbx
0x1800086de  retn
```
