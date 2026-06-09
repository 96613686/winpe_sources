# GetFrontEndStateDescription

- ea: `0x180016980`
- end: `0x180016a07`
- name: `GetFrontEndStateDescription`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000ba30`

## callees

- `0x180016980`

## string_xrefs

- `0x1800169b7`: `StateSpaeConfigChanged`

## pseudocode

```c
const wchar_t *__fastcall GetFrontEndStateDescription(int a1)
{
  const wchar_t *result; // rax

  if ( a1 == 7 )
    return L"StateSpaeAuthenticating";
  if ( a1 == 4 )
    return L"StateSpaeStartAuth";
  switch ( a1 )
  {
    case 1:
      result = L"StateSpaeAuthNotStarted";
      break;
    case 2:
      result = L"StateSpaeLogoff";
      break;
    case 3:
      result = L"StateSpaeConfigChanged";
      break;
    case 5:
      result = L"StateSpaeInitialize";
      break;
    case 6:
      result = L"StateSpaeConnecting";
      break;
    case 8:
      result = L"StateSpaeAuthenticated";
      break;
    case 9:
      result = L"StateSpaeHeld";
      break;
    case 10:
      result = L"StateSpaeUserUnavialable";
      break;
    case 11:
      result = L"StateSpaeFailure";
      break;
    default:
      result = L"Invalid state";
      break;
  }
  return result;
}

```

## disassembly

```asm
0x180016980  cmp     ecx, 7
0x180016983  jz      short loc_1800169FF
0x180016985  cmp     ecx, 4
0x180016988  jz      short loc_1800169F7
0x18001698a  dec     ecx; switch 11 cases
0x18001698c  cmp     ecx, 0Ah
0x18001698f  ja      short def_1800169A5; jumptable 00000001800169A5 default case, cases 4,7
0x180016991  movsxd  rax, ecx
0x180016994  lea     rdx, __ImageBase
0x18001699b  mov     ecx, ds:(jpt_1800169A5 - 180000000h)[rdx+rax*4]
0x1800169a2  add     rcx, rdx
0x1800169a5  jmp     rcx; switch jump
0x1800169a7  lea     rax, aStatespaeauthn; jumptable 00000001800169A5 case 1
0x1800169ae  retn
0x1800169af  lea     rax, aStatespaelogof; jumptable 00000001800169A5 case 2
0x1800169b6  retn
0x1800169b7  lea     rax, aStatespaeconfi; jumptable 00000001800169A5 case 3
0x1800169be  retn
0x1800169bf  lea     rax, aStatespaeiniti; jumptable 00000001800169A5 case 5
0x1800169c6  retn
0x1800169c7  lea     rax, aStatespaeconne; jumptable 00000001800169A5 case 6
0x1800169ce  retn
0x1800169cf  lea     rax, aStatespaeauthe; jumptable 00000001800169A5 case 8
0x1800169d6  retn
0x1800169d7  lea     rax, aStatespaeheld; jumptable 00000001800169A5 case 9
0x1800169de  retn
0x1800169df  lea     rax, aStatespaeuseru; jumptable 00000001800169A5 case 10
0x1800169e6  retn
0x1800169e7  lea     rax, aStatespaefailu; jumptable 00000001800169A5 case 11
0x1800169ee  retn
0x1800169ef  lea     rax, aInvalidState; jumptable 00000001800169A5 default case, cases 4,7
0x1800169f6  retn
0x1800169f7  lea     rax, aStatespaestart; "StateSpaeStartAuth"
0x1800169fe  retn
0x1800169ff  lea     rax, aStatespaeauthe_0; "StateSpaeAuthenticating"
0x180016a06  retn
```
