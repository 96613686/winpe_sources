# RealtimeProtection::MpRtpGetFinalPathName(ulong,wchar_t const *,wchar_t * *,ulong)

- ea: `0x1800402c8`
- end: `0x1800406fe`
- name: `?MpRtpGetFinalPathName@RealtimeProtection@@YAJKPEB_WPEAPEA_WK@Z`
- size: `1078`
- prototype: `__int64 __fastcall(RealtimeProtection *__hidden this, wchar_t *String1, const wchar_t *, wchar_t **, unsigned int)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18001b098`
- `0x18003ffd0`

## callees

- `0x1800402c8`
- `0x180079b8c`
- `0x1800809d0`
- `0x18009d300`
- `0x1801047b4`
- `0x180105f50`
- `0x180106620`
- `0x18010674c`
- `0x180106998`
- `0x180106a08`
- `0x18010cb40`
- `0x18010ce3c`
- `0x18010d1f8`

## import_xrefs

- `KERNEL32!GetFinalPathNameByHandleW` at `0x18004042c`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x18004042c`
- `KERNEL32!CloseHandle` at `0x180040473`
- `KERNEL32!CloseHandle` at `0x1800405c0`
- `KERNEL32!CloseHandle` at `0x180040473`
- `KERNEL32!CloseHandle` at `0x1800405c0`
- `ADVAPI32!RevertToSelf` at `0x180040507`
- `ADVAPI32!RevertToSelf` at `0x180040507`

## pseudocode

```c
__int64 __fastcall RealtimeProtection::MpRtpGetFinalPathName(
        RealtimeProtection *this,
        wchar_t *String1,
        wchar_t *a3,
        wchar_t **a4)
{
  wchar_t *v5; // r15
  unsigned int v6; // edi
  unsigned int v7; // r12d
  int v8; // r13d
  const wchar_t *v9; // rdx
  wchar_t *v10; // rax
  wchar_t **v11; // rdx
  int v12; // eax
  const struct std::nothrow_t *v13; // rdx
  unsigned int v14; // r8d
  unsigned int v15; // ebx
  WCHAR *v16; // rbx
  DWORD v17; // r13d
  wchar_t **v18; // rdi
  int File; // esi
  __int64 LastFailure; // r9
  DWORD v21; // r15d
  unsigned __int64 v22; // rax
  WCHAR *v23; // rax
  WCHAR *v24; // rsi
  DWORD FinalPathNameByHandleW; // eax
  const struct std::nothrow_t *v26; // rdx
  PVOID *v27; // rax
  __int64 v28; // rdx
  int FinalPathName; // eax
  PVOID v31; // rcx
  __int64 v32; // rdx
  WCHAR *v33; // [rsp+40h] [rbp-29h] BYREF
  const wchar_t *v34; // [rsp+48h] [rbp-21h]
  void **v35; // [rsp+50h] [rbp-19h] BYREF
  int v36; // [rsp+58h] [rbp-11h]
  wchar_t v37; // [rsp+60h] [rbp-9h] BYREF
  HANDLE hFile; // [rsp+68h] [rbp-1h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp+7h] BYREF

  v34 = a3;
  v5 = a3;
  v6 = (unsigned int)this;
  v7 = 0;
  v8 = (int)a4;
  v37 = 0;
  if ( (unsigned int)CommonUtil::UtilIsNetworkPath(String1, &v37, (bool *)&v37 + 1, (bool *)a4) == -2147024881 )
    LOBYTE(v37) = 1;
  v10 = (wchar_t *)CommonUtil::UtilSkipPathPrefix(String1, v9);
  hFile = 0;
  if ( HIBYTE(v37) )
  {
    if ( v10 == String1 )
      v10 += 2;
    v11 = (wchar_t **)L"\\\\?\\UNC\\%s";
  }
  else
  {
    v11 = (wchar_t **)L"\\\\?\\%s";
  }
  v12 = CommonUtil::NewSprintfW((CommonUtil *)&hFile, v11, v10);
  v15 = v12;
  if ( v12 >= 0 )
  {
    LOBYTE(v14) = v37;
    v36 = 0;
    v16 = 0;
    v33 = 0;
    v35 = &RealtimeProtection::CThreadImpersonation::`vftable';
    v17 = ((_BYTE)v37 != 0 ? 8 : 0) | v8 & 0xFFFFFFF7;
    if ( (_BYTE)v37 && v6 )
      RealtimeProtection::CThreadImpersonation::Impersonate((RealtimeProtection::CThreadImpersonation *)&v35, v6, v14);
    v18 = (wchar_t **)hFile;
    hObject = (HANDLE)-1LL;
    File = CommonUtil::UtilCreateFile(
             (CommonUtil *)&hObject,
             (const WCHAR *)hFile,
             (const wchar_t *)0x80,
             7u,
             3u,
             0x2000000u,
             0,
             0);
    if ( File < 0 )
    {
      v27 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          WPP_89084a7458c437416cf69f6f341ed2b0_Traceguids,
          (unsigned int)File);
        v27 = (PVOID *)WPP_GLOBAL_Control;
      }
      v28 = -1;
      if ( hObject != (HANDLE)-1LL )
      {
        CloseHandle(hObject);
        v27 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
    else
    {
      v21 = 260;
      hFile = hObject;
      while ( 1 )
      {
        if ( v7 >= 2 )
          goto LABEL_47;
        v22 = 2LL * v21;
        if ( !is_mul_ok(v21, 2u) )
          v22 = -1;
        v23 = (WCHAR *)operator new[](v22, (const struct std::nothrow_t *)&std::nothrow);
        v24 = v23;
        if ( !v23 )
          break;
        FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, v23, v21, v17);
        if ( !FinalPathNameByHandleW )
        {
          operator delete(v24, v26);
LABEL_47:
          File = HrGetLastFailure();
LABEL_17:
          v27 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_18;
        }
        if ( FinalPathNameByHandleW < v21 )
        {
          v16 = v24;
          v33 = v24;
          File = 0;
          goto LABEL_17;
        }
        v21 = FinalPathNameByHandleW;
        _mm_lfence();
        operator delete(v24, v26);
        ++v7;
      }
      v27 = (PVOID *)WPP_GLOBAL_Control;
      File = -2147024882;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_89084a7458c437416cf69f6f341ed2b0_Traceguids, 2147942414LL);
        v27 = (PVOID *)WPP_GLOBAL_Control;
      }
LABEL_18:
      v28 = -1;
      if ( hObject != (HANDLE)-1LL )
      {
        CloseHandle(hObject);
        v27 = (PVOID *)WPP_GLOBAL_Control;
      }
      v5 = (wchar_t *)v34;
    }
    if ( !v36 )
    {
LABEL_22:
      if ( File == -2147024891 )
      {
        if ( !(_BYTE)v37 )
          goto LABEL_59;
        if ( v16 )
        {
          operator delete(v16, (const struct std::nothrow_t *)v28);
          v33 = 0;
        }
        FinalPathName = CommonUtil::UtilGetFinalPathName((CommonUtil *)&v33, v18, (const wchar_t *)v17, LastFailure);
        v16 = v33;
        File = FinalPathName;
        v27 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( File >= 0 )
      {
        File = CommonUtil::UtilStripPathPrefix(v16, (wchar_t *)v28);
        if ( File >= 0 )
        {
          *(_QWORD *)v5 = v16;
          if ( v18 )
            operator delete(v18, (const struct std::nothrow_t *)v28);
          return 0;
        }
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_63;
        v31 = (PVOID)*((_QWORD *)WPP_GLOBAL_Control + 2);
        v32 = 56;
        goto LABEL_62;
      }
LABEL_59:
      if ( v27 == &WPP_GLOBAL_Control || (*((_BYTE *)v27 + 28) & 1) == 0 )
        goto LABEL_63;
      v31 = v27[2];
      v32 = 55;
LABEL_62:
      WPP_SF_d(v31, v32, WPP_e4409c6afbe839b09d832b56b623f3aa_Traceguids, (unsigned int)File);
LABEL_63:
      if ( v16 )
        operator delete(v16, (const struct std::nothrow_t *)v28);
      if ( v18 )
        operator delete(v18, (const struct std::nothrow_t *)v28);
      return (unsigned int)File;
    }
    if ( !RevertToSelf() )
    {
      LastFailure = (unsigned int)HrGetLastFailure();
      v27 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_22;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_e4409c6afbe839b09d832b56b623f3aa_Traceguids, LastFailure);
    }
    v27 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_22;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      54,
      WPP_e4409c6afbe839b09d832b56b623f3aa_Traceguids,
      (unsigned int)v12);
  if ( hFile )
    operator delete(hFile, v13);
  return v15;
}

```

## disassembly

```asm
0x1800402c8  push    rbp
0x1800402ca  push    rbx
0x1800402cb  push    rsi
0x1800402cc  push    rdi
0x1800402cd  push    r12
0x1800402cf  push    r13
0x1800402d1  push    r14
0x1800402d3  push    r15
0x1800402d5  lea     rbp, [rsp-1Fh]
0x1800402da  sub     rsp, 88h
0x1800402e1  mov     rax, cs:__security_cookie
0x1800402e8  xor     rax, rsp
0x1800402eb  mov     [rbp+57h+var_48], rax
0x1800402ef  mov     rbx, rdx
0x1800402f2  mov     [rbp+57h+var_78], r8
0x1800402f6  mov     r15, r8
0x1800402f9  lea     rdx, [rbp+57h+var_60]; wchar_t *
0x1800402fd  mov     edi, ecx
0x1800402ff  lea     r8, [rbp+57h+var_60+1]; bool *
0x180040303  xor     r12d, r12d
0x180040306  mov     rcx, rbx; String1
0x180040309  mov     r13d, r9d
0x18004030c  mov     byte ptr [rbp+57h+var_60], r12b
0x180040310  mov     byte ptr [rbp+57h+var_60+1], r12b
0x180040314  call    ?UtilIsNetworkPath@CommonUtil@@YAJPEB_WPEA_N1@Z; CommonUtil::UtilIsNetworkPath(wchar_t const *,bool *,bool *)
0x180040319  cmp     eax, 8007000Fh
0x18004031e  jz      loc_180040521
0x180040324  mov     rcx, rbx; String1
0x180040327  call    ?UtilSkipPathPrefix@CommonUtil@@YAPEB_WPEB_W@Z; CommonUtil::UtilSkipPathPrefix(wchar_t const *)
0x18004032c  mov     [rbp+57h+hFile], r12
0x180040330  cmp     byte ptr [rbp+57h+var_60+1], r12b
0x180040334  jnz     loc_18004052A
0x18004033a  lea     rdx, aS_0; "\\\\?\\%s"
0x180040341  mov     r8, rax; wchar_t *
0x180040344  lea     rcx, [rbp+57h+hFile]; this
0x180040348  call    ?NewSprintfW@CommonUtil@@YAJPEAPEA_WPEB_WZZ; CommonUtil::NewSprintfW(wchar_t * *,wchar_t const *,...)
0x18004034d  mov     ebx, eax
0x18004034f  test    eax, eax
0x180040351  js      loc_1800404E2
0x180040357  mov     r8b, byte ptr [rbp+57h+var_60]; unsigned int
0x18004035b  and     r13d, 0FFFFFFF7h
0x18004035f  mov     al, r8b
0x180040362  mov     [rbp+57h+var_68], r12d
0x180040366  neg     al
0x180040368  mov     rbx, r12
0x18004036b  lea     rax, ??_7CThreadImpersonation@RealtimeProtection@@6B@; const RealtimeProtection::CThreadImpersonation::`vftable'
0x180040372  mov     [rbp+57h+var_80], rbx
0x180040376  sbb     ecx, ecx
0x180040378  mov     [rbp+57h+var_70], rax
0x18004037c  and     ecx, 8
0x18004037f  or      r13d, ecx
0x180040382  test    r8b, r8b
0x180040385  jnz     loc_18004055F
0x18004038b  mov     rdi, [rbp+57h+hFile]
0x18004038f  lea     rcx, [rbp+57h+hObject]; this
0x180040393  or      rax, 0FFFFFFFFFFFFFFFFh
0x180040397  mov     [rsp+0C0h+var_88], r12; struct _SECURITY_ATTRIBUTES *
0x18004039c  mov     qword ptr [rsp+0C0h+var_90], r12; unsigned int
0x1800403a1  mov     rdx, rdi; void **
0x1800403a4  mov     [rsp+0C0h+var_98], 2000000h; unsigned int
0x1800403ac  mov     [rbp+57h+hObject], rax
0x1800403b0  lea     r9d, [rax+8]; unsigned int
0x1800403b4  mov     [rsp+0C0h+var_A0], 3; unsigned int
0x1800403bc  lea     r8d, [r9+79h]; wchar_t *
0x1800403c0  call    ?UtilCreateFile@CommonUtil@@YAJPEAPEAXPEB_WKKKKPEAU_SECURITY_ATTRIBUTES@@PEAX@Z; CommonUtil::UtilCreateFile(void * *,wchar_t const *,ulong,ulong,ulong,ulong,_SECURITY_ATTRIBUTES *,void *)
0x1800403c5  mov     esi, eax
0x1800403c7  test    eax, eax
0x1800403c9  js      loc_180040577
0x1800403cf  mov     rax, [rbp+57h+hObject]
0x1800403d3  mov     r15d, 104h
0x1800403d9  mov     [rbp+57h+hFile], rax
0x1800403dd  lea     r14, WPP_GLOBAL_Control
0x1800403e4  cmp     r12d, 2
0x1800403e8  jnb     loc_1800405DA
0x1800403ee  mov     ecx, r15d
0x1800403f1  mov     eax, 2
0x1800403f6  mul     rcx
0x1800403f9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180040400  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180040407  cmovb   rax, rcx
0x18004040b  mov     rcx, rax; unsigned __int64
0x18004040e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180040413  mov     rsi, rax
0x180040416  test    rax, rax
0x180040419  jz      loc_1800405E9
0x18004041f  mov     rcx, [rbp+57h+hFile]; hFile
0x180040423  mov     r9d, r13d; dwFlags
0x180040426  mov     r8d, r15d; cchFilePath
0x180040429  mov     rdx, rax; lpszFilePath
0x18004042c  call    cs:__imp_GetFinalPathNameByHandleW
0x180040432  test    eax, eax
0x180040434  jz      loc_1800405D2
0x18004043a  cmp     eax, r15d
0x18004043d  jb      short loc_180040452
0x18004043f  mov     r15d, eax
0x180040442  lfence
0x180040445  mov     rcx, rsi; void *
0x180040448  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004044d  inc     r12d
0x180040450  jmp     short loc_1800403DD
0x180040452  mov     rbx, rsi
0x180040455  xor     r12d, r12d
0x180040458  mov     [rbp+57h+var_80], rbx
0x18004045c  mov     esi, r12d
0x18004045f  mov     rax, cs:WPP_GLOBAL_Control
0x180040466  mov     rcx, [rbp+57h+hObject]; hObject
0x18004046a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004046e  cmp     rcx, rdx
0x180040471  jz      short loc_180040480
0x180040473  call    cs:__imp_CloseHandle
0x180040479  mov     rax, cs:WPP_GLOBAL_Control
0x180040480  mov     r15, [rbp+57h+var_78]
0x180040484  cmp     [rbp+57h+var_68], r12d
0x180040488  jnz     short loc_180040507
0x18004048a  cmp     esi, 80070005h
0x180040490  jz      loc_180040663
0x180040496  test    esi, esi
0x180040498  js      loc_18004069B
0x18004049e  mov     rcx, rbx; this
0x1800404a1  call    ?UtilStripPathPrefix@CommonUtil@@YAJPEA_W@Z; CommonUtil::UtilStripPathPrefix(wchar_t *)
0x1800404a6  mov     esi, eax
0x1800404a8  test    eax, eax
0x1800404aa  js      loc_1800406EA
0x1800404b0  mov     [r15], rbx
0x1800404b3  test    rdi, rdi
0x1800404b6  jz      short loc_1800404C0
0x1800404b8  mov     rcx, rdi; void *
0x1800404bb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800404c0  xor     eax, eax
0x1800404c2  mov     rcx, [rbp+57h+var_48]
0x1800404c6  xor     rcx, rsp; StackCookie
0x1800404c9  call    __security_check_cookie
0x1800404ce  add     rsp, 88h
0x1800404d5  pop     r15
0x1800404d7  pop     r14
0x1800404d9  pop     r13
0x1800404db  pop     r12
0x1800404dd  pop     rdi
0x1800404de  pop     rsi
0x1800404df  pop     rbx
0x1800404e0  pop     rbp
0x1800404e1  retn
0x1800404e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800404e9  lea     r14, WPP_GLOBAL_Control
0x1800404f0  cmp     rcx, r14
0x1800404f3  jnz     short loc_18004053F
0x1800404f5  mov     rcx, [rbp+57h+hFile]; void *
0x1800404f9  test    rcx, rcx
0x1800404fc  jz      short loc_180040503
0x1800404fe  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180040503  mov     eax, ebx
0x180040505  jmp     short loc_1800404C2
0x180040507  call    cs:__imp_RevertToSelf
0x18004050d  test    eax, eax
0x18004050f  jz      loc_180040627
0x180040515  mov     rax, cs:WPP_GLOBAL_Control
0x18004051c  jmp     loc_18004048A
0x180040521  mov     byte ptr [rbp+57h+var_60], 1
0x180040525  jmp     loc_180040324
0x18004052a  cmp     rax, rbx
0x18004052d  jnz     short loc_180040533
0x18004052f  add     rax, 4
0x180040533  lea     rdx, aUncS; "\\\\?\\UNC\\%s"
0x18004053a  jmp     loc_180040341
0x18004053f  test    byte ptr [rcx+1Ch], 1
0x180040543  jz      short loc_1800404F5
0x180040545  mov     rcx, [rcx+10h]
0x180040549  lea     r8, WPP_e4409c6afbe839b09d832b56b623f3aa_Traceguids
0x180040550  mov     edx, 36h ; '6'
0x180040555  mov     r9d, ebx
0x180040558  call    WPP_SF_d
0x18004055d  jmp     short loc_1800404F5
0x18004055f  test    edi, edi
0x180040561  jz      loc_18004038B
0x180040567  mov     edx, edi; unsigned int
0x180040569  lea     rcx, [rbp+57h+var_70]; this
0x18004056d  call    ?Impersonate@CThreadImpersonation@RealtimeProtection@@QEAAJKK@Z; RealtimeProtection::CThreadImpersonation::Impersonate(ulong,ulong)
0x180040572  jmp     loc_18004038B
0x180040577  mov     rax, cs:WPP_GLOBAL_Control
0x18004057e  lea     r14, WPP_GLOBAL_Control
0x180040585  cmp     rax, r14
0x180040588  jz      short loc_1800405AF
0x18004058a  test    byte ptr [rax+1Ch], 1
0x18004058e  jz      short loc_1800405AF
0x180040590  mov     rcx, [rax+10h]
0x180040594  lea     r8, WPP_89084a7458c437416cf69f6f341ed2b0_Traceguids
0x18004059b  mov     edx, 1Ah
0x1800405a0  mov     r9d, esi
0x1800405a3  call    WPP_SF_d
0x1800405a8  mov     rax, cs:WPP_GLOBAL_Control
0x1800405af  mov     rcx, [rbp+57h+hObject]; hObject
0x1800405b3  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800405b7  cmp     rcx, rdx
0x1800405ba  jz      loc_180040484
0x1800405c0  call    cs:__imp_CloseHandle
0x1800405c6  mov     rax, cs:WPP_GLOBAL_Control
0x1800405cd  jmp     loc_180040484
0x1800405d2  mov     rcx, rsi; void *
0x1800405d5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800405da  call    HrGetLastFailure
0x1800405df  mov     esi, eax
0x1800405e1  xor     r12d, r12d
0x1800405e4  jmp     loc_18004045F
0x1800405e9  mov     rax, cs:WPP_GLOBAL_Control
0x1800405f0  mov     esi, 8007000Eh
0x1800405f5  cmp     rax, r14
0x1800405f8  jz      short loc_18004061F
0x1800405fa  test    byte ptr [rax+1Ch], 1
0x1800405fe  jz      short loc_18004061F
0x180040600  mov     rcx, [rax+10h]
0x180040604  lea     r8, WPP_89084a7458c437416cf69f6f341ed2b0_Traceguids
0x18004060b  mov     edx, 14h
0x180040610  mov     r9d, esi
0x180040613  call    WPP_SF_d
0x180040618  mov     rax, cs:WPP_GLOBAL_Control
0x18004061f  xor     r12d, r12d
0x180040622  jmp     loc_180040466
0x180040627  call    HrGetLastFailure
0x18004062c  mov     r9d, eax
0x18004062f  mov     rax, cs:WPP_GLOBAL_Control
0x180040636  cmp     rax, r14
0x180040639  jz      loc_18004048A
0x18004063f  test    byte ptr [rax+1Ch], 2
0x180040643  jz      loc_18004048A
0x180040649  mov     rcx, [rax+10h]
0x18004064d  lea     r8, WPP_e4409c6afbe839b09d832b56b623f3aa_Traceguids
0x180040654  mov     edx, 22h ; '"'
0x180040659  call    WPP_SF_d
0x18004065e  jmp     loc_180040515
0x180040663  cmp     byte ptr [rbp+57h+var_60], r12b
0x180040667  jz      short loc_18004069B
0x180040669  test    rbx, rbx
0x18004066c  jz      short loc_18004067A
0x18004066e  mov     rcx, rbx; void *
0x180040671  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180040676  mov     [rbp+57h+var_80], r12
0x18004067a  mov     r8d, r13d; wchar_t *
0x18004067d  lea     rcx, [rbp+57h+var_80]; this
0x180040681  mov     rdx, rdi; wchar_t **
0x180040684  call    ?UtilGetFinalPathName@CommonUtil@@YAJPEAPEA_WPEB_WK@Z; CommonUtil::UtilGetFinalPathName(wchar_t * *,wchar_t const *,ulong)
0x180040689  mov     rbx, [rbp+57h+var_80]
0x18004068d  mov     esi, eax
0x18004068f  mov     rax, cs:WPP_GLOBAL_Control
0x180040696  jmp     loc_180040496
0x18004069b  cmp     rax, r14
0x18004069e  jz      short loc_1800406C9
0x1800406a0  test    byte ptr [rax+1Ch], 1
0x1800406a4  jz      short loc_1800406C9
0x1800406a6  mov     rcx, [rax+10h]
0x1800406aa  mov     edx, 37h ; '7'
0x1800406af  jmp     short loc_1800406BA
0x1800406b1  mov     rcx, [rcx+10h]
0x1800406b5  mov     edx, 38h ; '8'
0x1800406ba  mov     r9d, esi
0x1800406bd  lea     r8, WPP_e4409c6afbe839b09d832b56b623f3aa_Traceguids
0x1800406c4  call    WPP_SF_d
0x1800406c9  test    rbx, rbx
0x1800406cc  jz      short loc_1800406D6
0x1800406ce  mov     rcx, rbx; void *
0x1800406d1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800406d6  test    rdi, rdi
0x1800406d9  jz      short loc_1800406E3
0x1800406db  mov     rcx, rdi; void *
0x1800406de  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800406e3  mov     eax, esi
0x1800406e5  jmp     loc_1800404C2
0x1800406ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800406f1  cmp     rcx, r14
0x1800406f4  jz      short loc_1800406C9
0x1800406f6  test    byte ptr [rcx+1Ch], 1
0x1800406fa  jz      short loc_1800406C9
0x1800406fc  jmp     short loc_1800406B1
```
