# OnReceived(IUnknown *,long,ushort *)

- ea: `0x140047d10`
- end: `0x1400482b3`
- name: `?OnReceived@@YAXPEAUIUnknown@@JPEAG@Z`
- size: `1443`
- prototype: `void __fastcall(struct IRDPSRAPIVirtualChannel *, int, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x140034ce4`
- `0x14003bd48`
- `0x14003bda4`
- `0x14003be00`
- `0x14003bec0`
- `0x14003d920`
- `0x14003f674`
- `0x1400474f4`
- `0x140047d10`
- `0x1400482bc`
- `0x140048e34`
- `0x14004d010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x140047ef8`
- `KERNEL32!CompareStringW` at `0x140047f54`
- `KERNEL32!CompareStringW` at `0x140047fa2`
- `KERNEL32!CompareStringW` at `0x140047feb`
- `KERNEL32!CompareStringW` at `0x140048034`
- `KERNEL32!CompareStringW` at `0x14004807b`
- `KERNEL32!CompareStringW` at `0x1400480c2`
- `KERNEL32!CompareStringW` at `0x140047ef8`
- `KERNEL32!CompareStringW` at `0x140047f54`
- `KERNEL32!CompareStringW` at `0x140047fa2`
- `KERNEL32!CompareStringW` at `0x140047feb`
- `KERNEL32!CompareStringW` at `0x140048034`
- `KERNEL32!CompareStringW` at `0x14004807b`
- `KERNEL32!CompareStringW` at `0x1400480c2`
- `OLEAUT32!__imp_SysFreeString` at `0x14004823a`
- `OLEAUT32!__imp_SysFreeString` at `0x14004824e`
- `OLEAUT32!__imp_SysFreeString` at `0x14004823a`
- `OLEAUT32!__imp_SysFreeString` at `0x14004824e`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140047df1`
- `OLEAUT32!__imp_SysStringByteLen` at `0x140047df1`

## string_xrefs

- `0x140047eea`: `<RCCOMMAND NAME="REMOTECTRLSTART"/>`
- `0x140047f46`: `<RCCOMMAND NAME="REMOTECTRLEND"/>`
- `0x140047f94`: `<RCCOMMAND NAME="ACCEPTRC"/>`
- `0x140047fdd`: `<RCCOMMAND NAME="REJECTRC"/>`
- `0x1400480b4`: `<RCCOMMAND NAME="DENIEDRC"/>`
- `0x14004806d`: `<RCCOMMAND NAME="ESCRC"/>`
- `0x140048026`: `<RCCOMMAND NAME="TAKECONTROL"/>`

## pseudocode

```c
void __fastcall OnReceived(struct IRDPSRAPIVirtualChannel *a1, int a2, unsigned __int16 *a3)
{
  struct IRDPSRAPIVirtualChannel *v4; // r13
  struct IRDPSRAPIVirtualChannel *v5; // rbx
  struct IRDPSRAPIVirtualChannel *v6; // rdi
  struct IRDPSRAPIVirtualChannel *v7; // rsi
  OLECHAR *v8; // r12
  OLECHAR *v9; // r15
  unsigned int v10; // r9d
  signed int LegacyVC; // eax
  CEventLogger *v12; // rcx
  CRATicket *v13; // r15
  UINT v14; // eax
  signed int ControlVC; // eax
  CEventLogger *v16; // rcx
  signed int ChatVC; // eax
  struct IRDPSRAPIVirtualChannel *v18; // rdx
  CEventLogger *v19; // rcx
  CRATicket *v20; // rcx
  void (__fastcall *v21)(_QWORD, __int64); // rax
  void (__fastcall *v22)(_QWORD, __int64); // rax
  void (__fastcall *v23)(__int64); // rax
  void (__fastcall *v24)(__int64); // rax
  void (__fastcall *v25)(__int64); // rax
  void (__fastcall *v26)(__int64); // rax
  void (*v27)(void); // rax
  void (__fastcall *v28)(BSTR, BSTR); // rax
  StringMatchAgent **v29; // rcx
  _QWORD *v30; // r12
  int v31; // r13d
  _QWORD *i; // r15
  _QWORD *v33; // rax
  CRATicket *v34; // r10
  StringMatchAgent **v35; // rcx
  BSTR bstrString; // [rsp+30h] [rbp-30h] BYREF
  BSTR v37; // [rsp+38h] [rbp-28h] BYREF
  struct IRDPSRAPIVirtualChannel *v38; // [rsp+40h] [rbp-20h] BYREF
  __int128 v39; // [rsp+48h] [rbp-18h] BYREF
  __int64 v40; // [rsp+58h] [rbp-8h]
  struct IRDPSRAPIVirtualChannel *v41; // [rsp+A0h] [rbp+40h] BYREF
  int v42; // [rsp+A8h] [rbp+48h]
  struct IRDPSRAPIVirtualChannel *v43; // [rsp+B8h] [rbp+58h] BYREF

  v42 = a2;
  v4 = a1;
  v5 = 0;
  v43 = 0;
  v6 = 0;
  v38 = 0;
  v7 = 0;
  v41 = 0;
  v8 = 0;
  bstrString = 0;
  v9 = 0;
  v37 = 0;
  if ( !a1 )
  {
    v10 = 599;
LABEL_3:
    CEventLogger::LogError(
      (CEventLogger *)a1,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\core\\lib\\rarecv.cpp",
      v10,
      L"OnReceived",
      0x80004003);
    goto LABEL_63;
  }
  a1 = (struct IRDPSRAPIVirtualChannel *)RAGlobals;
  if ( !RAGlobals )
  {
    v10 = 600;
    goto LABEL_3;
  }
  LegacyVC = CRATicket::GetLegacyVC(RAGlobals, &v41, 0);
  if ( LegacyVC < 0 )
  {
    CEventLogger::LogError(
      v12,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\core\\lib\\rarecv.cpp",
      0x25Eu,
      L"OnReceived",
      LegacyVC);
    v7 = v41;
    goto LABEL_63;
  }
  v7 = v41;
  if ( v4 == v41 )
  {
    v13 = RAGlobals;
    v14 = SysStringByteLen(a3);
    if ( v14 >= 4 )
      CRATicket::SignalVC(v13, *(_DWORD *)a3, (unsigned __int8 *)a3, v14);
    goto LABEL_63;
  }
  if ( *((_DWORD *)RAGlobals + 133) != 2 && *((_DWORD *)RAGlobals + 132) != 3 )
    goto LABEL_63;
  ControlVC = CRATicket::GetControlVC(RAGlobals, &v43, 0);
  if ( ControlVC < 0 )
  {
    CEventLogger::LogError(
      v16,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\core\\lib\\rarecv.cpp",
      0x273u,
      L"OnReceived",
      ControlVC);
    v5 = v43;
    goto LABEL_63;
  }
  ChatVC = CRATicket::GetChatVC(RAGlobals, &v38, 0);
  if ( ChatVC < 0 )
  {
    CEventLogger::LogError(
      v19,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\core\\lib\\rarecv.cpp",
      0x274u,
      L"OnReceived",
      ChatVC);
    v5 = v43;
    v6 = v38;
    goto LABEL_63;
  }
  v6 = v38;
  v5 = v43;
  if ( v4 == v43 )
  {
    if ( CompareStringW(0x400u, 0, L"<RCCOMMAND NAME=\"REMOTECTRLSTART\"/>", -1, a3, -1) == 2 )
    {
      v20 = RAGlobals;
      *((_DWORD *)RAGlobals + 39) = 2;
      v21 = (void (__fastcall *)(_QWORD, __int64))*((_QWORD *)v20 + 31);
      if ( v21 )
        v21(*((_QWORD *)v20 + 38), 3);
    }
    if ( CompareStringW(0x400u, 0, L"<RCCOMMAND NAME=\"REMOTECTRLEND\"/>", -1, a3, -1) == 2 )
    {
      v22 = (void (__fastcall *)(_QWORD, __int64))*((_QWORD *)RAGlobals + 31);
      if ( v22 )
        v22(*((_QWORD *)RAGlobals + 38), 2);
    }
    if ( CompareStringW(0x400u, 0, L"<RCCOMMAND NAME=\"ACCEPTRC\"/>", -1, a3, -1) == 2 )
    {
      v23 = (void (__fastcall *)(__int64))*((_QWORD *)RAGlobals + 32);
      if ( v23 )
        v23(3);
    }
    if ( CompareStringW(0x400u, 0, L"<RCCOMMAND NAME=\"REJECTRC\"/>", -1, a3, -1) == 2 )
    {
      v24 = (void (__fastcall *)(__int64))*((_QWORD *)RAGlobals + 30);
      if ( v24 )
        v24(63);
    }
    if ( CompareStringW(0x400u, 0, L"<RCCOMMAND NAME=\"TAKECONTROL\"/>", -1, a3, -1) == 2 )
    {
      v25 = (void (__fastcall *)(__int64))*((_QWORD *)RAGlobals + 32);
      if ( v25 )
        v25(2);
    }
    if ( CompareStringW(0x400u, 0, L"<RCCOMMAND NAME=\"ESCRC\"/>", -1, a3, -1) == 2 )
    {
      v26 = (void (__fastcall *)(__int64))*((_QWORD *)RAGlobals + 32);
      if ( v26 )
        v26(2);
    }
    if ( CompareStringW(0x400u, 0, L"<RCCOMMAND NAME=\"DENIEDRC\"/>", -1, a3, -1) == 2 )
    {
      v27 = (void (*)(void))*((_QWORD *)RAGlobals + 33);
      if ( v27 )
        v27();
    }
    if ( ProcessCommandForPropAnnounce(a3, &bstrString, &v37) == 1 )
    {
      v28 = (void (__fastcall *)(BSTR, BSTR))*((_QWORD *)RAGlobals + 37);
      if ( v28 )
      {
        v9 = v37;
        v8 = bstrString;
        v28(bstrString, v37);
LABEL_59:
        if ( v8 )
          SysFreeString(v8);
        if ( v9 )
          SysFreeString(v9);
        goto LABEL_63;
      }
    }
    else
    {
      v29 = (StringMatchAgent **)*((_QWORD *)RAGlobals + 63);
      if ( v29 )
        StringMatchAgent::WalkStringPatternList(v29, v42, v4, a3);
    }
    v8 = bstrString;
    v9 = v37;
    goto LABEL_59;
  }
  if ( v4 != v38 )
  {
    if ( !CRATicket::GetFileXferInstByFileVC(RAGlobals, v4) )
      goto LABEL_63;
    v35 = (StringMatchAgent **)*((_QWORD *)v34 + 62);
    if ( v35 )
    {
      if ( !(unsigned int)StringMatchAgent::WalkStringPatternList(v35, v42, v4, a3) )
        goto LABEL_63;
      v34 = RAGlobals;
    }
    ReceiveFile((ReceivingFileContext **)v34, v4, v42, a3);
    goto LABEL_59;
  }
  a1 = (struct IRDPSRAPIVirtualChannel *)RAGlobals;
  v30 = (_QWORD *)*((_QWORD *)RAGlobals + 61);
  if ( !v30 )
  {
    v10 = 739;
    goto LABEL_3;
  }
  v31 = v42;
  CRATicket::ReBcastChatMsg(RAGlobals, v18, v42, a3);
  v39 = 0;
  v40 = 0;
  for ( i = (_QWORD *)*v30; i != v30; i = (_QWORD *)*i )
  {
    v33 = (_QWORD *)i[2];
    if ( v33 && *v33 )
    {
      DWORD2(v39) = v31;
      v40 = *(_QWORD *)(i[2] + 8LL);
      *(_QWORD *)&v39 = a3;
      (*(void (__fastcall **)(__int128 *, __int64))i[2])(&v39, 6);
    }
  }
LABEL_63:
  if ( v7 )
    ((void (__fastcall *)(struct IRDPSRAPIVirtualChannel *))v7->lpVtbl->Release)(v7);
  if ( v6 )
    ((void (__fastcall *)(struct IRDPSRAPIVirtualChannel *))v6->lpVtbl->Release)(v6);
  if ( v5 )
    ((void (__fastcall *)(struct IRDPSRAPIVirtualChannel *))v5->lpVtbl->Release)(v5);
}

