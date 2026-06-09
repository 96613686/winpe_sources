# GetUserSid2NameSubKey(void *,ushort * *)

- ea: `0x180006cb0`
- end: `0x180006f95`
- name: `?GetUserSid2NameSubKey@@YAJPEAXPEAPEAG@Z`
- size: `741`
- prototype: `__int64 __fastcall(void *, unsigned __int16 **)`
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180004e80`
- `0x180006a80`
- `0x180008060`
- `0x18002ea68`
- `0x1800307d0`
- `0x18005dc18`

## callees

- `0x180006cb0`
- `0x180007690`
- `0x180007fc0`
- `0x18000a600`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006eac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006eac`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180006cd2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180006cd2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006d9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006d9d`

## string_xrefs

- `0x180006d5f`: `Sid2Name`
- `0x180006dc5`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180006e08`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180006e5e`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180006ebf`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180006f10`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180006f49`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180006eec`: `ConvertSidToStringSid`

## pseudocode

```c
__int64 __fastcall GetUserSid2NameSubKey(void *a1, unsigned __int16 **a2)
{
  unsigned __int16 *v2; // rdi
  LPWSTR v4; // rax
  __int64 v5; // rcx
  unsigned int v6; // edx
  unsigned int v7; // ebx
  unsigned __int64 v8; // rbx
  const UCHAR *v10; // r9
  char v11; // al
  const UCHAR *v12; // rdx
  bool v13; // zf
  const char *v14; // r9
  const UCHAR *v15; // r9
  char v16; // al
  const UCHAR *v17; // rdx
  bool v18; // zf
  signed int LastError; // eax
  const UCHAR *v20; // r9
  char v21; // al
  const UCHAR *v22; // rdx
  bool v23; // zf
  const char *v24; // r9
  const char *v25; // r9
  __int64 v26; // [rsp+20h] [rbp-28h]
  LPWSTR StringSid; // [rsp+60h] [rbp+18h] BYREF

  v2 = 0;
  StringSid = 0;
  if ( ConvertSidToStringSidW(a1, &StringSid) )
  {
    v4 = StringSid;
    if ( StringSid )
    {
      v5 = 185;
      do
      {
        if ( !*v4 )
          break;
        ++v4;
        --v5;
      }
      while ( v5 );
      v6 = 185 - v5;
      v7 = -1073741811;
      if ( v5 )
      {
        if ( v6 + 10 < v6 )
        {
          v7 = -1073741675;
          v10 = "";
          while ( 1 )
          {
            v11 = *(v10 - 1);
            v12 = v10--;
            v13 = v11 == 92;
            if ( v11 == 92 )
              break;
            if ( v10 <= "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" )
            {
              v13 = v11 == 92;
              break;
            }
          }
          if ( v13 )
            v10 = v12;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225621LL, v10, 1390, "RtlDWordAdd", &Class);
        }
        else
        {
          v8 = 2LL * (v6 + 10);
          if ( v8 > 0xFFFFFFFF )
          {
            v7 = -1073741675;
            v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225621LL, v14, 1393, "RtlDWordMult", &Class);
          }
          else
          {
            v2 = (unsigned __int16 *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)((unsigned int)v8);
            if ( v2 )
            {
              v7 = RtlStringCchPrintfW(v2, (unsigned __int64)(unsigned int)v8 >> 1, L"%ws\\%ws", L"Sid2Name", StringSid);
              if ( v7 )
              {
                v25 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
                LODWORD(v26) = 1408;
                WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v7, v25, v26, "RtlStringCchPrintfW", &Class);
              }
              else
              {
                *a2 = v2;
                v2 = 0;
              }
            }
            else
            {
              v7 = -1073741801;
              v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v24, 1399, "AllocateLsaHeap", &Class);
            }
          }
        }
        goto LABEL_12;
      }
    }
    else
    {
      v7 = -1073741811;
    }
    v15 = "";
    while ( 1 )
    {
      v16 = *(v15 - 1);
      v17 = v15--;
      v18 = v16 == 92;
      if ( v16 == 92 )
        break;
      if ( v15 <= "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" )
      {
        v18 = v16 == 92;
        break;
      }
    }
    if ( v18 )
      v15 = v17;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v15, 1385, "RtlStringCchLengthW", &Class);
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0xC0070000;
    v20 = "";
    while ( 1 )
    {
      v21 = *(v20 - 1);
      v22 = v20--;
      v23 = v21 == 92;
      if ( v21 == 92 )
        break;
      if ( v20 <= "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" )
      {
        v23 = v21 == 92;
        break;
      }
    }
    if ( v23 )
      v20 = v22;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v7, v20, 1378, "ConvertSidToStringSid", &Class);
  }
