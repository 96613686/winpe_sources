# FwMoneisParseEdpCloudResourceStringToNetNames

- ea: `0x1800c10c4`
- end: `0x1800c13c9`
- name: `FwMoneisParseEdpCloudResourceStringToNetNames`
- size: `773`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180069e24`

## callees

- `0x18000a710`
- `0x18006a710`
- `0x1800729c0`
- `0x1800c10c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800c1185`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800c11dd`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800c11f9`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800c1185`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800c11dd`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800c11f9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800c121b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800c121b`
- `fwbase!FwHResultToWindowsError` at `0x1800c1392`
- `fwbase!FwHResultToWindowsError` at `0x1800c1392`
- `fwbase!FwStringCopy` at `0x1800c1123`
- `fwbase!FwStringCopy` at `0x1800c11b8`
- `fwbase!FwStringCopy` at `0x1800c1249`
- `fwbase!FwStringCopy` at `0x1800c1123`
- `fwbase!FwStringCopy` at `0x1800c11b8`
- `fwbase!FwStringCopy` at `0x1800c1249`
- `fwbase!FwFree` at `0x1800c11a1`
- `fwbase!FwFree` at `0x1800c1360`
- `fwbase!FwFree` at `0x1800c1370`
- `fwbase!FwFree` at `0x1800c1380`
- `fwbase!FwFree` at `0x1800c11a1`
- `fwbase!FwFree` at `0x1800c1360`
- `fwbase!FwFree` at `0x1800c1370`
- `fwbase!FwFree` at `0x1800c1380`
- `fwbase!FwArrayAppend` at `0x1800c126d`
- `fwbase!FwArrayAppend` at `0x1800c126d`

## string_xrefs

