# RemoveAllDnsServerForCompartmentRules(void)

- ea: `0x180093bc0`
- end: `0x180093fe5`
- name: `?RemoveAllDnsServerForCompartmentRules@@YAXXZ`
- size: `1061`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180075fb8`

## callees

- `0x180001b68`
- `0x18005ecc0`
- `0x18005f0c0`
- `0x180067c00`
- `0x18006c530`
- `0x1800759d8`
- `0x180075a34`
- `0x180075aac`
- `0x180085c64`
- `0x180093bc0`

## import_xrefs

- `FirewallAPI!FWFreeFirewallRules` at `0x180093f5e`
- `FirewallAPI!FWFreeFirewallRules` at `0x180093f5e`
- `FirewallAPI!FWQueryFirewallRules` at `0x180093d09`
- `FirewallAPI!FWQueryFirewallRules` at `0x180093d09`
- `FirewallAPI!FWDeleteFirewallRule` at `0x180093dd9`
- `FirewallAPI!FWDeleteFirewallRule` at `0x180093e70`
- `FirewallAPI!FWDeleteFirewallRule` at `0x180093dd9`
- `FirewallAPI!FWDeleteFirewallRule` at `0x180093e70`
- `FirewallAPI!FWOpenPolicyStore` at `0x180093c77`
- `FirewallAPI!FWOpenPolicyStore` at `0x180093c77`
- `FirewallAPI!FWClosePolicyStore` at `0x180093f8e`
- `FirewallAPI!FWClosePolicyStore` at `0x180093f8e`

## string_xrefs

- `0x180093bec`: `RemoveAllDnsServerForCompartmentRules`
- `0x180093c8e`: `RemoveAllDnsServerForCompartmentRules`
- `0x180093df2`: `RemoveAllDnsServerForCompartmentRules`
- `0x180093e87`: `RemoveAllDnsServerForCompartmentRules`
- `0x180093ec3`: `RemoveAllDnsServerForCompartmentRules`
- `0x180093f73`: `RemoveAllDnsServerForCompartmentRules`
- `0x180093fa3`: `RemoveAllDnsServerForCompartmentRules`
- `0x180093fb9`: `RemoveAllDnsServerForCompartmentRules`

## pseudocode

```c
void RemoveAllDnsServerForCompartmentRules(void)
{
  signed int v0; // eax
  unsigned int v1; // edx
  signed int v2; // eax
  __int64 v3; // rdx
  int v4; // r13d
  _QWORD *i; // r15
  _WORD *v6; // rdi
  unsigned __int64 v7; // rax
  __int64 v8; // r14
  __int64 v9; // rax
  __int64 v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rax
  signed int v13; // eax
  bool v14; // zf
  unsigned __int64 v15; // r8
  __int64 v16; // rbx
  __int64 v17; // rax
  signed int v18; // eax
  bool v19; // zf
  signed int v20; // eax
  signed int v21; // eax
  __int64 v22; // [rsp+30h] [rbp-D0h] BYREF
  int v23; // [rsp+38h] [rbp-C8h] BYREF
  int v24; // [rsp+3Ch] [rbp-C4h] BYREF
  _QWORD *v25; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v26[2]; // [rsp+48h] [rbp-B8h] BYREF
  int *v27; // [rsp+50h] [rbp-B0h]
  __int64 v28; // [rsp+58h] [rbp-A8h]
  __int64 v29; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v30; // [rsp+68h] [rbp-98h] BYREF
  __int128 v31; // [rsp+78h] [rbp-88h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int128 v33; // [rsp+98h] [rbp-68h] BYREF
  __int128 v34; // [rsp+A8h] [rbp-58h]
  __int128 v35; // [rsp+B8h] [rbp-48h]
  int v36; // [rsp+C8h] [rbp-38h] BYREF
  __int128 *v37; // [rsp+D0h] [rbp-30h]
  int v38; // [rsp+D8h] [rbp-28h]
  __int128 *v39; // [rsp+E0h] [rbp-20h]
  _OWORD v40[2]; // [rsp+E8h] [rbp-18h] BYREF
  _BYTE v41[32]; // [rsp+110h] [rbp+10h] BYREF
  __int64 *v42; // [rsp+130h] [rbp+30h]
  __int64 v43; // [rsp+138h] [rbp+38h]
  int *v44; // [rsp+140h] [rbp+40h]
  __int64 v45; // [rsp+148h] [rbp+48h]

  HNSTraceProvider::TraceEnter("RemoveAllDnsServerForCompartmentRules", 0x519u);
  v28 = 0x10000;
  v25 = 0;
  v22 = 0;
  v23 = 0;
  v37 = &v30;
  v36 = 2;
  v39 = &v33;
  v38 = 2;
  v27 = &v36;
  v26[0] = 545;
  v30 = 0;
  v26[1] = 2;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v0 = FWOpenPolicyStore(545, 0, 2, 2, 0, &v22);
  if ( v0 )
  {
    if ( v0 > 0 )
      v0 = (unsigned __int16)v0 | 0x80070000;
    HNSTraceProvider::TraceError("RemoveAllDnsServerForCompartmentRules", 0x536u, v0);
    v1 = 1335;
    goto LABEL_57;
  }
  *(_QWORD *)&v30 = 5;
  LOWORD(v31) = 17;
  DWORD2(v30) = 2;
  *((_QWORD *)&v31 + 1) = 6;
  LOWORD(v34) = 6;
  *((_QWORD *)&v34 + 1) = 6;
  LODWORD(v32) = 2;
  WORD4(v32) = 53;
  WORD4(v35) = 53;
  *(_QWORD *)&v33 = 5;
  DWORD2(v33) = 2;
  LODWORD(v35) = 2;
  v2 = FWQueryFirewallRules(v22, v26, 0, &v23, &v25);
  v4 = 0;
  if ( !v2 )
  {
    for ( i = v25; ; i = (_QWORD *)*i )
    {
      if ( !i )
        goto LABEL_42;
      v6 = (_WORD *)i[4];
      if ( v6 )
      {
        if ( HNS::Feature::m_npmPerfOptimizationEnabled )
        {
          v7 = -1;
          do
            ++v7;
          while ( v6[v7] );
          v8 = v7;
          if ( v7 < 0x18 )
          {
            if ( v7 < 0x17 )
              continue;
          }
          else
          {
            v9 = _std_search_2(i[4], &v6[v8], L"HNS Container Networking", 24);
            if ( (_WORD *)v9 != &v6[v8] )
            {
              v10 = (v9 - (__int64)v6) >> 1;
              goto LABEL_16;
            }
          }
          v10 = -1;
LABEL_16:
          v11 = _std_search_2(v6, &v6[v8], L"DNS Server Forward Rule", 23);
          if ( (_WORD *)v11 == &v6[v8] )
            v12 = -1;
          else
            v12 = (v11 - (__int64)v6) >> 1;
          if ( v10 != -1 || v12 != -1 )
          {
            v13 = FWDeleteFirewallRule(v22, i[2]);
            v14 = v13 == 0;
            if ( v13 > 0 )
            {
              v13 = (unsigned __int16)v13 | 0x80070000;
              v14 = v13 == 0;
            }
            if ( v14 )
              ++v4;
            else
              HNSTraceProvider::TraceError("RemoveAllDnsServerForCompartmentRules", 0x566u, v13);
          }
          continue;
        }
        memset(v40, 0, sizeof(v40));
        v15 = -1;
        do
          ++v15;
        while ( v6[v15] );
        std::wstring::_Construct<1,unsigned short const *>((char **)v40, v6, v15);
        v16 = std::wstring::find(v40, L"HNS Container Networking");
        v17 = std::wstring::find(v40, L"DNS Server Forward Rule");
        if ( v16 != -1 || v17 != -1 )
        {
          v18 = FWDeleteFirewallRule(v22, i[2]);
          v19 = v18 == 0;
          if ( v18 > 0 )
          {
            v18 = (unsigned __int16)v18 | 0x80070000;
            v19 = v18 == 0;
          }
          if ( v19 )
            ++v4;
          else
            HNSTraceProvider::TraceError("RemoveAllDnsServerForCompartmentRules", 0x578u, v18);
        }
        std::wstring::~wstring(v40);
      }
    }
  }
  if ( v2 > 0 )
    v2 = (unsigned __int16)v2 | 0x80070000;
  HNSTraceProvider::TraceError("RemoveAllDnsServerForCompartmentRules", 0x585u, v2);
LABEL_42:
  if ( *(_DWORD *)qword_1803982A8 > 5u )
  {
    v3 = *(_QWORD *)(qword_1803982A8 + 24);
    if ( (*(_QWORD *)(qword_1803982A8 + 16) & 0x400000000000LL) != 0 && (v3 & 0x400000000000LL) == v3 )
    {
      v24 = v4;
      v45 = 4;
      v44 = &v24;
      v29 = 2048;
      v42 = &v29;
      v43 = 8;
      tlgWriteTransfer_EventWriteTransfer(qword_1803982A8, &unk_18033467D, 0, 0, 4, v41);
    }
  }
  if ( v25 )
  {
    v20 = FWFreeFirewallRules(v25, v3);
    if ( v20 )
    {
      if ( v20 > 0 )
        v20 = (unsigned __int16)v20 | 0x80070000;
      HNSTraceProvider::TraceError("RemoveAllDnsServerForCompartmentRules", 0x594u, v20);
    }
  }
  if ( v22 )
  {
    v21 = FWClosePolicyStore(v22, v3);
    if ( v21 )
    {
      if ( v21 > 0 )
        v21 = (unsigned __int16)v21 | 0x80070000;
      HNSTraceProvider::TraceError("RemoveAllDnsServerForCompartmentRules", 0x59Du, v21);
    }
  }
  v1 = 1441;
LABEL_57:
  HNSTraceProvider::TraceSuccess("RemoveAllDnsServerForCompartmentRules", v1);
}

