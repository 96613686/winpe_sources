# acmdDriverConfigInit

- ea: `0x180004700`
- end: `0x180004943`
- name: `acmdDriverConfigInit`
- size: `579`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800020b0`

## callees

- `0x180004700`
- `0x18000494c`
- `0x180004ec4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800047c7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800047c7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000478a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800047bd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000478a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800047bd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004822`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004878`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800048cc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004822`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004878`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800048cc`

## pseudocode

```c
__int64 __fastcall acmdDriverConfigInit(__int64 a1, const WCHAR *a2)
{
  HKEY *phkResult; // r12
  HKEY v5; // rcx
  int v6; // r14d
  int v7; // r15d
  int *v8; // rsi
  int *v9; // rdi
  int v10; // r13d
  int v11; // eax
  HKEY v12; // rcx
  HKEY v13; // rcx
  int v14; // eax
  int v16; // [rsp+50h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+54h] [rbp-Ch] BYREF
  HKEY hKey; // [rsp+58h] [rbp-8h] BYREF
  DWORD Type; // [rsp+A8h] [rbp+48h] BYREF
  int Data; // [rsp+B0h] [rbp+50h] BYREF
  int v21; // [rsp+B8h] [rbp+58h] BYREF

  hKey = 0;
  v21 = 0;
  v16 = 0;
  if ( !a2 )
  {
    *(_DWORD *)(a1 + 56) = 5;
    *(_DWORD *)(a1 + 60) = 6;
    *(_DWORD *)(a1 + 64) = 50;
    return 1;
  }
  phkResult = (HKEY *)(a1 + 48);
  if ( !*(_QWORD *)(a1 + 48)
    && !RegCreateKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Multimedia\\", 0, 0, 0, 4u, 0, &hKey, 0) )
  {
    RegCreateKeyExW(hKey, a2, 0, 0, 0, 0xBu, 0, phkResult, 0);
    RegCloseKey(hKey);
  }
  v5 = *phkResult;
  v6 = 5;
  v7 = 6;
  if ( *phkResult )
  {
    cbData = 4;
    Data = 0;
    Type = -5;
    v10 = 2457;
    if ( RegQueryValueExW(v5, L"MaxRTEncodeSetting", 0, &Type, (LPBYTE)&Data, &cbData) || (v11 = Data, Type != 4) )
      v11 = 2457;
    v12 = *phkResult;
    v8 = (int *)(a1 + 56);
    *(_DWORD *)(a1 + 56) = v11;
    Type = -5;
    cbData = 4;
    Data = 0;
    if ( !RegQueryValueExW(v12, L"MaxRTDecodeSetting", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      v10 = Data;
    v13 = *phkResult;
    v9 = (int *)(a1 + 60);
    *(_DWORD *)(a1 + 60) = v10;
    Data = 0;
    Type = -5;
    cbData = 4;
    if ( RegQueryValueExW(v13, L"PercentCPU", 0, &Type, (LPBYTE)&Data, &cbData) || (v14 = Data, Type != 4) )
      v14 = 50;
    *(_DWORD *)(a1 + 64) = v14;
    if ( v14 )
      goto LABEL_19;
  }
  else
  {
    v8 = (int *)(a1 + 56);
    v9 = (int *)(a1 + 60);
    *(_DWORD *)(a1 + 56) = 5;
    *(_DWORD *)(a1 + 60) = 6;
  }
  *(_DWORD *)(a1 + 64) = 50;
LABEL_19:
  if ( (unsigned int)*v8 >= 7 || (unsigned int)*v9 >= 7 )
  {
    if ( !(unsigned int)configAutoConfig(a1, &v21, &v16) )
    {
      v6 = v21;
      v7 = v16;
    }
    *v8 = v6;
    *v9 = v7;
    configWriteConfiguration(a1);
  }
  return 1;
}

```

## disassembly

```asm
0x180004700  mov     [rsp-38h+arg_0], rbx
0x180004705  push    rbp
0x180004706  push    rsi
0x180004707  push    rdi
0x180004708  push    r12
0x18000470a  push    r13
0x18000470c  push    r14
0x18000470e  push    r15
0x180004710  mov     rbp, rsp
0x180004713  sub     rsp, 60h
0x180004717  xor     r13d, r13d
0x18000471a  mov     rdi, rdx
0x18000471d  mov     [rbp+hKey], r13
0x180004721  mov     rbx, rcx
0x180004724  mov     [rbp+arg_18], r13d
0x180004728  mov     [rbp+var_10], r13d
0x18000472c  test    rdx, rdx
0x18000472f  jnz     short loc_18000474B
0x180004731  mov     dword ptr [rcx+38h], 5
0x180004738  mov     dword ptr [rcx+3Ch], 6
0x18000473f  mov     dword ptr [rcx+40h], 32h ; '2'
0x180004746  jmp     loc_180004926
0x18000474b  lea     r12, [rcx+30h]
0x18000474f  mov     esi, 4
0x180004754  cmp     [r12], r13
0x180004758  jnz     short loc_1800047CD
0x18000475a  mov     [rsp+60h+lpdwDisposition], r13; lpdwDisposition
0x18000475f  lea     rax, [rbp+hKey]
0x180004763  mov     [rsp+60h+phkResult], rax; phkResult
0x180004768  lea     rdx, gszMultimediaKey; "Software\\Microsoft\\Multimedia\\"
0x18000476f  mov     [rsp+60h+lpSecurityAttributes], r13; lpSecurityAttributes
0x180004774  xor     r9d, r9d; lpClass
0x180004777  mov     [rsp+60h+samDesired], esi; samDesired
0x18000477b  xor     r8d, r8d; Reserved
0x18000477e  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180004785  mov     [rsp+60h+dwOptions], r13d; dwOptions
0x18000478a  call    cs:__imp_RegCreateKeyExW
0x180004790  test    eax, eax
0x180004792  jnz     short loc_1800047CD
0x180004794  mov     rcx, [rbp+hKey]; hKey
0x180004798  xor     r9d, r9d; lpClass
0x18000479b  mov     [rsp+60h+lpdwDisposition], r13; lpdwDisposition
0x1800047a0  xor     r8d, r8d; Reserved
0x1800047a3  mov     [rsp+60h+phkResult], r12; phkResult
0x1800047a8  mov     rdx, rdi; lpSubKey
0x1800047ab  mov     [rsp+60h+lpSecurityAttributes], r13; lpSecurityAttributes
0x1800047b0  mov     [rsp+60h+samDesired], 0Bh; samDesired
0x1800047b8  mov     [rsp+60h+dwOptions], r13d; dwOptions
0x1800047bd  call    cs:__imp_RegCreateKeyExW
0x1800047c3  mov     rcx, [rbp+hKey]; hKey
0x1800047c7  call    cs:__imp_RegCloseKey
0x1800047cd  mov     rcx, [r12]; hKey
0x1800047d1  mov     r14d, 5
0x1800047d7  lea     r15d, [r14+1]
0x1800047db  test    rcx, rcx
0x1800047de  jnz     short loc_1800047F3
0x1800047e0  lea     rsi, [rbx+38h]
0x1800047e4  lea     rdi, [rbx+3Ch]
0x1800047e8  mov     [rsi], r14d
0x1800047eb  mov     [rdi], r15d
0x1800047ee  jmp     loc_1800048EB
0x1800047f3  lea     rax, [rbp+cbData]
0x1800047f7  mov     [rbp+cbData], esi
0x1800047fa  mov     qword ptr [rsp+60h+samDesired], rax; lpcbData
0x1800047ff  lea     r9, [rbp+Type]; lpType
0x180004803  lea     rax, [rbp+Data]
0x180004807  mov     [rbp+Data], r13d
0x18000480b  mov     edi, 0FFFFFFFBh
0x180004810  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180004815  xor     r8d, r8d; lpReserved
0x180004818  mov     [rbp+Type], edi
0x18000481b  lea     rdx, gszMaxRTEncodeSetting; "MaxRTEncodeSetting"
0x180004822  call    cs:__imp_RegQueryValueExW
0x180004828  mov     r13d, 999h
0x18000482e  test    eax, eax
0x180004830  jnz     short loc_18000483A
0x180004832  mov     eax, [rbp+Data]
0x180004835  cmp     [rbp+Type], esi
0x180004838  jz      short loc_18000483D
0x18000483a  mov     eax, r13d
0x18000483d  mov     rcx, [r12]; hKey
0x180004841  lea     rsi, [rbx+38h]
0x180004845  mov     [rsi], eax
0x180004847  lea     r9, [rbp+Type]; lpType
0x18000484b  lea     rax, [rbp+cbData]
0x18000484f  mov     [rbp+Type], edi
0x180004852  mov     qword ptr [rsp+60h+samDesired], rax; lpcbData
0x180004857  lea     rdx, gszMaxRTDecodeSetting; "MaxRTDecodeSetting"
0x18000485e  lea     rax, [rbp+Data]
0x180004862  mov     [rbp+cbData], 4
0x180004869  xor     r8d, r8d; lpReserved
0x18000486c  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x180004871  mov     [rbp+Data], 0
0x180004878  call    cs:__imp_RegQueryValueExW
0x18000487e  test    eax, eax
0x180004880  jnz     short loc_18000488C
0x180004882  cmp     [rbp+Type], 4
0x180004886  jnz     short loc_18000488C
0x180004888  mov     r13d, [rbp+Data]
0x18000488c  mov     rcx, [r12]; hKey
0x180004890  lea     rax, [rbp+cbData]
0x180004894  mov     qword ptr [rsp+60h+samDesired], rax; lpcbData
0x180004899  lea     rdi, [rbx+3Ch]
0x18000489d  mov     [rdi], r13d
0x1800048a0  lea     rax, [rbp+Data]
0x1800048a4  xor     r13d, r13d
0x1800048a7  mov     qword ptr [rsp+60h+dwOptions], rax; lpData
0x1800048ac  lea     r9, [rbp+Type]; lpType
0x1800048b0  mov     [rbp+Data], r13d
0x1800048b4  xor     r8d, r8d; lpReserved
0x1800048b7  mov     [rbp+Type], 0FFFFFFFBh
0x1800048be  lea     rdx, gszPercentCPU; "PercentCPU"
0x1800048c5  mov     [rbp+cbData], 4
0x1800048cc  call    cs:__imp_RegQueryValueExW
0x1800048d2  test    eax, eax
0x1800048d4  jnz     short loc_1800048DF
0x1800048d6  cmp     [rbp+Type], 4
0x1800048da  mov     eax, [rbp+Data]
0x1800048dd  jz      short loc_1800048E4
0x1800048df  mov     eax, 32h ; '2'
0x1800048e4  mov     [rbx+40h], eax
0x1800048e7  test    eax, eax
0x1800048e9  jnz     short loc_1800048F2
0x1800048eb  mov     dword ptr [rbx+40h], 32h ; '2'
0x1800048f2  cmp     dword ptr [rsi], 7
0x1800048f5  jnb     short loc_1800048FC
0x1800048f7  cmp     dword ptr [rdi], 7
0x1800048fa  jb      short loc_180004926
0x1800048fc  lea     r8, [rbp+var_10]
0x180004900  mov     rcx, rbx
0x180004903  lea     rdx, [rbp+arg_18]
0x180004907  call    configAutoConfig
0x18000490c  test    eax, eax
0x18000490e  jnz     short loc_180004918
0x180004910  mov     r14d, [rbp+arg_18]
0x180004914  mov     r15d, [rbp+var_10]
0x180004918  mov     rcx, rbx
0x18000491b  mov     [rsi], r14d
0x18000491e  mov     [rdi], r15d
0x180004921  call    configWriteConfiguration
0x180004926  mov     rbx, [rsp+60h+arg_0]
0x18000492e  mov     eax, 1
0x180004933  add     rsp, 60h
0x180004937  pop     r15
0x180004939  pop     r14
0x18000493b  pop     r13
0x18000493d  pop     r12
0x18000493f  pop     rdi
0x180004940  pop     rsi
0x180004941  pop     rbp
0x180004942  retn
```
