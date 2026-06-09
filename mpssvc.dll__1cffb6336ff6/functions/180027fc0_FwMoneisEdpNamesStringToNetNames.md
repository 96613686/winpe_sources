# FwMoneisEdpNamesStringToNetNames

- ea: `0x180027fc0`
- end: `0x1800281bf`
- name: `FwMoneisEdpNamesStringToNetNames`
- size: `511`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180027b90`
- `0x1800be78c`

## callees

- `0x18000af3c`
- `0x180027fc0`
- `0x1800670c0`
- `0x18006f520`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x180028067`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x1800280f1`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x180028067`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x1800280f1`
- `fwbase!FwHResultToWindowsError` at `0x180028013`
- `fwbase!FwHResultToWindowsError` at `0x180028077`
- `fwbase!FwHResultToWindowsError` at `0x180028194`
- `fwbase!FwHResultToWindowsError` at `0x180028013`
- `fwbase!FwHResultToWindowsError` at `0x180028077`
- `fwbase!FwHResultToWindowsError` at `0x180028194`
- `fwbase!FwArrayAppend` at `0x1800280db`
- `fwbase!FwArrayAppend` at `0x1800280db`
- `fwbase!FwStringCopy` at `0x180028009`
- `fwbase!FwStringCopy` at `0x1800280bb`
- `fwbase!FwStringCopy` at `0x180028009`
- `fwbase!FwStringCopy` at `0x1800280bb`
- `fwbase!FwFree` at `0x18002817d`
- `fwbase!FwFree` at `0x180028188`
- `fwbase!FwFree` at `0x18002817d`
- `fwbase!FwFree` at `0x180028188`

## string_xrefs

- `0x180028164`: `mpssvc.dll`

## pseudocode

```c
__int64 __fastcall FwMoneisEdpNamesStringToNetNames(_WORD *a1, const wchar_t *a2, _DWORD *a3)
{
  int v5; // ebx
  unsigned int v6; // eax
  unsigned int v7; // edi
  __int64 v8; // rcx
  __int64 v9; // rdx
  wchar_t *v10; // rax
  unsigned int v11; // ebp
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v17; // [rsp+20h] [rbp-48h] BYREF
  wchar_t *String; // [rsp+28h] [rbp-40h] BYREF

  String = 0;
  v17 = 0;
  if ( a1 && *a1 )
  {
    v5 = FwStringCopy(a1, &String);
    v6 = FwHResultToWindowsError((unsigned int)v5);
    v7 = v6;
    if ( v6 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v9 = 61;
LABEL_7:
        WPP_SF_d(*(_QWORD *)(v8 + 16), v9, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids, v6);
      }
    }
    else
    {
      v10 = wcstok(String, a2, 0);
      if ( v10 )
      {
        v11 = 0;
        while ( v10 )
        {
          v12 = FwStringCopy(v10, &v17);
          v5 = v12;
          if ( v12 < 0 )
          {
            v13 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              v14 = 63;
              goto LABEL_23;
            }
            goto LABEL_30;
          }
          v12 = FwArrayAppend(8, FwCopyIPv4Range, a3, &v17);
          v5 = v12;
          if ( v12 < 0 )
          {
            v13 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              v14 = 64;
LABEL_23:
              WPP_SF_d(*(_QWORD *)(v13 + 16), v14, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids, (unsigned int)v12);
              goto LABEL_30;
            }
            goto LABEL_30;
          }
          ++v11;
          v10 = wcstok(0, a2, 0);
          v17 = 0;
        }
        if ( a3 )
        {
          if ( *a3 == v11 )
            goto LABEL_30;
          v15 = (unsigned int)*a3;
        }
        else
        {
          v15 = 0;
        }
        MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v15, v11);
      }
      else
      {
        v6 = FwHResultToWindowsError(2147942487LL);
        v7 = v6;
        v8 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v9 = 62;
          goto LABEL_7;
        }
      }
    }
  }
  else
  {
    v7 = 0;
    v5 = 0;
  }
LABEL_30:
  FwFree(String);
  FwFree(v17);
  if ( v5 < 0 )
    return (unsigned int)FwHResultToWindowsError((unsigned int)v5);
  return v7;
}

