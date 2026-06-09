# _GetMsgHook(tagSYSTHREAD *,unsigned __int64,__int64)

- ea: `0x1800a60a4`
- end: `0x1800a6841`
- name: `?_GetMsgHook@@YAHPEAUtagSYSTHREAD@@_K_J@Z`
- size: `1949`
- prototype: `__int64 __fastcall(struct tagSYSTHREAD *this, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `28`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180080540`

## callees

- `0x180007bc8`
- `0x18000a220`
- `0x18000a368`
- `0x18000b750`
- `0x18001e9f0`
- `0x18002b3a8`
- `0x180039200`
- `0x18003f9b4`
- `0x18003fa4c`
- `0x18004edc0`
- `0x180057444`
- `0x18006e1b8`
- `0x18007e8e0`
- `0x18007f4e8`
- `0x1800831b8`
- `0x18008bd40`
- `0x18009eaea`
- `0x1800a60a4`
- `0x1800a6848`
- `0x1800a6944`
- `0x1800ac498`
- `0x1800b417c`
- `0x1800b5dac`
- `0x1800b5e5c`
- `0x1800b5f58`
- `0x1800b7320`
- `0x180106a60`
- `0x18010a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a60fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a60fa`
- `USER32!SendMessageW` at `0x1800a65cb`
- `USER32!SendMessageW` at `0x1800a65cb`
- `USER32!ActivateKeyboardLayout` at `0x1800a6694`
- `USER32!ActivateKeyboardLayout` at `0x1800a6694`
- `USER32!GetPointerInfo` at `0x1800a67b7`
- `USER32!GetPointerInfo` at `0x1800a67b7`
- `USER32!GetPointerTouchInfo` at `0x1800a67af`
- `USER32!GetPointerTouchInfo` at `0x1800a67af`
- `USER32!GetPointerPenInfo` at `0x1800a6799`
- `USER32!GetPointerPenInfo` at `0x1800a6799`
- `USER32!GetPointerType` at `0x1800a6781`
- `USER32!GetPointerType` at `0x1800a6781`
- `USER32!GetFocus` at `0x1800a63ce`
- `USER32!GetFocus` at `0x1800a63ce`
- `USER32!IsWindow` at `0x1800a64d2`
- `USER32!IsWindow` at `0x1800a64d2`
- `USER32!PostThreadMessageW` at `0x1800a610b`
- `USER32!PostThreadMessageW` at `0x1800a610b`
- `IMM32!ImmSetConversionStatus` at `0x1800a6481`
- `IMM32!ImmSetConversionStatus` at `0x1800a6481`
- `IMM32!ImmGetConversionStatus` at `0x1800a6451`
- `IMM32!ImmGetConversionStatus` at `0x1800a6451`
- `IMM32!ImmSetOpenStatus` at `0x1800a641d`
- `IMM32!ImmSetOpenStatus` at `0x1800a641d`

## pseudocode

