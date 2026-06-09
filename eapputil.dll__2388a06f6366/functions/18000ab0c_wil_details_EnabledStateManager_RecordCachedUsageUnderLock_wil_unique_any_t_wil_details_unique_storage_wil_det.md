# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x18000ab0c`
- end: `0x18000acc3`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: `__int64 (__fastcall *__fastcall(__int64))(_QWORD, __int64, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000a57c`
- `0x180013740`
- `0x1800137a0`

## callees

- `0x1800021d0`
- `0x18000ab0c`
- `0x18000c394`
- `0x180033010`

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
0x18000ab0c  push    rbx
0x18000ab0e  push    rbp
0x18000ab0f  push    rsi
0x18000ab10  push    rdi
0x18000ab11  push    r14
0x18000ab13  push    r15
0x18000ab15  sub     rsp, 78h
0x18000ab19  mov     rax, cs:__security_cookie
0x18000ab20  xor     rax, rsp
0x18000ab23  mov     [rsp+0A8h+var_48], rax
0x18000ab28  mov     rsi, rcx
0x18000ab2b  mov     rbx, [rcx+20h]
0x18000ab2f  mov     rdi, [rcx+28h]
0x18000ab33  mov     rax, rdi
0x18000ab36  sub     rax, rbx
0x18000ab39  cmp     rax, 10h
0x18000ab3d  jb      loc_18000ACA9
0x18000ab43  mov     ebp, 1
0x18000ab48  lea     r14d, [rbp+1]
0x18000ab4c  mov     r15d, 1FFh
0x18000ab52  cmp     rbx, rdi
0x18000ab55  jz      loc_18000AC76
0x18000ab5b  mov     r8, [rbx+8]
0x18000ab5f  mov     r10d, [rbx]
0x18000ab62  prefetchw byte ptr [r8]
0x18000ab66  mov     eax, [r8]
0x18000ab69  mov     ecx, eax
0x18000ab6b  and     ecx, 0FFC0401Eh
0x18000ab71  lock cmpxchg [r8], ecx
0x18000ab76  jnz     short loc_18000AB69
0x18000ab78  mov     ecx, eax
0x18000ab7a  mov     r9d, eax
0x18000ab7d  shr     r9d, 1
0x18000ab80  and     r9d, 0Fh
0x18000ab84  jz      short loc_18000ABA3
0x18000ab86  prefetchw byte ptr [r8+4]
0x18000ab8b  mov     eax, [r8+4]
0x18000ab8f  mov     edx, eax
0x18000ab91  or      edx, r9d
0x18000ab94  lock cmpxchg [r8+4], edx
0x18000ab9a  jnz     short loc_18000AB8F
0x18000ab9c  not     eax
0x18000ab9e  and     eax, r9d
0x18000aba1  jmp     short loc_18000ABA6
0x18000aba3  mov     eax, r9d
0x18000aba6  test    bpl, al
0x18000aba9  jz      short loc_18000ABBF
0x18000abab  mov     [rsp+0A8h+var_78], r10d
0x18000abb0  mov     [rsp+0A8h+var_74], 10002h
0x18000abb8  lea     rdx, [rsp+0A8h+var_70]
0x18000abbd  jmp     short loc_18000ABC4
0x18000abbf  lea     rdx, [rsp+0A8h+var_78]
0x18000abc4  test    r14b, al
0x18000abc7  jz      short loc_18000ABD7
0x18000abc9  mov     [rdx], r10d
0x18000abcc  mov     dword ptr [rdx+4], 10006h
0x18000abd3  add     rdx, 8
0x18000abd7  test    al, 4
0x18000abd9  jz      short loc_18000ABE9
0x18000abdb  mov     [rdx], r10d
0x18000abde  mov     dword ptr [rdx+4], 10003h
0x18000abe5  add     rdx, 8
0x18000abe9  cmp     eax, 8
0x18000abec  jb      short loc_18000ABFC
0x18000abee  mov     [rdx], r10d
0x18000abf1  mov     dword ptr [rdx+4], 10007h
0x18000abf8  add     rdx, 8
0x18000abfc  mov     r8d, ecx
0x18000abff  shr     r8d, 5
0x18000ac03  test    r15d, r8d
0x18000ac06  jz      short loc_18000AC28
0x18000ac08  mov     [rdx], r10d
0x18000ac0b  mov     eax, ecx
0x18000ac0d  shr     eax, 0Eh
0x18000ac10  and     ax, bp
0x18000ac13  shl     ax, 2
0x18000ac17  mov     [rdx+4], ax
0x18000ac1b  and     r8w, r15w; unsigned __int64
0x18000ac1f  mov     [rdx+6], r8w
0x18000ac24  add     rdx, 8
0x18000ac28  mov     eax, ecx
0x18000ac2a  shr     eax, 0Fh
0x18000ac2d  test    al, 7Fh
0x18000ac2f  jz      short loc_18000AC51
0x18000ac31  mov     [rdx], r10d
0x18000ac34  shr     ecx, 16h
0x18000ac37  and     cx, bp
0x18000ac3a  shl     cx, 2
0x18000ac3e  add     cx, bp
0x18000ac41  mov     [rdx+4], cx
0x18000ac45  and     ax, 7Fh
0x18000ac49  mov     [rdx+6], ax
0x18000ac4d  add     rdx, 8
0x18000ac51  lea     rax, [rsp+0A8h+var_78]
0x18000ac56  sub     rdx, rax
0x18000ac59  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18000ac5d  test    rdx, rdx
0x18000ac60  jle     short loc_18000AC6D
0x18000ac62  lea     rcx, [rsp+0A8h+var_78]; this
0x18000ac67  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18000ac6c  nop
0x18000ac6d  add     rbx, 10h
0x18000ac71  jmp     loc_18000AB52
0x18000ac76  mov     rax, [rsi+20h]
0x18000ac7a  mov     [rsi+28h], rax
0x18000ac7e  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000ac85  test    rax, rax
0x18000ac88  jnz     short loc_18000AC96
0x18000ac8a  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000ac91  test    rax, rax
0x18000ac94  jz      short loc_18000ACA9
0x18000ac96  xor     r9d, r9d
0x18000ac99  xor     r8d, r8d
0x18000ac9c  mov     edx, 0FEh
0x18000aca1  xor     ecx, ecx
0x18000aca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aca8  nop
0x18000aca9  mov     rcx, [rsp+0A8h+var_48]
0x18000acae  xor     rcx, rsp; StackCookie
0x18000acb1  call    __security_check_cookie
0x18000acb6  add     rsp, 78h
0x18000acba  pop     r15
0x18000acbc  pop     r14
0x18000acbe  pop     rdi
0x18000acbf  pop     rsi
0x18000acc0  pop     rbp
0x18000acc1  pop     rbx
0x18000acc2  retn
```