LABEL_12:
  if ( StringSid )
    LocalFree(StringSid);
  if ( v2 )
    ((void (__fastcall *)(unsigned __int16 *))g_pLsaFunctionTable->FreeLsaHeap)(v2);
  return v7;
}

```

## disassembly

```asm
0x180006cb0  mov     [rsp+arg_8], rbx
0x180006cb5  push    rdi
0x180006cb6  sub     rsp, 40h
0x180006cba  mov     [rsp+48h+arg_0], rsi
0x180006cbf  xor     edi, edi
0x180006cc1  mov     rsi, rdx
0x180006cc4  mov     [rsp+48h+StringSid], 0
0x180006ccd  lea     rdx, [rsp+48h+StringSid]; StringSid
0x180006cd2  call    cs:__imp_ConvertSidToStringSidW
0x180006cd8  test    eax, eax
0x180006cda  jz      loc_180006EAC
0x180006ce0  mov     rax, [rsp+48h+StringSid]
0x180006ce5  test    rax, rax
0x180006ce8  jz      loc_180006E52
0x180006cee  mov     edx, 0B9h
0x180006cf3  mov     ecx, edx
0x180006cf5  cmp     [rax], di
0x180006cf8  jz      short loc_180006D04
0x180006cfa  add     rax, 2
0x180006cfe  sub     rcx, 1
0x180006d02  jnz     short loc_180006CF5
0x180006d04  xor     eax, eax
0x180006d06  sub     rdx, rcx
0x180006d09  test    rcx, rcx
0x180006d0c  mov     ebx, 0C000000Dh
0x180006d11  cmovz   rdx, rax
0x180006d15  cmovnz  ebx, eax
0x180006d18  jz      loc_180006E57
0x180006d1e  lea     eax, [rdx+0Ah]
0x180006d21  cmp     eax, edx
0x180006d23  jb      loc_180006DB9
0x180006d29  mov     ebx, eax
0x180006d2b  mov     eax, 0FFFFFFFFh
0x180006d30  add     rbx, rbx
0x180006d33  cmp     rbx, rax
0x180006d36  ja      loc_180006E08
0x180006d3c  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180006d43  mov     ecx, ebx
0x180006d45  mov     rax, [rax+28h]
0x180006d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d4e  mov     rdi, rax
0x180006d51  test    rax, rax
0x180006d54  jz      loc_180006F10
0x180006d5a  mov     rax, [rsp+48h+StringSid]
0x180006d5f  lea     r9, aSid2name; "Sid2Name"
0x180006d66  mov     edx, ebx
0x180006d68  lea     r8, aWsWs_1; "%ws\\%ws"
0x180006d6f  shr     rdx, 1; unsigned __int64
0x180006d72  mov     rcx, rdi; unsigned __int16 *
0x180006d75  mov     [rsp+48h+var_28], rax
0x180006d7a  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006d7f  mov     ebx, eax
0x180006d81  test    eax, eax
0x180006d83  jnz     loc_180006F49
0x180006d89  mov     [rsi], rdi
0x180006d8c  xor     edi, edi
0x180006d8e  mov     rcx, [rsp+48h+StringSid]; hMem
0x180006d93  mov     rsi, [rsp+48h+arg_0]
0x180006d98  test    rcx, rcx
0x180006d9b  jz      short loc_180006DA3
0x180006d9d  call    cs:__imp_LocalFree
0x180006da3  test    rdi, rdi
0x180006da6  jnz     loc_180006F7D
0x180006dac  mov     eax, ebx
0x180006dae  mov     rbx, [rsp+48h+arg_8]
0x180006db3  add     rsp, 40h
0x180006db7  pop     rdi
0x180006db8  retn
0x180006db9  mov     ebx, 0C0000095h
0x180006dbe  lea     r9, pbInput+24h; ""
0x180006dc5  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180006dcc  movzx   eax, byte ptr [r9-1]
0x180006dd1  mov     rdx, r9
0x180006dd4  dec     r9
0x180006dd7  cmp     al, 5Ch ; '\'
0x180006dd9  jz      short loc_180006DE2
0x180006ddb  cmp     r9, rcx
0x180006dde  ja      short loc_180006DCC
0x180006de0  cmp     al, 5Ch ; '\'
0x180006de2  lea     rax, Class
0x180006de9  cmovz   r9, rdx
0x180006ded  mov     [rsp+48h+var_18], rax
0x180006df2  lea     rax, aRtldwordadd; "RtlDWordAdd"
0x180006df9  mov     [rsp+48h+var_20], rax
0x180006dfe  mov     dword ptr [rsp+48h+var_28], 56Eh
0x180006e06  jmp     short loc_180006E3C
0x180006e08  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180006e0f  mov     ebx, 0C0000095h
0x180006e14  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180006e19  mov     r9, rax
0x180006e1c  lea     rax, Class
0x180006e23  mov     [rsp+48h+var_18], rax
0x180006e28  lea     rax, aRtldwordmult; "RtlDWordMult"
0x180006e2f  mov     [rsp+48h+var_20], rax
0x180006e34  mov     dword ptr [rsp+48h+var_28], 571h
0x180006e3c  mov     r8d, ebx
0x180006e3f  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180006e46  xor     ecx, ecx
0x180006e48  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180006e4d  jmp     loc_180006D8E
0x180006e52  mov     ebx, 0C000000Dh
0x180006e57  lea     r9, pbInput+24h; ""
0x180006e5e  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180006e65  nop     word ptr [rax+rax+00000000h]
0x180006e70  movzx   eax, byte ptr [r9-1]
0x180006e75  mov     rdx, r9
0x180006e78  dec     r9
0x180006e7b  cmp     al, 5Ch ; '\'
0x180006e7d  jz      short loc_180006E86
0x180006e7f  cmp     r9, rcx
0x180006e82  ja      short loc_180006E70
0x180006e84  cmp     al, 5Ch ; '\'
0x180006e86  lea     rax, Class
0x180006e8d  cmovz   r9, rdx
0x180006e91  mov     [rsp+48h+var_18], rax
0x180006e96  lea     rax, aRtlstringcchle_0; "RtlStringCchLengthW"
0x180006e9d  mov     [rsp+48h+var_20], rax
0x180006ea2  mov     dword ptr [rsp+48h+var_28], 569h
0x180006eaa  jmp     short loc_180006E3C
0x180006eac  call    cs:__imp_GetLastError
0x180006eb2  mov     ebx, eax
0x180006eb4  test    eax, eax
0x180006eb6  jg      short loc_180006F05
0x180006eb8  lea     r9, pbInput+24h; ""
0x180006ebf  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180006ec6  movzx   eax, byte ptr [r9-1]
0x180006ecb  mov     rdx, r9
0x180006ece  dec     r9
0x180006ed1  cmp     al, 5Ch ; '\'
0x180006ed3  jz      short loc_180006EDC
0x180006ed5  cmp     r9, rcx
0x180006ed8  ja      short loc_180006EC6
0x180006eda  cmp     al, 5Ch ; '\'
0x180006edc  lea     rax, Class
0x180006ee3  cmovz   r9, rdx
0x180006ee7  mov     [rsp+48h+var_18], rax
0x180006eec  lea     rax, aConvertsidtost; "ConvertSidToStringSid"
0x180006ef3  mov     [rsp+48h+var_20], rax
0x180006ef8  mov     dword ptr [rsp+48h+var_28], 562h
0x180006f00  jmp     loc_180006E3C
0x180006f05  movzx   ebx, ax
0x180006f08  or      ebx, 0C0070000h
0x180006f0e  jmp     short loc_180006EB8
0x180006f10  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180006f17  mov     ebx, 0C0000017h
0x180006f1c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180006f21  mov     r9, rax
0x180006f24  lea     rax, Class
0x180006f2b  mov     [rsp+48h+var_18], rax
0x180006f30  lea     rax, aAllocatelsahea_3; "AllocateLsaHeap"
0x180006f37  mov     [rsp+48h+var_20], rax
0x180006f3c  mov     dword ptr [rsp+48h+var_28], 577h
0x180006f44  jmp     loc_180006E3C
0x180006f49  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180006f50  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180006f55  mov     r9, rax
0x180006f58  lea     rax, Class
0x180006f5f  mov     [rsp+48h+var_18], rax
0x180006f64  lea     rax, aRtlstringcchpr; "RtlStringCchPrintfW"
0x180006f6b  mov     [rsp+48h+var_20], rax
0x180006f70  mov     dword ptr [rsp+48h+var_28], 580h
0x180006f78  jmp     loc_180006E3C
0x180006f7d  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180006f84  mov     rcx, rdi
0x180006f87  mov     rax, [rax+30h]
0x180006f8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f90  jmp     loc_180006DAC
```