```c
__int64 __fastcall _GetMsgHook(struct tagSYSTHREAD *this, __int64 a2, __int64 *a3)
{
  unsigned int v3; // esi
  __int64 *v4; // rdi
  struct tagSYSTHREAD *SYSTHREAD; // rbx
  unsigned int v6; // r12d
  UINT v7; // ebx
  DWORD CurrentThreadId; // eax
  struct IInputContextPrivate *TopInputContext; // rax
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  CCompartmentMgr *v17; // rcx
  CInputProfileManager *v18; // rcx
  CInputProfileManager *v19; // rcx
  __int64 v20; // rbx
  __int64 v21; // rbx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  __int64 v26; // rcx
  CTipProxy *v27; // rcx
  __int64 v28; // rdx
  CTipProxy *v29; // rcx
  CInputProfileManager *v30; // rcx
  HWND Focus; // rax
  HIMC v32; // r14
  unsigned __int16 v33; // si
  unsigned int v34; // edx
  DWORD v35; // edx
  unsigned int v36; // ecx
  unsigned int v37; // ecx
  unsigned int v38; // ecx
  LPARAM v39; // rax
  CInputProfileManager *Instance; // rbx
  CInputProfileManager *v41; // rax
  unsigned int v42; // ecx
  unsigned int v43; // ecx
  unsigned int v44; // ecx
  unsigned int v45; // ecx
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rcx
  HKL v49; // rcx
  __int64 v50; // rcx
  unsigned int v51; // r14d
  int v52; // r8d
  int v53; // edx
  char *v54; // rcx
  __int64 v55; // rdx
  DWORD fdwSentence; // [rsp+30h] [rbp-A9h] BYREF
  DWORD fdwConversion; // [rsp+34h] [rbp-A5h] BYREF
  __int64 v58; // [rsp+38h] [rbp-A1h] BYREF
  int v59; // [rsp+40h] [rbp-99h]
  __int64 v60; // [rsp+50h] [rbp-89h] BYREF
  HIMC v61; // [rsp+58h] [rbp-81h]
  _BYTE v62[4]; // [rsp+60h] [rbp-79h] BYREF
  int v63; // [rsp+64h] [rbp-75h]
  struct _GUID v64; // [rsp+68h] [rbp-71h] BYREF
  struct _GUID v65; // [rsp+78h] [rbp-61h] BYREF
  char v66; // [rsp+88h] [rbp-51h] BYREF

  v3 = *((_DWORD *)a3 + 2);
  v4 = a3;
  SYSTHREAD = this;
  v6 = 0;
  if ( ((v3 - 578) & 0xFFFFFFFA) == 0 )
  {
    if ( this )
    {
      v51 = *((unsigned __int16 *)a3 + 8);
      fdwSentence = 0;
      memset_0(v62, 0, 0x90u);
      if ( (unsigned int)GetPointerType(v51, &fdwSentence) )
      {
        if ( fdwSentence == 3 )
        {
          GetPointerPenInfo(v51, v62);
        }
        else if ( fdwSentence == 2 )
        {
          GetPointerTouchInfo(v51, v62);
        }
        else
        {
          GetPointerInfo(v51, v62);
        }
      }
      v52 = *((__int16 *)v4 + 13);
      v53 = *((__int16 *)v4 + 12);
      v58 = 0;
      v59 = 0;
      _PointerInfoToInputModality((struct tagPOINTER_INFO_UNION *)v62, v53, v52, (struct InputModalityInfo *)&v58);
      v54 = &v66;
      if ( !v63 )
        v54 = 0;
      v55 = *v4;
      v60 = v58;
      LODWORD(v61) = v59;
      _OnPointerInput(SYSTHREAD, v55, v3, &v60, v54);
    }
    return v6;
  }
  if ( v3 == 80 )
  {
    v7 = g_msgPrivate;
    CurrentThreadId = GetCurrentThreadId();
    PostThreadMessageW(CurrentThreadId, v7, 0xFu, 0);
    return v6;
  }
  if ( v3 != 258 )
  {
    if ( v3 != g_msgPrivate )
    {
      if ( v3 == g_msgLBarModal )
      {
        CLangBarMgr::StaticOnLanguageBarEvent(2, *((_DWORD *)a3 + 4), a3[3]);
      }
      else if ( v3 == 537 || v3 == 568 )
      {
        LOBYTE(a3) = 3;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_MTestAbSh1>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_MTestAbSh1>::GetImpl'::`2'::impl,
          1,
          a3);
        if ( SYSTHREAD )
        {
          v50 = *((_QWORD *)SYSTHREAD + 31);
          if ( v50 )
            (*(void (__fastcall **)(__int64, _QWORD, __int64, __int64))(*(_QWORD *)v50 + 80LL))(v50, v3, v4[2], v4[3]);
        }
      }
      else if ( v3 == 842 )
      {
        LOBYTE(a3) = 3;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_MTestAbSh1>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_MTestAbSh1>::GetImpl'::`2'::impl,
          1,
          a3);
        if ( SYSTHREAD )
          return (unsigned int)tagSYSTHREAD::OnShellHandwriting(SYSTHREAD, *((_DWORD *)v4 + 4), v4[3]);
      }
      return v6;
    }
    if ( !this )
    {
      SYSTHREAD = GetSYSTHREAD();
      if ( !SYSTHREAD )
        return 1;
    }
    v11 = *((unsigned __int16 *)v4 + 8);
    if ( v11 <= 0x13 )
    {
      if ( v11 == 19 )
      {
        Focus = GetFocus();
        CImmContext::CImmContext((CImmContext *)&v60, Focus);
        v32 = v61;
        if ( v61 )
        {
          v33 = *((_WORD *)v4 + 9);
          *((_DWORD *)SYSTHREAD + 48) &= ~0x400u;
          *((_DWORD *)SYSTHREAD + 48) |= 32 * (v33 & 0x20);
          if ( (v33 & 3) != 0 )
          {
            v34 = v33;
            LOWORD(v34) = ~v33;
            ImmSetOpenStatus(v32, (v34 >> 1) & 1);
          }
          if ( (v33 & 0xC) != 0 )
          {
            fdwConversion = 0;
            fdwSentence = 0;
            if ( (v33 & 4) != 0 && (v33 & 8) != 0
              || (ImmGetConversionStatus(v32, &fdwConversion, &fdwSentence), (v33 & 4) != 0) )
            {
              v35 = *((unsigned __int16 *)v4 + 12);
              fdwConversion = v35;
            }
            else
            {
              v35 = fdwConversion;
            }
            if ( (v33 & 8) != 0 )
              fdwSentence = *((unsigned __int16 *)v4 + 13);
            ImmSetConversionStatus(v32, v35, fdwSentence);
          }
          *((_DWORD *)SYSTHREAD + 48) &= ~0x400u;
        }
        CImmContext::~CImmContext((CImmContext *)&v60);
        return v6;
      }
      if ( v11 <= 0xA )
      {
        if ( v11 == 10 )
        {
          v20 = *((_QWORD *)SYSTHREAD + 8);
          if ( v20 )
          {
            memset_0(v62, 0, 0x58u);
            v21 = *(_QWORD *)(v20 + 96);
            if ( v21 )
            {
              if ( (*(int (__fastcall **)(__int64, _QWORD, _BYTE *))(*(_QWORD *)v21 + 32LL))(
                     v21,
                     *((unsigned int *)v4 + 6),
                     v62) >= 0 )
                (*(void (__fastcall **)(__int64, struct _GUID *))(*(_QWORD *)v21 + 56LL))(v21, &v64);
            }
          }
        }
        else
        {
          v12 = v11 - 4;
          if ( v12 )
          {
            v13 = v12 - 1;
            if ( v13 )
            {
              v14 = v13 - 1;
              if ( v14 )
              {
                v15 = v14 - 1;
                if ( v15 )
                {
                  v16 = v15 - 1;
                  if ( v16 )
                  {
                    if ( v16 == 1 && *((_DWORD *)SYSTHREAD + 31) == *((_DWORD *)v4 + 6) )
                      *(_QWORD *)((char *)SYSTHREAD + 124) = 0;
                  }
                  else
                  {
                    *(_QWORD *)((char *)SYSTHREAD + 124) = *((unsigned int *)v4 + 6);
                  }
                }
                else
                {
                  v17 = (CCompartmentMgr *)*((_QWORD *)SYSTHREAD + 9);
                  if ( v17 )
                    CCompartmentMgr::NotifyGlobalCompartmentChange(v17, *((_DWORD *)v4 + 6));
                }
              }
              else
              {
                v18 = (CInputProfileManager *)*((_QWORD *)SYSTHREAD + 4);
                if ( v18 )
                  CInputProfileManager::ActivateNextKeyboardProfile(v18, *((_DWORD *)v4 + 6) == 0);
              }
            }
            else
            {
              v19 = (CInputProfileManager *)*((_QWORD *)SYSTHREAD + 4);
              if ( v19 )
                CInputProfileManager::ActivateNextLanguage(v19, *((_DWORD *)v4 + 6) == 0);
            }
          }
          else if ( *(_QWORD *)SYSTHREAD )
          {
            CThreadInputMgr::UpdateDispAttr(*(CThreadInputMgr **)SYSTHREAD);
          }
        }
        return v6;
      }
      v22 = v11 - 12;
      if ( !v22 )
      {
        v30 = (CInputProfileManager *)*((_QWORD *)SYSTHREAD + 4);
        if ( v30 )
          CInputProfileManager::OnLocalProfileChange(v30);
        return v6;
      }
      v23 = v22 - 1;
      if ( !v23 )
      {
        v29 = (CTipProxy *)*((_QWORD *)SYSTHREAD + 10);
        if ( v29 && *((_DWORD *)v29 + 51) == *((_DWORD *)v4 + 6) )
          CTipProxy::CloseUI(v29, 0);
        return v6;
      }
      v24 = v23 - 1;
      if ( !v24 )
      {
        v27 = (CTipProxy *)*((_QWORD *)SYSTHREAD + 10);
        if ( v27 )
        {
          v28 = *((_QWORD *)v27 + 23);
          if ( v28 )
          {
            if ( *(_DWORD *)(v28 + 124) == *((_DWORD *)v4 + 6) )
              CTipProxy::SendFocusEvent(v27);
          }
        }
        return v6;
      }
      v25 = v24 - 1;
      if ( v25 )
      {
        if ( v25 == 1 )
        {
          *((_DWORD *)SYSTHREAD + 48) &= ~0x80u;
          if ( *(_QWORD *)SYSTHREAD )
            CThreadInputMgr::OnPostponedLockRequest(*(CThreadInputMgr **)SYSTHREAD, 0, 1);
        }
        return v6;
      }
      v26 = 1;
      goto LABEL_112;
    }
    if ( v11 > 0x1B )
    {
      v42 = v11 - 28;
      if ( v42 )
      {
        v43 = v42 - 1;
        if ( v43 )
        {
          v44 = v43 - 1;
          if ( v44 )
          {
            v45 = v44 - 1;
            if ( v45 )
            {
              if ( v45 == 1 )
              {
                *((_DWORD *)SYSTHREAD + 31) = *((_DWORD *)v4 + 6);
                *((_DWORD *)SYSTHREAD + 32) = 1;
              }
            }
            else
            {
              OnTextInputClientWrapperReleased();
            }
          }
          else
          {
            v46 = *((_QWORD *)SYSTHREAD + 12);
            if ( v46 )
              (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v46 + 88LL))(v46, *((unsigned int *)v4 + 6));
          }
        }
        else
        {
          v47 = *((_QWORD *)SYSTHREAD + 8);
          if ( v47 )
          {
            v48 = *(_QWORD *)(v47 + 96);
            if ( v48 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 64LL))(v48);
          }
        }
        return v6;
      }
      v49 = (HKL)*((_QWORD *)SYSTHREAD + 19);
      if ( !v49 || !(unsigned int)CanActivateKeyboardLayout(v49) || (*((_BYTE *)SYSTHREAD + 192) & 8) != 0 )
        return v6;
      v26 = *((_QWORD *)SYSTHREAD + 19);
      *((_QWORD *)SYSTHREAD + 19) = 0;
