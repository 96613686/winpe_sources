# LoadDDMParameters

- ea: `0x180017794`
- end: `0x180017cf3`
- name: `LoadDDMParameters`
- size: `1375`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b3c0`
- `0x18001b570`

## callees

- `0x180007b7c`
- `0x180012070`
- `0x180017794`
- `0x18001846c`
- `0x180024eb0`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`

## import_xrefs

- `ADVAPI32!RegOpenKeyW` at `0x18001786a`
- `ADVAPI32!RegOpenKeyW` at `0x18001786a`
- `ADVAPI32!RegOpenKeyExW` at `0x180017c90`
- `ADVAPI32!RegOpenKeyExW` at `0x180017c90`
- `ADVAPI32!RegQueryValueExW` at `0x180017994`
- `ADVAPI32!RegQueryValueExW` at `0x180017b27`
- `ADVAPI32!RegQueryValueExW` at `0x180017cc8`
- `ADVAPI32!RegQueryValueExW` at `0x180017994`
- `ADVAPI32!RegQueryValueExW` at `0x180017b27`
- `ADVAPI32!RegQueryValueExW` at `0x180017cc8`
- `ADVAPI32!RegCloseKey` at `0x1800178d3`
- `ADVAPI32!RegCloseKey` at `0x180017ce6`
- `ADVAPI32!RegCloseKey` at `0x1800178d3`
- `ADVAPI32!RegCloseKey` at `0x180017ce6`
- `rtutils!RouterLogEventW` at `0x180017916`
- `rtutils!RouterLogEventW` at `0x180017a1d`
- `rtutils!RouterLogEventW` at `0x180017aa3`
- `rtutils!RouterLogEventW` at `0x180017916`
- `rtutils!RouterLogEventW` at `0x180017a1d`
- `rtutils!RouterLogEventW` at `0x180017aa3`
- `rasman!RasGetProtocolInfo` at `0x180017840`
- `rasman!RasGetProtocolInfo` at `0x180017840`

## string_xrefs