- `0x1800c134b`: `mpssvc.dll`
- `0x1800c1211`: `/*AppCompat*/`

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
  if ( a1 && *a1 )
  {
    *a3 = 0;
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
        v12 = wcstok_s(v16, asc_1801087A0, &v19);
        v13 = wcstok_s(0, asc_1801087A0, &v19);
        if ( !v12 )
        {
          v5 = 87;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 142, WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids, 87);
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
        WPP_SF_d(*(_QWORD *)(v7 + 16), v8, WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids, (unsigned int)v6);
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
0x1800c10c4  mov     [rsp-38h+arg_18], rbx
0x1800c10c9  push    rbp
0x1800c10ca  push    rsi
0x1800c10cb  push    rdi
0x1800c10cc  push    r12
0x1800c10ce  push    r13
0x1800c10d0  push    r14
0x1800c10d2  push    r15
0x1800c10d4  mov     rbp, rsp
0x1800c10d7  sub     rsp, 50h
0x1800c10db  mov     rax, cs:__security_cookie
0x1800c10e2  xor     rax, rsp
0x1800c10e5  mov     [rbp+var_8], rax
0x1800c10e9  xor     r13d, r13d
0x1800c10ec  mov     r12, r8
0x1800c10ef  mov     [rbp+var_30], r13
0x1800c10f3  mov     rdi, rdx
0x1800c10f6  mov     [rbp+Context], r13
0x1800c10fa  mov     r14d, r13d
0x1800c10fd  mov     [rbp+String], r13
0x1800c1101  mov     [rbp+var_28], r13
0x1800c1105  mov     [rbp+var_18], r13
0x1800c1109  test    rcx, rcx
0x1800c110c  jz      loc_1800C1359
0x1800c1112  cmp     [rcx], r13w
0x1800c1116  jz      loc_1800C1359
0x1800c111c  lea     rdx, [rbp+String]
0x1800c1120  mov     [r8], r13d
0x1800c1123  call    cs:__imp_FwStringCopy
0x1800c112a  nop     dword ptr [rax+rax+00h]
0x1800c112f  mov     ebx, eax
0x1800c1131  test    eax, eax
0x1800c1133  jns     short loc_1800C1173
0x1800c1135  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c113c  lea     rax, WPP_GLOBAL_Control
0x1800c1143  cmp     rcx, rax
0x1800c1146  jz      loc_1800C135C
0x1800c114c  test    byte ptr [rcx+1Ch], 1
0x1800c1150  jz      loc_1800C135C
0x1800c1156  mov     edx, 8Ch
0x1800c115b  mov     rcx, [rcx+10h]
0x1800c115f  lea     r8, WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids
0x1800c1166  mov     r9d, ebx
0x1800c1169  call    WPP_SF_d
0x1800c116e  jmp     loc_1800C135C
0x1800c1173  mov     rcx, [rbp+String]; String
0x1800c1177  mov     esi, r13d
0x1800c117a  lea     r8, [rbp+Context]; Context
0x1800c117e  lea     rdx, Delimiter; Delimiter
0x1800c1185  call    cs:__imp_wcstok_s
0x1800c118c  nop     dword ptr [rax+rax+00h]
0x1800c1191  mov     r15, rax
0x1800c1194  test    rax, rax
0x1800c1197  jz      loc_1800C1338
0x1800c119d  mov     rcx, [rbp+var_30]
0x1800c11a1  call    cs:__imp_FwFree
0x1800c11a8  nop     dword ptr [rax+rax+00h]
0x1800c11ad  lea     rdx, [rbp+var_30]
0x1800c11b1  mov     [rbp+var_30], r13
0x1800c11b5  mov     rcx, r15
0x1800c11b8  call    cs:__imp_FwStringCopy
0x1800c11bf  nop     dword ptr [rax+rax+00h]
0x1800c11c4  mov     ebx, eax
0x1800c11c6  test    eax, eax
0x1800c11c8  js      loc_1800C1315
0x1800c11ce  mov     rcx, [rbp+var_30]; String
0x1800c11d2  lea     r8, [rbp+var_18]; Context
0x1800c11d6  lea     rdx, asc_1801087A0; Delimiter
0x1800c11dd  call    cs:__imp_wcstok_s
0x1800c11e4  nop     dword ptr [rax+rax+00h]
0x1800c11e9  lea     r8, [rbp+var_18]; Context
0x1800c11ed  xor     ecx, ecx; String
0x1800c11ef  lea     rdx, asc_1801087A0; Delimiter
0x1800c11f6  mov     r15, rax
0x1800c11f9  call    cs:__imp_wcstok_s
0x1800c1200  nop     dword ptr [rax+rax+00h]
0x1800c1205  mov     r13, rax
0x1800c1208  test    r15, r15
0x1800c120b  jz      loc_1800C12DD
0x1800c1211  lea     rdx, aAppcompat; "/*AppCompat*/"
0x1800c1218  mov     rcx, r15; lpString1
0x1800c121b  call    cs:__imp_lstrcmpiW
0x1800c1222  nop     dword ptr [rax+rax+00h]
0x1800c1227  test    eax, eax
0x1800c1229  jnz     short loc_1800C123D
0x1800c122b  mov     dword ptr [r12], 1
0x1800c1233  xor     r13d, r13d
0x1800c1236  xor     ecx, ecx
0x1800c1238  jmp     loc_1800C117A
0x1800c123d  test    r13, r13
0x1800c1240  jnz     short loc_1800C1233
0x1800c1242  lea     rdx, [rbp+var_28]
0x1800c1246  mov     rcx, r15
0x1800c1249  call    cs:__imp_FwStringCopy
0x1800c1250  nop     dword ptr [rax+rax+00h]
0x1800c1255  mov     ebx, eax
0x1800c1257  test    eax, eax
0x1800c1259  js      short loc_1800C12B2
0x1800c125b  lea     r9, [rbp+var_28]
0x1800c125f  mov     r8, rdi
0x1800c1262  lea     rdx, FwCopyIPv4Range
0x1800c1269  lea     ecx, [r13+8]
0x1800c126d  call    cs:__imp_FwArrayAppend
0x1800c1274  nop     dword ptr [rax+rax+00h]
0x1800c1279  mov     ebx, eax
0x1800c127b  test    eax, eax
0x1800c127d  js      short loc_1800C1287
0x1800c127f  mov     [rbp+var_28], r13
0x1800c1283  inc     esi
0x1800c1285  jmp     short loc_1800C1236
0x1800c1287  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c128e  lea     rax, WPP_GLOBAL_Control
0x1800c1295  cmp     rcx, rax
0x1800c1298  jz      loc_1800C135C
0x1800c129e  test    byte ptr [rcx+1Ch], 1
0x1800c12a2  jz      loc_1800C135C
0x1800c12a8  mov     edx, 90h
0x1800c12ad  jmp     loc_1800C115B
0x1800c12b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c12b9  lea     rax, WPP_GLOBAL_Control
0x1800c12c0  cmp     rcx, rax
0x1800c12c3  jz      loc_1800C135C
0x1800c12c9  test    byte ptr [rcx+1Ch], 1
0x1800c12cd  jz      loc_1800C135C
0x1800c12d3  mov     edx, 8Fh
0x1800c12d8  jmp     loc_1800C115B
0x1800c12dd  mov     r14d, 57h ; 'W'
0x1800c12e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c12ea  lea     rax, WPP_GLOBAL_Control
0x1800c12f1  cmp     rcx, rax
0x1800c12f4  jz      short loc_1800C135C
0x1800c12f6  test    byte ptr [rcx+1Ch], 1
0x1800c12fa  jz      short loc_1800C135C
0x1800c12fc  mov     rcx, [rcx+10h]
0x1800c1300  lea     edx, [r14+37h]
0x1800c1304  mov     r9d, r14d
0x1800c1307  lea     r8, WPP_c82a0d1b11b03f6aea8fb1592911dce6_Traceguids
0x1800c130e  call    WPP_SF_d
0x1800c1313  jmp     short loc_1800C135C
0x1800c1315  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c131c  lea     rax, WPP_GLOBAL_Control
0x1800c1323  cmp     rcx, rax
0x1800c1326  jz      short loc_1800C135C
0x1800c1328  test    byte ptr [rcx+1Ch], 1
0x1800c132c  jz      short loc_1800C135C
0x1800c132e  mov     edx, 8Dh
0x1800c1333  jmp     loc_1800C115B
0x1800c1338  test    rdi, rdi
0x1800c133b  jz      short loc_1800C1345
0x1800c133d  cmp     [rdi], esi
0x1800c133f  jz      short loc_1800C135C
0x1800c1341  mov     edx, [rdi]
0x1800c1343  jmp     short loc_1800C1348
0x1800c1345  mov     edx, r13d
0x1800c1348  mov     r8d, esi
0x1800c134b  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x1800c1352  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800c1357  jmp     short loc_1800C135C
0x1800c1359  mov     ebx, r13d
0x1800c135c  mov     rcx, [rbp+String]
0x1800c1360  call    cs:__imp_FwFree
0x1800c1367  nop     dword ptr [rax+rax+00h]
0x1800c136c  mov     rcx, [rbp+var_28]
0x1800c1370  call    cs:__imp_FwFree
0x1800c1377  nop     dword ptr [rax+rax+00h]
0x1800c137c  mov     rcx, [rbp+var_30]
0x1800c1380  call    cs:__imp_FwFree
0x1800c1387  nop     dword ptr [rax+rax+00h]
0x1800c138c  test    ebx, ebx
0x1800c138e  jns     short loc_1800C13A1
0x1800c1390  mov     ecx, ebx
0x1800c1392  call    cs:__imp_FwHResultToWindowsError
0x1800c1399  nop     dword ptr [rax+rax+00h]
0x1800c139e  mov     r14d, eax
0x1800c13a1  mov     eax, r14d
0x1800c13a4  mov     rcx, [rbp+var_8]
0x1800c13a8  xor     rcx, rsp; StackCookie
0x1800c13ab  call    __security_check_cookie
0x1800c13b0  mov     rbx, [rsp+50h+arg_18]
0x1800c13b8  add     rsp, 50h
0x1800c13bc  pop     r15
0x1800c13be  pop     r14
0x1800c13c0  pop     r13
0x1800c13c2  pop     r12
0x1800c13c4  pop     rdi
0x1800c13c5  pop     rsi
0x1800c13c6  pop     rbp
0x1800c13c7  retn
```
