# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x18000f09c`
- end: `0x18000f253`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: `__int64 (__fastcall *__fastcall(__int64))(_QWORD, __int64, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180003b00`
- `0x180003ca0`
- `0x18000e750`

## callees

- `0x180002e50`
- `0x18000f09c`
- `0x180014db4`
- `0x180023010`

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
0x18000f09c  push    rbx
0x18000f09e  push    rbp
0x18000f09f  push    rsi
0x18000f0a0  push    rdi
0x18000f0a1  push    r14
0x18000f0a3  push    r15
0x18000f0a5  sub     rsp, 78h
0x18000f0a9  mov     rax, cs:__security_cookie
0x18000f0b0  xor     rax, rsp
0x18000f0b3  mov     [rsp+0A8h+var_48], rax
0x18000f0b8  mov     rsi, rcx
0x18000f0bb  mov     rbx, [rcx+20h]
0x18000f0bf  mov     rdi, [rcx+28h]
0x18000f0c3  mov     rax, rdi
0x18000f0c6  sub     rax, rbx
0x18000f0c9  cmp     rax, 10h
0x18000f0cd  jb      loc_18000F239
0x18000f0d3  mov     ebp, 1
0x18000f0d8  lea     r14d, [rbp+1]
0x18000f0dc  mov     r15d, 1FFh
0x18000f0e2  cmp     rbx, rdi
0x18000f0e5  jz      loc_18000F206
0x18000f0eb  mov     r8, [rbx+8]
0x18000f0ef  mov     r10d, [rbx]
0x18000f0f2  prefetchw byte ptr [r8]
0x18000f0f6  mov     eax, [r8]
0x18000f0f9  mov     ecx, eax
0x18000f0fb  and     ecx, 0FFC0401Eh
0x18000f101  lock cmpxchg [r8], ecx
0x18000f106  jnz     short loc_18000F0F9
0x18000f108  mov     ecx, eax
0x18000f10a  mov     r9d, eax
0x18000f10d  shr     r9d, 1
0x18000f110  and     r9d, 0Fh
0x18000f114  jz      short loc_18000F133
0x18000f116  prefetchw byte ptr [r8+4]
0x18000f11b  mov     eax, [r8+4]
0x18000f11f  mov     edx, eax
0x18000f121  or      edx, r9d
0x18000f124  lock cmpxchg [r8+4], edx
0x18000f12a  jnz     short loc_18000F11F
0x18000f12c  not     eax
0x18000f12e  and     eax, r9d
0x18000f131  jmp     short loc_18000F136
0x18000f133  mov     eax, r9d
0x18000f136  test    bpl, al
0x18000f139  jz      short loc_18000F14F
0x18000f13b  mov     [rsp+0A8h+var_78], r10d
0x18000f140  mov     [rsp+0A8h+var_74], 10002h
0x18000f148  lea     rdx, [rsp+0A8h+var_70]
0x18000f14d  jmp     short loc_18000F154
0x18000f14f  lea     rdx, [rsp+0A8h+var_78]
0x18000f154  test    r14b, al
0x18000f157  jz      short loc_18000F167
0x18000f159  mov     [rdx], r10d
0x18000f15c  mov     dword ptr [rdx+4], 10006h
0x18000f163  add     rdx, 8
0x18000f167  test    al, 4
0x18000f169  jz      short loc_18000F179
0x18000f16b  mov     [rdx], r10d
0x18000f16e  mov     dword ptr [rdx+4], 10003h
0x18000f175  add     rdx, 8
0x18000f179  cmp     eax, 8
0x18000f17c  jb      short loc_18000F18C
0x18000f17e  mov     [rdx], r10d
0x18000f181  mov     dword ptr [rdx+4], 10007h
0x18000f188  add     rdx, 8
0x18000f18c  mov     r8d, ecx
0x18000f18f  shr     r8d, 5
0x18000f193  test    r15d, r8d
0x18000f196  jz      short loc_18000F1B8
0x18000f198  mov     [rdx], r10d
0x18000f19b  mov     eax, ecx
0x18000f19d  shr     eax, 0Eh
0x18000f1a0  and     ax, bp
0x18000f1a3  shl     ax, 2
0x18000f1a7  mov     [rdx+4], ax
0x18000f1ab  and     r8w, r15w; unsigned __int64
0x18000f1af  mov     [rdx+6], r8w
0x18000f1b4  add     rdx, 8
0x18000f1b8  mov     eax, ecx
0x18000f1ba  shr     eax, 0Fh
0x18000f1bd  test    al, 7Fh
0x18000f1bf  jz      short loc_18000F1E1
0x18000f1c1  mov     [rdx], r10d
0x18000f1c4  shr     ecx, 16h
0x18000f1c7  and     cx, bp
0x18000f1ca  shl     cx, 2
0x18000f1ce  add     cx, bp
0x18000f1d1  mov     [rdx+4], cx
0x18000f1d5  and     ax, 7Fh
0x18000f1d9  mov     [rdx+6], ax
0x18000f1dd  add     rdx, 8
0x18000f1e1  lea     rax, [rsp+0A8h+var_78]
0x18000f1e6  sub     rdx, rax
0x18000f1e9  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18000f1ed  test    rdx, rdx
0x18000f1f0  jle     short loc_18000F1FD
0x18000f1f2  lea     rcx, [rsp+0A8h+var_78]; this
0x18000f1f7  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18000f1fc  nop
0x18000f1fd  add     rbx, 10h
0x18000f201  jmp     loc_18000F0E2
0x18000f206  mov     rax, [rsi+20h]
0x18000f20a  mov     [rsi+28h], rax
0x18000f20e  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000f215  test    rax, rax
0x18000f218  jnz     short loc_18000F226
0x18000f21a  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000f221  test    rax, rax
0x18000f224  jz      short loc_18000F239
0x18000f226  xor     r9d, r9d
0x18000f229  xor     r8d, r8d
0x18000f22c  mov     edx, 0FEh
0x18000f231  xor     ecx, ecx
0x18000f233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f238  nop
0x18000f239  mov     rcx, [rsp+0A8h+var_48]
0x18000f23e  xor     rcx, rsp; StackCookie
0x18000f241  call    __security_check_cookie
0x18000f246  add     rsp, 78h
0x18000f24a  pop     r15
0x18000f24c  pop     r14
0x18000f24e  pop     rdi
0x18000f24f  pop     rsi
0x18000f250  pop     rbp
0x18000f251  pop     rbx
0x18000f252  retn
```
