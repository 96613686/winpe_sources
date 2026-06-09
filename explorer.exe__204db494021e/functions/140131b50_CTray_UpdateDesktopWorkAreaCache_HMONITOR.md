# CTray::_UpdateDesktopWorkAreaCache(HMONITOR__ *)

- ea: `0x140131b50`
- end: `0x140131e21`
- name: `?_UpdateDesktopWorkAreaCache@CTray@@IEAAXPEAUHMONITOR__@@@Z`
- size: `721`
- prototype: `void(CTray *__hidden this, HMONITOR)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14007b920`
- `0x1400937f0`

## callees

- `0x140007ec0`
- `0x1400335d0`
- `0x140068120`
- `0x1400923f0`
- `0x1400bb4e0`
- `0x14010e160`
- `0x14011e904`
- `0x140131b50`
- `0x1401d9010`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!GetMonitorInfoW` at `0x140131bb0`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetMonitorInfoW` at `0x140131bb0`
- `api-ms-win-ntuser-rectangle-l1-1-0!SubtractRect` at `0x140131c99`
- `api-ms-win-ntuser-rectangle-l1-1-0!SubtractRect` at `0x140131c99`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x140131c45`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x140131d0c`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x140131c45`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x140131d0c`
- `USER32!MonitorFromWindow` at `0x140131d21`
- `USER32!MonitorFromWindow` at `0x140131d21`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CTray::_UpdateDesktopWorkAreaCache(CTray *this, HMONITOR a2)
{
  char v3; // bl
  CTray *v4; // rcx
  char v5; // al
  RECT *p_rc; // r8
  LONG *v7; // rax
  int v8; // r14d
  int v9; // r15d
  int v10; // r12d
  int v11; // esi
  LONG v12; // r13d
  char *Ptr; // rax
  char *v14; // rbx
  HMONITOR v15; // rax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  struct tagRECT v19; // xmm6
  _DWORD v20[2]; // [rsp+30h] [rbp-69h]
  HMONITOR v21; // [rsp+38h] [rbp-61h] BYREF
  struct tagRECT rcDst; // [rsp+40h] [rbp-59h] BYREF
  RECT rc; // [rsp+50h] [rbp-49h] BYREF
  struct tagMONITORINFO mi; // [rsp+60h] [rbp-39h] BYREF
  __int128 v25; // [rsp+88h] [rbp-11h] BYREF
  __int128 v26; // [rsp+98h] [rbp-1h] BYREF

  if ( a2 )
  {
    v21 = a2;
    mi.cbSize = 40;
    memset(&mi.rcMonitor, 0, 36);
    if ( GetMonitorInfoW(a2, &mi) )
    {
      rcDst = mi.rcMonitor;
      v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 133) + 144LL))(*((_QWORD *)this + 133));
      if ( (!(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_52580392>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_52580392>::GetImpl'::`2'::impl)
         || !CTray::IsTrayCloaked(v4))
        && (v3 & 1) == 0 )
      {
        rc = 0;
        (*(void (__fastcall **)(_QWORD, HMONITOR, RECT *))(**((_QWORD **)this + 133) + 136LL))(
          *((_QWORD *)this + 133),
          v21,
          &rc);
        if ( !IsRectEmpty(&rc) )
        {
          v25 = 0;
          v26 = 0;
          v5 = (*(__int64 (__fastcall **)(_QWORD, HMONITOR, __int128 *, __int128 *))(**((_QWORD **)this + 133) + 128LL))(
                 *((_QWORD *)this + 133),
                 v21,
                 &v25,
                 &v26);
          p_rc = (RECT *)&v25;
          if ( !v5 )
            p_rc = &rc;
          SubtractRect(&rcDst, &rcDst, p_rc);
        }
      }
      v7 = (LONG *)*((_QWORD *)this + 32);
      if ( v7 )
      {
        v8 = 0;
        v9 = 0;
        v10 = 0;
        v11 = 0;
        v20[0] = 0;
        rc.left = *v7;
        v12 = 0;
        if ( rc.left > 0 )
        {
          do
          {
            Ptr = (char *)DPA_GetPtr(*((HDPA *)this + 32), (unsigned int)v12);
            v14 = Ptr;
            if ( Ptr )
            {
              if ( !*((_DWORD *)Ptr + 10)
                && !*((_DWORD *)Ptr + 9)
                && *((_DWORD *)Ptr + 7) != -1
                && !IsRectEmpty((const RECT *)(Ptr + 12)) )
              {
                v15 = MonitorFromWindow(*(HWND *)v14, 0);
                if ( v15 == v21 )
                {
                  v16 = *((_DWORD *)v14 + 7);
                  *((_BYTE *)v20 + v16) = 1;
                  if ( v16 )
                  {
                    v17 = v16 - 1;
                    if ( v17 )
                    {
                      v18 = v17 - 1;
                      if ( v18 )
                      {
                        if ( v18 == 1 && v11 <= rcDst.bottom - *((_DWORD *)v14 + 4) )
                          v11 = rcDst.bottom - *((_DWORD *)v14 + 4);
                      }
                      else if ( v10 <= rcDst.right - *((_DWORD *)v14 + 3) )
                      {
                        v10 = rcDst.right - *((_DWORD *)v14 + 3);
                      }
                    }
                    else if ( v9 <= *((_DWORD *)v14 + 6) - rcDst.top )
                    {
                      v9 = *((_DWORD *)v14 + 6) - rcDst.top;
                    }
                  }
                  else if ( v8 <= *((_DWORD *)v14 + 5) - rcDst.left )
                  {
                    v8 = *((_DWORD *)v14 + 5) - rcDst.left;
                  }
                }
              }
            }
            ++v12;
          }
          while ( v12 < rc.left );
          if ( LOBYTE(v20[0]) )
            rcDst.left += v8;
          if ( BYTE1(v20[0]) )
            rcDst.top += v9;
          if ( BYTE2(v20[0]) )
            rcDst.right -= v10;
          if ( HIBYTE(v20[0]) )
            rcDst.bottom -= v11;
        }
      }
      wil::AcquireSRWLockExclusive(&rc, (char *)this + 272);
      v19 = rcDst;
      *(struct tagRECT *)(*(_QWORD *)std::_Hash<std::_Umap_traits<HMONITOR__ *,tagRECT,std::_Uhash_compare<HMONITOR__ *,std::hash<HMONITOR__ *>,std::equal_to<HMONITOR__ *>>,std::allocator<std::pair<HMONITOR__ * const,tagRECT>>,0>>::_Try_emplace<HMONITOR__ * const &,>(
                                       (char *)this + 280,
                                       &v26,
                                       &v21)
                        + 24LL) = v19;
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&rc);
    }
  }
}

