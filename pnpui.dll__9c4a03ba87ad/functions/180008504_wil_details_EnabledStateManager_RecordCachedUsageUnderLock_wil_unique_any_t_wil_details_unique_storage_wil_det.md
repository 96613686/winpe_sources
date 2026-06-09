# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180008504`
- end: `0x1800086b9`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `437`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800080dc`

## callees

- `0x180008504`
- `0x18000a2e4`
- `0x18000cd10`
- `0x18000e010`

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
0x180008504  push    rbx
0x180008506  push    rbp
0x180008507  push    rsi
0x180008508  push    rdi
0x180008509  push    r14
0x18000850b  push    r15
0x18000850d  sub     rsp, 78h
0x180008511  mov     rax, cs:__security_cookie
0x180008518  xor     rax, rsp
0x18000851b  mov     [rsp+0A8h+var_48], rax
0x180008520  mov     rdi, [rcx+28h]
0x180008524  mov     rsi, rcx
0x180008527  mov     rbx, [rcx+20h]
0x18000852b  mov     rax, rdi
0x18000852e  sub     rax, rbx
0x180008531  cmp     rax, 10h
0x180008535  jb      loc_18000869F
0x18000853b  mov     ebp, 1
0x180008540  mov     r15d, 1FFh
0x180008546  lea     r14d, [rbp+1]
0x18000854a  cmp     rbx, rdi
0x18000854d  jz      loc_18000866D
0x180008553  mov     r8, [rbx+8]
0x180008557  mov     r10d, [rbx]
0x18000855a  prefetchw byte ptr [r8]
0x18000855e  mov     eax, [r8]
0x180008561  mov     ecx, eax
0x180008563  and     ecx, 0FFC0401Eh
0x180008569  lock cmpxchg [r8], ecx
0x18000856e  jnz     short loc_180008561
0x180008570  mov     r9d, eax
0x180008573  mov     ecx, eax
0x180008575  shr     r9d, 1
0x180008578  and     r9d, 0Fh
0x18000857c  jz      short loc_18000859B
0x18000857e  prefetchw byte ptr [r8+4]
0x180008583  mov     eax, [r8+4]
0x180008587  mov     edx, eax
0x180008589  or      edx, r9d
0x18000858c  lock cmpxchg [r8+4], edx
0x180008592  jnz     short loc_180008587
0x180008594  not     eax
0x180008596  and     eax, r9d
0x180008599  jmp     short loc_18000859E
0x18000859b  mov     eax, r9d
0x18000859e  test    bpl, al
0x1800085a1  jz      short loc_1800085B7
0x1800085a3  mov     [rsp+0A8h+var_78], r10d
0x1800085a8  lea     rdx, [rsp+0A8h+var_70]
0x1800085ad  mov     [rsp+0A8h+var_74], 10002h
0x1800085b5  jmp     short loc_1800085BC
0x1800085b7  lea     rdx, [rsp+0A8h+var_78]
0x1800085bc  test    r14b, al
0x1800085bf  jz      short loc_1800085CF
0x1800085c1  mov     [rdx], r10d
0x1800085c4  mov     dword ptr [rdx+4], 10006h
0x1800085cb  add     rdx, 8
0x1800085cf  test    al, 4
0x1800085d1  jz      short loc_1800085E1
0x1800085d3  mov     [rdx], r10d
0x1800085d6  mov     dword ptr [rdx+4], 10003h
0x1800085dd  add     rdx, 8
0x1800085e1  cmp     eax, 8
0x1800085e4  jb      short loc_1800085F4
0x1800085e6  mov     [rdx], r10d
0x1800085e9  mov     dword ptr [rdx+4], 10007h
0x1800085f0  add     rdx, 8
0x1800085f4  mov     r8d, ecx
0x1800085f7  shr     r8d, 5
0x1800085fb  test    r15d, r8d
0x1800085fe  jz      short loc_180008620
0x180008600  and     r8w, r15w; unsigned __int64
0x180008604  mov     [rdx], r10d
0x180008607  mov     eax, ecx
0x180008609  mov     [rdx+6], r8w
0x18000860e  shr     eax, 0Eh
0x180008611  and     ax, bp
0x180008614  shl     ax, 2
0x180008618  mov     [rdx+4], ax
0x18000861c  add     rdx, 8
0x180008620  mov     eax, ecx
0x180008622  shr     eax, 0Fh
0x180008625  test    al, 7Fh
0x180008627  jz      short loc_180008649
0x180008629  shr     ecx, 16h
0x18000862c  and     ax, 7Fh
0x180008630  and     cx, bp
0x180008633  mov     [rdx], r10d
0x180008636  shl     cx, 2
0x18000863a  add     cx, bp
0x18000863d  mov     [rdx+6], ax
0x180008641  mov     [rdx+4], cx
0x180008645  add     rdx, 8
0x180008649  lea     rax, [rsp+0A8h+var_78]
0x18000864e  sub     rdx, rax
0x180008651  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180008655  test    rdx, rdx
0x180008658  jle     short loc_180008664
0x18000865a  lea     rcx, [rsp+0A8h+var_78]; this
0x18000865f  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180008664  add     rbx, 10h
0x180008668  jmp     loc_18000854A
0x18000866d  mov     rax, [rsi+20h]
0x180008671  mov     [rsi+28h], rax
0x180008675  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000867c  test    rax, rax
0x18000867f  jnz     short loc_18000868D
0x180008681  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180008688  test    rax, rax
0x18000868b  jz      short loc_18000869F
0x18000868d  xor     r9d, r9d
0x180008690  xor     r8d, r8d
0x180008693  mov     edx, 0FEh
0x180008698  xor     ecx, ecx
0x18000869a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000869f  mov     rcx, [rsp+0A8h+var_48]
0x1800086a4  xor     rcx, rsp; StackCookie
0x1800086a7  call    __security_check_cookie
0x1800086ac  add     rsp, 78h
0x1800086b0  pop     r15
0x1800086b2  pop     r14
0x1800086b4  pop     rdi
0x1800086b5  pop     rsi
0x1800086b6  pop     rbp
0x1800086b7  pop     rbx
0x1800086b8  retn
```
