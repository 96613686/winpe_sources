# BuildEccCurves

- ea: `0x180012fa4`
- end: `0x1800133e6`
- name: `BuildEccCurves`
- size: `1090`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x18001e014`

## callees

- `0x180003ef0`
- `0x180007940`
- `0x180012fa4`
- `0x180014460`
- `0x180024ef0`
- `0x180024fb0`
- `0x180025660`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013354`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001336c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013354`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001336c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013135`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013189`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800131dd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013135`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013189`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800131dd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013085`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800130f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013085`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800130f7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18001322d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18001322d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800130cd`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800130cd`
- `ntdll!RtlReleaseResource` at `0x18001339d`
- `ntdll!RtlReleaseResource` at `0x18001339d`
- `ntdll!RtlAcquireResourceExclusive` at `0x18001337b`
- `ntdll!RtlAcquireResourceExclusive` at `0x18001337b`

## pseudocode

```c
__int64 BuildEccCurves()
{
  unsigned int v0; // ebx
  char *v1; // rax
  char *v2; // r14
  unsigned int v3; // r15d
  unsigned int v4; // r13d
  char *v5; // rdi
  DWORD i; // r12d
  __int64 v7; // rax
  unsigned __int64 v8; // rax
  unsigned int v9; // ebx
  char *v10; // rsi
  __int64 v11; // r8
  void *v12; // rbx
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  DWORD v16; // [rsp+48h] [rbp-B8h] BYREF
  BYTE v17[4]; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD cchName; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  BYTE v20[4]; // [rsp+60h] [rbp-A0h] BYREF
  BYTE Data[4]; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  BYTE Src[256]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Name[256]; // [rsp+170h] [rbp+70h] BYREF

  hKey = 0;
  phkResult = 0;
  cbData = 0;
  v0 = 1168;
  Type = 0;
  memset(Name, 0, 0x1FEu);
  cchName = 255;
  memset(Src, 0, 0xFFu);
  v16 = 255;
  *(_DWORD *)Data = 0;
  *(_DWORD *)v20 = 0;
  *(_DWORD *)v17 = 0;
  v1 = (char *)SafeAllocaAllocateFromHeap(15600);
  v2 = v1;
  if ( !v1 )
    return v0;
  memset(v1, 0, 0x3CF0u);
  memmove(v2, aCurve25519, 0x3CF0u);
  v3 = 20;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Control\\Cryptography\\ECCParameters",
         0,
         0x20119u,
         &hKey) )
  {
    goto LABEL_37;
  }
  v4 = 20;
  v5 = v2 + 15600;
  for ( i = 0; ; ++i )
  {
    cchName = 255;
    if ( RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0) )
      break;
    if ( !RegOpenKeyExW(hKey, Name, 0, 0x20119u, &phkResult) )
    {
      cbData = 4;
      if ( !RegQueryValueExW(phkResult, L"CurveType", 0, &Type, Data, &cbData) && Type == 4 && cbData == 4 )
      {
        cbData = 4;
        if ( !RegQueryValueExW(phkResult, L"PublicKeyLength", 0, &Type, v20, &cbData) && Type == 4 && cbData == 4 )
        {
          cbData = 4;
          if ( RegQueryValueExW(phkResult, L"EccCurveFlags", 0, &Type, v17, &cbData) )
            *(_DWORD *)v17 = 3;
          if ( Type != 4 || cbData != 4 )
            *(_DWORD *)v17 = 3;
          if ( RegQueryValueExA(phkResult, "OID", 0, &Type, Src, &v16) || Type != 1 || v16 - 1 > 0xFB )
          {
            v16 = 0;
          }
          else
          {
            v7 = v16;
            if ( v16 >= 0xFFuLL || (Src[v16] = 0, v8 = v7 + 1, v8 >= 0xFF) )
              _report_rangecheckfailure();
            Src[v8] = 0;
          }
          if ( v3 != v4 )
            goto LABEL_29;
          v9 = v4 + 1;
          if ( v4 + 1 >= v4 && 780 * (unsigned __int64)v9 <= 0xFFFFFFFF )
          {
            v10 = (char *)SafeAllocaAllocateFromHeap(780 * v9);
            if ( v10 )
            {
              ++v4;
              memmove(v10, v2, 780LL * v3);
              MSCryptFree(v2);
              v2 = v10;
              v5 = &v10[780 * v3];
LABEL_29:
              v11 = -1;
              do
                ++v11;
              while ( Name[v11] );
              memmove(v5, Name, 2 * v11 + 2);
              if ( v16 )
                memmove(v5 + 510, Src, v16 + 2LL);
              ++v3;
              *((_DWORD *)v5 + 192) = *(_DWORD *)v20;
              *((_DWORD *)v5 + 194) = *(_DWORD *)v17;
              *((_DWORD *)v5 + 193) = *(_DWORD *)Data;
              v5 += 780;
              RegCloseKey(phkResult);
              continue;
            }
          }
        }
      }
    }
  }
  RegCloseKey(hKey);