```

## disassembly

```asm
0x140131b50  test    rdx, rdx
0x140131b53  jz      locret_140131E1F
0x140131b59  mov     rax, rsp
0x140131b5c  mov     [rax+18h], rbx
0x140131b60  push    rbp
0x140131b61  push    rsi
0x140131b62  push    rdi
0x140131b63  push    r12
0x140131b65  push    r13
0x140131b67  push    r14
0x140131b69  push    r15
0x140131b6b  lea     rbp, [rax-5Fh]
0x140131b6f  sub     rsp, 0C0h
0x140131b76  movaps  xmmword ptr [rax-48h], xmm6
0x140131b7a  mov     rax, cs:__security_cookie
0x140131b81  xor     rax, rsp
0x140131b84  mov     [rbp+57h+var_48], rax
0x140131b88  mov     rax, rdx
0x140131b8b  mov     rdi, rcx
0x140131b8e  mov     [rbp+57h+var_B8], rdx
0x140131b92  mov     [rbp+57h+mi.cbSize], 28h ; '('
0x140131b99  xorps   xmm0, xmm0
0x140131b9c  xor     ecx, ecx
0x140131b9e  movups  xmmword ptr [rbp+57h+mi.rcMonitor.left], xmm0
0x140131ba2  movups  xmmword ptr [rbp+57h+mi.rcWork.left], xmm0
0x140131ba6  mov     [rbp+57h+mi.dwFlags], ecx
0x140131ba9  lea     rdx, [rbp+57h+mi]; lpmi
0x140131bad  mov     rcx, rax; hMonitor
0x140131bb0  call    cs:__imp_GetMonitorInfoW
0x140131bb7  nop     dword ptr [rax+rax+00h]
0x140131bbc  test    eax, eax
0x140131bbe  jz      loc_140131DF4
0x140131bc4  mov     eax, [rbp+57h+mi.rcMonitor.left]
0x140131bc7  mov     [rbp+57h+rcDst.left], eax
0x140131bca  mov     eax, [rbp+57h+mi.rcMonitor.top]
0x140131bcd  mov     [rbp+57h+rcDst.top], eax
0x140131bd0  mov     eax, [rbp+57h+mi.rcMonitor.right]
0x140131bd3  mov     [rbp+57h+rcDst.right], eax
0x140131bd6  mov     eax, [rbp+57h+mi.rcMonitor.bottom]
0x140131bd9  mov     [rbp+57h+rcDst.bottom], eax
0x140131bdc  mov     rcx, [rdi+428h]
0x140131be3  mov     rax, [rcx]
0x140131be6  mov     rax, [rax+90h]
0x140131bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140131bf2  mov     ebx, eax
0x140131bf4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_52580392@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_52580392@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_52580392> `wil::Feature<__WilFeatureTraits_Feature_52580392>::GetImpl(void)'::`2'::impl
0x140131bfb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_52580392@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_52580392>::__private_IsEnabled(void)
0x140131c00  test    al, al
0x140131c02  jz      short loc_140131C11
0x140131c04  call    ?IsTrayCloaked@CTray@@QEAA_NXZ; CTray::IsTrayCloaked(void)
0x140131c09  test    al, al
0x140131c0b  jnz     loc_140131CA5
0x140131c11  not     bl
0x140131c13  test    bl, 1
0x140131c16  jz      loc_140131CA5
0x140131c1c  xorps   xmm0, xmm0
0x140131c1f  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x140131c23  mov     rcx, [rdi+428h]
0x140131c2a  mov     rax, [rcx]
0x140131c2d  lea     r8, [rbp+57h+rc]
0x140131c31  mov     rdx, [rbp+57h+var_B8]
0x140131c35  mov     rax, [rax+88h]
0x140131c3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140131c41  lea     rcx, [rbp+57h+rc]; lprc
0x140131c45  call    cs:__imp_IsRectEmpty
0x140131c4c  nop     dword ptr [rax+rax+00h]
0x140131c51  test    eax, eax
0x140131c53  jnz     short loc_140131CA5
0x140131c55  xorps   xmm0, xmm0
0x140131c58  movups  [rbp+57h+var_68], xmm0
0x140131c5c  xorps   xmm1, xmm1
0x140131c5f  movups  [rbp+57h+var_58], xmm1
0x140131c63  mov     rcx, [rdi+428h]
0x140131c6a  mov     rax, [rcx]
0x140131c6d  lea     r9, [rbp+57h+var_58]
0x140131c71  lea     r8, [rbp+57h+var_68]
0x140131c75  mov     rdx, [rbp+57h+var_B8]
0x140131c79  mov     rax, [rax+80h]
0x140131c80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140131c85  lea     rdx, [rbp+57h+rcDst]; lprcSrc1
0x140131c89  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x140131c8d  test    al, al
0x140131c8f  lea     r8, [rbp+57h+var_68]
0x140131c93  jnz     short loc_140131C99
0x140131c95  lea     r8, [rbp+57h+rc]; lprcSrc2
0x140131c99  call    cs:__imp_SubtractRect
0x140131ca0  nop     dword ptr [rax+rax+00h]
0x140131ca5  mov     rax, [rdi+100h]
0x140131cac  test    rax, rax
0x140131caf  jz      loc_140131DBA
0x140131cb5  xor     r14d, r14d
0x140131cb8  xor     r15d, r15d
0x140131cbb  xor     r12d, r12d
0x140131cbe  xor     esi, esi
0x140131cc0  mov     [rbp+57h+var_C0], esi
0x140131cc3  mov     eax, [rax]
0x140131cc5  mov     [rbp+57h+rc.left], eax
0x140131cc8  xor     r13d, r13d
0x140131ccb  test    eax, eax
0x140131ccd  jle     loc_140131DBA
0x140131cd3  mov     edx, r13d; i
0x140131cd6  mov     rcx, [rdi+100h]; hdpa
0x140131cdd  call    DPA_GetPtr
0x140131ce2  mov     rbx, rax
0x140131ce5  test    rax, rax
0x140131ce8  jz      loc_140131D86
0x140131cee  cmp     dword ptr [rax+28h], 0
0x140131cf2  jnz     loc_140131D86
0x140131cf8  cmp     dword ptr [rax+24h], 0
0x140131cfc  jnz     loc_140131D86
0x140131d02  cmp     dword ptr [rax+1Ch], 0FFFFFFFFh
0x140131d06  jz      short loc_140131D86
0x140131d08  lea     rcx, [rax+0Ch]; lprc
0x140131d0c  call    cs:__imp_IsRectEmpty
0x140131d13  nop     dword ptr [rax+rax+00h]
0x140131d18  test    eax, eax
0x140131d1a  jnz     short loc_140131D86
0x140131d1c  xor     edx, edx; dwFlags
0x140131d1e  mov     rcx, [rbx]; hwnd
0x140131d21  call    cs:__imp_MonitorFromWindow
0x140131d28  nop     dword ptr [rax+rax+00h]
0x140131d2d  cmp     rax, [rbp+57h+var_B8]
0x140131d31  jnz     short loc_140131D86
0x140131d33  mov     eax, [rbx+1Ch]
0x140131d36  mov     byte ptr [rbp+rax+57h+var_C0], 1
0x140131d3b  test    eax, eax
0x140131d3d  jz      short loc_140131D79
0x140131d3f  sub     eax, 1
0x140131d42  jz      short loc_140131D6A
0x140131d44  sub     eax, 1
0x140131d47  jz      short loc_140131D5B
0x140131d49  cmp     eax, 1
0x140131d4c  jnz     short loc_140131D86
0x140131d4e  mov     eax, [rbp+57h+rcDst.bottom]
0x140131d51  sub     eax, [rbx+10h]
0x140131d54  cmp     esi, eax
0x140131d56  cmovle  esi, eax
0x140131d59  jmp     short loc_140131D86
0x140131d5b  mov     eax, [rbp+57h+rcDst.right]
0x140131d5e  sub     eax, [rbx+0Ch]
0x140131d61  cmp     r12d, eax
0x140131d64  cmovle  r12d, eax
0x140131d68  jmp     short loc_140131D86
0x140131d6a  mov     eax, [rbx+18h]
0x140131d6d  sub     eax, [rbp+57h+rcDst.top]
0x140131d70  cmp     r15d, eax
0x140131d73  cmovle  r15d, eax
0x140131d77  jmp     short loc_140131D86
0x140131d79  mov     eax, [rbx+14h]
0x140131d7c  sub     eax, [rbp+57h+rcDst.left]
0x140131d7f  cmp     r14d, eax
0x140131d82  cmovle  r14d, eax
0x140131d86  inc     r13d
0x140131d89  cmp     r13d, [rbp+57h+rc.left]
0x140131d8d  jl      loc_140131CD3
0x140131d93  cmp     byte ptr [rbp+57h+var_C0], 0
0x140131d97  jz      short loc_140131D9D
0x140131d99  add     [rbp+57h+rcDst.left], r14d
0x140131d9d  cmp     byte ptr [rbp+57h+var_C0+1], 0
0x140131da1  jz      short loc_140131DA7
0x140131da3  add     [rbp+57h+rcDst.top], r15d
0x140131da7  cmp     byte ptr [rbp+57h+var_C0+2], 0
0x140131dab  jz      short loc_140131DB1
0x140131dad  sub     [rbp+57h+rcDst.right], r12d
0x140131db1  cmp     byte ptr [rbp+57h+var_C0+3], 0
0x140131db5  jz      short loc_140131DBA
0x140131db7  sub     [rbp+57h+rcDst.bottom], esi
0x140131dba  lea     rdx, [rdi+110h]
0x140131dc1  lea     rcx, [rbp+57h+rc]
0x140131dc5  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x140131dca  nop
0x140131dcb  movups  xmm6, xmmword ptr [rbp+57h+rcDst.left]
0x140131dcf  lea     rcx, [rdi+118h]
0x140131dd6  lea     r8, [rbp+57h+var_B8]
0x140131dda  lea     rdx, [rbp+57h+var_58]
0x140131dde  call    ??$_Try_emplace@AEBQEAUHMONITOR__@@$$V@?$_Hash@V?$_Umap_traits@PEAUHMONITOR__@@UtagRECT@@V?$_Uhash_compare@PEAUHMONITOR__@@U?$hash@PEAUHMONITOR__@@@std@@U?$equal_to@PEAUHMONITOR__@@@3@@std@@V?$allocator@U?$pair@QEAUHMONITOR__@@UtagRECT@@@std@@@4@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@QEAUHMONITOR__@@UtagRECT@@@std@@PEAX@std@@_N@1@AEBQEAUHMONITOR__@@@Z; std::_Hash<std::_Umap_traits<HMONITOR__ *,tagRECT,std::_Uhash_compare<HMONITOR__ *,std::hash<HMONITOR__ *>,std::equal_to<HMONITOR__ *>>,std::allocator<std::pair<HMONITOR__ * const,tagRECT>>,0>>::_Try_emplace<HMONITOR__ * const &,>(HMONITOR__ * const &)
0x140131de3  mov     rcx, [rax]
0x140131de6  movdqu  xmmword ptr [rcx+18h], xmm6
0x140131deb  lea     rcx, [rbp+57h+rc]
0x140131def  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x140131df4  mov     rcx, [rbp+57h+var_48]
0x140131df8  xor     rcx, rsp; StackCookie
0x140131dfb  call    __security_check_cookie
0x140131e00  lea     r11, [rsp+0F0h+var_30]
0x140131e08  mov     rbx, [r11+50h]
0x140131e0c  movaps  xmm6, xmmword ptr [r11-10h]
0x140131e11  mov     rsp, r11
0x140131e14  pop     r15
0x140131e16  pop     r14
0x140131e18  pop     r13
0x140131e1a  pop     r12
0x140131e1c  pop     rdi
0x140131e1d  pop     rsi
0x140131e1e  pop     rbp
0x140131e1f  retn
```
