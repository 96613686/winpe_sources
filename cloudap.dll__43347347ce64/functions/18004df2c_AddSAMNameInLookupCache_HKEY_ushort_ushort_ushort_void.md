# AddSAMNameInLookupCache(HKEY__ *,ushort *,ushort *,ushort *,void *)

- ea: `0x18004df2c`
- end: `0x18004e1af`
- name: `?AddSAMNameInLookupCache@@YAJPEAUHKEY__@@PEAG11PEAX@Z`
- size: `643`
- prototype: `__int64 __fastcall(HKEY, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, PSID Sid)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800307d0`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18003ca18`
- `0x18004df2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004df63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004df63`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004df59`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004df59`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18004e139`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18004e139`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004e19c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004e19c`

## string_xrefs

- `0x18004df78`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18004dfe8`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18004e048`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18004e0a7`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18004e108`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18004e152`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18004e0e4`: `Sid2Name`
- `0x18004e088`: `Name2Sid`
- `0x18004df93`: `ConvertSidToStringSidW`
- `0x18004dffc`: `SetStringRegVal(Name2SID)`
- `0x18004e0bf`: `SetStringRegVal(Name2SID)`
- `0x18004e120`: `SetStringRegVal(SID2Name)`

## pseudocode

```c
__int64 __fastcall AddSAMNameInLookupCache(
        HKEY a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        PSID Sid)
{
  signed int LastError; // eax
  unsigned int v10; // ebx
  const char *v11; // r9
  const char *v12; // rax
  __int64 v13; // r8
  const char *v14; // rax
  __int64 v15; // r8
  const char *v16; // r9
  const char *v17; // r9
  LSTATUS v18; // eax
  const char *v19; // r9
  unsigned __int16 *v21; // [rsp+20h] [rbp-58h]
  unsigned __int16 *v22; // [rsp+20h] [rbp-58h]
  unsigned __int16 *v23; // [rsp+20h] [rbp-58h]
  unsigned __int16 *v24; // [rsp+20h] [rbp-58h]
  LPWSTR StringSid; // [rsp+40h] [rbp-38h] BYREF

  StringSid = 0;
  if ( ConvertSidToStringSidW(Sid, &StringSid) )
  {
    v10 = SetStringRegVal(a1, L"SAM_Name", a4, L"Sid", StringSid);
    if ( v10 )
    {
      v12 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
      LODWORD(v21) = 2050;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v10, v12, v21, "SetStringRegVal(Name2SID)", v13);
    }
    else
    {
      v10 = SetStringRegVal(a1, L"SAM_Name", a4, L"IdentityName", a3);
      if ( v10 )
      {
        v14 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
        LODWORD(v22) = 2059;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v10, v14, v22, "SetStringRegVal(SAMName-IdentityName)", v15);
      }
      else
      {
        v10 = SetStringRegVal(a1, L"Name2Sid", a2, L"SAMName", a4);
        if ( v10 )
        {
          if ( !a4 )
            a4 = (unsigned __int16 *)&Class;
          v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
          LODWORD(v23) = 2069;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v10, v16, v23, "SetStringRegVal(Name2SID)", a4);
        }
        else
        {
          v10 = SetStringRegVal(a1, L"Sid2Name", StringSid, L"SAMName", a4);
          if ( v10 )
          {
            if ( !a4 )
              a4 = (unsigned __int16 *)&Class;
            v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
            LODWORD(v24) = 2081;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v10, v17, v24, "SetStringRegVal(SID2Name)", a4);
          }
          else
          {
            v18 = RegFlushKey(a1);
            if ( v18 )
            {
              if ( v18 > 0 )
                v10 = (unsigned __int16)v18 | 0xC0070000;
              else
                v10 = v18;
              v19 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
              LODWORD(v24) = 2087;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v10, v19, v24, "RegFlushKey", &Class);
            }
          }
        }
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0xC0070000;
    v11 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v10, v11, 2033, "ConvertSidToStringSidW", &Class);
  }
  if ( StringSid )
    LocalFree(StringSid);
  return v10;
}

```

## disassembly

