# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x18000b24c`
- end: `0x18000b403`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `439`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180007a50`
- `0x180007bf0`
- `0x18000ac40`

## callees

- `0x180002490`
- `0x18000b24c`
- `0x18000fa84`
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
0x18000b24c  push    rbx
0x18000b24e  push    rbp
0x18000b24f  push    rsi
0x18000b250  push    rdi
0x18000b251  push    r14
0x18000b253  push    r15
0x18000b255  sub     rsp, 78h
0x18000b259  mov     rax, cs:__security_cookie
0x18000b260  xor     rax, rsp
0x18000b263  mov     [rsp+0A8h+var_48], rax
0x18000b268  mov     rsi, rcx
0x18000b26b  mov     rbx, [rcx+20h]
0x18000b26f  mov     rdi, [rcx+28h]
0x18000b273  mov     rax, rdi
0x18000b276  sub     rax, rbx
0x18000b279  cmp     rax, 10h
0x18000b27d  jb      loc_18000B3E9
0x18000b283  mov     ebp, 1
0x18000b288  lea     r14d, [rbp+1]
0x18000b28c  mov     r15d, 1FFh
0x18000b292  cmp     rbx, rdi
0x18000b295  jz      loc_18000B3B6
0x18000b29b  mov     r8, [rbx+8]
0x18000b29f  mov     r10d, [rbx]
0x18000b2a2  prefetchw byte ptr [r8]
0x18000b2a6  mov     eax, [r8]
0x18000b2a9  mov     ecx, eax
0x18000b2ab  and     ecx, 0FFC0401Eh
0x18000b2b1  lock cmpxchg [r8], ecx
0x18000b2b6  jnz     short loc_18000B2A9
0x18000b2b8  mov     ecx, eax
0x18000b2ba  mov     r9d, eax
0x18000b2bd  shr     r9d, 1
0x18000b2c0  and     r9d, 0Fh
0x18000b2c4  jz      short loc_18000B2E3
0x18000b2c6  prefetchw byte ptr [r8+4]
0x18000b2cb  mov     eax, [r8+4]
0x18000b2cf  mov     edx, eax
0x18000b2d1  or      edx, r9d
0x18000b2d4  lock cmpxchg [r8+4], edx
0x18000b2da  jnz     short loc_18000B2CF
0x18000b2dc  not     eax
0x18000b2de  and     eax, r9d
0x18000b2e1  jmp     short loc_18000B2E6
0x18000b2e3  mov     eax, r9d
0x18000b2e6  test    bpl, al
0x18000b2e9  jz      short loc_18000B2FF
0x18000b2eb  mov     [rsp+0A8h+var_78], r10d
0x18000b2f0  mov     [rsp+0A8h+var_74], 10002h
0x18000b2f8  lea     rdx, [rsp+0A8h+var_70]
0x18000b2fd  jmp     short loc_18000B304
0x18000b2ff  lea     rdx, [rsp+0A8h+var_78]
0x18000b304  test    r14b, al
0x18000b307  jz      short loc_18000B317
0x18000b309  mov     [rdx], r10d
0x18000b30c  mov     dword ptr [rdx+4], 10006h
0x18000b313  add     rdx, 8
0x18000b317  test    al, 4
0x18000b319  jz      short loc_18000B329
0x18000b31b  mov     [rdx], r10d
0x18000b31e  mov     dword ptr [rdx+4], 10003h
0x18000b325  add     rdx, 8
0x18000b329  cmp     eax, 8
0x18000b32c  jb      short loc_18000B33C
0x18000b32e  mov     [rdx], r10d
0x18000b331  mov     dword ptr [rdx+4], 10007h
0x18000b338  add     rdx, 8
0x18000b33c  mov     r8d, ecx
0x18000b33f  shr     r8d, 5
0x18000b343  test    r15d, r8d
0x18000b346  jz      short loc_18000B368
0x18000b348  mov     [rdx], r10d
0x18000b34b  mov     eax, ecx
0x18000b34d  shr     eax, 0Eh
0x18000b350  and     ax, bp
0x18000b353  shl     ax, 2
0x18000b357  mov     [rdx+4], ax
0x18000b35b  and     r8w, r15w; unsigned __int64
0x18000b35f  mov     [rdx+6], r8w
0x18000b364  add     rdx, 8
0x18000b368  mov     eax, ecx
0x18000b36a  shr     eax, 0Fh
0x18000b36d  test    al, 7Fh
0x18000b36f  jz      short loc_18000B391
0x18000b371  mov     [rdx], r10d
0x18000b374  shr     ecx, 16h
0x18000b377  and     cx, bp
0x18000b37a  shl     cx, 2
0x18000b37e  add     cx, bp
0x18000b381  mov     [rdx+4], cx
0x18000b385  and     ax, 7Fh
0x18000b389  mov     [rdx+6], ax
0x18000b38d  add     rdx, 8
0x18000b391  lea     rax, [rsp+0A8h+var_78]
0x18000b396  sub     rdx, rax
0x18000b399  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x18000b39d  test    rdx, rdx
0x18000b3a0  jle     short loc_18000B3AD
0x18000b3a2  lea     rcx, [rsp+0A8h+var_78]; this
0x18000b3a7  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x18000b3ac  nop
0x18000b3ad  add     rbx, 10h
0x18000b3b1  jmp     loc_18000B292
0x18000b3b6  mov     rax, [rsi+20h]
0x18000b3ba  mov     [rsi+28h], rax
0x18000b3be  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x18000b3c5  test    rax, rax
0x18000b3c8  jnz     short loc_18000B3D6
0x18000b3ca  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x18000b3d1  test    rax, rax
0x18000b3d4  jz      short loc_18000B3E9
0x18000b3d6  xor     r9d, r9d
0x18000b3d9  xor     r8d, r8d
0x18000b3dc  mov     edx, 0FEh
0x18000b3e1  xor     ecx, ecx
0x18000b3e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3e8  nop
0x18000b3e9  mov     rcx, [rsp+0A8h+var_48]
0x18000b3ee  xor     rcx, rsp; StackCookie
0x18000b3f1  call    __security_check_cookie
0x18000b3f6  add     rsp, 78h
0x18000b3fa  pop     r15
0x18000b3fc  pop     r14
0x18000b3fe  pop     rdi
0x18000b3ff  pop     rsi
0x18000b400  pop     rbp
0x18000b401  pop     rbx
0x18000b402  retn
```