```

## disassembly

```asm
0x180093bc0  push    rbp
0x180093bc2  push    rbx
0x180093bc3  push    rsi
0x180093bc4  push    rdi
0x180093bc5  push    r12
0x180093bc7  push    r13
0x180093bc9  push    r14
0x180093bcb  push    r15
0x180093bcd  lea     rbp, [rsp-68h]
0x180093bd2  sub     rsp, 168h
0x180093bd9  mov     rax, cs:__security_cookie
0x180093be0  xor     rax, rsp
0x180093be3  mov     [rbp+0A0h+var_50], rax
0x180093be7  mov     edx, 519h; unsigned int
0x180093bec  lea     rcx, aRemovealldnsse; "RemoveAllDnsServerForCompartmentRules"
0x180093bf3  call    ?TraceEnter@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceEnter(char const *,uint)
0x180093bf8  xor     esi, esi
0x180093bfa  mov     [rsp+1A0h+var_148], 10000h
0x180093c03  xorps   xmm0, xmm0
0x180093c06  mov     [rsp+1A0h+var_160], rsi
0x180093c0b  xorps   xmm1, xmm1
0x180093c0e  mov     [rsp+1A0h+var_170], rsi
0x180093c13  lea     rax, [rsp+1A0h+var_138]
0x180093c18  mov     [rsp+1A0h+var_168], esi
0x180093c1c  lea     ebx, [rsi+2]
0x180093c1f  mov     [rbp+0A0h+var_D0], rax
0x180093c23  lea     rax, [rbp+0A0h+var_108]
0x180093c27  mov     [rbp+0A0h+var_D8], ebx
0x180093c2a  mov     [rbp+0A0h+var_C0], rax
0x180093c2e  mov     ecx, 221h
0x180093c33  lea     rax, [rbp+0A0h+var_D8]
0x180093c37  mov     [rbp+0A0h+var_C8], ebx
0x180093c3a  mov     [rsp+1A0h+var_150], rax
0x180093c3f  mov     r9d, ebx
0x180093c42  lea     rax, [rsp+1A0h+var_170]
0x180093c47  mov     [rsp+1A0h+var_158], ecx
0x180093c4b  mov     [rsp+1A0h+var_178], rax
0x180093c50  mov     r8d, ebx
0x180093c53  xor     edx, edx
0x180093c55  mov     dword ptr [rsp+1A0h+var_180], esi
0x180093c59  movups  [rsp+1A0h+var_138], xmm0
0x180093c5e  mov     [rsp+1A0h+var_154], ebx
0x180093c62  movups  [rsp+1A0h+var_128], xmm0
0x180093c67  movups  [rbp+0A0h+var_118], xmm0
0x180093c6b  movups  [rbp+0A0h+var_108], xmm1
0x180093c6f  movups  [rbp+0A0h+var_F8], xmm1
0x180093c73  movups  [rbp+0A0h+var_E8], xmm1
0x180093c77  call    cs:__imp_FWOpenPolicyStore
0x180093c7d  test    eax, eax
0x180093c7f  jz      short loc_180093CA9
0x180093c81  jle     short loc_180093C8B
0x180093c83  movzx   eax, ax
0x180093c86  or      eax, 80070000h
0x180093c8b  mov     r8d, eax; int
0x180093c8e  lea     rcx, aRemovealldnsse; "RemoveAllDnsServerForCompartmentRules"
0x180093c95  mov     edx, 536h; unsigned int
0x180093c9a  call    ?TraceError@HNSTraceProvider@@SAXPEBDIJ@Z; HNSTraceProvider::TraceError(char const *,uint,long)
0x180093c9f  mov     edx, 537h
0x180093ca4  jmp     loc_180093FB9
0x180093ca9  mov     eax, 11h
0x180093cae  mov     qword ptr [rsp+1A0h+var_138], 5
0x180093cb7  mov     word ptr [rsp+1A0h+var_128], ax
0x180093cbc  lea     r9, [rsp+1A0h+var_168]
0x180093cc1  mov     eax, 6
0x180093cc6  mov     dword ptr [rsp+1A0h+var_138+8], ebx
0x180093cca  mov     qword ptr [rbp+0A0h+var_128+8], rax
0x180093cce  lea     rdx, [rsp+1A0h+var_158]
0x180093cd3  mov     word ptr [rbp+0A0h+var_F8], ax
0x180093cd7  xor     r8d, r8d
0x180093cda  mov     qword ptr [rbp+0A0h+var_F8+8], rax
0x180093cde  lea     ecx, [rax+2Fh]
0x180093ce1  mov     dword ptr [rbp+0A0h+var_118], ebx
0x180093ce4  mov     word ptr [rbp+0A0h+var_118+8], cx
0x180093ce8  lea     rax, [rsp+1A0h+var_160]
0x180093ced  mov     word ptr [rbp+0A0h+var_E8+8], cx
0x180093cf1  mov     rcx, [rsp+1A0h+var_170]
0x180093cf6  mov     qword ptr [rbp+0A0h+var_108], 5
0x180093cfe  mov     dword ptr [rbp+0A0h+var_108+8], ebx
0x180093d01  mov     dword ptr [rbp+0A0h+var_E8], ebx
0x180093d04  mov     [rsp+1A0h+var_180], rax
0x180093d09  call    cs:__imp_FWQueryFirewallRules
0x180093d0f  mov     r13d, esi
0x180093d12  mov     r12d, 80070000h
0x180093d18  test    eax, eax
0x180093d1a  jnz     loc_180093EB8
0x180093d20  mov     r15, [rsp+1A0h+var_160]
0x180093d25  jmp     loc_180093EAD
0x180093d2a  mov     rdi, [r15+20h]
0x180093d2e  test    rdi, rdi
0x180093d31  jz      loc_180093EAA
0x180093d37  cmp     cs:?m_npmPerfOptimizationEnabled@Feature@HNS@@3HA, esi; int HNS::Feature::m_npmPerfOptimizationEnabled
0x180093d3d  jz      loc_180093E10
0x180093d43  or      rax, 0FFFFFFFFFFFFFFFFh
0x180093d47  inc     rax
0x180093d4a  cmp     [rdi+rax*2], si
0x180093d4e  jnz     short loc_180093D47
0x180093d50  lea     r14, [rax+rax]
0x180093d54  cmp     rax, 18h
0x180093d58  jb      short loc_180093D86
0x180093d5a  lea     rbx, [rdi+r14]
0x180093d5e  mov     r9d, 18h
0x180093d64  mov     rdx, rbx
0x180093d67  lea     r8, aHnsContainerNe; "HNS Container Networking"
0x180093d6e  mov     rcx, rdi
0x180093d71  call    __std_search_2
0x180093d76  mov     rsi, rax
0x180093d79  cmp     rax, rbx
0x180093d7c  jz      short loc_180093D90
0x180093d7e  sub     rsi, rdi
0x180093d81  sar     rsi, 1
0x180093d84  jmp     short loc_180093D94
0x180093d86  cmp     rax, 17h
0x180093d8a  jb      loc_180093EAA
0x180093d90  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180093d94  lea     rbx, [rdi+r14]
0x180093d98  mov     r9d, 17h
0x180093d9e  mov     rdx, rbx
0x180093da1  lea     r8, aDnsServerForwa; "DNS Server Forward Rule"
0x180093da8  mov     rcx, rdi
0x180093dab  call    __std_search_2
0x180093db0  cmp     rax, rbx
0x180093db3  jz      short loc_180093DBD
0x180093db5  sub     rax, rdi
0x180093db8  sar     rax, 1
0x180093dbb  jmp     short loc_180093DC1
0x180093dbd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180093dc1  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180093dc5  jnz     short loc_180093DD0
0x180093dc7  cmp     rax, rsi
0x180093dca  jz      loc_180093EA8
0x180093dd0  mov     rdx, [r15+10h]
0x180093dd4  mov     rcx, [rsp+1A0h+var_170]
0x180093dd9  call    cs:__imp_FWDeleteFirewallRule
0x180093ddf  xor     esi, esi
0x180093de1  test    eax, eax
0x180093de3  jle     short loc_180093DED
0x180093de5  movzx   eax, ax
0x180093de8  or      eax, r12d
0x180093deb  test    eax, eax
0x180093ded  jz      short loc_180093E08
0x180093def  mov     r8d, eax; int
0x180093df2  lea     rcx, aRemovealldnsse; "RemoveAllDnsServerForCompartmentRules"
0x180093df9  mov     edx, 566h; unsigned int
0x180093dfe  call    ?TraceError@HNSTraceProvider@@SAXPEBDIJ@Z; HNSTraceProvider::TraceError(char const *,uint,long)
0x180093e03  jmp     loc_180093EAA
0x180093e08  inc     r13d
0x180093e0b  jmp     loc_180093EAA
0x180093e10  xorps   xmm0, xmm0
0x180093e13  xorps   xmm1, xmm1
0x180093e16  movups  [rbp+0A0h+var_B8], xmm0
0x180093e1a  or      r8, 0FFFFFFFFFFFFFFFFh
0x180093e1e  movdqu  [rbp+0A0h+var_A8], xmm1
0x180093e23  inc     r8
0x180093e26  cmp     [rdi+r8*2], si
0x180093e2b  jnz     short loc_180093E23
0x180093e2d  mov     rdx, rdi
0x180093e30  lea     rcx, [rbp+0A0h+var_B8]
0x180093e34  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180093e39  lea     rdx, aHnsContainerNe; "HNS Container Networking"
0x180093e40  lea     rcx, [rbp+0A0h+var_B8]
0x180093e44  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x180093e49  lea     rdx, aDnsServerForwa; "DNS Server Forward Rule"
0x180093e50  mov     rbx, rax
0x180093e53  lea     rcx, [rbp+0A0h+var_B8]
0x180093e57  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x180093e5c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180093e60  jnz     short loc_180093E67
0x180093e62  cmp     rax, rbx
0x180093e65  jz      short loc_180093E9D
0x180093e67  mov     rdx, [r15+10h]
0x180093e6b  mov     rcx, [rsp+1A0h+var_170]
0x180093e70  call    cs:__imp_FWDeleteFirewallRule
0x180093e76  test    eax, eax
0x180093e78  jle     short loc_180093E82
0x180093e7a  movzx   eax, ax
0x180093e7d  or      eax, r12d
0x180093e80  test    eax, eax
0x180093e82  jz      short loc_180093E9A
0x180093e84  mov     r8d, eax; int
0x180093e87  lea     rcx, aRemovealldnsse; "RemoveAllDnsServerForCompartmentRules"
0x180093e8e  mov     edx, 578h; unsigned int
0x180093e93  call    ?TraceError@HNSTraceProvider@@SAXPEBDIJ@Z; HNSTraceProvider::TraceError(char const *,uint,long)
0x180093e98  jmp     short loc_180093E9D
0x180093e9a  inc     r13d
0x180093e9d  lea     rcx, [rbp+0A0h+var_B8]; void *
0x180093ea1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180093ea6  jmp     short loc_180093EAA
0x180093ea8  xor     esi, esi
0x180093eaa  mov     r15, [r15]
0x180093ead  test    r15, r15
0x180093eb0  jnz     loc_180093D2A
0x180093eb6  jmp     short loc_180093ED4
0x180093eb8  jle     short loc_180093EC0
0x180093eba  movzx   eax, ax
0x180093ebd  or      eax, r12d
0x180093ec0  mov     r8d, eax; int
0x180093ec3  lea     rcx, aRemovealldnsse; "RemoveAllDnsServerForCompartmentRules"
0x180093eca  mov     edx, 585h; unsigned int
0x180093ecf  call    ?TraceError@HNSTraceProvider@@SAXPEBDIJ@Z; HNSTraceProvider::TraceError(char const *,uint,long)
0x180093ed4  mov     rcx, cs:qword_1803982A8
0x180093edb  mov     eax, [rcx]
0x180093edd  cmp     eax, 5
0x180093ee0  jbe     short loc_180093F54
0x180093ee2  mov     rdx, [rcx+18h]
0x180093ee6  mov     r8, 400000000000h
0x180093ef0  mov     rax, [rcx+10h]
0x180093ef4  test    r8, rax
0x180093ef7  jz      short loc_180093F54
0x180093ef9  mov     rax, rdx
0x180093efc  and     rax, r8
0x180093eff  cmp     rax, rdx
0x180093f02  jnz     short loc_180093F54
0x180093f04  mov     edx, 4
0x180093f09  mov     [rsp+1A0h+var_164], r13d
0x180093f0e  lea     rax, [rsp+1A0h+var_164]
0x180093f13  mov     [rbp+0A0h+var_58], rdx
0x180093f17  mov     [rbp+0A0h+var_60], rax
0x180093f1b  xor     r9d, r9d
0x180093f1e  lea     rax, [rsp+1A0h+var_140]
0x180093f23  mov     [rsp+1A0h+var_140], 800h
0x180093f2c  mov     [rbp+0A0h+var_70], rax
0x180093f30  xor     r8d, r8d
0x180093f33  lea     rax, [rbp+0A0h+var_90]
0x180093f37  mov     [rbp+0A0h+var_68], 8
0x180093f3f  mov     [rsp+1A0h+var_178], rax
0x180093f44  mov     dword ptr [rsp+1A0h+var_180], edx
0x180093f48  lea     rdx, unk_18033467D
0x180093f4f  call    _tlgWriteTransfer_EventWriteTransfer
0x180093f54  mov     rcx, [rsp+1A0h+var_160]
0x180093f59  test    rcx, rcx
0x180093f5c  jz      short loc_180093F84
0x180093f5e  call    cs:__imp_FWFreeFirewallRules
0x180093f64  test    eax, eax
0x180093f66  jz      short loc_180093F84
0x180093f68  jle     short loc_180093F70
0x180093f6a  movzx   eax, ax
0x180093f6d  or      eax, r12d
0x180093f70  mov     r8d, eax; int
0x180093f73  lea     rcx, aRemovealldnsse; "RemoveAllDnsServerForCompartmentRules"
0x180093f7a  mov     edx, 594h; unsigned int
0x180093f7f  call    ?TraceError@HNSTraceProvider@@SAXPEBDIJ@Z; HNSTraceProvider::TraceError(char const *,uint,long)
0x180093f84  mov     rcx, [rsp+1A0h+var_170]
0x180093f89  test    rcx, rcx
0x180093f8c  jz      short loc_180093FB4
0x180093f8e  call    cs:__imp_FWClosePolicyStore
0x180093f94  test    eax, eax
0x180093f96  jz      short loc_180093FB4
0x180093f98  jle     short loc_180093FA0
0x180093f9a  movzx   eax, ax
0x180093f9d  or      eax, r12d
0x180093fa0  mov     r8d, eax; int
0x180093fa3  lea     rcx, aRemovealldnsse; "RemoveAllDnsServerForCompartmentRules"
0x180093faa  mov     edx, 59Dh; unsigned int
0x180093faf  call    ?TraceError@HNSTraceProvider@@SAXPEBDIJ@Z; HNSTraceProvider::TraceError(char const *,uint,long)
0x180093fb4  mov     edx, 5A1h; unsigned int
0x180093fb9  lea     rcx, aRemovealldnsse; "RemoveAllDnsServerForCompartmentRules"
0x180093fc0  call    ?TraceSuccess@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceSuccess(char const *,uint)
0x180093fc5  mov     rcx, [rbp+0A0h+var_50]
0x180093fc9  xor     rcx, rsp; StackCookie
0x180093fcc  call    __security_check_cookie
0x180093fd1  add     rsp, 168h
0x180093fd8  pop     r15
0x180093fda  pop     r14
0x180093fdc  pop     r13
0x180093fde  pop     r12
0x180093fe0  pop     rdi
0x180093fe1  pop     rsi
0x180093fe2  pop     rbx
0x180093fe3  pop     rbp
0x180093fe4  retn
```
