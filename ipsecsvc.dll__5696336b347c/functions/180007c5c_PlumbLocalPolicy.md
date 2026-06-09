# PlumbLocalPolicy

- ea: `0x180007c5c`
- end: `0x1800080da`
- name: `PlumbLocalPolicy`
- size: `1150`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001590`
- `0x18000adac`

## callees

- `0x180001220`
- `0x180006f60`
- `0x180007c5c`
- `0x1800080e0`
- `0x180008280`
- `0x180008504`
- `0x18000b29c`
- `0x18000c904`
- `0x18000e078`
- `0x18000e510`
- `0x18000f638`
- `0x180019d80`
- `0x18003947c`
- `0x180039c80`
- `0x18003c2d4`
- `0x180042e20`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180007ca5`
- `ntdll!EtwEventWrite` at `0x180008048`
- `ntdll!EtwEventWrite` at `0x1800080ba`
- `ntdll!EtwEventWrite` at `0x180007ca5`
- `ntdll!EtwEventWrite` at `0x180008048`
- `ntdll!EtwEventWrite` at `0x1800080ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007e42`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007e42`

## pseudocode

```c
__int64 __fastcall PlumbLocalPolicy(_QWORD *a1)
{
  __int64 v1; // rsi
  _DWORD *v3; // r14
  unsigned int v4; // r12d
  DWORD RegistryPolicyDN; // eax
  DWORD dwMessageId; // ebx
  _QWORD *v7; // rcx
  unsigned __int16 *v8; // rdi
  void *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rdx
  DWORD v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rbx
  LPVOID *v16; // rcx
  _DWORD *v17; // rcx
  void *v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rcx
  DWORD v24; // ebx
  __int64 v25; // [rsp+40h] [rbp-10h] BYREF
  __int64 v26; // [rsp+48h] [rbp-8h]
  int v27; // [rsp+98h] [rbp+48h]
  DWORD v28; // [rsp+A0h] [rbp+50h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+58h] BYREF

  v1 = 0;
  v3 = 0;
  hKey = 0;
  v25 = 0;
  v28 = 0;
  v4 = 1;
  if ( g_Provider )
    EtwEventWrite(g_Provider, IPSEC_SVC_ApplyLocalPolicy_Begin, 0, 0);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids);
  RegistryPolicyDN = GetRegistryPolicyDN((LPVOID *)&hKey);
  dwMessageId = RegistryPolicyDN;
  if ( RegistryPolicyDN )
  {
    v27 = 0;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v8 = (unsigned __int16 *)hKey;
      goto LABEL_59;
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        60,
        WPP_e815f316f4bb38f383997e5feee741ae_Traceguids,
        RegistryPolicyDN);
      v8 = (unsigned __int16 *)hKey;
LABEL_55:
      v7 = WPP_GLOBAL_Control;
      goto LABEL_56;
    }
    v8 = (unsigned __int16 *)hKey;
    goto LABEL_56;
  }
  v27 = 1;
  v8 = (unsigned __int16 *)hKey;
  hKey = 0;
  v26 = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids);
  dwMessageId = OpenRegistryIPSECRootKey(
                  (__int64)v9,
                  L"SOFTWARE\\Policies\\Microsoft\\Windows\\IPSEC\\Policy\\Local",
                  &hKey);
  if ( dwMessageId )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_29;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v10 = 79;
LABEL_23:
      WPP_SF_d(v7[2], v10, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, dwMessageId);
      v7 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    dwMessageId = ReadPolicyObjectFromRegistry(hKey);
    if ( !dwMessageId )
    {
      v1 = v26;
      goto LABEL_28;
    }
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      goto LABEL_29;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v10 = 80;
      goto LABEL_23;
    }
  }
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x10) != 0 )
  {
    WPP_SF_SD(v7[2], 81, (unsigned int)WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, (_DWORD)v8, dwMessageId);
LABEL_28:
    v7 = WPP_GLOBAL_Control;
  }
LABEL_29:
  if ( hKey )
  {
    RegCloseKey(hKey);
    v7 = WPP_GLOBAL_Control;
  }
  if ( dwMessageId )
  {
    if ( v7 == &WPP_GLOBAL_Control )
      goto LABEL_59;
    if ( (*((_BYTE *)v7 + 28) & 0x10) == 0 )
      goto LABEL_56;
    v11 = 61;
    goto LABEL_54;
  }
  v12 = ProcessNFAs(v1, 0, &v28, &v25);
  dwMessageId = v12;
  if ( v12 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v3 = (_DWORD *)v25;
      goto LABEL_59;
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, v12);
      v3 = (_DWORD *)v25;
      goto LABEL_55;
    }
    v3 = (_DWORD *)v25;
