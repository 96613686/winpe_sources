# CRDPPerfMonLogger::GetTransportPerfMonSessionByConnectionId(ulong,ushort const *,IRdpPerfMonSession * *)

- ea: `0x180008a80`
- end: `0x18000904f`
- name: `?GetTransportPerfMonSessionByConnectionId@CRDPPerfMonLogger@@UEAAJKPEBGPEAPEAVIRdpPerfMonSession@@@Z`
- size: `1487`
- prototype: `__int64 __fastcall(CRDPPerfMonLogger *__hidden this, unsigned int, const unsigned __int16 *, struct IRdpPerfMonSession **)`
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x180008a80`
- `0x180009058`
- `0x180009088`
- `0x1800090d4`
- `0x1800091a8`
- `0x18002e600`
- `0x180033964`
- `0x180033da0`
- `0x180059838`
- `0x1800598d0`
- `0x180072abc`
- `0x180072b54`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e5d`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180008ae3`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180008ae3`
- `RDPBASE!PAL_System_CritSecLeave` at `0x180008b2b`
- `RDPBASE!PAL_System_CritSecLeave` at `0x180008b2b`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x180008d48`
- `api-ms-win-core-perfcounters-l1-1-0!PerfCreateInstance` at `0x180008d48`

## string_xrefs

- `0x180008f26`: `failed to create a session instance name for perf counter`
- `0x180008fc9`: `Failed to create a session instance name for perf counter`

## pseudocode

```c
__int64 __fastcall CRDPPerfMonLogger::GetTransportPerfMonSessionByConnectionId(
        CRDPPerfMonLogger *this,
        __int64 a2,
        const unsigned __int16 *a3,
        struct IRdpPerfMonSession **a4)
{
  unsigned int v6; // r15d
  PVOID *v7; // rax
  _QWORD *v8; // rdi
  _QWORD *v9; // rbx
  signed int v10; // ebp
  _QWORD *v12; // rsi
  _QWORD *v13; // r14
  _QWORD *v14; // rbp
  unsigned int CurrentThreadActivityIdPrefix; // eax
  _QWORD *v16; // rax
  HANDLE v17; // rdx
  PPERF_COUNTERSET_INSTANCE Instance; // rax
  PVOID *v19; // rax
  unsigned int v20; // eax
  int v21; // edx
  const char *v22; // rcx
  unsigned int v23; // eax
  signed int LastError; // eax
  int v25; // esi
  unsigned int v26; // eax
  unsigned int v27; // eax
  int v28; // esi
  unsigned int v29; // eax
  unsigned int v30; // eax
  __int64 v31; // [rsp+20h] [rbp-288h]
  __int64 v32; // [rsp+28h] [rbp-280h]
  WCHAR Name[264]; // [rsp+40h] [rbp-268h] BYREF

