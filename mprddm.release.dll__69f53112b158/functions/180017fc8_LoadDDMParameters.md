# LoadDDMParameters

- ea: `0x180017fc8`
- end: `0x18001856f`
- name: `LoadDDMParameters`
- size: `1447`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b6b0`
- `0x18001bf40`

## callees

- `0x180007c0c`
- `0x180012448`
- `0x180017fc8`
- `0x180018d8c`
- `0x180027044`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`

## import_xrefs

- `ADVAPI32!RegOpenKeyW` at `0x1800180a6`
- `ADVAPI32!RegOpenKeyW` at `0x1800180a6`
- `ADVAPI32!RegOpenKeyExW` at `0x1800184df`
- `ADVAPI32!RegOpenKeyExW` at `0x1800184df`
- `ADVAPI32!RegQueryValueExW` at `0x1800181e4`
- `ADVAPI32!RegQueryValueExW` at `0x180018375`
- `ADVAPI32!RegQueryValueExW` at `0x18001851a`
- `ADVAPI32!RegQueryValueExW` at `0x1800181e4`
- `ADVAPI32!RegQueryValueExW` at `0x180018375`
- `ADVAPI32!RegQueryValueExW` at `0x18001851a`
- `ADVAPI32!RegCloseKey` at `0x18001810e`
- `ADVAPI32!RegCloseKey` at `0x18001853d`
- `ADVAPI32!RegCloseKey` at `0x18001810e`
- `ADVAPI32!RegCloseKey` at `0x18001853d`
- `rtutils!RouterLogEventW` at `0x18001815b`
- `rtutils!RouterLogEventW` at `0x180018272`
- `rtutils!RouterLogEventW` at `0x1800182d4`
- `rtutils!RouterLogEventW` at `0x18001815b`
- `rtutils!RouterLogEventW` at `0x180018272`
- `rtutils!RouterLogEventW` at `0x1800182d4`
- `rasman!RasGetProtocolInfo` at `0x180018076`
- `rasman!RasGetProtocolInfo` at `0x180018076`

## string_xrefs

