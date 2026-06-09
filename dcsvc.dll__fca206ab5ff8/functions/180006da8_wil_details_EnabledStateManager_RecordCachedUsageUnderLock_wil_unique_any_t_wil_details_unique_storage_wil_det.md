# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180006da8`
- end: `0x180006f5f`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: `__int64 (__fastcall *__fastcall(__int64))(_QWORD, __int64, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000695c`
- `0x18000abe0`
- `0x18000ac40`

## callees

- `0x180001cf0`
- `0x180006da8`
- `0x180009e94`
- `0x180013010`

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
0x180006da8  push    rbx
0x180006daa  push    rbp
0x180006dab  push    rsi
0x180006dac  push    rdi
0x180006dad  push    r14
0x180006daf  push    r15
0x180006db1  sub     rsp, 78h
0x180006db5  mov     rax, cs:__security_cookie
0x180006dbc  xor     rax, rsp
0x180006dbf  mov     [rsp+0A8h+var_48], rax
0x180006dc4  mov     rsi, rcx
0x180006dc7  mov     rbx, [rcx+20h]
0x180006dcb  mov     rdi, [rcx+28h]
0x180006dcf  mov     rax, rdi
0x180006dd2  sub     rax, rbx
0x180006dd5  cmp     rax, 10h
0x180006dd9  jb      loc_180006F45
0x180006ddf  mov     ebp, 1
0x180006de4  lea     r14d, [rbp+1]
0x180006de8  mov     r15d, 1FFh
0x180006dee  cmp     rbx, rdi
0x180006df1  jz      loc_180006F12
0x180006df7  mov     r8, [rbx+8]
0x180006dfb  mov     r10d, [rbx]
0x180006dfe  prefetchw byte ptr [r8]
0x180006e02  mov     eax, [r8]
0x180006e05  mov     ecx, eax
0x180006e07  and     ecx, 0FFC0401Eh
0x180006e0d  lock cmpxchg [r8], ecx
0x180006e12  jnz     short loc_180006E05
0x180006e14  mov     ecx, eax
0x180006e16  mov     r9d, eax
0x180006e19  shr     r9d, 1
0x180006e1c  and     r9d, 0Fh
0x180006e20  jz      short loc_180006E3F
0x180006e22  prefetchw byte ptr [r8+4]
0x180006e27  mov     eax, [r8+4]
0x180006e2b  mov     edx, eax
0x180006e2d  or      edx, r9d
0x180006e30  lock cmpxchg [r8+4], edx
0x180006e36  jnz     short loc_180006E2B
0x180006e38  not     eax
0x180006e3a  and     eax, r9d
0x180006e3d  jmp     short loc_180006E42
0x180006e3f  mov     eax, r9d
0x180006e42  test    bpl, al
0x180006e45  jz      short loc_180006E5B
0x180006e47  mov     [rsp+0A8h+var_78], r10d
0x180006e4c  mov     [rsp+0A8h+var_74], 10002h
0x180006e54  lea     rdx, [rsp+0A8h+var_70]
0x180006e59  jmp     short loc_180006E60
0x180006e5b  lea     rdx, [rsp+0A8h+var_78]
0x180006e60  test    r14b, al
0x180006e63  jz      short loc_180006E73
0x180006e65  mov     [rdx], r10d
0x180006e68  mov     dword ptr [rdx+4], 10006h
0x180006e6f  add     rdx, 8
0x180006e73  test    al, 4
0x180006e75  jz      short loc_180006E85
0x180006e77  mov     [rdx], r10d
0x180006e7a  mov     dword ptr [rdx+4], 10003h
0x180006e81  add     rdx, 8
0x180006e85  cmp     eax, 8
0x180006e88  jb      short loc_180006E98
0x180006e8a  mov     [rdx], r10d
0x180006e8d  mov     dword ptr [rdx+4], 10007h
0x180006e94  add     rdx, 8
0x180006e98  mov     r8d, ecx
0x180006e9b  shr     r8d, 5
0x180006e9f  test    r15d, r8d
0x180006ea2  jz      short loc_180006EC4
0x180006ea4  mov     [rdx], r10d
0x180006ea7  mov     eax, ecx
0x180006ea9  shr     eax, 0Eh
0x180006eac  and     ax, bp
0x180006eaf  shl     ax, 2
0x180006eb3  mov     [rdx+4], ax
0x180006eb7  and     r8w, r15w; unsigned __int64
0x180006ebb  mov     [rdx+6], r8w
0x180006ec0  add     rdx, 8
0x180006ec4  mov     eax, ecx
0x180006ec6  shr     eax, 0Fh
0x180006ec9  test    al, 7Fh
0x180006ecb  jz      short loc_180006EED
0x180006ecd  mov     [rdx], r10d
0x180006ed0  shr     ecx, 16h
0x180006ed3  and     cx, bp
0x180006ed6  shl     cx, 2
0x180006eda  add     cx, bp
0x180006edd  mov     [rdx+4], cx
0x180006ee1  and     ax, 7Fh
0x180006ee5  mov     [rdx+6], ax
0x180006ee9  add     rdx, 8
0x180006eed  lea     rax, [rsp+0A8h+var_78]
0x180006ef2  sub     rdx, rax
0x180006ef5  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180006ef9  test    rdx, rdx
0x180006efc  jle     short loc_180006F09
0x180006efe  lea     rcx, [rsp+0A8h+var_78]; this
0x180006f03  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180006f08  nop
0x180006f09  add     rbx, 10h
0x180006f0d  jmp     loc_180006DEE
0x180006f12  mov     rax, [rsi+20h]
0x180006f16  mov     [rsi+28h], rax
0x180006f1a  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180006f21  test    rax, rax
0x180006f24  jnz     short loc_180006F32
0x180006f26  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180006f2d  test    rax, rax
0x180006f30  jz      short loc_180006F45
0x180006f32  xor     r9d, r9d
0x180006f35  xor     r8d, r8d
0x180006f38  mov     edx, 0FEh
0x180006f3d  xor     ecx, ecx
0x180006f3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f44  nop
0x180006f45  mov     rcx, [rsp+0A8h+var_48]
0x180006f4a  xor     rcx, rsp; StackCookie
0x180006f4d  call    __security_check_cookie
0x180006f52  add     rsp, 78h
0x180006f56  pop     r15
0x180006f58  pop     r14
0x180006f5a  pop     rdi
0x180006f5b  pop     rsi
0x180006f5c  pop     rbp
0x180006f5d  pop     rbx
0x180006f5e  retn
```
