# FwMoneisParseEdpCloudResourceStringToNetNames

- ea: `0x1800ba18c`
- end: `0x1800ba442`
- name: `FwMoneisParseEdpCloudResourceStringToNetNames`
- size: `694`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180066754`

## callees

- `0x18000af3c`
- `0x1800670c0`
- `0x18006f520`
- `0x1800ba18c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800ba247`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800ba28d`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800ba2a3`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800ba247`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800ba28d`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800ba2a3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800ba2bf`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800ba2bf`
- `fwbase!FwHResultToWindowsError` at `0x1800ba412`
- `fwbase!FwHResultToWindowsError` at `0x1800ba412`
- `fwbase!FwArrayAppend` at `0x1800ba305`
- `fwbase!FwArrayAppend` at `0x1800ba305`
- `fwbase!FwStringCopy` at `0x1800ba1eb`
- `fwbase!FwStringCopy` at `0x1800ba26e`
- `fwbase!FwStringCopy` at `0x1800ba2e7`
- `fwbase!FwStringCopy` at `0x1800ba1eb`
- `fwbase!FwStringCopy` at `0x1800ba26e`
- `fwbase!FwStringCopy` at `0x1800ba2e7`
- `fwbase!FwFree` at `0x1800ba25d`
- `fwbase!FwFree` at `0x1800ba3f2`
- `fwbase!FwFree` at `0x1800ba3fc`
- `fwbase!FwFree` at `0x1800ba406`
- `fwbase!FwFree` at `0x1800ba25d`
- `fwbase!FwFree` at `0x1800ba3f2`
- `fwbase!FwFree` at `0x1800ba3fc`
- `fwbase!FwFree` at `0x1800ba406`

## string_xrefs

- `0x1800ba3dd`: `mpssvc.dll`
- `0x1800ba2b5`: `/*AppCompat*/`

## pseudocode

```c
__int64 __fastcall FwMoneisParseEdpCloudResourceStringToNetNames(_WORD *a1, _DWORD *a2, _DWORD *a3)
{
  unsigned int v5; // r14d
  int v6; // ebx
  __int64 v7; // rcx
  __int64 v8; // rdx
  wchar_t *v9; // rcx
  unsigned int v10; // esi
  wchar_t *v11; // r15
  wchar_t *v12; // r15
  wchar_t *v13; // r13
  __int64 v14; // rdx
  wchar_t *v16; // [rsp+20h] [rbp-30h] BYREF
  __int64 v17; // [rsp+28h] [rbp-28h] BYREF
  wchar_t *String; // [rsp+30h] [rbp-20h] BYREF
  wchar_t *v19; // [rsp+38h] [rbp-18h] BYREF
  wchar_t *Context; // [rsp+40h] [rbp-10h] BYREF

  v16 = 0;
  Context = 0;
  v5 = 0;
  String = 0;
  v17 = 0;
  v19 = 0;
  *a3 = 0;
  if ( a1 && *a1 )
  {
    v6 = FwStringCopy(a1, &String);
    if ( v6 >= 0 )
    {
      v9 = String;
      v10 = 0;
      while ( 1 )
      {
        v11 = wcstok_s(v9, Delimiter, &Context);
        if ( !v11 )
          break;
        FwFree(v16);
        v16 = 0;
        v6 = FwStringCopy(v11, &v16);
        if ( v6 < 0 )
        {
          v7 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v8 = 141;
            goto LABEL_7;
          }
          goto LABEL_37;
        }
        v12 = wcstok_s(v16, asc_180102CE8, &v19);
        v13 = wcstok_s(0, asc_180102CE8, &v19);
        if ( !v12 )
        {
          v5 = 87;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 142, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids, 87);
          goto LABEL_37;
        }
        if ( lstrcmpiW(v12, L"/*AppCompat*/") )
        {
          if ( !v13 )
          {
            v6 = FwStringCopy(v12, &v17);
            if ( v6 < 0 )
            {
              v7 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
              {
                v8 = 143;
                goto LABEL_7;
              }
              goto LABEL_37;
            }
            v6 = FwArrayAppend(8, FwCopyIPv4Range, a2, &v17);
            if ( v6 < 0 )
            {
              v7 = WPP_GLOBAL_Control;
              if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
              {
                v8 = 144;
                goto LABEL_7;
              }
              goto LABEL_37;
            }
            v17 = 0;
            ++v10;
          }
        }
        else
        {
          *a3 = 1;
        }
        v9 = 0;
      }
      if ( a2 )
      {
        if ( *a2 == v10 )
          goto LABEL_37;
        v14 = (unsigned int)*a2;
      }
      else
      {
        v14 = 0;
      }
      MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v14, v10);
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v8 = 140;
LABEL_7:
        WPP_SF_d(*(_QWORD *)(v7 + 16), v8, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids, (unsigned int)v6);
      }
    }
  }
  else
  {
    v6 = 0;
  }
