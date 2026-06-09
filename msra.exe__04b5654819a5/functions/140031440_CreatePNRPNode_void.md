# CreatePNRPNode(void *)

- ea: `0x140031440`
- end: `0x14003160c`
- name: `?CreatePNRPNode@@YAKPEAX@Z`
- size: `460`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1400273a4`
- `0x140027f24`
- `0x140031440`
- `0x140034ce4`
- `0x140037c8c`
- `0x14003fab8`
- `0x14003fb64`

## import_xrefs

- `USER32!PostMessageW` at `0x1400315c8`
- `USER32!PostMessageW` at `0x1400315c8`
- `OLEAUT32!__imp_SysFreeString` at `0x1400315dc`
- `OLEAUT32!__imp_SysFreeString` at `0x1400315f0`
- `OLEAUT32!__imp_SysFreeString` at `0x1400315dc`
- `OLEAUT32!__imp_SysFreeString` at `0x1400315f0`

## string_xrefs

- `0x14003148b`: `CreatePNRPNode`
- `0x140031505`: `CreatePNRPNode`

## pseudocode

```c
__int64 __fastcall CreatePNRPNode(HWND Parameter)
{
  unsigned __int16 *v2; // rdi
  signed int RATicketString; // eax
  CEventLogger *v4; // rcx
  unsigned __int16 *v5; // rsi
  int v6; // ebx
  unsigned int v7; // r9d
  __int64 v8; // r8
  signed int PNRPAddress; // eax
  CEventLogger *v10; // rcx
  struct CReadWriteLock *v11; // r8
  void **v12; // r9
  char *v13; // rcx
  unsigned __int16 *v15; // [rsp+58h] [rbp+10h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp+18h] BYREF

  bstrString = 0;
  v2 = 0;
  v15 = 0;
  RATicketString = CRATicket::get_RATicketString(*((CRATicket **)_AtlModule + 104), &bstrString);
  v5 = bstrString;
  v6 = RATicketString;
  if ( RATicketString >= 0 )
  {
    v8 = *((_QWORD *)_AtlModule + 104);
    if ( *(_DWORD *)(v8 + 136) == 7 )
    {
      RATicketString = EscalateAsPNRPNode(
                         *((struct CRATicket **)_AtlModule + 104),
                         (CEventLogger *)((char *)_AtlModule + 672),
                         (void **)v8,
                         bstrString);
      v6 = RATicketString;
      if ( RATicketString < 0 )
      {
        v7 = 2685;
        goto LABEL_3;
      }
      v13 = (char *)_AtlModule + 496;
      *((_DWORD *)_AtlModule + 131) = 10;
    }
    else
    {
      if ( *(_DWORD *)(v8 + 136) != 8 )
      {
        v6 = -2147467259;
        CEventLogger::LogError(
          (CEventLogger *)(unsigned int)(*(_DWORD *)(v8 + 136) - 7),
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\wizard.cpp",
          0xA85u,
          L"CreatePNRPNode",
          0x80004005);
        goto LABEL_17;
      }
      PNRPAddress = CRATicket::get_PNRPAddress(*((CRATicket **)_AtlModule + 104), &v15);
      v6 = PNRPAddress;
      if ( PNRPAddress < 0 )
      {
        CEventLogger::LogError(
          v10,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\wizard.cpp",
          0xA6Au,
          L"CreatePNRPNode",
          PNRPAddress);
        v2 = v15;
        goto LABEL_17;
      }
      v2 = v15;
      RATicketString = EscalateAsContact(v15, *((struct CRATicket **)_AtlModule + 104), v11, v12, v5);
      v6 = RATicketString;
      if ( RATicketString < 0 )
      {
        v7 = 2673;
        goto LABEL_3;
      }
      v13 = (char *)_AtlModule + 496;
      *((_DWORD *)_AtlModule + 131) = 12;
    }
    CSqmManager::ProcessRAEvent(v13, 0);
    goto LABEL_17;
  }
  v7 = 2657;
LABEL_3:
  CEventLogger::LogError(
    v4,
    &Recoverable_Error,
    L"base\\diagnosis\\ra\\ui\\wizard.cpp",
    v7,
    L"CreatePNRPNode",
    RATicketString);
LABEL_17:
  PostMessageW(Parameter, 0x8023u, (unsigned __int64)(unsigned int)~v6 >> 31, 0);
  if ( v5 )
    SysFreeString(v5);
  if ( v2 )
    SysFreeString(v2);
  return 0;
}

