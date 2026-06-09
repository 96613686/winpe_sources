# FwMoneisDeleteInterfaceContainer

- ea: `0x18006267c`
- end: `0x180062ae3`
- name: `FwMoneisDeleteInterfaceContainer`
- size: `1127`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800bcae0`
- `0x1800c6bb0`

## callees

- `0x18000af3c`
- `0x18002f478`
- `0x180032080`
- `0x18003ca2c`
- `0x18003d5b0`
- `0x18006267c`
- `0x18006a41c`
- `0x18006f520`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800627e7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800627e7`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180062767`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180062767`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180062870`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180062870`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800628be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800628be`
- `fwbase!FwRegSetDWord` at `0x18006281c`
- `fwbase!FwRegSetDWord` at `0x18006281c`
- `fwbase!FwHResultToWindowsError` at `0x18006276f`
- `fwbase!FwHResultToWindowsError` at `0x1800628d2`
- `fwbase!FwHResultToWindowsError` at `0x18006291d`
- `fwbase!FwHResultToWindowsError` at `0x1800629d8`
- `fwbase!FwHResultToWindowsError` at `0x180062a25`
- `fwbase!FwHResultToWindowsError` at `0x18006276f`
- `fwbase!FwHResultToWindowsError` at `0x1800628d2`
- `fwbase!FwHResultToWindowsError` at `0x18006291d`
- `fwbase!FwHResultToWindowsError` at `0x1800629d8`
- `fwbase!FwHResultToWindowsError` at `0x180062a25`
- `FWPolicyIOMgr!FwFreeRules` at `0x1800629d0`
- `FWPolicyIOMgr!FwFreeRules` at `0x180062a1d`
- `FWPolicyIOMgr!FwFreeRules` at `0x1800629d0`
- `FWPolicyIOMgr!FwFreeRules` at `0x180062a1d`

## string_xrefs

- `0x18006280e`: `SYSTEM\CurrentControlSet\Services\mpssvc\Parameters\ACService`

## pseudocode

```c
__int64 __fastcall FwMoneisDeleteInterfaceContainer(__int64 a1, const IID *a2, const WCHAR *a3)
{
  struct _tag_FW_RULE *v5; // rdi
  unsigned int v7; // ebx
  unsigned int v8; // eax
  unsigned int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rsi
  unsigned __int32 v13; // ebx
  const unsigned __int16 *v15; // r14
  unsigned __int64 v16; // rsi
  OLECHAR *v17; // rax
  unsigned int v18; // eax
  unsigned int i; // esi
  void *v20; // r14
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  struct _tag_FW_RULE *v24; // [rsp+30h] [rbp-59h] BYREF
  void *v25; // [rsp+38h] [rbp-51h] BYREF
  void *v26; // [rsp+40h] [rbp-49h] BYREF
  void *v27[2]; // [rsp+48h] [rbp-41h]
  LPOLESTR lpsz; // [rsp+58h] [rbp-31h] BYREF
  int v29; // [rsp+60h] [rbp-29h] BYREF
  int v30; // [rsp+64h] [rbp-25h]
  __int128 *v31; // [rsp+68h] [rbp-21h]
  __int64 v32; // [rsp+70h] [rbp-19h]
  __int128 v33; // [rsp+78h] [rbp-11h] BYREF
  _DWORD v34[4]; // [rsp+88h] [rbp-1h] BYREF
  LPOLESTR v35; // [rsp+98h] [rbp+Fh]

  v29 = 545;
  lpsz = 0;
  v26 = 0;
  v25 = 0;
  ++g_invokedDeleteAllowEnterpriseIdRule;
  v30 = 1;
  v31 = 0;
  v33 = 0;
  v5 = 0;
  v24 = 0;
  v32 = 0x10000;
  FwMoneisOpenIfIsoStore(0, &v26);
  v7 = FwMoneisOpenIfIsoStore(2u, &v25);
  if ( v7 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 31, "A", v7);
    goto LABEL_42;
  }
  v27[0] = v25;
  v27[1] = v26;
  if ( a2 )
  {
    v8 = StringFromCLSID(a2, &lpsz);
    v9 = FwHResultToWindowsError(v8);
    v7 = v9;
    if ( v9 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v11 = 32;
        goto LABEL_47;
      }
      goto LABEL_42;
    }
