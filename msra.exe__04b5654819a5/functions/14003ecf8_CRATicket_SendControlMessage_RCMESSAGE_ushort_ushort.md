# CRATicket::SendControlMessage(_RCMESSAGE,ushort *,ushort *)

- ea: `0x14003ecf8`
- end: `0x14003ef9c`
- name: `?SendControlMessage@CRATicket@@QEAAJW4_RCMESSAGE@@PEAG1@Z`
- size: `676`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14001b5d4`
- `0x1400213ac`
- `0x14002b7f0`

## callees

- `0x140002463`
- `0x1400080fc`
- `0x140034ce4`
- `0x14003bda4`
- `0x14003ecf8`
- `0x14004ad80`
- `0x14004d010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14003ee8a`
- `OLEAUT32!__imp_SysAllocString` at `0x14003ee8a`
- `OLEAUT32!__imp_SysFreeString` at `0x14003ef25`
- `OLEAUT32!__imp_SysFreeString` at `0x14003ef25`

## string_xrefs

- `0x14003ee83`: `<RCCOMMAND NAME="REMOTECTRLSTART"/>`
- `0x14003ee7a`: `<RCCOMMAND NAME="REMOTECTRLEND"/>`
- `0x14003ee71`: `<RCCOMMAND NAME="ACCEPTRC"/>`
- `0x14003ee68`: `<RCCOMMAND NAME="REJECTRC"/>`
- `0x14003ee5f`: `<RCCOMMAND NAME="DENIEDRC"/>`
- `0x14003ee56`: `<RCCOMMAND NAME="ESCRC"/>`
- `0x14003ee2b`: `<RCCOMMAND NAME="SETTINGANNOUNCE" PROPERTY="%s" VALUE="%s"/>`
- `0x14003edce`: `<RCCOMMAND NAME="ACKNOWLEDGE" PROPERTY="%s"/>`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CRATicket::SendControlMessage(CRATicket *a1, int a2, __int64 a3, __int64 a4)
{
  int ControlVC; // eax
  struct IRDPSRAPIVirtualChannel *v9; // rbx
  CEventLogger *v10; // rcx
  unsigned int v11; // r9d
  signed int v12; // eax
  CEventLogger *v13; // rcx
  unsigned int v14; // edi
  unsigned __int16 *v15; // rcx
  signed int v16; // eax
  CEventLogger *v17; // rcx
  BSTR v18; // rax
  OLECHAR *v19; // rsi
  signed int v20; // eax
  CEventLogger *v21; // rcx
  void (__fastcall *v22)(__int64); // rax
  struct IRDPSRAPIVirtualChannel *v24; // [rsp+30h] [rbp-848h] BYREF
  unsigned __int16 v25[1024]; // [rsp+40h] [rbp-838h] BYREF

  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  ControlVC = CRATicket::GetControlVC(a1, &v24, 1);
  v9 = v24;
  LOBYTE(v10) = v24 == 0;
  if ( !v24 || ControlVC < 0 )
  {
    v11 = 6259;
    goto LABEL_38;
  }
  if ( a2 )
  {
    switch ( a2 )
    {
      case 1:
        v15 = L"<RCCOMMAND NAME=\"REMOTECTRLEND\"/>";
        break;
      case 2:
        v15 = L"<RCCOMMAND NAME=\"ACCEPTRC\"/>";
        break;
      case 3:
        v15 = L"<RCCOMMAND NAME=\"REJECTRC\"/>";
        break;
      case 4:
        v15 = L"<RCCOMMAND NAME=\"DENIEDRC\"/>";
        break;
      case 5:
      case 6:
        v15 = L"<RCCOMMAND NAME=\"ESCRC\"/>";
        break;
      default:
        v10 = (CEventLogger *)(unsigned int)(a2 - 7);
        if ( a2 == 7 )
        {
          if ( !a3 )
          {
            v11 = 6300;
            goto LABEL_38;
          }
          if ( !a4 )
          {
            v11 = 6301;
            goto LABEL_38;
          }
          v16 = StringCchPrintfW(
                  v25,
                  0x400u,
                  L"<RCCOMMAND NAME=\"SETTINGANNOUNCE\" PROPERTY=\"%s\" VALUE=\"%s\"/>",
                  a3,
                  a4);
          v14 = v16;
          if ( v16 < 0 )
          {
            CEventLogger::LogError(
              v17,
              &Recoverable_Error,
              L"base\\diagnosis\\ra\\core\\lib\\raticket.cpp",
              0x18A4u,
              L"CRATicket::SendControlMessage",
              v16);
            goto LABEL_39;
          }
        }
        else
        {
          if ( a2 != 8 )
          {
LABEL_30:
            v14 = -2147024882;
            CEventLogger::LogError(
              v10,
              &Recoverable_Error,
              L"base\\diagnosis\\ra\\core\\lib\\raticket.cpp",
              0x18C0u,
              L"CRATicket::SendControlMessage",
              0x8007000E);
            goto LABEL_39;
          }
          if ( !a3 )
          {
            v11 = 6319;
LABEL_38:
            v14 = -2147467261;
            CEventLogger::LogError(
              v10,
              &Recoverable_Error,
              L"base\\diagnosis\\ra\\core\\lib\\raticket.cpp",
              v11,
              L"CRATicket::SendControlMessage",
              0x80004003);
            goto LABEL_39;
          }
          v12 = StringCchPrintfW(v25, 0x400u, L"<RCCOMMAND NAME=\"ACKNOWLEDGE\" PROPERTY=\"%s\"/>", a3);
          v14 = v12;
          if ( v12 < 0 )
          {
            CEventLogger::LogError(
              v13,
              &Recoverable_Error,
              L"base\\diagnosis\\ra\\core\\lib\\raticket.cpp",
              0x18B5u,
              L"CRATicket::SendControlMessage",
              v12);
            goto LABEL_39;
          }
        }
        v15 = v25;
        break;
    }
  }
  else
  {
    v15 = L"<RCCOMMAND NAME=\"REMOTECTRLSTART\"/>";
  }
  v18 = SysAllocString(v15);
  v19 = v18;
  if ( !v18 )
    goto LABEL_30;
  v20 = ((__int64 (__fastcall *)(struct IRDPSRAPIVirtualChannel *, BSTR, _QWORD, _QWORD))v9->lpVtbl->SendData)(
          v9,
          v18,
          (unsigned int)-(*((_QWORD *)a1 + 26) != 0),
          0);
  v14 = v20;
  if ( v20 >= 0 )
  {
    if ( a2 == 1 )
    {
      v22 = (void (__fastcall *)(__int64))*((_QWORD *)a1 + 32);
      if ( v22 )
        v22(2);
    }
  }
  else
  {
    CEventLogger::LogError(
      v21,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\core\\lib\\raticket.cpp",
      0x18C9u,
      L"CRATicket::SendControlMessage",
      v20);
  }
  SysFreeString(v19);
LABEL_39:
  if ( v9 )
    ((void (__fastcall *)(struct IRDPSRAPIVirtualChannel *))v9->lpVtbl->Release)(v9);
  return v14;
}

```

