# GetRegVal(HKEY__ *,ushort const *,ulong,ulong *,void * *)

- ea: `0x18000a8f0`
- end: `0x18000ac39`
- name: `?GetRegVal@@YAJPEAUHKEY__@@PEBGKPEAKPEAPEAX@Z`
- size: `841`
- prototype: `__int64 __usercall@<rax>(HKEY hkey@<rcx>, LPCWSTR lpValue@<rdx>, DWORD dwFlags@<r8d>, unsigned int *@<r9>, void **)`
- caller_count: `16`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180004e80`
- `0x180008060`
- `0x18000c600`
- `0x18001a624`
- `0x18002ea68`
- `0x1800307d0`
- `0x180037240`
- `0x18003ea9c`
- `0x180048e60`
- `0x18004c808`
- `0x18004e3b4`
- `0x18004e7b0`
- `0x18004f600`
- `0x180052358`
- `0x180052978`
- `0x18005c644`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18000a8f0`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a96c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a9c9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a96c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a9c9`

## string_xrefs

- `0x18000aa15`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18000aac8`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18000ab15`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18000abbb`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18000abec`: `onecore\ds\ext\cloudap\dll\utils.cpp`

## pseudocode

```c
__int64 __fastcall GetRegVal(HKEY hkey, LPCWSTR lpValue, DWORD dwFlags, unsigned int *a4, void **a5)
{
  unsigned int ValueW; // r15d
  void *pvData; // rsi
  unsigned int v11; // r15d
  __int64 result; // rax
  const UCHAR *v13; // rbx
  const UCHAR *v14; // r9
  char v15; // al
  const UCHAR *v16; // rcx
  bool v17; // zf
  char v18; // al
  const UCHAR *v19; // rcx
  bool v20; // zf
  const char *v21; // rax
  const char *v22; // rax
  const char *v23; // rax
  const char *v24; // r9
  const char *v25; // r9
  LPDWORD pdwType; // [rsp+20h] [rbp-58h]
  LPDWORD pdwTypea; // [rsp+20h] [rbp-58h]
  LPDWORD pdwTypeb; // [rsp+20h] [rbp-58h]
  LPDWORD pdwTypec; // [rsp+20h] [rbp-58h]
  DWORD pcbData; // [rsp+40h] [rbp-38h] BYREF
  DWORD v31[13]; // [rsp+44h] [rbp-34h] BYREF

  v31[0] = 0;
  pcbData = 0;
  if ( !a5 || !a4 )
  {
    v25 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v25, 355, "Invalid Arg(s)", &Class);
    return 3221225485LL;
  }
  *a5 = 0;
  *a4 = 0;
  if ( !hkey || !lpValue )
  {
    v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v24, 364, "Invalid Arg(s)", &Class);
    return 3221225485LL;
  }
  ValueW = RegGetValueW(hkey, 0, lpValue, dwFlags, v31, 0, &pcbData);
  if ( ValueW )
  {
    v13 = "";
    v14 = "";
    while ( 1 )
    {
      v15 = *(v14 - 1);
      v16 = v14--;
      v17 = v15 == 92;
      if ( v15 == 92 )
        break;
      if ( v14 <= "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" )
      {
        v17 = v15 == 92;
        break;
      }
    }
    if ( v17 )
      v14 = v16;
    LODWORD(pdwType) = 377;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", ValueW, v14, pdwType, "RegGetValueW", lpValue);
    if ( ValueW - 2 > 1 )
    {
      if ( (int)ValueW > 0 )
        ValueW = (unsigned __int16)ValueW | 0xC0070000;
    }
    else
    {
      ValueW = -1073741275;
    }
    while ( 1 )
    {
      v18 = *(v13 - 1);
      v19 = v13--;
      v20 = v18 == 92;
      if ( v18 == 92 )
        break;
      if ( v13 <= "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" )
      {
        v20 = v18 == 92;
        break;
      }
    }
    if ( v20 )
      v13 = v19;
    LODWORD(pdwTypeb) = 387;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", ValueW, v13, pdwTypeb, "RegGetValueW", lpValue);
    return ValueW;
  }
  else
  {
    pvData = (void *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)(pcbData);
    if ( pvData )
    {
      v11 = RegGetValueW(hkey, 0, lpValue, dwFlags, v31, pvData, &pcbData);
      if ( v11 )
      {
        v22 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
        LODWORD(pdwTypea) = 407;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v22, pdwTypea, "RegGetValueW", lpValue);
        if ( v11 - 2 <= 1 )
        {
          v11 = -1073741275;
        }
        else if ( (int)v11 > 0 )
        {
          v11 = (unsigned __int16)v11 | 0xC0070000;
        }
        v23 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
        LODWORD(pdwTypec) = 417;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v11, v23, pdwTypec, "RegGetValueW", lpValue);
        ((void (__fastcall *)(void *))g_pLsaFunctionTable->FreeLsaHeap)(pvData);
        return v11;
      }
      else
      {
        *a4 = pcbData;
        result = 0;
        *a5 = pvData;
      }
    }
    else
    {
      v21 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
      LODWORD(pdwType) = 394;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v21, pdwType, "AllocateLsaHeap", &Class);
      return 3221225495LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000a8f0  mov     r11, rsp
