# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x140011330`
- end: `0x1400114e7`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140010e9c`
- `0x140033d50`
- `0x140033db0`

## callees

- `0x140002f60`
- `0x140011330`
- `0x140013ae4`
- `0x14003e010`

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
0x140011330  push    rbx
0x140011332  push    rbp
0x140011333  push    rsi
0x140011334  push    rdi
0x140011335  push    r14
0x140011337  push    r15
0x140011339  sub     rsp, 78h
0x14001133d  mov     rax, cs:__security_cookie
0x140011344  xor     rax, rsp
0x140011347  mov     [rsp+0A8h+var_48], rax
0x14001134c  mov     rsi, rcx
0x14001134f  mov     rbx, [rcx+20h]
0x140011353  mov     rdi, [rcx+28h]
0x140011357  mov     rax, rdi
0x14001135a  sub     rax, rbx
0x14001135d  cmp     rax, 10h
0x140011361  jb      loc_1400114CD
0x140011367  mov     ebp, 1
0x14001136c  lea     r14d, [rbp+1]
0x140011370  mov     r15d, 1FFh
0x140011376  cmp     rbx, rdi
0x140011379  jz      loc_14001149A
0x14001137f  mov     r8, [rbx+8]
0x140011383  mov     r10d, [rbx]
0x140011386  prefetchw byte ptr [r8]
0x14001138a  mov     eax, [r8]
0x14001138d  mov     ecx, eax
0x14001138f  and     ecx, 0FFC0401Eh
0x140011395  lock cmpxchg [r8], ecx
0x14001139a  jnz     short loc_14001138D
0x14001139c  mov     ecx, eax
0x14001139e  mov     r9d, eax
0x1400113a1  shr     r9d, 1
0x1400113a4  and     r9d, 0Fh
0x1400113a8  jz      short loc_1400113C7
0x1400113aa  prefetchw byte ptr [r8+4]
0x1400113af  mov     eax, [r8+4]
0x1400113b3  mov     edx, eax
0x1400113b5  or      edx, r9d
0x1400113b8  lock cmpxchg [r8+4], edx
0x1400113be  jnz     short loc_1400113B3
0x1400113c0  not     eax
0x1400113c2  and     eax, r9d
0x1400113c5  jmp     short loc_1400113CA
0x1400113c7  mov     eax, r9d
0x1400113ca  test    bpl, al
0x1400113cd  jz      short loc_1400113E3
0x1400113cf  mov     [rsp+0A8h+var_78], r10d
0x1400113d4  mov     [rsp+0A8h+var_74], 10002h
0x1400113dc  lea     rdx, [rsp+0A8h+var_70]
0x1400113e1  jmp     short loc_1400113E8
0x1400113e3  lea     rdx, [rsp+0A8h+var_78]
0x1400113e8  test    r14b, al
0x1400113eb  jz      short loc_1400113FB
0x1400113ed  mov     [rdx], r10d
0x1400113f0  mov     dword ptr [rdx+4], 10006h
0x1400113f7  add     rdx, 8
0x1400113fb  test    al, 4
0x1400113fd  jz      short loc_14001140D
0x1400113ff  mov     [rdx], r10d
0x140011402  mov     dword ptr [rdx+4], 10003h
0x140011409  add     rdx, 8
0x14001140d  cmp     eax, 8
0x140011410  jb      short loc_140011420
0x140011412  mov     [rdx], r10d
0x140011415  mov     dword ptr [rdx+4], 10007h
0x14001141c  add     rdx, 8
0x140011420  mov     r8d, ecx
0x140011423  shr     r8d, 5
0x140011427  test    r15d, r8d
0x14001142a  jz      short loc_14001144C
0x14001142c  mov     [rdx], r10d
0x14001142f  mov     eax, ecx
0x140011431  shr     eax, 0Eh
0x140011434  and     ax, bp
0x140011437  shl     ax, 2
0x14001143b  mov     [rdx+4], ax
0x14001143f  and     r8w, r15w; unsigned __int64
0x140011443  mov     [rdx+6], r8w
0x140011448  add     rdx, 8
0x14001144c  mov     eax, ecx
0x14001144e  shr     eax, 0Fh
0x140011451  test    al, 7Fh
0x140011453  jz      short loc_140011475
0x140011455  mov     [rdx], r10d
0x140011458  shr     ecx, 16h
0x14001145b  and     cx, bp
0x14001145e  shl     cx, 2
0x140011462  add     cx, bp
0x140011465  mov     [rdx+4], cx
0x140011469  and     ax, 7Fh
0x14001146d  mov     [rdx+6], ax
0x140011471  add     rdx, 8
0x140011475  lea     rax, [rsp+0A8h+var_78]
0x14001147a  sub     rdx, rax
0x14001147d  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x140011481  test    rdx, rdx
0x140011484  jle     short loc_140011491
0x140011486  lea     rcx, [rsp+0A8h+var_78]; this
0x14001148b  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x140011490  nop
0x140011491  add     rbx, 10h
0x140011495  jmp     loc_140011376
0x14001149a  mov     rax, [rsi+20h]
0x14001149e  mov     [rsi+28h], rax
0x1400114a2  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x1400114a9  test    rax, rax
0x1400114ac  jnz     short loc_1400114BA
0x1400114ae  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x1400114b5  test    rax, rax
0x1400114b8  jz      short loc_1400114CD
0x1400114ba  xor     r9d, r9d
0x1400114bd  xor     r8d, r8d
0x1400114c0  mov     edx, 0FEh
0x1400114c5  xor     ecx, ecx
0x1400114c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400114cc  nop
0x1400114cd  mov     rcx, [rsp+0A8h+var_48]
0x1400114d2  xor     rcx, rsp; StackCookie
0x1400114d5  call    __security_check_cookie
0x1400114da  add     rsp, 78h
0x1400114de  pop     r15
0x1400114e0  pop     r14
0x1400114e2  pop     rdi
0x1400114e3  pop     rsi
0x1400114e4  pop     rbp
0x1400114e5  pop     rbx
0x1400114e6  retn
```
