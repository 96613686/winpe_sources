# MkvMfSourceLib::MkvMfSource::PurgeCache(void)

- ea: `0x18001aaa0`
- end: `0x18001b35c`
- name: `?PurgeCache@MkvMfSource@MkvMfSourceLib@@AEAAJXZ`
- size: `2236`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfSource *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180016840`

## callees

- `0x180002400`
- `0x180008344`
- `0x180009b04`
- `0x180009bec`
- `0x18000ca3c`
- `0x18000d0dc`
- `0x18000d554`
- `0x18000ddc0`
- `0x18000e148`
- `0x1800114dc`
- `0x18001aaa0`
- `0x180021b9c`
- `0x180046470`
- `0x1800744d8`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001ae87`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001af1c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001aff4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001b0a4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001ae87`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001af1c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001aff4`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001b0a4`

## string_xrefs

- `0x18001ac4d`: `MkvMfSourceLib::MkvMfSource::PurgeCache`
- `0x18001ad27`: `MkvMfSourceLib::MkvMfSource::PurgeCache`
- `0x18001adca`: `MkvMfSourceLib::MkvMfSource::PurgeCache`
- `0x18001aeea`: `MkvMfSourceLib::MkvMfSource::PurgeCache`
- `0x18001af7f`: `MkvMfSourceLib::MkvMfSource::PurgeCache`
- `0x18001b057`: `MkvMfSourceLib::MkvMfSource::PurgeCache`
- `0x18001b107`: `MkvMfSourceLib::MkvMfSource::PurgeCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall MkvMfSourceLib::MkvMfSource::PurgeCache(MkvMfSourceLib::MkvMfSource *this)
{
  char v2; // r8
  char *v3; // rdi
  _QWORD *v4; // rcx
  __int64 v5; // rax
  __int64 v6; // r13
  __int64 *v7; // rcx
  __int64 v8; // r9
  const char *v9; // r9
  __int64 *v10; // rax
  int v11; // ebx
  __int64 *v12; // rdx
  __int64 v13; // r15
  __int64 v14; // r12
  unsigned __int64 v15; // rcx
  char v16; // di
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v18; // ebx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  struct CallStackContext *v25; // rdi
  int v26; // ebx
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  struct CallStackContext *v30; // rdi
  int v31; // ebx
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 *v35; // rcx
  CallStackTracing *v36; // rax
  struct CallStackContext *v37; // rax
  __int64 v38; // rdx
  __int64 *v39; // rcx
  CallStackTracing *v40; // rax
  struct CallStackContext *v41; // rax
  __int64 *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  __int64 *v46; // rcx
  CallStackTracing *v47; // rax
  struct CallStackContext *v48; // rax
  __int64 v49; // rbx
  mkvparser::BlockEntry *v50; // rcx
  _QWORD *v51; // r8
  __int64 v52; // rdx
  const char *v53; // r9
  __int64 v54; // rbx
  const char *v55; // r9
  __int64 v56; // rax
  char v57; // [rsp+30h] [rbp-98h] BYREF
  char v58; // [rsp+31h] [rbp-97h]
  __int64 v59; // [rsp+38h] [rbp-90h]
  __int128 v60; // [rsp+40h] [rbp-88h] BYREF
  __int64 v61; // [rsp+50h] [rbp-78h]
  __int64 v62; // [rsp+58h] [rbp-70h] BYREF
  int v63; // [rsp+60h] [rbp-68h] BYREF
  __int64 v64; // [rsp+68h] [rbp-60h] BYREF
  _QWORD v65[2]; // [rsp+70h] [rbp-58h] BYREF
  _QWORD v66[2]; // [rsp+80h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v60 = 0;
  v61 = 0;
  v2 = *((_BYTE *)this + 592);
  v3 = (char *)this + 416;
  if ( v2 )
  {
    v4 = *(_QWORD **)(*(_QWORD *)v3 + 136LL);
    v5 = v4[1] + v4[2];
    if ( v4[7] < v5 )
    {
      v58 = 0;
      v59 = -1;
      v6 = -1;
      goto LABEL_5;
    }
  }
  v59 = -1;
  v6 = -1;
  v58 = 1;
  if ( v2 )
  {
LABEL_5:
    v7 = *(__int64 **)(*(_QWORD *)v3 + 136LL);
    v8 = v7[1] + v7[2];
    if ( v7[7] < v8 )
    {
      v59 = v7[1];
      v6 = v8;
    }
  }
  try
  {
    v62 = -1;
    std::vector<__int64>::_Emplace_reallocate<__int64 const &>(&v60, 0, &v62);
    v56 = **((_QWORD **)this + 72);
    v62 = v56;
  }
  catch ( ... )
  {
    LODWORD(v59) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0xCC5,
                     (unsigned int)"avcore\\mf\\core\\mediasource\\mkv\\lib\\mkvmfsource.cpp",
                     v55);
    goto LABEL_116;
  }
  while ( v56 != *((_QWORD *)this + 72) )
  {
    v63 = *(_DWORD *)(v56 + 32);
    v64 = *(_QWORD *)(v56 + 40);
    v49 = v64;
    Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(&v64);
    v65[0] = v49;
    Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStreamSubtitle>::InternalAddRef(v65);
    if ( *(int *)(v49 + 292) <= 0 )
    {
      if ( v49 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
        v64 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
      }
    }
    else
    {
      v50 = *(mkvparser::BlockEntry **)(v49 + 192);
      if ( v50 && mkvparser::BlockEntry::EOS(v50) )
      {
        if ( v49 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
          v64 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
        }
      }
      else
      {
        v51 = *(_QWORD **)(v49 + 328);
        if ( v51 )
        {
          if ( *((_BYTE *)this + 656) )
            v52 = v51[1] + *(_QWORD *)(*(_QWORD *)v3 + 16LL) - *(_QWORD *)(*v51 + 16LL);
          else
            v52 = v51[3] + *(_QWORD *)(*(_QWORD *)v3 + 16LL);
          v66[0] = v52;
          if ( *((_QWORD *)&v60 + 1) == v61 )
          {
            try
            {
              std::vector<__int64>::_Emplace_reallocate<__int64 const &>(&v60, *((_QWORD *)&v60 + 1), v66);
            }
            catch ( ... )
            {
              LODWORD(v59) = wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0xCE5,
                               (unsigned int)"avcore\\mf\\core\\mediasource\\mkv\\lib\\mkvmfsource.cpp",
                               v53);
              v54 = v64;
              if ( v64 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
              if ( v54 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
LABEL_116:
              if ( (_QWORD)v60 )
                std::_Deallocate<16>(v60, (v61 - v60) & 0xFFFFFFFFFFFFFFF8uLL);
              return (unsigned int)v59;
            }
          }
          else
          {
            **((_QWORD **)&v60 + 1) = v52;
            *((_QWORD *)&v60 + 1) += 8LL;
          }
          if ( v49 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
            v64 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
          }
        }
        else if ( v49 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
          v64 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
        }
      }
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,Microsoft::WRL::ComPtr<MkvMfSourceLib::MkvMfStream>>>>,std::_Iterator_base0>::operator++(&v62);
    v56 = v62;
  }
  try
  {
    LOBYTE(v55) = 0;
    std::_Sort_unchecked<__int64 *,std::less<void>>(
      v60,
      *((_QWORD *)&v60 + 1),
      (__int64)(*((_QWORD *)&v60 + 1) - v60) >> 3,
      v55);
    v10 = (__int64 *)v60;
    if ( *((_BYTE *)this + 656)
      && (unsigned __int64)((__int64)(*((_QWORD *)&v60 + 1) - v60) >> 3) > 2
      && (_QWORD)v60 + 16LL != *((_QWORD *)&v60 + 1) )
    {
      *((_QWORD *)&v60 + 1) = v60 + 16;
    }
    v11 = 0;
  }
  catch ( ... )
  {
    LODWORD(v59) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0xCEC,
                     (unsigned int)"avcore\\mf\\core\\mediasource\\mkv\\lib\\mkvmfsource.cpp",
                     v9);
    goto LABEL_116;
  }
  while ( 1 )
  {
    if ( v10 == *((__int64 **)&v60 + 1) )
    {
LABEL_65:
      if ( (_QWORD)v60 )
        std::_Deallocate<16>(v60, (v61 - v60) & 0xFFFFFFFFFFFFFFF8uLL);
      return (unsigned int)v11;
    }
    v12 = v10 + 1;
    v62 = (__int64)(v10 + 1);
    if ( v10 + 1 != *((__int64 **)&v60 + 1) )
    {
      v13 = *v10;
      v14 = *v12;
      v15 = *((_QWORD *)this + 59);
      if ( *v12 - *v10 >= v15 )
        break;
    }
LABEL_42:
    v10 = v12;
  }
  if ( !*((_BYTE *)this + 656) )
    v13 += v15;
  v16 = v58;
  if ( v58 )
    goto LABEL_37;
  if ( v59 >= v13 && v59 < v14 )
  {
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v57,
      "MkvMfSourceLib::MkvMfSource::PurgeCache",
      3337);
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 86) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      v18 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 86) + 296LL))(*((_QWORD *)this + 86));
      *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 86) + 280LL))(
                                                              *((_QWORD *)this + 86),
                                                              &v63);
      *((_DWORD *)ThreadRelativeContext + 504) = v18;
      v16 = v58;
    }
    v11 = MkvReader::Purge((MkvMfSourceLib::MkvMfSource *)((char *)this + 184), v13, v59);
    if ( v11 < 0 )
    {
      v39 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v19, v20, v21);
        CallStackTracing::s_wpInstance = v40;
        if ( v40 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
        {
          v39 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v39 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v39 + 8) )
      {
        v41 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v39);
        if ( *((_DWORD *)v41 + 499) != v11 )
          CallStackContext::TraceFailure(v41, "MkvMfSourceLib::MkvMfSource::PurgeCache", 3337, v11);
      }
      if ( g_wppLevels )
      {
        v38 = 218;
LABEL_63:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v38, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, this, v11);
      }
