# FwMoneisEdpNamesStringToNetNames

- ea: `0x18002b660`
- end: `0x18002b89c`
- name: `FwMoneisEdpNamesStringToNetNames`
- size: `572`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002b18c`
- `0x1800c53e4`

## callees

- `0x18000a710`
- `0x18002b660`
- `0x18006a710`
- `0x1800729c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x18002b713`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x18002b7b5`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x18002b713`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok` at `0x18002b7b5`
- `fwbase!FwHResultToWindowsError` at `0x18002b6b9`
- `fwbase!FwHResultToWindowsError` at `0x18002b729`
- `fwbase!FwHResultToWindowsError` at `0x18002b86a`
- `fwbase!FwHResultToWindowsError` at `0x18002b6b9`
- `fwbase!FwHResultToWindowsError` at `0x18002b729`
- `fwbase!FwHResultToWindowsError` at `0x18002b86a`
- `fwbase!FwStringCopy` at `0x18002b6a9`
- `fwbase!FwStringCopy` at `0x18002b773`
- `fwbase!FwStringCopy` at `0x18002b6a9`
- `fwbase!FwStringCopy` at `0x18002b773`
- `fwbase!FwFree` at `0x18002b847`
- `fwbase!FwFree` at `0x18002b858`
- `fwbase!FwFree` at `0x18002b847`
- `fwbase!FwFree` at `0x18002b858`
- `fwbase!FwArrayAppend` at `0x18002b799`
- `fwbase!FwArrayAppend` at `0x18002b799`

## string_xrefs

