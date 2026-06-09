# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x1800263b0`
- end: `0x18002657d`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `461`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021650`
- `0x180021770`
- `0x180022710`
- `0x180025dd0`

## callees

- `0x18001e1d0`
- `0x1800263b0`
- `0x180029020`
- `0x180030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 (__fastcall *__fastcall wil::details::EnabledStateManager::RecordCachedUsageUnderLock(
        __int64 a1))(_QWORD, __int64, _QWORD, _QWORD)
{
  int *v2; // rbx
  int *v3; // rdi
  __int64 (__fastcall *result)(_QWORD, __int64, _QWORD, _QWORD); // rax
  unsigned __int32 *v5; // r8
  int v6; // r10d
  unsigned __int32 v7; // eax
  unsigned __int32 v8; // ett
  unsigned __int32 v9; // ecx
  unsigned __int32 v10; // eax
  char *v11; // rdx
  unsigned __int64 v12; // r8
  __int64 v13; // rdx
  _DWORD v14[2]; // [rsp+30h] [rbp-88h] BYREF
  char v15; // [rsp+38h] [rbp-80h] BYREF

  v2 = *(int **)(a1 + 32);
  v3 = *(int **)(a1 + 40);
  result = (__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))((char *)v3 - (char *)v2);
  if ( (unsigned __int64)((char *)v3 - (char *)v2) >= 0x10 )
  {
    while ( v2 != v3 )
    {
      v5 = (unsigned __int32 *)*((_QWORD *)v2 + 1);
      v6 = *v2;
      _m_prefetchw(v5);
      v7 = *v5;
      do
      {
        v8 = v7;
        v7 = _InterlockedCompareExchange((volatile signed __int32 *)v5, v7 & 0xFFC0401E, v7);
      }
      while ( v8 != v7 );
      v9 = v7;
      if ( ((v7 >> 1) & 0xF) != 0 )
      {
        _m_prefetchw(v5 + 1);
        v10 = (v7 >> 1) & 0xF & ~_InterlockedOr((volatile signed __int32 *)v5 + 1, (v7 >> 1) & 0xF);
      }
      else
      {
        v10 = 0;
      }
      if ( (v10 & 1) != 0 )
      {
        v14[0] = v6;
        v14[1] = 65538;
        v11 = &v15;
      }
      else
      {
        v11 = (char *)v14;
      }
      if ( (v10 & 2) != 0 )
      {
        *(_DWORD *)v11 = v6;
        *((_DWORD *)v11 + 1) = 65542;
        v11 += 8;
      }
      if ( (v10 & 4) != 0 )
      {
        *(_DWORD *)v11 = v6;
        *((_DWORD *)v11 + 1) = 65539;
        v11 += 8;
      }
      if ( v10 >= 8 )
      {
        *(_DWORD *)v11 = v6;
        *((_DWORD *)v11 + 1) = 65543;
        v11 += 8;
      }
      v12 = v9 >> 5;
      if ( (v12 & 0x1FF) != 0 )
      {
        *(_DWORD *)v11 = v6;
        *((_WORD *)v11 + 2) = 4 * ((v9 >> 14) & 1);
        LOWORD(v12) = v12 & 0x1FF;
        *((_WORD *)v11 + 3) = v12;
        v11 += 8;
      }
      if ( ((v9 >> 15) & 0x7F) != 0 )
      {
        *(_DWORD *)v11 = v6;
        *((_WORD *)v11 + 2) = 4 * ((v9 >> 22) & 1) + 1;
        *((_WORD *)v11 + 3) = (v9 >> 15) & 0x7F;
        v11 += 8;
      }
      v13 = (v11 - (char *)v14) >> 3;
      if ( v13 > 0 )
        wil::details::WilApi_RecordFeatureUsageReports(
          (wil::details *)v14,
          (struct __WIL_RTL_FEATURE_USAGE_DATA *)v13,
          v12);
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
0x1800263b0  push    rbx
0x1800263b2  push    rbp
0x1800263b3  push    rsi
0x1800263b4  push    rdi
0x1800263b5  push    r12
0x1800263b7  push    r13
0x1800263b9  push    r14
0x1800263bb  push    r15
0x1800263bd  sub     rsp, 78h
0x1800263c1  mov     rax, cs:__security_cookie
0x1800263c8  xor     rax, rsp
0x1800263cb  mov     [rsp+0B8h+var_58], rax
0x1800263d0  mov     rsi, rcx
0x1800263d3  mov     rbx, [rcx+20h]
0x1800263d7  mov     rdi, [rcx+28h]
0x1800263db  mov     rax, rdi
0x1800263de  sub     rax, rbx
0x1800263e1  cmp     rax, 10h
0x1800263e5  jb      loc_18002655F
0x1800263eb  mov     r11d, 3
0x1800263f1  mov     r14d, 1FFh
0x1800263f7  cmp     rbx, rdi
0x1800263fa  jz      loc_18002652C
0x180026400  mov     r8, [rbx+8]
0x180026404  mov     r10d, [rbx]
0x180026407  prefetchw byte ptr [r8]
0x18002640b  mov     eax, [r8]
0x18002640e  xchg    ax, ax
0x180026410  mov     ecx, eax
0x180026412  and     ecx, 0FFC0401Eh
0x180026418  lock cmpxchg [r8], ecx
0x18002641d  jnz     short loc_180026410
0x18002641f  mov     ecx, eax
0x180026421  mov     r9d, eax
0x180026424  shr     r9d, 1
0x180026427  and     r9d, 0Fh
0x18002642b  jz      short loc_180026454
0x18002642d  prefetchw byte ptr [r8+4]
0x180026432  mov     eax, [r8+4]
0x180026436  nop     word ptr [rax+rax+00000000h]
0x180026440  mov     edx, eax
0x180026442  or      edx, r9d
0x180026445  lock cmpxchg [r8+4], edx
0x18002644b  jnz     short loc_180026440
0x18002644d  not     eax
0x18002644f  and     eax, r9d
0x180026452  jmp     short loc_180026457
0x180026454  mov     eax, r9d
0x180026457  test    al, 1
0x180026459  jz      short loc_18002646F
0x18002645b  mov     [rsp+0B8h+var_88], r10d
0x180026460  mov     [rsp+0B8h+var_84], 10002h
0x180026468  lea     rdx, [rsp+0B8h+var_80]
0x18002646d  jmp     short loc_180026474
0x18002646f  lea     rdx, [rsp+0B8h+var_88]
0x180026474  test    al, 2
0x180026476  jz      short loc_180026486
0x180026478  mov     [rdx], r10d
0x18002647b  mov     dword ptr [rdx+4], 10006h
0x180026482  add     rdx, 8
0x180026486  test    al, 4
0x180026488  jz      short loc_180026498
0x18002648a  mov     [rdx], r10d
0x18002648d  mov     dword ptr [rdx+4], 10003h
0x180026494  add     rdx, 8
0x180026498  cmp     eax, 8
0x18002649b  jb      short loc_1800264AB
0x18002649d  mov     [rdx], r10d
0x1800264a0  mov     dword ptr [rdx+4], 10007h
0x1800264a7  add     rdx, 8
0x1800264ab  mov     r8d, ecx
0x1800264ae  shr     r8d, 5
0x1800264b2  test    r14d, r8d
0x1800264b5  jz      short loc_1800264D8
0x1800264b7  mov     [rdx], r10d
0x1800264ba  mov     eax, ecx
0x1800264bc  shr     eax, 0Eh
0x1800264bf  and     ax, 1
0x1800264c3  shl     ax, 2
0x1800264c7  mov     [rdx+4], ax
0x1800264cb  and     r8w, r14w; unsigned __int64
0x1800264cf  mov     [rdx+6], r8w
0x1800264d4  add     rdx, 8
0x1800264d8  mov     eax, ecx
0x1800264da  shr     eax, 0Fh
0x1800264dd  test    al, 7Fh
0x1800264df  jz      short loc_180026502
0x1800264e1  mov     [rdx], r10d
0x1800264e4  shr     ecx, 16h
0x1800264e7  and     cx, 1
0x1800264eb  shl     cx, 2
0x1800264ef  inc     cx
0x1800264f2  mov     [rdx+4], cx
0x1800264f6  and     ax, 7Fh
0x1800264fa  mov     [rdx+6], ax
0x1800264fe  add     rdx, 8
0x180026502  lea     rax, [rsp+0B8h+var_88]
0x180026507  sub     rdx, rax
0x18002650a  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18002650e  test    rdx, rdx
0x180026511  jle     short loc_180026523
0x180026513  lea     rcx, [rsp+0B8h+var_88]; this
0x180026518  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18002651d  mov     r11d, 3
0x180026523  add     rbx, 10h
0x180026527  jmp     loc_1800263F7
0x18002652c  mov     rax, [rsi+20h]
0x180026530  mov     [rsi+28h], rax
0x180026534  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18002653b  test    rax, rax
0x18002653e  jnz     short loc_18002654C
0x180026540  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180026547  test    rax, rax
0x18002654a  jz      short loc_18002655F
0x18002654c  xor     r9d, r9d
0x18002654f  xor     r8d, r8d
0x180026552  mov     edx, 0FEh
0x180026557  xor     ecx, ecx
0x180026559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002655e  nop
0x18002655f  mov     rcx, [rsp+0B8h+var_58]
0x180026564  xor     rcx, rsp; StackCookie
0x180026567  call    __security_check_cookie
0x18002656c  add     rsp, 78h
0x180026570  pop     r15
0x180026572  pop     r14
0x180026574  pop     r13
0x180026576  pop     r12
0x180026578  pop     rdi
0x180026579  pop     rsi
0x18002657a  pop     rbp
0x18002657b  pop     rbx
0x18002657c  retn
```
