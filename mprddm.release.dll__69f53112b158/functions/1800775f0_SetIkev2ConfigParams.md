# SetIkev2ConfigParams

- ea: `0x1800775f0`
- end: `0x180077baf`
- name: `SetIkev2ConfigParams`
- size: `1471`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180005bc0`

## callees

- `0x180046fd4`
- `0x1800775f0`
- `0x180077bb8`
- `0x180092ad0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x1800776eb`
- `ADVAPI32!RegSetValueExW` at `0x180077736`
- `ADVAPI32!RegSetValueExW` at `0x180077861`
- `ADVAPI32!RegSetValueExW` at `0x180077917`
- `ADVAPI32!RegSetValueExW` at `0x180077959`
- `ADVAPI32!RegSetValueExW` at `0x180077a98`
- `ADVAPI32!RegSetValueExW` at `0x180077ad3`
- `ADVAPI32!RegSetValueExW` at `0x180077b2d`
- `ADVAPI32!RegSetValueExW` at `0x1800776eb`
- `ADVAPI32!RegSetValueExW` at `0x180077736`
- `ADVAPI32!RegSetValueExW` at `0x180077861`
- `ADVAPI32!RegSetValueExW` at `0x180077917`
- `ADVAPI32!RegSetValueExW` at `0x180077959`
- `ADVAPI32!RegSetValueExW` at `0x180077a98`
- `ADVAPI32!RegSetValueExW` at `0x180077ad3`
- `ADVAPI32!RegSetValueExW` at `0x180077b2d`
- `ADVAPI32!RegCloseKey` at `0x180077873`
- `ADVAPI32!RegCloseKey` at `0x180077ae9`
- `ADVAPI32!RegCloseKey` at `0x180077b41`
- `ADVAPI32!RegCloseKey` at `0x180077b64`
- `ADVAPI32!RegCloseKey` at `0x180077b79`
- `ADVAPI32!RegCloseKey` at `0x180077873`
- `ADVAPI32!RegCloseKey` at `0x180077ae9`
- `ADVAPI32!RegCloseKey` at `0x180077b41`
- `ADVAPI32!RegCloseKey` at `0x180077b64`
- `ADVAPI32!RegCloseKey` at `0x180077b79`
- `ADVAPI32!RegDeleteValueW` at `0x18007792f`
- `ADVAPI32!RegDeleteValueW` at `0x180077b4f`
- `ADVAPI32!RegDeleteValueW` at `0x18007792f`
- `ADVAPI32!RegDeleteValueW` at `0x180077b4f`
- `ADVAPI32!RegCreateKeyExW` at `0x180077780`
- `ADVAPI32!RegCreateKeyExW` at `0x18007781e`
- `ADVAPI32!RegCreateKeyExW` at `0x1800779ad`
- `ADVAPI32!RegCreateKeyExW` at `0x180077a51`
- `ADVAPI32!RegCreateKeyExW` at `0x180077780`
- `ADVAPI32!RegCreateKeyExW` at `0x18007781e`
- `ADVAPI32!RegCreateKeyExW` at `0x1800779ad`
- `ADVAPI32!RegCreateKeyExW` at `0x180077a51`
- `ADVAPI32!RegDeleteKeyExW` at `0x1800778e4`
- `ADVAPI32!RegDeleteKeyExW` at `0x1800778e4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800777a2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800779cf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800777a2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800779cf`

## string_xrefs

- `0x180077677`: `ConfigOptions`

## pseudocode

```c
__int64 __fastcall SetIkev2ConfigParams(HKEY hKey, char a2, __int64 a3)
{
  unsigned int v6; // ebx
  unsigned int v7; // r15d
  LPCWSTR *v8; // r14
  unsigned int v9; // r14d
  int v10; // eax
  DWORD cbData; // eax
  unsigned int v12; // r14d
  __int64 v13; // r15
  LSTATUS v14; // eax
  HKEY v15; // rcx
  DWORD v16; // eax
  DWORD dwDisposition; // [rsp+50h] [rbp-69h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-61h] BYREF
  HKEY hKeya; // [rsp+60h] [rbp-59h] BYREF
  HKEY v21; // [rsp+68h] [rbp-51h] BYREF
  _QWORD v22[10]; // [rsp+70h] [rbp-49h] BYREF
  WCHAR SubKey[12]; // [rsp+C0h] [rbp+7h] BYREF

  hKeya = 0;
  v22[0] = L"idleTimeout";
  v21 = 0;
  v22[2] = L"networkBlackoutTime";
  dwDisposition = 0;
  v22[3] = a3 + 4;
  v22[4] = L"saLifeTime";
  v22[5] = a3 + 8;
  v22[6] = L"saDataSize";
  v22[7] = a3 + 12;
  v22[8] = L"ConfigOptions";
  v22[9] = a3 + 16;
  v22[1] = a3;
  if ( a2 != 1 )
  {
    if ( a2 != 2 && a2 != 3 && (unsigned int)(a2 - 4) >= 2 )
      return 50;
    if ( *(_DWORD *)(a3 + 48) > 3u )
      return 87;
  }
  v7 = 0;
  v8 = (LPCWSTR *)v22;
  do
  {
    v6 = RegSetValueExW(hKey, *v8, 0, 4u, (const BYTE *)v8[1], 4u);
    if ( v6 )
      goto LABEL_50;
    ++v7;
    v8 += 2;
  }
  while ( v7 < 5 );
  if ( a2 >= 5 )
  {
    v6 = RegSetValueExW(hKey, L"mmSaLifeTime", 0, 4u, (const BYTE *)(a3 + 96), 4u);
    if ( v6 )
      goto LABEL_50;
  }
  v6 = RegCreateKeyExW(hKey, L"AllowedTrustedRootCerts", 0, 0, 0, 0xF003Fu, 0, &hKeya, &dwDisposition);
  if ( v6 )
    goto LABEL_50;
  if ( dwDisposition == 2 )
  {
    v6 = RegDeleteTreeW(hKeya, 0);
    if ( v6 )
      goto LABEL_50;
  }
  if ( *(_DWORD *)(a3 + 20) )
  {
    phkResult = 0;
    v9 = 0;
    while ( 1 )
    {
      v10 = StringCchPrintfW(SubKey, 0xCu, L"%04d", v9);
      v6 = v10;
      if ( v10 < 0 )
        break;
      v6 = RegCreateKeyExW(hKeya, SubKey, 0, 0, 0, 0xF003Fu, 0, &phkResult, &dwDisposition);
      if ( v6 )
        goto LABEL_50;
      v6 = RegSetValueExW(
             phkResult,
             L"TrustedRootCert",
             0,
             3u,
             *(const BYTE **)(*(_QWORD *)(a3 + 24) + 16LL * v9 + 8),
             *(_DWORD *)(*(_QWORD *)(a3 + 24) + 16LL * v9));
      RegCloseKey(phkResult);
      phkResult = 0;
      if ( v6 )
        goto LABEL_50;
      if ( ++v9 >= *(_DWORD *)(a3 + 20) )
        goto LABEL_22;
    }
LABEL_26:
    if ( (v10 & 0x1FFF0000) == 0x70000 )
      v6 = (unsigned __int16)v6;
    goto LABEL_50;
  }
LABEL_22:
  if ( a2 < 2 )
    goto LABEL_57;
  if ( *(_QWORD *)(a3 + 56) )
  {
    v6 = SetIkev2CustomPolicy(hKey);
    if ( v6 )
      goto LABEL_50;
  }
  else
  {
    RegDeleteKeyExW(hKey, L"IKEv2CustomPolicy", 0, 0);
  }
  cbData = *(_DWORD *)(a3 + 32);
  if ( cbData )
  {
    v6 = RegSetValueExW(hKey, L"MachineCertificateName", 0, 3u, *(const BYTE **)(a3 + 40), cbData);
    if ( v6 )
      goto LABEL_50;
  }
  else
  {
    RegDeleteValueW(hKey, L"MachineCertificateName");
  }
  v6 = RegSetValueExW(hKey, L"EncryptionType", 0, 4u, (const BYTE *)(a3 + 48), 4u);
  if ( !v6 )
  {
LABEL_57:
    if ( a2 >= 3 )
    {
      v6 = RegCreateKeyExW(hKey, L"AllowedCertEku", 0, 0, 0, 0x2001Fu, 0, &v21, &dwDisposition);
      if ( !v6 && (dwDisposition != 2 || (v6 = RegDeleteTreeW(v21, 0)) == 0) )
      {
        if ( !*(_DWORD *)(a3 + 64) )
        {
LABEL_45:
          v16 = *(_DWORD *)(a3 + 80);
          if ( v16 )
            v6 = RegSetValueExW(hKey, L"MachineCertificateHash", 0, 3u, *(const BYTE **)(a3 + 88), v16);
          else
            RegDeleteValueW(hKey, L"MachineCertificateHash");
          goto LABEL_50;
        }
        phkResult = 0;
        v12 = 0;
        while ( 1 )
        {
          v10 = StringCchPrintfW(SubKey, 0xCu, L"%04d", v12);
          v6 = v10;
          if ( v10 < 0 )
            goto LABEL_26;
          v6 = RegCreateKeyExW(v21, SubKey, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
          if ( v6 )
            break;
          v13 = 16LL * v12;
          v6 = RegSetValueExW(
                 phkResult,
                 L"TrustedEku",
                 0,
                 1u,
                 *(const BYTE **)(*(_QWORD *)(a3 + 72) + v13 + 8),
                 2 * *(_DWORD *)(*(_QWORD *)(a3 + 72) + v13));
          if ( v6 )
          {
            v15 = phkResult;
LABEL_48:
            RegCloseKey(v15);
            break;
          }
          v14 = RegSetValueExW(phkResult, L"IsEkuOID", 0, 4u, (const BYTE *)(v13 + *(_QWORD *)(a3 + 72) + 4LL), 4u);
          v15 = phkResult;
          v6 = v14;
          if ( v14 )
            goto LABEL_48;
          RegCloseKey(phkResult);
          ++v12;
          phkResult = 0;
          if ( v12 >= *(_DWORD *)(a3 + 64) )
            goto LABEL_45;
        }
      }
    }
  }
LABEL_50:
  if ( hKeya )
    RegCloseKey(hKeya);
  if ( v21 )
    RegCloseKey(v21);
  return v6;
}

```

## disassembly

```asm
0x1800775f0  mov     [rsp-8+arg_8], rbx
0x1800775f5  push    rbp
0x1800775f6  push    rsi
0x1800775f7  push    rdi
0x1800775f8  push    r12
0x1800775fa  push    r13
0x1800775fc  push    r14
0x1800775fe  push    r15
0x180077600  lea     rbp, [rsp-27h]
0x180077605  sub     rsp, 0E0h
0x18007760c  mov     rax, cs:__security_cookie
0x180077613  xor     rax, rsp
0x180077616  mov     [rbp+57h+var_38], rax
0x18007761a  xor     r13d, r13d
0x18007761d  movsx   r12d, dl
0x180077621  lea     rax, aIdletimeout; "idleTimeout"
0x180077628  mov     [rbp+57h+hKey], r13
0x18007762c  mov     [rbp+57h+var_A0], rax
0x180077630  mov     rsi, rcx
0x180077633  lea     rax, aNetworkblackou; "networkBlackoutTime"
0x18007763a  mov     [rbp+57h+var_A8], r13
0x18007763e  mov     [rbp+57h+var_90], rax
0x180077642  mov     ecx, r12d
0x180077645  mov     [rbp+57h+dwDisposition], r13d
0x180077649  lea     rax, [r8+4]
0x18007764d  mov     [rbp+57h+var_88], rax
0x180077651  lea     rax, aSalifetime; "saLifeTime"
0x180077658  mov     [rbp+57h+var_80], rax
0x18007765c  lea     rax, [r8+8]
0x180077660  mov     [rbp+57h+var_78], rax
0x180077664  lea     rax, aSadatasize; "saDataSize"
0x18007766b  mov     [rbp+57h+var_70], rax
0x18007766f  lea     rax, [r8+0Ch]
0x180077673  mov     [rbp+57h+var_68], rax
0x180077677  lea     rax, aConfigoptions; "ConfigOptions"
0x18007767e  mov     [rbp+57h+var_60], rax
0x180077682  lea     rax, [r8+10h]
0x180077686  mov     [rbp+57h+var_58], rax
0x18007768a  mov     rdi, r8
0x18007768d  mov     [rbp+57h+var_98], r8
0x180077691  sub     ecx, 1
0x180077694  jz      short loc_1800776C4
0x180077696  sub     ecx, 1
0x180077699  jz      short loc_1800776B3
0x18007769b  sub     ecx, 1
0x18007769e  jz      short loc_1800776B3
0x1800776a0  sub     ecx, 1
0x1800776a3  jz      short loc_1800776B3
0x1800776a5  cmp     ecx, 1
0x1800776a8  jz      short loc_1800776B3
0x1800776aa  lea     ebx, [r13+32h]
0x1800776ae  jmp     loc_180077B85
0x1800776b3  cmp     dword ptr [r8+30h], 3
0x1800776b8  jbe     short loc_1800776C4
0x1800776ba  mov     ebx, 57h ; 'W'
0x1800776bf  jmp     loc_180077B85
0x1800776c4  mov     r15d, r13d
0x1800776c7  lea     r14, [rbp+57h+var_A0]
0x1800776cb  mov     rax, [r14+8]
0x1800776cf  mov     r9d, 4; dwType
0x1800776d5  mov     rdx, [r14]; lpValueName
0x1800776d8  xor     r8d, r8d; Reserved
0x1800776db  mov     [rsp+110h+cbData], 4; cbData
0x1800776e3  mov     rcx, rsi; hKey
0x1800776e6  mov     [rsp+110h+lpData], rax; lpData
0x1800776eb  call    cs:__imp_RegSetValueExW
0x1800776f2  nop     dword ptr [rax+rax+00h]
0x1800776f7  mov     ebx, eax
0x1800776f9  test    eax, eax
0x1800776fb  jnz     loc_180077B5B
0x180077701  inc     r15d
0x180077704  add     r14, 10h
0x180077708  cmp     r15d, 5
0x18007770c  jb      short loc_1800776CB
0x18007770e  lea     r15d, [rax+4]
0x180077712  cmp     r12b, 5
0x180077716  jl      short loc_18007774C
0x180077718  lea     rax, [rdi+60h]
0x18007771c  mov     [rsp+110h+cbData], r15d; cbData
0x180077721  mov     r9d, r15d; dwType
0x180077724  mov     [rsp+110h+lpData], rax; lpData
0x180077729  xor     r8d, r8d; Reserved
0x18007772c  lea     rdx, aMmsalifetime; "mmSaLifeTime"
0x180077733  mov     rcx, rsi; hKey
0x180077736  call    cs:__imp_RegSetValueExW
0x18007773d  nop     dword ptr [rax+rax+00h]
0x180077742  mov     ebx, eax
0x180077744  test    eax, eax
0x180077746  jnz     loc_180077B5B
0x18007774c  lea     rax, [rbp+57h+dwDisposition]
0x180077750  xor     r9d, r9d; lpClass
0x180077753  mov     [rsp+110h+lpdwDisposition], rax; lpdwDisposition
0x180077758  lea     rdx, aAllowedtrusted; "AllowedTrustedRootCerts"
0x18007775f  lea     rax, [rbp+57h+hKey]
0x180077763  xor     r8d, r8d; Reserved
0x180077766  mov     [rsp+110h+phkResult], rax; phkResult
0x18007776b  mov     rcx, rsi; hKey
0x18007776e  mov     [rsp+110h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180077773  mov     [rsp+110h+cbData], 0F003Fh; samDesired
0x18007777b  mov     dword ptr [rsp+110h+lpData], r13d; dwOptions
0x180077780  call    cs:__imp_RegCreateKeyExW
0x180077787  nop     dword ptr [rax+rax+00h]
0x18007778c  mov     ebx, eax
0x18007778e  test    eax, eax
0x180077790  jnz     loc_180077B5B
0x180077796  cmp     [rbp+57h+dwDisposition], 2
0x18007779a  jnz     short loc_1800777B8
0x18007779c  mov     rcx, [rbp+57h+hKey]; hKey
0x1800777a0  xor     edx, edx; lpSubKey
0x1800777a2  call    cs:__imp_RegDeleteTreeW
0x1800777a9  nop     dword ptr [rax+rax+00h]
0x1800777ae  mov     ebx, eax
0x1800777b0  test    eax, eax
0x1800777b2  jnz     loc_180077B5B
0x1800777b8  mov     eax, [rdi+14h]
0x1800777bb  test    eax, eax
0x1800777bd  jz      loc_180077898
0x1800777c3  mov     [rbp+57h+var_B8], r13
0x1800777c7  mov     r14d, r13d
0x1800777ca  mov     r9d, r14d
0x1800777cd  lea     r8, a04d; "%04d"
0x1800777d4  mov     edx, 0Ch; unsigned __int64
0x1800777d9  lea     rcx, [rbp+57h+SubKey]; unsigned __int16 *
0x1800777dd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800777e2  mov     ebx, eax
0x1800777e4  test    eax, eax
0x1800777e6  js      loc_1800778BF
0x1800777ec  mov     rcx, [rbp+57h+hKey]; hKey
0x1800777f0  lea     rax, [rbp+57h+dwDisposition]
0x1800777f4  mov     [rsp+110h+lpdwDisposition], rax; lpdwDisposition
0x1800777f9  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x1800777fd  lea     rax, [rbp+57h+var_B8]
0x180077801  xor     r9d, r9d; lpClass
0x180077804  mov     [rsp+110h+phkResult], rax; phkResult
0x180077809  xor     r8d, r8d; Reserved
0x18007780c  mov     [rsp+110h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180077811  mov     [rsp+110h+cbData], 0F003Fh; samDesired
0x180077819  mov     dword ptr [rsp+110h+lpData], r13d; dwOptions
0x18007781e  call    cs:__imp_RegCreateKeyExW
0x180077825  nop     dword ptr [rax+rax+00h]
0x18007782a  mov     ebx, eax
0x18007782c  test    eax, eax
0x18007782e  jnz     loc_180077B5B
0x180077834  mov     rcx, [rdi+18h]
0x180077838  lea     r9d, [rbx+3]; dwType
0x18007783c  mov     edx, r14d
0x18007783f  xor     r8d, r8d; Reserved
0x180077842  add     rdx, rdx
0x180077845  mov     eax, [rcx+rdx*8]
0x180077848  mov     [rsp+110h+cbData], eax; cbData
0x18007784c  mov     rax, [rcx+rdx*8+8]
0x180077851  lea     rdx, Value; "TrustedRootCert"
0x180077858  mov     rcx, [rbp+57h+var_B8]; hKey
0x18007785c  mov     [rsp+110h+lpData], rax; lpData
0x180077861  call    cs:__imp_RegSetValueExW
0x180077868  nop     dword ptr [rax+rax+00h]
0x18007786d  mov     rcx, [rbp+57h+var_B8]; hKey
0x180077871  mov     ebx, eax
0x180077873  call    cs:__imp_RegCloseKey
0x18007787a  nop     dword ptr [rax+rax+00h]
0x18007787f  mov     [rbp+57h+var_B8], r13
0x180077883  test    ebx, ebx
0x180077885  jnz     loc_180077B5B
0x18007788b  inc     r14d
0x18007788e  cmp     r14d, [rdi+14h]
0x180077892  jb      loc_1800777CA
0x180077898  cmp     r12b, 2
0x18007789c  jl      loc_18007796F
0x1800778a2  mov     rdx, [rdi+38h]
0x1800778a6  mov     rcx, rsi; hKey
0x1800778a9  test    rdx, rdx
0x1800778ac  jz      short loc_1800778D7
0x1800778ae  call    SetIkev2CustomPolicy
0x1800778b3  mov     ebx, eax
0x1800778b5  test    eax, eax
0x1800778b7  jnz     loc_180077B5B
0x1800778bd  jmp     short loc_1800778F0
0x1800778bf  and     eax, 1FFF0000h
0x1800778c4  cmp     eax, 70000h
0x1800778c9  jnz     loc_180077B5B
0x1800778cf  movzx   ebx, bx
0x1800778d2  jmp     loc_180077B5B
0x1800778d7  xor     r9d, r9d; Reserved
0x1800778da  lea     rdx, aIkev2custompol; "IKEv2CustomPolicy"
0x1800778e1  xor     r8d, r8d; samDesired
0x1800778e4  call    cs:__imp_RegDeleteKeyExW
0x1800778eb  nop     dword ptr [rax+rax+00h]
0x1800778f0  mov     eax, [rdi+20h]
0x1800778f3  lea     rdx, aMachinecertifi_0; "MachineCertificateName"
0x1800778fa  mov     rcx, rsi; hKey
0x1800778fd  test    eax, eax
0x1800778ff  jz      short loc_18007792F
0x180077901  mov     [rsp+110h+cbData], eax; cbData
0x180077905  mov     r9d, 3; dwType
0x18007790b  mov     rax, [rdi+28h]
0x18007790f  xor     r8d, r8d; Reserved
0x180077912  mov     [rsp+110h+lpData], rax; lpData
0x180077917  call    cs:__imp_RegSetValueExW
0x18007791e  nop     dword ptr [rax+rax+00h]
0x180077923  mov     ebx, eax
0x180077925  test    eax, eax
0x180077927  jnz     loc_180077B5B
0x18007792d  jmp     short loc_18007793B
0x18007792f  call    cs:__imp_RegDeleteValueW
0x180077936  nop     dword ptr [rax+rax+00h]
0x18007793b  lea     rax, [rdi+30h]
0x18007793f  mov     [rsp+110h+cbData], r15d; cbData
0x180077944  mov     r9d, r15d; dwType
0x180077947  mov     [rsp+110h+lpData], rax; lpData
0x18007794c  xor     r8d, r8d; Reserved
0x18007794f  lea     rdx, aEncryptiontype; "EncryptionType"
0x180077956  mov     rcx, rsi; hKey
0x180077959  call    cs:__imp_RegSetValueExW
0x180077960  nop     dword ptr [rax+rax+00h]
0x180077965  mov     ebx, eax
0x180077967  test    eax, eax
0x180077969  jnz     loc_180077B5B
0x18007796f  cmp     r12b, 3
0x180077973  jl      loc_180077B5B
0x180077979  lea     rax, [rbp+57h+dwDisposition]
0x18007797d  xor     r9d, r9d; lpClass
0x180077980  mov     [rsp+110h+lpdwDisposition], rax; lpdwDisposition
0x180077985  lea     rdx, aAllowedcerteku; "AllowedCertEku"
0x18007798c  lea     rax, [rbp+57h+var_A8]
0x180077990  xor     r8d, r8d; Reserved
0x180077993  mov     [rsp+110h+phkResult], rax; phkResult
0x180077998  mov     rcx, rsi; hKey
0x18007799b  mov     [rsp+110h+lpSecurityAttributes], r13; lpSecurityAttributes
0x1800779a0  mov     [rsp+110h+cbData], 2001Fh; samDesired
0x1800779a8  mov     dword ptr [rsp+110h+lpData], r13d; dwOptions
0x1800779ad  call    cs:__imp_RegCreateKeyExW
0x1800779b4  nop     dword ptr [rax+rax+00h]
0x1800779b9  mov     ebx, eax
0x1800779bb  test    eax, eax
0x1800779bd  jnz     loc_180077B5B
0x1800779c3  cmp     [rbp+57h+dwDisposition], 2
0x1800779c7  jnz     short loc_1800779E5
0x1800779c9  mov     rcx, [rbp+57h+var_A8]; hKey
0x1800779cd  xor     edx, edx; lpSubKey
0x1800779cf  call    cs:__imp_RegDeleteTreeW
0x1800779d6  nop     dword ptr [rax+rax+00h]
0x1800779db  mov     ebx, eax
0x1800779dd  test    eax, eax
0x1800779df  jnz     loc_180077B5B
0x1800779e5  mov     eax, [rdi+40h]
0x1800779e8  test    eax, eax
0x1800779ea  jz      loc_180077B06
0x1800779f0  mov     [rbp+57h+var_B8], r13
0x1800779f4  mov     r14d, r13d
0x1800779f7  mov     r12d, 4
0x1800779fd  mov     r9d, r14d
0x180077a00  lea     r8, a04d; "%04d"
0x180077a07  mov     edx, 0Ch; unsigned __int64
0x180077a0c  lea     rcx, [rbp+57h+SubKey]; unsigned __int16 *
0x180077a10  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180077a15  mov     ebx, eax
0x180077a17  test    eax, eax
0x180077a19  js      loc_1800778BF
0x180077a1f  mov     rcx, [rbp+57h+var_A8]; hKey
0x180077a23  lea     rax, [rbp+57h+dwDisposition]
0x180077a27  mov     [rsp+110h+lpdwDisposition], rax; lpdwDisposition
0x180077a2c  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x180077a30  lea     rax, [rbp+57h+var_B8]
0x180077a34  xor     r9d, r9d; lpClass
0x180077a37  mov     [rsp+110h+phkResult], rax; phkResult
0x180077a3c  xor     r8d, r8d; Reserved
0x180077a3f  mov     [rsp+110h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180077a44  mov     [rsp+110h+cbData], 2001Fh; samDesired
0x180077a4c  mov     dword ptr [rsp+110h+lpData], r13d; dwOptions
0x180077a51  call    cs:__imp_RegCreateKeyExW
0x180077a58  nop     dword ptr [rax+rax+00h]
0x180077a5d  mov     ebx, eax
0x180077a5f  test    eax, eax
0x180077a61  jnz     loc_180077B5B
0x180077a67  mov     rcx, [rdi+48h]
0x180077a6b  lea     r9d, [rbx+1]; dwType
0x180077a6f  mov     r15d, r14d
0x180077a72  lea     rdx, aTrustedeku; "TrustedEku"
0x180077a79  shl     r15, 4
0x180077a7d  xor     r8d, r8d; Reserved
0x180077a80  mov     eax, [rcx+r15]
0x180077a84  add     eax, eax
0x180077a86  mov     [rsp+110h+cbData], eax; cbData
0x180077a8a  mov     rax, [rcx+r15+8]
0x180077a8f  mov     rcx, [rbp+57h+var_B8]; hKey
0x180077a93  mov     [rsp+110h+lpData], rax; lpData
0x180077a98  call    cs:__imp_RegSetValueExW
0x180077a9f  nop     dword ptr [rax+rax+00h]
0x180077aa4  mov     ebx, eax
0x180077aa6  test    eax, eax
0x180077aa8  jnz     loc_180077B3D
0x180077aae  mov     rcx, [rdi+48h]
0x180077ab2  lea     rdx, aIsekuoid; "IsEkuOID"
0x180077ab9  add     rcx, r12
0x180077abc  mov     [rsp+110h+cbData], r12d; cbData
0x180077ac1  add     rcx, r15
0x180077ac4  mov     r9d, r12d; dwType
0x180077ac7  mov     [rsp+110h+lpData], rcx; lpData
0x180077acc  xor     r8d, r8d; Reserved
0x180077acf  mov     rcx, [rbp+57h+var_B8]; hKey
  ... truncated ...
```
