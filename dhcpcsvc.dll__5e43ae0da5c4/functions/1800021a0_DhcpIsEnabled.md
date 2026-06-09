# DhcpIsEnabled

- ea: `0x1800021a0`
- end: `0x18000260c`
- name: `DhcpIsEnabled`
- size: `1132`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18000c110`

## callees

- `0x1800021a0`
- `0x1800026a0`
- `0x180004170`
- `0x180004240`
- `0x1800048c0`
- `0x180005162`
- `0x1800127f0`
- `0x180012850`
- `0x1800128d0`
- `0x180012a00`
- `0x180012a40`
- `0x180012b80`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180002563`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180002563`
- `ntdll!RtlFreeUnicodeString` at `0x1800024a0`
- `ntdll!RtlFreeUnicodeString` at `0x1800024a0`
- `ntdll!RtlStringFromGUID` at `0x180002310`
- `ntdll!RtlStringFromGUID` at `0x180002310`
- `ntdll!RtlNtStatusToDosError` at `0x1800025ee`
- `ntdll!RtlNtStatusToDosError` at `0x1800025ee`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800023a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800023ca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800023a5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800023ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002405`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002405`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000241e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000242d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000241e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000242d`
- `IPHLPAPI!ConvertInterfaceNameToLuidW` at `0x180002243`
- `IPHLPAPI!ConvertInterfaceNameToLuidW` at `0x180002243`
- `NSI!NsiGetAllParametersEx` at `0x1800022cb`
- `NSI!NsiGetAllParametersEx` at `0x1800022cb`

## string_xrefs

- `0x180002397`: `System\CurrentControlSet\Services\Tcpip\Parameters\Interfaces`

## pseudocode

