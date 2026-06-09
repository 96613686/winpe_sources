# MkvMfSourceLib::MkvMfSource::PurgeCache(void)

- ea: `0x180019ec4`
- end: `0x18001a767`
- name: `?PurgeCache@MkvMfSource@MkvMfSourceLib@@AEAAJXZ`
- size: `2211`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfSource *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180015dcc`

## callees

- `0x1800023e0`
- `0x1800080b8`
- `0x1800097f0`
- `0x1800098b8`
- `0x18000c4c0`
- `0x18000cb48`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x18000db40`
- `0x180010d98`
- `0x180019ec4`
- `0x180020d84`
- `0x180044624`
- `0x180071330`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001a2ab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001a33a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001a40c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001a4b6`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001a2ab`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001a33a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001a40c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001a4b6`

## string_xrefs

- `0x18001a071`: `MkvMfSourceLib::MkvMfSource::PurgeCache`
- `0x18001a14b`: `MkvMfSourceLib::MkvMfSource::PurgeCache`
- `0x18001a1ee`: `MkvMfSourceLib::MkvMfSource::PurgeCache`
- `0x18001a308`: `MkvMfSourceLib::MkvMfSource::PurgeCache`
- `0x18001a397`: `MkvMfSourceLib::MkvMfSource::PurgeCache`
- `0x18001a469`: `MkvMfSourceLib::MkvMfSource::PurgeCache`
- `0x18001a513`: `MkvMfSourceLib::MkvMfSource::PurgeCache`

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
          v39 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v35 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v46 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v43 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
0x180019ec4  mov     [rsp+arg_8], rbx
0x180019ec9  mov     [rsp+arg_10], rsi
0x180019ece  push    rdi
0x180019ecf  push    r12
0x180019ed1  push    r13
0x180019ed3  push    r14
0x180019ed5  push    r15
0x180019ed7  sub     rsp, 0A0h
0x180019ede  mov     rax, cs:__security_cookie
0x180019ee5  xor     rax, rsp
0x180019ee8  mov     [rsp+0C8h+var_38], rax
0x180019ef0  mov     r14, rcx
0x180019ef3  xorps   xmm0, xmm0
0x180019ef6  movdqu  [rsp+0C8h+var_88], xmm0
0x180019efc  xor     esi, esi
0x180019efe  mov     [rsp+0C8h+var_78], rsi
0x180019f03  mov     r8b, [rcx+250h]
0x180019f0a  lea     rdi, [rcx+1A0h]
0x180019f11  test    r8b, r8b
0x180019f14  jz      short loc_180019F41
0x180019f16  mov     rax, [rdi]
0x180019f19  mov     rcx, [rax+88h]
0x180019f20  mov     rax, [rcx+10h]
0x180019f24  add     rax, [rcx+8]
0x180019f28  cmp     [rcx+38h], rax
0x180019f2c  jge     short loc_180019F41
0x180019f2e  mov     [rsp+0C8h+var_97], sil
0x180019f33  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180019f37  mov     [rsp+0C8h+var_90], rdx
0x180019f3c  mov     r13, rdx
0x180019f3f  jmp     short loc_180019F57
0x180019f41  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180019f45  mov     [rsp+0C8h+var_90], rdx
0x180019f4a  mov     r13, rdx
0x180019f4d  mov     [rsp+0C8h+var_97], 1
0x180019f52  test    r8b, r8b
0x180019f55  jz      short loc_180019F7A
0x180019f57  mov     rax, [rdi]
0x180019f5a  mov     rcx, [rax+88h]
0x180019f61  mov     r8, [rcx+8]
0x180019f65  mov     r9, [rcx+10h]
0x180019f69  add     r9, r8
0x180019f6c  cmp     [rcx+38h], r9
0x180019f70  jge     short loc_180019F7A
0x180019f72  mov     [rsp+0C8h+var_90], r8
0x180019f77  mov     r13, r9
0x180019f7a  mov     [rsp+0C8h+var_70], rdx
0x180019f7f  lea     r8, [rsp+0C8h+var_70]
0x180019f84  xor     edx, edx
0x180019f86  lea     rcx, [rsp+0C8h+var_88]
0x180019f8b  call    ??$_Emplace_reallocate@AEB_J@?$vector@_JV?$allocator@_J@std@@@std@@AEAAPEA_JQEA_JAEB_J@Z; std::vector<__int64>::_Emplace_reallocate<__int64 const &>(__int64 * const,__int64 const &)
0x180019f90  nop
0x180019f91  mov     rax, [r14+240h]
0x180019f98  mov     rax, [rax]
0x180019f9b  mov     [rsp+0C8h+var_70], rax
0x180019fa0  cmp     rax, [r14+240h]
0x180019fa7  jnz     loc_18001A559
0x180019fad  mov     rdx, qword ptr [rsp+0C8h+var_88+8]
0x180019fb2  mov     rcx, qword ptr [rsp+0C8h+var_88]
0x180019fb7  mov     r8, rdx
0x180019fba  sub     r8, rcx
0x180019fbd  sar     r8, 3
0x180019fc1  mov     r9b, sil
0x180019fc4  call    ??$_Sort_unchecked@PEA_JU?$less@X@std@@@std@@YAXPEA_J0_JU?$less@X@0@@Z; std::_Sort_unchecked<__int64 *,std::less<void>>(__int64 *,__int64 *,__int64,std::less<void>)
0x180019fc9  nop
0x180019fca  mov     rax, qword ptr [rsp+0C8h+var_88]
0x180019fcf  cmp     [r14+290h], sil
0x180019fd6  jz      short loc_180019FFA
0x180019fd8  mov     rcx, qword ptr [rsp+0C8h+var_88+8]
0x180019fdd  sub     rcx, rax
0x180019fe0  sar     rcx, 3
0x180019fe4  cmp     rcx, 2
0x180019fe8  jbe     short loc_180019FFA
0x180019fea  lea     rcx, [rax+10h]
0x180019fee  cmp     rcx, qword ptr [rsp+0C8h+var_88+8]
0x180019ff3  jz      short loc_180019FFA
0x180019ff5  mov     qword ptr [rsp+0C8h+var_88+8], rcx
0x180019ffa  mov     ebx, esi
0x180019ffc  cmp     rax, qword ptr [rsp+0C8h+var_88+8]
0x18001a001  jz      loc_18001A3DE
0x18001a007  lea     rdx, [rax+8]
0x18001a00b  mov     [rsp+0C8h+var_70], rdx
0x18001a010  cmp     rdx, qword ptr [rsp+0C8h+var_88+8]
0x18001a015  jz      loc_18001A297
0x18001a01b  mov     r15, [rax]
0x18001a01e  mov     r12, [rdx]
0x18001a021  mov     rcx, [r14+1D8h]
0x18001a028  mov     rax, r12
0x18001a02b  sub     rax, r15
0x18001a02e  cmp     rax, rcx
0x18001a031  jb      loc_18001A297
0x18001a037  lea     rax, [rcx+r15]
0x18001a03b  cmp     [r14+290h], sil
0x18001a042  cmovz   r15, rax
0x18001a046  mov     dil, [rsp+0C8h+var_97]
0x18001a04b  test    dil, dil
0x18001a04e  jnz     loc_18001A1E8
0x18001a054  mov     rax, [rsp+0C8h+var_90]
0x18001a059  cmp     rax, r15
0x18001a05c  jl      loc_18001A133
0x18001a062  cmp     rax, r12
0x18001a065  jge     loc_18001A133
0x18001a06b  mov     r8d, 0D09h; int
0x18001a071  lea     rdx, aMkvmfsourcelib_104; "MkvMfSourceLib::MkvMfSource::PurgeCache"
0x18001a078  lea     rcx, [rsp+0C8h+var_98]; this
0x18001a07d  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18001a082  nop
0x18001a083  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001a08a  cmp     [rcx+8], sil
0x18001a08e  jz      short loc_18001A0EA
0x18001a090  cmp     [r14+2B0h], rsi
0x18001a097  jz      short loc_18001A0EA
0x18001a099  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001a09e  mov     rdi, rax
0x18001a0a1  mov     rcx, [r14+2B0h]
0x18001a0a8  mov     rax, [rcx]
0x18001a0ab  mov     rax, [rax+128h]
0x18001a0b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0b7  mov     ebx, eax
0x18001a0b9  mov     rcx, [r14+2B0h]
0x18001a0c0  mov     rax, [rcx]
0x18001a0c3  lea     rdx, [rsp+0C8h+var_68]
0x18001a0c8  mov     rax, [rax+118h]
0x18001a0cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a0d4  movups  xmm0, xmmword ptr [rax]
0x18001a0d7  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18001a0df  mov     [rdi+7E0h], ebx
0x18001a0e5  mov     dil, [rsp+0C8h+var_97]
0x18001a0ea  lea     rcx, [r14+0B8h]; this
0x18001a0f1  mov     r8, [rsp+0C8h+var_90]; __int64
0x18001a0f6  mov     rdx, r15; __int64
0x18001a0f9  call    ?Purge@MkvReader@@QEAAJ_J0@Z; MkvReader::Purge(__int64,__int64)
0x18001a0fe  mov     ebx, eax
0x18001a100  test    eax, eax
0x18001a102  js      loc_18001A32E
0x18001a108  cmp     r13, r15
0x18001a10b  jl      short loc_18001A12E
0x18001a10d  cmp     r13, r12
0x18001a110  jge     short loc_18001A12E
0x18001a112  mov     r8, r12; __int64
0x18001a115  mov     rdx, r13; __int64
0x18001a118  lea     rcx, [r14+0B8h]; this
0x18001a11f  call    ?Purge@MkvReader@@QEAAJ_J0@Z; MkvReader::Purge(__int64,__int64)
0x18001a124  mov     ebx, eax
0x18001a126  test    eax, eax
0x18001a128  js      loc_18001A29F
0x18001a12e  jmp     loc_18001A283
0x18001a133  cmp     r13, r15
0x18001a136  jl      loc_18001A1E8
0x18001a13c  cmp     r13, r12
0x18001a13f  jge     loc_18001A1E8
0x18001a145  mov     r8d, 0D14h; int
0x18001a14b  lea     rdx, aMkvmfsourcelib_104; "MkvMfSourceLib::MkvMfSource::PurgeCache"
0x18001a152  lea     rcx, [rsp+0C8h+var_98]; this
0x18001a157  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18001a15c  nop
0x18001a15d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001a164  cmp     [rcx+8], sil
0x18001a168  jz      short loc_18001A1C7
0x18001a16a  cmp     [r14+2B0h], rsi
0x18001a171  jz      short loc_18001A1C7
0x18001a173  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001a178  mov     rdi, rax
0x18001a17b  mov     rcx, [r14+2B0h]
0x18001a182  mov     rdx, [rcx]
0x18001a185  mov     rax, [rdx+128h]
0x18001a18c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a191  mov     ebx, eax
0x18001a193  mov     rcx, [r14+2B0h]
0x18001a19a  mov     rdx, [rcx]
0x18001a19d  mov     rax, [rdx+118h]
0x18001a1a4  lea     rdx, [rsp+0C8h+var_48]
0x18001a1ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1b1  movups  xmm0, xmmword ptr [rax]
0x18001a1b4  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18001a1bc  mov     [rdi+7E0h], ebx
0x18001a1c2  mov     dil, [rsp+0C8h+var_97]
0x18001a1c7  lea     rcx, [r14+0B8h]; this
0x18001a1ce  mov     r8, r12; __int64
0x18001a1d1  mov     rdx, r13; __int64
0x18001a1d4  call    ?Purge@MkvReader@@QEAAJ_J0@Z; MkvReader::Purge(__int64,__int64)
0x18001a1d9  mov     ebx, eax
0x18001a1db  test    eax, eax
0x18001a1dd  js      loc_18001A400
0x18001a1e3  jmp     loc_18001A283
0x18001a1e8  mov     r8d, 0D19h; int
0x18001a1ee  lea     rdx, aMkvmfsourcelib_104; "MkvMfSourceLib::MkvMfSource::PurgeCache"
0x18001a1f5  lea     rcx, [rsp+0C8h+var_98]; this
0x18001a1fa  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18001a1ff  nop
0x18001a200  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18001a207  cmp     [rcx+8], sil
0x18001a20b  jz      short loc_18001A267
0x18001a20d  cmp     [r14+2B0h], rsi
0x18001a214  jz      short loc_18001A267
0x18001a216  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001a21b  mov     rdi, rax
0x18001a21e  mov     rcx, [r14+2B0h]
0x18001a225  mov     rdx, [rcx]
0x18001a228  mov     rax, [rdx+128h]
0x18001a22f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a234  mov     ebx, eax
0x18001a236  mov     rcx, [r14+2B0h]
0x18001a23d  mov     r8, [rcx]
0x18001a240  lea     rdx, [rsp+0C8h+var_58]
0x18001a245  mov     rax, [r8+118h]
0x18001a24c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a251  movups  xmm0, xmmword ptr [rax]
0x18001a254  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18001a25c  mov     [rdi+7E0h], ebx
0x18001a262  mov     dil, [rsp+0C8h+var_97]
0x18001a267  lea     rcx, [r14+0B8h]; this
0x18001a26e  mov     r8, r12; __int64
0x18001a271  mov     rdx, r15; __int64
0x18001a274  call    ?Purge@MkvReader@@QEAAJ_J0@Z; MkvReader::Purge(__int64,__int64)
0x18001a279  mov     ebx, eax
0x18001a27b  test    eax, eax
0x18001a27d  js      loc_18001A4AA
0x18001a283  lea     rcx, [rsp+0C8h+var_98]; this
0x18001a288  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001a28d  mov     [rsp+0C8h+var_97], dil
0x18001a292  mov     rdx, [rsp+0C8h+var_70]
0x18001a297  mov     rax, rdx
0x18001a29a  jmp     loc_180019FFC
0x18001a29f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a2a6  test    rcx, rcx
0x18001a2a9  jnz     short loc_18001A2EC
0x18001a2ab  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001a2b1  mov     rcx, rax
0x18001a2b4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a2bb  test    rax, rax
0x18001a2be  jz      short loc_18001A2DE
0x18001a2c0  mov     rax, [rax]
0x18001a2c3  mov     edx, 7F0h
0x18001a2c8  mov     rax, [rax+8]
0x18001a2cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2d1  test    eax, eax
0x18001a2d3  jz      short loc_18001A2DE
0x18001a2d5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a2dc  jmp     short loc_18001A2EC
0x18001a2de  lea     rcx, qword_1800D6F70; this
0x18001a2e5  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a2ec  cmp     [rcx+8], sil
0x18001a2f0  jz      short loc_18001A317
0x18001a2f2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001a2f7  cmp     [rax+7CCh], ebx
0x18001a2fd  jz      short loc_18001A317
0x18001a2ff  mov     r9d, ebx; int
0x18001a302  mov     r8d, 0D0Dh; int
0x18001a308  lea     rdx, aMkvmfsourcelib_104; "MkvMfSourceLib::MkvMfSource::PurgeCache"
0x18001a30f  mov     rcx, rax; this
0x18001a312  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001a317  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001a31e  jb      loc_18001A3D3
0x18001a324  mov     edx, 0DBh
0x18001a329  jmp     loc_18001A3B4
0x18001a32e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a335  test    rcx, rcx
0x18001a338  jnz     short loc_18001A37B
0x18001a33a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001a340  mov     rcx, rax
0x18001a343  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a34a  test    rax, rax
0x18001a34d  jz      short loc_18001A36D
0x18001a34f  mov     rax, [rax]
0x18001a352  mov     edx, 7F0h
0x18001a357  mov     rax, [rax+8]
0x18001a35b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a360  test    eax, eax
0x18001a362  jz      short loc_18001A36D
0x18001a364  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a36b  jmp     short loc_18001A37B
0x18001a36d  lea     rcx, qword_1800D6F70; this
0x18001a374  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001a37b  cmp     [rcx+8], sil
0x18001a37f  jz      short loc_18001A3A6
0x18001a381  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001a386  cmp     [rax+7CCh], ebx
0x18001a38c  jz      short loc_18001A3A6
0x18001a38e  mov     r9d, ebx; int
0x18001a391  mov     r8d, 0D09h; int
0x18001a397  lea     rdx, aMkvmfsourcelib_104; "MkvMfSourceLib::MkvMfSource::PurgeCache"
0x18001a39e  mov     rcx, rax; this
0x18001a3a1  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18001a3a6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001a3ad  jb      short loc_18001A3D3
0x18001a3af  mov     edx, 0DAh
0x18001a3b4  mov     [rsp+0C8h+var_A8], ebx
0x18001a3b8  mov     r9, r14
0x18001a3bb  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x18001a3c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a3c9  mov     rcx, [rcx+10h]
0x18001a3cd  call    WPP_SF_qD
0x18001a3d2  nop
0x18001a3d3  lea     rcx, [rsp+0C8h+var_98]; this
0x18001a3d8  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001a3dd  nop
0x18001a3de  mov     rcx, qword ptr [rsp+0C8h+var_88]
0x18001a3e3  test    rcx, rcx
0x18001a3e6  jz      short loc_18001A3F9
  ... truncated ...
```