- `0x18001809f`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Parameters`
- `0x18001834e`: `IcConfigured`
- `0x1800183a6`: `LoadDDMParameters: value of IcConfigured key is %d`
- `0x180018446`: `LoadDDMParameters: g_fIsICConfigured %d dwErr %d`

## pseudocode

```c
__int64 __fastcall LoadDDMParameters(HKEY hKey, int a2, _DWORD *a3, _DWORD *a4)
{
  int v4; // edi
  HKEY v7; // r14
  __int64 v9; // rcx
  unsigned int ProtocolInfo; // eax
  unsigned int v11; // ebx
  int v12; // r8d
  unsigned int v13; // eax
  int v15; // r15d
  unsigned __int64 v16; // rbx
  HKEY *v17; // rsi
  int *v18; // rdx
  HKEY v19; // rdx
  LSTATUS dwErrorCode; // eax
  unsigned int v21; // edi
  int v22; // eax
  _DWORD *v23; // rcx
  unsigned int v24; // ecx
  int v25; // eax
  int v26; // ecx
  __int64 v27; // rbx
  unsigned int v28; // edi
  __int64 v29; // r8
  __int64 v30; // rax
  __int64 v31; // r8
  BYTE *plpszSubStringArray; // [rsp+20h] [rbp-E0h]
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  DWORD v35; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKeya; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Type[3]; // [rsp+54h] [rbp-ACh] BYREF
  _DWORD v39[132]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v40[16]; // [rsp+270h] [rbp+170h] BYREF
  int *v41; // [rsp+280h] [rbp+180h]
  int v42; // [rsp+288h] [rbp+188h]
  int v43; // [rsp+28Ch] [rbp+18Ch]
  int v44; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v45[2044]; // [rsp+294h] [rbp+194h] BYREF

  v4 = 0;
  hKeya = hKey;
  cbData = 0;
  Type[0] = 0;
  v7 = hKey;
  v44 = 0;
  memset_0(v45, 0, sizeof(v45));
  dword_1800CF4EC &= 0xF7FFFFF7;
  dword_1800CF4E8 = 1;
  dword_1800CF4F0 = 120;
  memset_0(v39, 0, 0x204u);
  *a3 = 0;
  *a4 = 0;
  phkResult = 0;
  if ( dword_1800CF654 )
    ProtocolInfo = DdmGetProtocolInfo(v9, v39);
  else
    ProtocolInfo = RasGetProtocolInfo(0, v39);
  v11 = ProtocolInfo;
  if ( ProtocolInfo )
    return v11;
  v11 = RegOpenKeyW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Parameters", &phkResult);
  if ( !v11 )
  {
    if ( v39[0] )
    {
      while ( LOWORD(v39[4 * v4 + 1]) != 2048 )
      {
        if ( LOWORD(v39[4 * v4 + 1]) == 0x86DD )
        {
          v13 = lProtocolEnabled((_DWORD)phkResult, 87, v12, a2, (__int64)a4);
LABEL_11:
          v11 = v13;
        }
        if ( (unsigned int)++v4 >= v39[0] )
          goto LABEL_13;
      }
      v13 = lProtocolEnabled((_DWORD)phkResult, 33, v12, a2, (__int64)a3);
      goto LABEL_11;
    }
LABEL_13:
    RegCloseKey(phkResult);
  }
  if ( v11 )
    return v11;
  if ( !*a3 && !*a4 )
  {
    if ( dword_1800CF4E4 )
      RouterLogEventW(hLogHandle, 1u, 0x4E92u, 0, 0, 0);
    return 0;
  }
  v15 = 0;
  if ( !DDMRegParams )
  {
LABEL_39:
    v25 = dword_1800CF4EC;
    if ( *a3 )
    {
      v25 = dword_1800CF4EC | 8;
      dword_1800CF4EC |= 8u;
    }
    if ( *a4 )
    {
      v25 |= 0x8000000u;
      dword_1800CF4EC = v25;
    }
    if ( (v25 & 0x1000) != 0 )
    {
      v26 = 1;
    }
    else
    {
      if ( (v25 & 0x80u) == 0 )
      {
LABEL_48:
        LODWORD(phkResult) = 0;
        dword_1800CF4EC = v25 & 0xFFFFEF7F;
        *(_DWORD *)Data = 0;
        hKeya = 0;
        v35 = 4;
        v27 = -1;
        v28 = RegQueryValueExW(v7, L"IcConfigured", 0, (LPDWORD)&phkResult, Data, &v35);
        if ( !v28 )
        {
          if ( (byte_1800CF404 & 0x10) != 0 )
          {
            LOWORD(v44) = 0;
            FormatRRASErrorString(&v44, L"LoadDDMParameters: value of IcConfigured key is %d", *(unsigned int *)Data);
            if ( (byte_1800CF404 & 0x10) != 0 )
            {
              v30 = -1;
              do
                ++v30;
              while ( *(_WORD *)&v45[2 * v30 - 4] );
              v43 = 0;
              v42 = 2 * v30 + 2;
              v41 = &v44;
              McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v29, 2, v40);
            }
          }
          if ( *(_DWORD *)Data )
            g_fIsICConfigured = 1;
        }
        if ( (byte_1800CF404 & 0x10) != 0 )
        {
          LOWORD(v44) = 0;
          FormatRRASErrorString(
            &v44,
            L"LoadDDMParameters: g_fIsICConfigured %d dwErr %d",
            (unsigned int)g_fIsICConfigured,
            v28);
          if ( (byte_1800CF404 & 0x10) != 0 )
          {
            do
              ++v27;
            while ( *(_WORD *)&v45[2 * v27 - 4] );
            v43 = 0;
            v42 = 2 * v27 + 2;
            v41 = &v44;
            McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceInfo, v31, 2, v40);
          }
        }
        if ( !RegOpenKeyExW(v7, L"IKEV2", 0, 0x20019u, &hKeya) )
        {
          v35 = 4;
          if ( !RegQueryValueExW(hKeya, L"StrictPskPolicy", 0, 0, Data, &v35) && *(_DWORD *)Data )
            dword_1800CF4EC |= 0x80000000;
          RegCloseKey(hKeya);
        }
        return 0;
      }
      v26 = 0;
    }
    ModifyDefPolicyToForceEncryption(v26);
    v25 = dword_1800CF4EC;
    goto LABEL_48;
  }
  v16 = 0;
  v17 = (HKEY *)&DDMRegParams;
  while ( 1 )
  {
    v18 = *(int **)((char *)&DDMRegParams + v16 + 8);
    if ( &dword_1800CF658 == v18 )
      LODWORD(qword_1800CE5D0[v16 / 8]) = dword_1800CF650 != 0 ? 1 : 5;
    plpszSubStringArray = (BYTE *)v18;
    v19 = *v17;
    cbData = 4;
    dwErrorCode = RegQueryValueExW(hKeya, (LPCWSTR)v19, 0, Type, plpszSubStringArray, &cbData);
    v21 = dwErrorCode;
    if ( dwErrorCode )
      break;
    if ( Type[0] == 4 )
    {
      v24 = **(_DWORD **)((char *)&DDMRegParams + v16 + 8);
      if ( v24 <= *(_DWORD *)((char *)&DDMRegParams + v16 + 24) && v24 >= *(_DWORD *)((char *)&DDMRegParams + v16 + 20) )
        goto LABEL_34;
    }
    phkResult = *v17;
    if ( (unsigned int)dword_1800CF4E4 > 1 )
      RouterLogEventW(hLogHandle, 2u, 0x4E85u, 1u, (LPWSTR *)&phkResult, 0);
    v23 = *(struct _DDM_REGISTRY_PARAMS near **)((char *)&DDMRegParams + v16 + 8);
    v22 = *(_DWORD *)((char *)&DDMRegParams + v16 + 16);
LABEL_33:
    *v23 = v22;
LABEL_34:
    v16 = 32LL * (unsigned int)++v15;
    v17 = (HKEY *)((char *)&DDMRegParams + v16);
    if ( !*(struct _DDM_REGISTRY_PARAMS near **)((char *)&DDMRegParams + v16) )
    {
      v7 = hKeya;
      goto LABEL_39;
    }
  }
  if ( dwErrorCode == 2 )
  {
    v22 = qword_1800CE5D0[v16 / 8];
    v23 = *(struct _DDM_REGISTRY_PARAMS near **)((char *)&DDMRegParams + v16 + 8);
    goto LABEL_33;
  }
  if ( dword_1800CF4E4 )
    RouterLogEventW(hLogHandle, 1u, 0x4E22u, 0, 0, dwErrorCode);
  return v21;
}