  v6 = a2;
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dqd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      WPP_1c81c145608e3855819657761c2bbeb5_Traceguids,
      CurrentThreadActivityIdPrefix,
      this,
      v6);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  v8 = (_QWORD *)((char *)this + 504);
  if ( *((_DWORD *)this + 128) )
  {
    PAL_System_CritSecEnter(*v8, a2, a3);
    v7 = (PVOID *)WPP_GLOBAL_Control;
  }
  v9 = 0;
  if ( !a4 )
  {
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 && *((_BYTE *)v7 + 25) >= 2u )
    {
      v23 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        (unsigned int)WPP_1c81c145608e3855819657761c2bbeb5_Traceguids,
        v23,
        (__int64)"ppSession");
    }
    v10 = -2147467261;
    goto LABEL_7;
  }
  *a4 = 0;
  v12 = (_QWORD *)*((_QWORD *)this + 60);
  while ( v12 )
  {
    v13 = (_QWORD *)*v12;
    v14 = (_QWORD *)v12[1];
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*v12 + 40LL) + 8LL))(*(_QWORD *)(*v12 + 40LL));
    if ( *((_DWORD *)v13 + 16) == v6 )
    {
      v10 = 0;
LABEL_18:
      *a4 = (struct IRdpPerfMonSession *)v13;
      goto LABEL_7;
    }
    v12 = v14;
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v13[5] + 16LL))(v13[5]);
  }
  v16 = operator new(0x58u);
  v13 = v16;
  if ( v16 )
  {
    v17 = RDPPerfMonCounters;
    *v16 = &RdpXInterfaceTexture2DProperties::`vftable';
    v16[3] = "CRDPPerfMonSession";
    *((_DWORD *)v16 + 8) = -607474739;
    *((_DWORD *)v16 + 9) = 1;
    v16[1] = &CClipLevelCallback::`vftable'{for `INonDelegatingUnknown'};
    v16[2] = &CTSUnknown::`vftable'{for `CTSObject'};
    *((_DWORD *)v16 + 12) = 0;
    v16[5] = v16 + 1;
    *v16 = &CRDPPerfMonSession::`vftable';
    v16[1] = &CRDPPerfMonSession::`vftable'{for `INonDelegatingUnknown'};
    v16[2] = &CRDPPerfMonSession::`vftable'{for `CTSObject'};
    v16[10] = 0;
    v16[9] = 0;
    *((_DWORD *)v16 + 16) = v6;
    v16[7] = v17;
    if ( this )
    {
      TCntPtr<CRDPSQMLogger>::SafeRelease(v16 + 10);
      v13[10] = this;
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 8LL))(*((_QWORD *)this + 5));
    }
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v13[5] + 8LL))(v13[5]);
    if ( a3 && *a3 )
    {
      LODWORD(v31) = v6;
      v10 = StringCchPrintfW(Name, 0x104u, L"%s %d", a3, v31);
      if ( v10 < 0 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_39;
        }
        v20 = RdpWppGetCurrentThreadActivityIdPrefix();
        v21 = 26;
        v22 = "failed to create a session instance name for perf counter";
        goto LABEL_38;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v27 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_1c81c145608e3855819657761c2bbeb5_Traceguids, v27);
      }
      v10 = StringCchPrintfW(Name, 0x104u, L"RDP-Tcp %d", v6);
      if ( v10 < 0 )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_39;
        }
        v20 = RdpWppGetCurrentThreadActivityIdPrefix();
        v21 = 28;
        v22 = "Failed to create a session instance name for perf counter";
        goto LABEL_38;
      }
    }
    Instance = PerfCreateInstance((HANDLE)v13[7], &NetworkPerSessionGuid, Name, *((_DWORD *)v13 + 16));
    v13[9] = Instance;
    if ( Instance )
    {
      v19 = (PVOID *)WPP_GLOBAL_Control;
      v10 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v28 = *((_DWORD *)v13 + 16);
        v29 = RdpWppGetCurrentThreadActivityIdPrefix();
        LODWORD(v32) = v28;
        WPP_SF_DSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          32,
          (unsigned int)WPP_1c81c145608e3855819657761c2bbeb5_Traceguids,
          v29,
          (__int64)Name,
          v32);
LABEL_32:
        if ( CVPtrList::AddTail((CRDPPerfMonLogger *)((char *)this + 56), v13) )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v13[5] + 8LL))(v13[5]);
        goto LABEL_18;
      }
    }
    else
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      v19 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v25 = *((_DWORD *)v13 + 16);
        v26 = RdpWppGetCurrentThreadActivityIdPrefix();
        LODWORD(v32) = v25;
        WPP_SF_DSd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          (unsigned int)WPP_1c81c145608e3855819657761c2bbeb5_Traceguids,
          v26,
          (__int64)Name,
          v32);
        v19 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
    if ( v10 >= 0 )
      goto LABEL_32;
    if ( v19 == &WPP_GLOBAL_Control || (*((_BYTE *)v19 + 28) & 8) == 0 || *((_BYTE *)v19 + 25) < 2u )
    {
LABEL_39:
      v9 = v13;
      goto LABEL_7;
    }
    v20 = RdpWppGetCurrentThreadActivityIdPrefix();
    v21 = 29;
    v22 = "Failed to initialize instance for perf counter";
LABEL_38:
    LODWORD(v32) = v10;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v21,
      (unsigned int)WPP_1c81c145608e3855819657761c2bbeb5_Traceguids,
      v20,
      (__int64)v22,
      v32);
    goto LABEL_39;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v30 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      (unsigned int)WPP_1c81c145608e3855819657761c2bbeb5_Traceguids,
      v30,
      (__int64)"CRDPSQMLogSession");
  }
  v10 = -2147024882;
LABEL_7:
  if ( this != (CRDPPerfMonLogger *)-504LL && *((_DWORD *)this + 128) )
    PAL_System_CritSecLeave(*v8);
  if ( v9 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v9[5] + 16LL))(v9[5]);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180008a80  mov     r11, rsp