LABEL_34:
    for ( i = 0; i < 2; ++i )
    {
      LODWORD(v33) = 1;
      *((_QWORD *)&v33 + 1) = v34;
      v31 = &v33;
      v35 = lpsz;
      v30 = 1;
      v34[0] = 8;
      v34[1] = 1;
      v20 = v27[i];
      v34[2] = 5;
      if ( v20 )
      {
        v21 = FwMoneisQueryRules(v20, (struct _tag_FW_QUERY *)&v29, &v24);
        v7 = v21;
        if ( v21 )
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 36, "A", v21);
          v5 = v24;
          goto LABEL_42;
        }
        v5 = v24;
        v9 = FwMoneisDeleteRules(v20, v24, 0);
        v7 = v9;
        if ( v9 )
        {
          v10 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v11 = 37;
            goto LABEL_47;
          }
          goto LABEL_42;
        }
        v22 = FwFreeRules(v5, 0);
        v9 = FwHResultToWindowsError(v22);
        v7 = v9;
        if ( v9 )
        {
          v10 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v11 = 38;
            goto LABEL_47;
          }
          goto LABEL_42;
        }
        v5 = 0;
        v24 = 0;
      }
    }
    if ( !v7 )
      goto LABEL_18;
    goto LABEL_42;
  }
  v12 = -1;
  if ( a1 )
  {
    if ( *((_DWORD *)gEnterpriseDomainProtectionManager + 13) )
    {
      if ( a3 )
      {
        if ( CompareStringOrdinal(a3, -1, L"EDPAllInterfacesContainerGroupIdzzz", -1, 1) == 2 )
        {
          v13 = _InterlockedExchangeAdd((volatile signed __int32 *)gEnterpriseDomainProtectionManager + 13, 0xFFFFFFFF);
          FwRegSetDWord(
            -2147483646,
            L"SYSTEM\\CurrentControlSet\\Services\\mpssvc\\Parameters\\ACService",
            L"TmpEdpAppHsviRefCnt",
            v13);
          if ( v13 )
          {
            v7 = 0;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 33, "A", 0);
            }
            goto LABEL_18;
          }
        }
      }
    }
  }
  v15 = L"AllInterfacesContainerGroupIdzzz";
  if ( a3 )
    v15 = a3;
  do
    ++v12;
  while ( v15[v12] );
  v16 = v12 + 1;
  v17 = (OLECHAR *)CoTaskMemAlloc(2 * v16);
  lpsz = v17;
  if ( !v17 )
  {
    v9 = FwHResultToWindowsError(2147942414LL);
    v7 = v9;
    if ( v9 )
    {
      v10 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v11 = 34;
        goto LABEL_47;
      }
      goto LABEL_42;
    }
    v17 = lpsz;
  }
  v18 = StringCchCopyW(v17, v16, v15);
  v9 = FwHResultToWindowsError(v18);
  v7 = v9;
  if ( !v9 )
    goto LABEL_34;
  v10 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v11 = 35;
    goto LABEL_47;
  }
LABEL_42:
  while ( 1 )
  {
    ++g_failedDeleteAllowEnterpriseIdRule;
    if ( !v5 )
      break;
    v23 = FwFreeRules(v5, 0);
    v9 = FwHResultToWindowsError(v23);
    v7 = v9;
    if ( !v9 )
      break;
    v10 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v11 = 39;
LABEL_47:
      WPP_SF_d(*(_QWORD *)(v10 + 16), v11, "A", v9);
    }
  }
LABEL_18:
  FwMoneisCloseStores(&v26, &v25);
  if ( lpsz )
    CoTaskMemFree(lpsz);
  return v7;
}