```

## disassembly

```asm
0x180027fc0  mov     r11, rsp
0x180027fc3  mov     [r11+20h], rbx
0x180027fc7  push    rbp
0x180027fc8  push    rsi
0x180027fc9  push    rdi
0x180027fca  push    r14
0x180027fcc  push    r15
0x180027fce  sub     rsp, 40h
0x180027fd2  mov     rax, cs:__security_cookie
0x180027fd9  xor     rax, rsp
0x180027fdc  mov     [rsp+68h+var_38], rax
0x180027fe1  xor     r15d, r15d
0x180027fe4  mov     rsi, r8
0x180027fe7  mov     [r11-40h], r15
0x180027feb  mov     r14, rdx
0x180027fee  mov     [r11-48h], r15
0x180027ff2  test    rcx, rcx
0x180027ff5  jz      loc_180028172
0x180027ffb  cmp     [rcx], r15w
0x180027fff  jz      loc_180028172
0x180028005  lea     rdx, [r11-40h]
0x180028009  call    cs:__imp_FwStringCopy
0x18002800f  mov     ecx, eax
0x180028011  mov     ebx, eax
0x180028013  call    cs:__imp_FwHResultToWindowsError
0x180028019  mov     edi, eax
0x18002801b  test    eax, eax
0x18002801d  jz      short loc_18002805C
0x18002801f  mov     rcx, cs:WPP_GLOBAL_Control
0x180028026  lea     rdx, WPP_GLOBAL_Control
0x18002802d  cmp     rcx, rdx
0x180028030  jz      loc_180028178
0x180028036  test    byte ptr [rcx+1Ch], 1
0x18002803a  jz      loc_180028178
0x180028040  lea     edx, [r15+3Dh]
0x180028044  mov     rcx, [rcx+10h]
0x180028048  lea     r8, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids
0x18002804f  mov     r9d, eax
0x180028052  call    WPP_SF_d
0x180028057  jmp     loc_180028178
0x18002805c  mov     rcx, [rsp+68h+String]; String
0x180028061  xor     r8d, r8d; Context
0x180028064  mov     rdx, r14; Delimiter
0x180028067  call    cs:__imp_wcstok
0x18002806d  test    rax, rax
0x180028070  jnz     short loc_1800280A7
0x180028072  mov     ecx, 80070057h
0x180028077  call    cs:__imp_FwHResultToWindowsError
0x18002807d  mov     edi, eax
0x18002807f  mov     rcx, cs:WPP_GLOBAL_Control
0x180028086  lea     rdx, WPP_GLOBAL_Control
0x18002808d  cmp     rcx, rdx
0x180028090  jz      loc_180028178
0x180028096  test    byte ptr [rcx+1Ch], 1
0x18002809a  jz      loc_180028178
0x1800280a0  mov     edx, 3Eh ; '>'
0x1800280a5  jmp     short loc_180028044
0x1800280a7  mov     ebp, r15d
0x1800280aa  test    rax, rax
0x1800280ad  jz      loc_180028151
0x1800280b3  lea     rdx, [rsp+68h+var_48]
0x1800280b8  mov     rcx, rax
0x1800280bb  call    cs:__imp_FwStringCopy
0x1800280c1  mov     ebx, eax
0x1800280c3  test    eax, eax
0x1800280c5  js      short loc_18002811E
0x1800280c7  lea     r9, [rsp+68h+var_48]
0x1800280cc  mov     r8, rsi
0x1800280cf  lea     rdx, FwCopyIPv4Range
0x1800280d6  mov     ecx, 8
0x1800280db  call    cs:__imp_FwArrayAppend
0x1800280e1  mov     ebx, eax
0x1800280e3  test    eax, eax
0x1800280e5  js      short loc_1800280FE
0x1800280e7  inc     ebp
0x1800280e9  xor     r8d, r8d; Context
0x1800280ec  mov     rdx, r14; Delimiter
0x1800280ef  xor     ecx, ecx; String
0x1800280f1  call    cs:__imp_wcstok
0x1800280f7  mov     [rsp+68h+var_48], r15
0x1800280fc  jmp     short loc_1800280AA
0x1800280fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180028105  lea     rdx, WPP_GLOBAL_Control
0x18002810c  cmp     rcx, rdx
0x18002810f  jz      short loc_180028178
0x180028111  test    byte ptr [rcx+1Ch], 1
0x180028115  jz      short loc_180028178
0x180028117  mov     edx, 40h ; '@'
0x18002811c  jmp     short loc_18002813C
0x18002811e  mov     rcx, cs:WPP_GLOBAL_Control
0x180028125  lea     rdx, WPP_GLOBAL_Control
0x18002812c  cmp     rcx, rdx
0x18002812f  jz      short loc_180028178
0x180028131  test    byte ptr [rcx+1Ch], 1
0x180028135  jz      short loc_180028178
0x180028137  mov     edx, 3Fh ; '?'
0x18002813c  mov     rcx, [rcx+10h]
0x180028140  lea     r8, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids
0x180028147  mov     r9d, eax
0x18002814a  call    WPP_SF_d
0x18002814f  jmp     short loc_180028178
0x180028151  test    rsi, rsi
0x180028154  jz      short loc_18002815E
0x180028156  cmp     [rsi], ebp
0x180028158  jz      short loc_180028178
0x18002815a  mov     edx, [rsi]
0x18002815c  jmp     short loc_180028161
0x18002815e  mov     edx, r15d
0x180028161  mov     r8d, ebp
0x180028164  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x18002816b  call    MicrosoftTelemetryAssertTriggeredArgs
0x180028170  jmp     short loc_180028178
0x180028172  mov     edi, r15d
0x180028175  mov     ebx, r15d
0x180028178  mov     rcx, [rsp+68h+String]
0x18002817d  call    cs:__imp_FwFree
0x180028183  mov     rcx, [rsp+68h+var_48]
0x180028188  call    cs:__imp_FwFree
0x18002818e  test    ebx, ebx
0x180028190  jns     short loc_18002819C
0x180028192  mov     ecx, ebx
0x180028194  call    cs:__imp_FwHResultToWindowsError
0x18002819a  mov     edi, eax
0x18002819c  mov     eax, edi
0x18002819e  mov     rcx, [rsp+68h+var_38]
0x1800281a3  xor     rcx, rsp; StackCookie
0x1800281a6  call    __security_check_cookie
0x1800281ab  mov     rbx, [rsp+68h+arg_18]
0x1800281b3  add     rsp, 40h
0x1800281b7  pop     r15
0x1800281b9  pop     r14
0x1800281bb  pop     rdi
0x1800281bc  pop     rsi
0x1800281bd  pop     rbp
0x1800281be  retn
```
