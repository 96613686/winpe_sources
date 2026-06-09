# NatGetIPv4FragGrouping(uchar *)

- ea: `0x18006dec8`
- end: `0x18006e1b3`
- name: `?NatGetIPv4FragGrouping@@YAEPEAE@Z`
- size: `747`
- prototype: `unsigned __int8 __fastcall(unsigned __int8 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180070598`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18004215c`
- `0x18004e0c0`
- `0x18004ed64`
- `0x18006dec8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006e119`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18006e119`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006e0b6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006e0b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e126`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e126`
- `NSI!NsiGetAllParameters` at `0x18006e042`
- `NSI!NsiGetAllParameters` at `0x18006e042`

## string_xrefs

- `0x18006df2c`: `System\CurrentControlSet\Services\SharedAccess\Parameters`

## pseudocode

```c
bool __fastcall NatGetIPv4FragGrouping(unsigned __int8 *a1)
{
  bool v1; // bl
  unsigned int AllParameters; // eax
  __int64 v3; // r9
  PVOID *v4; // rcx
  unsigned int v5; // edi
  BYTE Data[4]; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbData; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v10[160]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR ValueName[40]; // [rsp+110h] [rbp+10h] BYREF
  WCHAR SubKey[64]; // [rsp+160h] [rbp+60h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 292, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids);
  }
  wcscpy(SubKey, L"System\\CurrentControlSet\\Services\\SharedAccess\\Parameters");
  wcscpy(ValueName, L"EnableIPv4GroupForwardedFragments");
  hKey = 0;
  *(_DWORD *)Data = 0;
  cbData = 4;
  memset_0(v10, 0, 0x9Cu);
  v1 = 1;
  AllParameters = NsiGetAllParameters(1, &NPI_MS_IPV4_MODULEID, 6, 0, 0, v10, 156, 0, 0, 0, 0);
  if ( AllParameters )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        293,
        &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids,
        AllParameters);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    v1 = 0;
    goto LABEL_24;
  }
  GroupForwardedFragmentsOld = v10[112];
  if ( GroupForwardedFragmentsEnabled )
    goto LABEL_23;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey) )
  {
    v5 = RegQueryValueExW(hKey, ValueName, 0, 0, Data, &cbData);
    RegCloseKey(hKey);
    if ( v5 )
    {
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return v1;
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_24;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 295, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, v5);
    }
    else
    {
      v1 = *(_DWORD *)Data != 0;
    }
    goto LABEL_23;
  }
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v1;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 294, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids);
LABEL_23:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_24:
  if ( v4 != &WPP_GLOBAL_Control && (*((_DWORD *)v4 + 7) & 0x200) != 0 && *((_BYTE *)v4 + 25) >= 6u )
  {
    LOBYTE(v3) = v1;
    WPP_SF_c(v4[2], 296, &WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids, v3);
  }
  return v1;
}

```

## disassembly