```

## disassembly

```asm
0x140031440  mov     rax, rsp
0x140031443  mov     [rax+8], rbx
0x140031447  push    rbp
0x140031448  push    rsi
0x140031449  push    rdi
0x14003144a  sub     rsp, 30h
0x14003144e  mov     rbp, rcx
0x140031451  mov     qword ptr [rax+18h], 0
0x140031459  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140031460  lea     rdx, [rax+18h]; unsigned __int16 **
0x140031464  xor     edi, edi
0x140031466  mov     [rax+10h], rdi
0x14003146a  mov     rcx, [rcx+340h]; this
0x140031471  call    ?get_RATicketString@CRATicket@@QEAAJPEAPEAG@Z; CRATicket::get_RATicketString(ushort * *)
0x140031476  mov     rsi, [rsp+48h+bstrString]
0x14003147b  mov     ebx, eax
0x14003147d  test    eax, eax
0x14003147f  jns     short loc_1400314AF
0x140031481  mov     r9d, 0A61h; unsigned int
0x140031487  mov     [rsp+48h+var_20], eax; unsigned int
0x14003148b  lea     rax, aCreatepnrpnode; "CreatePNRPNode"
0x140031492  lea     r8, aBaseDiagnosisR_12; "base\\diagnosis\\ra\\ui\\wizard.cpp"
0x140031499  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x14003149e  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x1400314a5  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400314aa  jmp     loc_1400315B4
0x1400314af  mov     rdx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x1400314b6  mov     r8, [rdx+340h]; void **
0x1400314bd  mov     ecx, [r8+88h]
0x1400314c4  sub     ecx, 7
0x1400314c7  jz      loc_140031575
0x1400314cd  cmp     ecx, 1
0x1400314d0  jz      short loc_1400314E7
0x1400314d2  mov     ebx, 80004005h
0x1400314d7  mov     [rsp+48h+var_20], 80004005h
0x1400314df  mov     r9d, 0A85h
0x1400314e5  jmp     short loc_14003148B
0x1400314e7  lea     rdx, [rsp+48h+arg_8]; unsigned __int16 **
0x1400314ec  mov     rcx, r8; this
0x1400314ef  call    ?get_PNRPAddress@CRATicket@@QEAAJPEAPEAG@Z; CRATicket::get_PNRPAddress(ushort * *)
0x1400314f4  mov     ebx, eax
0x1400314f6  test    eax, eax
0x1400314f8  jns     short loc_14003152D
0x1400314fa  mov     [rsp+48h+var_20], eax; unsigned int
0x1400314fe  lea     r8, aBaseDiagnosisR_12; "base\\diagnosis\\ra\\ui\\wizard.cpp"
0x140031505  lea     rax, aCreatepnrpnode; "CreatePNRPNode"
0x14003150c  mov     r9d, 0A6Ah; unsigned int
0x140031512  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140031519  mov     [rsp+48h+var_28], rax; unsigned __int16 *
0x14003151e  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140031523  mov     rdi, [rsp+48h+arg_8]
0x140031528  jmp     loc_1400315B4
0x14003152d  mov     rdx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140031534  mov     rdi, [rsp+48h+arg_8]
0x140031539  mov     rcx, rdi; unsigned __int16 *
0x14003153c  mov     [rsp+48h+var_28], rsi; unsigned __int16 *
0x140031541  mov     rdx, [rdx+340h]; struct CRATicket *
0x140031548  call    ?EscalateAsContact@@YAJPEAGPEAVCRATicket@@PEAVCReadWriteLock@@PEAPEAX0@Z; EscalateAsContact(ushort *,CRATicket *,CReadWriteLock *,void * *,ushort *)
0x14003154d  mov     ebx, eax
0x14003154f  test    eax, eax
0x140031551  jns     short loc_14003155E
0x140031553  mov     r9d, 0A71h
0x140031559  jmp     loc_140031487
0x14003155e  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140031565  add     rcx, 1F0h
0x14003156c  mov     dword ptr [rcx+1Ch], 0Ch
0x140031573  jmp     short loc_1400315AD
0x140031575  add     rdx, 2A0h; struct CReadWriteLock *
0x14003157c  mov     r9, rsi; unsigned __int16 *
0x14003157f  mov     rcx, r8; struct CRATicket *
0x140031582  call    ?EscalateAsPNRPNode@@YAJPEAVCRATicket@@PEAVCReadWriteLock@@PEAPEAXPEAG@Z; EscalateAsPNRPNode(CRATicket *,CReadWriteLock *,void * *,ushort *)
0x140031587  mov     ebx, eax
0x140031589  test    eax, eax
0x14003158b  jns     short loc_140031598
0x14003158d  mov     r9d, 0A7Dh
0x140031593  jmp     loc_140031487
0x140031598  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x14003159f  add     rcx, 1F0h
0x1400315a6  mov     dword ptr [rcx+1Ch], 0Ah
0x1400315ad  xor     edx, edx
0x1400315af  call    ?ProcessRAEvent@CSqmManager@@QEAAXW4_RASQM_EVENT@@@Z; CSqmManager::ProcessRAEvent(_RASQM_EVENT)
0x1400315b4  not     ebx
0x1400315b6  xor     r9d, r9d; lParam
0x1400315b9  mov     r8d, ebx
0x1400315bc  mov     edx, 8023h; Msg
0x1400315c1  shr     r8, 1Fh; wParam
0x1400315c5  mov     rcx, rbp; hWnd
0x1400315c8  call    cs:__imp_PostMessageW
0x1400315cf  nop     dword ptr [rax+rax+00h]
0x1400315d4  test    rsi, rsi
0x1400315d7  jz      short loc_1400315E8
0x1400315d9  mov     rcx, rsi; bstrString
0x1400315dc  call    cs:__imp_SysFreeString
0x1400315e3  nop     dword ptr [rax+rax+00h]
0x1400315e8  test    rdi, rdi
0x1400315eb  jz      short loc_1400315FC
0x1400315ed  mov     rcx, rdi; bstrString
0x1400315f0  call    cs:__imp_SysFreeString
0x1400315f7  nop     dword ptr [rax+rax+00h]
0x1400315fc  mov     rbx, [rsp+48h+arg_0]
0x140031601  xor     eax, eax
0x140031603  add     rsp, 30h
0x140031607  pop     rdi
0x140031608  pop     rsi
0x140031609  pop     rbp
0x14003160a  retn
```
