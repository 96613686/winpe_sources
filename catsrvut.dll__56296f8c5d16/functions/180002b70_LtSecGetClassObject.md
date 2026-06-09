# LtSecGetClassObject

- ea: `0x180002b70`
- end: `0x180003023`
- name: `LtSecGetClassObject`
- size: `1203`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180002440`

## callees

- `0x180002b70`
- `0x18001c944`
- `0x18001cb84`
- `0x18001cdc4`
- `0x18001e654`
- `0x18001e698`
- `0x18005583a`
- `0x180057010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002ffc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180002ffc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002bb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002c0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002c4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002c9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002cef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002d41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002ddd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002e8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002f3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002f7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002bb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002c0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002c4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002c9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002cef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002d41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002ddd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002e8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002f3b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180002f7c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall LtSecGetClassObject(_QWORD *a1, __int64 a2, _QWORD *a3)
{
  __int64 v6; // rax
  CLTRoleConfig *v7; // rax
  CLTRoleConfig *v8; // rax
  CLTClassSecurity *v9; // rbx
  __int64 (__fastcall **v10)(CLTClassSecurity *, __int64, _QWORD *); // rax
  int v11; // eax
  __int64 v12; // rax
  CLTRoleDef *v13; // rax
  __int64 v14; // rax
  CLTMethodSecurity *v15; // rax
  __int64 v16; // rax
  CLTInterfaceSecurity *v17; // rax
  __int64 v18; // rax
  CLTClassSecurity *v19; // rax
  __int64 v20; // rax
  char *v21; // rax
  __int64 v22; // rax
  CLTClassSecurity *v23; // rax
  __int64 v24; // rax
  CLTClassSecurity *v25; // rax
  __int64 v26; // rax
  CLTClassSecurity *v27; // rax
  __int64 v28; // rax
  CLTClassSecurity *v29; // rax
  unsigned int v30; // edi

  if ( !a3 )
    return 2147942487LL;
  *a3 = 0;
  v6 = clsidSLTROLECONFIG - *a1;
  if ( clsidSLTROLECONFIG == *a1 )
    v6 = 0xCAE5B0086000359DuLL - a1[1];
  if ( !v6 )
  {
    v7 = (CLTRoleConfig *)CoTaskMemAlloc(0x48u);
    if ( !v7 )
      return 2147942414LL;
    v8 = CLTRoleConfig::CLTRoleConfig(v7);
    goto LABEL_8;
  }
  v12 = clsidSLTROLEDEFINITION - *a1;
  if ( clsidSLTROLEDEFINITION == *a1 )
    v12 = 0xCAE5B0086000359DuLL - a1[1];
  if ( !v12 )
  {
    v13 = (CLTRoleDef *)CoTaskMemAlloc(0x48u);
    if ( !v13 )
      return 2147942414LL;
    v8 = CLTRoleDef::CLTRoleDef(v13);
LABEL_8:
    v9 = v8;
    if ( v8 )
    {
      v10 = *(__int64 (__fastcall ***)(CLTClassSecurity *, __int64, _QWORD *))v8;
LABEL_10:
      v11 = (*v10)(v9, a2, a3);
      goto LABEL_66;
    }
    return 2147942414LL;
  }
  v14 = clsidSLTROLESBYMETHOD - *a1;
  if ( clsidSLTROLESBYMETHOD == *a1 )
    v14 = 0xCAE5B0086000359DuLL - a1[1];
  if ( !v14 )
  {
    v15 = (CLTMethodSecurity *)CoTaskMemAlloc(0x248u);
    if ( v15 )
      v9 = CLTMethodSecurity::CLTMethodSecurity(v15);
    else
      v9 = 0;
    if ( v9 )
    {
      v10 = *(__int64 (__fastcall ***)(CLTClassSecurity *, __int64, _QWORD *))v9;
      goto LABEL_10;
    }
    return 2147942414LL;
  }
  v16 = clsidSLTROLESBYINTERFACE - *a1;
  if ( clsidSLTROLESBYINTERFACE == *a1 )
    v16 = 0xCAE5B0086000359DuLL - a1[1];
  if ( !v16 )
  {
    v17 = (CLTInterfaceSecurity *)CoTaskMemAlloc(0x208u);
    if ( v17 )
      v9 = CLTInterfaceSecurity::CLTInterfaceSecurity(v17);
    else
      v9 = 0;
    if ( v9 )
    {
      v10 = *(__int64 (__fastcall ***)(CLTClassSecurity *, __int64, _QWORD *))v9;
      goto LABEL_10;
    }
    return 2147942414LL;
  }
  v18 = clsidSLTROLESBYCLSID - *a1;
  if ( clsidSLTROLESBYCLSID == *a1 )
    v18 = 0xCAE5B0086000359DuLL - a1[1];
  if ( !v18 )
  {
    v19 = (CLTClassSecurity *)CoTaskMemAlloc(0x1F0u);
    if ( v19 )
      v9 = CLTClassSecurity::CLTClassSecurity(v19);
    else
      v9 = 0;
    if ( v9 )
    {
      v10 = *(__int64 (__fastcall ***)(CLTClassSecurity *, __int64, _QWORD *))v9;
      goto LABEL_10;
    }
    return 2147942414LL;
  }
  v20 = clsidSLTLegacyClasses - *a1;
  if ( clsidSLTLegacyClasses == *a1 )
    v20 = 0xA358AE802F6CB19CuLL - a1[1];
  if ( !v20 )
  {
    v21 = (char *)CoTaskMemAlloc(0x140u);
    v9 = (CLTClassSecurity *)v21;
    if ( v21 )
    {
      *(_QWORD *)v21 = &CLTLegacyClasses::`vftable'{for `IClassFactory'};
      *((_QWORD *)v21 + 1) = &CLTLegacyClasses::`vftable'{for `ISimpleTableWrite'};
      *((_QWORD *)v21 + 2) = &CLTLegacyClasses::`vftable'{for `ISimpleTableControl'};
      *((_QWORD *)v21 + 3) = &CLTLegacyClasses::`vftable'{for `ISimpleLogicTableDispenser'};
      *((_QWORD *)v21 + 4) = 0;
      *((_DWORD *)v21 + 10) = 0;
      *((_QWORD *)v21 + 6) = 0;
      *((_QWORD *)v21 + 7) = 0;
      *((_DWORD *)v21 + 76) = 0;
      *((_QWORD *)v21 + 39) = 0;
      memset_0(v21 + 64, 0, 0xF0u);
      v10 = *(__int64 (__fastcall ***)(CLTClassSecurity *, __int64, _QWORD *))v9;
      goto LABEL_10;
    }
    return 2147942414LL;
  }
  v22 = clsidSLTMethods - *a1;
  if ( clsidSLTMethods == *a1 )
    v22 = 0xDA91B40A8F485FA6uLL - a1[1];
  if ( !v22 )
  {
    v23 = (CLTClassSecurity *)CoTaskMemAlloc(0x48u);
    v9 = v23;
    if ( !v23 )
      return 2147942414LL;
    *(_QWORD *)v23 = &CLTInterfaceMethodBase::`vftable'{for `IClassFactory'};
    *((_QWORD *)v23 + 1) = &CLTMethod::`vftable'{for `ISimpleTableWrite'};
    *((_QWORD *)v23 + 2) = &CLTMethod::`vftable'{for `ISimpleLogicTableDispenser'};
    *((_QWORD *)v23 + 3) = &CLTInterfaceMethodBase::`vftable'{for `ISimpleTableControl'};
    *((struct _GUID *)v23 + 2) = tidCOMSERVICES_CLASSITFMETHOD;
    *((_QWORD *)v23 + 6) = 0;
    *((_QWORD *)v23 + 8) = 0;
    *(_QWORD *)v23 = &CLTMethod::`vftable'{for `IClassFactory'};
    *((_QWORD *)v23 + 1) = &CLTMethod::`vftable'{for `ISimpleTableWrite'};
    *((_QWORD *)v23 + 2) = &CLTMethod::`vftable'{for `ISimpleLogicTableDispenser'};
    *((_QWORD *)v23 + 3) = &CLTInterfaceMethodBase::`vftable'{for `ISimpleTableControl'};
    v11 = ((__int64 (__fastcall *)(CLTClassSecurity *, __int64, _QWORD *))CLTMethod::`vftable'{for `IClassFactory'})(
            v23,
            a2,
            a3);
LABEL_66:
    v30 = v11;
    if ( v11 < 0 )
    {
      if ( v9 )
        CoTaskMemFree(v9);
    }
    return v30;
  }
  v24 = clsidSLTInterfaces - *a1;
  if ( clsidSLTInterfaces == *a1 )
    v24 = 0xBFFC6F226A7D4AA9uLL - a1[1];
  if ( !v24 )
  {
    v25 = (CLTClassSecurity *)CoTaskMemAlloc(0x48u);
    v9 = v25;
    if ( !v25 )
      return 2147942414LL;
    *(_QWORD *)v25 = &CLTInterfaceMethodBase::`vftable'{for `IClassFactory'};
    *((_QWORD *)v25 + 1) = &CLTMethod::`vftable'{for `ISimpleTableWrite'};
    *((_QWORD *)v25 + 2) = &CLTMethod::`vftable'{for `ISimpleLogicTableDispenser'};
    *((_QWORD *)v25 + 3) = &CLTInterfaceMethodBase::`vftable'{for `ISimpleTableControl'};
    *((struct _GUID *)v25 + 2) = tidCOMSERVICES_CLASSINTERFACE;
    *((_QWORD *)v25 + 6) = 0;
    *((_QWORD *)v25 + 8) = 0;
    *(_QWORD *)v25 = &CLTInterface::`vftable'{for `IClassFactory'};
    *((_QWORD *)v25 + 1) = &CLTMethod::`vftable'{for `ISimpleTableWrite'};
    *((_QWORD *)v25 + 2) = &CLTMethod::`vftable'{for `ISimpleLogicTableDispenser'};
    *((_QWORD *)v25 + 3) = &CLTInterfaceMethodBase::`vftable'{for `ISimpleTableControl'};
    v11 = ((__int64 (__fastcall *)(CLTClassSecurity *, __int64, _QWORD *))CLTInterface::`vftable'{for `IClassFactory'})(
            v25,
            a2,
            a3);
    goto LABEL_66;
  }
  v26 = clsidSLTLegacyServers - *a1;
  if ( clsidSLTLegacyServers == *a1 )
    v26 = 0x299D8F5BA8BB08A0LL - a1[1];
  if ( !v26 )
  {
    v27 = (CLTClassSecurity *)CoTaskMemAlloc(0x58u);
    v9 = v27;
    if ( !v27 )
      return 2147942414LL;
    *((_DWORD *)v27 + 11) = 0;
    goto LABEL_65;
  }
  v28 = clsidSLTWOWLegacyServers - *a1;
  if ( clsidSLTWOWLegacyServers == *a1 )
    v28 = 0x7AEB9CE4944C4E87LL - a1[1];
  if ( !v28 )
  {
    v29 = (CLTClassSecurity *)CoTaskMemAlloc(0x58u);
    v9 = v29;
    if ( !v29 )
      return 2147942414LL;
    *((_DWORD *)v29 + 11) = 1;
LABEL_65:
    *(_QWORD *)v9 = &CLTLegacyServers::`vftable'{for `IClassFactory'};
    *((_QWORD *)v9 + 1) = &CLTLegacyServers::`vftable'{for `ISimpleTableRead'};
    *((_QWORD *)v9 + 2) = &CLTLegacyServers::`vftable'{for `ISimpleTableControl'};
    *((_QWORD *)v9 + 3) = &CLTLegacyServers::`vftable'{for `ISimpleLogicTableDispenser'};
    *((_QWORD *)v9 + 4) = 0;
    *((_QWORD *)v9 + 6) = 0;
    *((_QWORD *)v9 + 7) = 0;
    *((_QWORD *)v9 + 8) = 0;
    *((_QWORD *)v9 + 9) = 0;
    *((_QWORD *)v9 + 10) = 0;
    v11 = ((__int64 (__fastcall *)(CLTClassSecurity *, __int64, _QWORD *))CLTLegacyServers::`vftable'{for `IClassFactory'})(
            v9,
            a2,
            a3);
    goto LABEL_66;
  }
  return (unsigned int)-2147221231;
}