```c
__int64 __fastcall DhcpIsEnabled(PCWSTR SourceString, _DWORD *a2)
{
  NTSTATUS v4; // eax
  unsigned int v5; // ebx
  unsigned int AllParameters; // eax
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  unsigned int v10; // esi
  const WCHAR *Buffer; // rsi
  DWORD v12; // r14d
  unsigned int v14; // eax
  ULONG v15; // eax
  DWORD cbData; // [rsp+78h] [rbp-90h] BYREF
  DWORD Type; // [rsp+7Ch] [rbp-8Ch] BYREF
  DWORD Data; // [rsp+80h] [rbp-88h] BYREF
  NET_LUID InterfaceLuid; // [rsp+88h] [rbp-80h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-78h] BYREF
  HKEY hKey; // [rsp+98h] [rbp-70h] BYREF
  _UNICODE_STRING GuidString; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v23[8]; // [rsp+B8h] [rbp-50h] BYREF
  int v24; // [rsp+C0h] [rbp-48h]
  const NPI_MODULEID *v25; // [rsp+C8h] [rbp-40h]
  int v26; // [rsp+D0h] [rbp-38h]
  __int64 v27; // [rsp+D8h] [rbp-30h]
  NET_LUID *p_InterfaceLuid; // [rsp+E0h] [rbp-28h]
  int v29; // [rsp+E8h] [rbp-20h]
  __int64 v30; // [rsp+F0h] [rbp-18h]
  int v31; // [rsp+F8h] [rbp-10h]
  __int64 v32; // [rsp+100h] [rbp-8h]
  int v33; // [rsp+108h] [rbp+0h]
  _BYTE *v34; // [rsp+110h] [rbp+8h]
  int v35; // [rsp+118h] [rbp+10h]
  _BYTE v36[536]; // [rsp+128h] [rbp+20h] BYREF
  GUID Guid; // [rsp+340h] [rbp+238h] BYREF

  InterfaceLuid.Value = 0;
  memset_0(v36, 0, 0x238u);
  cbData = 0;
  GuidString = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_S(1028, 58, WPP_e15037783097355a5233924022d92169_Traceguids, SourceString);
  if ( !SourceString )
  {
    v5 = 87;
    goto LABEL_32;
  }
  if ( !a2 )
  {
    v5 = 87;
    goto LABEL_32;
  }
  if ( *SourceString == 123 )
    v4 = ConvertIfGuidToInterfaceLuidW(SourceString, &InterfaceLuid);
  else
    v4 = ConvertInterfaceNameToLuidW(SourceString, &InterfaceLuid);
  v5 = v4;
  if ( v4 )
  {
    if ( (xmmword_18001E1E0 & 2) != 0 )
      WPP_SF_DS(1025, 13, (unsigned int)WPP_1c950673330936d81a3de42a8ac0149e_Traceguids, v4, (__int64)SourceString);
  }
  else
  {
    memset_0(v23, 0, 0x68u);
    if ( (xmmword_18001E1E0 & 0x10) != 0 )
      WPP_SF_qqLqLLLLdd();
    v24 = 0;
    v25 = &NPI_MS_NDIS_MODULEID;
    v26 = 1;
    p_InterfaceLuid = &InterfaceLuid;
    v34 = v36;
    v29 = 8;
    v30 = 0;
    v31 = 0;
    v32 = 0;
    v33 = 0;
    v35 = 568;
    v27 = 1;
    AllParameters = NsiGetAllParametersEx(v23);
    v5 = AllParameters;
    if ( (xmmword_18001E1E0 & 0x10) != 0 )
      WPP_SF_d(1028, 11, WPP_427c3a8e92a933594072e65998df1ebc_Traceguids, AllParameters);
    if ( !v5 )
    {
      v7 = RtlStringFromGUID(&Guid, &GuidString);
      v10 = v7;
      if ( v7 >= 0 )
      {
        Buffer = GuidString.Buffer;
        if ( dword_18001E224 )
        {
          if ( dword_18001E224 != 1 )
          {
LABEL_16:
            cbData = 0;
            Type = 0;
            Data = 0;
            hKey = 0;
            phkResult = 0;
            if ( (xmmword_18001E1E0 & 0x10) != 0 )
              WPP_SF_(1028, 20, WPP_94d5010c5674399d06148e3a91870046_Traceguids);
            v12 = 0;
            if ( Buffer )
            {
              v5 = RegOpenKeyExW(
                     HKEY_LOCAL_MACHINE,
                     L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces",
                     0,
                     1u,
                     &hKey);
              if ( !v5 )
              {
                v5 = RegOpenKeyExW(hKey, Buffer, 0, 1u, &phkResult);
                if ( !v5 )
                {
                  cbData = 4;
                  v5 = RegQueryValueExW(phkResult, L"EnableDhcp", 0, &Type, (LPBYTE)&Data, &cbData);
                  if ( !v5 )
                  {
                    if ( Type == 4 )
                    {
                      v12 = Data;
                      v5 = 0;
                      if ( (xmmword_18001E1E0 & 0x10) != 0 )
                        WPP_SF_SD(
                          1028,
                          21,
                          (unsigned int)WPP_94d5010c5674399d06148e3a91870046_Traceguids,
                          (_DWORD)Buffer,
                          Data);
                    }
                    else
                    {
                      v5 = 87;
                    }
                  }
                }
              }
            }
            else
            {
              v5 = 87;
            }
            if ( phkResult )
              RegCloseKey(phkResult);
            if ( hKey )
              RegCloseKey(hKey);
            if ( (xmmword_18001E1E0 & 0x10) != 0 )
              WPP_SF_d(1028, 22, WPP_94d5010c5674399d06148e3a91870046_Traceguids, v5);
            goto LABEL_28;
          }
        }
        else
        {
          if ( !(unsigned __int8)RtlIsStateSeparationEnabled() || (unsigned int)DhcpIsXBOXSystem() )
          {
            dword_18001E224 = 2;
            goto LABEL_16;
          }
          dword_18001E224 = 1;
        }
        v14 = DhcpRegReadEnabledDhcpFromMultipleLocations(v9, v8, Buffer, &cbData);
        v12 = cbData;
        v5 = v14;
LABEL_28:
        if ( v5 - 2 <= 1 || v5 == 1168 )
        {
          *a2 = 0;
          v5 = 0;
        }
        else if ( !v5 )
        {
          *a2 = v12 == 1;
        }
        goto LABEL_32;
      }
      v15 = RtlNtStatusToDosError(v7);
      v5 = v15;
      if ( !v15 || v15 == 317 )
        v5 = v10;
    }
  }
LABEL_32:
  if ( GuidString.Buffer )
  {
    RtlFreeUnicodeString(&GuidString);
    GuidString.Buffer = 0;
  }
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_SD(1028, 59, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, (_DWORD)SourceString, v5);
  return v5;
}

```

## disassembly

