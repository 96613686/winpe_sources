# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(void)

- ea: `0x180023a74`
- end: `0x180023c40`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXXZ`
- size: `460`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x18001b2f0`
- `0x18001b430`
- `0x18001c004`
- `0x1800314a0`

## callees

- `0x180023a74`
- `0x1800260c8`
- `0x180031040`
- `0x180032010`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::details::EnabledStateManager *this)
{
  int *v1; // rsi
  int *v3; // rbx
  __int64 v4; // r9
  int v5; // r10d
  unsigned __int32 v6; // edx
  unsigned int v7; // ecx
  char *v8; // r8
  signed __int64 v9; // r8
  void (__fastcall *v10)(_QWORD, __int64, _QWORD, _QWORD); // rax
  _DWORD v11[2]; // [rsp+30h] [rbp-58h] BYREF
  char v12; // [rsp+38h] [rbp-50h] BYREF

  v1 = (int *)*((_QWORD *)this + 7);
  v3 = (int *)*((_QWORD *)this + 6);
  if ( (unsigned __int64)((char *)v1 - (char *)v3) >= 0x10 )
  {
    while ( v3 != v1 )
    {
      v4 = *((_QWORD *)v3 + 1);
      v5 = *v3;
      _m_prefetchw((const void *)v4);
      v6 = _InterlockedAnd((volatile signed __int32 *)v4, 0xFFC0401E);
      v7 = (v6 >> 1) & 0xF;
      if ( v7 )
      {
        _m_prefetchw((const void *)(v4 + 4));
        v7 &= ~_InterlockedOr((volatile signed __int32 *)(v4 + 4), v7);
      }
      v8 = (char *)v11;
      if ( (v7 & 1) != 0 )
      {
        v11[0] = v5;
        v8 = &v12;
        v11[1] = 65538;
      }
      if ( (v7 & 2) != 0 )
      {
        *(_DWORD *)v8 = v5;
        *((_DWORD *)v8 + 1) = 65542;
        v8 += 8;
      }
      if ( (v7 & 4) != 0 )
      {
        *(_DWORD *)v8 = v5;
        *((_DWORD *)v8 + 1) = 65539;
        v8 += 8;
      }
      if ( v7 >= 8 )
      {
        *(_DWORD *)v8 = v5;
        *((_DWORD *)v8 + 1) = 65543;
        v8 += 8;
      }
      if ( ((v6 >> 5) & 0x1FF) != 0 )
      {
        *(_DWORD *)v8 = v5;
        *((_WORD *)v8 + 3) = (v6 >> 5) & 0x1FF;
        *((_WORD *)v8 + 2) = 4 * ((v6 >> 14) & 1);
        v8 += 8;
      }
      if ( ((v6 >> 15) & 0x7F) != 0 )
      {
        *(_DWORD *)v8 = v5;
        *((_WORD *)v8 + 3) = (v6 >> 15) & 0x7F;
        *((_WORD *)v8 + 2) = 4 * ((v6 >> 22) & 1) + 1;
        v8 += 8;
      }
      v9 = (v8 - (char *)v11) >> 3;
      if ( v9 > 0 )
        wil::details::WilApi_RecordFeatureUsageReports(
          (wil::details *)v11,
          (struct __WIL_RTL_FEATURE_USAGE_DATA *)v9,
          v9);
      v3 += 4;
    }
    *((_QWORD *)this + 7) = *((_QWORD *)this + 6);
    v10 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v10 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v10(0, 254, 0, 0);
    }
  }
}