0x18000a8f3  mov     [r11+18h], rbx
0x18000a8f7  push    rbp
0x18000a8f8  push    rdi
0x18000a8f9  push    r12
0x18000a8fb  push    r13
0x18000a8fd  push    r14
0x18000a8ff  sub     rsp, 50h
0x18000a903  mov     rdi, [rsp+78h+arg_20]
0x18000a90b  xor     r13d, r13d
0x18000a90e  mov     [r11-34h], r13d
0x18000a912  mov     rbx, r9
0x18000a915  mov     [r11-38h], r13d
0x18000a919  mov     r12d, r8d
0x18000a91c  mov     r14, rdx
0x18000a91f  mov     rbp, rcx
0x18000a922  test    rdi, rdi
0x18000a925  jz      loc_18000ABEC
0x18000a92b  test    rbx, rbx
0x18000a92e  jz      loc_18000ABEC
0x18000a934  mov     [rdi], r13
0x18000a937  mov     [r9], r13d
0x18000a93a  test    rcx, rcx
0x18000a93d  jz      loc_18000ABBB
0x18000a943  test    rdx, rdx
0x18000a946  jz      loc_18000ABBB
0x18000a94c  lea     rax, [r11-38h]
0x18000a950  mov     [r11+10h], r15
0x18000a954  mov     [r11-48h], rax
0x18000a958  mov     r9d, r8d; dwFlags
0x18000a95b  lea     rax, [r11-34h]
0x18000a95f  mov     [r11-50h], r13
0x18000a963  mov     r8, rdx; lpValue
0x18000a966  mov     [r11-58h], rax
0x18000a96a  xor     edx, edx; lpSubKey
0x18000a96c  call    cs:__imp_RegGetValueW
0x18000a972  mov     r15d, eax
0x18000a975  test    eax, eax
0x18000a977  jnz     loc_18000AA0B
0x18000a97d  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18000a984  mov     ecx, [rsp+78h+var_38]
0x18000a988  mov     [rsp+78h+arg_0], rsi
0x18000a990  mov     rax, [rax+28h]
0x18000a994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a999  mov     rsi, rax
0x18000a99c  test    rax, rax
0x18000a99f  jz      loc_18000AAC8
0x18000a9a5  lea     rax, [rsp+78h+var_38]
0x18000a9aa  mov     r9d, r12d; dwFlags
0x18000a9ad  mov     [rsp+78h+pcbData], rax; pcbData
0x18000a9b2  mov     r8, r14; lpValue
0x18000a9b5  lea     rax, [rsp+78h+var_34]
0x18000a9ba  mov     [rsp+78h+pvData], rsi; pvData
0x18000a9bf  xor     edx, edx; lpSubKey
0x18000a9c1  mov     [rsp+78h+pdwType], rax; pdwType
0x18000a9c6  mov     rcx, rbp; hkey
0x18000a9c9  call    cs:__imp_RegGetValueW
0x18000a9cf  mov     r15d, eax
0x18000a9d2  test    eax, eax
0x18000a9d4  jnz     loc_18000AB15
0x18000a9da  mov     eax, [rsp+78h+var_38]
0x18000a9de  mov     [rbx], eax
0x18000a9e0  mov     eax, r13d
0x18000a9e3  mov     [rdi], rsi
0x18000a9e6  mov     rsi, [rsp+78h+arg_0]
0x18000a9ee  mov     r15, [rsp+78h+arg_8]
0x18000a9f6  mov     rbx, [rsp+78h+arg_10]
0x18000a9fe  add     rsp, 50h
0x18000aa02  pop     r14
0x18000aa04  pop     r13
0x18000aa06  pop     r12
0x18000aa08  pop     rdi
0x18000aa09  pop     rbp
0x18000aa0a  retn
0x18000aa0b  lea     rbx, pbInput+24h; ""
0x18000aa12  mov     r9, rbx
0x18000aa15  lea     rdi, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18000aa1c  movzx   eax, byte ptr [r9-1]
0x18000aa21  mov     rcx, r9
0x18000aa24  dec     r9
0x18000aa27  cmp     al, 5Ch ; '\'
0x18000aa29  jz      short loc_18000AA32
0x18000aa2b  cmp     r9, rdi
0x18000aa2e  ja      short loc_18000AA1C
0x18000aa30  cmp     al, 5Ch ; '\'
0x18000aa32  cmovz   r9, rcx
0x18000aa36  mov     [rsp+78h+pcbData], r14
0x18000aa3b  lea     rbp, aReggetvaluew; "RegGetValueW"
0x18000aa42  mov     r8d, r15d
0x18000aa45  mov     [rsp+78h+pvData], rbp
0x18000aa4a  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000aa51  xor     ecx, ecx
0x18000aa53  mov     dword ptr [rsp+78h+pdwType], 179h
0x18000aa5b  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000aa60  lea     eax, [r15-2]
0x18000aa64  cmp     eax, 1
0x18000aa67  ja      short loc_18000AAB6
0x18000aa69  mov     r15d, 0C0000225h
0x18000aa6f  movzx   eax, byte ptr [rbx-1]
0x18000aa73  mov     rcx, rbx
0x18000aa76  dec     rbx
0x18000aa79  cmp     al, 5Ch ; '\'
0x18000aa7b  jz      short loc_18000AA84
0x18000aa7d  cmp     rbx, rdi
0x18000aa80  ja      short loc_18000AA6F
0x18000aa82  cmp     al, 5Ch ; '\'
0x18000aa84  cmovz   rbx, rcx
0x18000aa88  mov     [rsp+78h+pcbData], r14
0x18000aa8d  mov     r9, rbx
0x18000aa90  mov     [rsp+78h+pvData], rbp
0x18000aa95  mov     r8d, r15d
0x18000aa98  mov     dword ptr [rsp+78h+pdwType], 183h
0x18000aaa0  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000aaa7  xor     ecx, ecx
0x18000aaa9  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000aaae  mov     eax, r15d
0x18000aab1  jmp     loc_18000A9EE
0x18000aab6  test    r15d, r15d
0x18000aab9  jle     short loc_18000AA6F
0x18000aabb  movzx   r15d, r15w
0x18000aabf  or      r15d, 0C0070000h
0x18000aac6  jmp     short loc_18000AA6F
0x18000aac8  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18000aacf  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000aad4  lea     rcx, Class
0x18000aadb  mov     r9, rax
0x18000aade  mov     [rsp+78h+pcbData], rcx
0x18000aae3  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000aaea  lea     rcx, aAllocatelsahea_3; "AllocateLsaHeap"
0x18000aaf1  mov     r8d, 0C0000017h
0x18000aaf7  mov     [rsp+78h+pvData], rcx
0x18000aafc  xor     ecx, ecx
0x18000aafe  mov     dword ptr [rsp+78h+pdwType], 18Ah
0x18000ab06  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000ab0b  mov     eax, 0C0000017h
0x18000ab10  jmp     loc_18000A9E6
0x18000ab15  lea     rdi, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18000ab1c  mov     rcx, rdi; char *
0x18000ab1f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000ab24  mov     [rsp+78h+pcbData], r14
0x18000ab29  lea     rbp, aReggetvaluew; "RegGetValueW"
0x18000ab30  mov     [rsp+78h+pvData], rbp
0x18000ab35  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000ab3c  mov     r9, rax
0x18000ab3f  mov     dword ptr [rsp+78h+pdwType], 197h
0x18000ab47  mov     r8d, r15d
0x18000ab4a  xor     ecx, ecx
0x18000ab4c  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000ab51  lea     eax, [r15-2]
0x18000ab55  cmp     eax, 1
0x18000ab58  jbe     short loc_18000AB6C
0x18000ab5a  test    r15d, r15d
0x18000ab5d  jle     short loc_18000AB72
0x18000ab5f  movzx   r15d, r15w
0x18000ab63  or      r15d, 0C0070000h
0x18000ab6a  jmp     short loc_18000AB72
0x18000ab6c  mov     r15d, 0C0000225h
0x18000ab72  mov     rcx, rdi; char *
0x18000ab75  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000ab7a  mov     [rsp+78h+pcbData], r14
0x18000ab7f  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000ab86  mov     r9, rax
0x18000ab89  mov     [rsp+78h+pvData], rbp
0x18000ab8e  mov     r8d, r15d
0x18000ab91  mov     dword ptr [rsp+78h+pdwType], 1A1h
0x18000ab99  xor     ecx, ecx
0x18000ab9b  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000aba0  mov     rcx, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18000aba7  mov     rax, [rcx+30h]
0x18000abab  mov     rcx, rsi
0x18000abae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abb3  mov     eax, r15d
0x18000abb6  jmp     loc_18000A9E6
0x18000abbb  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18000abc2  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000abc7  mov     r9, rax
0x18000abca  lea     rcx, Class
0x18000abd1  mov     [rsp+78h+pcbData], rcx
0x18000abd6  lea     rax, aInvalidArgS; "Invalid Arg(s)"
0x18000abdd  mov     [rsp+78h+pvData], rax
0x18000abe2  mov     dword ptr [rsp+78h+pdwType], 16Ch
0x18000abea  jmp     short loc_18000AC1B
0x18000abec  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18000abf3  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000abf8  mov     r9, rax
0x18000abfb  lea     rcx, Class
0x18000ac02  mov     [rsp+78h+pcbData], rcx
0x18000ac07  lea     rax, aInvalidArgS; "Invalid Arg(s)"
0x18000ac0e  mov     [rsp+78h+pvData], rax
0x18000ac13  mov     dword ptr [rsp+78h+pdwType], 163h
0x18000ac1b  mov     r8d, 0C000000Dh
0x18000ac21  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000ac28  xor     ecx, ecx
0x18000ac2a  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000ac2f  mov     eax, 0C000000Dh
0x18000ac34  jmp     loc_18000A9F6
```