```asm
0x18006dec8  push    rbp
0x18006deca  push    rbx
0x18006decb  push    rsi
0x18006decc  push    rdi
0x18006decd  push    r14
0x18006decf  push    r15
0x18006ded1  lea     rbp, [rsp-0F8h]
0x18006ded9  sub     rsp, 1F8h
0x18006dee0  mov     rax, cs:__security_cookie
0x18006dee7  xor     rax, rsp
0x18006deea  mov     [rbp+120h+var_40], rax
0x18006def1  mov     rcx, cs:WPP_GLOBAL_Control
0x18006def8  lea     r14, WPP_GLOBAL_Control
0x18006deff  lea     r15, WPP_032b8fef1b8e3ee883495e11f046ac7e_Traceguids
0x18006df06  mov     esi, 200h
0x18006df0b  cmp     rcx, r14
0x18006df0e  jz      short loc_18006DF2C
0x18006df10  test    [rcx+1Ch], esi
0x18006df13  jz      short loc_18006DF2C
0x18006df15  cmp     byte ptr [rcx+19h], 6
0x18006df19  jb      short loc_18006DF2C
0x18006df1b  mov     rcx, [rcx+10h]
0x18006df1f  mov     edx, 124h
0x18006df24  mov     r8, r15
0x18006df27  call    WPP_SF_
0x18006df2c  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2; "System\\CurrentControlSet\\Services\\Sh"...
0x18006df33  lea     rcx, [rsp+220h+var_1B0]; void *
0x18006df38  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+10h; "urrentControlSet\\Services\\SharedAcces"...
0x18006df3f  mov     ebx, 9Ch
0x18006df44  mov     eax, dword ptr cs:aSystemCurrentc_2+70h; "s"
0x18006df4a  mov     r8d, ebx; Size
0x18006df4d  movaps  xmmword ptr [rbp+120h+SubKey], xmm0
0x18006df51  xor     edx, edx; Val
0x18006df53  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+20h; "ntrolSet\\Services\\SharedAccess\\Param"...
0x18006df5a  movaps  [rbp+120h+var_A0], xmm0
0x18006df61  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+40h; "s\\SharedAccess\\Parameters"
0x18006df68  movaps  [rbp+120h+var_B0], xmm1
0x18006df6c  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+30h; "\\Services\\SharedAccess\\Parameters"
0x18006df73  movaps  [rbp+120h+var_80], xmm0
0x18006df7a  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_2+60h; "arameters"
0x18006df81  movaps  [rbp+120h+var_90], xmm1
0x18006df88  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_2+50h; "Access\\Parameters"
0x18006df8f  movaps  [rbp+120h+var_60], xmm0
0x18006df96  movaps  xmm0, xmmword ptr cs:aEnableipv4grou; "EnableIPv4GroupForwardedFragments"
0x18006df9d  movaps  [rbp+120h+var_70], xmm1
0x18006dfa4  movaps  xmm1, xmmword ptr cs:aEnableipv4grou+10h; "v4GroupForwardedFragments"
0x18006dfab  movaps  xmmword ptr [rbp+120h+ValueName], xmm0
0x18006dfaf  movaps  xmm0, xmmword ptr cs:aEnableipv4grou+20h; "orwardedFragments"
0x18006dfb6  movaps  [rbp+120h+var_100], xmm1
0x18006dfba  movaps  xmm1, xmmword ptr cs:aEnableipv4grou+30h; "Fragments"
0x18006dfc1  mov     [rbp+120h+var_50], eax
0x18006dfc7  mov     eax, dword ptr cs:aEnableipv4grou+40h; "s"
0x18006dfcd  movaps  [rbp+120h+var_F0], xmm0
0x18006dfd1  movaps  [rbp+120h+var_E0], xmm1
0x18006dfd5  mov     [rbp+120h+var_D0], eax
0x18006dfd8  mov     [rsp+220h+hKey], 0
0x18006dfe1  mov     dword ptr [rsp+220h+Data], 0
0x18006dfe9  mov     [rsp+220h+cbData], 4
0x18006dff1  call    memset_0
0x18006dff6  mov     [rsp+220h+var_1D0], 0
0x18006dffe  lea     rax, [rsp+220h+var_1B0]
0x18006e003  mov     [rsp+220h+var_1D8], 0
0x18006e00c  lea     rdx, NPI_MS_IPV4_MODULEID
0x18006e013  mov     [rsp+220h+var_1E0], 0
0x18006e01b  xor     r9d, r9d
0x18006e01e  mov     [rsp+220h+var_1E8], 0
0x18006e027  mov     [rsp+220h+var_1F0], ebx
0x18006e02b  mov     [rsp+220h+lpcbData], rax
0x18006e030  lea     ebx, [r9+1]
0x18006e034  mov     dword ptr [rsp+220h+phkResult], 0
0x18006e03c  mov     ecx, ebx
0x18006e03e  lea     r8d, [r9+6]
0x18006e042  call    cs:__imp_NsiGetAllParameters
0x18006e048  test    eax, eax
0x18006e04a  jz      short loc_18006E085
0x18006e04c  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e053  cmp     rcx, r14
0x18006e056  jz      short loc_18006E07E
0x18006e058  test    [rcx+1Ch], esi
0x18006e05b  jz      short loc_18006E07E
0x18006e05d  cmp     byte ptr [rcx+19h], 2
0x18006e061  jb      short loc_18006E07E
0x18006e063  mov     rcx, [rcx+10h]
0x18006e067  mov     edx, 125h
0x18006e06c  mov     r9d, eax
0x18006e06f  mov     r8, r15
0x18006e072  call    WPP_SF_d
0x18006e077  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e07e  xor     bl, bl
0x18006e080  jmp     loc_18006E16E
0x18006e085  cmp     cs:?GroupForwardedFragmentsEnabled@@3EA, 0; uchar GroupForwardedFragmentsEnabled
0x18006e08c  mov     al, [rbp+120h+var_140]
0x18006e08f  mov     cs:?GroupForwardedFragmentsOld@@3EA, al; uchar GroupForwardedFragmentsOld
0x18006e095  jnz     loc_18006E167
0x18006e09b  lea     rax, [rsp+220h+hKey]
0x18006e0a0  mov     r9d, ebx; samDesired
0x18006e0a3  xor     r8d, r8d; ulOptions
0x18006e0a6  mov     [rsp+220h+phkResult], rax; phkResult
0x18006e0ab  lea     rdx, [rbp+120h+SubKey]; lpSubKey
0x18006e0af  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006e0b6  call    cs:__imp_RegOpenKeyExW
0x18006e0bc  test    eax, eax
0x18006e0be  jz      short loc_18006E0F6
0x18006e0c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e0c7  cmp     rcx, r14
0x18006e0ca  jz      loc_18006E192
0x18006e0d0  test    [rcx+1Ch], esi
0x18006e0d3  jz      loc_18006E16E
0x18006e0d9  cmp     byte ptr [rcx+19h], 2
0x18006e0dd  jb      loc_18006E16E
0x18006e0e3  mov     rcx, [rcx+10h]
0x18006e0e7  mov     edx, 126h
0x18006e0ec  mov     r8, r15
0x18006e0ef  call    WPP_SF_
0x18006e0f4  jmp     short loc_18006E167
0x18006e0f6  mov     rcx, [rsp+220h+hKey]; hKey
0x18006e0fb  lea     rax, [rsp+220h+cbData]
0x18006e100  mov     [rsp+220h+lpcbData], rax; lpcbData
0x18006e105  lea     rdx, [rbp+120h+ValueName]; lpValueName
0x18006e109  lea     rax, [rsp+220h+Data]
0x18006e10e  xor     r9d, r9d; lpType
0x18006e111  xor     r8d, r8d; lpReserved
0x18006e114  mov     [rsp+220h+phkResult], rax; lpData
0x18006e119  call    cs:__imp_RegQueryValueExW
0x18006e11f  mov     rcx, [rsp+220h+hKey]; hKey
0x18006e124  mov     edi, eax
0x18006e126  call    cs:__imp_RegCloseKey
0x18006e12c  test    edi, edi
0x18006e12e  jz      short loc_18006E15D
0x18006e130  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e137  cmp     rcx, r14
0x18006e13a  jz      short loc_18006E192
0x18006e13c  test    [rcx+1Ch], esi
0x18006e13f  jz      short loc_18006E16E
0x18006e141  cmp     byte ptr [rcx+19h], 2
0x18006e145  jb      short loc_18006E16E
0x18006e147  mov     rcx, [rcx+10h]
0x18006e14b  mov     edx, 127h
0x18006e150  mov     r9d, edi
0x18006e153  mov     r8, r15
0x18006e156  call    WPP_SF_d
0x18006e15b  jmp     short loc_18006E167
0x18006e15d  mov     eax, dword ptr [rsp+220h+Data]
0x18006e161  neg     eax
0x18006e163  sbb     cl, cl
0x18006e165  and     bl, cl
0x18006e167  mov     rcx, cs:WPP_GLOBAL_Control
0x18006e16e  cmp     rcx, r14
0x18006e171  jz      short loc_18006E192
0x18006e173  test    [rcx+1Ch], esi
0x18006e176  jz      short loc_18006E192
0x18006e178  cmp     byte ptr [rcx+19h], 6
0x18006e17c  jb      short loc_18006E192
0x18006e17e  mov     rcx, [rcx+10h]
0x18006e182  mov     edx, 128h
0x18006e187  mov     r9b, bl
0x18006e18a  mov     r8, r15
0x18006e18d  call    WPP_SF_c
0x18006e192  mov     al, bl
0x18006e194  mov     rcx, [rbp+120h+var_40]
0x18006e19b  xor     rcx, rsp; StackCookie
0x18006e19e  call    __security_check_cookie
0x18006e1a3  add     rsp, 1F8h
0x18006e1aa  pop     r15
0x18006e1ac  pop     r14
0x18006e1ae  pop     rdi
0x18006e1af  pop     rsi
0x18006e1b0  pop     rbx
0x18006e1b1  pop     rbp
0x18006e1b2  retn
```
