# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x1800065b4`
- end: `0x18000676b`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800060e0`

## callees

- `0x1800016d0`
- `0x1800065b4`
- `0x180008c24`
- `0x180022010`

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
0x1800065b4  push    rbx
0x1800065b6  push    rbp
0x1800065b7  push    rsi
0x1800065b8  push    rdi
0x1800065b9  push    r14
0x1800065bb  push    r15
0x1800065bd  sub     rsp, 78h
0x1800065c1  mov     rax, cs:__security_cookie
0x1800065c8  xor     rax, rsp
0x1800065cb  mov     [rsp+0A8h+var_48], rax
0x1800065d0  mov     rsi, rcx
0x1800065d3  mov     rbx, [rcx+20h]
0x1800065d7  mov     rdi, [rcx+28h]
0x1800065db  mov     rax, rdi
0x1800065de  sub     rax, rbx
0x1800065e1  cmp     rax, 10h
0x1800065e5  jb      loc_180006751
0x1800065eb  mov     ebp, 1
0x1800065f0  lea     r14d, [rbp+1]
0x1800065f4  mov     r15d, 1FFh
0x1800065fa  cmp     rbx, rdi
0x1800065fd  jz      loc_18000671E
0x180006603  mov     r8, [rbx+8]
0x180006607  mov     r10d, [rbx]
0x18000660a  prefetchw byte ptr [r8]
0x18000660e  mov     eax, [r8]
0x180006611  mov     ecx, eax
0x180006613  and     ecx, 0FFC0401Eh
0x180006619  lock cmpxchg [r8], ecx
0x18000661e  jnz     short loc_180006611
0x180006620  mov     ecx, eax
0x180006622  mov     r9d, eax
0x180006625  shr     r9d, 1
0x180006628  and     r9d, 0Fh
0x18000662c  jz      short loc_18000664B
0x18000662e  prefetchw byte ptr [r8+4]
0x180006633  mov     eax, [r8+4]
0x180006637  mov     edx, eax
0x180006639  or      edx, r9d
0x18000663c  lock cmpxchg [r8+4], edx
0x180006642  jnz     short loc_180006637
0x180006644  not     eax
0x180006646  and     eax, r9d
0x180006649  jmp     short loc_18000664E
0x18000664b  mov     eax, r9d
0x18000664e  test    bpl, al
0x180006651  jz      short loc_180006667
0x180006653  mov     [rsp+0A8h+var_78], r10d
0x180006658  mov     [rsp+0A8h+var_74], 10002h
0x180006660  lea     rdx, [rsp+0A8h+var_70]
0x180006665  jmp     short loc_18000666C
0x180006667  lea     rdx, [rsp+0A8h+var_78]
0x18000666c  test    r14b, al
0x18000666f  jz      short loc_18000667F
0x180006671  mov     [rdx], r10d
0x180006674  mov     dword ptr [rdx+4], 10006h
0x18000667b  add     rdx, 8
0x18000667f  test    al, 4
0x180006681  jz      short loc_180006691
0x180006683  mov     [rdx], r10d
0x180006686  mov     dword ptr [rdx+4], 10003h
0x18000668d  add     rdx, 8
0x180006691  cmp     eax, 8
0x180006694  jb      short loc_1800066A4
0x180006696  mov     [rdx], r10d
0x180006699  mov     dword ptr [rdx+4], 10007h
0x1800066a0  add     rdx, 8
0x1800066a4  mov     r8d, ecx
0x1800066a7  shr     r8d, 5
0x1800066ab  test    r15d, r8d
0x1800066ae  jz      short loc_1800066D0
0x1800066b0  mov     [rdx], r10d
0x1800066b3  mov     eax, ecx
0x1800066b5  shr     eax, 0Eh
0x1800066b8  and     ax, bp
0x1800066bb  shl     ax, 2
0x1800066bf  mov     [rdx+4], ax
0x1800066c3  and     r8w, r15w; unsigned __int64
0x1800066c7  mov     [rdx+6], r8w
0x1800066cc  add     rdx, 8
0x1800066d0  mov     eax, ecx
0x1800066d2  shr     eax, 0Fh
0x1800066d5  test    al, 7Fh
0x1800066d7  jz      short loc_1800066F9
0x1800066d9  mov     [rdx], r10d
0x1800066dc  shr     ecx, 16h
0x1800066df  and     cx, bp
0x1800066e2  shl     cx, 2
0x1800066e6  add     cx, bp
0x1800066e9  mov     [rdx+4], cx
0x1800066ed  and     ax, 7Fh
0x1800066f1  mov     [rdx+6], ax
0x1800066f5  add     rdx, 8
0x1800066f9  lea     rax, [rsp+0A8h+var_78]
0x1800066fe  sub     rdx, rax
0x180006701  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180006705  test    rdx, rdx
0x180006708  jle     short loc_180006715
0x18000670a  lea     rcx, [rsp+0A8h+var_78]; this
0x18000670f  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180006714  nop
0x180006715  add     rbx, 10h
0x180006719  jmp     loc_1800065FA
0x18000671e  mov     rax, [rsi+20h]
0x180006722  mov     [rsi+28h], rax
0x180006726  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000672d  test    rax, rax
0x180006730  jnz     short loc_18000673E
0x180006732  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180006739  test    rax, rax
0x18000673c  jz      short loc_180006751
0x18000673e  xor     r9d, r9d
0x180006741  xor     r8d, r8d
0x180006744  mov     edx, 0FEh
0x180006749  xor     ecx, ecx
0x18000674b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006750  nop
0x180006751  mov     rcx, [rsp+0A8h+var_48]
0x180006756  xor     rcx, rsp; StackCookie
0x180006759  call    __security_check_cookie
0x18000675e  add     rsp, 78h
0x180006762  pop     r15
0x180006764  pop     r14
0x180006766  pop     rdi
0x180006767  pop     rsi
0x180006768  pop     rbp
0x180006769  pop     rbx
0x18000676a  retn
```
