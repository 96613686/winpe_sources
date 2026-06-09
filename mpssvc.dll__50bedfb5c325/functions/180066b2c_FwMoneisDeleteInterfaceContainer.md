# FwMoneisDeleteInterfaceContainer

- ea: `0x180066b2c`
- end: `0x180066fe4`
- name: `FwMoneisDeleteInterfaceContainer`
- size: `1208`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800c3ea0`
- `0x1800ce0b0`

## callees

- `0x18000a710`
- `0x180034660`
- `0x180036220`
- `0x18003cfe0`
- `0x18003d990`
- `0x180066b2c`
- `0x18006d210`
- `0x1800729c0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180066ca3`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180066ca3`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180066c17`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180066c17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066d3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180066d3c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180066d91`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180066d91`
- `fwbase!FwHResultToWindowsError` at `0x180066c25`
- `fwbase!FwHResultToWindowsError` at `0x180066dab`
- `fwbase!FwHResultToWindowsError` at `0x180066dfc`
- `fwbase!FwHResultToWindowsError` at `0x180066ec3`
- `fwbase!FwHResultToWindowsError` at `0x180066f20`
- `fwbase!FwHResultToWindowsError` at `0x180066c25`
- `fwbase!FwHResultToWindowsError` at `0x180066dab`
- `fwbase!FwHResultToWindowsError` at `0x180066dfc`
- `fwbase!FwHResultToWindowsError` at `0x180066ec3`
- `fwbase!FwHResultToWindowsError` at `0x180066f20`
- `fwbase!FwRegSetDWord` at `0x180066cde`
- `fwbase!FwRegSetDWord` at `0x180066cde`
- `FWPolicyIOMgr!FwFreeRules` at `0x180066eb5`
- `FWPolicyIOMgr!FwFreeRules` at `0x180066f12`
- `FWPolicyIOMgr!FwFreeRules` at `0x180066eb5`
- `FWPolicyIOMgr!FwFreeRules` at `0x180066f12`

## string_xrefs

- `0x180066cd0`: `SYSTEM\CurrentControlSet\Services\mpssvc\Parameters\ACService`

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
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 31, WPP_c1b1b84f9be43d56c172dc8519c16790_Traceguids, v7);
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
            WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 36, WPP_c1b1b84f9be43d56c172dc8519c16790_Traceguids, v21);
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
              WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 33, WPP_c1b1b84f9be43d56c172dc8519c16790_Traceguids, 0);
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
      WPP_SF_d(*(_QWORD *)(v10 + 16), v11, WPP_c1b1b84f9be43d56c172dc8519c16790_Traceguids, v9);
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
0x180066b2c  mov     [rsp-8+arg_0], rbx
0x180066b31  push    rbp
0x180066b32  push    rsi
0x180066b33  push    rdi
0x180066b34  push    r12
0x180066b36  push    r13
0x180066b38  push    r14
0x180066b3a  push    r15
0x180066b3c  lea     rbp, [rsp-27h]
0x180066b41  sub     rsp, 0B0h
0x180066b48  mov     rax, cs:__security_cookie
0x180066b4f  xor     rax, rsp
0x180066b52  mov     [rbp+57h+var_40], rax
0x180066b56  xor     r12d, r12d
0x180066b59  mov     [rbp+57h+var_80], 221h
0x180066b60  mov     rsi, rdx
0x180066b63  mov     [rbp+57h+lpsz], r12
0x180066b67  mov     r14, rcx
0x180066b6a  mov     [rbp+57h+var_A0], r12
0x180066b6e  mov     r13d, 1
0x180066b74  mov     [rbp+57h+var_A8], r12
0x180066b78  add     cs:g_invokedDeleteAllowEnterpriseIdRule, r13
0x180066b7f  lea     rdx, [rbp+57h+var_A0]; void **
0x180066b83  xorps   xmm0, xmm0
0x180066b86  mov     [rbp+57h+var_7C], r13d
0x180066b8a  xor     ecx, ecx; unsigned int
0x180066b8c  mov     [rbp+57h+var_78], r12
0x180066b90  movups  [rbp+57h+var_68], xmm0
0x180066b94  mov     edi, r12d
0x180066b97  mov     [rbp+57h+var_B0], r12
0x180066b9b  mov     r15, r8
0x180066b9e  mov     [rbp+57h+var_70], 10000h
0x180066ba6  call    ?FwMoneisOpenIfIsoStore@@YAKKPEAPEAX@Z; FwMoneisOpenIfIsoStore(ulong,void * *)
0x180066bab  lea     rdx, [rbp+57h+var_A8]; void **
0x180066baf  lea     ecx, [r13+1]; unsigned int
0x180066bb3  call    ?FwMoneisOpenIfIsoStore@@YAKKPEAPEAX@Z; FwMoneisOpenIfIsoStore(ulong,void * *)
0x180066bb8  mov     ebx, eax
0x180066bba  lea     rax, WPP_GLOBAL_Control
0x180066bc1  test    ebx, ebx
0x180066bc3  jz      short loc_180066BFB
0x180066bc5  mov     rcx, cs:WPP_GLOBAL_Control
0x180066bcc  cmp     rcx, rax
0x180066bcf  jz      loc_180066EF6
0x180066bd5  test    [rcx+1Ch], r13b
0x180066bd9  jz      loc_180066EF6
0x180066bdf  mov     rcx, [rcx+10h]
0x180066be3  lea     edx, [r13+1Eh]
0x180066be7  mov     r9d, ebx
0x180066bea  lea     r8, WPP_c1b1b84f9be43d56c172dc8519c16790_Traceguids
0x180066bf1  call    WPP_SF_d
0x180066bf6  jmp     loc_180066EF6
0x180066bfb  mov     rax, [rbp+57h+var_A8]
0x180066bff  mov     [rbp+57h+var_98], rax
0x180066c03  mov     rax, [rbp+57h+var_A0]
0x180066c07  mov     [rbp+57h+var_90], rax
0x180066c0b  test    rsi, rsi
0x180066c0e  jz      short loc_180066C66
0x180066c10  lea     rdx, [rbp+57h+lpsz]; lplpsz
0x180066c14  mov     rcx, rsi; rclsid
0x180066c17  call    cs:__imp_StringFromCLSID
0x180066c1e  nop     dword ptr [rax+rax+00h]
0x180066c23  mov     ecx, eax
0x180066c25  call    cs:__imp_FwHResultToWindowsError
0x180066c2c  nop     dword ptr [rax+rax+00h]
0x180066c31  mov     ebx, eax
0x180066c33  test    eax, eax
0x180066c35  jz      loc_180066E39
0x180066c3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180066c42  lea     rsi, WPP_GLOBAL_Control
0x180066c49  cmp     rcx, rsi
0x180066c4c  jz      loc_180066EFD
0x180066c52  test    [rcx+1Ch], r13b
0x180066c56  jz      loc_180066EFD
0x180066c5c  mov     edx, 20h ; ' '
0x180066c61  jmp     loc_180066F4D
0x180066c66  mov     rax, cs:?gEnterpriseDomainProtectionManager@@3V?$unique_ptr@VEnterpriseDomainProtection@appIsolation@@U?$default_delete@VEnterpriseDomainProtection@appIsolation@@@wistd@@@wistd@@A; wistd::unique_ptr<appIsolation::EnterpriseDomainProtection,wistd::default_delete<appIsolation::EnterpriseDomainProtection>> gEnterpriseDomainProtectionManager
0x180066c6d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180066c71  mov     ecx, [rax+34h]
0x180066c74  nop
0x180066c75  test    r14, r14
0x180066c78  jz      loc_180066D72
0x180066c7e  test    ecx, ecx
0x180066c80  jz      loc_180066D72
0x180066c86  test    r15, r15
0x180066c89  jz      loc_180066D72
0x180066c8f  mov     r9d, esi; cchCount2
0x180066c92  mov     [rsp+0E0h+bIgnoreCase], r13d; bIgnoreCase
0x180066c97  lea     r8, aEdpallinterfac; "EDPAllInterfacesContainerGroupIdzzz"
0x180066c9e  mov     edx, esi; cchCount1
0x180066ca0  mov     rcx, r15; lpString1
0x180066ca3  call    cs:__imp_CompareStringOrdinal
0x180066caa  nop     dword ptr [rax+rax+00h]
0x180066caf  cmp     eax, 2
0x180066cb2  jnz     loc_180066D72
0x180066cb8  mov     rax, cs:?gEnterpriseDomainProtectionManager@@3V?$unique_ptr@VEnterpriseDomainProtection@appIsolation@@U?$default_delete@VEnterpriseDomainProtection@appIsolation@@@wistd@@@wistd@@A; wistd::unique_ptr<appIsolation::EnterpriseDomainProtection,wistd::default_delete<appIsolation::EnterpriseDomainProtection>> gEnterpriseDomainProtectionManager
0x180066cbf  mov     ebx, esi
0x180066cc1  lock xadd [rax+34h], ebx
0x180066cc6  mov     r9d, ebx
0x180066cc9  lea     r8, aTmpedpapphsvir; "TmpEdpAppHsviRefCnt"
0x180066cd0  lea     rdx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Services\\mp"...
0x180066cd7  mov     rcx, 0FFFFFFFF80000002h
0x180066cde  call    cs:__imp_FwRegSetDWord
0x180066ce5  nop     dword ptr [rax+rax+00h]
0x180066cea  test    ebx, ebx
0x180066cec  jz      loc_180066D72
0x180066cf2  mov     ebx, r12d
0x180066cf5  mov     rcx, cs:WPP_GLOBAL_Control
0x180066cfc  lea     rsi, WPP_GLOBAL_Control
0x180066d03  cmp     rcx, rsi
0x180066d06  jz      short loc_180066D26
0x180066d08  test    [rcx+1Ch], r13b
0x180066d0c  jz      short loc_180066D26
0x180066d0e  mov     rcx, [rcx+10h]
0x180066d12  lea     r8, WPP_c1b1b84f9be43d56c172dc8519c16790_Traceguids
0x180066d19  mov     edx, 21h ; '!'
0x180066d1e  xor     r9d, r9d
0x180066d21  call    WPP_SF_d
0x180066d26  lea     rdx, [rbp+57h+var_A8]; void **
0x180066d2a  lea     rcx, [rbp+57h+var_A0]; void **
0x180066d2e  call    ?FwMoneisCloseStores@@YAXPEAPEAX0@Z; FwMoneisCloseStores(void * *,void * *)
0x180066d33  mov     rcx, [rbp+57h+lpsz]; pv
0x180066d37  test    rcx, rcx
0x180066d3a  jz      short loc_180066D48
0x180066d3c  call    cs:__imp_CoTaskMemFree
0x180066d43  nop     dword ptr [rax+rax+00h]
0x180066d48  mov     eax, ebx
0x180066d4a  mov     rcx, [rbp+57h+var_40]
0x180066d4e  xor     rcx, rsp; StackCookie
0x180066d51  call    __security_check_cookie
0x180066d56  mov     rbx, [rsp+0E0h+arg_0]
0x180066d5e  add     rsp, 0B0h
0x180066d65  pop     r15
0x180066d67  pop     r14
0x180066d69  pop     r13
0x180066d6b  pop     r12
0x180066d6d  pop     rdi
0x180066d6e  pop     rsi
0x180066d6f  pop     rbp
0x180066d70  retn
0x180066d72  test    r15, r15
0x180066d75  lea     r14, aAllinterfacesc; "AllInterfacesContainerGroupIdzzz"
0x180066d7c  cmovnz  r14, r15
0x180066d80  inc     rsi
0x180066d83  cmp     [r14+rsi*2], r12w
0x180066d88  jnz     short loc_180066D80
0x180066d8a  inc     rsi
0x180066d8d  lea     rcx, [rsi+rsi]; cb
0x180066d91  call    cs:__imp_CoTaskMemAlloc
0x180066d98  nop     dword ptr [rax+rax+00h]
0x180066d9d  mov     [rbp+57h+lpsz], rax
0x180066da1  test    rax, rax
0x180066da4  jnz     short loc_180066DEC
0x180066da6  mov     ecx, 8007000Eh
0x180066dab  call    cs:__imp_FwHResultToWindowsError
0x180066db2  nop     dword ptr [rax+rax+00h]
0x180066db7  mov     ebx, eax
0x180066db9  test    eax, eax
0x180066dbb  jz      short loc_180066DE8
0x180066dbd  mov     rcx, cs:WPP_GLOBAL_Control
0x180066dc4  lea     rsi, WPP_GLOBAL_Control
0x180066dcb  cmp     rcx, rsi
0x180066dce  jz      loc_180066EFD
0x180066dd4  test    [rcx+1Ch], r13b
0x180066dd8  jz      loc_180066EFD
0x180066dde  mov     edx, 22h ; '"'
0x180066de3  jmp     loc_180066F4D
0x180066de8  mov     rax, [rbp+57h+lpsz]
0x180066dec  mov     r8, r14; unsigned __int16 *
0x180066def  mov     rdx, rsi; unsigned __int64
0x180066df2  mov     rcx, rax; unsigned __int16 *
0x180066df5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180066dfa  mov     ecx, eax
0x180066dfc  call    cs:__imp_FwHResultToWindowsError
0x180066e03  nop     dword ptr [rax+rax+00h]
0x180066e08  mov     ebx, eax
0x180066e0a  test    eax, eax
0x180066e0c  jz      short loc_180066E39
0x180066e0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180066e15  lea     rsi, WPP_GLOBAL_Control
0x180066e1c  cmp     rcx, rsi
0x180066e1f  jz      loc_180066EFD
0x180066e25  test    [rcx+1Ch], r13b
0x180066e29  jz      loc_180066EFD
0x180066e2f  mov     edx, 23h ; '#'
0x180066e34  jmp     loc_180066F4D
0x180066e39  mov     esi, r12d
0x180066e3c  lea     rax, [rbp+57h+var_58]
0x180066e40  mov     dword ptr [rbp+57h+var_68], r13d
0x180066e44  mov     qword ptr [rbp+57h+var_68+8], rax
0x180066e48  lea     rax, [rbp+57h+var_68]
0x180066e4c  mov     [rbp+57h+var_78], rax
0x180066e50  mov     rax, [rbp+57h+lpsz]
0x180066e54  mov     [rbp+57h+var_48], rax
0x180066e58  mov     eax, esi
0x180066e5a  mov     [rbp+57h+var_7C], r13d
0x180066e5e  mov     [rbp+57h+var_58], 8
0x180066e65  mov     [rbp+57h+var_54], r13d
0x180066e69  mov     r14, [rbp+rax*8+57h+var_98]
0x180066e6e  mov     [rbp+57h+var_50], 5
0x180066e75  test    r14, r14
0x180066e78  jz      short loc_180066EE0
0x180066e7a  lea     r8, [rbp+57h+var_B0]; struct _tag_FW_RULE **
0x180066e7e  mov     rcx, r14; void *
0x180066e81  lea     rdx, [rbp+57h+var_80]; struct _tag_FW_QUERY *
0x180066e85  call    ?FwMoneisQueryRules@@YAKPEAXPEAU_tag_FW_QUERY@@PEAPEAU_tag_FW_RULE@@@Z; FwMoneisQueryRules(void *,_tag_FW_QUERY *,_tag_FW_RULE * *)
0x180066e8a  mov     ebx, eax
0x180066e8c  test    eax, eax
0x180066e8e  jnz     loc_180066FAA
0x180066e94  mov     rdi, [rbp+57h+var_B0]
0x180066e98  xor     r8d, r8d; unsigned __int16 *
0x180066e9b  mov     rdx, rdi; struct _tag_FW_RULE *
0x180066e9e  mov     rcx, r14; void *
0x180066ea1  call    ?FwMoneisDeleteRules@@YAKPEAXPEAU_tag_FW_RULE@@PEBG@Z; FwMoneisDeleteRules(void *,_tag_FW_RULE *,ushort const *)
0x180066ea6  mov     ebx, eax
0x180066ea8  test    eax, eax
0x180066eaa  jnz     loc_180066F82
0x180066eb0  xor     edx, edx
0x180066eb2  mov     rcx, rdi
0x180066eb5  call    cs:__imp_FwFreeRules
0x180066ebc  nop     dword ptr [rax+rax+00h]
0x180066ec1  mov     ecx, eax
0x180066ec3  call    cs:__imp_FwHResultToWindowsError
0x180066eca  nop     dword ptr [rax+rax+00h]
0x180066ecf  mov     ebx, eax
0x180066ed1  test    eax, eax
0x180066ed3  jnz     loc_180066F62
0x180066ed9  mov     rdi, r12
0x180066edc  mov     [rbp+57h+var_B0], r12
0x180066ee0  add     esi, r13d
0x180066ee3  mov     eax, ebx
0x180066ee5  cmp     esi, 2
0x180066ee8  jb      loc_180066E3C
0x180066eee  test    eax, eax
0x180066ef0  jz      loc_180066D26
0x180066ef6  lea     rsi, WPP_GLOBAL_Control
0x180066efd  add     cs:g_failedDeleteAllowEnterpriseIdRule, r13
0x180066f04  test    rdi, rdi
0x180066f07  jz      loc_180066D26
0x180066f0d  xor     edx, edx
0x180066f0f  mov     rcx, rdi
0x180066f12  call    cs:__imp_FwFreeRules
0x180066f19  nop     dword ptr [rax+rax+00h]
0x180066f1e  mov     ecx, eax
0x180066f20  call    cs:__imp_FwHResultToWindowsError
0x180066f27  nop     dword ptr [rax+rax+00h]
0x180066f2c  mov     ebx, eax
0x180066f2e  test    eax, eax
0x180066f30  jz      loc_180066D26
0x180066f36  mov     rcx, cs:WPP_GLOBAL_Control
0x180066f3d  cmp     rcx, rsi
0x180066f40  jz      short loc_180066EFD
0x180066f42  test    [rcx+1Ch], r13b
0x180066f46  jz      short loc_180066EFD
0x180066f48  mov     edx, 27h ; '''
0x180066f4d  mov     rcx, [rcx+10h]
0x180066f51  lea     r8, WPP_c1b1b84f9be43d56c172dc8519c16790_Traceguids
0x180066f58  mov     r9d, eax
0x180066f5b  call    WPP_SF_d
0x180066f60  jmp     short loc_180066EFD
0x180066f62  mov     rcx, cs:WPP_GLOBAL_Control
0x180066f69  lea     rsi, WPP_GLOBAL_Control
0x180066f70  cmp     rcx, rsi
0x180066f73  jz      short loc_180066EFD
0x180066f75  test    [rcx+1Ch], r13b
0x180066f79  jz      short loc_180066EFD
0x180066f7b  mov     edx, 26h ; '&'
0x180066f80  jmp     short loc_180066F4D
0x180066f82  mov     rcx, cs:WPP_GLOBAL_Control
0x180066f89  lea     rsi, WPP_GLOBAL_Control
0x180066f90  cmp     rcx, rsi
0x180066f93  jz      loc_180066EFD
0x180066f99  test    [rcx+1Ch], r13b
0x180066f9d  jz      loc_180066EFD
0x180066fa3  mov     edx, 25h ; '%'
0x180066fa8  jmp     short loc_180066F4D
0x180066faa  mov     rcx, cs:WPP_GLOBAL_Control
0x180066fb1  lea     rsi, WPP_GLOBAL_Control
0x180066fb8  cmp     rcx, rsi
0x180066fbb  jz      short loc_180066FDB
0x180066fbd  test    [rcx+1Ch], r13b
0x180066fc1  jz      short loc_180066FDB
0x180066fc3  mov     rcx, [rcx+10h]
0x180066fc7  lea     r8, WPP_c1b1b84f9be43d56c172dc8519c16790_Traceguids
0x180066fce  mov     edx, 24h ; '$'
0x180066fd3  mov     r9d, eax
0x180066fd6  call    WPP_SF_d
0x180066fdb  mov     rdi, [rbp+57h+var_B0]
0x180066fdf  jmp     loc_180066EFD
```
