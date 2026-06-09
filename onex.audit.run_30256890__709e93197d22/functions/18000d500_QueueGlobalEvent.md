# QueueGlobalEvent

- ea: `0x18000d500`
- end: `0x18000d6bc`
- name: `QueueGlobalEvent`
- size: `444`
- prototype: ``
- caller_count: `11`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180003a1c`
- `0x18000d8d0`
- `0x18000e6c0`
- `0x18000eab4`
- `0x18000ee70`
- `0x180010b20`
- `0x180019080`
- `0x180023b6c`
- `0x180024238`
- `0x18002b6d0`
- `0x18002bbf8`

## callees

- `0x180005440`
- `0x180007f60`
- `0x18000d310`
- `0x18000d500`
- `0x1800214f0`

## string_xrefs

- `0x18000d59d`: `ConfigChanged`

## pseudocode

```c
__int64 __fastcall QueueGlobalEvent(__int64 a1)
{
  __int64 v2; // rdx
  int v3; // eax
  unsigned int v4; // edi
  const wchar_t *v5; // r9
  __int64 result; // rax
  unsigned int v7; // ebx
  _QWORD *v8; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x800) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 26, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids);
  v2 = *(_QWORD *)(a1 + 24);
  v3 = *(_DWORD *)(a1 + 16);
  v4 = *(_DWORD *)(v2 + 20);
  if ( v3 == 1 )
  {
    v5 = L"StartAuth";
  }
  else if ( v3 == 6 )
  {
    v5 = L"EapPkt";
  }
  else
  {
    switch ( v3 )
    {
      case 0:
        v5 = L"StopAuth";
        break;
      case 2:
        v5 = L"SetAuthParams";
        break;
      case 3:
        v5 = L"ForceAuthenticated";
        break;
      case 4:
        v5 = L"SessionNotification";
        break;
      case 5:
        v5 = L"ConfigChanged";
        break;
      case 7:
        v5 = L"Timeout";
        break;
      case 8:
        v5 = L"UIResponse";
        break;
      case 9:
        v5 = L"SetEapAttributes";
        break;
      case 10:
        v5 = L"SetRuntimeState";
        break;
      case 11:
        v5 = L"SelfAuthRestarted";
        break;
      case 12:
        v5 = L"Max";
        break;
      default:
        v5 = L"OneXEventInvalid";
        break;
    }
  }
  result = QueueOneXEvent(a1, (int)v2 + 176, (unsigned int)L"GlobalQueue", (_DWORD)v5, 1);
  v7 = result;
  if ( !(_DWORD)result )
    goto LABEL_25;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return result;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 7), 27, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v4, result);
