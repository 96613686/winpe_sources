# QueueSupplicantEvent

- ea: `0x18000cf70`
- end: `0x18000d304`
- name: `QueueSupplicantEvent`
- size: `916`
- prototype: ``
- caller_count: `13`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180002020`
- `0x180009540`
- `0x180009be0`
- `0x18000ade0`
- `0x18000c870`
- `0x18000cd90`
- `0x18000dad0`
- `0x18000ee70`
- `0x180023b6c`
- `0x180023f94`
- `0x1800240fc`
- `0x180024238`
- `0x1800243a4`

## callees

- `0x180005440`
- `0x180007f60`
- `0x18000cf70`
- `0x18000d310`
- `0x1800214f0`

## string_xrefs

- `0x18000d070`: `PAEConfigChanged`
- `0x18000d13c`: `BackendEapConfigChanged`

## pseudocode

```c
__int64 __fastcall QueueSupplicantEvent(__int64 a1)
{
  int v2; // eax
  __int64 v3; // rdi
  const wchar_t *v4; // r9
  __int64 result; // rax
  unsigned int v6; // ebx
  _QWORD *v7; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 29, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids);
  v2 = *(_DWORD *)(a1 + 16);
  v3 = *(_QWORD *)(a1 + 24);
  switch ( v2 )
  {
    case 35:
      v4 = L"BackendEapPktReceived";
      break;
    case 5:
      v4 = L"PAEStopAuth";
      break;
    case 8:
      v4 = L"PAESetRuntimeState";
      break;
    case 29:
      v4 = L"BackendEapActivate";
      break;
    case 38:
      v4 = L"BackendEapWaitForPkt";
      break;
    default:
      switch ( v2 )
      {
        case 0:
          v4 = L"SupplicantNone";
          break;
        case 1:
          v4 = L"SupplicantForceAuthenticated";
          break;
        case 2:
          v4 = L"SupplicantSelfAuthRestarted";
          break;
        case 3:
          v4 = L"SupplicantPeerAuthRestarted";
          break;
        case 4:
          v4 = L"PAEUCT";
          break;
        case 6:
          v4 = L"PAEStartAuth";
          break;
        case 7:
          v4 = L"SetAuthParams";
          break;
        case 9:
          v4 = L"PAESessionChange";
          break;
        case 10:
          v4 = L"PAEUserLogoff";
          break;
        case 11:
          v4 = L"PAEConfigChanged";
          break;
        case 12:
          v4 = L"PAEUserUnavailable";
          break;
        case 13:
          v4 = L"PAEUserIdentified";
          break;
        case 14:
          v4 = L"PAEStartWhen1";
          break;
        case 15:
          v4 = L"PAEStartWhen2";
          break;
        case 16:
          v4 = L"PAEAuthenticatorNoLongerPresent";
          break;
        case 17:
          v4 = L"PAEAuthenticating";
          break;
        case 18:
          v4 = L"PAESuppSuccess";
          break;
        case 19:
          v4 = L"PAESuppFail";
          break;
        case 20:
          v4 = L"PAESuppTimeout";
          break;
        case 21:
          v4 = L"PAESuppNoRetry";
          break;
        case 22:
          v4 = L"PAEHeldWhile";
          break;
        case 23:
          v4 = L"PAEGiveup";
          break;
        case 24:
          v4 = L"BackendUCT";
          break;
        case 25:
          v4 = L"BackendStopBackend";
          break;
        case 26:
          v4 = L"BackendStartBackend";
          break;
        case 27:
          v4 = L"BackendUserChanged";
          break;
        case 28:
          v4 = L"BackendEapConfigChanged";
          break;
        case 30:
          v4 = L"BackendGotInteractiveData";
          break;
        case 31:
          v4 = L"BackendUINeeded";
          break;
        case 32:
          v4 = L"BackendUIResponse";
          break;
        case 33:
          v4 = L"BackendUIFailure";
          break;
        case 34:
          v4 = L"BackendAuthWhile";
          break;
        case 36:
          v4 = L"BackendLocalEapFail";
          break;
        case 37:
          v4 = L"BackendLocalEapSuccess";
          break;
        case 39:
          v4 = L"BackendSetEapAttributes";
          break;
        case 40:
          v4 = L"SupplicantEventMax";
          break;
        default:
          v4 = L"SupplicantInvalidEvent";
          break;
      }
      break;
  }
  result = QueueOneXEvent(a1, (int)v3 + 2808, (unsigned int)L"SupplicantQueue", (_DWORD)v4, 0);
  v6 = result;
  if ( !(_DWORD)result )
    goto LABEL_56;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return result;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      30,
      WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids,
      *(unsigned int *)(v3 + 20),
      result);