## disassembly

```asm
0x14003ecf8  push    rbx
0x14003ecfa  push    rbp
0x14003ecfb  push    rsi
0x14003ecfc  push    rdi
0x14003ecfd  push    r14
0x14003ecff  sub     rsp, 850h
0x14003ed06  mov     rax, cs:__security_cookie
0x14003ed0d  xor     rax, rsp
0x14003ed10  mov     [rsp+878h+var_38], rax
0x14003ed18  mov     rsi, r9
0x14003ed1b  mov     rdi, r8
0x14003ed1e  mov     ebp, edx
0x14003ed20  mov     r14, rcx
0x14003ed23  mov     [rsp+878h+var_848], 0
0x14003ed2c  xor     edx, edx; Val
0x14003ed2e  mov     r8d, 800h; Size
0x14003ed34  lea     rcx, [rsp+878h+var_838]; void *
0x14003ed39  call    memset_0
0x14003ed3e  mov     r8d, 1; int
0x14003ed44  lea     rdx, [rsp+878h+var_848]; struct IRDPSRAPIVirtualChannel **
0x14003ed49  mov     rcx, r14; this
0x14003ed4c  call    ?GetControlVC@CRATicket@@QEAAJPEAPEAUIRDPSRAPIVirtualChannel@@H@Z; CRATicket::GetControlVC(IRDPSRAPIVirtualChannel * *,int)
0x14003ed51  nop
0x14003ed52  mov     rbx, [rsp+878h+var_848]
0x14003ed57  test    rbx, rbx
0x14003ed5a  setz    cl; this
0x14003ed5d  test    cl, cl
0x14003ed5f  jnz     loc_14003EF33
0x14003ed65  test    eax, eax
0x14003ed67  js      loc_14003EF33
0x14003ed6d  mov     ecx, ebp
0x14003ed6f  test    ebp, ebp
0x14003ed71  jz      loc_14003EE83
0x14003ed77  sub     ecx, 1
0x14003ed7a  jz      loc_14003EE7A
0x14003ed80  sub     ecx, 1
0x14003ed83  jz      loc_14003EE71
0x14003ed89  sub     ecx, 1
0x14003ed8c  jz      loc_14003EE68
0x14003ed92  sub     ecx, 1
0x14003ed95  jz      loc_14003EE5F
0x14003ed9b  sub     ecx, 1
0x14003ed9e  jz      loc_14003EE56
0x14003eda4  sub     ecx, 1
0x14003eda7  jz      loc_14003EE56
0x14003edad  sub     ecx, 1
0x14003edb0  jz      short loc_14003EE03
0x14003edb2  cmp     ecx, 1
0x14003edb5  jnz     loc_14003EE9E
0x14003edbb  test    rdi, rdi
0x14003edbe  jnz     short loc_14003EDCB
0x14003edc0  mov     r9d, 18AFh
0x14003edc6  jmp     loc_14003EF39
0x14003edcb  mov     r9, rdi
0x14003edce  lea     r8, aRccommandNameA; "<RCCOMMAND NAME=\"ACKNOWLEDGE\" PROPERT"...
0x14003edd5  mov     edx, 400h; unsigned __int64
0x14003edda  lea     rcx, [rsp+878h+var_838]; unsigned __int16 *
0x14003eddf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14003ede4  mov     edi, eax
0x14003ede6  test    eax, eax
0x14003ede8  jns     short loc_14003EDF9
0x14003edea  mov     [rsp+878h+var_850], eax
0x14003edee  mov     r9d, 18B5h
0x14003edf4  jmp     loc_14003EF46
0x14003edf9  lea     rcx, [rsp+878h+var_838]
0x14003edfe  jmp     loc_14003EE8A
0x14003ee03  test    rdi, rdi
0x14003ee06  jnz     short loc_14003EE13
0x14003ee08  mov     r9d, 189Ch
0x14003ee0e  jmp     loc_14003EF39
0x14003ee13  test    rsi, rsi
0x14003ee16  jnz     short loc_14003EE23
0x14003ee18  mov     r9d, 189Dh
0x14003ee1e  jmp     loc_14003EF39
0x14003ee23  mov     [rsp+878h+var_858], rsi
0x14003ee28  mov     r9, rdi
0x14003ee2b  lea     r8, aRccommandNameS; "<RCCOMMAND NAME=\"SETTINGANNOUNCE\" PRO"...
0x14003ee32  mov     edx, 400h; unsigned __int64
0x14003ee37  lea     rcx, [rsp+878h+var_838]; unsigned __int16 *
0x14003ee3c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14003ee41  mov     edi, eax
0x14003ee43  test    eax, eax
0x14003ee45  jns     short loc_14003EDF9
0x14003ee47  mov     [rsp+878h+var_850], eax
0x14003ee4b  mov     r9d, 18A4h
0x14003ee51  jmp     loc_14003EF46
0x14003ee56  lea     rcx, aRccommandNameE; "<RCCOMMAND NAME=\"ESCRC\"/>"
0x14003ee5d  jmp     short loc_14003EE8A
0x14003ee5f  lea     rcx, aRccommandNameD; "<RCCOMMAND NAME=\"DENIEDRC\"/>"
0x14003ee66  jmp     short loc_14003EE8A
0x14003ee68  lea     rcx, aRccommandNameR_0; "<RCCOMMAND NAME=\"REJECTRC\"/>"
0x14003ee6f  jmp     short loc_14003EE8A
0x14003ee71  lea     rcx, aRccommandNameA_0; "<RCCOMMAND NAME=\"ACCEPTRC\"/>"
0x14003ee78  jmp     short loc_14003EE8A
0x14003ee7a  lea     rcx, aRccommandNameR_1; "<RCCOMMAND NAME=\"REMOTECTRLEND\"/>"
0x14003ee81  jmp     short loc_14003EE8A
0x14003ee83  lea     rcx, String1; "<RCCOMMAND NAME=\"REMOTECTRLSTART\"/>"
0x14003ee8a  call    cs:__imp_SysAllocString
0x14003ee91  nop     dword ptr [rax+rax+00h]
0x14003ee96  mov     rsi, rax
0x14003ee99  test    rax, rax
0x14003ee9c  jnz     short loc_14003EEB6
0x14003ee9e  mov     edi, 8007000Eh
0x14003eea3  mov     [rsp+878h+var_850], 8007000Eh
0x14003eeab  mov     r9d, 18C0h
0x14003eeb1  jmp     loc_14003EF46
0x14003eeb6  mov     rax, [rbx]
0x14003eeb9  mov     rcx, [r14+0D0h]
0x14003eec0  neg     rcx
0x14003eec3  sbb     r8d, r8d
0x14003eec6  xor     r9d, r9d
0x14003eec9  mov     rdx, rsi
0x14003eecc  mov     rcx, rbx
0x14003eecf  mov     rax, [rax+38h]
0x14003eed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003eed8  mov     edi, eax
0x14003eeda  test    eax, eax
0x14003eedc  jns     short loc_14003EF09
0x14003eede  mov     [rsp+878h+var_850], eax; unsigned int
0x14003eee2  lea     rax, aCraticketSendc; "CRATicket::SendControlMessage"
0x14003eee9  mov     [rsp+878h+var_858], rax; unsigned __int16 *
0x14003eeee  mov     r9d, 18C9h; unsigned int
0x14003eef4  lea     r8, aBaseDiagnosisR_26; "base\\diagnosis\\ra\\core\\lib\\raticke"...
0x14003eefb  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14003ef02  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14003ef07  jmp     short loc_14003EF22
0x14003ef09  cmp     ebp, 1
0x14003ef0c  jnz     short loc_14003EF22
0x14003ef0e  mov     rax, [r14+100h]
0x14003ef15  test    rax, rax
0x14003ef18  jz      short loc_14003EF22
0x14003ef1a  lea     ecx, [rbp+1]
0x14003ef1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ef22  mov     rcx, rsi; bstrString
0x14003ef25  call    cs:__imp_SysFreeString
0x14003ef2c  nop     dword ptr [rax+rax+00h]
0x14003ef31  jmp     short loc_14003EF66
0x14003ef33  mov     r9d, 1873h; unsigned int
0x14003ef39  mov     [rsp+878h+var_850], 80004003h; unsigned int
0x14003ef41  mov     edi, 80004003h
0x14003ef46  lea     rax, aCraticketSendc; "CRATicket::SendControlMessage"
0x14003ef4d  mov     [rsp+878h+var_858], rax; unsigned __int16 *
0x14003ef52  lea     r8, aBaseDiagnosisR_26; "base\\diagnosis\\ra\\core\\lib\\raticke"...
0x14003ef59  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14003ef60  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14003ef65  nop
0x14003ef66  test    rbx, rbx
0x14003ef69  jz      short loc_14003EF7B
0x14003ef6b  mov     rax, [rbx]
0x14003ef6e  mov     rcx, rbx
0x14003ef71  mov     rax, [rax+10h]
0x14003ef75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ef7a  nop
0x14003ef7b  mov     eax, edi
0x14003ef7d  mov     rcx, [rsp+878h+var_38]
0x14003ef85  xor     rcx, rsp; StackCookie
0x14003ef88  call    __security_check_cookie
0x14003ef8d  add     rsp, 850h
0x14003ef94  pop     r14
0x14003ef96  pop     rdi
0x14003ef97  pop     rsi
0x14003ef98  pop     rbp
0x14003ef99  pop     rbx
0x14003ef9a  retn
```
