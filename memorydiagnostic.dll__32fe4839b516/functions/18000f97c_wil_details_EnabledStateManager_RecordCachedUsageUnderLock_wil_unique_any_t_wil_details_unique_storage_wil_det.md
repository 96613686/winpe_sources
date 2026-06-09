# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x18000f97c`
- end: `0x18000fb4a`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `462`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180003510`
- `0x1800036b0`
- `0x18000f090`

## callees

- `0x1800026b0`
- `0x18000f97c`
- `0x180015b18`
- `0x180024010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 (__fastcall *__fastcall wil::details::EnabledStateManager::RecordCachedUsageUnderLock(
        __int64 a1))(_QWORD, __int64, _QWORD, _QWORD)
{
  int *v2; // rsi
  int *v3; // rbx
  __int64 (__fastcall *result)(_QWORD, __int64, _QWORD, _QWORD); // rax
  __int64 v5; // r9
  int v6; // r10d
  unsigned __int32 v7; // edx
  unsigned int v8; // ecx
  char *v9; // r8
  signed __int64 v10; // r8
  _DWORD v11[2]; // [rsp+30h] [rbp-58h] BYREF
  char v12; // [rsp+38h] [rbp-50h] BYREF

  v2 = *(int **)(a1 + 40);
  v3 = *(int **)(a1 + 32);
  result = (__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))((char *)v2 - (char *)v3);
  if ( (unsigned __int64)((char *)v2 - (char *)v3) >= 0x10 )
  {
    while ( v3 != v2 )
    {
      v5 = *((_QWORD *)v3 + 1);
      v6 = *v3;
      _m_prefetchw((const void *)v5);
      v7 = _InterlockedAnd((volatile signed __int32 *)v5, 0xFFC0401E);
      v8 = (v7 >> 1) & 0xF;
      if ( v8 )
      {
        _m_prefetchw((const void *)(v5 + 4));
        v8 &= ~_InterlockedOr((volatile signed __int32 *)(v5 + 4), v8);
      }
      v9 = (char *)v11;
      if ( (v8 & 1) != 0 )
      {
        v11[0] = v6;
        v11[1] = 65538;
        v9 = &v12;
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
      if ( ((v7 >> 5) & 0x1FF) != 0 )
      {
        *(_DWORD *)v9 = v6;
        *((_WORD *)v9 + 2) = 4 * ((v7 >> 14) & 1);
        *((_WORD *)v9 + 3) = (v7 >> 5) & 0x1FF;
        v9 += 8;
      }
      if ( ((v7 >> 15) & 0x7F) != 0 )
      {
        *(_DWORD *)v9 = v6;
        *((_WORD *)v9 + 2) = 4 * ((v7 >> 22) & 1) + 1;
        *((_WORD *)v9 + 3) = (v7 >> 15) & 0x7F;
        v9 += 8;
      }
      v10 = (v9 - (char *)v11) >> 3;
      if ( v10 > 0 )
        wil::details::WilApi_RecordFeatureUsageReports(
          (wil::details *)v11,
          (struct __WIL_RTL_FEATURE_USAGE_DATA *)v10,
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
0x18000f97c  mov     [rsp+arg_8], rbx
0x18000f981  mov     [rsp+arg_10], rbp
0x18000f986  mov     [rsp+arg_18], rsi
0x18000f98b  push    rdi
0x18000f98c  push    r14
0x18000f98e  push    r15
0x18000f990  sub     rsp, 70h
0x18000f994  mov     rax, cs:__security_cookie
0x18000f99b  xor     rax, rsp
0x18000f99e  mov     [rsp+88h+var_28], rax
0x18000f9a3  mov     rdi, rcx
0x18000f9a6  mov     rsi, [rcx+28h]
0x18000f9aa  mov     rbx, [rcx+20h]
0x18000f9ae  mov     rax, rsi
0x18000f9b1  sub     rax, rbx
0x18000f9b4  cmp     rax, 10h
0x18000f9b8  jb      loc_18000FB22
0x18000f9be  mov     ebp, 1
0x18000f9c3  lea     r14d, [rbp+1]
0x18000f9c7  mov     r15d, 1FFh
0x18000f9cd  cmp     rbx, rsi
0x18000f9d0  jz      loc_18000FAEF
0x18000f9d6  mov     r9, [rbx+8]
0x18000f9da  mov     r10d, [rbx]
0x18000f9dd  prefetchw byte ptr [r9]
0x18000f9e1  mov     eax, [r9]
0x18000f9e4  mov     ecx, eax
0x18000f9e6  and     ecx, 0FFC0401Eh
0x18000f9ec  lock cmpxchg [r9], ecx
0x18000f9f1  jnz     short loc_18000F9E4
0x18000f9f3  mov     edx, eax
0x18000f9f5  mov     ecx, eax
0x18000f9f7  shr     ecx, 1
0x18000f9f9  and     ecx, 0Fh
0x18000f9fc  jz      short loc_18000FA19
0x18000f9fe  prefetchw byte ptr [r9+4]
0x18000fa03  mov     eax, [r9+4]
0x18000fa07  mov     r8d, eax
0x18000fa0a  or      r8d, ecx
0x18000fa0d  lock cmpxchg [r9+4], r8d
0x18000fa13  jnz     short loc_18000FA07
0x18000fa15  not     eax
0x18000fa17  and     ecx, eax
0x18000fa19  lea     r8, [rsp+88h+var_58]
0x18000fa1e  test    bpl, cl
0x18000fa21  jz      short loc_18000FA35
0x18000fa23  mov     [rsp+88h+var_58], r10d
0x18000fa28  mov     [rsp+88h+var_54], 10002h
0x18000fa30  lea     r8, [rsp+88h+var_50]
0x18000fa35  test    r14b, cl
0x18000fa38  jz      short loc_18000FA49
0x18000fa3a  mov     [r8], r10d
0x18000fa3d  mov     dword ptr [r8+4], 10006h
0x18000fa45  add     r8, 8
0x18000fa49  test    cl, 4
0x18000fa4c  jz      short loc_18000FA5D
0x18000fa4e  mov     [r8], r10d
0x18000fa51  mov     dword ptr [r8+4], 10003h
0x18000fa59  add     r8, 8
0x18000fa5d  cmp     ecx, 8
0x18000fa60  jb      short loc_18000FA71
0x18000fa62  mov     [r8], r10d
0x18000fa65  mov     dword ptr [r8+4], 10007h
0x18000fa6d  add     r8, 8
0x18000fa71  mov     ecx, edx
0x18000fa73  shr     ecx, 5
0x18000fa76  test    r15d, ecx
0x18000fa79  jz      short loc_18000FA9C
0x18000fa7b  mov     [r8], r10d
0x18000fa7e  mov     eax, edx
0x18000fa80  shr     eax, 0Eh
0x18000fa83  and     ax, bp
0x18000fa86  shl     ax, 2
0x18000fa8a  mov     [r8+4], ax
0x18000fa8f  and     cx, r15w
0x18000fa93  mov     [r8+6], cx
0x18000fa98  add     r8, 8
0x18000fa9c  mov     eax, edx
0x18000fa9e  shr     eax, 0Fh
0x18000faa1  test    al, 7Fh
0x18000faa3  jz      short loc_18000FAC7
0x18000faa5  mov     [r8], r10d
0x18000faa8  shr     edx, 16h
0x18000faab  and     dx, bp
0x18000faae  shl     dx, 2
0x18000fab2  add     dx, bp
0x18000fab5  mov     [r8+4], dx
0x18000faba  and     ax, 7Fh
0x18000fabe  mov     [r8+6], ax
0x18000fac3  add     r8, 8
0x18000fac7  lea     rax, [rsp+88h+var_58]
0x18000facc  sub     r8, rax
0x18000facf  sar     r8, 3; unsigned __int64
0x18000fad3  test    r8, r8
0x18000fad6  jle     short loc_18000FAE6
0x18000fad8  mov     rdx, r8; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18000fadb  lea     rcx, [rsp+88h+var_58]; this
0x18000fae0  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18000fae5  nop
0x18000fae6  add     rbx, 10h
0x18000faea  jmp     loc_18000F9CD
0x18000faef  mov     rax, [rdi+20h]
0x18000faf3  mov     [rdi+28h], rax
0x18000faf7  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000fafe  test    rax, rax
0x18000fb01  jnz     short loc_18000FB0F
0x18000fb03  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000fb0a  test    rax, rax
0x18000fb0d  jz      short loc_18000FB22
0x18000fb0f  xor     r9d, r9d
0x18000fb12  xor     r8d, r8d
0x18000fb15  mov     edx, 0FEh
0x18000fb1a  xor     ecx, ecx
0x18000fb1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb21  nop
0x18000fb22  mov     rcx, [rsp+88h+var_28]
0x18000fb27  xor     rcx, rsp; StackCookie
0x18000fb2a  call    __security_check_cookie
0x18000fb2f  lea     r11, [rsp+88h+var_18]
0x18000fb34  mov     rbx, [r11+28h]
0x18000fb38  mov     rbp, [r11+30h]
0x18000fb3c  mov     rsi, [r11+38h]
0x18000fb40  mov     rsp, r11
0x18000fb43  pop     r15
0x18000fb45  pop     r14
0x18000fb47  pop     rdi
0x18000fb48  retn
```
