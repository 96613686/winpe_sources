# CTray::_UpdateDesktopWorkAreaCache(HMONITOR__ *)

- ea: `0x140126468`
- end: `0x14012670e`
- name: `?_UpdateDesktopWorkAreaCache@CTray@@IEAAXPEAUHMONITOR__@@@Z`
- size: `678`
- prototype: `void(CTray *__hidden this, HMONITOR)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140076810`
- `0x14008e0d0`

## callees

- `0x140018864`
- `0x14002944c`
- `0x140065790`
- `0x14008d0b4`
- `0x1400b53fc`
- `0x1401040e0`
- `0x140114028`
- `0x140126468`
- `0x1401db010`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!GetMonitorInfoW` at `0x1401264c8`
- `api-ms-win-ntuser-sysparams-l1-1-0!GetMonitorInfoW` at `0x1401264c8`
- `api-ms-win-ntuser-rectangle-l1-1-0!SubtractRect` at `0x1401265a1`
- `api-ms-win-ntuser-rectangle-l1-1-0!SubtractRect` at `0x1401265a1`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x140126553`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x140126606`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x140126553`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x140126606`
- `USER32!MonitorFromWindow` at `0x140126615`
- `USER32!MonitorFromWindow` at `0x140126615`

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
      if ( (!(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_52580392>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_52580392>::GetImpl'::`2'::impl)
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
0x140126468  test    rdx, rdx
0x14012646b  jz      locret_14012670D
0x140126471  mov     rax, rsp
0x140126474  mov     [rax+18h], rbx
0x140126478  push    rbp
0x140126479  push    rsi
0x14012647a  push    rdi
0x14012647b  push    r12
0x14012647d  push    r13
0x14012647f  push    r14
0x140126481  push    r15
0x140126483  lea     rbp, [rax-5Fh]
0x140126487  sub     rsp, 0C0h
0x14012648e  movaps  xmmword ptr [rax-48h], xmm6
0x140126492  mov     rax, cs:__security_cookie
0x140126499  xor     rax, rsp
0x14012649c  mov     [rbp+57h+var_48], rax
0x1401264a0  mov     rax, rdx
0x1401264a3  mov     rdi, rcx
0x1401264a6  mov     [rbp+57h+var_B8], rdx
0x1401264aa  mov     [rbp+57h+mi.cbSize], 28h ; '('
0x1401264b1  xorps   xmm0, xmm0
0x1401264b4  xor     ecx, ecx
0x1401264b6  movups  xmmword ptr [rbp+57h+mi.rcMonitor.left], xmm0
0x1401264ba  movups  xmmword ptr [rbp+57h+mi.rcWork.left], xmm0
0x1401264be  mov     [rbp+57h+mi.dwFlags], ecx
0x1401264c1  lea     rdx, [rbp+57h+mi]; lpmi
0x1401264c5  mov     rcx, rax; hMonitor
0x1401264c8  call    cs:__imp_GetMonitorInfoW
0x1401264ce  test    eax, eax
0x1401264d0  jz      loc_1401266E2
0x1401264d6  mov     eax, [rbp+57h+mi.rcMonitor.left]
0x1401264d9  mov     [rbp+57h+rcDst.left], eax
0x1401264dc  mov     eax, [rbp+57h+mi.rcMonitor.top]
0x1401264df  mov     [rbp+57h+rcDst.top], eax
0x1401264e2  mov     eax, [rbp+57h+mi.rcMonitor.right]
0x1401264e5  mov     [rbp+57h+rcDst.right], eax
0x1401264e8  mov     eax, [rbp+57h+mi.rcMonitor.bottom]
0x1401264eb  mov     [rbp+57h+rcDst.bottom], eax
0x1401264ee  mov     rcx, [rdi+428h]
0x1401264f5  mov     rax, [rcx]
0x1401264f8  mov     rax, [rax+90h]
0x1401264ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140126504  mov     ebx, eax
0x140126506  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_52580392@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_52580392@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_52580392> `wil::Feature<__WilFeatureTraits_Feature_52580392>::GetImpl(void)'::`2'::impl
0x14012650d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_52580392@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_52580392>::__private_IsEnabled(void)
0x140126512  test    al, al
0x140126514  jz      short loc_140126523
0x140126516  call    ?IsTrayCloaked@CTray@@QEAA_NXZ; CTray::IsTrayCloaked(void)
0x14012651b  test    al, al
0x14012651d  jnz     loc_1401265A7
0x140126523  not     bl
0x140126525  test    bl, 1
0x140126528  jz      short loc_1401265A7
0x14012652a  xorps   xmm0, xmm0
0x14012652d  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x140126531  mov     rcx, [rdi+428h]
0x140126538  mov     rax, [rcx]
0x14012653b  lea     r8, [rbp+57h+rc]
0x14012653f  mov     rdx, [rbp+57h+var_B8]
0x140126543  mov     rax, [rax+88h]
0x14012654a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14012654f  lea     rcx, [rbp+57h+rc]; lprc
0x140126553  call    cs:__imp_IsRectEmpty
0x140126559  test    eax, eax
0x14012655b  jnz     short loc_1401265A7
0x14012655d  xorps   xmm0, xmm0
0x140126560  movups  [rbp+57h+var_68], xmm0
0x140126564  xorps   xmm1, xmm1
0x140126567  movups  [rbp+57h+var_58], xmm1
0x14012656b  mov     rcx, [rdi+428h]
0x140126572  mov     rax, [rcx]
0x140126575  lea     r9, [rbp+57h+var_58]
0x140126579  lea     r8, [rbp+57h+var_68]
0x14012657d  mov     rdx, [rbp+57h+var_B8]
0x140126581  mov     rax, [rax+80h]
0x140126588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14012658d  lea     rdx, [rbp+57h+rcDst]; lprcSrc1
0x140126591  lea     rcx, [rbp+57h+rcDst]; lprcDst
0x140126595  test    al, al
0x140126597  lea     r8, [rbp+57h+var_68]
0x14012659b  jnz     short loc_1401265A1
0x14012659d  lea     r8, [rbp+57h+rc]; lprcSrc2
0x1401265a1  call    cs:__imp_SubtractRect
0x1401265a7  mov     rax, [rdi+100h]
0x1401265ae  test    rax, rax
0x1401265b1  jz      loc_1401266A8
0x1401265b7  xor     r14d, r14d
0x1401265ba  xor     r15d, r15d
0x1401265bd  xor     r12d, r12d
0x1401265c0  xor     esi, esi
0x1401265c2  mov     [rbp+57h+var_C0], esi
0x1401265c5  mov     eax, [rax]
0x1401265c7  mov     [rbp+57h+rc.left], eax
0x1401265ca  xor     r13d, r13d
0x1401265cd  test    eax, eax
0x1401265cf  jle     loc_1401266A8
0x1401265d5  mov     edx, r13d; i
0x1401265d8  mov     rcx, [rdi+100h]; hdpa
0x1401265df  call    DPA_GetPtr
0x1401265e4  mov     rbx, rax
0x1401265e7  test    rax, rax
0x1401265ea  jz      loc_140126674
0x1401265f0  cmp     dword ptr [rax+28h], 0
0x1401265f4  jnz     short loc_140126674
0x1401265f6  cmp     dword ptr [rax+24h], 0
0x1401265fa  jnz     short loc_140126674
0x1401265fc  cmp     dword ptr [rax+1Ch], 0FFFFFFFFh
0x140126600  jz      short loc_140126674
0x140126602  lea     rcx, [rax+0Ch]; lprc
0x140126606  call    cs:__imp_IsRectEmpty
0x14012660c  test    eax, eax
0x14012660e  jnz     short loc_140126674
0x140126610  xor     edx, edx; dwFlags
0x140126612  mov     rcx, [rbx]; hwnd
0x140126615  call    cs:__imp_MonitorFromWindow
0x14012661b  cmp     rax, [rbp+57h+var_B8]
0x14012661f  jnz     short loc_140126674
0x140126621  mov     eax, [rbx+1Ch]
0x140126624  mov     byte ptr [rbp+rax+57h+var_C0], 1
0x140126629  test    eax, eax
0x14012662b  jz      short loc_140126667
0x14012662d  sub     eax, 1
0x140126630  jz      short loc_140126658
0x140126632  sub     eax, 1
0x140126635  jz      short loc_140126649
0x140126637  cmp     eax, 1
0x14012663a  jnz     short loc_140126674
0x14012663c  mov     eax, [rbp+57h+rcDst.bottom]
0x14012663f  sub     eax, [rbx+10h]
0x140126642  cmp     esi, eax
0x140126644  cmovle  esi, eax
0x140126647  jmp     short loc_140126674
0x140126649  mov     eax, [rbp+57h+rcDst.right]
0x14012664c  sub     eax, [rbx+0Ch]
0x14012664f  cmp     r12d, eax
0x140126652  cmovle  r12d, eax
0x140126656  jmp     short loc_140126674
0x140126658  mov     eax, [rbx+18h]
0x14012665b  sub     eax, [rbp+57h+rcDst.top]
0x14012665e  cmp     r15d, eax
0x140126661  cmovle  r15d, eax
0x140126665  jmp     short loc_140126674
0x140126667  mov     eax, [rbx+14h]
0x14012666a  sub     eax, [rbp+57h+rcDst.left]
0x14012666d  cmp     r14d, eax
0x140126670  cmovle  r14d, eax
0x140126674  inc     r13d
0x140126677  cmp     r13d, [rbp+57h+rc.left]
0x14012667b  jl      loc_1401265D5
0x140126681  cmp     byte ptr [rbp+57h+var_C0], 0
0x140126685  jz      short loc_14012668B
0x140126687  add     [rbp+57h+rcDst.left], r14d
0x14012668b  cmp     byte ptr [rbp+57h+var_C0+1], 0
0x14012668f  jz      short loc_140126695
0x140126691  add     [rbp+57h+rcDst.top], r15d
0x140126695  cmp     byte ptr [rbp+57h+var_C0+2], 0
0x140126699  jz      short loc_14012669F
0x14012669b  sub     [rbp+57h+rcDst.right], r12d
0x14012669f  cmp     byte ptr [rbp+57h+var_C0+3], 0
0x1401266a3  jz      short loc_1401266A8
0x1401266a5  sub     [rbp+57h+rcDst.bottom], esi
0x1401266a8  lea     rdx, [rdi+110h]
0x1401266af  lea     rcx, [rbp+57h+rc]
0x1401266b3  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1401266b8  nop
0x1401266b9  movups  xmm6, xmmword ptr [rbp+57h+rcDst.left]
0x1401266bd  lea     rcx, [rdi+118h]
0x1401266c4  lea     r8, [rbp+57h+var_B8]
0x1401266c8  lea     rdx, [rbp+57h+var_58]
0x1401266cc  call    ??$_Try_emplace@AEBQEAUHMONITOR__@@$$V@?$_Hash@V?$_Umap_traits@PEAUHMONITOR__@@UtagRECT@@V?$_Uhash_compare@PEAUHMONITOR__@@U?$hash@PEAUHMONITOR__@@@std@@U?$equal_to@PEAUHMONITOR__@@@3@@std@@V?$allocator@U?$pair@QEAUHMONITOR__@@UtagRECT@@@std@@@4@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_List_node@U?$pair@QEAUHMONITOR__@@UtagRECT@@@std@@PEAX@std@@_N@1@AEBQEAUHMONITOR__@@@Z; std::_Hash<std::_Umap_traits<HMONITOR__ *,tagRECT,std::_Uhash_compare<HMONITOR__ *,std::hash<HMONITOR__ *>,std::equal_to<HMONITOR__ *>>,std::allocator<std::pair<HMONITOR__ * const,tagRECT>>,0>>::_Try_emplace<HMONITOR__ * const &,>(HMONITOR__ * const &)
0x1401266d1  mov     rcx, [rax]
0x1401266d4  movdqu  xmmword ptr [rcx+18h], xmm6
0x1401266d9  lea     rcx, [rbp+57h+rc]
0x1401266dd  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x1401266e2  mov     rcx, [rbp+57h+var_48]
0x1401266e6  xor     rcx, rsp; StackCookie
0x1401266e9  call    __security_check_cookie
0x1401266ee  lea     r11, [rsp+0F0h+var_30]
0x1401266f6  mov     rbx, [r11+50h]
0x1401266fa  movaps  xmm6, xmmword ptr [r11-10h]
0x1401266ff  mov     rsp, r11
0x140126702  pop     r15
0x140126704  pop     r14
0x140126706  pop     r13
0x140126708  pop     r12
0x14012670a  pop     rdi
0x14012670b  pop     rsi
0x14012670c  pop     rbp
0x14012670d  retn
```