LABEL_64:
      CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v57);
      goto LABEL_65;
    }
    if ( v6 >= v13 && v6 < v14 )
    {
      v11 = MkvReader::Purge((MkvMfSourceLib::MkvMfSource *)((char *)this + 184), v6, v14);
      if ( v11 < 0 )
      {
        v35 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v22, v23, v24);
          CallStackTracing::s_wpInstance = v36;
          if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
          {
            v35 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v35 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v35 + 8) )
        {
          v37 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v35);
          if ( *((_DWORD *)v37 + 499) != v11 )
            CallStackContext::TraceFailure(v37, "MkvMfSourceLib::MkvMfSource::PurgeCache", 3341, v11);
        }
        if ( g_wppLevels )
        {
          v38 = 219;
          goto LABEL_63;
        }
        goto LABEL_64;
      }
    }
    goto LABEL_41;
  }
  if ( v6 < v13 || v6 >= v14 )
  {
LABEL_37:
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v57,
      "MkvMfSourceLib::MkvMfSource::PurgeCache",
      3353);
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 86) )
    {
      v30 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      v31 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 86) + 296LL))(*((_QWORD *)this + 86));
      *((_OWORD *)v30 + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 86) + 280LL))(
                                            *((_QWORD *)this + 86),
                                            v65);
      *((_DWORD *)v30 + 504) = v31;
      v16 = v58;
    }
    v11 = MkvReader::Purge((MkvMfSourceLib::MkvMfSource *)((char *)this + 184), v13, v14);
    if ( v11 < 0 )
    {
      v46 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v47 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v32, v33, v34);
        CallStackTracing::s_wpInstance = v47;
        if ( v47 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v47 + 8LL))(v47, 2032) )
        {
          v46 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v46 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v46 + 8) )
      {
        v48 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v46);
        if ( *((_DWORD *)v48 + 499) != v11 )
          CallStackContext::TraceFailure(v48, "MkvMfSourceLib::MkvMfSource::PurgeCache", 3353, v11);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 221, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, this, v11);
      goto LABEL_64;
    }
  }
  else
  {
    CallStackScopeTrace::CallStackScopeTrace(
      (CallStackScopeTrace *)&v57,
      "MkvMfSourceLib::MkvMfSource::PurgeCache",
      3348);
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 86) )
    {
      v25 = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
      v26 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 86) + 296LL))(*((_QWORD *)this + 86));
      *((_OWORD *)v25 + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**((_QWORD **)this + 86) + 280LL))(
                                            *((_QWORD *)this + 86),
                                            v66);
      *((_DWORD *)v25 + 504) = v26;
      v16 = v58;
    }
    v11 = MkvReader::Purge((MkvMfSourceLib::MkvMfSource *)((char *)this + 184), v6, v14);
    if ( v11 < 0 )
    {
      v43 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v27, v28, v29);
        CallStackTracing::s_wpInstance = v44;
        if ( v44 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
        {
          v43 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v43 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      if ( *((_BYTE *)v43 + 8) )
      {
        v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
        if ( *((_DWORD *)v45 + 499) != v11 )
          CallStackContext::TraceFailure(v45, "MkvMfSourceLib::MkvMfSource::PurgeCache", 3348, v11);
      }
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 220, &WPP_767377f0d4d83278867700df36ce02a8_Traceguids, this, v11);
      goto LABEL_64;
    }
  }
