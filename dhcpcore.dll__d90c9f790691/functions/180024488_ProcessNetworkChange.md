# ProcessNetworkChange

- ea: `0x180024488`
- end: `0x1800249e5`
- name: `ProcessNetworkChange`
- size: `1373`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021128`

## callees

- `0x180003910`
- `0x180009174`
- `0x18000a100`
- `0x180012ef0`
- `0x180013398`
- `0x180016458`
- `0x18001ade4`
- `0x18001bb80`
- `0x18001d826`
- `0x1800205e4`
- `0x180023684`
- `0x180024488`
- `0x1800368d0`
- `0x18004a114`
- `0x18004d1a0`
- `0x18004d1e0`

## import_xrefs

- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800245d0`
- `api-ms-win-crt-time-l1-1-0!_time64` at `0x1800245d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024924`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024924`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002454e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002454e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002458f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002458f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180024675`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800248e1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180024675`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800248e1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800245d9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800247c8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800245d9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800247c8`

## pseudocode

```c
__int64 __fastcall ProcessNetworkChange(__int64 a1, const WCHAR *a2, __int64 a3, int a4)
{
  int v8; // edx
  int v9; // ecx
  unsigned int v10; // ebx
  __int64 v11; // rsi
  unsigned __int64 v12; // r12
  __time64_t v13; // rbx
  __int64 v14; // rax
  int v15; // edx
  int v16; // ecx
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  __int64 v20; // rdx
  unsigned int v21; // eax
  __int64 v22; // r9
  ULONGLONG v23; // rcx
  int v24; // ecx
  unsigned int v25; // eax
  unsigned int v26; // eax
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  _OWORD v30[17]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+170h] [rbp+70h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  *(_DWORD *)Data = 0;
  memset_0(v30, 0, 0xC8u);
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_SJ(1028, 172, (unsigned int)WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, a4, *(_QWORD *)(a1 + 24));
  if ( (unsigned int)DhcpIsFSEGuestSystem() )
  {
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_(1028, 173, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids);
    return 0;
  }
  if ( RegOpenKeyExW(*(HKEY *)(a1 + 728), a2, 0, 0xFu, &hKey) )
  {
    hKey = 0;
    if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 1) != 0 )
      McTemplateU0zzq_EtwEventWriteTransfer(v9, v8, a4, (_DWORD)a2, *(_DWORD *)(a1 + 48));
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_(1028, 186, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids);
    v26 = DhcpSaveInterfaceConfiguration(a1);
    if ( v26 && (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_D(1028, 187, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, v26);
    *(_DWORD *)(a1 + 776) = 1;
    v19 = DhcpUnplumbOldConfig(a1);
    v10 = v19;
    if ( v19 )
    {
      if ( (xmmword_1800616A0 & 0x10) == 0 )
        goto LABEL_57;
      v20 = 188;
      goto LABEL_36;
    }
    goto LABEL_56;
  }
  Type = 0;
  cbData = 4;
  v10 = RegQueryValueExW(hKey, L"LeaseTerminatesTime", 0, &Type, Data, &cbData);
  if ( v10 )
  {
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_(1028, 174, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids);
    goto LABEL_57;
  }
  v11 = *(unsigned int *)Data;
  v12 = 0xFFFFFFFFLL;
  if ( *(_DWORD *)Data != -1 )
  {
    v13 = _time64(0);
    v12 = 0;
    v14 = v11 + GetTickCount64() / 0x3E8 - v13;
    if ( v14 >= 0 )
      v12 = v14;
  }
  if ( (unsigned int)MatchClientIdentifier(hKey, a1) )
  {
    *(_DWORD *)(a1 + 1924) = 1;
    if ( Microsoft_Windows_Dhcp_ClientEnableBits < 0 )
      McTemplateU0zzqbr2_EtwEventWriteTransfer(
        v16,
        (unsigned int)NetworkHintMatchFound,
        a4,
        (_DWORD)a2,
        *(_DWORD *)(a1 + 96),
        *(_QWORD *)(a1 + 88));
    v21 = DhcpSaveInterfaceConfiguration(a1);
    if ( v21 && (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_D(1028, 179, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, v21);
    *(_DWORD *)(a1 + 776) = 1;
    v19 = DhcpUnplumbOldConfig(a1);
    v10 = v19;
    if ( v19 )
    {
      if ( (xmmword_1800616A0 & 0x10) != 0 )
      {
        v20 = 180;
        goto LABEL_36;
      }
      goto LABEL_57;
    }
    v19 = DhcpCopyToCurrentContext(a1, a2);
    v10 = v19;
    if ( v19 )
    {
      if ( (xmmword_1800616A0 & 0x10) == 0 )
        goto LABEL_57;
      v20 = 181;
      goto LABEL_36;
    }
    RefillDhcpContext(a1);
    v23 = GetTickCount64() / 0x3E8;
    if ( v23 <= v12 )
    {
      DhcpCopyExistingStackParams(a1, v30);
      v19 = ApplyDhcpConfigurationToNIC(a1, (__int64)v30, 1);
      v10 = v19;
      if ( !v19 )
      {
        if ( Microsoft_Windows_Dhcp_ClientEnableBits < 0 )
          McTemplateU0zzqbr2_EtwEventWriteTransfer(
            v24,
            (unsigned int)MatchedAddressPlumbed,
            a4,
            (_DWORD)a2,
            *(_DWORD *)(a1 + 96),
            *(_QWORD *)(a1 + 88));
        *(_DWORD *)(a1 + 776) = 0;
        if ( (xmmword_1800616A0 & 0x10) == 0 )
          goto LABEL_57;
        v22 = *(unsigned int *)(a1 + 120);
        v20 = 183;
        goto LABEL_37;
      }
      if ( (xmmword_1800616A0 & 0x10) == 0 )
        goto LABEL_57;
      v20 = 182;
LABEL_36:
      v22 = v19;
LABEL_37:
      WPP_SF_D(1028, v20, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, v22);
      goto LABEL_57;
    }
    if ( Microsoft_Windows_Dhcp_ClientEnableBits < 0 )
      McTemplateU0zzqbr2_EtwEventWriteTransfer(
        v23,
        (unsigned int)MatchedAddressNotPlumbed,
        a4,
        (_DWORD)a2,
        *(_DWORD *)(a1 + 96),
        *(_QWORD *)(a1 + 88));
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_D(1028, 184, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, *(unsigned int *)(a1 + 132));
    v25 = RegDeleteKeyExW(*(HKEY *)(a1 + 728), a2, 0, 0);
    v10 = v25;
    if ( v25 && (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_D(1028, 185, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, v25);
LABEL_56:
    *(_DWORD *)(a1 + 120) = 0;
    *(_DWORD *)(a1 + 132) = 0;
    goto LABEL_57;
  }
  if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 1) != 0 )
    McTemplateU0zzq_EtwEventWriteTransfer(v16, v15, a4, (_DWORD)a2, *(_DWORD *)(a1 + 48));
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 175, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids);
  v17 = RegDeleteKeyExW(*(HKEY *)(a1 + 728), a2, 0, 0);
  if ( v17 && (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 176, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, v17);
  v18 = DhcpSaveInterfaceConfiguration(a1);
  if ( v18 && (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 177, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, v18);
  *(_DWORD *)(a1 + 776) = 1;
  v19 = DhcpUnplumbOldConfig(a1);
  v10 = v19;
  if ( !v19 )
    goto LABEL_56;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
  {
    v20 = 178;
    goto LABEL_36;
  }
LABEL_57:
  if ( hKey )
    RegCloseKey(hKey);
  DhcpCleanParsedOptions((char *)v30);
  return v10;
}

```