```asm
0x1800021a0  mov     r11, rsp
0x1800021a3  push    rbp
0x1800021a4  push    rdi
0x1800021a5  lea     rbp, [r11-298h]
0x1800021ac  sub     rsp, 388h
0x1800021b3  mov     rax, cs:__security_cookie
0x1800021ba  xor     rax, rsp
0x1800021bd  mov     [rbp+290h+var_30], rax
0x1800021c4  mov     [r11-18h], r12
0x1800021c8  mov     rdi, rcx
0x1800021cb  mov     [r11-28h], r15
0x1800021cf  lea     rcx, [rbp+290h+var_270]; void *
0x1800021d3  mov     r15, rdx
0x1800021d6  xor     r12d, r12d
0x1800021d9  xor     edx, edx; Val
0x1800021db  mov     qword ptr [rbp+290h+InterfaceLuid], r12
0x1800021df  mov     r8d, 238h; Size
0x1800021e5  call    memset_0
0x1800021ea  xorps   xmm0, xmm0
0x1800021ed  mov     [rsp+390h+cbData], r12d
0x1800021f2  movups  xmmword ptr [rbp+290h+GuidString.Length], xmm0
0x1800021f6  test    byte ptr cs:xmmword_18001E1E0, 10h
0x1800021fd  jz      short loc_180002218
0x1800021ff  mov     edx, 3Ah ; ':'
0x180002204  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000220b  mov     ecx, 404h
0x180002210  mov     r9, rdi
0x180002213  call    WPP_SF_S
0x180002218  mov     [rsp+390h+arg_10], rbx
0x180002220  test    rdi, rdi
0x180002223  jz      loc_180002545
0x180002229  test    r15, r15
0x18000222c  jz      loc_1800025E2
0x180002232  cmp     word ptr [rdi], 7Bh ; '{'
0x180002236  lea     rdx, [rbp+290h+InterfaceLuid]; InterfaceLuid
0x18000223a  mov     rcx, rdi; SourceString
0x18000223d  jz      loc_180002559
0x180002243  call    cs:__imp_ConvertInterfaceNameToLuidW
0x180002249  mov     ebx, eax
0x18000224b  test    eax, eax
0x18000224d  jnz     loc_1800025A8
0x180002253  xor     edx, edx; Val
0x180002255  lea     rcx, [rbp+290h+var_2E0]; void *
0x180002259  mov     r8d, 68h ; 'h'; Size
0x18000225f  call    memset_0
0x180002264  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000226b  jz      short loc_18000227B
0x18000226d  lea     rax, [rbp+290h+InterfaceLuid]
0x180002271  mov     [rsp+30h], rax
0x180002276  call    WPP_SF_qqLqLLLLdd
0x18000227b  lea     rax, NPI_MS_NDIS_MODULEID
0x180002282  mov     [rbp+290h+var_2D8], r12d
0x180002286  mov     [rbp+290h+var_2D0], rax
0x18000228a  lea     rcx, [rbp+290h+var_2E0]
0x18000228e  lea     rax, [rbp+290h+InterfaceLuid]
0x180002292  mov     [rbp+290h+var_2C8], 1
0x180002299  mov     [rbp+290h+var_2B8], rax
0x18000229d  lea     rax, [rbp+290h+var_270]
0x1800022a1  mov     [rbp+290h+var_288], rax
0x1800022a5  mov     [rbp+290h+var_2B0], 8
0x1800022ac  mov     [rbp+290h+var_2A8], r12
0x1800022b0  mov     [rbp+290h+var_2A0], r12d
0x1800022b4  mov     [rbp+290h+var_298], r12
0x1800022b8  mov     [rbp+290h+var_290], r12d
0x1800022bc  mov     [rbp+290h+var_280], 238h
0x1800022c3  mov     [rbp+290h+var_2C0], 1
0x1800022cb  call    cs:__imp_NsiGetAllParametersEx
0x1800022d1  mov     ebx, eax
0x1800022d3  test    byte ptr cs:xmmword_18001E1E0, 10h
0x1800022da  jz      short loc_1800022F5
0x1800022dc  mov     edx, 0Bh
0x1800022e1  lea     r8, WPP_427c3a8e92a933594072e65998df1ebc_Traceguids
0x1800022e8  mov     ecx, 404h
0x1800022ed  mov     r9d, eax
0x1800022f0  call    WPP_SF_d
0x1800022f5  test    ebx, ebx
0x1800022f7  jnz     loc_18000248E
0x1800022fd  lea     rdx, [rbp+290h+GuidString]; GuidString
0x180002301  mov     [rsp+390h+arg_18], rsi
0x180002309  lea     rcx, [rbp+290h+Guid]; Guid
0x180002310  call    cs:__imp_RtlStringFromGUID
0x180002316  mov     esi, eax
0x180002318  test    eax, eax
0x18000231a  js      loc_1800025EC
0x180002320  mov     eax, cs:dword_18001E224
0x180002326  mov     rsi, [rbp+290h+GuidString.Buffer]
0x18000232a  mov     [rsp+390h+var_18], r14
0x180002332  test    eax, eax
0x180002334  jz      loc_180002563
0x18000233a  cmp     eax, 1
0x18000233d  jz      loc_18000258F
0x180002343  mov     [rsp+390h+cbData], r12d
0x180002348  mov     [rsp+390h+Type], r12d
0x18000234d  mov     [rsp+390h+Data], r12d
0x180002352  mov     [rbp+290h+hKey], r12
0x180002356  mov     [rbp+290h+var_308], r12
0x18000235a  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180002361  jz      short loc_180002379
0x180002363  mov     edx, 14h
0x180002368  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x18000236f  mov     ecx, 404h
0x180002374  call    WPP_SF_
0x180002379  mov     r14d, r12d
0x18000237c  test    rsi, rsi
0x18000237f  jz      loc_1800025D8
0x180002385  lea     rax, [rbp+290h+hKey]
0x180002389  mov     r9d, 1; samDesired
0x18000238f  xor     r8d, r8d; ulOptions
0x180002392  mov     [rsp+390h+phkResult], rax; phkResult
0x180002397  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\Tc"...
0x18000239e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800023a5  call    cs:__imp_RegOpenKeyExW
0x1800023ab  mov     ebx, eax
0x1800023ad  test    eax, eax
0x1800023af  jnz     short loc_180002415
0x1800023b1  mov     rcx, [rbp+290h+hKey]; hKey
0x1800023b5  lea     rax, [rbp+290h+var_308]
0x1800023b9  mov     r9d, 1; samDesired
0x1800023bf  mov     [rsp+390h+phkResult], rax; phkResult
0x1800023c4  xor     r8d, r8d; ulOptions
0x1800023c7  mov     rdx, rsi; lpSubKey
0x1800023ca  call    cs:__imp_RegOpenKeyExW
0x1800023d0  mov     ebx, eax
0x1800023d2  test    eax, eax
0x1800023d4  jnz     short loc_180002415
0x1800023d6  mov     rcx, [rbp+290h+var_308]; hKey
0x1800023da  lea     rax, [rsp+390h+cbData]
0x1800023df  mov     [rsp+390h+lpcbData], rax; lpcbData
0x1800023e4  lea     r9, [rsp+390h+Type]; lpType
0x1800023e9  lea     rax, [rsp+390h+Data]
0x1800023ee  mov     [rsp+390h+cbData], 4
0x1800023f6  xor     r8d, r8d; lpReserved
0x1800023f9  mov     [rsp+390h+phkResult], rax; lpData
0x1800023fe  lea     rdx, ValueName; "EnableDhcp"
0x180002405  call    cs:__imp_RegQueryValueExW
0x18000240b  mov     ebx, eax
0x18000240d  test    eax, eax
0x18000240f  jz      loc_180002506
0x180002415  mov     rcx, [rbp+290h+var_308]; hKey
0x180002419  test    rcx, rcx
0x18000241c  jz      short loc_180002424
0x18000241e  call    cs:__imp_RegCloseKey
0x180002424  mov     rcx, [rbp+290h+hKey]; hKey
0x180002428  test    rcx, rcx
0x18000242b  jz      short loc_180002433
0x18000242d  call    cs:__imp_RegCloseKey
0x180002433  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000243a  jz      short loc_180002455
0x18000243c  mov     edx, 16h
0x180002441  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x180002448  mov     ecx, 404h
0x18000244d  mov     r9d, ebx
0x180002450  call    WPP_SF_d
0x180002455  lea     eax, [rbx-2]
0x180002458  cmp     eax, 1
0x18000245b  jbe     loc_1800024FB
0x180002461  cmp     ebx, 490h
0x180002467  jz      loc_1800024FB
0x18000246d  test    ebx, ebx
0x18000246f  jnz     short loc_18000247E
0x180002471  mov     eax, r12d
0x180002474  cmp     r14d, 1
0x180002478  setz    al
0x18000247b  mov     [r15], eax
0x18000247e  mov     r14, [rsp+390h+var_18]
0x180002486  mov     rsi, [rsp+390h+arg_18]
0x18000248e  mov     r15, [rsp+390h+var_20]
0x180002496  cmp     [rbp+290h+GuidString.Buffer], r12
0x18000249a  jz      short loc_1800024AA
0x18000249c  lea     rcx, [rbp+290h+GuidString]; UnicodeString
0x1800024a0  call    cs:__imp_RtlFreeUnicodeString
0x1800024a6  mov     [rbp+290h+GuidString.Buffer], r12
0x1800024aa  test    byte ptr cs:xmmword_18001E1E0, 10h
0x1800024b1  mov     r12, [rsp+380h]
0x1800024b9  jz      short loc_1800024D8
0x1800024bb  mov     edx, 3Bh ; ';'
0x1800024c0  mov     dword ptr [rsp+390h+phkResult], ebx
0x1800024c4  mov     ecx, 404h
0x1800024c9  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x1800024d0  mov     r9, rdi
0x1800024d3  call    WPP_SF_SD
0x1800024d8  mov     eax, ebx
0x1800024da  mov     rbx, [rsp+390h+arg_10]
0x1800024e2  mov     rcx, [rbp+290h+var_30]
0x1800024e9  xor     rcx, rsp; StackCookie
0x1800024ec  call    __security_check_cookie
0x1800024f1  add     rsp, 388h
0x1800024f8  pop     rdi
0x1800024f9  pop     rbp
0x1800024fa  retn
0x1800024fb  mov     [r15], r12d
0x1800024fe  mov     ebx, r12d
0x180002501  jmp     loc_18000247E
0x180002506  cmp     [rsp+390h+Type], 4
0x18000250b  jnz     short loc_18000254F
0x18000250d  mov     r14d, [rsp+390h+Data]
0x180002512  mov     ebx, r12d
0x180002515  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000251c  jz      loc_180002415
0x180002522  mov     edx, 15h
0x180002527  mov     dword ptr [rsp+390h+phkResult], r14d
0x18000252c  mov     ecx, 404h
0x180002531  lea     r8, WPP_94d5010c5674399d06148e3a91870046_Traceguids
0x180002538  mov     r9, rsi
0x18000253b  call    WPP_SF_SD
0x180002540  jmp     loc_180002415
0x180002545  mov     ebx, 57h ; 'W'
0x18000254a  jmp     loc_18000248E
0x18000254f  mov     ebx, 57h ; 'W'
0x180002554  jmp     loc_180002415
0x180002559  call    ConvertIfGuidToInterfaceLuidW
0x18000255e  jmp     loc_180002249
0x180002563  call    cs:__imp_RtlIsStateSeparationEnabled
0x180002569  test    al, al
0x18000256b  jnz     short loc_18000257C
0x18000256d  mov     cs:dword_18001E224, 2
0x180002577  jmp     loc_180002343
0x18000257c  call    DhcpIsXBOXSystem
0x180002581  test    eax, eax
0x180002583  jnz     short loc_18000256D
0x180002585  mov     cs:dword_18001E224, 1
0x18000258f  lea     r9, [rsp+390h+cbData]
0x180002594  mov     r8, rsi
0x180002597  call    DhcpRegReadEnabledDhcpFromMultipleLocations
0x18000259c  mov     r14d, [rsp+390h+cbData]
0x1800025a1  mov     ebx, eax
0x1800025a3  jmp     loc_180002455
0x1800025a8  test    byte ptr cs:xmmword_18001E1E0, 2
0x1800025af  jz      loc_18000248E
0x1800025b5  mov     edx, 0Dh
0x1800025ba  mov     [rsp+390h+phkResult], rdi
0x1800025bf  mov     ecx, 401h
0x1800025c4  lea     r8, WPP_1c950673330936d81a3de42a8ac0149e_Traceguids
0x1800025cb  mov     r9d, ebx
0x1800025ce  call    WPP_SF_DS
0x1800025d3  jmp     loc_18000248E
0x1800025d8  mov     ebx, 57h ; 'W'
0x1800025dd  jmp     loc_180002415
0x1800025e2  mov     ebx, 57h ; 'W'
0x1800025e7  jmp     loc_18000248E
0x1800025ec  mov     ecx, esi; Status
0x1800025ee  call    cs:__imp_RtlNtStatusToDosError
0x1800025f4  mov     ebx, eax
0x1800025f6  test    eax, eax
0x1800025f8  jz      short loc_180002605
0x1800025fa  cmp     eax, 13Dh
0x1800025ff  jnz     loc_180002486
0x180002605  mov     ebx, esi
0x180002607  jmp     loc_180002486
```
