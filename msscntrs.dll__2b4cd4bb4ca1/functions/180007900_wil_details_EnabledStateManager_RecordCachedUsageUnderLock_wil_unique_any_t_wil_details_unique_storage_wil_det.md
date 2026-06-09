# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180007900`
- end: `0x180007ab7`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: `__int64 (__fastcall *__fastcall(__int64))(_QWORD, __int64, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000746c`
- `0x18000af40`
- `0x18000b020`

## callees

- `0x1800024a0`
- `0x180007900`
- `0x18000a124`
- `0x180018010`

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
0x180007900  push    rbx
0x180007902  push    rbp
0x180007903  push    rsi
0x180007904  push    rdi
0x180007905  push    r14
0x180007907  push    r15
0x180007909  sub     rsp, 78h
0x18000790d  mov     rax, cs:__security_cookie
0x180007914  xor     rax, rsp
0x180007917  mov     [rsp+0A8h+var_48], rax
0x18000791c  mov     rsi, rcx
0x18000791f  mov     rbx, [rcx+20h]
0x180007923  mov     rdi, [rcx+28h]
0x180007927  mov     rax, rdi
0x18000792a  sub     rax, rbx
0x18000792d  cmp     rax, 10h
0x180007931  jb      loc_180007A9D
0x180007937  mov     ebp, 1
0x18000793c  lea     r14d, [rbp+1]
0x180007940  mov     r15d, 1FFh
0x180007946  cmp     rbx, rdi
0x180007949  jz      loc_180007A6A
0x18000794f  mov     r8, [rbx+8]
0x180007953  mov     r10d, [rbx]
0x180007956  prefetchw byte ptr [r8]
0x18000795a  mov     eax, [r8]
0x18000795d  mov     ecx, eax
0x18000795f  and     ecx, 0FFC0401Eh
0x180007965  lock cmpxchg [r8], ecx
0x18000796a  jnz     short loc_18000795D
0x18000796c  mov     ecx, eax
0x18000796e  mov     r9d, eax
0x180007971  shr     r9d, 1
0x180007974  and     r9d, 0Fh
0x180007978  jz      short loc_180007997
0x18000797a  prefetchw byte ptr [r8+4]
0x18000797f  mov     eax, [r8+4]
0x180007983  mov     edx, eax
0x180007985  or      edx, r9d
0x180007988  lock cmpxchg [r8+4], edx
0x18000798e  jnz     short loc_180007983
0x180007990  not     eax
0x180007992  and     eax, r9d
0x180007995  jmp     short loc_18000799A
0x180007997  mov     eax, r9d
0x18000799a  test    bpl, al
0x18000799d  jz      short loc_1800079B3
0x18000799f  mov     [rsp+0A8h+var_78], r10d
0x1800079a4  mov     [rsp+0A8h+var_74], 10002h
0x1800079ac  lea     rdx, [rsp+0A8h+var_70]
0x1800079b1  jmp     short loc_1800079B8
0x1800079b3  lea     rdx, [rsp+0A8h+var_78]
0x1800079b8  test    r14b, al
0x1800079bb  jz      short loc_1800079CB
0x1800079bd  mov     [rdx], r10d
0x1800079c0  mov     dword ptr [rdx+4], 10006h
0x1800079c7  add     rdx, 8
0x1800079cb  test    al, 4
0x1800079cd  jz      short loc_1800079DD
0x1800079cf  mov     [rdx], r10d
0x1800079d2  mov     dword ptr [rdx+4], 10003h
0x1800079d9  add     rdx, 8
0x1800079dd  cmp     eax, 8
0x1800079e0  jb      short loc_1800079F0
0x1800079e2  mov     [rdx], r10d
0x1800079e5  mov     dword ptr [rdx+4], 10007h
0x1800079ec  add     rdx, 8
0x1800079f0  mov     r8d, ecx
0x1800079f3  shr     r8d, 5
0x1800079f7  test    r15d, r8d
0x1800079fa  jz      short loc_180007A1C
0x1800079fc  mov     [rdx], r10d
0x1800079ff  mov     eax, ecx
0x180007a01  shr     eax, 0Eh
0x180007a04  and     ax, bp
0x180007a07  shl     ax, 2
0x180007a0b  mov     [rdx+4], ax
0x180007a0f  and     r8w, r15w; unsigned __int64
0x180007a13  mov     [rdx+6], r8w
0x180007a18  add     rdx, 8
0x180007a1c  mov     eax, ecx
0x180007a1e  shr     eax, 0Fh
0x180007a21  test    al, 7Fh
0x180007a23  jz      short loc_180007A45
0x180007a25  mov     [rdx], r10d
0x180007a28  shr     ecx, 16h
0x180007a2b  and     cx, bp
0x180007a2e  shl     cx, 2
0x180007a32  add     cx, bp
0x180007a35  mov     [rdx+4], cx
0x180007a39  and     ax, 7Fh
0x180007a3d  mov     [rdx+6], ax
0x180007a41  add     rdx, 8
0x180007a45  lea     rax, [rsp+0A8h+var_78]
0x180007a4a  sub     rdx, rax
0x180007a4d  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180007a51  test    rdx, rdx
0x180007a54  jle     short loc_180007A61
0x180007a56  lea     rcx, [rsp+0A8h+var_78]; this
0x180007a5b  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180007a60  nop
0x180007a61  add     rbx, 10h
0x180007a65  jmp     loc_180007946
0x180007a6a  mov     rax, [rsi+20h]
0x180007a6e  mov     [rsi+28h], rax
0x180007a72  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180007a79  test    rax, rax
0x180007a7c  jnz     short loc_180007A8A
0x180007a7e  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180007a85  test    rax, rax
0x180007a88  jz      short loc_180007A9D
0x180007a8a  xor     r9d, r9d
0x180007a8d  xor     r8d, r8d
0x180007a90  mov     edx, 0FEh
0x180007a95  xor     ecx, ecx
0x180007a97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a9c  nop
0x180007a9d  mov     rcx, [rsp+0A8h+var_48]
0x180007aa2  xor     rcx, rsp; StackCookie
0x180007aa5  call    __security_check_cookie
0x180007aaa  add     rsp, 78h
0x180007aae  pop     r15
0x180007ab0  pop     r14
0x180007ab2  pop     rdi
0x180007ab3  pop     rsi
0x180007ab4  pop     rbp
0x180007ab5  pop     rbx
0x180007ab6  retn
```