LABEL_112:
      ActivateKeyboardLayout((HKL)v26, 0);
      return v6;
    }
    if ( v11 != 27 )
    {
      v36 = v11 - 20;
      if ( v36 )
      {
        v37 = v36 - 1;
        if ( v37 )
        {
          v38 = v37 - 1;
          if ( v38 )
          {
            if ( v38 - 3 > 1 )
              return v6;
            goto LABEL_82;
          }
          Instance = CInputProfileManager::CreateInstance();
          memset_0(v62, 0, 0x58u);
          if ( !Instance )
            return v6;
          if ( (*(int (__fastcall **)(CInputProfileManager *, _QWORD, _BYTE *))(*(_QWORD *)Instance + 24LL))(
                 Instance,
                 *((unsigned int *)v4 + 6),
                 v62) >= 0 )
            CInputProfileManager::ActivateProfile(Instance, v63, &v64, &v65, 0, 1);
        }
        else
        {
          Instance = CInputProfileManager::CreateInstance();
          if ( !Instance )
            return v6;
          CInputProfileManager::ActivateProfile(
            Instance,
            *((_DWORD *)v4 + 6),
            &GUID_NULL,
            &GUID_NULL,
            (HKL)*((int *)v4 + 6),
            1);
        }
      }
      else
      {
        v41 = CInputProfileManager::CreateInstance();
        Instance = v41;
        if ( !v41 )
          return v6;
        CInputProfileManager::ActivateLanguage(v41, *((_WORD *)v4 + 12));
      }
      CInputProfileManager::Release(Instance);
      return v6;
    }