```

## disassembly

```asm
0x180023a74  mov     [rsp+arg_8], rbx
0x180023a79  mov     [rsp+arg_10], rbp
0x180023a7e  mov     [rsp+arg_18], rsi
0x180023a83  push    rdi
0x180023a84  push    r14
0x180023a86  push    r15
0x180023a88  sub     rsp, 70h
0x180023a8c  mov     rax, cs:__security_cookie
0x180023a93  xor     rax, rsp
0x180023a96  mov     [rsp+88h+var_28], rax
0x180023a9b  mov     rsi, [rcx+38h]
0x180023a9f  mov     rdi, rcx
0x180023aa2  mov     rbx, [rcx+30h]
0x180023aa6  mov     rax, rsi
0x180023aa9  sub     rax, rbx
0x180023aac  cmp     rax, 10h
0x180023ab0  jb      loc_180023C18
0x180023ab6  mov     ebp, 1
0x180023abb  mov     r15d, 1FFh
0x180023ac1  lea     r14d, [rbp+1]
0x180023ac5  cmp     rbx, rsi
0x180023ac8  jz      loc_180023BE6
0x180023ace  mov     r9, [rbx+8]
0x180023ad2  mov     r10d, [rbx]
0x180023ad5  prefetchw byte ptr [r9]
0x180023ad9  mov     eax, [r9]
0x180023adc  mov     ecx, eax
0x180023ade  and     ecx, 0FFC0401Eh
0x180023ae4  lock cmpxchg [r9], ecx
0x180023ae9  jnz     short loc_180023ADC
0x180023aeb  mov     ecx, eax
0x180023aed  mov     edx, eax
0x180023aef  shr     ecx, 1
0x180023af1  and     ecx, 0Fh
0x180023af4  jz      short loc_180023B11
0x180023af6  prefetchw byte ptr [r9+4]
0x180023afb  mov     eax, [r9+4]
0x180023aff  mov     r8d, eax
0x180023b02  or      r8d, ecx
0x180023b05  lock cmpxchg [r9+4], r8d
0x180023b0b  jnz     short loc_180023AFF
0x180023b0d  not     eax
0x180023b0f  and     ecx, eax
0x180023b11  lea     r8, [rsp+88h+var_58]
0x180023b16  test    bpl, cl
0x180023b19  jz      short loc_180023B2D
0x180023b1b  mov     [rsp+88h+var_58], r10d
0x180023b20  lea     r8, [rsp+88h+var_50]
0x180023b25  mov     [rsp+88h+var_54], 10002h
0x180023b2d  test    r14b, cl
0x180023b30  jz      short loc_180023B41
0x180023b32  mov     [r8], r10d
0x180023b35  mov     dword ptr [r8+4], 10006h
0x180023b3d  add     r8, 8
0x180023b41  test    cl, 4
0x180023b44  jz      short loc_180023B55
0x180023b46  mov     [r8], r10d
0x180023b49  mov     dword ptr [r8+4], 10003h
0x180023b51  add     r8, 8
0x180023b55  cmp     ecx, 8
0x180023b58  jb      short loc_180023B69
0x180023b5a  mov     [r8], r10d
0x180023b5d  mov     dword ptr [r8+4], 10007h
0x180023b65  add     r8, 8
0x180023b69  mov     ecx, edx
0x180023b6b  shr     ecx, 5
0x180023b6e  test    r15d, ecx
0x180023b71  jz      short loc_180023B94
0x180023b73  and     cx, r15w
0x180023b77  mov     [r8], r10d
0x180023b7a  mov     eax, edx
0x180023b7c  mov     [r8+6], cx
0x180023b81  shr     eax, 0Eh
0x180023b84  and     ax, bp
0x180023b87  shl     ax, 2
0x180023b8b  mov     [r8+4], ax
0x180023b90  add     r8, 8
0x180023b94  mov     eax, edx
0x180023b96  shr     eax, 0Fh
0x180023b99  test    al, 7Fh
0x180023b9b  jz      short loc_180023BBF
0x180023b9d  shr     edx, 16h
0x180023ba0  and     ax, 7Fh
0x180023ba4  and     dx, bp
0x180023ba7  mov     [r8], r10d
0x180023baa  shl     dx, 2
0x180023bae  add     dx, bp
0x180023bb1  mov     [r8+6], ax
0x180023bb6  mov     [r8+4], dx
0x180023bbb  add     r8, 8
0x180023bbf  lea     rax, [rsp+88h+var_58]
0x180023bc4  sub     r8, rax
0x180023bc7  sar     r8, 3; unsigned __int64
0x180023bcb  test    r8, r8
0x180023bce  jle     short loc_180023BDD
0x180023bd0  mov     rdx, r8; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x180023bd3  lea     rcx, [rsp+88h+var_58]; this
0x180023bd8  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x180023bdd  add     rbx, 10h
0x180023be1  jmp     loc_180023AC5
0x180023be6  mov     rax, [rdi+30h]
0x180023bea  mov     [rdi+38h], rax
0x180023bee  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x180023bf5  test    rax, rax
0x180023bf8  jnz     short loc_180023C06
0x180023bfa  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x180023c01  test    rax, rax
0x180023c04  jz      short loc_180023C18
0x180023c06  xor     r9d, r9d
0x180023c09  xor     r8d, r8d
0x180023c0c  mov     edx, 0FEh
0x180023c11  xor     ecx, ecx
0x180023c13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c18  mov     rcx, [rsp+88h+var_28]
0x180023c1d  xor     rcx, rsp; StackCookie
0x180023c20  call    __security_check_cookie
0x180023c25  lea     r11, [rsp+88h+var_18]
0x180023c2a  mov     rbx, [r11+28h]
0x180023c2e  mov     rbp, [r11+30h]
0x180023c32  mov     rsi, [r11+38h]
0x180023c36  mov     rsp, r11
0x180023c39  pop     r15
0x180023c3b  pop     r14
0x180023c3d  pop     rdi
0x180023c3e  retn
```