```

## disassembly

```asm
0x180002b70  push    rbx
0x180002b72  push    rbp
0x180002b73  push    rsi
0x180002b74  push    rdi
0x180002b75  sub     rsp, 28h
0x180002b79  mov     rdi, r8
0x180002b7c  mov     rsi, rdx
0x180002b7f  test    r8, r8
0x180002b82  jnz     short loc_180002B92
0x180002b84  mov     eax, 80070057h
0x180002b89  add     rsp, 28h
0x180002b8d  pop     rdi
0x180002b8e  pop     rsi
0x180002b8f  pop     rbp
0x180002b90  pop     rbx
0x180002b91  retn
0x180002b92  xor     ebp, ebp
0x180002b94  mov     [r8], rbp
0x180002b97  mov     rax, cs:clsidSLTROLECONFIG
0x180002b9e  sub     rax, [rcx]
0x180002ba1  jnz     short loc_180002BAE
0x180002ba3  mov     rax, cs:qword_180060B50
0x180002baa  sub     rax, [rcx+8]
0x180002bae  test    rax, rax
0x180002bb1  jnz     short loc_180002BEB
0x180002bb3  mov     ecx, 48h ; 'H'; cb
0x180002bb8  call    cs:__imp_CoTaskMemAlloc
0x180002bbe  mov     [rsp+48h+arg_10], rax
0x180002bc3  test    rax, rax
0x180002bc6  jz      loc_180003005
0x180002bcc  mov     rcx, rax; this
0x180002bcf  call    ??0CLTRoleConfig@@QEAA@XZ; CLTRoleConfig::CLTRoleConfig(void)
0x180002bd4  mov     rbx, rax
0x180002bd7  test    rax, rax
0x180002bda  jz      loc_180003005
0x180002be0  mov     rax, [rax]
0x180002be3  mov     rax, [rax]
0x180002be6  jmp     loc_180002FE0
0x180002beb  mov     rax, cs:clsidSLTROLEDEFINITION
0x180002bf2  sub     rax, [rcx]
0x180002bf5  jnz     short loc_180002C02
0x180002bf7  mov     rax, cs:qword_180060B20
0x180002bfe  sub     rax, [rcx+8]
0x180002c02  test    rax, rax
0x180002c05  jnz     short loc_180002C2A
0x180002c07  mov     ecx, 48h ; 'H'; cb
0x180002c0c  call    cs:__imp_CoTaskMemAlloc
0x180002c12  mov     [rsp+48h+arg_10], rax
0x180002c17  test    rax, rax
0x180002c1a  jz      loc_180003005
0x180002c20  mov     rcx, rax; this
0x180002c23  call    ??0CLTRoleDef@@QEAA@XZ; CLTRoleDef::CLTRoleDef(void)
0x180002c28  jmp     short loc_180002BD4
0x180002c2a  mov     rax, cs:clsidSLTROLESBYMETHOD
0x180002c31  sub     rax, [rcx]
0x180002c34  jnz     short loc_180002C41
0x180002c36  mov     rax, cs:qword_180060B00
0x180002c3d  sub     rax, [rcx+8]
0x180002c41  test    rax, rax
0x180002c44  jnz     short loc_180002C7C
0x180002c46  mov     ecx, 248h; cb
0x180002c4b  call    cs:__imp_CoTaskMemAlloc
0x180002c51  mov     [rsp+48h+arg_10], rax
0x180002c56  test    rax, rax
0x180002c59  jz      short loc_180002C68
0x180002c5b  mov     rcx, rax; this
0x180002c5e  call    ??0CLTMethodSecurity@@QEAA@XZ; CLTMethodSecurity::CLTMethodSecurity(void)
0x180002c63  mov     rbx, rax
0x180002c66  jmp     short loc_180002C6B
0x180002c68  mov     rbx, rbp
0x180002c6b  test    rbx, rbx
0x180002c6e  jz      loc_180003005
0x180002c74  mov     rax, [rbx]
0x180002c77  jmp     loc_180002BE3
0x180002c7c  mov     rax, cs:clsidSLTROLESBYINTERFACE
0x180002c83  sub     rax, [rcx]
0x180002c86  jnz     short loc_180002C93
0x180002c88  mov     rax, cs:qword_180060B10
0x180002c8f  sub     rax, [rcx+8]
0x180002c93  test    rax, rax
0x180002c96  jnz     short loc_180002CCE
0x180002c98  mov     ecx, 208h; cb
0x180002c9d  call    cs:__imp_CoTaskMemAlloc
0x180002ca3  mov     [rsp+48h+arg_10], rax
0x180002ca8  test    rax, rax
0x180002cab  jz      short loc_180002CBA
0x180002cad  mov     rcx, rax; this
0x180002cb0  call    ??0CLTInterfaceSecurity@@QEAA@XZ; CLTInterfaceSecurity::CLTInterfaceSecurity(void)
0x180002cb5  mov     rbx, rax
0x180002cb8  jmp     short loc_180002CBD
0x180002cba  mov     rbx, rbp
0x180002cbd  test    rbx, rbx
0x180002cc0  jz      loc_180003005
0x180002cc6  mov     rax, [rbx]
0x180002cc9  jmp     loc_180002BE3
0x180002cce  mov     rax, cs:clsidSLTROLESBYCLSID
0x180002cd5  sub     rax, [rcx]
0x180002cd8  jnz     short loc_180002CE5
0x180002cda  mov     rax, cs:qword_180060AF0
0x180002ce1  sub     rax, [rcx+8]
0x180002ce5  test    rax, rax
0x180002ce8  jnz     short loc_180002D20
0x180002cea  mov     ecx, 1F0h; cb
0x180002cef  call    cs:__imp_CoTaskMemAlloc
0x180002cf5  mov     [rsp+48h+arg_10], rax
0x180002cfa  test    rax, rax
0x180002cfd  jz      short loc_180002D0C
0x180002cff  mov     rcx, rax; this
0x180002d02  call    ??0CLTClassSecurity@@QEAA@XZ; CLTClassSecurity::CLTClassSecurity(void)
0x180002d07  mov     rbx, rax
0x180002d0a  jmp     short loc_180002D0F
0x180002d0c  mov     rbx, rbp
0x180002d0f  test    rbx, rbx
0x180002d12  jz      loc_180003005
0x180002d18  mov     rax, [rbx]
0x180002d1b  jmp     loc_180002BE3
0x180002d20  mov     rax, cs:clsidSLTLegacyClasses
0x180002d27  sub     rax, [rcx]
0x180002d2a  jnz     short loc_180002D37
0x180002d2c  mov     rax, cs:qword_180060B60
0x180002d33  sub     rax, [rcx+8]
0x180002d37  test    rax, rax
0x180002d3a  jnz     short loc_180002DB8
0x180002d3c  mov     ecx, 140h; cb
0x180002d41  call    cs:__imp_CoTaskMemAlloc
0x180002d47  mov     rbx, rax
0x180002d4a  mov     [rsp+48h+arg_10], rax
0x180002d4f  test    rax, rax
0x180002d52  jz      loc_180003005
0x180002d58  lea     rax, ??_7CLTLegacyClasses@@6BIClassFactory@@@; const CLTLegacyClasses::`vftable'{for `IClassFactory'}
0x180002d5f  mov     [rbx], rax
0x180002d62  lea     rax, ??_7CLTLegacyClasses@@6BISimpleTableWrite@@@; const CLTLegacyClasses::`vftable'{for `ISimpleTableWrite'}
0x180002d69  mov     [rbx+8], rax
0x180002d6d  lea     rax, ??_7CLTLegacyClasses@@6BISimpleTableControl@@@; const CLTLegacyClasses::`vftable'{for `ISimpleTableControl'}
0x180002d74  mov     [rbx+10h], rax
0x180002d78  lea     rax, ??_7CLTLegacyClasses@@6BISimpleLogicTableDispenser@@@; const CLTLegacyClasses::`vftable'{for `ISimpleLogicTableDispenser'}
0x180002d7f  mov     [rbx+18h], rax
0x180002d83  mov     [rbx+20h], rbp
0x180002d87  mov     [rbx+28h], ebp
0x180002d8a  mov     [rbx+30h], rbp
0x180002d8e  mov     [rbx+38h], rbp
0x180002d92  mov     [rbx+130h], ebp
0x180002d98  mov     [rbx+138h], rbp
0x180002d9f  lea     rcx, [rbx+40h]; void *
0x180002da3  xor     edx, edx; Val
0x180002da5  mov     r8d, 0F0h; Size
0x180002dab  call    memset_0
0x180002db0  mov     rax, [rbx]
0x180002db3  jmp     loc_180002BE3
0x180002db8  mov     rax, cs:clsidSLTMethods
0x180002dbf  sub     rax, [rcx]
0x180002dc2  jnz     short loc_180002DCF
0x180002dc4  mov     rax, cs:qword_180060B30
0x180002dcb  sub     rax, [rcx+8]
0x180002dcf  test    rax, rax
0x180002dd2  jnz     loc_180002E69
0x180002dd8  mov     ecx, 48h ; 'H'; cb
0x180002ddd  call    cs:__imp_CoTaskMemAlloc
0x180002de3  mov     rbx, rax
0x180002de6  mov     [rsp+48h+arg_10], rax
0x180002deb  test    rax, rax
0x180002dee  jz      loc_180003005
0x180002df4  lea     rax, ??_7CLTInterfaceMethodBase@@6BIClassFactory@@@; const CLTInterfaceMethodBase::`vftable'{for `IClassFactory'}
0x180002dfb  mov     [rbx], rax
0x180002dfe  lea     rax, ??_7CLTMethod@@6BISimpleTableWrite@@@; const CLTMethod::`vftable'{for `ISimpleTableWrite'}
0x180002e05  mov     [rbx+8], rax
0x180002e09  lea     rax, ??_7CLTMethod@@6BISimpleLogicTableDispenser@@@; const CLTMethod::`vftable'{for `ISimpleLogicTableDispenser'}
0x180002e10  mov     [rbx+10h], rax
0x180002e14  lea     rax, ??_7CLTInterfaceMethodBase@@6BISimpleTableControl@@@; const CLTInterfaceMethodBase::`vftable'{for `ISimpleTableControl'}
0x180002e1b  mov     [rbx+18h], rax
0x180002e1f  movups  xmm0, xmmword ptr cs:tidCOMSERVICES_CLASSITFMETHOD.Data1
0x180002e26  movups  xmmword ptr [rbx+20h], xmm0
0x180002e2a  mov     [rbx+30h], rbp
0x180002e2e  mov     [rbx+40h], rbp
0x180002e32  lea     rax, ??_7CLTMethod@@6BIClassFactory@@@; const CLTMethod::`vftable'{for `IClassFactory'}
0x180002e39  mov     [rbx], rax
0x180002e3c  lea     rax, ??_7CLTMethod@@6BISimpleTableWrite@@@; const CLTMethod::`vftable'{for `ISimpleTableWrite'}
0x180002e43  mov     [rbx+8], rax
0x180002e47  lea     rax, ??_7CLTMethod@@6BISimpleLogicTableDispenser@@@; const CLTMethod::`vftable'{for `ISimpleLogicTableDispenser'}
0x180002e4e  mov     [rbx+10h], rax
0x180002e52  lea     rax, ??_7CLTInterfaceMethodBase@@6BISimpleTableControl@@@; const CLTInterfaceMethodBase::`vftable'{for `ISimpleTableControl'}
0x180002e59  mov     [rbx+18h], rax
0x180002e5d  mov     rax, cs:??_7CLTMethod@@6BIClassFactory@@@; const CLTMethod::`vftable'{for `IClassFactory'}
0x180002e64  jmp     loc_180002FE0
0x180002e69  mov     rax, cs:clsidSLTInterfaces
0x180002e70  sub     rax, [rcx]
0x180002e73  jnz     short loc_180002E80
0x180002e75  mov     rax, cs:qword_180060B40
0x180002e7c  sub     rax, [rcx+8]
0x180002e80  test    rax, rax
0x180002e83  jnz     loc_180002F1A
0x180002e89  mov     ecx, 48h ; 'H'; cb
0x180002e8e  call    cs:__imp_CoTaskMemAlloc
0x180002e94  mov     rbx, rax
0x180002e97  mov     [rsp+48h+arg_10], rax
0x180002e9c  test    rax, rax
0x180002e9f  jz      loc_180003005
0x180002ea5  lea     rax, ??_7CLTInterfaceMethodBase@@6BIClassFactory@@@; const CLTInterfaceMethodBase::`vftable'{for `IClassFactory'}
0x180002eac  mov     [rbx], rax
0x180002eaf  lea     rax, ??_7CLTMethod@@6BISimpleTableWrite@@@; const CLTMethod::`vftable'{for `ISimpleTableWrite'}
0x180002eb6  mov     [rbx+8], rax
0x180002eba  lea     rax, ??_7CLTMethod@@6BISimpleLogicTableDispenser@@@; const CLTMethod::`vftable'{for `ISimpleLogicTableDispenser'}
0x180002ec1  mov     [rbx+10h], rax
0x180002ec5  lea     rax, ??_7CLTInterfaceMethodBase@@6BISimpleTableControl@@@; const CLTInterfaceMethodBase::`vftable'{for `ISimpleTableControl'}
0x180002ecc  mov     [rbx+18h], rax
0x180002ed0  movups  xmm0, xmmword ptr cs:tidCOMSERVICES_CLASSINTERFACE.Data1
0x180002ed7  movups  xmmword ptr [rbx+20h], xmm0
0x180002edb  mov     [rbx+30h], rbp
0x180002edf  mov     [rbx+40h], rbp
0x180002ee3  lea     rax, ??_7CLTInterface@@6BIClassFactory@@@; const CLTInterface::`vftable'{for `IClassFactory'}
0x180002eea  mov     [rbx], rax
0x180002eed  lea     rax, ??_7CLTMethod@@6BISimpleTableWrite@@@; const CLTMethod::`vftable'{for `ISimpleTableWrite'}
0x180002ef4  mov     [rbx+8], rax
0x180002ef8  lea     rax, ??_7CLTMethod@@6BISimpleLogicTableDispenser@@@; const CLTMethod::`vftable'{for `ISimpleLogicTableDispenser'}
0x180002eff  mov     [rbx+10h], rax
0x180002f03  lea     rax, ??_7CLTInterfaceMethodBase@@6BISimpleTableControl@@@; const CLTInterfaceMethodBase::`vftable'{for `ISimpleTableControl'}
0x180002f0a  mov     [rbx+18h], rax
0x180002f0e  mov     rax, cs:??_7CLTInterface@@6BIClassFactory@@@; const CLTInterface::`vftable'{for `IClassFactory'}
0x180002f15  jmp     loc_180002FE0
0x180002f1a  mov     rax, cs:clsidSLTLegacyServers
0x180002f21  sub     rax, [rcx]
0x180002f24  jnz     short loc_180002F31
0x180002f26  mov     rax, cs:qword_180060B70
0x180002f2d  sub     rax, [rcx+8]
0x180002f31  test    rax, rax
0x180002f34  jnz     short loc_180002F57
0x180002f36  mov     ecx, 58h ; 'X'; cb
0x180002f3b  call    cs:__imp_CoTaskMemAlloc
0x180002f41  mov     rbx, rax
0x180002f44  mov     [rsp+48h+arg_10], rax
0x180002f49  test    rax, rax
0x180002f4c  jz      loc_180003005
0x180002f52  mov     [rax+2Ch], ebp
0x180002f55  jmp     short loc_180002F96
0x180002f57  mov     rax, cs:clsidSLTWOWLegacyServers
0x180002f5e  sub     rax, [rcx]
0x180002f61  jnz     short loc_180002F6E
0x180002f63  mov     rax, cs:qword_180060B80
0x180002f6a  sub     rax, [rcx+8]
0x180002f6e  test    rax, rax
0x180002f71  jnz     loc_180003013
0x180002f77  mov     ecx, 58h ; 'X'; cb
0x180002f7c  call    cs:__imp_CoTaskMemAlloc
0x180002f82  mov     rbx, rax
0x180002f85  mov     [rsp+48h+arg_10], rax
0x180002f8a  test    rax, rax
0x180002f8d  jz      short loc_180003005
0x180002f8f  mov     dword ptr [rax+2Ch], 1
0x180002f96  lea     rax, ??_7CLTLegacyServers@@6BIClassFactory@@@; const CLTLegacyServers::`vftable'{for `IClassFactory'}
0x180002f9d  mov     [rbx], rax
0x180002fa0  lea     rax, ??_7CLTLegacyServers@@6BISimpleTableRead@@@; const CLTLegacyServers::`vftable'{for `ISimpleTableRead'}
0x180002fa7  mov     [rbx+8], rax
0x180002fab  lea     rax, ??_7CLTLegacyServers@@6BISimpleTableControl@@@; const CLTLegacyServers::`vftable'{for `ISimpleTableControl'}
0x180002fb2  mov     [rbx+10h], rax
0x180002fb6  lea     rax, ??_7CLTLegacyServers@@6BISimpleLogicTableDispenser@@@; const CLTLegacyServers::`vftable'{for `ISimpleLogicTableDispenser'}
0x180002fbd  mov     [rbx+18h], rax
0x180002fc1  mov     [rbx+20h], rbp
0x180002fc5  mov     [rbx+30h], rbp
0x180002fc9  mov     [rbx+38h], rbp
0x180002fcd  mov     [rbx+40h], rbp
0x180002fd1  mov     [rbx+48h], rbp
0x180002fd5  mov     [rbx+50h], rbp
0x180002fd9  mov     rax, cs:??_7CLTLegacyServers@@6BIClassFactory@@@; const CLTLegacyServers::`vftable'{for `IClassFactory'}
0x180002fe0  mov     r8, rdi
0x180002fe3  mov     rdx, rsi
0x180002fe6  mov     rcx, rbx
0x180002fe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fee  mov     edi, eax
0x180002ff0  test    eax, eax
0x180002ff2  jns     short loc_180003018
0x180002ff4  test    rbx, rbx
0x180002ff7  jz      short loc_180003018
0x180002ff9  mov     rcx, rbx; pv
0x180002ffc  call    cs:__imp_CoTaskMemFree
0x180003002  nop
0x180003003  jmp     short loc_180003018
0x180003005  mov     eax, 8007000Eh
0x18000300a  add     rsp, 28h
0x18000300e  pop     rdi
0x18000300f  pop     rsi
0x180003010  pop     rbp
0x180003011  pop     rbx
0x180003012  retn
0x180003013  mov     edi, 80040111h
0x180003018  mov     eax, edi
0x18000301a  add     rsp, 28h
0x18000301e  pop     rdi
0x18000301f  pop     rsi
0x180003020  pop     rbp
0x180003021  pop     rbx
0x180003022  retn
```