LABEL_82:
    if ( IsWindow((HWND)v4[3]) )
    {
      if ( v4[2] == 25 )
      {
        v39 = 1;
      }
      else
      {
        v39 = 0;
        if ( v4[2] == 27 )
          v39 = 2;
      }
      SendMessageW((HWND)v4[3], 0x505u, 0, v39);
    }
    return v6;
  }
  if ( !IsInputServiceEnabled() )
  {
    if ( (g_uModifiers & 0x49) == 0 || (g_uModifiers & 0x92) == 0 )
    {
      if ( (g_uModifiers & 0x92) != 0 )
      {
        if ( *((_WORD *)v4 + 8) < 0x20u )
          return v6;
      }
      else if ( (g_uModifiers & 0x49) != 0 )
      {
        return v6;
      }
    }
    if ( SYSTHREAD && *(_QWORD *)SYSTHREAD )
    {
      TopInputContext = CThreadInputMgr::GetTopInputContext(*(CThreadInputMgr **)SYSTHREAD);
      if ( TopInputContext )
        LOBYTE(v6) = (*(unsigned __int8 (__fastcall **)(struct IInputContextPrivate *, __int64, __int64))(*(_QWORD *)TopInputContext + 368LL))(
                       TopInputContext,
                       v4[2],
                       v4[3]) != 0;
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1800a60a4  mov     [rsp-8+arg_8], rbx
0x1800a60a9  push    rbp
0x1800a60aa  push    rsi
0x1800a60ab  push    rdi
0x1800a60ac  push    r12
0x1800a60ae  push    r13
0x1800a60b0  push    r14
0x1800a60b2  push    r15
0x1800a60b4  lea     rbp, [rsp-27h]
0x1800a60b9  sub     rsp, 100h
0x1800a60c0  mov     rax, cs:__security_cookie
0x1800a60c7  xor     rax, rsp
0x1800a60ca  mov     [rbp+57h+var_40], rax
0x1800a60ce  mov     esi, [r8+8]
0x1800a60d2  xor     r13d, r13d
0x1800a60d5  mov     rdi, r8
0x1800a60d8  mov     rbx, rcx
0x1800a60db  mov     r12d, r13d
0x1800a60de  lea     eax, [rsi-242h]
0x1800a60e4  test    eax, 0FFFFFFFAh
0x1800a60e9  jz      loc_1800A6755
0x1800a60ef  cmp     esi, 50h ; 'P'
0x1800a60f2  jnz     short loc_1800A6116
0x1800a60f4  mov     ebx, cs:?g_msgPrivate@@3IA; uint g_msgPrivate
0x1800a60fa  call    cs:__imp_GetCurrentThreadId
0x1800a6100  xor     r9d, r9d; lParam
0x1800a6103  lea     r8d, [r13+0Fh]; wParam
0x1800a6107  mov     ecx, eax; idThread
0x1800a6109  mov     edx, ebx; Msg
0x1800a610b  call    cs:__imp_PostThreadMessageW
0x1800a6111  jmp     loc_1800A6817
0x1800a6116  cmp     esi, 102h
0x1800a611c  jnz     loc_1800A61A7
0x1800a6122  call    ?IsInputServiceEnabled@@YA_NXZ; IsInputServiceEnabled(void)
0x1800a6127  test    al, al
0x1800a6129  jnz     loc_1800A6817
0x1800a612f  mov     ecx, cs:?g_uModifiers@@3IA; uint g_uModifiers
0x1800a6135  mov     eax, ecx
0x1800a6137  and     eax, 49h
0x1800a613a  jz      short loc_1800A6141
0x1800a613c  test    cl, 92h
0x1800a613f  jnz     short loc_1800A615F
0x1800a6141  test    cl, 92h
0x1800a6144  jz      short loc_1800A6157
0x1800a6146  mov     ecx, 20h ; ' '
0x1800a614b  cmp     [rdi+10h], cx
0x1800a614f  jb      loc_1800A6817
0x1800a6155  jmp     short loc_1800A615F
0x1800a6157  test    eax, eax
0x1800a6159  jnz     loc_1800A6817
0x1800a615f  test    rbx, rbx
0x1800a6162  jz      loc_1800A6817
0x1800a6168  mov     rcx, [rbx]; this
0x1800a616b  test    rcx, rcx
0x1800a616e  jz      loc_1800A6817
0x1800a6174  call    ?GetTopInputContext@CThreadInputMgr@@QEBAPEAUIInputContextPrivate@@XZ; CThreadInputMgr::GetTopInputContext(void)
0x1800a6179  mov     rcx, rax
0x1800a617c  test    rax, rax
0x1800a617f  jz      loc_1800A6817
0x1800a6185  mov     rax, [rax]
0x1800a6188  mov     r8, [rdi+18h]
0x1800a618c  mov     rdx, [rdi+10h]
0x1800a6190  mov     rax, [rax+170h]
0x1800a6197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a619c  test    al, al
0x1800a619e  setnz   r12b
0x1800a61a2  jmp     loc_1800A6817
0x1800a61a7  cmp     esi, cs:?g_msgPrivate@@3IA; uint g_msgPrivate
0x1800a61ad  jnz     loc_1800A669F
0x1800a61b3  test    rbx, rbx
0x1800a61b6  jnz     short loc_1800A61CD
0x1800a61b8  call    ?GetSYSTHREAD@@YAPEAUtagSYSTHREAD@@XZ; GetSYSTHREAD(void)
0x1800a61bd  mov     rbx, rax
0x1800a61c0  test    rax, rax
0x1800a61c3  jnz     short loc_1800A61CD
0x1800a61c5  lea     eax, [rbx+1]
0x1800a61c8  jmp     loc_1800A681A
0x1800a61cd  movzx   ecx, word ptr [rdi+10h]
0x1800a61d1  cmp     ecx, 13h
0x1800a61d4  ja      loc_1800A649E
0x1800a61da  jz      loc_1800A63CE
0x1800a61e0  cmp     ecx, 0Ah
0x1800a61e3  ja      loc_1800A630D
0x1800a61e9  jz      loc_1800A62AE
0x1800a61ef  sub     ecx, 4
0x1800a61f2  jz      loc_1800A6298
0x1800a61f8  sub     ecx, 1
0x1800a61fb  jz      short loc_1800A6277
0x1800a61fd  sub     ecx, 1
0x1800a6200  jz      short loc_1800A6256
0x1800a6202  sub     ecx, 1
0x1800a6205  jz      short loc_1800A623C
0x1800a6207  sub     ecx, 1
0x1800a620a  jz      short loc_1800A622A
0x1800a620c  cmp     ecx, 1
0x1800a620f  jnz     loc_1800A6817
0x1800a6215  mov     eax, [rdi+18h]
0x1800a6218  cmp     [rbx+7Ch], eax
0x1800a621b  jnz     loc_1800A6817
0x1800a6221  mov     [rbx+7Ch], r13
0x1800a6225  jmp     loc_1800A6817
0x1800a622a  mov     eax, [rdi+18h]
0x1800a622d  mov     [rbx+7Ch], eax
0x1800a6230  mov     [rbx+80h], r13d
0x1800a6237  jmp     loc_1800A6817
0x1800a623c  mov     rcx, [rbx+48h]; this
0x1800a6240  test    rcx, rcx
0x1800a6243  jz      loc_1800A6817
0x1800a6249  mov     edx, [rdi+18h]; unsigned int
0x1800a624c  call    ?NotifyGlobalCompartmentChange@CCompartmentMgr@@QEAAXK@Z; CCompartmentMgr::NotifyGlobalCompartmentChange(ulong)
0x1800a6251  jmp     loc_1800A6817
0x1800a6256  mov     rcx, [rbx+20h]; this
0x1800a625a  test    rcx, rcx
0x1800a625d  jz      loc_1800A6817
0x1800a6263  cmp     [rdi+18h], r13d
0x1800a6267  mov     edx, r13d
0x1800a626a  setz    dl; int
0x1800a626d  call    ?ActivateNextKeyboardProfile@CInputProfileManager@@QEAAJH@Z; CInputProfileManager::ActivateNextKeyboardProfile(int)
0x1800a6272  jmp     loc_1800A6817
0x1800a6277  mov     rcx, [rbx+20h]; this
0x1800a627b  test    rcx, rcx
0x1800a627e  jz      loc_1800A6817
0x1800a6284  cmp     [rdi+18h], r13d
0x1800a6288  mov     edx, r13d
0x1800a628b  setz    dl; int
0x1800a628e  call    ?ActivateNextLanguage@CInputProfileManager@@QEAAJH@Z; CInputProfileManager::ActivateNextLanguage(int)
0x1800a6293  jmp     loc_1800A6817
0x1800a6298  mov     rcx, [rbx]; this
0x1800a629b  test    rcx, rcx
0x1800a629e  jz      loc_1800A6817
0x1800a62a4  call    ?UpdateDispAttr@CThreadInputMgr@@QEAAXXZ; CThreadInputMgr::UpdateDispAttr(void)
0x1800a62a9  jmp     loc_1800A6817
0x1800a62ae  mov     rbx, [rbx+40h]
0x1800a62b2  test    rbx, rbx
0x1800a62b5  jz      loc_1800A6817
0x1800a62bb  xor     edx, edx; Val
0x1800a62bd  lea     rcx, [rbp+57h+var_D0]; void *
0x1800a62c1  lea     r8d, [rdx+58h]; Size
0x1800a62c5  call    memset_0
0x1800a62ca  mov     rbx, [rbx+60h]
0x1800a62ce  test    rbx, rbx
0x1800a62d1  jz      loc_1800A6817
0x1800a62d7  mov     rax, [rbx]
0x1800a62da  lea     r8, [rbp+57h+var_D0]
0x1800a62de  mov     edx, [rdi+18h]
0x1800a62e1  mov     rcx, rbx
0x1800a62e4  mov     rax, [rax+20h]
0x1800a62e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a62ed  test    eax, eax
0x1800a62ef  js      loc_1800A6817
0x1800a62f5  mov     rax, [rbx]
0x1800a62f8  lea     rdx, [rbp+57h+var_C8]
0x1800a62fc  mov     rcx, rbx
0x1800a62ff  mov     rax, [rax+38h]
0x1800a6303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6308  jmp     loc_1800A6817
0x1800a630d  sub     ecx, 0Ch
0x1800a6310  jz      loc_1800A63B7
0x1800a6316  sub     ecx, 1
0x1800a6319  jz      short loc_1800A638F
0x1800a631b  sub     ecx, 1
0x1800a631e  jz      short loc_1800A635C
0x1800a6320  sub     ecx, 1
0x1800a6323  jz      short loc_1800A6352
0x1800a6325  cmp     ecx, 1
0x1800a6328  jnz     loc_1800A6817
0x1800a632e  btr     dword ptr [rbx+0C0h], 7
0x1800a6336  mov     rcx, [rbx]; this
0x1800a6339  test    rcx, rcx
0x1800a633c  jz      loc_1800A6817
0x1800a6342  xor     edx, edx; struct IInputContextPrivate *
0x1800a6344  lea     r8d, [rdx+1]; bool
0x1800a6348  call    ?OnPostponedLockRequest@CThreadInputMgr@@QEAAXPEAUIInputContextPrivate@@_N@Z; CThreadInputMgr::OnPostponedLockRequest(IInputContextPrivate *,bool)
0x1800a634d  jmp     loc_1800A6817
0x1800a6352  mov     ecx, 1
0x1800a6357  jmp     loc_1800A6692
0x1800a635c  mov     rcx, [rbx+50h]; this
0x1800a6360  test    rcx, rcx
0x1800a6363  jz      loc_1800A6817
0x1800a6369  mov     rdx, [rcx+0B8h]
0x1800a6370  test    rdx, rdx
0x1800a6373  jz      loc_1800A6817
0x1800a6379  mov     eax, [rdi+18h]
0x1800a637c  cmp     [rdx+7Ch], eax
0x1800a637f  jnz     loc_1800A6817
0x1800a6385  call    ?SendFocusEvent@CTipProxy@@AEAAXXZ; CTipProxy::SendFocusEvent(void)
0x1800a638a  jmp     loc_1800A6817
0x1800a638f  mov     rcx, [rbx+50h]; this
0x1800a6393  test    rcx, rcx
0x1800a6396  jz      loc_1800A6817
0x1800a639c  mov     eax, [rdi+18h]
0x1800a639f  cmp     [rcx+0CCh], eax
0x1800a63a5  jnz     loc_1800A6817
0x1800a63ab  xor     edx, edx; bool
0x1800a63ad  call    ?CloseUI@CTipProxy@@AEAAX_N@Z; CTipProxy::CloseUI(bool)
0x1800a63b2  jmp     loc_1800A6817
0x1800a63b7  mov     rcx, [rbx+20h]; this
0x1800a63bb  test    rcx, rcx
0x1800a63be  jz      loc_1800A6817
0x1800a63c4  call    ?OnLocalProfileChange@CInputProfileManager@@QEAAXXZ; CInputProfileManager::OnLocalProfileChange(void)
0x1800a63c9  jmp     loc_1800A6817
0x1800a63ce  call    cs:__imp_GetFocus
0x1800a63d4  mov     rdx, rax; HWND
0x1800a63d7  lea     rcx, [rsp+130h+var_E0]; this
0x1800a63dc  call    ??0CImmContext@@QEAA@PEAUHWND__@@@Z; CImmContext::CImmContext(HWND__ *)
0x1800a63e1  mov     r14, [rsp+130h+var_D8]
0x1800a63e6  test    r14, r14
0x1800a63e9  jz      loc_1800A648F
0x1800a63ef  movzx   esi, word ptr [rdi+12h]
0x1800a63f3  btr     dword ptr [rbx+0C0h], 0Ah
0x1800a63fb  mov     eax, esi
0x1800a63fd  and     eax, 20h
0x1800a6400  shl     eax, 5
0x1800a6403  or      [rbx+0C0h], eax
0x1800a6409  test    sil, 3
0x1800a640d  jz      short loc_1800A6423
0x1800a640f  movzx   edx, si
0x1800a6412  mov     rcx, r14; HIMC
0x1800a6415  not     dx
0x1800a6418  shr     edx, 1
0x1800a641a  and     edx, 1; BOOL
0x1800a641d  call    cs:__imp_ImmSetOpenStatus
0x1800a6423  test    sil, 0Ch
0x1800a6427  jz      short loc_1800A6487
0x1800a6429  movzx   r15d, si
0x1800a642d  mov     [rsp+130h+fdwConversion], r13d
0x1800a6432  mov     [rsp+130h+fdwSentence], r13d
0x1800a6437  and     r15w, 4
0x1800a643c  jz      short loc_1800A6444
0x1800a643e  test    sil, 8
0x1800a6442  jnz     short loc_1800A645D
0x1800a6444  lea     r8, [rsp+130h+fdwSentence]; lpfdwSentence
0x1800a6449  mov     rcx, r14; HIMC
0x1800a644c  lea     rdx, [rsp+130h+fdwConversion]; lpfdwConversion
0x1800a6451  call    cs:__imp_ImmGetConversionStatus
0x1800a6457  test    r15w, r15w
0x1800a645b  jz      short loc_1800A6467
0x1800a645d  movzx   edx, word ptr [rdi+18h]
0x1800a6461  mov     [rsp+130h+fdwConversion], edx
0x1800a6465  jmp     short loc_1800A646B
0x1800a6467  mov     edx, [rsp+130h+fdwConversion]; DWORD
0x1800a646b  test    sil, 8
0x1800a646f  jz      short loc_1800A6479
0x1800a6471  movzx   eax, word ptr [rdi+1Ah]
0x1800a6475  mov     [rsp+130h+fdwSentence], eax
0x1800a6479  mov     r8d, [rsp+130h+fdwSentence]; DWORD
0x1800a647e  mov     rcx, r14; HIMC
0x1800a6481  call    cs:__imp_ImmSetConversionStatus
0x1800a6487  btr     dword ptr [rbx+0C0h], 0Ah
0x1800a648f  lea     rcx, [rsp+130h+var_E0]; this
0x1800a6494  call    ??1CImmContext@@QEAA@XZ; CImmContext::~CImmContext(void)
0x1800a6499  jmp     loc_1800A6817
0x1800a649e  cmp     ecx, 1Bh
0x1800a64a1  ja      loc_1800A65D6
0x1800a64a7  jz      short loc_1800A64CE
0x1800a64a9  sub     ecx, 14h
0x1800a64ac  jz      loc_1800A657A
0x1800a64b2  sub     ecx, 1
0x1800a64b5  jz      loc_1800A6547
0x1800a64bb  sub     ecx, 1
0x1800a64be  jz      short loc_1800A64F5
0x1800a64c0  sub     ecx, 3
0x1800a64c3  jz      short loc_1800A64CE
0x1800a64c5  cmp     ecx, 1
0x1800a64c8  jnz     loc_1800A6817
0x1800a64ce  mov     rcx, [rdi+18h]; hWnd
0x1800a64d2  call    cs:__imp_IsWindow
0x1800a64d8  test    eax, eax
0x1800a64da  jz      loc_1800A6817
0x1800a64e0  cmp     qword ptr [rdi+10h], 19h
0x1800a64e5  jnz     loc_1800A65A4
0x1800a64eb  mov     eax, 1
0x1800a64f0  jmp     loc_1800A65BC
0x1800a64f5  call    ?CreateInstance@CInputProfileManager@@SAPEAV1@XZ; CInputProfileManager::CreateInstance(void)
0x1800a64fa  xor     edx, edx; Val
0x1800a64fc  lea     rcx, [rbp+57h+var_D0]; void *
0x1800a6500  mov     rbx, rax
0x1800a6503  lea     r8d, [rdx+58h]; Size
0x1800a6507  call    memset_0
0x1800a650c  test    rbx, rbx
0x1800a650f  jz      loc_1800A6817
0x1800a6515  mov     rcx, [rbx]
0x1800a6518  lea     r8, [rbp+57h+var_D0]
0x1800a651c  mov     edx, [rdi+18h]
0x1800a651f  mov     rax, [rcx+18h]
0x1800a6523  mov     rcx, rbx
0x1800a6526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a652b  test    eax, eax
0x1800a652d  js      short loc_1800A6597
0x1800a652f  movzx   edx, word ptr [rbp+57h+var_CC]
0x1800a6533  lea     r9, [rbp+57h+var_B8]
0x1800a6537  mov     [rsp+130h+var_108], 1
0x1800a653c  lea     r8, [rbp+57h+var_C8]
0x1800a6540  mov     [rsp+130h+var_110], r13
0x1800a6545  jmp     short loc_1800A6570
0x1800a6547  call    ?CreateInstance@CInputProfileManager@@SAPEAV1@XZ; CInputProfileManager::CreateInstance(void)
0x1800a654c  mov     rbx, rax
0x1800a654f  test    rax, rax
0x1800a6552  jz      loc_1800A6817
0x1800a6558  movsxd  rdx, dword ptr [rdi+18h]; unsigned __int16
  ... truncated ...
```
