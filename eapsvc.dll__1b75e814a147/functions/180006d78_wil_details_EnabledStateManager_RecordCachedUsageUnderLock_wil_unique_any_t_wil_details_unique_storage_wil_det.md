# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180006d78`
- end: `0x180006f2f`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: `__int64 (__fastcall *__fastcall(__int64))(_QWORD, __int64, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800068e4`
- `0x18000a320`
- `0x18000a480`

## callees

- `0x180001f60`
- `0x180006d78`
- `0x1800097b4`
- `0x180017010`

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
0x180006d78  push    rbx
0x180006d7a  push    rbp
0x180006d7b  push    rsi
0x180006d7c  push    rdi
0x180006d7d  push    r14
0x180006d7f  push    r15
0x180006d81  sub     rsp, 78h
0x180006d85  mov     rax, cs:__security_cookie
0x180006d8c  xor     rax, rsp
0x180006d8f  mov     [rsp+0A8h+var_48], rax
0x180006d94  mov     rsi, rcx
0x180006d97  mov     rbx, [rcx+20h]
0x180006d9b  mov     rdi, [rcx+28h]
0x180006d9f  mov     rax, rdi
0x180006da2  sub     rax, rbx
0x180006da5  cmp     rax, 10h
0x180006da9  jb      loc_180006F15
0x180006daf  mov     ebp, 1
0x180006db4  lea     r14d, [rbp+1]
0x180006db8  mov     r15d, 1FFh
0x180006dbe  cmp     rbx, rdi
0x180006dc1  jz      loc_180006EE2
0x180006dc7  mov     r8, [rbx+8]
0x180006dcb  mov     r10d, [rbx]
0x180006dce  prefetchw byte ptr [r8]
0x180006dd2  mov     eax, [r8]
0x180006dd5  mov     ecx, eax
0x180006dd7  and     ecx, 0FFC0401Eh
0x180006ddd  lock cmpxchg [r8], ecx
0x180006de2  jnz     short loc_180006DD5
0x180006de4  mov     ecx, eax
0x180006de6  mov     r9d, eax
0x180006de9  shr     r9d, 1
0x180006dec  and     r9d, 0Fh
0x180006df0  jz      short loc_180006E0F
0x180006df2  prefetchw byte ptr [r8+4]
0x180006df7  mov     eax, [r8+4]
0x180006dfb  mov     edx, eax
0x180006dfd  or      edx, r9d
0x180006e00  lock cmpxchg [r8+4], edx
0x180006e06  jnz     short loc_180006DFB
0x180006e08  not     eax
0x180006e0a  and     eax, r9d
0x180006e0d  jmp     short loc_180006E12
0x180006e0f  mov     eax, r9d
0x180006e12  test    bpl, al
0x180006e15  jz      short loc_180006E2B
0x180006e17  mov     [rsp+0A8h+var_78], r10d
0x180006e1c  mov     [rsp+0A8h+var_74], 10002h
0x180006e24  lea     rdx, [rsp+0A8h+var_70]
0x180006e29  jmp     short loc_180006E30
0x180006e2b  lea     rdx, [rsp+0A8h+var_78]
0x180006e30  test    r14b, al
0x180006e33  jz      short loc_180006E43
0x180006e35  mov     [rdx], r10d
0x180006e38  mov     dword ptr [rdx+4], 10006h
0x180006e3f  add     rdx, 8
0x180006e43  test    al, 4
0x180006e45  jz      short loc_180006E55
0x180006e47  mov     [rdx], r10d
0x180006e4a  mov     dword ptr [rdx+4], 10003h
0x180006e51  add     rdx, 8
0x180006e55  cmp     eax, 8
0x180006e58  jb      short loc_180006E68
0x180006e5a  mov     [rdx], r10d
0x180006e5d  mov     dword ptr [rdx+4], 10007h
0x180006e64  add     rdx, 8
0x180006e68  mov     r8d, ecx
0x180006e6b  shr     r8d, 5
0x180006e6f  test    r15d, r8d
0x180006e72  jz      short loc_180006E94
0x180006e74  mov     [rdx], r10d
0x180006e77  mov     eax, ecx
0x180006e79  shr     eax, 0Eh
0x180006e7c  and     ax, bp
0x180006e7f  shl     ax, 2
0x180006e83  mov     [rdx+4], ax
0x180006e87  and     r8w, r15w; unsigned __int64
0x180006e8b  mov     [rdx+6], r8w
0x180006e90  add     rdx, 8
0x180006e94  mov     eax, ecx
0x180006e96  shr     eax, 0Fh
0x180006e99  test    al, 7Fh
0x180006e9b  jz      short loc_180006EBD
0x180006e9d  mov     [rdx], r10d
0x180006ea0  shr     ecx, 16h
0x180006ea3  and     cx, bp
0x180006ea6  shl     cx, 2
0x180006eaa  add     cx, bp
0x180006ead  mov     [rdx+4], cx
0x180006eb1  and     ax, 7Fh
0x180006eb5  mov     [rdx+6], ax
0x180006eb9  add     rdx, 8
0x180006ebd  lea     rax, [rsp+0A8h+var_78]
0x180006ec2  sub     rdx, rax
0x180006ec5  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180006ec9  test    rdx, rdx
0x180006ecc  jle     short loc_180006ED9
0x180006ece  lea     rcx, [rsp+0A8h+var_78]; this
0x180006ed3  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180006ed8  nop
0x180006ed9  add     rbx, 10h
0x180006edd  jmp     loc_180006DBE
0x180006ee2  mov     rax, [rsi+20h]
0x180006ee6  mov     [rsi+28h], rax
0x180006eea  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180006ef1  test    rax, rax
0x180006ef4  jnz     short loc_180006F02
0x180006ef6  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180006efd  test    rax, rax
0x180006f00  jz      short loc_180006F15
0x180006f02  xor     r9d, r9d
0x180006f05  xor     r8d, r8d
0x180006f08  mov     edx, 0FEh
0x180006f0d  xor     ecx, ecx
0x180006f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f14  nop
0x180006f15  mov     rcx, [rsp+0A8h+var_48]
0x180006f1a  xor     rcx, rsp; StackCookie
0x180006f1d  call    __security_check_cookie
0x180006f22  add     rsp, 78h
0x180006f26  pop     r15
0x180006f28  pop     r14
0x180006f2a  pop     rdi
0x180006f2b  pop     rsi
0x180006f2c  pop     rbp
0x180006f2d  pop     rbx
0x180006f2e  retn
```
