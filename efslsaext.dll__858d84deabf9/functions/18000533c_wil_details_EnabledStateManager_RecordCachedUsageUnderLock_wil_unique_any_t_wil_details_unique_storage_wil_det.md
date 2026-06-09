# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x18000533c`
- end: `0x1800054f1`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `437`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800052a0`

## callees

- `0x18000533c`
- `0x1800061a8`
- `0x180012040`
- `0x180013010`

## pseudocode

```c
__int64 (__fastcall *__fastcall wil::details::EnabledStateManager::RecordCachedUsageUnderLock(
        __int64 a1))(_QWORD, __int64, _QWORD, _QWORD)
{
  int *v1; // rdi
  int *v3; // rbx
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

  v1 = *(int **)(a1 + 40);
  v3 = *(int **)(a1 + 32);
  result = (__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))((char *)v1 - (char *)v3);
  if ( (unsigned __int64)((char *)v1 - (char *)v3) >= 0x10 )
  {
    while ( v3 != v1 )
    {
      v5 = *((_QWORD *)v3 + 1);
      v6 = *v3;
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
        v9 = &v13;
        v12[1] = 65538;
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
        LOWORD(v10) = v10 & 0x1FF;
        *(_DWORD *)v9 = v6;
        *((_WORD *)v9 + 3) = v10;
        *((_WORD *)v9 + 2) = 4 * ((v7 >> 14) & 1);
        v9 += 8;
      }
      if ( ((v7 >> 15) & 0x7F) != 0 )
      {
        *(_DWORD *)v9 = v6;
        *((_WORD *)v9 + 3) = (v7 >> 15) & 0x7F;
        *((_WORD *)v9 + 2) = 4 * ((v7 >> 22) & 1) + 1;
        v9 += 8;
      }
      v11 = (v9 - (char *)v12) >> 3;
      if ( v11 > 0 )
        wil::details::WilApi_RecordFeatureUsageReports(
          (wil::details *)v12,
          (struct __WIL_RTL_FEATURE_USAGE_DATA *)v11,
          v10);
      v3 += 4;
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
0x18000533c  push    rbx
0x18000533e  push    rbp
0x18000533f  push    rsi
0x180005340  push    rdi
0x180005341  push    r14
0x180005343  push    r15
0x180005345  sub     rsp, 78h
0x180005349  mov     rax, cs:__security_cookie
0x180005350  xor     rax, rsp
0x180005353  mov     [rsp+0A8h+var_48], rax
0x180005358  mov     rdi, [rcx+28h]
0x18000535c  mov     rsi, rcx
0x18000535f  mov     rbx, [rcx+20h]
0x180005363  mov     rax, rdi
0x180005366  sub     rax, rbx
0x180005369  cmp     rax, 10h
0x18000536d  jb      loc_1800054D7
0x180005373  mov     ebp, 1
0x180005378  mov     r15d, 1FFh
0x18000537e  lea     r14d, [rbp+1]
0x180005382  cmp     rbx, rdi
0x180005385  jz      loc_1800054A5
0x18000538b  mov     r8, [rbx+8]
0x18000538f  mov     r10d, [rbx]
0x180005392  prefetchw byte ptr [r8]
0x180005396  mov     eax, [r8]
0x180005399  mov     ecx, eax
0x18000539b  and     ecx, 0FFC0401Eh
0x1800053a1  lock cmpxchg [r8], ecx
0x1800053a6  jnz     short loc_180005399
0x1800053a8  mov     r9d, eax
0x1800053ab  mov     ecx, eax
0x1800053ad  shr     r9d, 1
0x1800053b0  and     r9d, 0Fh
0x1800053b4  jz      short loc_1800053D3
0x1800053b6  prefetchw byte ptr [r8+4]
0x1800053bb  mov     eax, [r8+4]
0x1800053bf  mov     edx, eax
0x1800053c1  or      edx, r9d
0x1800053c4  lock cmpxchg [r8+4], edx
0x1800053ca  jnz     short loc_1800053BF
0x1800053cc  not     eax
0x1800053ce  and     eax, r9d
0x1800053d1  jmp     short loc_1800053D6
0x1800053d3  mov     eax, r9d
0x1800053d6  test    bpl, al
0x1800053d9  jz      short loc_1800053EF
0x1800053db  mov     [rsp+0A8h+var_78], r10d
0x1800053e0  lea     rdx, [rsp+0A8h+var_70]
0x1800053e5  mov     [rsp+0A8h+var_74], 10002h
0x1800053ed  jmp     short loc_1800053F4
0x1800053ef  lea     rdx, [rsp+0A8h+var_78]
0x1800053f4  test    r14b, al
0x1800053f7  jz      short loc_180005407
0x1800053f9  mov     [rdx], r10d
0x1800053fc  mov     dword ptr [rdx+4], 10006h
0x180005403  add     rdx, 8
0x180005407  test    al, 4
0x180005409  jz      short loc_180005419
0x18000540b  mov     [rdx], r10d
0x18000540e  mov     dword ptr [rdx+4], 10003h
0x180005415  add     rdx, 8
0x180005419  cmp     eax, 8
0x18000541c  jb      short loc_18000542C
0x18000541e  mov     [rdx], r10d
0x180005421  mov     dword ptr [rdx+4], 10007h
0x180005428  add     rdx, 8
0x18000542c  mov     r8d, ecx
0x18000542f  shr     r8d, 5
0x180005433  test    r15d, r8d
0x180005436  jz      short loc_180005458
0x180005438  and     r8w, r15w; unsigned __int64
0x18000543c  mov     [rdx], r10d
0x18000543f  mov     eax, ecx
0x180005441  mov     [rdx+6], r8w
0x180005446  shr     eax, 0Eh
0x180005449  and     ax, bp
0x18000544c  shl     ax, 2
0x180005450  mov     [rdx+4], ax
0x180005454  add     rdx, 8
0x180005458  mov     eax, ecx
0x18000545a  shr     eax, 0Fh
0x18000545d  test    al, 7Fh
0x18000545f  jz      short loc_180005481
0x180005461  shr     ecx, 16h
0x180005464  and     ax, 7Fh
0x180005468  and     cx, bp
0x18000546b  mov     [rdx], r10d
0x18000546e  shl     cx, 2
0x180005472  add     cx, bp
0x180005475  mov     [rdx+6], ax
0x180005479  mov     [rdx+4], cx
0x18000547d  add     rdx, 8
0x180005481  lea     rax, [rsp+0A8h+var_78]
0x180005486  sub     rdx, rax
0x180005489  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18000548d  test    rdx, rdx
0x180005490  jle     short loc_18000549C
0x180005492  lea     rcx, [rsp+0A8h+var_78]; this
0x180005497  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18000549c  add     rbx, 10h
0x1800054a0  jmp     loc_180005382
0x1800054a5  mov     rax, [rsi+20h]
0x1800054a9  mov     [rsi+28h], rax
0x1800054ad  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1800054b4  test    rax, rax
0x1800054b7  jnz     short loc_1800054C5
0x1800054b9  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1800054c0  test    rax, rax
0x1800054c3  jz      short loc_1800054D7
0x1800054c5  xor     r9d, r9d
0x1800054c8  xor     r8d, r8d
0x1800054cb  mov     edx, 0FEh
0x1800054d0  xor     ecx, ecx
0x1800054d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054d7  mov     rcx, [rsp+0A8h+var_48]
0x1800054dc  xor     rcx, rsp; StackCookie
0x1800054df  call    __security_check_cookie
0x1800054e4  add     rsp, 78h
0x1800054e8  pop     r15
0x1800054ea  pop     r14
0x1800054ec  pop     rdi
0x1800054ed  pop     rsi
0x1800054ee  pop     rbp
0x1800054ef  pop     rbx
0x1800054f0  retn
```