LABEL_56:
    v7 = WPP_GLOBAL_Control;
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_DWORD *)v7 + 17) & 0x800) != 0 )
    WPP_SF_D(v7[7], 31, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18000cf70  mov     [rsp+arg_0], rbx
0x18000cf75  mov     [rsp+arg_8], rsi
0x18000cf7a  push    rdi
0x18000cf7b  sub     rsp, 30h
0x18000cf7f  mov     rbx, rcx
0x18000cf82  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf89  lea     rsi, WPP_GLOBAL_Control
0x18000cf90  cmp     rcx, rsi
0x18000cf93  jz      short loc_18000CFB3
0x18000cf95  test    dword ptr [rcx+44h], 800h
0x18000cf9c  jz      short loc_18000CFB3
0x18000cf9e  mov     rcx, [rcx+38h]
0x18000cfa2  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000cfa9  mov     edx, 1Dh
0x18000cfae  call    WPP_SF_
0x18000cfb3  movsxd  rax, dword ptr [rbx+10h]
0x18000cfb7  mov     rdi, [rbx+18h]
0x18000cfbb  cmp     eax, 23h ; '#'
0x18000cfbe  jz      loc_18000D1C6
0x18000cfc4  cmp     eax, 5
0x18000cfc7  jz      loc_18000D1BD
0x18000cfcd  cmp     eax, 8
0x18000cfd0  jz      loc_18000D1B4
0x18000cfd6  cmp     eax, 1Dh
0x18000cfd9  jz      loc_18000D1AB
0x18000cfdf  cmp     eax, 26h ; '&'
0x18000cfe2  jz      loc_18000D1A2
0x18000cfe8  cmp     eax, 28h; switch 41 cases
0x18000cfeb  ja      def_18000D002; jumptable 000000018000D002 default case, cases 5,8,29,35,38
0x18000cff1  lea     rdx, __ImageBase
0x18000cff8  mov     ecx, ds:(jpt_18000D002 - 180000000h)[rdx+rax*4]
0x18000cfff  add     rcx, rdx
0x18000d002  jmp     rcx; switch jump
0x18000d004  lea     r9, aSupplicantnone; jumptable 000000018000D002 case 0
0x18000d00b  jmp     loc_18000D1CD
0x18000d010  lea     r9, aSupplicantforc; jumptable 000000018000D002 case 1
0x18000d017  jmp     loc_18000D1CD
0x18000d01c  lea     r9, aSupplicantself; jumptable 000000018000D002 case 2
0x18000d023  jmp     loc_18000D1CD
0x18000d028  lea     r9, aSupplicantpeer; jumptable 000000018000D002 case 3
0x18000d02f  jmp     loc_18000D1CD
0x18000d034  lea     r9, aPaeuct; jumptable 000000018000D002 case 4
0x18000d03b  jmp     loc_18000D1CD
0x18000d040  lea     r9, aPaestartauth; jumptable 000000018000D002 case 6
0x18000d047  jmp     loc_18000D1CD
0x18000d04c  lea     r9, aSetauthparams; jumptable 000000018000D002 case 7
0x18000d053  jmp     loc_18000D1CD
0x18000d058  lea     r9, aPaesessionchan; jumptable 000000018000D002 case 9
0x18000d05f  jmp     loc_18000D1CD
0x18000d064  lea     r9, aPaeuserlogoff; jumptable 000000018000D002 case 10
0x18000d06b  jmp     loc_18000D1CD
0x18000d070  lea     r9, aPaeconfigchang; jumptable 000000018000D002 case 11
0x18000d077  jmp     loc_18000D1CD
0x18000d07c  lea     r9, aPaeuserunavail; jumptable 000000018000D002 case 12
0x18000d083  jmp     loc_18000D1CD
0x18000d088  lea     r9, aPaeuseridentif; jumptable 000000018000D002 case 13
0x18000d08f  jmp     loc_18000D1CD
0x18000d094  lea     r9, aPaestartwhen1; jumptable 000000018000D002 case 14
0x18000d09b  jmp     loc_18000D1CD
0x18000d0a0  lea     r9, aPaestartwhen2; jumptable 000000018000D002 case 15
0x18000d0a7  jmp     loc_18000D1CD
0x18000d0ac  lea     r9, aPaeauthenticat; jumptable 000000018000D002 case 16
0x18000d0b3  jmp     loc_18000D1CD
0x18000d0b8  lea     r9, aPaeauthenticat_0; jumptable 000000018000D002 case 17
0x18000d0bf  jmp     loc_18000D1CD
0x18000d0c4  lea     r9, aPaesuppsuccess; jumptable 000000018000D002 case 18
0x18000d0cb  jmp     loc_18000D1CD
0x18000d0d0  lea     r9, aPaesuppfail; jumptable 000000018000D002 case 19
0x18000d0d7  jmp     loc_18000D1CD
0x18000d0dc  lea     r9, aPaesupptimeout; jumptable 000000018000D002 case 20
0x18000d0e3  jmp     loc_18000D1CD
0x18000d0e8  lea     r9, aPaesuppnoretry; jumptable 000000018000D002 case 21
0x18000d0ef  jmp     loc_18000D1CD
0x18000d0f4  lea     r9, aPaeheldwhile; jumptable 000000018000D002 case 22
0x18000d0fb  jmp     loc_18000D1CD
0x18000d100  lea     r9, aPaegiveup; jumptable 000000018000D002 case 23
0x18000d107  jmp     loc_18000D1CD
0x18000d10c  lea     r9, aBackenduct; jumptable 000000018000D002 case 24
0x18000d113  jmp     loc_18000D1CD
0x18000d118  lea     r9, aBackendstopbac; jumptable 000000018000D002 case 25
0x18000d11f  jmp     loc_18000D1CD
0x18000d124  lea     r9, aBackendstartba; jumptable 000000018000D002 case 26
0x18000d12b  jmp     loc_18000D1CD
0x18000d130  lea     r9, aBackendusercha; jumptable 000000018000D002 case 27
0x18000d137  jmp     loc_18000D1CD
0x18000d13c  lea     r9, aBackendeapconf; jumptable 000000018000D002 case 28
0x18000d143  jmp     loc_18000D1CD
0x18000d148  lea     r9, aBackendgotinte; jumptable 000000018000D002 case 30
0x18000d14f  jmp     short loc_18000D1CD
0x18000d151  lea     r9, aBackenduineede; jumptable 000000018000D002 case 31
0x18000d158  jmp     short loc_18000D1CD
0x18000d15a  lea     r9, aBackenduirespo; jumptable 000000018000D002 case 32
0x18000d161  jmp     short loc_18000D1CD
0x18000d163  lea     r9, aBackenduifailu; jumptable 000000018000D002 case 33
0x18000d16a  jmp     short loc_18000D1CD
0x18000d16c  lea     r9, aBackendauthwhi; jumptable 000000018000D002 case 34
0x18000d173  jmp     short loc_18000D1CD
0x18000d175  lea     r9, aBackendlocalea_0; jumptable 000000018000D002 case 36
0x18000d17c  jmp     short loc_18000D1CD
0x18000d17e  lea     r9, aBackendlocalea; jumptable 000000018000D002 case 37
0x18000d185  jmp     short loc_18000D1CD
0x18000d187  lea     r9, aBackendseteapa; jumptable 000000018000D002 case 39
0x18000d18e  jmp     short loc_18000D1CD
0x18000d190  lea     r9, aSupplicanteven; jumptable 000000018000D002 case 40
0x18000d197  jmp     short loc_18000D1CD
0x18000d199  lea     r9, aSupplicantinva; jumptable 000000018000D002 default case, cases 5,8,29,35,38
0x18000d1a0  jmp     short loc_18000D1CD
0x18000d1a2  lea     r9, aBackendeapwait; "BackendEapWaitForPkt"
0x18000d1a9  jmp     short loc_18000D1CD
0x18000d1ab  lea     r9, aBackendeapacti; "BackendEapActivate"
0x18000d1b2  jmp     short loc_18000D1CD
0x18000d1b4  lea     r9, aPaesetruntimes; "PAESetRuntimeState"
0x18000d1bb  jmp     short loc_18000D1CD
0x18000d1bd  lea     r9, aPaestopauth; "PAEStopAuth"
0x18000d1c4  jmp     short loc_18000D1CD
0x18000d1c6  lea     r9, aBackendeappktr; "BackendEapPktReceived"
0x18000d1cd  lea     rdx, [rdi+0AF8h]
0x18000d1d4  mov     [rsp+38h+var_18], 0
0x18000d1dc  lea     r8, aSupplicantqueu; "SupplicantQueue"
0x18000d1e3  mov     rcx, rbx
0x18000d1e6  call    QueueOneXEvent
0x18000d1eb  mov     ebx, eax
0x18000d1ed  test    eax, eax
0x18000d1ef  jz      short loc_18000D220
0x18000d1f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d1f8  cmp     rcx, rsi
0x18000d1fb  jz      short loc_18000D24F
0x18000d1fd  test    byte ptr [rcx+44h], 1
0x18000d201  jz      short loc_18000D227
0x18000d203  mov     r9d, [rdi+14h]
0x18000d207  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000d20e  mov     rcx, [rcx+38h]
0x18000d212  mov     edx, 1Eh
0x18000d217  mov     [rsp+38h+var_18], eax
0x18000d21b  call    WPP_SF_dd
0x18000d220  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d227  cmp     rcx, rsi
0x18000d22a  jz      short loc_18000D24D
0x18000d22c  test    dword ptr [rcx+44h], 800h
0x18000d233  jz      short loc_18000D24D
0x18000d235  mov     rcx, [rcx+38h]
0x18000d239  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000d240  mov     edx, 1Fh
0x18000d245  mov     r9d, ebx
0x18000d248  call    WPP_SF_D
0x18000d24d  mov     eax, ebx
0x18000d24f  mov     rbx, [rsp+38h+arg_0]
0x18000d254  mov     rsi, [rsp+38h+arg_8]
0x18000d259  add     rsp, 30h
0x18000d25d  pop     rdi
0x18000d25e  retn
```