```asm
0x18004df2c  push    rbx
0x18004df2e  push    rbp
0x18004df2f  push    rsi
0x18004df30  push    rdi
0x18004df31  push    r14
0x18004df33  sub     rsp, 50h
0x18004df37  mov     r14, rdx
0x18004df3a  mov     [rsp+78h+StringSid], 0
0x18004df43  mov     rsi, rcx
0x18004df46  lea     rdx, [rsp+78h+StringSid]; StringSid
0x18004df4b  mov     rcx, [rsp+78h+Sid]; Sid
0x18004df53  mov     rdi, r9
0x18004df56  mov     rbp, r8
0x18004df59  call    cs:__imp_ConvertSidToStringSidW
0x18004df5f  test    eax, eax
0x18004df61  jnz     short loc_18004DFAC
0x18004df63  call    cs:__imp_GetLastError
0x18004df69  mov     ebx, eax
0x18004df6b  test    eax, eax
0x18004df6d  jle     short loc_18004DF78
0x18004df6f  movzx   ebx, ax
0x18004df72  or      ebx, 0C0070000h
0x18004df78  lea     rcx, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x18004df7f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004df84  mov     r9, rax
0x18004df87  lea     r8, Class
0x18004df8e  mov     [rsp+78h+var_48], r8
0x18004df93  lea     rax, aConvertsidtost_0; "ConvertSidToStringSidW"
0x18004df9a  mov     [rsp+78h+var_50], rax
0x18004df9f  mov     dword ptr [rsp+78h+var_58], 7F1h
0x18004dfa7  jmp     loc_18004E181
0x18004dfac  mov     rax, [rsp+78h+StringSid]
0x18004dfb1  lea     r9, aSid; "Sid"
0x18004dfb8  mov     r8, rdi; unsigned __int16 *
0x18004dfbb  mov     [rsp+78h+var_58], rax; unsigned __int16 *
0x18004dfc0  lea     rdx, aSamName; "SAM_Name"
0x18004dfc7  mov     rcx, rsi; HKEY
0x18004dfca  call    ?SetStringRegVal@@YAJPEAUHKEY__@@PEBG111@Z; SetStringRegVal(HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18004dfcf  mov     ebx, eax
0x18004dfd1  test    eax, eax
0x18004dfd3  jz      short loc_18004E015
0x18004dfd5  mov     rcx, [rsp+78h+StringSid]
0x18004dfda  lea     r8, Class
0x18004dfe1  test    rcx, rcx
0x18004dfe4  cmovnz  r8, rcx
0x18004dfe8  lea     rcx, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x18004dfef  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004dff4  mov     [rsp+78h+var_48], r8
0x18004dff9  mov     r9, rax
0x18004dffc  lea     rax, aSetstringregva_6; "SetStringRegVal(Name2SID)"
0x18004e003  mov     [rsp+78h+var_50], rax
0x18004e008  mov     dword ptr [rsp+78h+var_58], 802h
0x18004e010  jmp     loc_18004E181
0x18004e015  lea     r9, aIdentityname; "IdentityName"
0x18004e01c  mov     [rsp+78h+var_58], rbp; unsigned __int16 *
0x18004e021  mov     r8, rdi; unsigned __int16 *
0x18004e024  lea     rdx, aSamName; "SAM_Name"
0x18004e02b  mov     rcx, rsi; HKEY
0x18004e02e  call    ?SetStringRegVal@@YAJPEAUHKEY__@@PEBG111@Z; SetStringRegVal(HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18004e033  mov     ebx, eax
0x18004e035  test    eax, eax
0x18004e037  jz      short loc_18004E079
0x18004e039  mov     rax, [rsp+78h+StringSid]
0x18004e03e  lea     r8, Class
0x18004e045  test    rax, rax
0x18004e048  lea     rcx, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x18004e04f  cmovnz  r8, rax
0x18004e053  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004e058  mov     [rsp+78h+var_48], r8
0x18004e05d  mov     r9, rax
0x18004e060  lea     rax, aSetstringregva_7; "SetStringRegVal(SAMName-IdentityName)"
0x18004e067  mov     [rsp+78h+var_50], rax
0x18004e06c  mov     dword ptr [rsp+78h+var_58], 80Bh
0x18004e074  jmp     loc_18004E181
0x18004e079  lea     r9, aSamname; "SAMName"
0x18004e080  mov     [rsp+78h+var_58], rdi; unsigned __int16 *
0x18004e085  mov     r8, r14; unsigned __int16 *
0x18004e088  lea     rdx, aName2sid; "Name2Sid"
0x18004e08f  mov     rcx, rsi; HKEY
0x18004e092  call    ?SetStringRegVal@@YAJPEAUHKEY__@@PEBG111@Z; SetStringRegVal(HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18004e097  mov     ebx, eax
0x18004e099  test    eax, eax
0x18004e09b  jz      short loc_18004E0D8
0x18004e09d  test    rdi, rdi
0x18004e0a0  lea     r8, Class
0x18004e0a7  lea     rcx, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x18004e0ae  cmovz   rdi, r8
0x18004e0b2  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004e0b7  mov     [rsp+78h+var_48], rdi
0x18004e0bc  mov     r9, rax
0x18004e0bf  lea     rax, aSetstringregva_6; "SetStringRegVal(Name2SID)"
0x18004e0c6  mov     [rsp+78h+var_50], rax
0x18004e0cb  mov     dword ptr [rsp+78h+var_58], 815h
0x18004e0d3  jmp     loc_18004E181
0x18004e0d8  mov     r8, [rsp+78h+StringSid]; unsigned __int16 *
0x18004e0dd  lea     r9, aSamname; "SAMName"
0x18004e0e4  lea     rdx, aSid2name; "Sid2Name"
0x18004e0eb  mov     [rsp+78h+var_58], rdi; unsigned __int16 *
0x18004e0f0  mov     rcx, rsi; HKEY
0x18004e0f3  call    ?SetStringRegVal@@YAJPEAUHKEY__@@PEBG111@Z; SetStringRegVal(HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18004e0f8  mov     ebx, eax
0x18004e0fa  test    eax, eax
0x18004e0fc  jz      short loc_18004E136
0x18004e0fe  test    rdi, rdi
0x18004e101  lea     r8, Class
0x18004e108  lea     rcx, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x18004e10f  cmovz   rdi, r8
0x18004e113  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004e118  mov     [rsp+78h+var_48], rdi
0x18004e11d  mov     r9, rax
0x18004e120  lea     rax, aSetstringregva_4; "SetStringRegVal(SID2Name)"
0x18004e127  mov     [rsp+78h+var_50], rax
0x18004e12c  mov     dword ptr [rsp+78h+var_58], 821h
0x18004e134  jmp     short loc_18004E181
0x18004e136  mov     rcx, rsi; hKey
0x18004e139  call    cs:__imp_RegFlushKey
0x18004e13f  test    eax, eax
0x18004e141  jz      short loc_18004E192
0x18004e143  jg      short loc_18004E149
0x18004e145  mov     ebx, eax
0x18004e147  jmp     short loc_18004E152
0x18004e149  movzx   ebx, ax
0x18004e14c  or      ebx, 0C0070000h
0x18004e152  lea     rcx, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x18004e159  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004e15e  mov     r9, rax
0x18004e161  lea     r8, Class
0x18004e168  mov     [rsp+78h+var_48], r8
0x18004e16d  lea     rax, aRegflushkey; "RegFlushKey"
0x18004e174  mov     [rsp+78h+var_50], rax
0x18004e179  mov     dword ptr [rsp+78h+var_58], 827h
0x18004e181  mov     r8d, ebx
0x18004e184  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004e18b  xor     ecx, ecx
0x18004e18d  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004e192  mov     rcx, [rsp+78h+StringSid]; hMem
0x18004e197  test    rcx, rcx
0x18004e19a  jz      short loc_18004E1A2
0x18004e19c  call    cs:__imp_LocalFree
0x18004e1a2  mov     eax, ebx
0x18004e1a4  add     rsp, 50h
0x18004e1a8  pop     r14
0x18004e1aa  pop     rdi
0x18004e1ab  pop     rsi
0x18004e1ac  pop     rbp
0x18004e1ad  pop     rbx
0x18004e1ae  retn
```