- `0x18002b82e`: `mpssvc.dll`

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
        WPP_SF_d(*(_QWORD *)(v8 + 16), v9, WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids, v6);
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
              WPP_SF_d(*(_QWORD *)(v13 + 16), v14, WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids, (unsigned int)v12);
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
0x18002b660  mov     r11, rsp
0x18002b663  mov     [r11+20h], rbx
0x18002b667  push    rbp
0x18002b668  push    rsi
0x18002b669  push    rdi
0x18002b66a  push    r14
0x18002b66c  push    r15
0x18002b66e  sub     rsp, 40h
0x18002b672  mov     rax, cs:__security_cookie
0x18002b679  xor     rax, rsp
0x18002b67c  mov     [rsp+68h+var_38], rax
0x18002b681  xor     r15d, r15d
0x18002b684  mov     rsi, r8
0x18002b687  mov     [r11-40h], r15
0x18002b68b  mov     r14, rdx
0x18002b68e  mov     [r11-48h], r15
0x18002b692  test    rcx, rcx
0x18002b695  jz      loc_18002B83C
0x18002b69b  cmp     [rcx], r15w
0x18002b69f  jz      loc_18002B83C
0x18002b6a5  lea     rdx, [r11-40h]
0x18002b6a9  call    cs:__imp_FwStringCopy
0x18002b6b0  nop     dword ptr [rax+rax+00h]
0x18002b6b5  mov     ecx, eax
0x18002b6b7  mov     ebx, eax
0x18002b6b9  call    cs:__imp_FwHResultToWindowsError
0x18002b6c0  nop     dword ptr [rax+rax+00h]
0x18002b6c5  mov     edi, eax
0x18002b6c7  test    eax, eax
0x18002b6c9  jz      short loc_18002B708
0x18002b6cb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b6d2  lea     rdx, WPP_GLOBAL_Control
0x18002b6d9  cmp     rcx, rdx
0x18002b6dc  jz      loc_18002B842
0x18002b6e2  test    byte ptr [rcx+1Ch], 1
0x18002b6e6  jz      loc_18002B842
0x18002b6ec  lea     edx, [r15+3Dh]
0x18002b6f0  mov     rcx, [rcx+10h]
0x18002b6f4  lea     r8, WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids
0x18002b6fb  mov     r9d, eax
0x18002b6fe  call    WPP_SF_d
0x18002b703  jmp     loc_18002B842
0x18002b708  mov     rcx, [rsp+68h+String]; String
0x18002b70d  xor     r8d, r8d; Context
0x18002b710  mov     rdx, r14; Delimiter
0x18002b713  call    cs:__imp_wcstok
0x18002b71a  nop     dword ptr [rax+rax+00h]
0x18002b71f  test    rax, rax
0x18002b722  jnz     short loc_18002B75F
0x18002b724  mov     ecx, 80070057h
0x18002b729  call    cs:__imp_FwHResultToWindowsError
0x18002b730  nop     dword ptr [rax+rax+00h]
0x18002b735  mov     edi, eax
0x18002b737  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b73e  lea     rdx, WPP_GLOBAL_Control
0x18002b745  cmp     rcx, rdx
0x18002b748  jz      loc_18002B842
0x18002b74e  test    byte ptr [rcx+1Ch], 1
0x18002b752  jz      loc_18002B842
0x18002b758  mov     edx, 3Eh ; '>'
0x18002b75d  jmp     short loc_18002B6F0
0x18002b75f  mov     ebp, r15d
0x18002b762  test    rax, rax
0x18002b765  jz      loc_18002B81B
0x18002b76b  lea     rdx, [rsp+68h+var_48]
0x18002b770  mov     rcx, rax
0x18002b773  call    cs:__imp_FwStringCopy
0x18002b77a  nop     dword ptr [rax+rax+00h]
0x18002b77f  mov     ebx, eax
0x18002b781  test    eax, eax
0x18002b783  js      short loc_18002B7E8
0x18002b785  lea     r9, [rsp+68h+var_48]
0x18002b78a  mov     r8, rsi
0x18002b78d  lea     rdx, FwCopyIPv4Range
0x18002b794  mov     ecx, 8
0x18002b799  call    cs:__imp_FwArrayAppend
0x18002b7a0  nop     dword ptr [rax+rax+00h]
0x18002b7a5  mov     ebx, eax
0x18002b7a7  test    eax, eax
0x18002b7a9  js      short loc_18002B7C8
0x18002b7ab  inc     ebp
0x18002b7ad  xor     r8d, r8d; Context
0x18002b7b0  mov     rdx, r14; Delimiter
0x18002b7b3  xor     ecx, ecx; String
0x18002b7b5  call    cs:__imp_wcstok
0x18002b7bc  nop     dword ptr [rax+rax+00h]
0x18002b7c1  mov     [rsp+68h+var_48], r15
0x18002b7c6  jmp     short loc_18002B762
0x18002b7c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b7cf  lea     rdx, WPP_GLOBAL_Control
0x18002b7d6  cmp     rcx, rdx
0x18002b7d9  jz      short loc_18002B842
0x18002b7db  test    byte ptr [rcx+1Ch], 1
0x18002b7df  jz      short loc_18002B842
0x18002b7e1  mov     edx, 40h ; '@'
0x18002b7e6  jmp     short loc_18002B806
0x18002b7e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b7ef  lea     rdx, WPP_GLOBAL_Control
0x18002b7f6  cmp     rcx, rdx
0x18002b7f9  jz      short loc_18002B842
0x18002b7fb  test    byte ptr [rcx+1Ch], 1
0x18002b7ff  jz      short loc_18002B842
0x18002b801  mov     edx, 3Fh ; '?'
0x18002b806  mov     rcx, [rcx+10h]
0x18002b80a  lea     r8, WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids
0x18002b811  mov     r9d, eax
0x18002b814  call    WPP_SF_d
0x18002b819  jmp     short loc_18002B842
0x18002b81b  test    rsi, rsi
0x18002b81e  jz      short loc_18002B828
0x18002b820  cmp     [rsi], ebp
0x18002b822  jz      short loc_18002B842
0x18002b824  mov     edx, [rsi]
0x18002b826  jmp     short loc_18002B82B
0x18002b828  mov     edx, r15d
0x18002b82b  mov     r8d, ebp
0x18002b82e  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x18002b835  call    MicrosoftTelemetryAssertTriggeredArgs
0x18002b83a  jmp     short loc_18002B842
0x18002b83c  mov     edi, r15d
0x18002b83f  mov     ebx, r15d
0x18002b842  mov     rcx, [rsp+68h+String]
0x18002b847  call    cs:__imp_FwFree
0x18002b84e  nop     dword ptr [rax+rax+00h]
0x18002b853  mov     rcx, [rsp+68h+var_48]
0x18002b858  call    cs:__imp_FwFree
0x18002b85f  nop     dword ptr [rax+rax+00h]
0x18002b864  test    ebx, ebx
0x18002b866  jns     short loc_18002B878
0x18002b868  mov     ecx, ebx
0x18002b86a  call    cs:__imp_FwHResultToWindowsError
0x18002b871  nop     dword ptr [rax+rax+00h]
0x18002b876  mov     edi, eax
0x18002b878  mov     eax, edi
0x18002b87a  mov     rcx, [rsp+68h+var_38]
0x18002b87f  xor     rcx, rsp; StackCookie
0x18002b882  call    __security_check_cookie
0x18002b887  mov     rbx, [rsp+68h+arg_18]
0x18002b88f  add     rsp, 40h
0x18002b893  pop     r15
0x18002b895  pop     r14
0x18002b897  pop     rdi
0x18002b898  pop     rsi
0x18002b899  pop     rbp
0x18002b89a  retn
```
