# CServerVCChannel::Initialize(IWTSVirtualChannelCallback *,void *,char const *,ulong,__MIDL___MIDL_itf_tscaddon_0000_0007_0001,int,IAPCThread *,ChannelType)

- ea: `0x140026358`
- end: `0x140026855`
- name: `?Initialize@CServerVCChannel@@QEAAJPEAUIWTSVirtualChannelCallback@@PEAXPEBDKW4__MIDL___MIDL_itf_tscaddon_0000_0007_0001@@HPEAVIAPCThread@@W4ChannelType@@@Z`
- size: `1277`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140025cf0`

## callees

- `0x1400028b4`
- `0x1400028f4`
- `0x140004b1c`
- `0x140005704`
- `0x140005750`
- `0x1400081ac`
- `0x1400081d0`
- `0x140009ef8`
- `0x14000ea3c`
- `0x140011054`
- `0x140026048`
- `0x140026358`
- `0x14006b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400265c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026660`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400265c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026660`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1400265b7`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x1400265b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400265aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400265aa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400267db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400267db`
- `ntdll!RtlMultiByteToUnicodeN` at `0x14002659f`
- `ntdll!RtlMultiByteToUnicodeN` at `0x14002659f`
- `WINSTA!WinStationVirtualOpenEx` at `0x140026655`
- `WINSTA!WinStationVirtualOpenEx` at `0x140026655`
- `WTSAPI32!WTSVirtualChannelClose` at `0x1400267c0`
- `WTSAPI32!WTSVirtualChannelClose` at `0x1400267c0`

## string_xrefs

- `0x140026432`: `StringCbCopyA failed`
- `0x1400266b2`: `CServerVCChannel::CreateDynamicChannel`
- `0x140026721`: `CServerVCChannel::CreateStaticChannel`
- `0x1400267a3`: `pAPCThread->PostAPC(static_IssueARead) failed`

## pseudocode