## disassembly

```asm
0x180024488  mov     [rsp-8+cbData], r8d
0x18002448d  push    rbp
0x18002448e  push    rbx
0x18002448f  push    rsi
0x180024490  push    rdi
0x180024491  push    r12
0x180024493  push    r13
0x180024495  push    r14
0x180024497  push    r15
0x180024499  lea     rbp, [rsp-18h]
0x18002449e  sub     rsp, 118h
0x1800244a5  xor     r13d, r13d
0x1800244a8  mov     r14, rdx
0x1800244ab  mov     rdi, rcx
0x1800244ae  mov     [rsp+150h+hKey], r13
0x1800244b3  xor     edx, edx; Val
0x1800244b5  mov     [rsp+150h+Type], r13d
0x1800244ba  lea     rcx, [rsp+150h+var_110]; void *
0x1800244bf  mov     [rbp+50h+cbData], r13d
0x1800244c3  mov     r8d, 0C8h; Size
0x1800244c9  mov     dword ptr [rsp+150h+Data], r13d
0x1800244ce  mov     r15, r9
0x1800244d1  call    memset_0
0x1800244d6  mov     r12b, 10h
0x1800244d9  lea     rsi, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x1800244e0  test    byte ptr cs:xmmword_1800616A0, r12b
0x1800244e7  mov     ebx, 404h
0x1800244ec  jz      short loc_180024509
0x1800244ee  mov     rax, [rdi+18h]
0x1800244f2  mov     edx, 0ACh
0x1800244f7  mov     ecx, ebx
0x1800244f9  mov     [rsp+150h+phkResult], rax
0x1800244fe  mov     r9, r15
0x180024501  mov     r8, rsi
0x180024504  call    WPP_SF_SJ
0x180024509  call    DhcpIsFSEGuestSystem
0x18002450e  test    eax, eax
0x180024510  jz      short loc_180024531
0x180024512  test    byte ptr cs:xmmword_1800616A0, r12b
0x180024519  jz      short loc_18002452A
0x18002451b  mov     edx, 0ADh
0x180024520  mov     ecx, ebx
0x180024522  mov     r8, rsi
0x180024525  call    WPP_SF_
0x18002452a  xor     eax, eax
0x18002452c  jmp     loc_180024936
0x180024531  mov     rcx, [rdi+2D8h]; hKey
0x180024538  lea     rax, [rsp+150h+hKey]
0x18002453d  mov     r9d, 0Fh; samDesired
0x180024543  mov     [rsp+150h+phkResult], rax; phkResult
0x180024548  xor     r8d, r8d; ulOptions
0x18002454b  mov     rdx, r14; lpSubKey
0x18002454e  call    cs:__imp_RegOpenKeyExW
0x180024554  test    eax, eax
0x180024556  jnz     loc_18002494A
0x18002455c  mov     rcx, [rsp+150h+hKey]; hKey
0x180024561  lea     rax, [rbp+50h+cbData]
0x180024565  mov     [rsp+150h+lpcbData], rax; lpcbData
0x18002456a  lea     r9, [rsp+150h+Type]; lpType
0x18002456f  lea     rax, [rsp+150h+Data]
0x180024574  mov     [rsp+150h+Type], r13d
0x180024579  xor     r8d, r8d; lpReserved
0x18002457c  mov     [rsp+150h+phkResult], rax; lpData
0x180024581  lea     rdx, aLeaseterminate; "LeaseTerminatesTime"
0x180024588  mov     [rbp+50h+cbData], 4
0x18002458f  call    cs:__imp_RegQueryValueExW
0x180024595  mov     ebx, eax
0x180024597  test    eax, eax
0x180024599  jz      short loc_1800245BF
0x18002459b  test    byte ptr cs:xmmword_1800616A0, r12b
0x1800245a2  jz      loc_18002491A
0x1800245a8  mov     edx, 0AEh
0x1800245ad  mov     ecx, 404h
0x1800245b2  mov     r8, rsi
0x1800245b5  call    WPP_SF_
0x1800245ba  jmp     loc_18002491A
0x1800245bf  mov     esi, dword ptr [rsp+150h+Data]
0x1800245c3  mov     r12d, 0FFFFFFFFh
0x1800245c9  cmp     esi, r12d
0x1800245cc  jz      short loc_18002460A
0x1800245ce  xor     ecx, ecx; Time
0x1800245d0  call    cs:__imp__time64
0x1800245d6  mov     rbx, rax
0x1800245d9  call    cs:__imp_GetTickCount64
0x1800245df  mov     r8, rax
0x1800245e2  mov     r12, r13
0x1800245e5  mov     rax, 624DD2F1A9FBE77h
0x1800245ef  mul     r8
0x1800245f2  sub     r8, rdx
0x1800245f5  shr     r8, 1
0x1800245f8  lea     rax, [rdx+r8]
0x1800245fc  shr     rax, 9
0x180024600  sub     rax, rbx
0x180024603  add     rax, rsi
0x180024606  cmovns  r12, rax
0x18002460a  mov     rcx, [rsp+150h+hKey]
0x18002460f  mov     rdx, rdi
0x180024612  call    MatchClientIdentifier
0x180024617  mov     esi, 1
0x18002461c  test    eax, eax
0x18002461e  jnz     loc_1800246FD
0x180024624  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, sil
0x18002462b  jz      short loc_18002463F
0x18002462d  mov     eax, [rdi+30h]
0x180024630  mov     r9, r14
0x180024633  mov     r8, r15
0x180024636  mov     dword ptr [rsp+150h+phkResult], eax
0x18002463a  call    McTemplateU0zzq_EtwEventWriteTransfer
0x18002463f  mov     r15b, 10h
0x180024642  mov     r12d, 404h
0x180024648  test    byte ptr cs:xmmword_1800616A0, r15b
0x18002464f  jz      short loc_180024665
0x180024651  mov     edx, 0AFh
0x180024656  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x18002465d  mov     ecx, r12d
0x180024660  call    WPP_SF_
0x180024665  mov     rcx, [rdi+2D8h]; hKey
0x18002466c  xor     r9d, r9d; Reserved
0x18002466f  xor     r8d, r8d; samDesired
0x180024672  mov     rdx, r14; lpSubKey
0x180024675  call    cs:__imp_RegDeleteKeyExW
0x18002467b  test    eax, eax
0x18002467d  jz      short loc_18002469F
0x18002467f  test    byte ptr cs:xmmword_1800616A0, r15b
0x180024686  jz      short loc_18002469F
0x180024688  mov     edx, 0B0h
0x18002468d  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x180024694  mov     ecx, r12d
0x180024697  mov     r9d, eax
0x18002469a  call    WPP_SF_D
0x18002469f  mov     rcx, rdi
0x1800246a2  call    DhcpSaveInterfaceConfiguration
0x1800246a7  test    eax, eax
0x1800246a9  jz      short loc_1800246CB
0x1800246ab  test    byte ptr cs:xmmword_1800616A0, r15b
0x1800246b2  jz      short loc_1800246CB
0x1800246b4  mov     edx, 0B1h
0x1800246b9  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x1800246c0  mov     ecx, r12d
0x1800246c3  mov     r9d, eax
0x1800246c6  call    WPP_SF_D
0x1800246cb  mov     rcx, rdi
0x1800246ce  mov     [rdi+308h], esi
0x1800246d4  call    DhcpUnplumbOldConfig
0x1800246d9  mov     ebx, eax
0x1800246db  test    eax, eax
0x1800246dd  jz      loc_18002490F
0x1800246e3  test    byte ptr cs:xmmword_1800616A0, r15b
0x1800246ea  jz      loc_18002491A
0x1800246f0  mov     edx, 0B2h
0x1800246f5  mov     ecx, r12d
0x1800246f8  jmp     loc_180024787
0x1800246fd  mov     [rdi+784h], esi
0x180024703  cmp     cs:Microsoft_Windows_Dhcp_ClientEnableBits, r13b
0x18002470a  jge     short loc_18002472E
0x18002470c  mov     rax, [rdi+58h]
0x180024710  lea     rdx, NetworkHintMatchFound
0x180024717  mov     [rsp+150h+lpcbData], rax
0x18002471c  mov     r9, r14
0x18002471f  mov     eax, [rdi+60h]
0x180024722  mov     r8, r15
0x180024725  mov     dword ptr [rsp+150h+phkResult], eax
0x180024729  call    McTemplateU0zzqbr2_EtwEventWriteTransfer
0x18002472e  mov     rcx, rdi
0x180024731  call    DhcpSaveInterfaceConfiguration
0x180024736  test    eax, eax
0x180024738  jz      short loc_18002475C
0x18002473a  test    byte ptr cs:xmmword_1800616A0, 10h
0x180024741  jz      short loc_18002475C
0x180024743  mov     edx, 0B3h
0x180024748  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x18002474f  mov     ecx, 404h
0x180024754  mov     r9d, eax
0x180024757  call    WPP_SF_D
0x18002475c  mov     rcx, rdi
0x18002475f  mov     [rdi+308h], esi
0x180024765  call    DhcpUnplumbOldConfig
0x18002476a  mov     ebx, eax
0x18002476c  test    eax, eax
0x18002476e  jz      short loc_18002479B
0x180024770  test    byte ptr cs:xmmword_1800616A0, 10h
0x180024777  jz      loc_18002491A
0x18002477d  mov     edx, 0B4h
0x180024782  mov     ecx, 404h
0x180024787  mov     r9d, eax
0x18002478a  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x180024791  call    WPP_SF_D
0x180024796  jmp     loc_18002491A
0x18002479b  mov     rdx, r14
0x18002479e  mov     rcx, rdi
0x1800247a1  call    DhcpCopyToCurrentContext
0x1800247a6  mov     ebx, eax
0x1800247a8  test    eax, eax
0x1800247aa  jz      short loc_1800247C0
0x1800247ac  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800247b3  jz      loc_18002491A
0x1800247b9  mov     edx, 0B5h
0x1800247be  jmp     short loc_180024782
0x1800247c0  mov     rcx, rdi
0x1800247c3  call    RefillDhcpContext
0x1800247c8  call    cs:__imp_GetTickCount64
0x1800247ce  mov     rcx, rax
0x1800247d1  mov     rax, 624DD2F1A9FBE77h
0x1800247db  mul     rcx
0x1800247de  sub     rcx, rdx
0x1800247e1  shr     rcx, 1
0x1800247e4  add     rcx, rdx
0x1800247e7  shr     rcx, 9
0x1800247eb  cmp     rcx, r12
0x1800247ee  ja      loc_180024880
0x1800247f4  lea     rdx, [rsp+150h+var_110]
0x1800247f9  mov     rcx, rdi
0x1800247fc  call    DhcpCopyExistingStackParams
0x180024801  mov     r8d, esi
0x180024804  lea     rdx, [rsp+150h+var_110]
0x180024809  mov     rcx, rdi
0x18002480c  call    ApplyDhcpConfigurationToNIC
0x180024811  mov     ebx, eax
0x180024813  test    eax, eax
0x180024815  jz      short loc_18002482E
0x180024817  test    byte ptr cs:xmmword_1800616A0, 10h
0x18002481e  jz      loc_18002491A
0x180024824  mov     edx, 0B6h
0x180024829  jmp     loc_180024782
0x18002482e  cmp     cs:Microsoft_Windows_Dhcp_ClientEnableBits, r13b
0x180024835  jge     short loc_180024859
0x180024837  mov     rax, [rdi+58h]
0x18002483b  lea     rdx, MatchedAddressPlumbed
0x180024842  mov     [rsp+150h+lpcbData], rax
0x180024847  mov     r9, r14
0x18002484a  mov     eax, [rdi+60h]
0x18002484d  mov     r8, r15
0x180024850  mov     dword ptr [rsp+150h+phkResult], eax
0x180024854  call    McTemplateU0zzqbr2_EtwEventWriteTransfer
0x180024859  mov     [rdi+308h], r13d
0x180024860  test    byte ptr cs:xmmword_1800616A0, 10h
0x180024867  jz      loc_18002491A
0x18002486d  mov     r9d, [rdi+78h]
0x180024871  mov     edx, 0B7h
0x180024876  mov     ecx, 404h
0x18002487b  jmp     loc_18002478A
0x180024880  cmp     cs:Microsoft_Windows_Dhcp_ClientEnableBits, r13b
0x180024887  jge     short loc_1800248AB
0x180024889  mov     rax, [rdi+58h]
0x18002488d  lea     rdx, MatchedAddressNotPlumbed
0x180024894  mov     [rsp+150h+lpcbData], rax
0x180024899  mov     r9, r14
0x18002489c  mov     eax, [rdi+60h]
0x18002489f  mov     r8, r15
0x1800248a2  mov     dword ptr [rsp+150h+phkResult], eax
0x1800248a6  call    McTemplateU0zzqbr2_EtwEventWriteTransfer
0x1800248ab  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800248b2  jz      short loc_1800248D1
0x1800248b4  mov     r9d, [rdi+84h]
0x1800248bb  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x1800248c2  mov     edx, 0B8h
0x1800248c7  mov     ecx, 404h
0x1800248cc  call    WPP_SF_D
0x1800248d1  mov     rcx, [rdi+2D8h]; hKey
0x1800248d8  xor     r9d, r9d; Reserved
0x1800248db  xor     r8d, r8d; samDesired
0x1800248de  mov     rdx, r14; lpSubKey
0x1800248e1  call    cs:__imp_RegDeleteKeyExW
0x1800248e7  mov     ebx, eax
0x1800248e9  test    eax, eax
0x1800248eb  jz      short loc_18002490F
0x1800248ed  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800248f4  jz      short loc_18002490F
0x1800248f6  mov     edx, 0B9h
0x1800248fb  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x180024902  mov     ecx, 404h
0x180024907  mov     r9d, eax
0x18002490a  call    WPP_SF_D
0x18002490f  mov     [rdi+78h], r13d
0x180024913  mov     [rdi+84h], r13d
0x18002491a  mov     rcx, [rsp+150h+hKey]; hKey
0x18002491f  test    rcx, rcx
0x180024922  jz      short loc_18002492A
0x180024924  call    cs:__imp_RegCloseKey
0x18002492a  lea     rcx, [rsp+150h+var_110]; void *
0x18002492f  call    DhcpCleanParsedOptions
0x180024934  mov     eax, ebx
0x180024936  add     rsp, 118h
0x18002493d  pop     r15
0x18002493f  pop     r14
0x180024941  pop     r13
0x180024943  pop     r12
0x180024945  pop     rdi
0x180024946  pop     rsi
0x180024947  pop     rbx
0x180024948  pop     rbp
0x180024949  retn
0x18002494a  mov     esi, 1
0x18002494f  mov     [rsp+150h+hKey], r13
0x180024954  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, sil
0x18002495b  jz      short loc_18002496F
0x18002495d  mov     eax, [rdi+30h]
0x180024960  mov     r9, r14
0x180024963  mov     r8, r15
0x180024966  mov     dword ptr [rsp+150h+phkResult], eax
  ... truncated ...
```