- `0x180017b06`: `IcConfigured`
- `0x180017b50`: `LoadDDMParameters: value of IcConfigured key is %d`
- `0x180017bf4`: `LoadDDMParameters: g_fIsICConfigured %d dwErr %d`
- `0x180017863`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Parameters`

## pseudocode

```c
__int64 __fastcall LoadDDMParameters(HKEY hKey, int a2, _DWORD *a3, _DWORD *a4)
{
  __int64 v8; // rcx
  unsigned int ProtocolInfo; // eax
  unsigned int v10; // ebx
  int v11; // r8d
  int v12; // edi
  unsigned int v13; // eax
  unsigned int v14; // esi
  unsigned __int64 v15; // rdi
  int *v16; // rdx
  __int64 *v17; // r14
  LSTATUS dwErrorCode; // eax
  unsigned int v19; // ecx
  int v20; // eax
  int v21; // ecx
  __int64 v23; // rbx
  unsigned int v24; // edi
  __int64 v25; // r8
  __int64 v26; // rax
  __int64 v27; // r8
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR plpszSubStringArray; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD v33[132]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v34[16]; // [rsp+260h] [rbp+160h] BYREF
  int *v35; // [rsp+270h] [rbp+170h]
  int v36; // [rsp+278h] [rbp+178h]
  int v37; // [rsp+27Ch] [rbp+17Ch]
  int v38; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v39[2044]; // [rsp+284h] [rbp+184h] BYREF

  cbData = 0;
  Type = 0;
  v38 = 0;
  memset_0(v39, 0, sizeof(v39));
  dword_1800C84EC &= 0xF7FFFFF7;
  dword_1800C84E8 = 1;
  dword_1800C84F0 = 120;
  memset_0(v33, 0, 0x204u);
  *a3 = 0;
  *a4 = 0;
  phkResult = 0;
  if ( dword_1800C8654 )
    ProtocolInfo = DdmGetProtocolInfo(v8, v33);
  else
    ProtocolInfo = RasGetProtocolInfo(0, v33);
  v10 = ProtocolInfo;
  if ( ProtocolInfo )
    return v10;
  v10 = RegOpenKeyW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Parameters", &phkResult);
  if ( v10 )
    return v10;
  v12 = 0;
  if ( v33[0] )
  {
    while ( LOWORD(v33[4 * v12 + 1]) != 2048 )
    {
      if ( LOWORD(v33[4 * v12 + 1]) == 0x86DD )
      {
        v13 = lProtocolEnabled((_DWORD)phkResult, 87, v11, a2, (__int64)a4);
LABEL_11:
        v10 = v13;
      }
      if ( (unsigned int)++v12 >= v33[0] )
        goto LABEL_13;
    }
    v13 = lProtocolEnabled((_DWORD)phkResult, 33, v11, a2, (__int64)a3);
    goto LABEL_11;
  }
LABEL_13:
  RegCloseKey(phkResult);
  if ( v10 )
    return v10;
  if ( !*a3 && !*a4 )
  {
    if ( dword_1800C84E4 )
      RouterLogEventW(hLogHandle, 1u, 0x4E92u, 0, 0, 0);
    return 0;
  }
  v14 = 0;
  if ( !DDMRegParams )
  {
LABEL_31:
    v20 = dword_1800C84EC;
    if ( *a3 )
    {
      v20 = dword_1800C84EC | 8;
      dword_1800C84EC |= 8u;
    }
    if ( *a4 )
    {
      v20 |= 0x8000000u;
      dword_1800C84EC = v20;
    }
    if ( (v20 & 0x1000) != 0 )
    {
      v21 = 1;
    }
    else
    {
      if ( (v20 & 0x80u) == 0 )
      {
LABEL_43:
        *(_DWORD *)Data = 0;
        dword_1800C84EC = v20 & 0xFFFFEF7F;
        LODWORD(phkResult) = 4;
        plpszSubStringArray = 0;
        Type = 0;
        v23 = -1;
        v24 = RegQueryValueExW(hKey, L"IcConfigured", 0, &Type, Data, (LPDWORD)&phkResult);
        if ( !v24 )
        {
          if ( (byte_1800C8404 & 0x10) != 0 )
          {
            LOWORD(v38) = 0;
            FormatRRASErrorString(&v38, L"LoadDDMParameters: value of IcConfigured key is %d", *(unsigned int *)Data);
            if ( (byte_1800C8404 & 0x10) != 0 )
            {
              v26 = -1;
              do
                ++v26;
              while ( *(_WORD *)&v39[2 * v26 - 4] );
              v37 = 0;
              v36 = 2 * v26 + 2;
              v35 = &v38;
              McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v25, 2, v34);
            }
          }
          if ( *(_DWORD *)Data )
            g_fIsICConfigured = 1;
        }
        if ( (byte_1800C8404 & 0x10) != 0 )
        {
          LOWORD(v38) = 0;
          FormatRRASErrorString(
            &v38,
            L"LoadDDMParameters: g_fIsICConfigured %d dwErr %d",
            (unsigned int)g_fIsICConfigured,
            v24);
          if ( (byte_1800C8404 & 0x10) != 0 )
          {
            do
              ++v23;
            while ( *(_WORD *)&v39[2 * v23 - 4] );
            v37 = 0;
            v36 = 2 * v23 + 2;
            v35 = &v38;
            McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v27, 2, v34);
          }
        }
        if ( !RegOpenKeyExW(hKey, L"IKEV2", 0, 0x20019u, (PHKEY)&plpszSubStringArray) )
        {
          LODWORD(phkResult) = 4;
          if ( !RegQueryValueExW((HKEY)plpszSubStringArray, L"StrictPskPolicy", 0, 0, Data, (LPDWORD)&phkResult)
            && *(_DWORD *)Data )
          {
            dword_1800C84EC |= 0x80000000;
          }
          RegCloseKey((HKEY)plpszSubStringArray);
        }
        return 0;
      }
      v21 = 0;
    }
    ModifyDefPolicyToForceEncryption(v21);
    v20 = dword_1800C84EC;
    goto LABEL_43;
  }
  while ( 1 )
  {
    v15 = 32LL * v14;
    v16 = *(int **)((char *)&DDMRegParams + v15 + 8);
    v17 = &qword_1800C75D0[v15 / 8];
    if ( &dword_1800C8658 == v16 )
      *(_DWORD *)v17 = dword_1800C8650 != 0 ? 1 : 5;
    cbData = 4;
    dwErrorCode = RegQueryValueExW(hKey, *(LPCWSTR *)((char *)&DDMRegParams + v15), 0, &Type, (LPBYTE)v16, &cbData);
    v10 = dwErrorCode;
    if ( !dwErrorCode )
    {
      if ( Type != 4
        || (v19 = **(_DWORD **)((char *)&DDMRegParams + v15 + 8), v19 > *(_DWORD *)((char *)&DDMRegParams + v15 + 24))
        || v19 < *(_DWORD *)((char *)&DDMRegParams + v15 + 20) )
      {
        plpszSubStringArray = *(LPWSTR *)((char *)&DDMRegParams + v15);
        if ( (unsigned int)dword_1800C84E4 > 1 )
          RouterLogEventW(hLogHandle, 2u, 0x4E85u, 1u, &plpszSubStringArray, 0);
        **(_DWORD **)((char *)&DDMRegParams + v15 + 8) = *(_DWORD *)v17;
      }
      goto LABEL_30;
    }
    if ( dwErrorCode != 2 )
      break;
    **(_DWORD **)((char *)&DDMRegParams + v15 + 8) = *(_DWORD *)v17;
LABEL_30:
    if ( !*(&DDMRegParams + 4 * ++v14) )
      goto LABEL_31;
  }
  if ( dword_1800C84E4 )
    RouterLogEventW(hLogHandle, 1u, 0x4E22u, 0, 0, dwErrorCode);
  return v10;
}

