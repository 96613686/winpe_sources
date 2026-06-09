# GetSupplicantEventDescription

- ea: `0x18000c630`
- end: `0x18000c7b8`
- name: `GetSupplicantEventDescription`
- size: `392`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000ba30`
- `0x1800183c0`

## callees

- `0x18000c630`

## string_xrefs

- `0x18000c6d8`: `PAEConfigChanged`
- `0x18000c760`: `BackendEapConfigChanged`

## pseudocode

```c
const wchar_t *__fastcall GetSupplicantEventDescription(int a1)
{
  const wchar_t *result; // rax

  switch ( a1 )
  {
    case 35:
      return L"BackendEapPktReceived";
    case 5:
      return L"PAEStopAuth";
    case 8:
      return L"PAESetRuntimeState";
    case 29:
      return L"BackendEapActivate";
    case 38:
      return L"BackendEapWaitForPkt";
  }
  switch ( a1 )
  {
    case 0:
      result = L"SupplicantNone";
      break;
    case 1:
      result = L"SupplicantForceAuthenticated";
      break;
    case 2:
      result = L"SupplicantSelfAuthRestarted";
      break;
    case 3:
      result = L"SupplicantPeerAuthRestarted";
      break;
    case 4:
      result = L"PAEUCT";
      break;
    case 6:
      result = L"PAEStartAuth";
      break;
    case 7:
      result = L"SetAuthParams";
      break;
    case 9:
      result = L"PAESessionChange";
      break;
    case 10:
      result = L"PAEUserLogoff";
      break;
    case 11:
      result = L"PAEConfigChanged";
      break;
    case 12:
      result = L"PAEUserUnavailable";
      break;
    case 13:
      result = L"PAEUserIdentified";
      break;
    case 14:
      result = L"PAEStartWhen1";
      break;
    case 15:
      result = L"PAEStartWhen2";
      break;
    case 16:
      result = L"PAEAuthenticatorNoLongerPresent";
      break;
    case 17:
      result = L"PAEAuthenticating";
      break;
    case 18:
      result = L"PAESuppSuccess";
      break;
    case 19:
      result = L"PAESuppFail";
      break;
    case 20:
      result = L"PAESuppTimeout";
      break;
    case 21:
      result = L"PAESuppNoRetry";
      break;
    case 22:
      result = L"PAEHeldWhile";
      break;
    case 23:
      result = L"PAEGiveup";
      break;
    case 24:
      result = L"BackendUCT";
      break;
    case 25:
      result = L"BackendStopBackend";
      break;
    case 26:
      result = L"BackendStartBackend";
      break;
    case 27:
      result = L"BackendUserChanged";
      break;
    case 28:
      result = L"BackendEapConfigChanged";
      break;
    case 30:
      result = L"BackendGotInteractiveData";
      break;
    case 31:
      result = L"BackendUINeeded";
      break;
    case 32:
      result = L"BackendUIResponse";
      break;
    case 33:
      result = L"BackendUIFailure";
      break;
    case 34:
      result = L"BackendAuthWhile";
      break;
    case 36:
      result = L"BackendLocalEapFail";
      break;
    case 37:
      result = L"BackendLocalEapSuccess";
      break;
    case 39:
      result = L"BackendSetEapAttributes";
      break;
    case 40:
      result = L"SupplicantEventMax";
      break;
    default:
      result = L"SupplicantInvalidEvent";
      break;
  }
  return result;
}