LABEL_56:
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x10) != 0 )
      WPP_SF_d(v7[2], 66, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, dwMessageId);
    goto LABEL_59;
  }
  v15 = v25;
  AuditIPSecPolicyEventOld(v14, v13, 1269629037, *(_QWORD *)(v25 + 48));
  v16 = (LPVOID *)a1[4];
  if ( v16 )
    FreeIpsecPolicyObject(v16);
  v17 = (_DWORD *)a1[5];
  if ( v17 )
    FreeIpsecPolicyData(v17);
  v18 = (void *)a1[1];
  if ( v18 )
    IpsecFreeMem(v18);
  a1[1] = v8;
  v8 = 0;
  a1[4] = v1;
  a1[5] = v15;
  dwMessageId = ApplyLoadedLocalPolicy(a1);
  if ( dwMessageId )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids);
    DeletePolicyInformation(a1[5]);
    v4 = 0;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
LABEL_59:
      SetSpdStateOnError(2, v4, dwMessageId, a1);
      if ( v27 )
      {
        if ( !v8 )
        {
LABEL_65:
          if ( v3 )
            FreeIpsecPolicyData(v3);
          if ( g_Provider )
            EtwEventWrite(g_Provider, IPSEC_SVC_ApplyLocalPolicy_End, 0, 0);
          return dwMessageId;
        }
        if ( v4 == 1 )
          AuditIPSecPolicyErrorEventOld(v22, v21, 0x4BAD006Eu, v8, dwMessageId);
      }
      if ( v8 )
        IpsecFreeMem(v8);
      goto LABEL_65;
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_56;
    v11 = 64;