```

## disassembly

```asm
0x140047d10  mov     [rsp-38h+arg_10], rbx
0x140047d15  mov     [rsp-38h+arg_8], edx
0x140047d19  push    rbp
0x140047d1a  push    rsi
0x140047d1b  push    rdi
0x140047d1c  push    r12
0x140047d1e  push    r13
0x140047d20  push    r14
0x140047d22  push    r15
0x140047d24  mov     rbp, rsp
0x140047d27  sub     rsp, 60h
0x140047d2b  mov     r14, r8
0x140047d2e  mov     r13, rcx
0x140047d31  xor     ebx, ebx
0x140047d33  mov     [rbp+arg_18], rbx
0x140047d37  xor     edi, edi
0x140047d39  mov     [rbp+var_20], rdi
0x140047d3d  xor     esi, esi
0x140047d3f  mov     [rbp+arg_0], rsi
0x140047d43  xor     r12d, r12d
0x140047d46  mov     [rbp+bstrString], r12
0x140047d4a  xor     r15d, r15d
0x140047d4d  mov     [rbp+var_28], r15
0x140047d51  test    rcx, rcx
0x140047d54  jnz     short loc_140047D88
0x140047d56  mov     r9d, 257h; unsigned int
0x140047d5c  mov     [rsp+60h+cchCount2], 80004003h; unsigned int
0x140047d64  lea     rax, aOnreceived; "OnReceived"
0x140047d6b  mov     [rsp+60h+lpString2], rax; unsigned __int16 *
0x140047d70  lea     r8, aBaseDiagnosisR; "base\\diagnosis\\ra\\core\\lib\\rarecv."...
0x140047d77  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140047d7e  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140047d83  jmp     loc_14004825B
0x140047d88  mov     rcx, cs:?RAGlobals@@3URA_GLOBAL_SYNC@@A; this
0x140047d8f  test    rcx, rcx
0x140047d92  jnz     short loc_140047D9C
0x140047d94  mov     r9d, 258h
0x140047d9a  jmp     short loc_140047D5C
0x140047d9c  xor     r8d, r8d; int
0x140047d9f  lea     rdx, [rbp+arg_0]; struct IRDPSRAPIVirtualChannel **
0x140047da3  call    ?GetLegacyVC@CRATicket@@QEAAJPEAPEAUIRDPSRAPIVirtualChannel@@H@Z; CRATicket::GetLegacyVC(IRDPSRAPIVirtualChannel * *,int)
0x140047da8  test    eax, eax
0x140047daa  jns     short loc_140047DDE
0x140047dac  mov     [rsp+60h+cchCount2], eax; unsigned int
0x140047db0  lea     rax, aOnreceived; "OnReceived"
0x140047db7  mov     [rsp+60h+lpString2], rax; unsigned __int16 *
0x140047dbc  mov     r9d, 25Eh; unsigned int
0x140047dc2  lea     r8, aBaseDiagnosisR; "base\\diagnosis\\ra\\core\\lib\\rarecv."...
0x140047dc9  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140047dd0  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140047dd5  mov     rsi, [rbp+arg_0]
0x140047dd9  jmp     loc_14004825B
0x140047dde  mov     rsi, [rbp+arg_0]
0x140047de2  cmp     r13, rsi
0x140047de5  jnz     short loc_140047E1C
0x140047de7  mov     r15, cs:?RAGlobals@@3URA_GLOBAL_SYNC@@A; RA_GLOBAL_SYNC RAGlobals
0x140047dee  mov     rcx, r14; bstr
0x140047df1  call    cs:__imp_SysStringByteLen
0x140047df8  nop     dword ptr [rax+rax+00h]
0x140047dfd  cmp     eax, 4
0x140047e00  jb      loc_14004825B
0x140047e06  mov     r9d, eax; unsigned int
0x140047e09  mov     r8, r14; unsigned __int8 *
0x140047e0c  mov     edx, [r14]; unsigned int
0x140047e0f  mov     rcx, r15; this
0x140047e12  call    ?SignalVC@CRATicket@@QEAAJKPEAEK@Z; CRATicket::SignalVC(ulong,uchar *,ulong)
0x140047e17  jmp     loc_14004825B
0x140047e1c  mov     rcx, cs:?RAGlobals@@3URA_GLOBAL_SYNC@@A; this
0x140047e23  cmp     dword ptr [rcx+214h], 2
0x140047e2a  jz      short loc_140047E39
0x140047e2c  cmp     dword ptr [rcx+210h], 3
0x140047e33  jnz     loc_14004825B
0x140047e39  xor     r8d, r8d; int
0x140047e3c  lea     rdx, [rbp+arg_18]; struct IRDPSRAPIVirtualChannel **
0x140047e40  call    ?GetControlVC@CRATicket@@QEAAJPEAPEAUIRDPSRAPIVirtualChannel@@H@Z; CRATicket::GetControlVC(IRDPSRAPIVirtualChannel * *,int)
0x140047e45  test    eax, eax
0x140047e47  jns     short loc_140047E7B
0x140047e49  mov     [rsp+60h+cchCount2], eax; unsigned int
0x140047e4d  lea     rax, aOnreceived; "OnReceived"
0x140047e54  mov     [rsp+60h+lpString2], rax; unsigned __int16 *
0x140047e59  mov     r9d, 273h; unsigned int
0x140047e5f  lea     r8, aBaseDiagnosisR; "base\\diagnosis\\ra\\core\\lib\\rarecv."...
0x140047e66  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140047e6d  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140047e72  mov     rbx, [rbp+arg_18]
0x140047e76  jmp     loc_14004825B
0x140047e7b  xor     r8d, r8d; int
0x140047e7e  lea     rdx, [rbp+var_20]; struct IRDPSRAPIVirtualChannel **
0x140047e82  mov     rcx, cs:?RAGlobals@@3URA_GLOBAL_SYNC@@A; this
0x140047e89  call    ?GetChatVC@CRATicket@@QEAAJPEAPEAUIRDPSRAPIVirtualChannel@@H@Z; CRATicket::GetChatVC(IRDPSRAPIVirtualChannel * *,int)
0x140047e8e  test    eax, eax
0x140047e90  jns     short loc_140047EC8
0x140047e92  mov     [rsp+60h+cchCount2], eax; unsigned int
0x140047e96  lea     rax, aOnreceived; "OnReceived"
0x140047e9d  mov     [rsp+60h+lpString2], rax; unsigned __int16 *
0x140047ea2  mov     r9d, 274h; unsigned int
0x140047ea8  lea     r8, aBaseDiagnosisR; "base\\diagnosis\\ra\\core\\lib\\rarecv."...
0x140047eaf  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140047eb6  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140047ebb  mov     rbx, [rbp+arg_18]
0x140047ebf  mov     rdi, [rbp+var_20]
0x140047ec3  jmp     loc_14004825B
0x140047ec8  mov     rdi, [rbp+var_20]
0x140047ecc  mov     rbx, [rbp+arg_18]
0x140047ed0  cmp     r13, rbx
0x140047ed3  jnz     loc_140048152
0x140047ed9  or      r12d, 0FFFFFFFFh
0x140047edd  mov     [rsp+60h+cchCount2], r12d; cchCount2
0x140047ee2  mov     [rsp+60h+lpString2], r14; lpString2
0x140047ee7  mov     r9d, r12d; cchCount1
0x140047eea  lea     r8, String1; "<RCCOMMAND NAME=\"REMOTECTRLSTART\"/>"
0x140047ef1  xor     edx, edx; dwCmpFlags
0x140047ef3  mov     ecx, 400h; Locale
0x140047ef8  call    cs:__imp_CompareStringW
0x140047eff  nop     dword ptr [rax+rax+00h]
0x140047f04  lea     r15d, [r12+3]
0x140047f09  cmp     eax, r15d
0x140047f0c  jnz     short loc_140047F39
0x140047f0e  mov     rcx, cs:?RAGlobals@@3URA_GLOBAL_SYNC@@A; RA_GLOBAL_SYNC RAGlobals
0x140047f15  mov     [rcx+9Ch], r15d
0x140047f1c  mov     rax, [rcx+0F8h]
0x140047f23  test    rax, rax
0x140047f26  jz      short loc_140047F39
0x140047f28  lea     edx, [r12+4]
0x140047f2d  mov     rcx, [rcx+130h]
0x140047f34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047f39  mov     [rsp+60h+cchCount2], r12d; cchCount2
0x140047f3e  mov     [rsp+60h+lpString2], r14; lpString2
0x140047f43  mov     r9d, r12d; cchCount1
0x140047f46  lea     r8, aRccommandNameR_1; "<RCCOMMAND NAME=\"REMOTECTRLEND\"/>"
0x140047f4d  xor     edx, edx; dwCmpFlags
0x140047f4f  mov     ecx, 400h; Locale
0x140047f54  call    cs:__imp_CompareStringW
0x140047f5b  nop     dword ptr [rax+rax+00h]
0x140047f60  cmp     eax, r15d
0x140047f63  jnz     short loc_140047F87
0x140047f65  mov     rcx, cs:?RAGlobals@@3URA_GLOBAL_SYNC@@A; RA_GLOBAL_SYNC RAGlobals
0x140047f6c  mov     rax, [rcx+0F8h]
0x140047f73  test    rax, rax
0x140047f76  jz      short loc_140047F87
0x140047f78  mov     edx, r15d
0x140047f7b  mov     rcx, [rcx+130h]
0x140047f82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047f87  mov     [rsp+60h+cchCount2], r12d; cchCount2
0x140047f8c  mov     [rsp+60h+lpString2], r14; lpString2
0x140047f91  mov     r9d, r12d; cchCount1
0x140047f94  lea     r8, aRccommandNameA_0; "<RCCOMMAND NAME=\"ACCEPTRC\"/>"
0x140047f9b  xor     edx, edx; dwCmpFlags
0x140047f9d  mov     ecx, 400h; Locale
0x140047fa2  call    cs:__imp_CompareStringW
0x140047fa9  nop     dword ptr [rax+rax+00h]
0x140047fae  cmp     eax, r15d
0x140047fb1  jnz     short loc_140047FD0
0x140047fb3  mov     rax, cs:?RAGlobals@@3URA_GLOBAL_SYNC@@A; RA_GLOBAL_SYNC RAGlobals
0x140047fba  mov     rax, [rax+100h]
0x140047fc1  test    rax, rax
0x140047fc4  jz      short loc_140047FD0
0x140047fc6  mov     ecx, 3
0x140047fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140047fd0  mov     [rsp+60h+cchCount2], r12d; cchCount2
0x140047fd5  mov     [rsp+60h+lpString2], r14; lpString2
0x140047fda  mov     r9d, r12d; cchCount1
0x140047fdd  lea     r8, aRccommandNameR_0; "<RCCOMMAND NAME=\"REJECTRC\"/>"
0x140047fe4  xor     edx, edx; dwCmpFlags
0x140047fe6  mov     ecx, 400h; Locale
0x140047feb  call    cs:__imp_CompareStringW
0x140047ff2  nop     dword ptr [rax+rax+00h]
0x140047ff7  cmp     eax, r15d
0x140047ffa  jnz     short loc_140048019
0x140047ffc  mov     rax, cs:?RAGlobals@@3URA_GLOBAL_SYNC@@A; RA_GLOBAL_SYNC RAGlobals
0x140048003  mov     rax, [rax+0F0h]
0x14004800a  test    rax, rax
0x14004800d  jz      short loc_140048019
0x14004800f  mov     ecx, 3Fh ; '?'
0x140048014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140048019  mov     [rsp+60h+cchCount2], r12d; cchCount2
0x14004801e  mov     [rsp+60h+lpString2], r14; lpString2
0x140048023  mov     r9d, r12d; cchCount1
0x140048026  lea     r8, aRccommandNameT; "<RCCOMMAND NAME=\"TAKECONTROL\"/>"
0x14004802d  xor     edx, edx; dwCmpFlags
0x14004802f  mov     ecx, 400h; Locale
0x140048034  call    cs:__imp_CompareStringW
0x14004803b  nop     dword ptr [rax+rax+00h]
0x140048040  cmp     eax, r15d
0x140048043  jnz     short loc_140048060
0x140048045  mov     rax, cs:?RAGlobals@@3URA_GLOBAL_SYNC@@A; RA_GLOBAL_SYNC RAGlobals
0x14004804c  mov     rax, [rax+100h]
0x140048053  test    rax, rax
0x140048056  jz      short loc_140048060
0x140048058  mov     ecx, r15d
0x14004805b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140048060  mov     [rsp+60h+cchCount2], r12d; cchCount2
0x140048065  mov     [rsp+60h+lpString2], r14; lpString2
0x14004806a  mov     r9d, r12d; cchCount1
0x14004806d  lea     r8, aRccommandNameE; "<RCCOMMAND NAME=\"ESCRC\"/>"
0x140048074  xor     edx, edx; dwCmpFlags
0x140048076  mov     ecx, 400h; Locale
0x14004807b  call    cs:__imp_CompareStringW
0x140048082  nop     dword ptr [rax+rax+00h]
0x140048087  cmp     eax, r15d
0x14004808a  jnz     short loc_1400480A7
0x14004808c  mov     rax, cs:?RAGlobals@@3URA_GLOBAL_SYNC@@A; RA_GLOBAL_SYNC RAGlobals
0x140048093  mov     rax, [rax+100h]
0x14004809a  test    rax, rax
0x14004809d  jz      short loc_1400480A7
0x14004809f  mov     ecx, r15d
0x1400480a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400480a7  mov     [rsp+60h+cchCount2], r12d; cchCount2
0x1400480ac  mov     [rsp+60h+lpString2], r14; lpString2
0x1400480b1  mov     r9d, r12d; cchCount1
0x1400480b4  lea     r8, aRccommandNameD; "<RCCOMMAND NAME=\"DENIEDRC\"/>"
0x1400480bb  xor     edx, edx; dwCmpFlags
0x1400480bd  mov     ecx, 400h; Locale
0x1400480c2  call    cs:__imp_CompareStringW
0x1400480c9  nop     dword ptr [rax+rax+00h]
0x1400480ce  cmp     eax, r15d
0x1400480d1  jnz     short loc_1400480EB
0x1400480d3  mov     rax, cs:?RAGlobals@@3URA_GLOBAL_SYNC@@A; RA_GLOBAL_SYNC RAGlobals
0x1400480da  mov     rax, [rax+108h]
0x1400480e1  test    rax, rax
0x1400480e4  jz      short loc_1400480EB
0x1400480e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400480eb  lea     r8, [rbp+var_28]; unsigned __int16 **
0x1400480ef  lea     rdx, [rbp+bstrString]; unsigned __int16 **
0x1400480f3  mov     rcx, r14; unsigned __int16 *
0x1400480f6  call    ?ProcessCommandForPropAnnounce@@YAHPEAGPEAPEAG1@Z; ProcessCommandForPropAnnounce(ushort *,ushort * *,ushort * *)
0x1400480fb  cmp     eax, 1
0x1400480fe  mov     rax, cs:?RAGlobals@@3URA_GLOBAL_SYNC@@A; RA_GLOBAL_SYNC RAGlobals
0x140048105  jnz     short loc_14004812B
0x140048107  mov     rax, [rax+128h]
0x14004810e  test    rax, rax
0x140048111  jz      short loc_140048145
0x140048113  mov     r15, [rbp+var_28]
0x140048117  mov     rdx, r15
0x14004811a  mov     r12, [rbp+bstrString]
0x14004811e  mov     rcx, r12
0x140048121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140048126  jmp     loc_140048232
0x14004812b  mov     rcx, [rax+1F8h]; this
0x140048132  test    rcx, rcx
0x140048135  jz      short loc_140048145
0x140048137  mov     r9, r14; unsigned __int16 *
0x14004813a  mov     r8, r13; struct IRDPSRAPIVirtualChannel *
0x14004813d  mov     edx, [rbp+arg_8]; int
0x140048140  call    ?WalkStringPatternList@StringMatchAgent@@QEAAJJPEAUIRDPSRAPIVirtualChannel@@PEAG@Z; StringMatchAgent::WalkStringPatternList(long,IRDPSRAPIVirtualChannel *,ushort *)
0x140048145  mov     r12, [rbp+bstrString]
0x140048149  mov     r15, [rbp+var_28]
0x14004814d  jmp     loc_140048232
0x140048152  cmp     r13, rdi
0x140048155  jnz     loc_1400481E4
0x14004815b  mov     rcx, cs:?RAGlobals@@3URA_GLOBAL_SYNC@@A; this
0x140048162  mov     r12, [rcx+1E8h]
0x140048169  test    r12, r12
0x14004816c  jnz     short loc_140048179
0x14004816e  mov     r9d, 2E3h
0x140048174  jmp     loc_140047D5C
0x140048179  mov     r9, r14; unsigned __int16 *
0x14004817c  mov     r13d, [rbp+arg_8]
0x140048180  mov     r8d, r13d; int
0x140048183  call    ?ReBcastChatMsg@CRATicket@@AEAAJPEAUIRDPSRAPIVirtualChannel@@JPEAG@Z; CRATicket::ReBcastChatMsg(IRDPSRAPIVirtualChannel *,long,ushort *)
0x140048188  xorps   xmm0, xmm0
0x14004818b  xor     eax, eax
0x14004818d  movups  [rbp+var_18], xmm0
0x140048191  mov     [rbp+var_8], rax
0x140048195  mov     r15, [r12]
0x140048199  cmp     r15, r12
0x14004819c  jz      loc_14004825B
0x1400481a2  mov     rax, [r15+10h]
0x1400481a6  test    rax, rax
0x1400481a9  jz      short loc_1400481DA
0x1400481ab  cmp     qword ptr [rax], 0
0x1400481af  jz      short loc_1400481DA
0x1400481b1  mov     dword ptr [rbp+var_18+8], r13d
0x1400481b5  mov     rax, [r15+10h]
0x1400481b9  mov     rcx, [rax+8]
0x1400481bd  mov     [rbp+var_8], rcx
0x1400481c1  mov     qword ptr [rbp+var_18], r14
0x1400481c5  mov     rax, [r15+10h]
0x1400481c9  mov     edx, 6
0x1400481ce  lea     rcx, [rbp+var_18]
0x1400481d2  mov     rax, [rax]
0x1400481d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400481da  mov     r15, [r15]
0x1400481dd  cmp     r15, r12
0x1400481e0  jnz     short loc_1400481A2
0x1400481e2  jmp     short loc_14004825B
0x1400481e4  mov     rdx, r13; struct IRDPSRAPIVirtualChannel *
0x1400481e7  mov     r10, cs:?RAGlobals@@3URA_GLOBAL_SYNC@@A; RA_GLOBAL_SYNC RAGlobals
0x1400481ee  mov     rcx, r10; this
0x1400481f1  call    ?GetFileXferInstByFileVC@CRATicket@@AEAAPEAVRAXferWorker@@PEAUIRDPSRAPIVirtualChannel@@@Z; CRATicket::GetFileXferInstByFileVC(IRDPSRAPIVirtualChannel *)
0x1400481f6  test    rax, rax
0x1400481f9  jz      short loc_14004825B
0x1400481fb  mov     rcx, [r10+1F0h]; this
0x140048202  test    rcx, rcx
0x140048205  jz      short loc_140048220
0x140048207  mov     r9, r14; unsigned __int16 *
0x14004820a  mov     r8, r13; struct IRDPSRAPIVirtualChannel *
0x14004820d  mov     edx, [rbp+arg_8]; int
0x140048210  call    ?WalkStringPatternList@StringMatchAgent@@QEAAJJPEAUIRDPSRAPIVirtualChannel@@PEAG@Z; StringMatchAgent::WalkStringPatternList(long,IRDPSRAPIVirtualChannel *,ushort *)
0x140048215  test    eax, eax
  ... truncated ...
```
