# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180007ba4`
- end: `0x180007d59`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `437`
- prototype: `__int64 (__fastcall *__fastcall(__int64))(_QWORD, __int64, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180007688`
- `0x1800138a0`
- `0x180013900`

## callees

- `0x180007ba4`
- `0x18000b154`
- `0x180018500`
- `0x180019010`

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
0x180007ba4  push    rbx
0x180007ba6  push    rbp
0x180007ba7  push    rsi
0x180007ba8  push    rdi
0x180007ba9  push    r14
0x180007bab  push    r15
0x180007bad  sub     rsp, 78h
0x180007bb1  mov     rax, cs:__security_cookie
0x180007bb8  xor     rax, rsp
0x180007bbb  mov     [rsp+0A8h+var_48], rax
0x180007bc0  mov     rdi, [rcx+28h]
0x180007bc4  mov     rsi, rcx
0x180007bc7  mov     rbx, [rcx+20h]
0x180007bcb  mov     rax, rdi
0x180007bce  sub     rax, rbx
0x180007bd1  cmp     rax, 10h
0x180007bd5  jb      loc_180007D3F
0x180007bdb  mov     ebp, 1
0x180007be0  mov     r15d, 1FFh
0x180007be6  lea     r14d, [rbp+1]
0x180007bea  cmp     rbx, rdi
0x180007bed  jz      loc_180007D0D
0x180007bf3  mov     r8, [rbx+8]
0x180007bf7  mov     r10d, [rbx]
0x180007bfa  prefetchw byte ptr [r8]
0x180007bfe  mov     eax, [r8]
0x180007c01  mov     ecx, eax
0x180007c03  and     ecx, 0FFC0401Eh
0x180007c09  lock cmpxchg [r8], ecx
0x180007c0e  jnz     short loc_180007C01
0x180007c10  mov     r9d, eax
0x180007c13  mov     ecx, eax
0x180007c15  shr     r9d, 1
0x180007c18  and     r9d, 0Fh
0x180007c1c  jz      short loc_180007C3B
0x180007c1e  prefetchw byte ptr [r8+4]
0x180007c23  mov     eax, [r8+4]
0x180007c27  mov     edx, eax
0x180007c29  or      edx, r9d
0x180007c2c  lock cmpxchg [r8+4], edx
0x180007c32  jnz     short loc_180007C27
0x180007c34  not     eax
0x180007c36  and     eax, r9d
0x180007c39  jmp     short loc_180007C3E
0x180007c3b  mov     eax, r9d
0x180007c3e  test    bpl, al
0x180007c41  jz      short loc_180007C57
0x180007c43  mov     [rsp+0A8h+var_78], r10d
0x180007c48  lea     rdx, [rsp+0A8h+var_70]
0x180007c4d  mov     [rsp+0A8h+var_74], 10002h
0x180007c55  jmp     short loc_180007C5C
0x180007c57  lea     rdx, [rsp+0A8h+var_78]
0x180007c5c  test    r14b, al
0x180007c5f  jz      short loc_180007C6F
0x180007c61  mov     [rdx], r10d
0x180007c64  mov     dword ptr [rdx+4], 10006h
0x180007c6b  add     rdx, 8
0x180007c6f  test    al, 4
0x180007c71  jz      short loc_180007C81
0x180007c73  mov     [rdx], r10d
0x180007c76  mov     dword ptr [rdx+4], 10003h
0x180007c7d  add     rdx, 8
0x180007c81  cmp     eax, 8
0x180007c84  jb      short loc_180007C94
0x180007c86  mov     [rdx], r10d
0x180007c89  mov     dword ptr [rdx+4], 10007h
0x180007c90  add     rdx, 8
0x180007c94  mov     r8d, ecx
0x180007c97  shr     r8d, 5
0x180007c9b  test    r15d, r8d
0x180007c9e  jz      short loc_180007CC0
0x180007ca0  and     r8w, r15w; unsigned __int64
0x180007ca4  mov     [rdx], r10d
0x180007ca7  mov     eax, ecx
0x180007ca9  mov     [rdx+6], r8w
0x180007cae  shr     eax, 0Eh
0x180007cb1  and     ax, bp
0x180007cb4  shl     ax, 2
0x180007cb8  mov     [rdx+4], ax
0x180007cbc  add     rdx, 8
0x180007cc0  mov     eax, ecx
0x180007cc2  shr     eax, 0Fh
0x180007cc5  test    al, 7Fh
0x180007cc7  jz      short loc_180007CE9
0x180007cc9  shr     ecx, 16h
0x180007ccc  and     ax, 7Fh
0x180007cd0  and     cx, bp
0x180007cd3  mov     [rdx], r10d
0x180007cd6  shl     cx, 2
0x180007cda  add     cx, bp
0x180007cdd  mov     [rdx+6], ax
0x180007ce1  mov     [rdx+4], cx
0x180007ce5  add     rdx, 8
0x180007ce9  lea     rax, [rsp+0A8h+var_78]
0x180007cee  sub     rdx, rax
0x180007cf1  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180007cf5  test    rdx, rdx
0x180007cf8  jle     short loc_180007D04
0x180007cfa  lea     rcx, [rsp+0A8h+var_78]; this
0x180007cff  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180007d04  add     rbx, 10h
0x180007d08  jmp     loc_180007BEA
0x180007d0d  mov     rax, [rsi+20h]
0x180007d11  mov     [rsi+28h], rax
0x180007d15  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180007d1c  test    rax, rax
0x180007d1f  jnz     short loc_180007D2D
0x180007d21  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180007d28  test    rax, rax
0x180007d2b  jz      short loc_180007D3F
0x180007d2d  xor     r9d, r9d
0x180007d30  xor     r8d, r8d
0x180007d33  mov     edx, 0FEh
0x180007d38  xor     ecx, ecx
0x180007d3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d3f  mov     rcx, [rsp+0A8h+var_48]
0x180007d44  xor     rcx, rsp; StackCookie
0x180007d47  call    __security_check_cookie
0x180007d4c  add     rsp, 78h
0x180007d50  pop     r15
0x180007d52  pop     r14
0x180007d54  pop     rdi
0x180007d55  pop     rsi
0x180007d56  pop     rbp
0x180007d57  pop     rbx
0x180007d58  retn
```
