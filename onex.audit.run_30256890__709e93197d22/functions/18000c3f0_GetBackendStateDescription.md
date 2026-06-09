# GetBackendStateDescription

- ea: `0x18000c3f0`
- end: `0x18000c47a`
- name: `GetBackendStateDescription`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000ba30`

## callees

- `0x18000c3f0`

## string_xrefs

- `0x18000c422`: `StateSBackendEapConfigChanged`

## pseudocode

```c
const wchar_t *__fastcall GetBackendStateDescription(int a1)
{
  const wchar_t *result; // rax

  if ( a1 == 8 )
    return L"StateSBackendRequest";
  switch ( a1 )
  {
    case 1:
      result = L"StateSBackendNotStarted";
      break;
    case 2:
      result = L"StateSBackendUserChanged";
      break;
    case 3:
      result = L"StateSBackendEapConfigChanged";
      break;
    case 4:
      result = L"StateSBackendDeactivated";
      break;
    case 5:
      result = L"StateSBackendIdle";
      break;
    case 6:
      result = L"StateSBackendUIFailure";
      break;
    case 7:
      result = L"StateSBackendReceive";
      break;
    case 9:
      result = L"StateSBackendRequestUI";
      break;
    case 10:
      result = L"StateSBackendSuccess";
      break;
    case 11:
      result = L"StateSBackendTimeout";
      break;
    case 12:
      result = L"StateSBackendFail";
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
0x18000c3f0  cmp     ecx, 8
0x18000c3f3  jz      short loc_18000C472
0x18000c3f5  dec     ecx; switch 12 cases
0x18000c3f7  cmp     ecx, 0Bh
0x18000c3fa  ja      short def_18000C410; jumptable 000000018000C410 default case, case 8
0x18000c3fc  movsxd  rax, ecx
0x18000c3ff  lea     rdx, __ImageBase
0x18000c406  mov     ecx, ds:(jpt_18000C410 - 180000000h)[rdx+rax*4]
0x18000c40d  add     rcx, rdx
0x18000c410  jmp     rcx; switch jump
0x18000c412  lea     rax, aStatesbackendn; jumptable 000000018000C410 case 1
0x18000c419  retn
0x18000c41a  lea     rax, aStatesbackendu; jumptable 000000018000C410 case 2
0x18000c421  retn
0x18000c422  lea     rax, aStatesbackende; jumptable 000000018000C410 case 3
0x18000c429  retn
0x18000c42a  lea     rax, aStatesbackendd; jumptable 000000018000C410 case 4
0x18000c431  retn
0x18000c432  lea     rax, aStatesbackendi; jumptable 000000018000C410 case 5
0x18000c439  retn
0x18000c43a  lea     rax, aStatesbackendu_0; jumptable 000000018000C410 case 6
0x18000c441  retn
0x18000c442  lea     rax, aStatesbackendr_0; jumptable 000000018000C410 case 7
0x18000c449  retn
0x18000c44a  lea     rax, aStatesbackendr_1; jumptable 000000018000C410 case 9
0x18000c451  retn
0x18000c452  lea     rax, aStatesbackends; jumptable 000000018000C410 case 10
0x18000c459  retn
0x18000c45a  lea     rax, aStatesbackendt; jumptable 000000018000C410 case 11
0x18000c461  retn
0x18000c462  lea     rax, aStatesbackendf; jumptable 000000018000C410 case 12
0x18000c469  retn
0x18000c46a  lea     rax, aInvalidState; jumptable 000000018000C410 default case, case 8
0x18000c471  retn
0x18000c472  lea     rax, aStatesbackendr; "StateSBackendRequest"
0x18000c479  retn
```
