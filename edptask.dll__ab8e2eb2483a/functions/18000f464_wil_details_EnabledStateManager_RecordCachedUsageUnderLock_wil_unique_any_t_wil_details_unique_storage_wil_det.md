# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x18000f464`
- end: `0x18000f61b`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: `__int64 (__fastcall *__fastcall(__int64))(_QWORD, __int64, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180006f30`
- `0x180007070`
- `0x18000ee88`

## callees

- `0x18000f464`
- `0x180011ab4`
- `0x180013410`
- `0x180014010`

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
0x18000f464  push    rbx
0x18000f466  push    rbp
0x18000f467  push    rsi
0x18000f468  push    rdi
0x18000f469  push    r14
0x18000f46b  push    r15
0x18000f46d  sub     rsp, 78h
0x18000f471  mov     rax, cs:__security_cookie
0x18000f478  xor     rax, rsp
0x18000f47b  mov     [rsp+0A8h+var_48], rax
0x18000f480  mov     rsi, rcx
0x18000f483  mov     rbx, [rcx+20h]
0x18000f487  mov     rdi, [rcx+28h]
0x18000f48b  mov     rax, rdi
0x18000f48e  sub     rax, rbx
0x18000f491  cmp     rax, 10h
0x18000f495  jb      loc_18000F601
0x18000f49b  mov     ebp, 1
0x18000f4a0  lea     r14d, [rbp+1]
0x18000f4a4  mov     r15d, 1FFh
0x18000f4aa  cmp     rbx, rdi
0x18000f4ad  jz      loc_18000F5CE
0x18000f4b3  mov     r8, [rbx+8]
0x18000f4b7  mov     r10d, [rbx]
0x18000f4ba  prefetchw byte ptr [r8]
0x18000f4be  mov     eax, [r8]
0x18000f4c1  mov     ecx, eax
0x18000f4c3  and     ecx, 0FFC0401Eh
0x18000f4c9  lock cmpxchg [r8], ecx
0x18000f4ce  jnz     short loc_18000F4C1
0x18000f4d0  mov     ecx, eax
0x18000f4d2  mov     r9d, eax
0x18000f4d5  shr     r9d, 1
0x18000f4d8  and     r9d, 0Fh
0x18000f4dc  jz      short loc_18000F4FB
0x18000f4de  prefetchw byte ptr [r8+4]
0x18000f4e3  mov     eax, [r8+4]
0x18000f4e7  mov     edx, eax
0x18000f4e9  or      edx, r9d
0x18000f4ec  lock cmpxchg [r8+4], edx
0x18000f4f2  jnz     short loc_18000F4E7
0x18000f4f4  not     eax
0x18000f4f6  and     eax, r9d
0x18000f4f9  jmp     short loc_18000F4FE
0x18000f4fb  mov     eax, r9d
0x18000f4fe  test    bpl, al
0x18000f501  jz      short loc_18000F517
0x18000f503  mov     [rsp+0A8h+var_78], r10d
0x18000f508  mov     [rsp+0A8h+var_74], 10002h
0x18000f510  lea     rdx, [rsp+0A8h+var_70]
0x18000f515  jmp     short loc_18000F51C
0x18000f517  lea     rdx, [rsp+0A8h+var_78]
0x18000f51c  test    r14b, al
0x18000f51f  jz      short loc_18000F52F
0x18000f521  mov     [rdx], r10d
0x18000f524  mov     dword ptr [rdx+4], 10006h
0x18000f52b  add     rdx, 8
0x18000f52f  test    al, 4
0x18000f531  jz      short loc_18000F541
0x18000f533  mov     [rdx], r10d
0x18000f536  mov     dword ptr [rdx+4], 10003h
0x18000f53d  add     rdx, 8
0x18000f541  cmp     eax, 8
0x18000f544  jb      short loc_18000F554
0x18000f546  mov     [rdx], r10d
0x18000f549  mov     dword ptr [rdx+4], 10007h
0x18000f550  add     rdx, 8
0x18000f554  mov     r8d, ecx
0x18000f557  shr     r8d, 5
0x18000f55b  test    r15d, r8d
0x18000f55e  jz      short loc_18000F580
0x18000f560  mov     [rdx], r10d
0x18000f563  mov     eax, ecx
0x18000f565  shr     eax, 0Eh
0x18000f568  and     ax, bp
0x18000f56b  shl     ax, 2
0x18000f56f  mov     [rdx+4], ax
0x18000f573  and     r8w, r15w; unsigned __int64
0x18000f577  mov     [rdx+6], r8w
0x18000f57c  add     rdx, 8
0x18000f580  mov     eax, ecx
0x18000f582  shr     eax, 0Fh
0x18000f585  test    al, 7Fh
0x18000f587  jz      short loc_18000F5A9
0x18000f589  mov     [rdx], r10d
0x18000f58c  shr     ecx, 16h
0x18000f58f  and     cx, bp
0x18000f592  shl     cx, 2
0x18000f596  add     cx, bp
0x18000f599  mov     [rdx+4], cx
0x18000f59d  and     ax, 7Fh
0x18000f5a1  mov     [rdx+6], ax
0x18000f5a5  add     rdx, 8
0x18000f5a9  lea     rax, [rsp+0A8h+var_78]
0x18000f5ae  sub     rdx, rax
0x18000f5b1  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18000f5b5  test    rdx, rdx
0x18000f5b8  jle     short loc_18000F5C5
0x18000f5ba  lea     rcx, [rsp+0A8h+var_78]; this
0x18000f5bf  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18000f5c4  nop
0x18000f5c5  add     rbx, 10h
0x18000f5c9  jmp     loc_18000F4AA
0x18000f5ce  mov     rax, [rsi+20h]
0x18000f5d2  mov     [rsi+28h], rax
0x18000f5d6  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000f5dd  test    rax, rax
0x18000f5e0  jnz     short loc_18000F5EE
0x18000f5e2  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000f5e9  test    rax, rax
0x18000f5ec  jz      short loc_18000F601
0x18000f5ee  xor     r9d, r9d
0x18000f5f1  xor     r8d, r8d
0x18000f5f4  mov     edx, 0FEh
0x18000f5f9  xor     ecx, ecx
0x18000f5fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f600  nop
0x18000f601  mov     rcx, [rsp+0A8h+var_48]
0x18000f606  xor     rcx, rsp; StackCookie
0x18000f609  call    __security_check_cookie
0x18000f60e  add     rsp, 78h
0x18000f612  pop     r15
0x18000f614  pop     r14
0x18000f616  pop     rdi
0x18000f617  pop     rsi
0x18000f618  pop     rbp
0x18000f619  pop     rbx
0x18000f61a  retn
```