```

## disassembly

```asm
0x18006267c  mov     [rsp-8+arg_0], rbx
0x180062681  push    rbp
0x180062682  push    rsi
0x180062683  push    rdi
0x180062684  push    r12
0x180062686  push    r13
0x180062688  push    r14
0x18006268a  push    r15
0x18006268c  lea     rbp, [rsp-27h]
0x180062691  sub     rsp, 0B0h
0x180062698  mov     rax, cs:__security_cookie
0x18006269f  xor     rax, rsp
0x1800626a2  mov     [rbp+57h+var_40], rax
0x1800626a6  xor     r12d, r12d
0x1800626a9  mov     [rbp+57h+var_80], 221h
0x1800626b0  mov     rsi, rdx
0x1800626b3  mov     [rbp+57h+lpsz], r12
0x1800626b7  mov     r14, rcx
0x1800626ba  mov     [rbp+57h+var_A0], r12
0x1800626be  mov     r13d, 1
0x1800626c4  mov     [rbp+57h+var_A8], r12
0x1800626c8  add     cs:g_invokedDeleteAllowEnterpriseIdRule, r13
0x1800626cf  lea     rdx, [rbp+57h+var_A0]; void **
0x1800626d3  xorps   xmm0, xmm0
0x1800626d6  mov     [rbp+57h+var_7C], r13d
0x1800626da  xor     ecx, ecx; unsigned int
0x1800626dc  mov     [rbp+57h+var_78], r12
0x1800626e0  movups  [rbp+57h+var_68], xmm0
0x1800626e4  mov     edi, r12d
0x1800626e7  mov     [rbp+57h+var_B0], r12
0x1800626eb  mov     r15, r8
0x1800626ee  mov     [rbp+57h+var_70], 10000h
0x1800626f6  call    ?FwMoneisOpenIfIsoStore@@YAKKPEAPEAX@Z; FwMoneisOpenIfIsoStore(ulong,void * *)
0x1800626fb  lea     rdx, [rbp+57h+var_A8]; void **
0x1800626ff  lea     ecx, [r13+1]; unsigned int
0x180062703  call    ?FwMoneisOpenIfIsoStore@@YAKKPEAPEAX@Z; FwMoneisOpenIfIsoStore(ulong,void * *)
0x180062708  mov     ebx, eax
0x18006270a  lea     rax, WPP_GLOBAL_Control
0x180062711  test    ebx, ebx
0x180062713  jz      short loc_18006274B
0x180062715  mov     rcx, cs:WPP_GLOBAL_Control
0x18006271c  cmp     rcx, rax
0x18006271f  jz      loc_180062A01
0x180062725  test    [rcx+1Ch], r13b
0x180062729  jz      loc_180062A01
0x18006272f  mov     rcx, [rcx+10h]
0x180062733  lea     edx, [r13+1Eh]
0x180062737  mov     r9d, ebx
0x18006273a  lea     r8, WPP_e0d30041b2973bba096172aea683b919_Traceguids; "A"
0x180062741  call    WPP_SF_d
0x180062746  jmp     loc_180062A01
0x18006274b  mov     rax, [rbp+57h+var_A8]
0x18006274f  mov     [rbp+57h+var_98], rax
0x180062753  mov     rax, [rbp+57h+var_A0]
0x180062757  mov     [rbp+57h+var_90], rax
0x18006275b  test    rsi, rsi
0x18006275e  jz      short loc_1800627AA
0x180062760  lea     rdx, [rbp+57h+lpsz]; lplpsz
0x180062764  mov     rcx, rsi; rclsid
0x180062767  call    cs:__imp_StringFromCLSID
0x18006276d  mov     ecx, eax
0x18006276f  call    cs:__imp_FwHResultToWindowsError
0x180062775  mov     ebx, eax
0x180062777  test    eax, eax
0x180062779  jz      loc_180062954
0x18006277f  mov     rcx, cs:WPP_GLOBAL_Control
0x180062786  lea     rsi, WPP_GLOBAL_Control
0x18006278d  cmp     rcx, rsi
0x180062790  jz      loc_180062A08
0x180062796  test    [rcx+1Ch], r13b
0x18006279a  jz      loc_180062A08
0x1800627a0  mov     edx, 20h ; ' '
0x1800627a5  jmp     loc_180062A4C
0x1800627aa  mov     rax, cs:?gEnterpriseDomainProtectionManager@@3V?$unique_ptr@VEnterpriseDomainProtection@appIsolation@@U?$default_delete@VEnterpriseDomainProtection@appIsolation@@@wistd@@@wistd@@A; wistd::unique_ptr<appIsolation::EnterpriseDomainProtection,wistd::default_delete<appIsolation::EnterpriseDomainProtection>> gEnterpriseDomainProtectionManager
0x1800627b1  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800627b5  mov     ecx, [rax+34h]
0x1800627b8  nop
0x1800627b9  test    r14, r14
0x1800627bc  jz      loc_18006289F
0x1800627c2  test    ecx, ecx
0x1800627c4  jz      loc_18006289F
0x1800627ca  test    r15, r15
0x1800627cd  jz      loc_18006289F
0x1800627d3  mov     r9d, esi; cchCount2
0x1800627d6  mov     [rsp+0E0h+bIgnoreCase], r13d; bIgnoreCase
0x1800627db  lea     r8, aEdpallinterfac; "EDPAllInterfacesContainerGroupIdzzz"
0x1800627e2  mov     edx, esi; cchCount1
0x1800627e4  mov     rcx, r15; lpString1
0x1800627e7  call    cs:__imp_CompareStringOrdinal
0x1800627ed  cmp     eax, 2
0x1800627f0  jnz     loc_18006289F
0x1800627f6  mov     rax, cs:?gEnterpriseDomainProtectionManager@@3V?$unique_ptr@VEnterpriseDomainProtection@appIsolation@@U?$default_delete@VEnterpriseDomainProtection@appIsolation@@@wistd@@@wistd@@A; wistd::unique_ptr<appIsolation::EnterpriseDomainProtection,wistd::default_delete<appIsolation::EnterpriseDomainProtection>> gEnterpriseDomainProtectionManager
0x1800627fd  mov     ebx, esi
0x1800627ff  lock xadd [rax+34h], ebx
0x180062804  mov     r9d, ebx
0x180062807  lea     r8, aTmpedpapphsvir; "TmpEdpAppHsviRefCnt"
0x18006280e  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Services\\mp"...
0x180062815  mov     rcx, 0FFFFFFFF80000002h
0x18006281c  call    cs:__imp_FwRegSetDWord
0x180062822  test    ebx, ebx
0x180062824  jz      short loc_18006289F
0x180062826  mov     ebx, r12d
0x180062829  mov     rcx, cs:WPP_GLOBAL_Control
0x180062830  lea     rsi, WPP_GLOBAL_Control
0x180062837  cmp     rcx, rsi
0x18006283a  jz      short loc_18006285A
0x18006283c  test    [rcx+1Ch], r13b
0x180062840  jz      short loc_18006285A
0x180062842  mov     rcx, [rcx+10h]
0x180062846  lea     r8, WPP_e0d30041b2973bba096172aea683b919_Traceguids; "A"
0x18006284d  mov     edx, 21h ; '!'
0x180062852  xor     r9d, r9d
0x180062855  call    WPP_SF_d
0x18006285a  lea     rdx, [rbp+57h+var_A8]; void **
0x18006285e  lea     rcx, [rbp+57h+var_A0]; void **
0x180062862  call    ?FwMoneisCloseStores@@YAXPEAPEAX0@Z; FwMoneisCloseStores(void * *,void * *)
0x180062867  mov     rcx, [rbp+57h+lpsz]; pv
0x18006286b  test    rcx, rcx
0x18006286e  jz      short loc_180062876
0x180062870  call    cs:__imp_CoTaskMemFree
0x180062876  mov     eax, ebx
0x180062878  mov     rcx, [rbp+57h+var_40]
0x18006287c  xor     rcx, rsp; StackCookie
0x18006287f  call    __security_check_cookie
0x180062884  mov     rbx, [rsp+0E0h+arg_0]
0x18006288c  add     rsp, 0B0h
0x180062893  pop     r15
0x180062895  pop     r14
0x180062897  pop     r13
0x180062899  pop     r12
0x18006289b  pop     rdi
0x18006289c  pop     rsi
0x18006289d  pop     rbp
0x18006289e  retn
0x18006289f  test    r15, r15
0x1800628a2  lea     r14, aAllinterfacesc; "AllInterfacesContainerGroupIdzzz"
0x1800628a9  cmovnz  r14, r15
0x1800628ad  inc     rsi
0x1800628b0  cmp     [r14+rsi*2], r12w
0x1800628b5  jnz     short loc_1800628AD
0x1800628b7  inc     rsi
0x1800628ba  lea     rcx, [rsi+rsi]; cb
0x1800628be  call    cs:__imp_CoTaskMemAlloc
0x1800628c4  mov     [rbp+57h+lpsz], rax
0x1800628c8  test    rax, rax
0x1800628cb  jnz     short loc_18006290D
0x1800628cd  mov     ecx, 8007000Eh
0x1800628d2  call    cs:__imp_FwHResultToWindowsError
0x1800628d8  mov     ebx, eax
0x1800628da  test    eax, eax
0x1800628dc  jz      short loc_180062909
0x1800628de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800628e5  lea     rsi, WPP_GLOBAL_Control
0x1800628ec  cmp     rcx, rsi
0x1800628ef  jz      loc_180062A08
0x1800628f5  test    [rcx+1Ch], r13b
0x1800628f9  jz      loc_180062A08
0x1800628ff  mov     edx, 22h ; '"'
0x180062904  jmp     loc_180062A4C
0x180062909  mov     rax, [rbp+57h+lpsz]
0x18006290d  mov     r8, r14; unsigned __int16 *
0x180062910  mov     rdx, rsi; unsigned __int64
0x180062913  mov     rcx, rax; unsigned __int16 *
0x180062916  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006291b  mov     ecx, eax
0x18006291d  call    cs:__imp_FwHResultToWindowsError
0x180062923  mov     ebx, eax
0x180062925  test    eax, eax
0x180062927  jz      short loc_180062954
0x180062929  mov     rcx, cs:WPP_GLOBAL_Control
0x180062930  lea     rsi, WPP_GLOBAL_Control
0x180062937  cmp     rcx, rsi
0x18006293a  jz      loc_180062A08
0x180062940  test    [rcx+1Ch], r13b
0x180062944  jz      loc_180062A08
0x18006294a  mov     edx, 23h ; '#'
0x18006294f  jmp     loc_180062A4C
0x180062954  mov     esi, r12d
0x180062957  lea     rax, [rbp+57h+var_58]
0x18006295b  mov     dword ptr [rbp+57h+var_68], r13d
0x18006295f  mov     qword ptr [rbp+57h+var_68+8], rax
0x180062963  lea     rax, [rbp+57h+var_68]
0x180062967  mov     [rbp+57h+var_78], rax
0x18006296b  mov     rax, [rbp+57h+lpsz]
0x18006296f  mov     [rbp+57h+var_48], rax
0x180062973  mov     eax, esi
0x180062975  mov     [rbp+57h+var_7C], r13d
0x180062979  mov     [rbp+57h+var_58], 8
0x180062980  mov     [rbp+57h+var_54], r13d
0x180062984  mov     r14, [rbp+rax*8+57h+var_98]
0x180062989  mov     [rbp+57h+var_50], 5
0x180062990  test    r14, r14
0x180062993  jz      short loc_1800629EB
0x180062995  lea     r8, [rbp+57h+var_B0]; struct _tag_FW_RULE **
0x180062999  mov     rcx, r14; void *
0x18006299c  lea     rdx, [rbp+57h+var_80]; struct _tag_FW_QUERY *
0x1800629a0  call    ?FwMoneisQueryRules@@YAKPEAXPEAU_tag_FW_QUERY@@PEAPEAU_tag_FW_RULE@@@Z; FwMoneisQueryRules(void *,_tag_FW_QUERY *,_tag_FW_RULE * *)
0x1800629a5  mov     ebx, eax
0x1800629a7  test    eax, eax
0x1800629a9  jnz     loc_180062AA9
0x1800629af  mov     rdi, [rbp+57h+var_B0]
0x1800629b3  xor     r8d, r8d; unsigned __int16 *
0x1800629b6  mov     rdx, rdi; struct _tag_FW_RULE *
0x1800629b9  mov     rcx, r14; void *
0x1800629bc  call    ?FwMoneisDeleteRules@@YAKPEAXPEAU_tag_FW_RULE@@PEBG@Z; FwMoneisDeleteRules(void *,_tag_FW_RULE *,ushort const *)
0x1800629c1  mov     ebx, eax
0x1800629c3  test    eax, eax
0x1800629c5  jnz     loc_180062A81
0x1800629cb  xor     edx, edx
0x1800629cd  mov     rcx, rdi
0x1800629d0  call    cs:__imp_FwFreeRules
0x1800629d6  mov     ecx, eax
0x1800629d8  call    cs:__imp_FwHResultToWindowsError
0x1800629de  mov     ebx, eax
0x1800629e0  test    eax, eax
0x1800629e2  jnz     short loc_180062A61
0x1800629e4  mov     rdi, r12
0x1800629e7  mov     [rbp+57h+var_B0], r12
0x1800629eb  add     esi, r13d
0x1800629ee  mov     eax, ebx
0x1800629f0  cmp     esi, 2
0x1800629f3  jb      loc_180062957
0x1800629f9  test    eax, eax
0x1800629fb  jz      loc_18006285A
0x180062a01  lea     rsi, WPP_GLOBAL_Control
0x180062a08  add     cs:g_failedDeleteAllowEnterpriseIdRule, r13
0x180062a0f  test    rdi, rdi
0x180062a12  jz      loc_18006285A
0x180062a18  xor     edx, edx
0x180062a1a  mov     rcx, rdi
0x180062a1d  call    cs:__imp_FwFreeRules
0x180062a23  mov     ecx, eax
0x180062a25  call    cs:__imp_FwHResultToWindowsError
0x180062a2b  mov     ebx, eax
0x180062a2d  test    eax, eax
0x180062a2f  jz      loc_18006285A
0x180062a35  mov     rcx, cs:WPP_GLOBAL_Control
0x180062a3c  cmp     rcx, rsi
0x180062a3f  jz      short loc_180062A08
0x180062a41  test    [rcx+1Ch], r13b
0x180062a45  jz      short loc_180062A08
0x180062a47  mov     edx, 27h ; '''
0x180062a4c  mov     rcx, [rcx+10h]
0x180062a50  lea     r8, WPP_e0d30041b2973bba096172aea683b919_Traceguids; "A"
0x180062a57  mov     r9d, eax
0x180062a5a  call    WPP_SF_d
0x180062a5f  jmp     short loc_180062A08
0x180062a61  mov     rcx, cs:WPP_GLOBAL_Control
0x180062a68  lea     rsi, WPP_GLOBAL_Control
0x180062a6f  cmp     rcx, rsi
0x180062a72  jz      short loc_180062A08
0x180062a74  test    [rcx+1Ch], r13b
0x180062a78  jz      short loc_180062A08
0x180062a7a  mov     edx, 26h ; '&'
0x180062a7f  jmp     short loc_180062A4C
0x180062a81  mov     rcx, cs:WPP_GLOBAL_Control
0x180062a88  lea     rsi, WPP_GLOBAL_Control
0x180062a8f  cmp     rcx, rsi
0x180062a92  jz      loc_180062A08
0x180062a98  test    [rcx+1Ch], r13b
0x180062a9c  jz      loc_180062A08
0x180062aa2  mov     edx, 25h ; '%'
0x180062aa7  jmp     short loc_180062A4C
0x180062aa9  mov     rcx, cs:WPP_GLOBAL_Control
0x180062ab0  lea     rsi, WPP_GLOBAL_Control
0x180062ab7  cmp     rcx, rsi
0x180062aba  jz      short loc_180062ADA
0x180062abc  test    [rcx+1Ch], r13b
0x180062ac0  jz      short loc_180062ADA
0x180062ac2  mov     rcx, [rcx+10h]
0x180062ac6  lea     r8, WPP_e0d30041b2973bba096172aea683b919_Traceguids; "A"
0x180062acd  mov     edx, 24h ; '$'
0x180062ad2  mov     r9d, eax
0x180062ad5  call    WPP_SF_d
0x180062ada  mov     rdi, [rbp+57h+var_B0]
0x180062ade  jmp     loc_180062A08
```