```c
__int64 __fastcall CServerVCChannel::Initialize(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4,
        unsigned int a5,
        int a6,
        int a7,
        __int64 a8,
        int a9)
{
  const char *v13; // rdx
  _QWORD *v15; // rsi
  WCHAR *v16; // r12
  __int64 v17; // rbx
  _QWORD *v18; // r14
  signed int LastError; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v21; // edx
  const char *v22; // rcx
  void *v23; // rax
  unsigned int v24; // eax
  int v25; // edx
  const char *v26; // rcx
  __int64 v27; // rbx
  __int64 v28; // rax
  int v29; // r15d
  DWORD CurrentProcessId; // eax
  unsigned int v31; // eax
  bool v32; // cf
  __int64 v33; // rax
  signed int v34; // eax
  __int64 v35; // rcx
  void *v36; // rcx
  void *v37; // rcx
  void *v38; // rcx
  int v39; // eax
  DWORD pSessionId[22]; // [rsp+30h] [rbp-58h] BYREF
  ULONG BytesInUnicodeString; // [rsp+90h] [rbp+8h] BYREF

  if ( !(unsigned int)CTSCriticalSection::Initialize((CTSCriticalSection *)(a1 + 56)) )
    return 2147500037LL;
  v15 = (_QWORD *)(a1 + 72);
  v16 = 0;
  if ( a2 != *(_QWORD *)(a1 + 72) )
  {
    TCntPtr<IRdpHintApiEventSink>::SafeRelease(a1 + 72);
    *v15 = a2;
    TCntPtr<IRdrVirtualChannel>::SafeAddRef(a1 + 72);
  }
  v17 = a8;
  v18 = (_QWORD *)(a1 + 400);
  if ( a8 != *(_QWORD *)(a1 + 400) )
  {
    TCntPtr<IRdpHintApiEventSink>::SafeRelease(a1 + 400);
    *v18 = v17;
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
  }
  if ( a4 )
  {
    LastError = StringCbCopyA((char *)(a1 + 80), 0x104u, a4);
    if ( LastError < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v21 = 20;
        v22 = "StringCbCopyA failed";
LABEL_14:
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v21,
          (unsigned int)WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids,
          CurrentThreadActivityIdPrefix,
          (__int64)v22,
          LastError,
          *(_QWORD *)pSessionId);
        goto LABEL_68;
      }
      goto LABEL_68;
    }
  }
  else
  {
    *(_BYTE *)(a1 + 80) = 0;
  }
  *(_DWORD *)(a1 + 36) |= 2u;
  if ( a3 )
  {
    *(_QWORD *)(a1 + 344) = a3;
LABEL_18:
    *(_DWORD *)(a1 + 360) = 1;
    goto LABEL_19;
  }
  if ( a9 == 1 )
  {
    v27 = -1;
    v28 = -1;
    do
      ++v28;
    while ( a4[v28] );
    v29 = v28 + 1;
    v16 = (WCHAR *)operator new(saturated_mul((unsigned int)(v28 + 1), 2u));
    if ( !v16 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_33;
      }
      v24 = RdpWppGetCurrentThreadActivityIdPrefix();
      v25 = 22;
      v26 = "WCHAR[]";
      goto LABEL_32;
    }
    BytesInUnicodeString = 0;
    do
      ++v27;
    while ( a4[v27] );
    RtlMultiByteToUnicodeN(v16, 2 * v29, &BytesInUnicodeString, a4, v27 + 1);
    pSessionId[0] = 0;
    CurrentProcessId = GetCurrentProcessId();
    if ( !ProcessIdToSessionId(CurrentProcessId, pSessionId) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v31 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids,
          v31,
          LastError);
      }
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError >= 0 )
        LastError = -2147467259;
      goto LABEL_68;
    }
    v32 = a7 != 0;
    a7 = -a7;
    v33 = WinStationVirtualOpenEx(0, a5, a4, (2 * a6) | (v32 ? 9 : 1));
    if ( v33 )
    {
      *(_QWORD *)(a1 + 344) = v33;
      goto LABEL_18;
    }
    v34 = GetLastError();
    LastError = v34;
    if ( v34 > 0 )
      LastError = (unsigned __int16)v34 | 0x80070000;
    if ( LastError < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v21 = 24;
        v22 = "CServerVCChannel::CreateDynamicChannel";
        goto LABEL_14;
      }
LABEL_68:
      v36 = *(void **)(a1 + 352);
      if ( v36 )
      {
        WTSVirtualChannelClose(v36);
        *(_QWORD *)(a1 + 352) = 0;
      }
      else
      {
        v37 = *(void **)(a1 + 344);
        if ( !v37 )
        {
LABEL_73:
          if ( *v18 )
          {
            TCntPtr<IRdpHintApiEventSink>::SafeRelease(a1 + 400);
            *v18 = 0;
          }
          if ( *v15 )
          {
            TCntPtr<IRdpHintApiEventSink>::SafeRelease(a1 + 72);
            *v15 = 0;
            TCntPtr<IRdrVirtualChannel>::SafeAddRef(a1 + 72);
          }
          v38 = *(void **)(a1 + 368);
          if ( v38 )
          {
            operator delete(v38);
            *(_QWORD *)(a1 + 368) = 0;
          }
          v39 = *(_DWORD *)(a1 + 36);
          if ( (v39 & 2) != 0 )
            *(_DWORD *)(a1 + 36) = v39 | 4;
          goto LABEL_81;
        }
        CloseHandle(v37);
      }
      *(_QWORD *)(a1 + 344) = 0;
      goto LABEL_73;
    }
  }
  else
  {
    if ( a9 )
    {
      LastError = -2147024809;
      goto LABEL_68;
    }
    LastError = CServerVCChannel::CreateStaticChannel((CServerVCChannel *)a1, v13, a5);
    if ( LastError < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v21 = 25;
        v22 = "CServerVCChannel::CreateStaticChannel";
        goto LABEL_14;
      }
      goto LABEL_68;
    }
  }
LABEL_19:
  v23 = operator new(0x648u);
  *(_QWORD *)(a1 + 368) = v23;
  if ( !v23 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_33;
    }
    v24 = RdpWppGetCurrentThreadActivityIdPrefix();
    v25 = 26;
    v26 = "BYTE[]";
LABEL_32:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v25,
      (unsigned int)WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids,
      v24,
      (__int64)v26);
LABEL_33:
    LastError = -2147024882;
    goto LABEL_68;
  }
  v35 = *(_QWORD *)(a1 + 40);
  *(_DWORD *)(a1 + 376) = 1608;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 8LL))(v35);
  LastError = (*(__int64 (__fastcall **)(_QWORD, void (__fastcall *)(unsigned __int64), __int64))(*(_QWORD *)*v18 + 24LL))(
                *v18,
                CServerVCChannel::static_IssueARead,
                a1);
  if ( LastError )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 40) + 16LL))(*(_QWORD *)(a1 + 40));
    if ( LastError < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v21 = 27;
      v22 = "pAPCThread->PostAPC(static_IssueARead) failed";
      goto LABEL_14;
    }
    goto LABEL_68;
  }
LABEL_81:
  if ( v16 )
    operator delete(v16);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140026358  push    rbx
0x14002635a  push    rbp
0x14002635b  push    rsi
0x14002635c  push    rdi
0x14002635d  push    r12
0x14002635f  push    r13
0x140026361  push    r14
0x140026363  push    r15
0x140026365  sub     rsp, 48h
0x140026369  mov     rdi, rcx
0x14002636c  mov     rbp, r9
0x14002636f  add     rcx, 38h ; '8'; this
0x140026373  mov     r15, r8
0x140026376  mov     rbx, rdx
0x140026379  call    ?Initialize@CTSCriticalSection@@QEAAHXZ; CTSCriticalSection::Initialize(void)
0x14002637e  xor     r13d, r13d
0x140026381  test    eax, eax
0x140026383  jnz     short loc_14002638F
0x140026385  mov     eax, 80004005h
0x14002638a  jmp     loc_140026844
0x14002638f  lea     rsi, [rdi+48h]
0x140026393  mov     r12, r13
0x140026396  cmp     rbx, [rsi]
0x140026399  jz      short loc_1400263AE
0x14002639b  mov     rcx, rsi
0x14002639e  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x1400263a3  mov     rcx, rsi
0x1400263a6  mov     [rsi], rbx
0x1400263a9  call    ?SafeAddRef@?$TCntPtr@VIRdrVirtualChannel@@@@AEAAXXZ; TCntPtr<IRdrVirtualChannel>::SafeAddRef(void)
0x1400263ae  mov     rbx, [rsp+88h+arg_38]
0x1400263b6  lea     r14, [rdi+190h]
0x1400263bd  cmp     rbx, [r14]
0x1400263c0  jz      short loc_1400263E1
0x1400263c2  mov     rcx, r14
0x1400263c5  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x1400263ca  mov     [r14], rbx
0x1400263cd  test    rbx, rbx
0x1400263d0  jz      short loc_1400263E1
0x1400263d2  mov     rax, [rbx]
0x1400263d5  mov     rcx, rbx
0x1400263d8  mov     rax, [rax+8]
0x1400263dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400263e1  test    rbp, rbp
0x1400263e4  jz      short loc_140026461
0x1400263e6  mov     r8, rbp; char *
0x1400263e9  lea     rcx, [rdi+50h]; char *
0x1400263ed  mov     edx, 104h; unsigned __int64
0x1400263f2  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x1400263f7  mov     ebx, eax
0x1400263f9  test    eax, eax
0x1400263fb  jns     short loc_140026465
0x1400263fd  mov     rcx, cs:WPP_GLOBAL_Control
0x140026404  lea     rax, WPP_GLOBAL_Control
0x14002640b  cmp     rcx, rax
0x14002640e  jz      loc_1400267B4
0x140026414  test    byte ptr [rcx+1Ch], 8
0x140026418  jz      loc_1400267B4
0x14002641e  cmp     byte ptr [rcx+19h], 2
0x140026422  jb      loc_1400267B4
0x140026428  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14002642d  mov     edx, 14h
0x140026432  lea     rcx, aStringcbcopyaF; "StringCbCopyA failed"
0x140026439  mov     [rsp+88h+var_60], ebx
0x14002643d  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x140026444  mov     qword ptr [rsp+88h+BytesInMultiByteString], rcx
0x140026449  mov     r9d, eax
0x14002644c  mov     rcx, cs:WPP_GLOBAL_Control
0x140026453  mov     rcx, [rcx+10h]
0x140026457  call    WPP_SF_DsD
0x14002645c  jmp     loc_1400267B4
0x140026461  mov     [rdi+50h], r13b
0x140026465  or      dword ptr [rdi+24h], 2
0x140026469  test    r15, r15
0x14002646c  jz      short loc_1400264D9
0x14002646e  mov     [rdi+158h], r15
0x140026475  mov     dword ptr [rdi+168h], 1
0x14002647f  mov     ebx, 648h
0x140026484  mov     ecx, ebx; Size
0x140026486  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002648b  mov     [rdi+170h], rax
0x140026492  test    rax, rax
0x140026495  jnz     loc_14002672D
0x14002649b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400264a2  lea     rax, WPP_GLOBAL_Control
0x1400264a9  cmp     rcx, rax
0x1400264ac  jz      loc_14002656B
0x1400264b2  test    byte ptr [rcx+1Ch], 8
0x1400264b6  jz      loc_14002656B
0x1400264bc  cmp     byte ptr [rcx+19h], 2
0x1400264c0  jb      loc_14002656B
0x1400264c6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400264cb  mov     edx, 1Ah
0x1400264d0  lea     rcx, aByte_0; "BYTE[]"
0x1400264d7  jmp     short loc_14002654C
0x1400264d9  mov     eax, [rsp+88h+arg_40]
0x1400264e0  cmp     eax, 1
0x1400264e3  jnz     loc_1400266CA
0x1400264e9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400264ed  mov     rax, rbx
0x1400264f0  inc     rax
0x1400264f3  cmp     [rax+rbp], r13b
0x1400264f7  jnz     short loc_1400264F0
0x1400264f9  lea     r15d, [rax+1]
0x1400264fd  mov     eax, 2
0x140026502  mov     ecx, r15d
0x140026505  mul     rcx
0x140026508  cmovb   rax, rbx
0x14002650c  mov     rcx, rax; Size
0x14002650f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140026514  mov     r12, rax
0x140026517  test    rax, rax
0x14002651a  jnz     short loc_140026575
0x14002651c  mov     rcx, cs:WPP_GLOBAL_Control
0x140026523  lea     rax, WPP_GLOBAL_Control
0x14002652a  cmp     rcx, rax
0x14002652d  jz      short loc_14002656B
0x14002652f  test    byte ptr [rcx+1Ch], 8
0x140026533  jz      short loc_14002656B
0x140026535  cmp     byte ptr [rcx+19h], 2
0x140026539  jb      short loc_14002656B
0x14002653b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140026540  lea     edx, [r12+16h]
0x140026545  lea     rcx, aWchar; "WCHAR[]"
0x14002654c  mov     qword ptr [rsp+88h+BytesInMultiByteString], rcx
0x140026551  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x140026558  mov     rcx, cs:WPP_GLOBAL_Control
0x14002655f  mov     r9d, eax
0x140026562  mov     rcx, [rcx+10h]
0x140026566  call    WPP_SF_Ds
0x14002656b  mov     ebx, 8007000Eh
0x140026570  jmp     loc_1400267B4
0x140026575  mov     [rsp+88h+BytesInUnicodeString], r13d
0x14002657d  inc     rbx
0x140026580  cmp     [rbx+rbp], r13b
0x140026584  jnz     short loc_14002657D
0x140026586  lea     eax, [rbx+1]
0x140026589  mov     r9, rbp; MultiByteString
0x14002658c  lea     edx, [r15+r15]; MaxBytesInUnicodeString
0x140026590  mov     [rsp+88h+BytesInMultiByteString], eax; BytesInMultiByteString
0x140026594  lea     r8, [rsp+88h+BytesInUnicodeString]; BytesInUnicodeString
0x14002659c  mov     rcx, r12; UnicodeString
0x14002659f  call    cs:__imp_RtlMultiByteToUnicodeN
0x1400265a5  mov     [rsp+88h+pSessionId], r13d
0x1400265aa  call    cs:__imp_GetCurrentProcessId
0x1400265b0  mov     ecx, eax; dwProcessId
0x1400265b2  lea     rdx, [rsp+88h+pSessionId]; pSessionId
0x1400265b7  call    cs:__imp_ProcessIdToSessionId
0x1400265bd  test    eax, eax
0x1400265bf  jnz     short loc_14002662C
0x1400265c1  call    cs:__imp_GetLastError
0x1400265c7  mov     ebx, eax
0x1400265c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400265d0  lea     rax, WPP_GLOBAL_Control
0x1400265d7  cmp     rcx, rax
0x1400265da  jz      short loc_140026610
0x1400265dc  test    byte ptr [rcx+1Ch], 8
0x1400265e0  jz      short loc_140026610
0x1400265e2  cmp     byte ptr [rcx+19h], 2
0x1400265e6  jb      short loc_140026610
0x1400265e8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400265ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400265f4  lea     r8, WPP_12a54374ce1a3d6eb8f95169a7d52c65_Traceguids
0x1400265fb  mov     edx, 17h
0x140026600  mov     [rsp+88h+BytesInMultiByteString], ebx
0x140026604  mov     r9d, eax
0x140026607  mov     rcx, [rcx+10h]
0x14002660b  call    WPP_SF_Dd
0x140026610  test    ebx, ebx
0x140026612  jle     short loc_14002661D
0x140026614  movzx   ebx, bx
0x140026617  or      ebx, 80070000h
0x14002661d  test    ebx, ebx
0x14002661f  mov     eax, 80004005h
0x140026624  cmovns  ebx, eax
0x140026627  jmp     loc_1400267B4
0x14002662c  mov     eax, [rsp+88h+arg_28]
0x140026633  mov     r8, rbp
0x140026636  neg     [rsp+88h+arg_30]
0x14002663d  mov     edx, [rsp+88h+arg_20]
0x140026644  sbb     r9d, r9d
0x140026647  add     eax, eax
0x140026649  and     r9d, 8
0x14002664d  xor     ecx, ecx
0x14002664f  inc     r9d
0x140026652  or      r9d, eax
0x140026655  call    cs:__imp_WinStationVirtualOpenEx
0x14002665b  test    rax, rax
0x14002665e  jnz     short loc_1400266BE
0x140026660  call    cs:__imp_GetLastError
0x140026666  mov     ebx, eax
0x140026668  test    eax, eax
0x14002666a  jle     short loc_140026675
0x14002666c  movzx   ebx, ax
0x14002666f  or      ebx, 80070000h
0x140026675  test    ebx, ebx
0x140026677  jns     loc_14002647F
0x14002667d  mov     rcx, cs:WPP_GLOBAL_Control
0x140026684  lea     rax, WPP_GLOBAL_Control
0x14002668b  cmp     rcx, rax
0x14002668e  jz      loc_1400267B4
0x140026694  test    byte ptr [rcx+1Ch], 8
0x140026698  jz      loc_1400267B4
0x14002669e  cmp     byte ptr [rcx+19h], 2
0x1400266a2  jb      loc_1400267B4
0x1400266a8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400266ad  mov     edx, 18h
0x1400266b2  lea     rcx, aCservervcchann_0; "CServerVCChannel::CreateDynamicChannel"
0x1400266b9  jmp     loc_140026439
0x1400266be  mov     [rdi+158h], rax
0x1400266c5  jmp     loc_140026475
0x1400266ca  test    eax, eax
0x1400266cc  jnz     loc_1400267AF
0x1400266d2  mov     r8d, [rsp+88h+arg_20]; unsigned int
0x1400266da  mov     rcx, rdi; this
0x1400266dd  call    ?CreateStaticChannel@CServerVCChannel@@QEAAJPEBDK@Z; CServerVCChannel::CreateStaticChannel(char const *,ulong)
0x1400266e2  mov     ebx, eax
0x1400266e4  test    eax, eax
0x1400266e6  jns     loc_14002647F
0x1400266ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400266f3  lea     rax, WPP_GLOBAL_Control
0x1400266fa  cmp     rcx, rax
0x1400266fd  jz      loc_1400267B4
0x140026703  test    byte ptr [rcx+1Ch], 8
0x140026707  jz      loc_1400267B4
0x14002670d  cmp     byte ptr [rcx+19h], 2
0x140026711  jb      loc_1400267B4
0x140026717  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14002671c  mov     edx, 19h
0x140026721  lea     rcx, aCservervcchann; "CServerVCChannel::CreateStaticChannel"
0x140026728  jmp     loc_140026439
0x14002672d  mov     rcx, [rdi+28h]
0x140026731  mov     [rdi+178h], ebx
0x140026737  mov     rax, [rcx]
0x14002673a  mov     rax, [rax+8]
0x14002673e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026743  mov     rcx, [r14]
0x140026746  lea     rdx, ?static_IssueARead@CServerVCChannel@@CAX_K@Z; CServerVCChannel::static_IssueARead(unsigned __int64)
0x14002674d  mov     r8, rdi
0x140026750  mov     rax, [rcx]
0x140026753  mov     rax, [rax+18h]
0x140026757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002675c  mov     ebx, eax
0x14002675e  test    eax, eax
0x140026760  jz      loc_140026835
0x140026766  mov     rcx, [rdi+28h]
0x14002676a  mov     rax, [rcx]
0x14002676d  mov     rax, [rax+10h]
0x140026771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026776  test    ebx, ebx
0x140026778  jns     short loc_1400267B4
0x14002677a  mov     rcx, cs:WPP_GLOBAL_Control
0x140026781  lea     rax, WPP_GLOBAL_Control
0x140026788  cmp     rcx, rax
0x14002678b  jz      short loc_1400267B4
0x14002678d  test    byte ptr [rcx+1Ch], 8
0x140026791  jz      short loc_1400267B4
0x140026793  cmp     byte ptr [rcx+19h], 2
0x140026797  jb      short loc_1400267B4
0x140026799  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14002679e  mov     edx, 1Bh
0x1400267a3  lea     rcx, aPapcthreadPost; "pAPCThread->PostAPC(static_IssueARead) "...
0x1400267aa  jmp     loc_140026439
0x1400267af  mov     ebx, 80070057h
0x1400267b4  mov     rcx, [rdi+160h]; hChannelHandle
0x1400267bb  test    rcx, rcx
0x1400267be  jz      short loc_1400267CF
0x1400267c0  call    cs:__imp_WTSVirtualChannelClose
0x1400267c6  mov     [rdi+160h], r13
0x1400267cd  jmp     short loc_1400267E1
0x1400267cf  mov     rcx, [rdi+158h]; hObject
0x1400267d6  test    rcx, rcx
0x1400267d9  jz      short loc_1400267E8
0x1400267db  call    cs:__imp_CloseHandle
0x1400267e1  mov     [rdi+158h], r13
0x1400267e8  cmp     [r14], r13
0x1400267eb  jz      short loc_1400267F8
0x1400267ed  mov     rcx, r14
0x1400267f0  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x1400267f5  mov     [r14], r13
0x1400267f8  cmp     [rsi], r13
0x1400267fb  jz      short loc_140026810
0x1400267fd  mov     rcx, rsi
0x140026800  call    ?SafeRelease@?$TCntPtr@VIRdpHintApiEventSink@@@@AEAAXXZ; TCntPtr<IRdpHintApiEventSink>::SafeRelease(void)
0x140026805  mov     rcx, rsi
0x140026808  mov     [rsi], r13
0x14002680b  call    ?SafeAddRef@?$TCntPtr@VIRdrVirtualChannel@@@@AEAAXXZ; TCntPtr<IRdrVirtualChannel>::SafeAddRef(void)
0x140026810  mov     rcx, [rdi+170h]; Block
0x140026817  test    rcx, rcx
0x14002681a  jz      short loc_140026828
0x14002681c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140026821  mov     [rdi+170h], r13
0x140026828  mov     eax, [rdi+24h]
0x14002682b  test    al, 2
0x14002682d  jz      short loc_140026835
0x14002682f  or      eax, 4
0x140026832  mov     [rdi+24h], eax
0x140026835  test    r12, r12
0x140026838  jz      short loc_140026842
0x14002683a  mov     rcx, r12; Block
0x14002683d  call    ??3@YAXPEAX@Z; operator delete(void *)
  ... truncated ...
```