LABEL_37:
  RtlAcquireResourceExclusive(&g_EccCurvesRWLock, 1u);
  v12 = g_EccCurves;
  g_EccCurves = v2;
  g_EccCurvesCount = v3;
  RtlReleaseResource(&g_EccCurvesRWLock);
  if ( v12 )
    MSCryptFree(v12);
  return 0;
}

```

## disassembly

```asm
0x180012fa4  push    rbp
0x180012fa6  push    rbx
0x180012fa7  push    rsi
0x180012fa8  push    rdi
0x180012fa9  push    r12
0x180012fab  push    r13
0x180012fad  push    r14
0x180012faf  push    r15
0x180012fb1  lea     rbp, [rsp-288h]
0x180012fb9  sub     rsp, 388h
0x180012fc0  mov     rax, cs:__security_cookie
0x180012fc7  xor     rax, rsp
0x180012fca  mov     [rbp+2C0h+var_50], rax
0x180012fd1  xor     edi, edi
0x180012fd3  lea     rcx, [rbp+2C0h+Name]; void *
0x180012fd7  xor     edx, edx; Val
0x180012fd9  mov     [rsp+3C0h+hKey], rdi
0x180012fde  mov     r8d, 1FEh; Size
0x180012fe4  mov     [rsp+3C0h+var_368], rdi
0x180012fe9  mov     [rsp+3C0h+cbData], edi
0x180012fed  mov     ebx, 490h
0x180012ff2  mov     [rsp+3C0h+Type], edi
0x180012ff6  call    memset
0x180012ffb  mov     esi, 0FFh
0x180013000  lea     rcx, [rsp+3C0h+Src]; void *
0x180013005  mov     r8d, esi; Size
0x180013008  mov     [rsp+3C0h+cchName], esi
0x18001300c  xor     edx, edx; Val
0x18001300e  call    memset
0x180013013  mov     r15d, 3CF0h
0x180013019  mov     [rsp+3C0h+var_378], esi
0x18001301d  mov     ecx, r15d
0x180013020  mov     dword ptr [rsp+3C0h+Data], edi
0x180013024  mov     dword ptr [rsp+3C0h+var_360], edi
0x180013028  mov     dword ptr [rsp+3C0h+var_374], edi
0x18001302c  call    SafeAllocaAllocateFromHeap
0x180013031  mov     r14, rax
0x180013034  test    rax, rax
0x180013037  jz      loc_1800133C1
0x18001303d  xor     ebx, ebx
0x18001303f  mov     r8d, r15d; Size
0x180013042  xor     edx, edx; Val
0x180013044  mov     rcx, rax; void *
0x180013047  mov     esi, ebx
0x180013049  call    memset
0x18001304e  mov     r8d, r15d; Size
0x180013051  lea     rdx, aCurve25519; "curve25519"
0x180013058  mov     rcx, r14; void *
0x18001305b  call    memmove
0x180013060  lea     rax, [rsp+3C0h+hKey]
0x180013065  mov     r9d, 20119h; samDesired
0x18001306b  xor     r8d, r8d; ulOptions
0x18001306e  mov     [rsp+3C0h+phkResult], rax; phkResult
0x180013073  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Cry"...
0x18001307a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013081  lea     r15d, [rdi+14h]
0x180013085  call    cs:__imp_RegOpenKeyExW
0x18001308b  test    eax, eax
0x18001308d  jnz     loc_180013372
0x180013093  mov     r13d, r15d
0x180013096  lea     rdi, [r14+3CF0h]
0x18001309d  mov     r12d, ebx
0x1800130a0  mov     rcx, [rsp+3C0h+hKey]; hKey
0x1800130a5  lea     r9, [rsp+3C0h+cchName]; lpcchName
0x1800130aa  mov     [rsp+3C0h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x1800130af  lea     r8, [rbp+2C0h+Name]; lpName
0x1800130b3  mov     [rsp+3C0h+lpcchClass], rbx; lpcchClass
0x1800130b8  mov     edx, r12d; dwIndex
0x1800130bb  mov     [rsp+3C0h+lpClass], rbx; lpClass
0x1800130c0  mov     [rsp+3C0h+phkResult], rbx; lpReserved
0x1800130c5  mov     [rsp+3C0h+cchName], 0FFh
0x1800130cd  call    cs:__imp_RegEnumKeyExW
0x1800130d3  mov     rcx, [rsp+3C0h+hKey]; hKey
0x1800130d8  test    eax, eax
0x1800130da  jnz     loc_18001336C
0x1800130e0  lea     rax, [rsp+3C0h+var_368]
0x1800130e5  mov     r9d, 20119h; samDesired
0x1800130eb  xor     r8d, r8d; ulOptions
0x1800130ee  mov     [rsp+3C0h+phkResult], rax; phkResult
0x1800130f3  lea     rdx, [rbp+2C0h+Name]; lpSubKey
0x1800130f7  call    cs:__imp_RegOpenKeyExW
0x1800130fd  test    eax, eax
0x1800130ff  jnz     loc_18001335E
0x180013105  mov     rcx, [rsp+3C0h+var_368]; hKey
0x18001310a  lea     rax, [rsp+3C0h+cbData]
0x18001310f  mov     [rsp+3C0h+lpClass], rax; lpcbData
0x180013114  lea     r9, [rsp+3C0h+Type]; lpType
0x180013119  lea     rax, [rsp+3C0h+Data]
0x18001311e  mov     [rsp+3C0h+cbData], 4
0x180013126  xor     r8d, r8d; lpReserved
0x180013129  mov     [rsp+3C0h+phkResult], rax; lpData
0x18001312e  lea     rdx, ValueName; "CurveType"
0x180013135  call    cs:__imp_RegQueryValueExW
0x18001313b  test    eax, eax
0x18001313d  jnz     loc_18001335E
0x180013143  cmp     [rsp+3C0h+Type], 4
0x180013148  jnz     loc_18001335E
0x18001314e  cmp     [rsp+3C0h+cbData], 4
0x180013153  jnz     loc_18001335E
0x180013159  mov     rcx, [rsp+3C0h+var_368]; hKey
0x18001315e  lea     rax, [rsp+3C0h+cbData]
0x180013163  mov     [rsp+3C0h+lpClass], rax; lpcbData
0x180013168  lea     r9, [rsp+3C0h+Type]; lpType
0x18001316d  lea     rax, [rsp+3C0h+var_360]
0x180013172  mov     [rsp+3C0h+cbData], 4
0x18001317a  xor     r8d, r8d; lpReserved
0x18001317d  mov     [rsp+3C0h+phkResult], rax; lpData
0x180013182  lea     rdx, aPublickeylengt; "PublicKeyLength"
0x180013189  call    cs:__imp_RegQueryValueExW
0x18001318f  test    eax, eax
0x180013191  jnz     loc_18001335E
0x180013197  cmp     [rsp+3C0h+Type], 4
0x18001319c  jnz     loc_18001335E
0x1800131a2  cmp     [rsp+3C0h+cbData], 4
0x1800131a7  jnz     loc_18001335E
0x1800131ad  mov     rcx, [rsp+3C0h+var_368]; hKey
0x1800131b2  lea     rax, [rsp+3C0h+cbData]
0x1800131b7  mov     [rsp+3C0h+lpClass], rax; lpcbData
0x1800131bc  lea     r9, [rsp+3C0h+Type]; lpType
0x1800131c1  lea     rax, [rsp+3C0h+var_374]
0x1800131c6  mov     [rsp+3C0h+cbData], 4
0x1800131ce  xor     r8d, r8d; lpReserved
0x1800131d1  mov     [rsp+3C0h+phkResult], rax; lpData
0x1800131d6  lea     rdx, aEcccurveflags; "EccCurveFlags"
0x1800131dd  call    cs:__imp_RegQueryValueExW
0x1800131e3  test    eax, eax
0x1800131e5  jz      short loc_1800131EF
0x1800131e7  mov     dword ptr [rsp+3C0h+var_374], 3
0x1800131ef  cmp     [rsp+3C0h+Type], 4
0x1800131f4  jnz     short loc_1800131FD
0x1800131f6  cmp     [rsp+3C0h+cbData], 4
0x1800131fb  jz      short loc_180013205
0x1800131fd  mov     dword ptr [rsp+3C0h+var_374], 3
0x180013205  mov     rcx, [rsp+3C0h+var_368]; hKey
0x18001320a  lea     rax, [rsp+3C0h+var_378]
0x18001320f  mov     [rsp+3C0h+lpClass], rax; lpcbData
0x180013214  lea     r9, [rsp+3C0h+Type]; lpType
0x180013219  lea     rax, [rsp+3C0h+Src]
0x18001321e  xor     r8d, r8d; lpReserved
0x180013221  lea     rdx, aOid; "OID"
0x180013228  mov     [rsp+3C0h+phkResult], rax; lpData
0x18001322d  call    cs:__imp_RegQueryValueExA
0x180013233  test    eax, eax
0x180013235  jnz     short loc_180013272
0x180013237  cmp     [rsp+3C0h+Type], 1
0x18001323c  jnz     short loc_180013272
0x18001323e  mov     ecx, [rsp+3C0h+var_378]
0x180013242  lea     eax, [rcx-1]
0x180013245  cmp     eax, 0FBh
0x18001324a  ja      short loc_180013272
0x18001324c  mov     eax, ecx
0x18001324e  mov     ecx, 0FFh
0x180013253  cmp     rax, rcx
0x180013256  jnb     loc_180013366
0x18001325c  mov     [rsp+rax+3C0h+Src], bl
0x180013260  inc     rax
0x180013263  cmp     rax, rcx
0x180013266  jnb     loc_180013366
0x18001326c  mov     [rsp+rax+3C0h+Src], bl
0x180013270  jmp     short loc_180013276
0x180013272  mov     [rsp+3C0h+var_378], ebx
0x180013276  cmp     r15d, r13d
0x180013279  jnz     short loc_1800132E4
0x18001327b  lea     ebx, [r13+1]
0x18001327f  cmp     ebx, r13d
0x180013282  jb      loc_18001335C
0x180013288  mov     eax, ebx
0x18001328a  imul    rcx, rax, 30Ch
0x180013291  mov     eax, 0FFFFFFFFh
0x180013296  cmp     rcx, rax
0x180013299  ja      loc_18001335C
0x18001329f  imul    ecx, ebx, 30Ch
0x1800132a5  call    SafeAllocaAllocateFromHeap
0x1800132aa  mov     rsi, rax
0x1800132ad  test    rax, rax
0x1800132b0  jz      loc_18001335C
0x1800132b6  mov     eax, r15d
0x1800132b9  mov     r13d, ebx
0x1800132bc  imul    rbx, rax, 30Ch
0x1800132c3  mov     rdx, r14; Src
0x1800132c6  mov     rcx, rsi; void *
0x1800132c9  mov     r8, rbx; Size
0x1800132cc  call    memmove
0x1800132d1  mov     rcx, r14
0x1800132d4  call    MSCryptFree
0x1800132d9  mov     r14, rsi
0x1800132dc  xor     esi, esi
0x1800132de  lea     rdi, [rbx+r14]
0x1800132e2  xor     ebx, ebx
0x1800132e4  lea     rax, [rbp+2C0h+Name]
0x1800132e8  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800132ec  inc     r8
0x1800132ef  cmp     [rax+r8*2], bx
0x1800132f4  jnz     short loc_1800132EC
0x1800132f6  lea     r8, ds:2[r8*2]; Size
0x1800132fe  mov     rcx, rdi; void *
0x180013301  lea     rdx, [rbp+2C0h+Name]; Src
0x180013305  call    memmove
0x18001330a  mov     eax, [rsp+3C0h+var_378]
0x18001330e  test    eax, eax
0x180013310  jz      short loc_180013327
0x180013312  lea     r8, [rax+2]; Size
0x180013316  lea     rcx, [rdi+1FEh]; void *
0x18001331d  lea     rdx, [rsp+3C0h+Src]; Src
0x180013322  call    memmove
0x180013327  mov     eax, dword ptr [rsp+3C0h+var_360]
0x18001332b  inc     r15d
0x18001332e  mov     [rdi+300h], eax
0x180013334  mov     eax, dword ptr [rsp+3C0h+var_374]
0x180013338  mov     [rdi+308h], eax
0x18001333e  mov     eax, dword ptr [rsp+3C0h+Data]
0x180013342  mov     [rdi+304h], eax
0x180013348  add     rdi, 30Ch
0x18001334f  mov     rcx, [rsp+3C0h+var_368]; hKey
0x180013354  call    cs:__imp_RegCloseKey
0x18001335a  jmp     short loc_18001335E
0x18001335c  xor     ebx, ebx
0x18001335e  inc     r12d
0x180013361  jmp     loc_1800130A0
0x180013366  call    __report_rangecheckfailure
0x18001336c  call    cs:__imp_RegCloseKey
0x180013372  mov     dl, 1; Wait
0x180013374  lea     rcx, g_EccCurvesRWLock; Resource
0x18001337b  call    cs:__imp_RtlAcquireResourceExclusive
0x180013381  mov     rbx, cs:g_EccCurves
0x180013388  lea     rcx, g_EccCurvesRWLock; Resource
0x18001338f  mov     cs:g_EccCurves, r14
0x180013396  mov     cs:g_EccCurvesCount, r15d
0x18001339d  call    cs:__imp_RtlReleaseResource
0x1800133a3  xor     edi, edi
0x1800133a5  test    rbx, rbx
0x1800133a8  jz      short loc_1800133B2
0x1800133aa  mov     rcx, rbx
0x1800133ad  call    MSCryptFree
0x1800133b2  mov     ebx, edi
0x1800133b4  test    rsi, rsi
0x1800133b7  jz      short loc_1800133C1
0x1800133b9  mov     rcx, rsi
0x1800133bc  call    MSCryptFree
0x1800133c1  mov     eax, ebx
0x1800133c3  mov     rcx, [rbp+2C0h+var_50]
0x1800133ca  xor     rcx, rsp; StackCookie
0x1800133cd  call    __security_check_cookie
0x1800133d2  add     rsp, 388h
0x1800133d9  pop     r15
0x1800133db  pop     r14
0x1800133dd  pop     r13
0x1800133df  pop     r12
0x1800133e1  pop     rdi
0x1800133e2  pop     rsi
0x1800133e3  pop     rbx
0x1800133e4  pop     rbp
0x1800133e5  retn
```