LABEL_25:
    v8 = WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 17) & 0x800) != 0 )
    WPP_SF_D(v8[7], 28, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x18000d500  mov     [rsp+arg_0], rbx
0x18000d505  mov     [rsp+arg_8], rsi
0x18000d50a  push    rdi
0x18000d50b  sub     rsp, 30h
0x18000d50f  mov     rbx, rcx
0x18000d512  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d519  lea     rsi, WPP_GLOBAL_Control
0x18000d520  cmp     rcx, rsi
0x18000d523  jz      short loc_18000D543
0x18000d525  test    dword ptr [rcx+44h], 800h
0x18000d52c  jz      short loc_18000D543
0x18000d52e  mov     rcx, [rcx+38h]
0x18000d532  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000d539  mov     edx, 1Ah
0x18000d53e  call    WPP_SF_
0x18000d543  mov     rdx, [rbx+18h]
0x18000d547  movsxd  rax, dword ptr [rbx+10h]
0x18000d54b  mov     edi, [rdx+14h]
0x18000d54e  cmp     eax, 1
0x18000d551  jz      loc_18000D5EE
0x18000d557  cmp     eax, 6
0x18000d55a  jz      loc_18000D5E5
0x18000d560  cmp     eax, 0Ch; switch 13 cases
0x18000d563  ja      short def_18000D577; jumptable 000000018000D577 default case, cases 1,6
0x18000d565  lea     r8, __ImageBase
0x18000d56c  mov     ecx, ds:(jpt_18000D577 - 180000000h)[r8+rax*4]
0x18000d574  add     rcx, r8
0x18000d577  jmp     rcx; switch jump
0x18000d579  lea     r9, aStopauth; jumptable 000000018000D577 case 0
0x18000d580  jmp     short loc_18000D5F5
0x18000d582  lea     r9, aSetauthparams; jumptable 000000018000D577 case 2
0x18000d589  jmp     short loc_18000D5F5
0x18000d58b  lea     r9, aForceauthentic; jumptable 000000018000D577 case 3
0x18000d592  jmp     short loc_18000D5F5
0x18000d594  lea     r9, aSessionnotific; jumptable 000000018000D577 case 4
0x18000d59b  jmp     short loc_18000D5F5
0x18000d59d  lea     r9, aConfigchanged; jumptable 000000018000D577 case 5
0x18000d5a4  jmp     short loc_18000D5F5
0x18000d5a6  lea     r9, aTimeout; jumptable 000000018000D577 case 7
0x18000d5ad  jmp     short loc_18000D5F5
0x18000d5af  lea     r9, aUiresponse; jumptable 000000018000D577 case 8
0x18000d5b6  jmp     short loc_18000D5F5
0x18000d5b8  lea     r9, aSeteapattribut; jumptable 000000018000D577 case 9
0x18000d5bf  jmp     short loc_18000D5F5
0x18000d5c1  lea     r9, aSetruntimestat; jumptable 000000018000D577 case 10
0x18000d5c8  jmp     short loc_18000D5F5
0x18000d5ca  lea     r9, aSelfauthrestar; jumptable 000000018000D577 case 11
0x18000d5d1  jmp     short loc_18000D5F5
0x18000d5d3  lea     r9, aMax; jumptable 000000018000D577 case 12
0x18000d5da  jmp     short loc_18000D5F5
0x18000d5dc  lea     r9, aOnexeventinval; jumptable 000000018000D577 default case, cases 1,6
0x18000d5e3  jmp     short loc_18000D5F5
0x18000d5e5  lea     r9, aEappkt; "EapPkt"
0x18000d5ec  jmp     short loc_18000D5F5
0x18000d5ee  lea     r9, aStartauth; "StartAuth"
0x18000d5f5  add     rdx, 0B0h
0x18000d5fc  mov     [rsp+38h+var_18], 1
0x18000d604  lea     r8, aGlobalqueue; "GlobalQueue"
0x18000d60b  mov     rcx, rbx
0x18000d60e  call    QueueOneXEvent
0x18000d613  mov     ebx, eax
0x18000d615  test    eax, eax
0x18000d617  jz      short loc_18000D647
0x18000d619  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d620  cmp     rcx, rsi
0x18000d623  jz      short loc_18000D676
0x18000d625  test    byte ptr [rcx+44h], 1
0x18000d629  jz      short loc_18000D64E
0x18000d62b  mov     rcx, [rcx+38h]
0x18000d62f  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000d636  mov     edx, 1Bh
0x18000d63b  mov     [rsp+38h+var_18], eax
0x18000d63f  mov     r9d, edi
0x18000d642  call    WPP_SF_dd
0x18000d647  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d64e  cmp     rcx, rsi
0x18000d651  jz      short loc_18000D674
0x18000d653  test    dword ptr [rcx+44h], 800h
0x18000d65a  jz      short loc_18000D674
0x18000d65c  mov     rcx, [rcx+38h]
0x18000d660  lea     r8, WPP_2cf9da9a762230b0257d97f0bfd8f1af_Traceguids
0x18000d667  mov     edx, 1Ch
0x18000d66c  mov     r9d, ebx
0x18000d66f  call    WPP_SF_D
0x18000d674  mov     eax, ebx
0x18000d676  mov     rbx, [rsp+38h+arg_0]
0x18000d67b  mov     rsi, [rsp+38h+arg_8]
0x18000d680  add     rsp, 30h
0x18000d684  pop     rdi
0x18000d685  retn
```