0x180008a83  push    rbx
0x180008a84  push    rbp
0x180008a85  sub     rsp, 298h
0x180008a8c  mov     rax, cs:__security_cookie
0x180008a93  xor     rax, rsp
0x180008a96  mov     [rsp+2A8h+var_58], rax
0x180008a9e  mov     [r11-20h], rdi
0x180008aa2  mov     [r11-28h], r12
0x180008aa6  mov     r12, r9
0x180008aa9  mov     [r11-30h], r13
0x180008aad  mov     r13, rcx
0x180008ab0  mov     [r11-40h], r15
0x180008ab4  mov     r15d, edx
0x180008ab7  mov     [rsp+2A8h+var_278], r8
0x180008abc  mov     rax, cs:WPP_GLOBAL_Control
0x180008ac3  lea     rbp, WPP_GLOBAL_Control
0x180008aca  cmp     rax, rbp
0x180008acd  jnz     loc_180008BDB
0x180008ad3  lea     rdi, [r13+1F8h]
0x180008ada  cmp     dword ptr [rdi+8], 0
0x180008ade  jz      short loc_180008AF0
0x180008ae0  mov     rcx, [rdi]
0x180008ae3  call    cs:__imp_PAL_System_CritSecEnter
0x180008ae9  mov     rax, cs:WPP_GLOBAL_Control
0x180008af0  xor     ebx, ebx
0x180008af2  test    r12, r12
0x180008af5  jnz     short loc_180008B6A
0x180008af7  cmp     rax, rbp
0x180008afa  jnz     loc_180008EE2
0x180008b00  mov     ebp, 80004003h
0x180008b05  mov     r15, [rsp+2A8h+var_40]
0x180008b0d  mov     r13, [rsp+2A8h+var_30]
0x180008b15  mov     r12, [rsp+2A8h+var_28]
0x180008b1d  test    rdi, rdi
0x180008b20  jz      short loc_180008B31
0x180008b22  cmp     dword ptr [rdi+8], 0
0x180008b26  jz      short loc_180008B31
0x180008b28  mov     rcx, [rdi]
0x180008b2b  call    cs:__imp_PAL_System_CritSecLeave
0x180008b31  mov     rdi, [rsp+2A8h+var_20]
0x180008b39  test    rbx, rbx
0x180008b3c  jz      short loc_180008B4E
0x180008b3e  mov     rcx, [rbx+28h]
0x180008b42  mov     rax, [rcx]
0x180008b45  mov     rax, [rax+10h]
0x180008b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b4e  mov     eax, ebp
0x180008b50  mov     rcx, [rsp+2A8h+var_58]
0x180008b58  xor     rcx, rsp; StackCookie
0x180008b5b  call    __security_check_cookie
0x180008b60  add     rsp, 298h
0x180008b67  pop     rbp
0x180008b68  pop     rbx
0x180008b69  retn
0x180008b6a  mov     [rsp+2A8h+var_18], rsi
0x180008b72  mov     [r12], rbx
0x180008b76  mov     rsi, [r13+1E0h]
0x180008b7d  mov     [rsp+2A8h+var_38], r14
0x180008b85  test    rsi, rsi
0x180008b88  jz      loc_180008C2C
0x180008b8e  mov     r14, [rsi]
0x180008b91  mov     rbp, [rsi+8]
0x180008b95  mov     rcx, [r14+28h]
0x180008b99  mov     rax, [rcx]
0x180008b9c  mov     rax, [rax+8]
0x180008ba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ba5  cmp     [r14+40h], r15d
0x180008ba9  jz      short loc_180008BC0
0x180008bab  mov     rcx, [r14+28h]
0x180008baf  mov     rsi, rbp
0x180008bb2  mov     rax, [rcx]
0x180008bb5  mov     rax, [rax+10h]
0x180008bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bbe  jmp     short loc_180008B85
0x180008bc0  mov     ebp, ebx
0x180008bc2  mov     [r12], r14
0x180008bc6  mov     r14, [rsp+2A8h+var_38]
0x180008bce  mov     rsi, [rsp+2A8h+var_18]
0x180008bd6  jmp     loc_180008B05
0x180008bdb  test    dword ptr [rax+1Ch], 800h
0x180008be2  jz      loc_180008AD3
0x180008be8  cmp     byte ptr [rax+19h], 4
0x180008bec  jb      loc_180008AD3
0x180008bf2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180008bf7  mov     rcx, cs:WPP_GLOBAL_Control
0x180008bfe  lea     r8, WPP_1c81c145608e3855819657761c2bbeb5_Traceguids
0x180008c05  mov     edx, 17h
0x180008c0a  mov     dword ptr [rsp+2A8h+var_280], r15d
0x180008c0f  mov     r9d, eax
0x180008c12  mov     [rsp+2A8h+var_288], r13
0x180008c17  mov     rcx, [rcx+10h]
0x180008c1b  call    WPP_SF_Dqd
0x180008c20  mov     rax, cs:WPP_GLOBAL_Control
0x180008c27  jmp     loc_180008AD3
0x180008c2c  mov     ecx, 58h ; 'X'; Size
0x180008c31  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008c36  mov     r14, rax
0x180008c39  test    rax, rax
0x180008c3c  jz      loc_180008DF1
0x180008c42  mov     rdx, cs:RDPPerfMonCounters
0x180008c49  lea     rcx, [r14+8]
0x180008c4d  lea     rax, ??_7RdpXInterfaceTexture2DProperties@@6B@; const RdpXInterfaceTexture2DProperties::`vftable'
0x180008c54  mov     [r14], rax
0x180008c57  lea     rax, aCrdpperfmonses; "CRDPPerfMonSession"
0x180008c5e  mov     [rcx+10h], rax
0x180008c62  lea     rax, ??_7CClipLevelCallback@@6BINonDelegatingUnknown@@@; const CClipLevelCallback::`vftable'{for `INonDelegatingUnknown'}
0x180008c69  mov     dword ptr [rcx+18h], 0DBCAABCDh
0x180008c70  mov     dword ptr [rcx+1Ch], 1
0x180008c77  mov     [rcx], rax
0x180008c7a  lea     rax, ??_7CTSUnknown@@6BCTSObject@@@; const CTSUnknown::`vftable'{for `CTSObject'}
0x180008c81  mov     [rcx+8], rax
0x180008c85  lea     rax, ??_7CRDPPerfMonSession@@6B@; const CRDPPerfMonSession::`vftable'
0x180008c8c  mov     [rcx+28h], ebx
0x180008c8f  mov     [rcx+20h], rcx
0x180008c93  mov     [r14], rax
0x180008c96  lea     rax, ??_7CRDPPerfMonSession@@6BINonDelegatingUnknown@@@; const CRDPPerfMonSession::`vftable'{for `INonDelegatingUnknown'}
0x180008c9d  mov     [rcx], rax
0x180008ca0  lea     rax, ??_7CRDPPerfMonSession@@6BCTSObject@@@; const CRDPPerfMonSession::`vftable'{for `CTSObject'}
0x180008ca7  mov     [r14+10h], rax
0x180008cab  mov     [r14+50h], rbx
0x180008caf  mov     [r14+48h], rbx
0x180008cb3  mov     [r14+40h], r15d
0x180008cb7  mov     [r14+38h], rdx
0x180008cbb  test    r13, r13
0x180008cbe  jz      short loc_180008CDD
0x180008cc0  lea     rcx, [r14+50h]
0x180008cc4  call    ?SafeRelease@?$TCntPtr@VCRDPSQMLogger@@@@AEAAXXZ; TCntPtr<CRDPSQMLogger>::SafeRelease(void)
0x180008cc9  mov     [r14+50h], r13
0x180008ccd  mov     rcx, [r13+28h]
0x180008cd1  mov     rax, [rcx]
0x180008cd4  mov     rax, [rax+8]
0x180008cd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cdd  mov     rcx, [r14+28h]
0x180008ce1  mov     rax, [rcx]
0x180008ce4  mov     rax, [rax+8]
0x180008ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ced  mov     rbp, [rsp+2A8h+var_278]
0x180008cf2  test    rbp, rbp
0x180008cf5  jz      loc_180008F32
0x180008cfb  cmp     [rbp+0], bx
0x180008cff  jz      loc_180008F32
0x180008d05  mov     r9, rbp
0x180008d08  mov     dword ptr [rsp+2A8h+var_288], r15d
0x180008d0d  lea     r8, aSD_2; "%s %d"
0x180008d14  mov     edx, 104h; unsigned __int64
0x180008d19  lea     rcx, [rsp+2A8h+Name]; unsigned __int16 *
0x180008d1e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008d23  mov     ebp, eax
0x180008d25  test    eax, eax
0x180008d27  js      loc_180008EF1
0x180008d2d  lea     rsi, WPP_GLOBAL_Control
0x180008d34  mov     r9d, [r14+40h]; Id
0x180008d38  lea     r8, [rsp+2A8h+Name]; Name
0x180008d3d  mov     rcx, [r14+38h]; ProviderHandle
0x180008d41  lea     rdx, NetworkPerSessionGuid; CounterSetGuid
0x180008d48  call    cs:__imp_PerfCreateInstance
0x180008d4e  mov     [r14+48h], rax
0x180008d52  test    rax, rax
0x180008d55  jz      loc_180008E5D
0x180008d5b  mov     rax, cs:WPP_GLOBAL_Control
0x180008d62  mov     ebp, ebx
0x180008d64  cmp     rax, rsi
0x180008d67  jz      short loc_180008D76
0x180008d69  test    dword ptr [rax+1Ch], 100h
0x180008d70  jnz     loc_180008FD5
0x180008d76  test    ebp, ebp
0x180008d78  js      short loc_180008DA4
0x180008d7a  mov     rdx, r14; void *
0x180008d7d  lea     rcx, [r13+38h]; this
0x180008d81  call    ?AddTail@CVPtrList@@QEAAPEAXPEAX@Z; CVPtrList::AddTail(void *)
0x180008d86  test    rax, rax
0x180008d89  jz      loc_180008BC2
0x180008d8f  mov     rcx, [r14+28h]
0x180008d93  mov     rax, [rcx]
0x180008d96  mov     rax, [rax+8]
0x180008d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d9f  jmp     loc_180008BC2
0x180008da4  cmp     rax, rsi
0x180008da7  jz      short loc_180008DE9
0x180008da9  test    byte ptr [rax+1Ch], 8
0x180008dad  jz      short loc_180008DE9
0x180008daf  cmp     byte ptr [rax+19h], 2
0x180008db3  jb      short loc_180008DE9
0x180008db5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180008dba  mov     edx, 1Dh
0x180008dbf  lea     rcx, aFailedToInitia_45; "Failed to initialize instance for perf "...
0x180008dc6  mov     dword ptr [rsp+2A8h+var_280], ebp
0x180008dca  lea     r8, WPP_1c81c145608e3855819657761c2bbeb5_Traceguids
0x180008dd1  mov     [rsp+2A8h+var_288], rcx
0x180008dd6  mov     r9d, eax
0x180008dd9  mov     rcx, cs:WPP_GLOBAL_Control
0x180008de0  mov     rcx, [rcx+10h]
0x180008de4  call    WPP_SF_DsD
0x180008de9  mov     rbx, r14
0x180008dec  jmp     loc_180008BC6
0x180008df1  mov     rax, cs:WPP_GLOBAL_Control
0x180008df8  lea     rcx, WPP_GLOBAL_Control
0x180008dff  cmp     rax, rcx
0x180008e02  jz      short loc_180008E14
0x180008e04  test    byte ptr [rax+1Ch], 8
0x180008e08  jz      short loc_180008E14
0x180008e0a  cmp     byte ptr [rax+19h], 2
0x180008e0e  jnb     loc_18000901A
0x180008e14  mov     ebp, 8007000Eh
0x180008e19  jmp     loc_180008BC6
0x180008e1e  cmp     byte ptr [rax+19h], 2
0x180008e22  jb      loc_180008B00
0x180008e28  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180008e2d  lea     rcx, aPpsession; "ppSession"
0x180008e34  mov     edx, 18h
0x180008e39  mov     [rsp+2A8h+var_288], rcx
0x180008e3e  lea     r8, WPP_1c81c145608e3855819657761c2bbeb5_Traceguids
0x180008e45  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e4c  mov     r9d, eax
0x180008e4f  mov     rcx, [rcx+10h]
0x180008e53  call    WPP_SF_Ds
0x180008e58  jmp     loc_180008B00
0x180008e5d  call    cs:__imp_GetLastError
0x180008e63  mov     ebp, eax
0x180008e65  test    eax, eax
0x180008e67  jle     short loc_180008E72
0x180008e69  movzx   ebp, ax
0x180008e6c  or      ebp, 80070000h
0x180008e72  mov     rax, cs:WPP_GLOBAL_Control
0x180008e79  cmp     rax, rsi
0x180008e7c  jz      loc_180008D76
0x180008e82  test    dword ptr [rax+1Ch], 100h
0x180008e89  jz      loc_180008D76
0x180008e8f  cmp     byte ptr [rax+19h], 2
0x180008e93  jb      loc_180008D76
0x180008e99  mov     esi, [r14+40h]
0x180008e9d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180008ea2  lea     rcx, [rsp+2A8h+Name]
0x180008ea7  mov     dword ptr [rsp+2A8h+var_280], esi
0x180008eab  mov     [rsp+2A8h+var_288], rcx
0x180008eb0  lea     r8, WPP_1c81c145608e3855819657761c2bbeb5_Traceguids
0x180008eb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ebe  mov     edx, 1Fh
0x180008ec3  mov     r9d, eax
0x180008ec6  mov     rcx, [rcx+10h]
0x180008eca  call    WPP_SF_DSd
0x180008ecf  mov     rax, cs:WPP_GLOBAL_Control
0x180008ed6  lea     rsi, WPP_GLOBAL_Control
0x180008edd  jmp     loc_180008D76
0x180008ee2  test    byte ptr [rax+1Ch], 8
0x180008ee6  jz      loc_180008B00
0x180008eec  jmp     loc_180008E1E
0x180008ef1  mov     rax, cs:WPP_GLOBAL_Control
0x180008ef8  lea     rcx, WPP_GLOBAL_Control
0x180008eff  cmp     rax, rcx
0x180008f02  jz      loc_180008DE9
0x180008f08  test    byte ptr [rax+1Ch], 8
0x180008f0c  jz      loc_180008DE9
0x180008f12  cmp     byte ptr [rax+19h], 2
0x180008f16  jb      loc_180008DE9
0x180008f1c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180008f21  mov     edx, 1Ah
0x180008f26  lea     rcx, aFailedToCreate_4; "failed to create a session instance nam"...
0x180008f2d  jmp     loc_180008DC6
0x180008f32  mov     rax, cs:WPP_GLOBAL_Control
0x180008f39  lea     rsi, WPP_GLOBAL_Control
0x180008f40  cmp     rax, rsi
0x180008f43  jz      short loc_180008F78
0x180008f45  test    dword ptr [rax+1Ch], 100h
0x180008f4c  jz      short loc_180008F78
0x180008f4e  cmp     byte ptr [rax+19h], 2
0x180008f52  jb      short loc_180008F78
0x180008f54  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180008f59  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f60  lea     r8, WPP_1c81c145608e3855819657761c2bbeb5_Traceguids
0x180008f67  mov     edx, 1Bh
0x180008f6c  mov     r9d, eax
0x180008f6f  mov     rcx, [rcx+10h]
0x180008f73  call    WPP_SF_d
0x180008f78  mov     r9d, r15d
0x180008f7b  lea     r8, aRdpTcpD; "RDP-Tcp %d"
0x180008f82  mov     edx, 104h; unsigned __int64
0x180008f87  lea     rcx, [rsp+2A8h+Name]; unsigned __int16 *
0x180008f8c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180008f91  mov     ebp, eax
0x180008f93  test    eax, eax
0x180008f95  jns     loc_180008D34
0x180008f9b  mov     rax, cs:WPP_GLOBAL_Control
0x180008fa2  cmp     rax, rsi
0x180008fa5  jz      loc_180008DE9
0x180008fab  test    byte ptr [rax+1Ch], 8
0x180008faf  jz      loc_180008DE9
0x180008fb5  cmp     byte ptr [rax+19h], 2
0x180008fb9  jb      loc_180008DE9
0x180008fbf  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180008fc4  mov     edx, 1Ch
0x180008fc9  lea     rcx, aFailedToCreate_39; "Failed to create a session instance nam"...
0x180008fd0  jmp     loc_180008DC6
0x180008fd5  cmp     byte ptr [rax+19h], 4
0x180008fd9  jb      loc_180008D76
0x180008fdf  mov     esi, [r14+40h]
0x180008fe3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180008fe8  lea     rcx, [rsp+2A8h+Name]
0x180008fed  mov     dword ptr [rsp+2A8h+var_280], esi
  ... truncated ...
```
