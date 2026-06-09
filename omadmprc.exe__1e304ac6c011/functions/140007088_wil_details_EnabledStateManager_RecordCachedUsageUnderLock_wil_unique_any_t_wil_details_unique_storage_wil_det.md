# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x140007088`
- end: `0x140007240`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `440`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140002b80`
- `0x140002cc0`
- `0x1400068b8`

## callees

- `0x140007088`
- `0x140009a58`
- `0x140015690`
- `0x140017010`

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

  v2 = *(int **)(a1 + 48);
  v3 = *(int **)(a1 + 56);
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
    *(_QWORD *)(a1 + 56) = *(_QWORD *)(a1 + 48);
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
0x140007088  push    rbx
0x14000708a  push    rbp
0x14000708b  push    rsi
0x14000708c  push    rdi
0x14000708d  push    r14
0x14000708f  push    r15
0x140007091  sub     rsp, 78h
0x140007095  mov     rax, cs:__security_cookie
0x14000709c  xor     rax, rsp
0x14000709f  mov     [rsp+0A8h+var_48], rax
0x1400070a4  mov     rsi, rcx
0x1400070a7  mov     rbx, [rcx+30h]
0x1400070ab  mov     rdi, [rcx+38h]
0x1400070af  mov     rax, rdi
0x1400070b2  sub     rax, rbx
0x1400070b5  cmp     rax, 10h
0x1400070b9  jb      loc_140007225
0x1400070bf  mov     ebp, 1
0x1400070c4  lea     r14d, [rbp+1]
0x1400070c8  mov     r15d, 1FFh
0x1400070ce  cmp     rbx, rdi
0x1400070d1  jz      loc_1400071F2
0x1400070d7  mov     r8, [rbx+8]
0x1400070db  mov     r10d, [rbx]
0x1400070de  prefetchw byte ptr [r8]
0x1400070e2  mov     eax, [r8]
0x1400070e5  mov     ecx, eax
0x1400070e7  and     ecx, 0FFC0401Eh
0x1400070ed  lock cmpxchg [r8], ecx
0x1400070f2  jnz     short loc_1400070E5
0x1400070f4  mov     ecx, eax
0x1400070f6  mov     r9d, eax
0x1400070f9  shr     r9d, 1
0x1400070fc  and     r9d, 0Fh
0x140007100  jz      short loc_14000711F
0x140007102  prefetchw byte ptr [r8+4]
0x140007107  mov     eax, [r8+4]
0x14000710b  mov     edx, eax
0x14000710d  or      edx, r9d
0x140007110  lock cmpxchg [r8+4], edx
0x140007116  jnz     short loc_14000710B
0x140007118  not     eax
0x14000711a  and     eax, r9d
0x14000711d  jmp     short loc_140007122
0x14000711f  mov     eax, r9d
0x140007122  test    bpl, al
0x140007125  jz      short loc_14000713B
0x140007127  mov     [rsp+0A8h+var_78], r10d
0x14000712c  mov     [rsp+0A8h+var_74], 10002h
0x140007134  lea     rdx, [rsp+0A8h+var_70]
0x140007139  jmp     short loc_140007140
0x14000713b  lea     rdx, [rsp+0A8h+var_78]
0x140007140  test    r14b, al
0x140007143  jz      short loc_140007153
0x140007145  mov     [rdx], r10d
0x140007148  mov     dword ptr [rdx+4], 10006h
0x14000714f  add     rdx, 8
0x140007153  test    al, 4
0x140007155  jz      short loc_140007165
0x140007157  mov     [rdx], r10d
0x14000715a  mov     dword ptr [rdx+4], 10003h
0x140007161  add     rdx, 8
0x140007165  cmp     eax, 8
0x140007168  jb      short loc_140007178
0x14000716a  mov     [rdx], r10d
0x14000716d  mov     dword ptr [rdx+4], 10007h
0x140007174  add     rdx, 8
0x140007178  mov     r8d, ecx
0x14000717b  shr     r8d, 5
0x14000717f  test    r15d, r8d
0x140007182  jz      short loc_1400071A4
0x140007184  mov     [rdx], r10d
0x140007187  mov     eax, ecx
0x140007189  shr     eax, 0Eh
0x14000718c  and     ax, bp
0x14000718f  shl     ax, 2
0x140007193  mov     [rdx+4], ax
0x140007197  and     r8w, r15w; unsigned __int64
0x14000719b  mov     [rdx+6], r8w
0x1400071a0  add     rdx, 8
0x1400071a4  mov     eax, ecx
0x1400071a6  shr     eax, 0Fh
0x1400071a9  test    al, 7Fh
0x1400071ab  jz      short loc_1400071CD
0x1400071ad  mov     [rdx], r10d
0x1400071b0  shr     ecx, 16h
0x1400071b3  and     cx, bp
0x1400071b6  shl     cx, 2
0x1400071ba  add     cx, bp
0x1400071bd  mov     [rdx+4], cx
0x1400071c1  and     ax, 7Fh
0x1400071c5  mov     [rdx+6], ax
0x1400071c9  add     rdx, 8
0x1400071cd  lea     rax, [rsp+0A8h+var_78]
0x1400071d2  sub     rdx, rax
0x1400071d5  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x1400071d9  test    rdx, rdx
0x1400071dc  jle     short loc_1400071E9
0x1400071de  lea     rcx, [rsp+0A8h+var_78]; this
0x1400071e3  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x1400071e8  nop
0x1400071e9  add     rbx, 10h
0x1400071ed  jmp     loc_1400070CE
0x1400071f2  mov     rax, [rsi+30h]
0x1400071f6  mov     [rsi+38h], rax
0x1400071fa  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x140007201  test    rax, rax
0x140007204  jnz     short loc_140007212
0x140007206  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x14000720d  test    rax, rax
0x140007210  jz      short loc_140007225
0x140007212  xor     r9d, r9d
0x140007215  xor     r8d, r8d
0x140007218  mov     edx, 0FEh
0x14000721d  xor     ecx, ecx
0x14000721f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007224  nop
0x140007225  mov     rcx, [rsp+0A8h+var_48]
0x14000722a  xor     rcx, rsp; StackCookie
0x14000722d  call    __security_check_cookie
0x140007232  add     rsp, 78h
0x140007236  pop     r15
0x140007238  pop     r14
0x14000723a  pop     rdi
0x14000723b  pop     rsi
0x14000723c  pop     rbp
0x14000723d  pop     rbx
0x14000723e  retn
```