LABEL_37:
  FwFree(String);
  FwFree(v17);
  FwFree(v16);
  if ( v6 < 0 )
    return (unsigned int)FwHResultToWindowsError((unsigned int)v6);
  return v5;
}

```

## disassembly

```asm
0x1800ba18c  mov     [rsp-38h+arg_18], rbx
0x1800ba191  push    rbp
0x1800ba192  push    rsi
0x1800ba193  push    rdi
0x1800ba194  push    r12
0x1800ba196  push    r13
0x1800ba198  push    r14
0x1800ba19a  push    r15
0x1800ba19c  mov     rbp, rsp
0x1800ba19f  sub     rsp, 50h
0x1800ba1a3  mov     rax, cs:__security_cookie
0x1800ba1aa  xor     rax, rsp
0x1800ba1ad  mov     [rbp+var_8], rax
0x1800ba1b1  xor     r13d, r13d
0x1800ba1b4  mov     r12, r8
0x1800ba1b7  mov     [rbp+var_30], r13
0x1800ba1bb  mov     rdi, rdx
0x1800ba1be  mov     [rbp+Context], r13
0x1800ba1c2  mov     r14d, r13d
0x1800ba1c5  mov     [rbp+String], r13
0x1800ba1c9  mov     [rbp+var_28], r13
0x1800ba1cd  mov     [rbp+var_18], r13
0x1800ba1d1  mov     [r8], r13d
0x1800ba1d4  test    rcx, rcx
0x1800ba1d7  jz      loc_1800BA3EB
0x1800ba1dd  cmp     [rcx], r13w
0x1800ba1e1  jz      loc_1800BA3EB
0x1800ba1e7  lea     rdx, [rbp+String]
0x1800ba1eb  call    cs:__imp_FwStringCopy
0x1800ba1f1  mov     ebx, eax
0x1800ba1f3  test    eax, eax
0x1800ba1f5  jns     short loc_1800BA235
0x1800ba1f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ba1fe  lea     rax, WPP_GLOBAL_Control
0x1800ba205  cmp     rcx, rax
0x1800ba208  jz      loc_1800BA3EE
0x1800ba20e  test    byte ptr [rcx+1Ch], 1
0x1800ba212  jz      loc_1800BA3EE
0x1800ba218  mov     edx, 8Ch
0x1800ba21d  mov     rcx, [rcx+10h]
0x1800ba221  lea     r8, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids
0x1800ba228  mov     r9d, ebx
0x1800ba22b  call    WPP_SF_d
0x1800ba230  jmp     loc_1800BA3EE
0x1800ba235  mov     rcx, [rbp+String]; String
0x1800ba239  mov     esi, r13d
0x1800ba23c  lea     r8, [rbp+Context]; Context
0x1800ba240  lea     rdx, Delimiter; Delimiter
0x1800ba247  call    cs:__imp_wcstok_s
0x1800ba24d  mov     r15, rax
0x1800ba250  test    rax, rax
0x1800ba253  jz      loc_1800BA3CA
0x1800ba259  mov     rcx, [rbp+var_30]
0x1800ba25d  call    cs:__imp_FwFree
0x1800ba263  lea     rdx, [rbp+var_30]
0x1800ba267  mov     [rbp+var_30], r13
0x1800ba26b  mov     rcx, r15
0x1800ba26e  call    cs:__imp_FwStringCopy
0x1800ba274  mov     ebx, eax
0x1800ba276  test    eax, eax
0x1800ba278  js      loc_1800BA3A7
0x1800ba27e  mov     rcx, [rbp+var_30]; String
0x1800ba282  lea     r8, [rbp+var_18]; Context
0x1800ba286  lea     rdx, asc_180102CE8; Delimiter
0x1800ba28d  call    cs:__imp_wcstok_s
0x1800ba293  lea     r8, [rbp+var_18]; Context
0x1800ba297  xor     ecx, ecx; String
0x1800ba299  lea     rdx, asc_180102CE8; Delimiter
0x1800ba2a0  mov     r15, rax
0x1800ba2a3  call    cs:__imp_wcstok_s
0x1800ba2a9  mov     r13, rax
0x1800ba2ac  test    r15, r15
0x1800ba2af  jz      loc_1800BA36F
0x1800ba2b5  lea     rdx, aAppcompat; "/*AppCompat*/"
0x1800ba2bc  mov     rcx, r15; lpString1
0x1800ba2bf  call    cs:__imp_lstrcmpiW
0x1800ba2c5  test    eax, eax
0x1800ba2c7  jnz     short loc_1800BA2DB
0x1800ba2c9  mov     dword ptr [r12], 1
0x1800ba2d1  xor     r13d, r13d
0x1800ba2d4  xor     ecx, ecx
0x1800ba2d6  jmp     loc_1800BA23C
0x1800ba2db  test    r13, r13
0x1800ba2de  jnz     short loc_1800BA2D1
0x1800ba2e0  lea     rdx, [rbp+var_28]
0x1800ba2e4  mov     rcx, r15
0x1800ba2e7  call    cs:__imp_FwStringCopy
0x1800ba2ed  mov     ebx, eax
0x1800ba2ef  test    eax, eax
0x1800ba2f1  js      short loc_1800BA344
0x1800ba2f3  lea     r9, [rbp+var_28]
0x1800ba2f7  mov     r8, rdi
0x1800ba2fa  lea     rdx, FwCopyIPv4Range
0x1800ba301  lea     ecx, [r13+8]
0x1800ba305  call    cs:__imp_FwArrayAppend
0x1800ba30b  mov     ebx, eax
0x1800ba30d  test    eax, eax
0x1800ba30f  js      short loc_1800BA319
0x1800ba311  mov     [rbp+var_28], r13
0x1800ba315  inc     esi
0x1800ba317  jmp     short loc_1800BA2D4
0x1800ba319  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ba320  lea     rax, WPP_GLOBAL_Control
0x1800ba327  cmp     rcx, rax
0x1800ba32a  jz      loc_1800BA3EE
0x1800ba330  test    byte ptr [rcx+1Ch], 1
0x1800ba334  jz      loc_1800BA3EE
0x1800ba33a  mov     edx, 90h
0x1800ba33f  jmp     loc_1800BA21D
0x1800ba344  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ba34b  lea     rax, WPP_GLOBAL_Control
0x1800ba352  cmp     rcx, rax
0x1800ba355  jz      loc_1800BA3EE
0x1800ba35b  test    byte ptr [rcx+1Ch], 1
0x1800ba35f  jz      loc_1800BA3EE
0x1800ba365  mov     edx, 8Fh
0x1800ba36a  jmp     loc_1800BA21D
0x1800ba36f  mov     r14d, 57h ; 'W'
0x1800ba375  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ba37c  lea     rax, WPP_GLOBAL_Control
0x1800ba383  cmp     rcx, rax
0x1800ba386  jz      short loc_1800BA3EE
0x1800ba388  test    byte ptr [rcx+1Ch], 1
0x1800ba38c  jz      short loc_1800BA3EE
0x1800ba38e  mov     rcx, [rcx+10h]
0x1800ba392  lea     edx, [r14+37h]
0x1800ba396  mov     r9d, r14d
0x1800ba399  lea     r8, WPP_0da5eba620563d62cce5b7087a7b5f88_Traceguids
0x1800ba3a0  call    WPP_SF_d
0x1800ba3a5  jmp     short loc_1800BA3EE
0x1800ba3a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ba3ae  lea     rax, WPP_GLOBAL_Control
0x1800ba3b5  cmp     rcx, rax
0x1800ba3b8  jz      short loc_1800BA3EE
0x1800ba3ba  test    byte ptr [rcx+1Ch], 1
0x1800ba3be  jz      short loc_1800BA3EE
0x1800ba3c0  mov     edx, 8Dh
0x1800ba3c5  jmp     loc_1800BA21D
0x1800ba3ca  test    rdi, rdi
0x1800ba3cd  jz      short loc_1800BA3D7
0x1800ba3cf  cmp     [rdi], esi
0x1800ba3d1  jz      short loc_1800BA3EE
0x1800ba3d3  mov     edx, [rdi]
0x1800ba3d5  jmp     short loc_1800BA3DA
0x1800ba3d7  mov     edx, r13d
0x1800ba3da  mov     r8d, esi
0x1800ba3dd  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x1800ba3e4  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800ba3e9  jmp     short loc_1800BA3EE
0x1800ba3eb  mov     ebx, r13d
0x1800ba3ee  mov     rcx, [rbp+String]
0x1800ba3f2  call    cs:__imp_FwFree
0x1800ba3f8  mov     rcx, [rbp+var_28]
0x1800ba3fc  call    cs:__imp_FwFree
0x1800ba402  mov     rcx, [rbp+var_30]
0x1800ba406  call    cs:__imp_FwFree
0x1800ba40c  test    ebx, ebx
0x1800ba40e  jns     short loc_1800BA41B
0x1800ba410  mov     ecx, ebx
0x1800ba412  call    cs:__imp_FwHResultToWindowsError
0x1800ba418  mov     r14d, eax
0x1800ba41b  mov     eax, r14d
0x1800ba41e  mov     rcx, [rbp+var_8]
0x1800ba422  xor     rcx, rsp; StackCookie
0x1800ba425  call    __security_check_cookie
0x1800ba42a  mov     rbx, [rsp+50h+arg_18]
0x1800ba432  add     rsp, 50h
0x1800ba436  pop     r15
0x1800ba438  pop     r14
0x1800ba43a  pop     r13
0x1800ba43c  pop     r12
0x1800ba43e  pop     rdi
0x1800ba43f  pop     rsi
0x1800ba440  pop     rbp
0x1800ba441  retn
```