```

## disassembly

```asm
0x180017fc8  push    rbp
0x180017fca  push    rbx
0x180017fcb  push    rsi
0x180017fcc  push    rdi
0x180017fcd  push    r12
0x180017fcf  push    r13
0x180017fd1  push    r14
0x180017fd3  push    r15
0x180017fd5  lea     rbp, [rsp-9A8h]
0x180017fdd  sub     rsp, 0AA8h
0x180017fe4  mov     rax, cs:__security_cookie
0x180017feb  xor     rax, rsp
0x180017fee  mov     [rbp+9E0h+var_50], rax
0x180017ff5  xor     edi, edi
0x180017ff7  mov     [rsp+0AE0h+hKey], rcx
0x180017ffc  mov     r12, r8
0x180017fff  mov     [rsp+0AE0h+cbData], edi
0x180018003  mov     esi, edx
0x180018005  mov     [rsp+0AE0h+Type], edi
0x180018009  mov     r14, rcx
0x18001800c  mov     [rbp+9E0h+var_850], edi
0x180018012  xor     edx, edx; Val
0x180018014  lea     rcx, [rbp+9E0h+var_84C]; void *
0x18001801b  mov     r8d, 7FCh; Size
0x180018021  mov     r13, r9
0x180018024  call    memset_0
0x180018029  and     cs:dword_1800CF4EC, 0F7FFFFF7h
0x180018033  lea     r15d, [rdi+1]
0x180018037  xor     edx, edx; Val
0x180018039  mov     cs:dword_1800CF4E8, r15d
0x180018040  mov     r8d, 204h; Size
0x180018046  mov     cs:dword_1800CF4F0, 78h ; 'x'
0x180018050  lea     rcx, [rsp+0AE0h+var_A80]; void *
0x180018055  call    memset_0
0x18001805a  mov     [r12], edi
0x18001805e  lea     rdx, [rsp+0AE0h+var_A80]
0x180018063  mov     [r13+0], edi
0x180018067  cmp     cs:dword_1800CF654, edi
0x18001806d  mov     [rsp+0AE0h+phkResult], rdi
0x180018072  jnz     short loc_180018084
0x180018074  xor     ecx, ecx
0x180018076  call    cs:__imp_RasGetProtocolInfo
0x18001807d  nop     dword ptr [rax+rax+00h]
0x180018082  jmp     short loc_180018089
0x180018084  call    DdmGetProtocolInfo
0x180018089  mov     ebx, eax
0x18001808b  test    eax, eax
0x18001808d  jnz     loc_180018120
0x180018093  lea     r8, [rsp+0AE0h+phkResult]; phkResult
0x180018098  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001809f  lea     rdx, aSystemCurrentc_12; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x1800180a6  call    cs:__imp_RegOpenKeyW
0x1800180ad  nop     dword ptr [rax+rax+00h]
0x1800180b2  mov     ebx, eax
0x1800180b4  test    eax, eax
0x1800180b6  jnz     short loc_18001811C
0x1800180b8  cmp     [rsp+0AE0h+var_A80], edi
0x1800180bc  jbe     short loc_180018109
0x1800180be  mov     eax, edi
0x1800180c0  mov     ecx, 800h
0x1800180c5  add     rax, rax
0x1800180c8  cmp     [rsp+rax*8+0AE0h+var_A7C], cx
0x1800180cd  jz      short loc_1800180E7
0x1800180cf  mov     ecx, 86DDh
0x1800180d4  cmp     [rsp+rax*8+0AE0h+var_A7C], cx
0x1800180d9  jnz     short loc_180018100
0x1800180db  mov     [rsp+0AE0h+plpszSubStringArray], r13
0x1800180e0  mov     edx, 57h ; 'W'
0x1800180e5  jmp     short loc_1800180F1
0x1800180e7  mov     [rsp+0AE0h+plpszSubStringArray], r12
0x1800180ec  mov     edx, 21h ; '!'
0x1800180f1  mov     rcx, [rsp+0AE0h+phkResult]
0x1800180f6  mov     r9d, esi
0x1800180f9  call    lProtocolEnabled
0x1800180fe  mov     ebx, eax
0x180018100  add     edi, r15d
0x180018103  cmp     edi, [rsp+0AE0h+var_A80]
0x180018107  jb      short loc_1800180BE
0x180018109  mov     rcx, [rsp+0AE0h+phkResult]; hKey
0x18001810e  call    cs:__imp_RegCloseKey
0x180018115  nop     dword ptr [rax+rax+00h]
0x18001811a  xor     edi, edi
0x18001811c  test    ebx, ebx
0x18001811e  jz      short loc_180018127
0x180018120  mov     eax, ebx
0x180018122  jmp     loc_18001854B
0x180018127  cmp     [r12], edi
0x18001812b  jnz     short loc_18001816C
0x18001812d  cmp     [r13+0], edi
0x180018131  jnz     short loc_18001816C
0x180018133  cmp     cs:dword_1800CF4E4, edi
0x180018139  jbe     loc_180018549
0x18001813f  mov     rcx, cs:hLogHandle; hLogHandle
0x180018146  xor     r9d, r9d; dwSubStringCount
0x180018149  mov     [rsp+0AE0h+dwErrorCode], edi; dwErrorCode
0x18001814d  mov     r8d, 4E92h; dwMessageId
0x180018153  mov     edx, r15d; dwEventType
0x180018156  mov     [rsp+0AE0h+plpszSubStringArray], rdi; plpszSubStringArray
0x18001815b  call    cs:__imp_RouterLogEventW
0x180018162  nop     dword ptr [rax+rax+00h]
0x180018167  jmp     loc_180018549
0x18001816c  cmp     cs:?DDMRegParams@@3PAU_DDM_REGISTRY_PARAMS@@A, rdi; _DDM_REGISTRY_PARAMS near * DDMRegParams
0x180018173  mov     r15d, edi
0x180018176  jz      loc_1800182E9
0x18001817c  lea     r14, ?DDMRegParams@@3PAU_DDM_REGISTRY_PARAMS@@A; _DDM_REGISTRY_PARAMS near * DDMRegParams
0x180018183  mov     rbx, rdi
0x180018186  mov     rsi, r14
0x180018189  mov     rdx, [rbx+r14+8]
0x18001818e  lea     rax, dword_1800CF658
0x180018195  cmp     rax, rdx
0x180018198  jnz     short loc_1800181B6
0x18001819a  mov     eax, cs:dword_1800CF650
0x1800181a0  neg     eax
0x1800181a2  sbb     ecx, ecx
0x1800181a4  add     r14, 10h
0x1800181a8  and     ecx, 0FFFFFFFCh
0x1800181ab  add     ecx, 5
0x1800181ae  add     r14, rbx
0x1800181b1  mov     [r14], ecx
0x1800181b4  jmp     short loc_1800181BD
0x1800181b6  add     r14, 10h
0x1800181ba  add     r14, rbx
0x1800181bd  mov     rcx, [rsp+0AE0h+hKey]; hKey
0x1800181c2  lea     rax, [rsp+0AE0h+cbData]
0x1800181c7  mov     qword ptr [rsp+0AE0h+dwErrorCode], rax; dwErrorCode
0x1800181cc  lea     r9, [rsp+0AE0h+Type]; lpType
0x1800181d1  mov     [rsp+0AE0h+plpszSubStringArray], rdx; plpszSubStringArray
0x1800181d6  xor     r8d, r8d; lpReserved
0x1800181d9  mov     rdx, [rsi]; lpValueName
0x1800181dc  mov     [rsp+0AE0h+cbData], 4
0x1800181e4  call    cs:__imp_RegQueryValueExW
0x1800181eb  nop     dword ptr [rax+rax+00h]
0x1800181f0  mov     edi, eax
0x1800181f2  test    eax, eax
0x1800181f4  jz      short loc_180018219
0x1800181f6  cmp     eax, 2
0x1800181f9  jnz     loc_1800182AD
0x1800181ff  mov     eax, [r14]
0x180018202  lea     rcx, ?DDMRegParams@@3PAU_DDM_REGISTRY_PARAMS@@A; _DDM_REGISTRY_PARAMS near * DDMRegParams
0x180018209  mov     rcx, [rbx+rcx+8]
0x18001820e  lea     r14, ?DDMRegParams@@3PAU_DDM_REGISTRY_PARAMS@@A; _DDM_REGISTRY_PARAMS near * DDMRegParams
0x180018215  xor     edi, edi
0x180018217  jmp     short loc_180018288
0x180018219  cmp     [rsp+0AE0h+Type], 4
0x18001821e  lea     r14, ?DDMRegParams@@3PAU_DDM_REGISTRY_PARAMS@@A; _DDM_REGISTRY_PARAMS near * DDMRegParams
0x180018225  jnz     short loc_18001823C
0x180018227  mov     rax, [rbx+r14+8]
0x18001822c  mov     ecx, [rax]
0x18001822e  cmp     ecx, [rbx+r14+18h]
0x180018233  ja      short loc_18001823C
0x180018235  cmp     ecx, [rbx+r14+14h]
0x18001823a  jnb     short loc_18001828A
0x18001823c  cmp     cs:dword_1800CF4E4, 1
0x180018243  mov     rax, [rsi]
0x180018246  mov     [rsp+0AE0h+phkResult], rax
0x18001824b  jbe     short loc_18001827E
0x18001824d  and     [rsp+0AE0h+dwErrorCode], 0
0x180018252  lea     rax, [rsp+0AE0h+phkResult]
0x180018257  mov     rcx, cs:hLogHandle; hLogHandle
0x18001825e  mov     edx, 2; dwEventType
0x180018263  mov     r8d, 4E85h; dwMessageId
0x180018269  mov     [rsp+0AE0h+plpszSubStringArray], rax; plpszSubStringArray
0x18001826e  lea     r9d, [rdx-1]; dwSubStringCount
0x180018272  call    cs:__imp_RouterLogEventW
0x180018279  nop     dword ptr [rax+rax+00h]
0x18001827e  mov     rcx, [rbx+r14+8]
0x180018283  mov     eax, [rbx+r14+10h]
0x180018288  mov     [rcx], eax
0x18001828a  inc     r15d
0x18001828d  mov     ebx, r15d
0x180018290  shl     rbx, 5
0x180018294  lea     rsi, [rbx+r14]
0x180018298  cmp     qword ptr [rsi], 0
0x18001829c  jnz     loc_180018189
0x1800182a2  test    edi, edi
0x1800182a4  jz      short loc_1800182E2
0x1800182a6  mov     eax, edi
0x1800182a8  jmp     loc_18001854B
0x1800182ad  cmp     cs:dword_1800CF4E4, 0
0x1800182b4  jbe     short loc_1800182A6
0x1800182b6  mov     rcx, cs:hLogHandle; hLogHandle
0x1800182bd  xor     r9d, r9d; dwSubStringCount
0x1800182c0  mov     [rsp+0AE0h+dwErrorCode], eax; dwErrorCode
0x1800182c4  mov     r8d, 4E22h; dwMessageId
0x1800182ca  and     [rsp+0AE0h+plpszSubStringArray], 0
0x1800182d0  lea     edx, [r9+1]; dwEventType
0x1800182d4  call    cs:__imp_RouterLogEventW
0x1800182db  nop     dword ptr [rax+rax+00h]
0x1800182e0  jmp     short loc_1800182A6
0x1800182e2  mov     r14, [rsp+0AE0h+hKey]
0x1800182e7  xor     edi, edi
0x1800182e9  mov     eax, cs:dword_1800CF4EC
0x1800182ef  cmp     [r12], edi
0x1800182f3  jz      short loc_1800182FE
0x1800182f5  or      eax, 8
0x1800182f8  mov     cs:dword_1800CF4EC, eax
0x1800182fe  cmp     [r13+0], edi
0x180018302  jz      short loc_18001830E
0x180018304  bts     eax, 1Bh
0x180018308  mov     cs:dword_1800CF4EC, eax
0x18001830e  bt      eax, 0Ch
0x180018312  jnb     short loc_18001831B
0x180018314  mov     ecx, 1
0x180018319  jmp     short loc_180018321
0x18001831b  test    al, al
0x18001831d  jns     short loc_18001832C
0x18001831f  xor     ecx, ecx; int
0x180018321  call    ?ModifyDefPolicyToForceEncryption@@YAKH@Z; ModifyDefPolicyToForceEncryption(int)
0x180018326  mov     eax, cs:dword_1800CF4EC
0x18001832c  and     eax, 0FFFFEF7Fh
0x180018331  mov     dword ptr [rsp+0AE0h+phkResult], edi
0x180018335  mov     cs:dword_1800CF4EC, eax
0x18001833b  lea     r9, [rsp+0AE0h+phkResult]; lpType
0x180018340  lea     rax, [rsp+0AE0h+var_AA0]
0x180018345  mov     dword ptr [rsp+0AE0h+Data], edi
0x180018349  mov     qword ptr [rsp+0AE0h+dwErrorCode], rax; lpcbData
0x18001834e  lea     rdx, aIcconfigured; "IcConfigured"
0x180018355  lea     rax, [rsp+0AE0h+Data]
0x18001835a  mov     [rsp+0AE0h+hKey], rdi
0x18001835f  mov     r12d, 4
0x180018365  mov     [rsp+0AE0h+plpszSubStringArray], rax; lpData
0x18001836a  xor     r8d, r8d; lpReserved
0x18001836d  mov     [rsp+0AE0h+var_AA0], r12d
0x180018372  mov     rcx, r14; hKey
0x180018375  call    cs:__imp_RegQueryValueExW
0x18001837c  nop     dword ptr [rax+rax+00h]
0x180018381  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180018385  xor     esi, esi
0x180018387  mov     edi, eax
0x180018389  mov     r15b, 10h
0x18001838c  test    eax, eax
0x18001838e  jnz     loc_180018432
0x180018394  test    cs:byte_1800CF404, r15b
0x18001839b  jz      loc_180018422
0x1800183a1  mov     r8d, dword ptr [rsp+0AE0h+Data]
0x1800183a6  lea     rdx, aLoadddmparamet; "LoadDDMParameters: value of IcConfigure"...
0x1800183ad  lea     rcx, [rbp+9E0h+var_850]
0x1800183b4  mov     word ptr [rbp+9E0h+var_850], si
0x1800183bb  call    FormatRRASErrorString
0x1800183c0  test    cs:byte_1800CF404, r15b
0x1800183c7  jz      short loc_180018422
0x1800183c9  lea     rcx, [rbp+9E0h+var_850]
0x1800183d0  mov     rax, rbx
0x1800183d3  inc     rax
0x1800183d6  cmp     [rcx+rax*2], si
0x1800183da  jnz     short loc_1800183D3
0x1800183dc  lea     eax, ds:2[rax*2]
0x1800183e3  mov     [rbp+9E0h+var_854], esi
0x1800183e9  lea     rcx, [rbp+9E0h+var_850]
0x1800183f0  mov     [rbp+9E0h+var_858], eax
0x1800183f6  lea     rax, [rbp+9E0h+var_870]
0x1800183fd  mov     [rbp+9E0h+var_860], rcx
0x180018404  mov     r9d, 2
0x18001840a  mov     [rsp+0AE0h+plpszSubStringArray], rax
0x18001840f  lea     rdx, RasDdmTraceInfo
0x180018416  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001841d  call    McGenEventWrite_EventWriteTransfer
0x180018422  cmp     dword ptr [rsp+0AE0h+Data], esi
0x180018426  jz      short loc_180018432
0x180018428  mov     cs:g_fIsICConfigured, 1
0x180018432  test    cs:byte_1800CF404, r15b
0x180018439  jz      loc_1800184C2
0x18001843f  mov     r8d, cs:g_fIsICConfigured
0x180018446  lea     rdx, aLoadddmparamet_0; "LoadDDMParameters: g_fIsICConfigured %d"...
0x18001844d  mov     r9d, edi
0x180018450  mov     word ptr [rbp+9E0h+var_850], si
0x180018457  lea     rcx, [rbp+9E0h+var_850]
0x18001845e  call    FormatRRASErrorString
0x180018463  test    cs:byte_1800CF404, r15b
0x18001846a  jz      short loc_1800184C2
0x18001846c  lea     rax, [rbp+9E0h+var_850]
0x180018473  inc     rbx
0x180018476  cmp     [rax+rbx*2], si
0x18001847a  jnz     short loc_180018473
0x18001847c  lea     eax, ds:2[rbx*2]
0x180018483  mov     [rbp+9E0h+var_854], esi
0x180018489  lea     rcx, [rbp+9E0h+var_850]
0x180018490  mov     [rbp+9E0h+var_858], eax
0x180018496  lea     rax, [rbp+9E0h+var_870]
0x18001849d  mov     [rbp+9E0h+var_860], rcx
0x1800184a4  mov     r9d, 2
0x1800184aa  mov     [rsp+0AE0h+plpszSubStringArray], rax
0x1800184af  lea     rdx, RasDdmTraceInfo
0x1800184b6  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800184bd  call    McGenEventWrite_EventWriteTransfer
0x1800184c2  lea     rax, [rsp+0AE0h+hKey]
0x1800184c7  mov     r9d, 20019h; samDesired
0x1800184cd  xor     r8d, r8d; ulOptions
0x1800184d0  mov     [rsp+0AE0h+plpszSubStringArray], rax; phkResult
0x1800184d5  lea     rdx, aIkev2; "IKEV2"
0x1800184dc  mov     rcx, r14; hKey
0x1800184df  call    cs:__imp_RegOpenKeyExW
0x1800184e6  nop     dword ptr [rax+rax+00h]
0x1800184eb  test    eax, eax
0x1800184ed  jnz     short loc_180018549
0x1800184ef  mov     rcx, [rsp+0AE0h+hKey]; hKey
0x1800184f4  lea     rax, [rsp+0AE0h+var_AA0]
0x1800184f9  mov     qword ptr [rsp+0AE0h+dwErrorCode], rax; lpcbData
0x1800184fe  lea     rdx, aStrictpskpolic; "StrictPskPolicy"
0x180018505  lea     rax, [rsp+0AE0h+Data]
  ... truncated ...
```