LABEL_41:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v57);
  v58 = v16;
  v12 = (__int64 *)v62;
  goto LABEL_42;
}

```

## disassembly

```asm
0x18001aaa0  mov     [rsp+arg_8], rbx
0x18001aaa5  mov     [rsp+arg_10], rsi
0x18001aaaa  push    rdi
0x18001aaab  push    r12
0x18001aaad  push    r13
0x18001aaaf  push    r14
0x18001aab1  push    r15
0x18001aab3  sub     rsp, 0A0h
0x18001aaba  mov     rax, cs:__security_cookie
0x18001aac1  xor     rax, rsp
0x18001aac4  mov     [rsp+0C8h+var_38], rax
0x18001aacc  mov     r14, rcx
0x18001aacf  xorps   xmm0, xmm0
0x18001aad2  movdqu  [rsp+0C8h+var_88], xmm0
0x18001aad8  xor     esi, esi
0x18001aada  mov     [rsp+0C8h+var_78], rsi
0x18001aadf  mov     r8b, [rcx+250h]
0x18001aae6  lea     rdi, [rcx+1A0h]
0x18001aaed  test    r8b, r8b
0x18001aaf0  jz      short loc_18001AB1D
0x18001aaf2  mov     rax, [rdi]
0x18001aaf5  mov     rcx, [rax+88h]
0x18001aafc  mov     rax, [rcx+10h]
0x18001ab00  add     rax, [rcx+8]
0x18001ab04  cmp     [rcx+38h], rax
0x18001ab08  jge     short loc_18001AB1D
0x18001ab0a  mov     [rsp+0C8h+var_97], sil
0x18001ab0f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001ab13  mov     [rsp+0C8h+var_90], rdx
0x18001ab18  mov     r13, rdx
0x18001ab1b  jmp     short loc_18001AB33
0x18001ab1d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001ab21  mov     [rsp+0C8h+var_90], rdx
0x18001ab26  mov     r13, rdx
0x18001ab29  mov     [rsp+0C8h+var_97], 1
0x18001ab2e  test    r8b, r8b
0x18001ab31  jz      short loc_18001AB56
0x18001ab33  mov     rax, [rdi]
0x18001ab36  mov     rcx, [rax+88h]
0x18001ab3d  mov     r8, [rcx+8]
0x18001ab41  mov     r9, [rcx+10h]
0x18001ab45  add     r9, r8
0x18001ab48  cmp     [rcx+38h], r9
0x18001ab4c  jge     short loc_18001AB56
0x18001ab4e  mov     [rsp+0C8h+var_90], r8
0x18001ab53  mov     r13, r9
0x18001ab56  mov     [rsp+0C8h+var_70], rdx
0x18001ab5b  lea     r8, [rsp+0C8h+var_70]
0x18001ab60  xor     edx, edx
0x18001ab62  lea     rcx, [rsp+0C8h+var_88]
0x18001ab67  call    ??$_Emplace_reallocate@AEB_J@?$vector@_JV?$allocator@_J@std@@@std@@AEAAPEA_JQEA_JAEB_J@Z; std::vector<__int64>::_Emplace_reallocate<__int64 const &>(__int64 * const,__int64 const &)
0x18001ab6c  nop
0x18001ab6d  mov     rax, [r14+240h]
0x18001ab74  mov     rax, [rax]
0x18001ab77  mov     [rsp+0C8h+var_70], rax
0x18001ab7c  cmp     rax, [r14+240h]
0x18001ab83  jnz     loc_18001B14D
0x18001ab89  mov     rdx, qword ptr [rsp+0C8h+var_88+8]
0x18001ab8e  mov     rcx, qword ptr [rsp+0C8h+var_88]
0x18001ab93  mov     r8, rdx
0x18001ab96  sub     r8, rcx
0x18001ab99  sar     r8, 3
0x18001ab9d  mov     r9b, sil
0x18001aba0  call    ??$_Sort_unchecked@PEA_JU?$less@X@std@@@std@@YAXPEA_J0_JU?$less@X@0@@Z; std::_Sort_unchecked<__int64 *,std::less<void>>(__int64 *,__int64 *,__int64,std::less<void>)
0x18001aba5  nop
0x18001aba6  mov     rax, qword ptr [rsp+0C8h+var_88]
0x18001abab  cmp     [r14+290h], sil
0x18001abb2  jz      short loc_18001ABD6
0x18001abb4  mov     rcx, qword ptr [rsp+0C8h+var_88+8]
0x18001abb9  sub     rcx, rax
0x18001abbc  sar     rcx, 3
0x18001abc0  cmp     rcx, 2
0x18001abc4  jbe     short loc_18001ABD6
0x18001abc6  lea     rcx, [rax+10h]
0x18001abca  cmp     rcx, qword ptr [rsp+0C8h+var_88+8]
0x18001abcf  jz      short loc_18001ABD6
0x18001abd1  mov     qword ptr [rsp+0C8h+var_88+8], rcx
0x18001abd6  mov     ebx, esi
0x18001abd8  cmp     rax, qword ptr [rsp+0C8h+var_88+8]
0x18001abdd  jz      loc_18001AFC6
0x18001abe3  lea     rdx, [rax+8]
0x18001abe7  mov     [rsp+0C8h+var_70], rdx
0x18001abec  cmp     rdx, qword ptr [rsp+0C8h+var_88+8]
0x18001abf1  jz      loc_18001AE73
0x18001abf7  mov     r15, [rax]
0x18001abfa  mov     r12, [rdx]
0x18001abfd  mov     rcx, [r14+1D8h]
0x18001ac04  mov     rax, r12
0x18001ac07  sub     rax, r15
0x18001ac0a  cmp     rax, rcx
0x18001ac0d  jb      loc_18001AE73
0x18001ac13  lea     rax, [rcx+r15]
0x18001ac17  cmp     [r14+290h], sil
0x18001ac1e  cmovz   r15, rax
0x18001ac22  mov     dil, [rsp+0C8h+var_97]
0x18001ac27  test    dil, dil
0x18001ac2a  jnz     loc_18001ADC4
0x18001ac30  mov     rax, [rsp+0C8h+var_90]
0x18001ac35  cmp     rax, r15
0x18001ac38  jl      loc_18001AD0F
0x18001ac3e  cmp     rax, r12
0x18001ac41  jge     loc_18001AD0F
0x18001ac47  mov     r8d, 0D09h; int
0x18001ac4d  lea     rdx, aMkvmfsourcelib_104; "MkvMfSourceLib::MkvMfSource::PurgeCache"
0x18001ac54  lea     rcx, [rsp+0C8h+var_98]; this
0x18001ac59  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18001ac5e  nop
0x18001ac5f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001ac66  cmp     [rcx+8], sil
0x18001ac6a  jz      short loc_18001ACC6
0x18001ac6c  cmp     [r14+2B0h], rsi
0x18001ac73  jz      short loc_18001ACC6
0x18001ac75  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001ac7a  mov     rdi, rax
0x18001ac7d  mov     rcx, [r14+2B0h]
0x18001ac84  mov     rax, [rcx]
0x18001ac87  mov     rax, [rax+128h]
0x18001ac8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac93  mov     ebx, eax
0x18001ac95  mov     rcx, [r14+2B0h]
0x18001ac9c  mov     rax, [rcx]
0x18001ac9f  lea     rdx, [rsp+0C8h+var_68]
0x18001aca4  mov     rax, [rax+118h]
0x18001acab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001acb0  movups  xmm0, xmmword ptr [rax]
0x18001acb3  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18001acbb  mov     [rdi+7E0h], ebx
0x18001acc1  mov     dil, [rsp+0C8h+var_97]
0x18001acc6  lea     rcx, [r14+0B8h]; this
0x18001accd  mov     r8, [rsp+0C8h+var_90]; __int64
0x18001acd2  mov     rdx, r15; __int64
0x18001acd5  call    ?Purge@MkvReader@@QEAAJ_J0@Z; MkvReader::Purge(__int64,__int64)
0x18001acda  mov     ebx, eax
0x18001acdc  test    eax, eax
0x18001acde  js      loc_18001AF10
0x18001ace4  cmp     r13, r15
0x18001ace7  jl      short loc_18001AD0A
0x18001ace9  cmp     r13, r12
0x18001acec  jge     short loc_18001AD0A
0x18001acee  mov     r8, r12; __int64
0x18001acf1  mov     rdx, r13; __int64
0x18001acf4  lea     rcx, [r14+0B8h]; this
0x18001acfb  call    ?Purge@MkvReader@@QEAAJ_J0@Z; MkvReader::Purge(__int64,__int64)
0x18001ad00  mov     ebx, eax
0x18001ad02  test    eax, eax
0x18001ad04  js      loc_18001AE7B
0x18001ad0a  jmp     loc_18001AE5F
0x18001ad0f  cmp     r13, r15
0x18001ad12  jl      loc_18001ADC4
0x18001ad18  cmp     r13, r12
0x18001ad1b  jge     loc_18001ADC4
0x18001ad21  mov     r8d, 0D14h; int
0x18001ad27  lea     rdx, aMkvmfsourcelib_104; "MkvMfSourceLib::MkvMfSource::PurgeCache"
0x18001ad2e  lea     rcx, [rsp+0C8h+var_98]; this
0x18001ad33  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18001ad38  nop
0x18001ad39  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001ad40  cmp     [rcx+8], sil
0x18001ad44  jz      short loc_18001ADA3
0x18001ad46  cmp     [r14+2B0h], rsi
0x18001ad4d  jz      short loc_18001ADA3
0x18001ad4f  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001ad54  mov     rdi, rax
0x18001ad57  mov     rcx, [r14+2B0h]
0x18001ad5e  mov     rdx, [rcx]
0x18001ad61  mov     rax, [rdx+128h]
0x18001ad68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad6d  mov     ebx, eax
0x18001ad6f  mov     rcx, [r14+2B0h]
0x18001ad76  mov     rdx, [rcx]
0x18001ad79  mov     rax, [rdx+118h]
0x18001ad80  lea     rdx, [rsp+0C8h+var_48]
0x18001ad88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ad8d  movups  xmm0, xmmword ptr [rax]
0x18001ad90  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18001ad98  mov     [rdi+7E0h], ebx
0x18001ad9e  mov     dil, [rsp+0C8h+var_97]
0x18001ada3  lea     rcx, [r14+0B8h]; this
0x18001adaa  mov     r8, r12; __int64
0x18001adad  mov     rdx, r13; __int64
0x18001adb0  call    ?Purge@MkvReader@@QEAAJ_J0@Z; MkvReader::Purge(__int64,__int64)
0x18001adb5  mov     ebx, eax
0x18001adb7  test    eax, eax
0x18001adb9  js      loc_18001AFE8
0x18001adbf  jmp     loc_18001AE5F
0x18001adc4  mov     r8d, 0D19h; int
0x18001adca  lea     rdx, aMkvmfsourcelib_104; "MkvMfSourceLib::MkvMfSource::PurgeCache"
0x18001add1  lea     rcx, [rsp+0C8h+var_98]; this
0x18001add6  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18001addb  nop
0x18001addc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001ade3  cmp     [rcx+8], sil
0x18001ade7  jz      short loc_18001AE43
0x18001ade9  cmp     [r14+2B0h], rsi
0x18001adf0  jz      short loc_18001AE43
0x18001adf2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001adf7  mov     rdi, rax
0x18001adfa  mov     rcx, [r14+2B0h]
0x18001ae01  mov     rdx, [rcx]
0x18001ae04  mov     rax, [rdx+128h]
0x18001ae0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae10  mov     ebx, eax
0x18001ae12  mov     rcx, [r14+2B0h]
0x18001ae19  mov     r8, [rcx]
0x18001ae1c  lea     rdx, [rsp+0C8h+var_58]
0x18001ae21  mov     rax, [r8+118h]
0x18001ae28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ae2d  movups  xmm0, xmmword ptr [rax]
0x18001ae30  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18001ae38  mov     [rdi+7E0h], ebx
0x18001ae3e  mov     dil, [rsp+0C8h+var_97]
0x18001ae43  lea     rcx, [r14+0B8h]; this
0x18001ae4a  mov     r8, r12; __int64
0x18001ae4d  mov     rdx, r15; __int64
0x18001ae50  call    ?Purge@MkvReader@@QEAAJ_J0@Z; MkvReader::Purge(__int64,__int64)
0x18001ae55  mov     ebx, eax
0x18001ae57  test    eax, eax
0x18001ae59  js      loc_18001B098
0x18001ae5f  lea     rcx, [rsp+0C8h+var_98]; this
0x18001ae64  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001ae69  mov     [rsp+0C8h+var_97], dil
0x18001ae6e  mov     rdx, [rsp+0C8h+var_70]
0x18001ae73  mov     rax, rdx
0x18001ae76  jmp     loc_18001ABD8
0x18001ae7b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001ae82  test    rcx, rcx
0x18001ae85  jnz     short loc_18001AECE
0x18001ae87  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001ae8e  nop     dword ptr [rax+rax+00h]
0x18001ae93  mov     rcx, rax
0x18001ae96  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001ae9d  test    rax, rax
0x18001aea0  jz      short loc_18001AEC0
0x18001aea2  mov     rax, [rax]
0x18001aea5  mov     edx, 7F0h
0x18001aeaa  mov     rax, [rax+8]
0x18001aeae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001aeb3  test    eax, eax
0x18001aeb5  jz      short loc_18001AEC0
0x18001aeb7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001aebe  jmp     short loc_18001AECE
0x18001aec0  lea     rcx, qword_1800DBF70; this
0x18001aec7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001aece  cmp     [rcx+8], sil
0x18001aed2  jz      short loc_18001AEF9
0x18001aed4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001aed9  cmp     [rax+7CCh], ebx
0x18001aedf  jz      short loc_18001AEF9
0x18001aee1  mov     r9d, ebx; int
0x18001aee4  mov     r8d, 0D0Dh; int
0x18001aeea  lea     rdx, aMkvmfsourcelib_104; "MkvMfSourceLib::MkvMfSource::PurgeCache"
0x18001aef1  mov     rcx, rax; this
0x18001aef4  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001aef9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001af00  jb      loc_18001AFBB
0x18001af06  mov     edx, 0DBh
0x18001af0b  jmp     loc_18001AF9C
0x18001af10  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001af17  test    rcx, rcx
0x18001af1a  jnz     short loc_18001AF63
0x18001af1c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001af23  nop     dword ptr [rax+rax+00h]
0x18001af28  mov     rcx, rax
0x18001af2b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001af32  test    rax, rax
0x18001af35  jz      short loc_18001AF55
0x18001af37  mov     rax, [rax]
0x18001af3a  mov     edx, 7F0h
0x18001af3f  mov     rax, [rax+8]
0x18001af43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001af48  test    eax, eax
0x18001af4a  jz      short loc_18001AF55
0x18001af4c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001af53  jmp     short loc_18001AF63
0x18001af55  lea     rcx, qword_1800DBF70; this
0x18001af5c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001af63  cmp     [rcx+8], sil
0x18001af67  jz      short loc_18001AF8E
0x18001af69  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001af6e  cmp     [rax+7CCh], ebx
0x18001af74  jz      short loc_18001AF8E
0x18001af76  mov     r9d, ebx; int
0x18001af79  mov     r8d, 0D09h; int
0x18001af7f  lea     rdx, aMkvmfsourcelib_104; "MkvMfSourceLib::MkvMfSource::PurgeCache"
0x18001af86  mov     rcx, rax; this
0x18001af89  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001af8e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001af95  jb      short loc_18001AFBB
0x18001af97  mov     edx, 0DAh
0x18001af9c  mov     [rsp+0C8h+var_A8], ebx
0x18001afa0  mov     r9, r14
0x18001afa3  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x18001afaa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001afb1  mov     rcx, [rcx+10h]
0x18001afb5  call    WPP_SF_qD
0x18001afba  nop
0x18001afbb  lea     rcx, [rsp+0C8h+var_98]; this
0x18001afc0  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001afc5  nop
0x18001afc6  mov     rcx, qword ptr [rsp+0C8h+var_88]
  ... truncated ...
```
