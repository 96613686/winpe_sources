# GetGlobalEventDescription

- ea: `0x18000ad00`
- end: `0x18000ad95`
- name: `GetGlobalEventDescription`
- size: `149`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000b330`
- `0x1800183c0`
- `0x18001be88`

## callees

- `0x18000ad00`

## string_xrefs

- `0x18000ad55`: `ConfigChanged`

## pseudocode

```c
const wchar_t *__fastcall GetGlobalEventDescription(int a1)
{
  const wchar_t *result; // rax

  if ( a1 == 1 )
    return L"StartAuth";
  if ( a1 == 6 )
    return L"EapPkt";
  switch ( a1 )
  {
    case 0:
      result = L"StopAuth";
      break;
    case 2:
      result = L"SetAuthParams";
      break;
    case 3:
      result = L"ForceAuthenticated";
      break;
    case 4:
      result = L"SessionNotification";
      break;
    case 5:
      result = L"ConfigChanged";
      break;
    case 7:
      result = L"Timeout";
      break;
    case 8:
      result = L"UIResponse";
      break;
    case 9:
      result = L"SetEapAttributes";
      break;
    case 10:
      result = L"SetRuntimeState";
      break;
    case 11:
      result = L"SelfAuthRestarted";
      break;
    case 12:
      result = L"Max";
      break;
    default:
      result = L"OneXEventInvalid";
      break;
  }
  return result;
}

```

## disassembly

```asm
0x18000ad00  cmp     ecx, 1
0x18000ad03  jnz     short loc_18000AD0D
0x18000ad05  lea     rax, aStartauth; "StartAuth"
0x18000ad0c  retn
0x18000ad0d  cmp     ecx, 6
0x18000ad10  jnz     short loc_18000AD1A
0x18000ad12  lea     rax, aEappkt; "EapPkt"
0x18000ad19  retn
0x18000ad1a  cmp     ecx, 0Ch; switch 13 cases
0x18000ad1d  ja      short def_18000AD33; jumptable 000000018000AD33 default case, cases 1,6
0x18000ad1f  movsxd  rax, ecx
0x18000ad22  lea     rdx, __ImageBase
0x18000ad29  mov     ecx, ds:(jpt_18000AD33 - 180000000h)[rdx+rax*4]
0x18000ad30  add     rcx, rdx
0x18000ad33  jmp     rcx; switch jump
0x18000ad35  lea     rax, aStopauth; jumptable 000000018000AD33 case 0
0x18000ad3c  retn
0x18000ad3d  lea     rax, aSetauthparams; jumptable 000000018000AD33 case 2
0x18000ad44  retn
0x18000ad45  lea     rax, aForceauthentic; jumptable 000000018000AD33 case 3
0x18000ad4c  retn
0x18000ad4d  lea     rax, aSessionnotific; jumptable 000000018000AD33 case 4
0x18000ad54  retn
0x18000ad55  lea     rax, aConfigchanged; jumptable 000000018000AD33 case 5
0x18000ad5c  retn
0x18000ad5d  lea     rax, aTimeout; jumptable 000000018000AD33 case 7
0x18000ad64  retn
0x18000ad65  lea     rax, aUiresponse; jumptable 000000018000AD33 case 8
0x18000ad6c  retn
0x18000ad6d  lea     rax, aSeteapattribut; jumptable 000000018000AD33 case 9
0x18000ad74  retn
0x18000ad75  lea     rax, aSetruntimestat; jumptable 000000018000AD33 case 10
0x18000ad7c  retn
0x18000ad7d  lea     rax, aSelfauthrestar; jumptable 000000018000AD33 case 11
0x18000ad84  retn
0x18000ad85  lea     rax, aMax; jumptable 000000018000AD33 case 12
0x18000ad8c  retn
0x18000ad8d  lea     rax, aOnexeventinval; jumptable 000000018000AD33 default case, cases 1,6
0x18000ad94  retn
```