```

## disassembly

```asm
0x18000c630  cmp     ecx, 23h ; '#'
0x18000c633  jz      short loc_18000C64C
0x18000c635  cmp     ecx, 5
0x18000c638  jz      short loc_18000C654
0x18000c63a  cmp     ecx, 8
0x18000c63d  jz      short loc_18000C669
0x18000c63f  cmp     ecx, 1Dh
0x18000c642  jnz     short loc_18000C65C
0x18000c644  lea     rax, aBackendeapacti; "BackendEapActivate"
0x18000c64b  retn
0x18000c64c  lea     rax, aBackendeappktr; "BackendEapPktReceived"
0x18000c653  retn
0x18000c654  lea     rax, aPaestopauth; "PAEStopAuth"
0x18000c65b  retn
0x18000c65c  cmp     ecx, 26h ; '&'
0x18000c65f  jnz     short loc_18000C671
0x18000c661  lea     rax, aBackendeapwait; "BackendEapWaitForPkt"
0x18000c668  retn
0x18000c669  lea     rax, aPaesetruntimes; "PAESetRuntimeState"
0x18000c670  retn
0x18000c671  cmp     ecx, 28h; switch 41 cases
0x18000c674  ja      def_18000C68E; jumptable 000000018000C68E default case, cases 5,8,29,35,38
0x18000c67a  movsxd  rax, ecx
0x18000c67d  lea     rdx, __ImageBase
0x18000c684  mov     ecx, ds:(jpt_18000C68E - 180000000h)[rdx+rax*4]
0x18000c68b  add     rcx, rdx
0x18000c68e  jmp     rcx; switch jump
0x18000c690  lea     rax, aSupplicantnone; jumptable 000000018000C68E case 0
0x18000c697  retn
0x18000c698  lea     rax, aSupplicantforc; jumptable 000000018000C68E case 1
0x18000c69f  retn
0x18000c6a0  lea     rax, aSupplicantself; jumptable 000000018000C68E case 2
0x18000c6a7  retn
0x18000c6a8  lea     rax, aSupplicantpeer; jumptable 000000018000C68E case 3
0x18000c6af  retn
0x18000c6b0  lea     rax, aPaeuct; jumptable 000000018000C68E case 4
0x18000c6b7  retn
0x18000c6b8  lea     rax, aPaestartauth; jumptable 000000018000C68E case 6
0x18000c6bf  retn
0x18000c6c0  lea     rax, aSetauthparams; jumptable 000000018000C68E case 7
0x18000c6c7  retn
0x18000c6c8  lea     rax, aPaesessionchan; jumptable 000000018000C68E case 9
0x18000c6cf  retn
0x18000c6d0  lea     rax, aPaeuserlogoff; jumptable 000000018000C68E case 10
0x18000c6d7  retn
0x18000c6d8  lea     rax, aPaeconfigchang; jumptable 000000018000C68E case 11
0x18000c6df  retn
0x18000c6e0  lea     rax, aPaeuserunavail; jumptable 000000018000C68E case 12
0x18000c6e7  retn
0x18000c6e8  lea     rax, aPaeuseridentif; jumptable 000000018000C68E case 13
0x18000c6ef  retn
0x18000c6f0  lea     rax, aPaestartwhen1; jumptable 000000018000C68E case 14
0x18000c6f7  retn
0x18000c6f8  lea     rax, aPaestartwhen2; jumptable 000000018000C68E case 15
0x18000c6ff  retn
0x18000c700  lea     rax, aPaeauthenticat; jumptable 000000018000C68E case 16
0x18000c707  retn
0x18000c708  lea     rax, aPaeauthenticat_0; jumptable 000000018000C68E case 17
0x18000c70f  retn
0x18000c710  lea     rax, aPaesuppsuccess; jumptable 000000018000C68E case 18
0x18000c717  retn
0x18000c718  lea     rax, aPaesuppfail; jumptable 000000018000C68E case 19
0x18000c71f  retn
0x18000c720  lea     rax, aPaesupptimeout; jumptable 000000018000C68E case 20
0x18000c727  retn
0x18000c728  lea     rax, aPaesuppnoretry; jumptable 000000018000C68E case 21
0x18000c72f  retn
0x18000c730  lea     rax, aPaeheldwhile; jumptable 000000018000C68E case 22
0x18000c737  retn
0x18000c738  lea     rax, aPaegiveup; jumptable 000000018000C68E case 23
0x18000c73f  retn
0x18000c740  lea     rax, aBackenduct; jumptable 000000018000C68E case 24
0x18000c747  retn
0x18000c748  lea     rax, aBackendstopbac; jumptable 000000018000C68E case 25
0x18000c74f  retn
0x18000c750  lea     rax, aBackendstartba; jumptable 000000018000C68E case 26
0x18000c757  retn
0x18000c758  lea     rax, aBackendusercha; jumptable 000000018000C68E case 27
0x18000c75f  retn
0x18000c760  lea     rax, aBackendeapconf; jumptable 000000018000C68E case 28
0x18000c767  retn
0x18000c768  lea     rax, aBackendgotinte; jumptable 000000018000C68E case 30
0x18000c76f  retn
0x18000c770  lea     rax, aBackenduineede; jumptable 000000018000C68E case 31
0x18000c777  retn
0x18000c778  lea     rax, aBackenduirespo; jumptable 000000018000C68E case 32
0x18000c77f  retn
0x18000c780  lea     rax, aBackenduifailu; jumptable 000000018000C68E case 33
0x18000c787  retn
0x18000c788  lea     rax, aBackendauthwhi; jumptable 000000018000C68E case 34
0x18000c78f  retn
0x18000c790  lea     rax, aBackendlocalea_0; jumptable 000000018000C68E case 36
0x18000c797  retn
0x18000c798  lea     rax, aBackendlocalea; jumptable 000000018000C68E case 37
0x18000c79f  retn
0x18000c7a0  lea     rax, aBackendseteapa; jumptable 000000018000C68E case 39
0x18000c7a7  retn
0x18000c7a8  lea     rax, aSupplicanteven; jumptable 000000018000C68E case 40
0x18000c7af  retn
0x18000c7b0  lea     rax, aSupplicantinva; jumptable 000000018000C68E default case, cases 5,8,29,35,38
0x18000c7b7  retn
```