LABEL_54:
    WPP_SF_d(v7[2], v11, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, dwMessageId);
    goto LABEL_55;
  }
  v24 = v28;
  if ( v28 )
  {
    AuditIPSecPolicyErrorEventOld(v20, v19, 0x4BAD0007u, *(unsigned __int16 **)(a1[5] + 48LL), v28);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids, v24);
  }
  if ( g_Provider )
    EtwEventWrite(g_Provider, IPSEC_SVC_ApplyLocalPolicy_End, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x180007c5c  mov     [rsp-38h+arg_0], rbx
0x180007c61  push    rbp
0x180007c62  push    rsi
0x180007c63  push    rdi
0x180007c64  push    r12
0x180007c66  push    r13
0x180007c68  push    r14
0x180007c6a  push    r15
0x180007c6c  mov     rbp, rsp
0x180007c6f  sub     rsp, 50h
0x180007c73  xor     esi, esi
0x180007c75  mov     r13, rcx
0x180007c78  mov     rcx, cs:g_Provider
0x180007c7f  mov     r14d, esi
0x180007c82  mov     [rbp+hKey], rsi
0x180007c86  mov     [rbp+var_10], rsi
0x180007c8a  mov     [rbp+arg_10], esi
0x180007c8d  lea     edi, [rsi+1]
0x180007c90  mov     r12d, edi
0x180007c93  test    rcx, rcx
0x180007c96  jz      short loc_180007CAB
0x180007c98  xor     r9d, r9d
0x180007c9b  lea     rdx, IPSEC_SVC_ApplyLocalPolicy_Begin
0x180007ca2  xor     r8d, r8d
0x180007ca5  call    cs:__imp_EtwEventWrite
0x180007cab  mov     rcx, cs:WPP_GLOBAL_Control
0x180007cb2  lea     r15, WPP_GLOBAL_Control
0x180007cb9  cmp     rcx, r15
0x180007cbc  jz      short loc_180007CD9
0x180007cbe  test    byte ptr [rcx+1Ch], 4
0x180007cc2  jz      short loc_180007CD9
0x180007cc4  mov     rcx, [rcx+10h]
0x180007cc8  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x180007ccf  mov     edx, 3Bh ; ';'
0x180007cd4  call    WPP_SF_
0x180007cd9  lea     rcx, [rbp+hKey]
0x180007cdd  call    GetRegistryPolicyDN
0x180007ce2  mov     ebx, eax
0x180007ce4  test    eax, eax
0x180007ce6  jz      short loc_180007D33
0x180007ce8  mov     [rbp+arg_8], esi
0x180007ceb  mov     rcx, cs:WPP_GLOBAL_Control
0x180007cf2  cmp     rcx, r15
0x180007cf5  jz      short loc_180007D2A
0x180007cf7  mov     r15b, 10h
0x180007cfa  test    [rcx+1Ch], r15b
0x180007cfe  jz      short loc_180007D21
0x180007d00  mov     rcx, [rcx+10h]
0x180007d04  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x180007d0b  mov     edx, 3Ch ; '<'
0x180007d10  mov     r9d, eax
0x180007d13  call    WPP_SF_d
0x180007d18  mov     rdi, [rbp+hKey]
0x180007d1c  jmp     loc_180007FA1
0x180007d21  mov     rdi, [rbp+hKey]
0x180007d25  jmp     loc_180007FA8
0x180007d2a  mov     rdi, [rbp+hKey]
0x180007d2e  jmp     loc_180007FD2
0x180007d33  mov     [rbp+arg_8], edi
0x180007d36  mov     rdi, [rbp+hKey]
0x180007d3a  mov     [rbp+hKey], rsi
0x180007d3e  mov     [rbp+var_8], rsi
0x180007d42  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d49  cmp     rcx, r15
0x180007d4c  jz      short loc_180007D69
0x180007d4e  test    byte ptr [rcx+1Ch], 4
0x180007d52  jz      short loc_180007D69
0x180007d54  mov     rcx, [rcx+10h]
0x180007d58  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x180007d5f  mov     edx, 4Dh ; 'M'
0x180007d64  call    WPP_SF_
0x180007d69  lea     r8, [rbp+hKey]
0x180007d6d  lea     rdx, SubKey; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180007d74  call    OpenRegistryIPSECRootKey
0x180007d79  mov     ebx, eax
0x180007d7b  mov     r15b, 10h
0x180007d7e  test    eax, eax
0x180007d80  jz      short loc_180007DA6
0x180007d82  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d89  lea     rax, WPP_GLOBAL_Control
0x180007d90  cmp     rcx, rax
0x180007d93  jz      loc_180007E36
0x180007d99  test    [rcx+1Ch], r15b
0x180007d9d  jz      short loc_180007E02
0x180007d9f  mov     edx, 4Fh ; 'O'
0x180007da4  jmp     short loc_180007DE1
0x180007da6  mov     rcx, [rbp+hKey]; hKey
0x180007daa  lea     r9, [rbp+var_8]
0x180007dae  lea     r8, SubKey; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180007db5  mov     rdx, rdi
0x180007db8  call    ReadPolicyObjectFromRegistry
0x180007dbd  mov     ebx, eax
0x180007dbf  test    eax, eax
0x180007dc1  jz      short loc_180007E2B
0x180007dc3  mov     rcx, cs:WPP_GLOBAL_Control
0x180007dca  lea     rax, WPP_GLOBAL_Control
0x180007dd1  cmp     rcx, rax
0x180007dd4  jz      short loc_180007E36
0x180007dd6  test    [rcx+1Ch], r15b
0x180007dda  jz      short loc_180007E02
0x180007ddc  mov     edx, 50h ; 'P'
0x180007de1  mov     rcx, [rcx+10h]
0x180007de5  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x180007dec  mov     r9d, ebx
0x180007def  call    WPP_SF_d
0x180007df4  mov     rcx, cs:WPP_GLOBAL_Control
0x180007dfb  lea     rax, WPP_GLOBAL_Control
0x180007e02  cmp     rcx, rax
0x180007e05  jz      short loc_180007E36
0x180007e07  test    [rcx+1Ch], r15b
0x180007e0b  jz      short loc_180007E36
0x180007e0d  mov     rcx, [rcx+10h]
0x180007e11  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x180007e18  mov     edx, 51h ; 'Q'
0x180007e1d  mov     [rsp+50h+dwMessageId], ebx
0x180007e21  mov     r9, rdi
0x180007e24  call    WPP_SF_SD
0x180007e29  jmp     short loc_180007E2F
0x180007e2b  mov     rsi, [rbp+var_8]
0x180007e2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e36  mov     rax, [rbp+hKey]
0x180007e3a  test    rax, rax
0x180007e3d  jz      short loc_180007E4F
0x180007e3f  mov     rcx, rax; hKey
0x180007e42  call    cs:__imp_RegCloseKey
0x180007e48  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e4f  test    ebx, ebx
0x180007e51  jz      short loc_180007E77
0x180007e53  lea     rax, WPP_GLOBAL_Control
0x180007e5a  cmp     rcx, rax
0x180007e5d  jz      loc_180007FD2
0x180007e63  test    [rcx+1Ch], r15b
0x180007e67  jz      loc_180007FAF
0x180007e6d  mov     edx, 3Dh ; '='
0x180007e72  jmp     loc_180007F8E
0x180007e77  lea     r9, [rbp+var_10]
0x180007e7b  xor     edx, edx
0x180007e7d  lea     r8, [rbp+arg_10]
0x180007e81  mov     rcx, rsi
0x180007e84  call    ProcessNFAs
0x180007e89  mov     ebx, eax
0x180007e8b  test    eax, eax
0x180007e8d  jz      short loc_180007EDB
0x180007e8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180007e96  lea     r14, WPP_GLOBAL_Control
0x180007e9d  cmp     rcx, r14
0x180007ea0  jz      short loc_180007ED2
0x180007ea2  test    [rcx+1Ch], r15b
0x180007ea6  jz      short loc_180007EC9
0x180007ea8  mov     rcx, [rcx+10h]
0x180007eac  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x180007eb3  mov     edx, 3Eh ; '>'
0x180007eb8  mov     r9d, eax
0x180007ebb  call    WPP_SF_d
0x180007ec0  mov     r14, [rbp+var_10]
0x180007ec4  jmp     loc_180007FA1
0x180007ec9  mov     r14, [rbp+var_10]
0x180007ecd  jmp     loc_180007FA8
0x180007ed2  mov     r14, [rbp+var_10]
0x180007ed6  jmp     loc_180007FD2
0x180007edb  mov     rbx, [rbp+var_10]
0x180007edf  mov     r8d, 4BAD006Dh
0x180007ee5  mov     r9, [rbx+30h]
0x180007ee9  call    AuditIPSecPolicyEventOld
0x180007eee  mov     rcx, [r13+20h]; lpMem
0x180007ef2  test    rcx, rcx
0x180007ef5  jz      short loc_180007EFC
0x180007ef7  call    FreeIpsecPolicyObject
0x180007efc  mov     rcx, [r13+28h]; lpMem
0x180007f00  test    rcx, rcx
0x180007f03  jz      short loc_180007F0A
0x180007f05  call    FreeIpsecPolicyData
0x180007f0a  mov     rcx, [r13+8]; lpMem
0x180007f0e  test    rcx, rcx
0x180007f11  jz      short loc_180007F18
0x180007f13  call    IpsecFreeMem
0x180007f18  mov     [r13+8], rdi
0x180007f1c  mov     rcx, r13
0x180007f1f  xor     edi, edi
0x180007f21  mov     [r13+20h], rsi
0x180007f25  mov     [r13+28h], rbx
0x180007f29  call    ApplyLoadedLocalPolicy
0x180007f2e  mov     ebx, eax
0x180007f30  test    eax, eax
0x180007f32  jz      loc_180008052
0x180007f38  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f3f  lea     rax, WPP_GLOBAL_Control
0x180007f46  cmp     rcx, rax
0x180007f49  jz      short loc_180007F64
0x180007f4b  test    byte ptr [rcx+1Ch], 4
0x180007f4f  jz      short loc_180007F64
0x180007f51  mov     rcx, [rcx+10h]
0x180007f55  lea     edx, [rdi+3Fh]
0x180007f58  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x180007f5f  call    WPP_SF_
0x180007f64  mov     rcx, [r13+28h]
0x180007f68  call    DeletePolicyInformation
0x180007f6d  xor     r12d, r12d
0x180007f70  xor     esi, esi
0x180007f72  mov     rcx, cs:WPP_GLOBAL_Control
0x180007f79  lea     rax, WPP_GLOBAL_Control
0x180007f80  cmp     rcx, rax
0x180007f83  jz      short loc_180007FD2
0x180007f85  test    [rcx+1Ch], r15b
0x180007f89  jz      short loc_180007FAF
0x180007f8b  lea     edx, [rsi+40h]
0x180007f8e  mov     rcx, [rcx+10h]
0x180007f92  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x180007f99  mov     r9d, ebx
0x180007f9c  call    WPP_SF_d
0x180007fa1  mov     rcx, cs:WPP_GLOBAL_Control
0x180007fa8  lea     rax, WPP_GLOBAL_Control
0x180007faf  cmp     rcx, rax
0x180007fb2  jz      short loc_180007FD2
0x180007fb4  test    [rcx+1Ch], r15b
0x180007fb8  jz      short loc_180007FD2
0x180007fba  mov     rcx, [rcx+10h]
0x180007fbe  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x180007fc5  mov     edx, 42h ; 'B'
0x180007fca  mov     r9d, ebx
0x180007fcd  call    WPP_SF_d
0x180007fd2  mov     r9, r13
0x180007fd5  mov     r8d, ebx
0x180007fd8  mov     edx, r12d
0x180007fdb  mov     ecx, 2
0x180007fe0  call    SetSpdStateOnError
0x180007fe5  cmp     [rbp+arg_8], 0
0x180007fe9  jz      short loc_180008008
0x180007feb  test    rdi, rdi
0x180007fee  jz      short loc_180008015
0x180007ff0  cmp     r12d, 1
0x180007ff4  jnz     short loc_180008008
0x180007ff6  mov     r9, rdi; int
0x180007ff9  mov     [rsp+50h+dwMessageId], ebx; dwMessageId
0x180007ffd  mov     r8d, 4BAD006Eh; int
0x180008003  call    AuditIPSecPolicyErrorEventOld
0x180008008  test    rdi, rdi
0x18000800b  jz      short loc_180008015
0x18000800d  mov     rcx, rdi; lpMem
0x180008010  call    IpsecFreeMem
0x180008015  test    rsi, rsi
0x180008018  jz      short loc_180008022
0x18000801a  mov     rcx, rsi; lpMem
0x18000801d  call    FreeIpsecPolicyObject
0x180008022  test    r14, r14
0x180008025  jz      short loc_18000802F
0x180008027  mov     rcx, r14; lpMem
0x18000802a  call    FreeIpsecPolicyData
0x18000802f  mov     rcx, cs:g_Provider
0x180008036  test    rcx, rcx
0x180008039  jz      short loc_18000804E
0x18000803b  xor     r9d, r9d
0x18000803e  lea     rdx, IPSEC_SVC_ApplyLocalPolicy_End
0x180008045  xor     r8d, r8d
0x180008048  call    cs:__imp_EtwEventWrite
0x18000804e  mov     eax, ebx
0x180008050  jmp     short loc_1800080C2
0x180008052  mov     ebx, [rbp+arg_10]
0x180008055  test    ebx, ebx
0x180008057  jz      short loc_1800080A1
0x180008059  mov     r9, [r13+28h]
0x18000805d  mov     r8d, 4BAD0007h; int
0x180008063  mov     [rsp+50h+dwMessageId], ebx; dwMessageId
0x180008067  mov     r9, [r9+30h]; int
0x18000806b  call    AuditIPSecPolicyErrorEventOld
0x180008070  mov     rcx, cs:WPP_GLOBAL_Control
0x180008077  lea     rax, WPP_GLOBAL_Control
0x18000807e  cmp     rcx, rax
0x180008081  jz      short loc_1800080A1
0x180008083  test    byte ptr [rcx+1Ch], 8
0x180008087  jz      short loc_1800080A1
0x180008089  mov     rcx, [rcx+10h]
0x18000808d  lea     r8, WPP_e815f316f4bb38f383997e5feee741ae_Traceguids
0x180008094  mov     edx, 41h ; 'A'
0x180008099  mov     r9d, ebx
0x18000809c  call    WPP_SF_d
0x1800080a1  mov     rcx, cs:g_Provider
0x1800080a8  test    rcx, rcx
0x1800080ab  jz      short loc_1800080C0
0x1800080ad  xor     r9d, r9d
0x1800080b0  lea     rdx, IPSEC_SVC_ApplyLocalPolicy_End
0x1800080b7  xor     r8d, r8d
0x1800080ba  call    cs:__imp_EtwEventWrite
0x1800080c0  xor     eax, eax
0x1800080c2  mov     rbx, [rsp+50h+arg_0]
0x1800080ca  add     rsp, 50h
0x1800080ce  pop     r15
0x1800080d0  pop     r14
0x1800080d2  pop     r13
0x1800080d4  pop     r12
0x1800080d6  pop     rdi
0x1800080d7  pop     rsi
0x1800080d8  pop     rbp
0x1800080d9  retn
```