```

## disassembly

```asm
0x180017794  push    rbp
0x180017796  push    rbx
0x180017797  push    rsi
0x180017798  push    rdi
0x180017799  push    r12
0x18001779b  push    r13
0x18001779d  push    r14
0x18001779f  push    r15
0x1800177a1  lea     rbp, [rsp-998h]
0x1800177a9  sub     rsp, 0A98h
0x1800177b0  mov     rax, cs:__security_cookie
0x1800177b7  xor     rax, rsp
0x1800177ba  mov     [rbp+9D0h+var_50], rax
0x1800177c1  xor     r14d, r14d
0x1800177c4  mov     r15, r8
0x1800177c7  mov     esi, edx
0x1800177c9  mov     [rsp+0AD0h+cbData], r14d
0x1800177ce  mov     r13, rcx
0x1800177d1  mov     [rsp+0AD0h+Type], r14d
0x1800177d6  xor     edx, edx; Val
0x1800177d8  mov     [rbp+9D0h+var_850], r14d
0x1800177df  mov     r8d, 7FCh; Size
0x1800177e5  lea     rcx, [rbp+9D0h+var_84C]; void *
0x1800177ec  mov     r12, r9
0x1800177ef  call    memset_0
0x1800177f4  and     cs:dword_1800C84EC, 0F7FFFFF7h
0x1800177fe  lea     rcx, [rsp+0AD0h+var_A80]; void *
0x180017803  xor     edx, edx; Val
0x180017805  mov     cs:dword_1800C84E8, 1
0x18001780f  mov     r8d, 204h; Size
0x180017815  mov     cs:dword_1800C84F0, 78h ; 'x'
0x18001781f  call    memset_0
0x180017824  mov     [r15], r14d
0x180017827  lea     rdx, [rsp+0AD0h+var_A80]
0x18001782c  mov     [r12], r14d
0x180017830  cmp     cs:dword_1800C8654, r14d
0x180017837  mov     [rsp+0AD0h+phkResult], r14
0x18001783c  jnz     short loc_180017848
0x18001783e  xor     ecx, ecx
0x180017840  call    cs:__imp_RasGetProtocolInfo
0x180017846  jmp     short loc_18001784D
0x180017848  call    DdmGetProtocolInfo
0x18001784d  mov     ebx, eax
0x18001784f  test    eax, eax
0x180017851  jnz     loc_180017AA9
0x180017857  lea     r8, [rsp+0AD0h+phkResult]; phkResult
0x18001785c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180017863  lea     rdx, aSystemCurrentc_37; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x18001786a  call    cs:__imp_RegOpenKeyW
0x180017870  mov     ebx, eax
0x180017872  test    eax, eax
0x180017874  jnz     loc_180017AA9
0x18001787a  mov     edi, r14d
0x18001787d  cmp     [rsp+0AD0h+var_A80], r14d
0x180017882  jbe     short loc_1800178CE
0x180017884  mov     eax, edi
0x180017886  mov     ecx, 800h
0x18001788b  add     rax, rax
0x18001788e  cmp     [rsp+rax*8+0AD0h+var_A7C], cx
0x180017893  jz      short loc_1800178AD
0x180017895  mov     ecx, 86DDh
0x18001789a  cmp     [rsp+rax*8+0AD0h+var_A7C], cx
0x18001789f  jnz     short loc_1800178C6
0x1800178a1  mov     [rsp+0AD0h+plpszSubStringArray], r12
0x1800178a6  mov     edx, 57h ; 'W'
0x1800178ab  jmp     short loc_1800178B7
0x1800178ad  mov     [rsp+0AD0h+plpszSubStringArray], r15
0x1800178b2  mov     edx, 21h ; '!'
0x1800178b7  mov     rcx, [rsp+0AD0h+phkResult]
0x1800178bc  mov     r9d, esi
0x1800178bf  call    lProtocolEnabled
0x1800178c4  mov     ebx, eax
0x1800178c6  inc     edi
0x1800178c8  cmp     edi, [rsp+0AD0h+var_A80]
0x1800178cc  jb      short loc_180017884
0x1800178ce  mov     rcx, [rsp+0AD0h+phkResult]; hKey
0x1800178d3  call    cs:__imp_RegCloseKey
0x1800178d9  test    ebx, ebx
0x1800178db  jnz     loc_180017AA9
0x1800178e1  cmp     [r15], r14d
0x1800178e4  jnz     short loc_180017921
0x1800178e6  cmp     [r12], r14d
0x1800178ea  jnz     short loc_180017921
0x1800178ec  cmp     cs:dword_1800C84E4, r14d
0x1800178f3  jbe     loc_180017CEC
0x1800178f9  mov     rcx, cs:hLogHandle; hLogHandle
0x180017900  lea     edx, [rbx+1]; dwEventType
0x180017903  mov     [rsp+0AD0h+dwErrorCode], r14d; dwErrorCode
0x180017908  xor     r9d, r9d; dwSubStringCount
0x18001790b  mov     r8d, 4E92h; dwMessageId
0x180017911  mov     [rsp+0AD0h+plpszSubStringArray], r14; plpszSubStringArray
0x180017916  call    cs:__imp_RouterLogEventW
0x18001791c  jmp     loc_180017CEC
0x180017921  cmp     cs:?DDMRegParams@@3PAU_DDM_REGISTRY_PARAMS@@A, r14; _DDM_REGISTRY_PARAMS near * DDMRegParams
0x180017928  mov     esi, r14d
0x18001792b  jz      loc_180017A4D
0x180017931  lea     r10, ?DDMRegParams@@3PAU_DDM_REGISTRY_PARAMS@@A; _DDM_REGISTRY_PARAMS near * DDMRegParams
0x180017938  mov     edi, esi
0x18001793a  lea     rax, dword_1800C8658
0x180017941  shl     rdi, 5
0x180017945  lea     r14, [r10+10h]
0x180017949  mov     rdx, [rdi+r10+8]
0x18001794e  cmp     rax, rdx
0x180017951  jnz     short loc_18001796B
0x180017953  mov     eax, cs:dword_1800C8650
0x180017959  neg     eax
0x18001795b  sbb     ecx, ecx
0x18001795d  and     ecx, 0FFFFFFFCh
0x180017960  add     ecx, 5
0x180017963  add     r14, rdi
0x180017966  mov     [r14], ecx
0x180017969  jmp     short loc_18001796E
0x18001796b  add     r14, rdi
0x18001796e  lea     rax, [rsp+0AD0h+cbData]
0x180017973  mov     [rsp+0AD0h+cbData], 4
0x18001797b  mov     qword ptr [rsp+0AD0h+dwErrorCode], rax; lpcbData
0x180017980  lea     r9, [rsp+0AD0h+Type]; lpType
0x180017985  mov     [rsp+0AD0h+plpszSubStringArray], rdx; lpData
0x18001798a  xor     r8d, r8d; lpReserved
0x18001798d  mov     rdx, [rdi+r10]; lpValueName
0x180017991  mov     rcx, r13; hKey
0x180017994  call    cs:__imp_RegQueryValueExW
0x18001799a  xor     edx, edx
0x18001799c  mov     ebx, eax
0x18001799e  test    eax, eax
0x1800179a0  jz      short loc_1800179C4
0x1800179a2  cmp     eax, 2
0x1800179a5  jnz     loc_180017A7E
0x1800179ab  mov     eax, [r14]
0x1800179ae  lea     r10, ?DDMRegParams@@3PAU_DDM_REGISTRY_PARAMS@@A; _DDM_REGISTRY_PARAMS near * DDMRegParams
0x1800179b5  mov     rcx, [rdi+r10+8]
0x1800179ba  xor     r14d, r14d
0x1800179bd  mov     ebx, r14d
0x1800179c0  mov     [rcx], eax
0x1800179c2  jmp     short loc_180017A37
0x1800179c4  cmp     [rsp+0AD0h+Type], 4
0x1800179c9  lea     r10, ?DDMRegParams@@3PAU_DDM_REGISTRY_PARAMS@@A; _DDM_REGISTRY_PARAMS near * DDMRegParams
0x1800179d0  jnz     short loc_1800179E7
0x1800179d2  mov     rax, [rdi+r10+8]
0x1800179d7  mov     ecx, [rax]
0x1800179d9  cmp     ecx, [rdi+r10+18h]
0x1800179de  ja      short loc_1800179E7
0x1800179e0  cmp     ecx, [rdi+r10+14h]
0x1800179e5  jnb     short loc_180017A34
0x1800179e7  cmp     cs:dword_1800C84E4, 1
0x1800179ee  mov     rax, [rdi+r10]
0x1800179f2  mov     [rsp+0AD0h+var_A88], rax
0x1800179f7  jbe     short loc_180017A2A
0x1800179f9  mov     rcx, cs:hLogHandle; hLogHandle
0x180017a00  lea     rax, [rsp+0AD0h+var_A88]
0x180017a05  mov     [rsp+0AD0h+dwErrorCode], edx; dwErrorCode
0x180017a09  mov     r8d, 4E85h; dwMessageId
0x180017a0f  mov     edx, 2; dwEventType
0x180017a14  mov     [rsp+0AD0h+plpszSubStringArray], rax; plpszSubStringArray
0x180017a19  lea     r9d, [rdx-1]; dwSubStringCount
0x180017a1d  call    cs:__imp_RouterLogEventW
0x180017a23  lea     r10, ?DDMRegParams@@3PAU_DDM_REGISTRY_PARAMS@@A; _DDM_REGISTRY_PARAMS near * DDMRegParams
0x180017a2a  mov     rcx, [rdi+r10+8]
0x180017a2f  mov     eax, [r14]
0x180017a32  mov     [rcx], eax
0x180017a34  xor     r14d, r14d
0x180017a37  inc     esi
0x180017a39  mov     eax, esi
0x180017a3b  shl     rax, 5
0x180017a3f  cmp     [rax+r10], r14
0x180017a43  jnz     loc_180017938
0x180017a49  test    ebx, ebx
0x180017a4b  jnz     short loc_180017AA9
0x180017a4d  mov     eax, cs:dword_1800C84EC
0x180017a53  cmp     [r15], r14d
0x180017a56  jz      short loc_180017A61
0x180017a58  or      eax, 8
0x180017a5b  mov     cs:dword_1800C84EC, eax
0x180017a61  cmp     [r12], r14d
0x180017a65  jz      short loc_180017A71
0x180017a67  bts     eax, 1Bh
0x180017a6b  mov     cs:dword_1800C84EC, eax
0x180017a71  bt      eax, 0Ch
0x180017a75  jnb     short loc_180017ACE
0x180017a77  mov     ecx, 1
0x180017a7c  jmp     short loc_180017AD4
0x180017a7e  cmp     cs:dword_1800C84E4, edx
0x180017a84  jbe     short loc_180017AA9
0x180017a86  mov     rcx, cs:hLogHandle; hLogHandle
0x180017a8d  xor     r9d, r9d; dwSubStringCount
0x180017a90  mov     [rsp+0AD0h+dwErrorCode], eax; dwErrorCode
0x180017a94  mov     r8d, 4E22h; dwMessageId
0x180017a9a  mov     [rsp+0AD0h+plpszSubStringArray], rdx; plpszSubStringArray
0x180017a9f  lea     edx, [r9+1]; dwEventType
0x180017aa3  call    cs:__imp_RouterLogEventW
0x180017aa9  mov     eax, ebx
0x180017aab  mov     rcx, [rbp+9D0h+var_50]
0x180017ab2  xor     rcx, rsp; StackCookie
0x180017ab5  call    __security_check_cookie
0x180017aba  add     rsp, 0A98h
0x180017ac1  pop     r15
0x180017ac3  pop     r14
0x180017ac5  pop     r13
0x180017ac7  pop     r12
0x180017ac9  pop     rdi
0x180017aca  pop     rsi
0x180017acb  pop     rbx
0x180017acc  pop     rbp
0x180017acd  retn
0x180017ace  test    al, al
0x180017ad0  jns     short loc_180017ADF
0x180017ad2  xor     ecx, ecx; int
0x180017ad4  call    ?ModifyDefPolicyToForceEncryption@@YAKH@Z; ModifyDefPolicyToForceEncryption(int)
0x180017ad9  mov     eax, cs:dword_1800C84EC
0x180017adf  and     eax, 0FFFFEF7Fh
0x180017ae4  mov     dword ptr [rsp+0AD0h+Data], r14d
0x180017ae9  mov     cs:dword_1800C84EC, eax
0x180017aef  lea     r9, [rsp+0AD0h+Type]; lpType
0x180017af4  lea     rax, [rsp+0AD0h+phkResult]
0x180017af9  mov     dword ptr [rsp+0AD0h+phkResult], 4
0x180017b01  mov     qword ptr [rsp+0AD0h+dwErrorCode], rax; lpcbData
0x180017b06  lea     rdx, aIcconfigured; "IcConfigured"
0x180017b0d  lea     rax, [rsp+0AD0h+Data]
0x180017b12  mov     [rsp+0AD0h+var_A88], r14
0x180017b17  xor     r8d, r8d; lpReserved
0x180017b1a  mov     [rsp+0AD0h+plpszSubStringArray], rax; lpData
0x180017b1f  mov     rcx, r13; hKey
0x180017b22  mov     [rsp+0AD0h+Type], r14d
0x180017b27  call    cs:__imp_RegQueryValueExW
0x180017b2d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180017b31  mov     sil, 10h
0x180017b34  mov     edi, eax
0x180017b36  test    eax, eax
0x180017b38  jnz     loc_180017BE0
0x180017b3e  test    cs:byte_1800C8404, sil
0x180017b45  jz      loc_180017BCF
0x180017b4b  mov     r8d, dword ptr [rsp+0AD0h+Data]
0x180017b50  lea     rdx, aLoadddmparamet; "LoadDDMParameters: value of IcConfigure"...
0x180017b57  lea     rcx, [rbp+9D0h+var_850]
0x180017b5e  mov     word ptr [rbp+9D0h+var_850], r14w
0x180017b66  call    FormatRRASErrorString
0x180017b6b  test    cs:byte_1800C8404, sil
0x180017b72  jz      short loc_180017BCF
0x180017b74  lea     rcx, [rbp+9D0h+var_850]
0x180017b7b  mov     rax, rbx
0x180017b7e  inc     rax
0x180017b81  cmp     [rcx+rax*2], r14w
0x180017b86  jnz     short loc_180017B7E
0x180017b88  lea     eax, ds:2[rax*2]
0x180017b8f  mov     [rbp+9D0h+var_854], r14d
0x180017b96  lea     rcx, [rbp+9D0h+var_850]
0x180017b9d  mov     [rbp+9D0h+var_858], eax
0x180017ba3  lea     rax, [rbp+9D0h+var_870]
0x180017baa  mov     [rbp+9D0h+var_860], rcx
0x180017bb1  mov     r9d, 2
0x180017bb7  mov     [rsp+0AD0h+plpszSubStringArray], rax
0x180017bbc  lea     rdx, RasDdmTraceInfo
0x180017bc3  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180017bca  call    McGenEventWrite_EventWriteTransfer
0x180017bcf  cmp     dword ptr [rsp+0AD0h+Data], r14d
0x180017bd4  jz      short loc_180017BE0
0x180017bd6  mov     cs:g_fIsICConfigured, 1
0x180017be0  test    cs:byte_1800C8404, sil
0x180017be7  jz      loc_180017C73
0x180017bed  mov     r8d, cs:g_fIsICConfigured
0x180017bf4  lea     rdx, aLoadddmparamet_0; "LoadDDMParameters: g_fIsICConfigured %d"...
0x180017bfb  mov     r9d, edi
0x180017bfe  mov     word ptr [rbp+9D0h+var_850], r14w
0x180017c06  lea     rcx, [rbp+9D0h+var_850]
0x180017c0d  call    FormatRRASErrorString
0x180017c12  test    cs:byte_1800C8404, sil
0x180017c19  jz      short loc_180017C73
0x180017c1b  lea     rax, [rbp+9D0h+var_850]
0x180017c22  inc     rbx
0x180017c25  cmp     [rax+rbx*2], r14w
0x180017c2a  jnz     short loc_180017C22
0x180017c2c  lea     eax, ds:2[rbx*2]
0x180017c33  mov     [rbp+9D0h+var_854], r14d
0x180017c3a  lea     rcx, [rbp+9D0h+var_850]
0x180017c41  mov     [rbp+9D0h+var_858], eax
0x180017c47  lea     rax, [rbp+9D0h+var_870]
0x180017c4e  mov     [rbp+9D0h+var_860], rcx
0x180017c55  mov     r9d, 2
0x180017c5b  mov     [rsp+0AD0h+plpszSubStringArray], rax
0x180017c60  lea     rdx, RasDdmTraceInfo
0x180017c67  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180017c6e  call    McGenEventWrite_EventWriteTransfer
0x180017c73  lea     rax, [rsp+0AD0h+var_A88]
0x180017c78  mov     r9d, 20019h; samDesired
0x180017c7e  xor     r8d, r8d; ulOptions
0x180017c81  mov     [rsp+0AD0h+plpszSubStringArray], rax; phkResult
0x180017c86  lea     rdx, aIkev2; "IKEV2"
0x180017c8d  mov     rcx, r13; hKey
0x180017c90  call    cs:__imp_RegOpenKeyExW
0x180017c96  test    eax, eax
0x180017c98  jnz     short loc_180017CEC
0x180017c9a  mov     rcx, [rsp+0AD0h+var_A88]; hKey
0x180017c9f  lea     rax, [rsp+0AD0h+phkResult]
0x180017ca4  mov     qword ptr [rsp+0AD0h+dwErrorCode], rax; lpcbData
0x180017ca9  lea     rdx, aStrictpskpolic; "StrictPskPolicy"
0x180017cb0  lea     rax, [rsp+0AD0h+Data]
0x180017cb5  mov     dword ptr [rsp+0AD0h+phkResult], 4
0x180017cbd  xor     r9d, r9d; lpType
0x180017cc0  mov     [rsp+0AD0h+plpszSubStringArray], rax; lpData
0x180017cc5  xor     r8d, r8d; lpReserved
  ... truncated ...
```
