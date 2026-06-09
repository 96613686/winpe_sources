# _RegLoadSettings

- ea: `0x180001e78`
- end: `0x180002279`
- name: `_RegLoadSettings`
- size: `1025`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000382c`

## callees

- `0x180001e78`
- `0x180009cd0`
- `0x18000a770`
- `0x18000e120`
- `0x180016c38`
- `0x18001f175`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180002237`
- `ntdll!RtlLeaveCriticalSection` at `0x180002237`
- `ntdll!RtlEnterCriticalSection` at `0x180001ebe`
- `ntdll!RtlEnterCriticalSection` at `0x180001ebe`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002001`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002150`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002001`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002150`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001ef8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001f6b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001ef8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001f6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002246`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002255`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002246`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002255`

## string_xrefs

- `0x180001fc4`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\reg.c`
- `0x1800021a2`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\reg.c`
- `0x18000220b`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\reg.c`

## pseudocode

```c
NTSTATUS RegLoadSettings()
{
  NTSTATUS result; // eax
  __int64 v1; // rbx
  int v2; // eax
  unsigned int v3; // esi
  int v4; // eax
  __int64 v5; // rcx
  size_t v6; // rdi
  LSTATUS v7; // r15d
  unsigned int i; // r14d
  __int64 v9; // r9
  __int64 v10; // rcx
  void *v11; // rax
  BYTE *v12; // r9
  unsigned int v13; // ecx
  DWORD v14; // r15d
  LSTATUS v15; // eax
  unsigned int j; // edx
  __int64 v17; // r14
  LPCWSTR *v18; // rdi
  __int64 *v19; // r13
  BYTE *v20; // r8
  DWORD *lpcbData; // r12
  __int64 v22; // rdx
  unsigned int v23; // r15d
  DWORD cbData; // [rsp+30h] [rbp-38h] BYREF
  __int64 v25; // [rsp+38h] [rbp-30h]
  HKEY v26; // [rsp+40h] [rbp-28h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-20h] BYREF
  HKEY hKey[3]; // [rsp+50h] [rbp-18h]
  DWORD Type; // [rsp+B0h] [rbp+48h] BYREF
  int v30; // [rsp+B8h] [rbp+50h]
  unsigned int v31; // [rsp+C0h] [rbp+58h]
  unsigned int v32; // [rsp+C8h] [rbp+60h]

  result = dword_18002AF50;
  v26 = 0;
  phkResult = 0;
  Type = 0;
  cbData = 0;
  *(_OWORD *)hKey = 0;
  if ( dword_18002AF50 )
    return result;
  v1 = 0;
  RtlEnterCriticalSection(&g_csKeyProtectorLock);
  if ( dword_18002AF50 )
    goto LABEL_55;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Policies\\Microsoft\\Cryptography\\NProtect",
         0,
         0x20019u,
         &phkResult);
  if ( v2 )
  {
    v3 = 0;
    if ( v2 > 0 )
      v2 = (unsigned __int16)v2 | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_a8d589a743023471636e7d078e4c0fe8_Traceguids,
        (unsigned int)v2);
  }
  else
  {
    v3 = 1;
    hKey[0] = phkResult;
  }
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Cryptography\\NProtect", 0, 0x20019u, &v26);
  if ( v4 )
  {
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_a8d589a743023471636e7d078e4c0fe8_Traceguids,
        (unsigned int)v4);
  }
  else
  {
    v5 = v3++;
    hKey[v5] = v26;
  }
  if ( !v3 )
    goto LABEL_55;
  v6 = (unsigned int)dword_18002A0C4 + 32LL;
  v7 = 3;
  for ( i = 0; i < v3; ++i )
  {
    if ( !v7 )
      break;
    v7 = RegQueryValueExW(hKey[i], lpValueName, 0, &Type, 0, &cbData);
    if ( !v7 )
    {
      if ( dword_18002A0B8 == Type )
      {
        v6 += cbData;
      }
      else
      {
        v7 = -2146893819;
        DebugTraceError(
          2148073477LL,
          "dwRes",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\reg.c",
          208);
      }
    }
  }
  if ( v6 > 0xFFFFFF )
  {
    v9 = 222;
    v10 = 2148073477LL;
    goto LABEL_27;
  }
  v11 = (void *)SafeAllocaAllocateFromHeap(v6);
  v1 = (__int64)v11;
  if ( !v11 )
  {
    v9 = 230;
    v10 = 2148073486LL;
    goto LABEL_27;
  }
  memset_0(v11, 0, v6);
  v12 = (BYTE *)(v1 + 32);
  v13 = 0;
  v25 = v1 + 32;
  v14 = v6 - 32;
LABEL_31:
  v32 = v13;
  if ( v13 )
  {
    qword_18002AF48 = v1;
    v1 = 0;
    goto LABEL_55;
  }
  v15 = 3;
  for ( j = 0; ; j = v31 + 1 )
  {
    v31 = j;
    if ( j >= v3 || !v15 )
    {
      ++v13;
      goto LABEL_31;
    }
    v17 = 4LL * v13;
    v18 = &(&lpValueName)[v17];
    if ( *((_DWORD *)&lpValueName + 2 * v17 + 5) || *((_DWORD *)v18 + 7) )
    {
      v20 = v12;
      v19 = &qword_18002A0C8[v17];
      *(_QWORD *)(LODWORD(qword_18002A0C8[v17]) + v1) = v12;
      if ( *((_DWORD *)v18 + 7) )
      {
        lpcbData = (DWORD *)(v1 + *((unsigned int *)v18 + 7));
        *lpcbData = v14;
        goto LABEL_42;
      }
      cbData = v14;
    }
    else
    {
      v19 = &qword_18002A0C8[v17];
      cbData = (DWORD)(&lpValueName)[v17 + 1];
      v20 = (BYTE *)(v1 + LODWORD(qword_18002A0C8[v17]));
    }
    lpcbData = &cbData;
LABEL_42:
    v15 = RegQueryValueExW(hKey[j], (&lpValueName)[v17], 0, &Type, v20, lpcbData);
    v30 = v15;
    if ( !v15 )
      break;
LABEL_49:
    *(_QWORD *)(*(unsigned int *)v19 + v1) = 0;
    v15 = v30;
    *lpcbData = 0;
LABEL_50:
    v12 = (BYTE *)v25;
LABEL_51:
    v13 = v32;
  }
  if ( *((_DWORD *)&lpValueName + 2 * v17 + 2) != Type )
  {
    v30 = -2146893819;
    DebugTraceError(
      2148073477LL,
      "dwRes",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\reg.c",
      309);
    *(_QWORD *)(*(unsigned int *)v19 + v1) = 0;
    *lpcbData = 0;
    goto LABEL_49;
  }
  v22 = *((unsigned int *)&lpValueName + 2 * v17 + 5);
  if ( !(_DWORD)v22 && !*((_DWORD *)v18 + 7) )
    goto LABEL_50;
  v23 = v14 - *lpcbData;
  if ( v23 >= (unsigned int)v22 )
  {
    v12 = (BYTE *)(v22 + v25 + *lpcbData);
    v25 = (__int64)v12;
    v14 = v23 - v22;
    goto LABEL_51;
  }
  v9 = 298;
  v10 = 2148073512LL;
LABEL_27:
  DebugTraceError(v10, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\reg.c", v9);
LABEL_55:
  dword_18002AF50 = 1;
  result = RtlLeaveCriticalSection(&g_csKeyProtectorLock);
  if ( v26 )
    result = RegCloseKey(v26);
  if ( phkResult )
    result = RegCloseKey(phkResult);
  if ( v1 )
    return MSCryptFree(v1);
  return result;
}

```

## disassembly

```asm
0x180001e78  push    rbp
0x180001e7a  push    rbx
0x180001e7b  push    rsi
0x180001e7c  push    rdi
0x180001e7d  push    r12
0x180001e7f  push    r13
0x180001e81  push    r14
0x180001e83  push    r15
0x180001e85  mov     rbp, rsp
0x180001e88  sub     rsp, 68h
0x180001e8c  mov     eax, cs:dword_18002AF50
0x180001e92  xor     r13d, r13d
0x180001e95  mov     [rbp+var_28], r13
0x180001e99  xorps   xmm0, xmm0
0x180001e9c  mov     [rbp+var_20], r13
0x180001ea0  mov     [rbp+Type], r13d
0x180001ea4  mov     [rbp+cbData], r13d
0x180001ea8  movups  xmmword ptr [rbp+hKey], xmm0
0x180001eac  test    eax, eax
0x180001eae  jnz     loc_180002268
0x180001eb4  lea     rcx, g_csKeyProtectorLock; CriticalSection
0x180001ebb  mov     ebx, r13d
0x180001ebe  call    cs:__imp_RtlEnterCriticalSection
0x180001ec4  mov     eax, cs:dword_18002AF50
0x180001eca  test    eax, eax
0x180001ecc  jnz     loc_180002226
0x180001ed2  lea     rax, [rbp+var_20]
0x180001ed6  mov     r15d, 20019h
0x180001edc  mov     r12, 0FFFFFFFF80000002h
0x180001ee3  mov     [rsp+68h+phkResult], rax; phkResult
0x180001ee8  mov     r9d, r15d; samDesired
0x180001eeb  lea     rdx, SubKey; "Software\\Policies\\Microsoft\\Cryptogr"...
0x180001ef2  mov     rcx, r12; hKey
0x180001ef5  xor     r8d, r8d; ulOptions
0x180001ef8  call    cs:__imp_RegOpenKeyExW
0x180001efe  mov     edi, 80070000h
0x180001f03  lea     r14, WPP_GLOBAL_Control
0x180001f0a  test    eax, eax
0x180001f0c  jnz     short loc_180001F1C
0x180001f0e  mov     rax, [rbp+var_20]
0x180001f12  lea     esi, [r13+1]
0x180001f16  mov     [rbp+hKey], rax
0x180001f1a  jmp     short loc_180001F52
0x180001f1c  mov     esi, r13d
0x180001f1f  test    eax, eax
0x180001f21  jle     short loc_180001F28
0x180001f23  movzx   eax, ax
0x180001f26  or      eax, edi
0x180001f28  mov     rcx, cs:WPP_GLOBAL_Control
0x180001f2f  cmp     rcx, r14
0x180001f32  jz      short loc_180001F52
0x180001f34  test    byte ptr [rcx+1Ch], 8
0x180001f38  jz      short loc_180001F52
0x180001f3a  mov     rcx, [rcx+10h]
0x180001f3e  lea     r8, WPP_a8d589a743023471636e7d078e4c0fe8_Traceguids
0x180001f45  mov     edx, 0Ah
0x180001f4a  mov     r9d, eax
0x180001f4d  call    WPP_SF_D
0x180001f52  lea     rax, [rbp+var_28]
0x180001f56  mov     r9d, r15d; samDesired
0x180001f59  xor     r8d, r8d; ulOptions
0x180001f5c  mov     [rsp+68h+phkResult], rax; phkResult
0x180001f61  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Cryptography\\NPro"...
0x180001f68  mov     rcx, r12; hKey
0x180001f6b  call    cs:__imp_RegOpenKeyExW
0x180001f71  test    eax, eax
0x180001f73  jnz     short loc_180001F84
0x180001f75  mov     rax, [rbp+var_28]
0x180001f79  mov     ecx, esi
0x180001f7b  inc     esi
0x180001f7d  mov     [rbp+rcx*8+hKey], rax
0x180001f82  jmp     short loc_180001FB5
0x180001f84  jle     short loc_180001F8B
0x180001f86  movzx   eax, ax
0x180001f89  or      eax, edi
0x180001f8b  mov     rcx, cs:WPP_GLOBAL_Control
0x180001f92  cmp     rcx, r14
0x180001f95  jz      short loc_180001FB5
0x180001f97  test    byte ptr [rcx+1Ch], 8
0x180001f9b  jz      short loc_180001FB5
0x180001f9d  mov     rcx, [rcx+10h]
0x180001fa1  lea     r8, WPP_a8d589a743023471636e7d078e4c0fe8_Traceguids
0x180001fa8  mov     edx, 0Bh
0x180001fad  mov     r9d, eax
0x180001fb0  call    WPP_SF_D
0x180001fb5  cmp     esi, 1
0x180001fb8  jb      loc_180002226
0x180001fbe  mov     edi, cs:dword_18002A0C4
0x180001fc4  lea     r12, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001fcb  add     rdi, 20h ; ' '
0x180001fcf  mov     r15d, 3
0x180001fd5  mov     r14d, r13d
0x180001fd8  test    r15d, r15d
0x180001fdb  jz      short loc_180002048
0x180001fdd  mov     rdx, cs:lpValueName; lpValueName
0x180001fe4  lea     rax, [rbp+cbData]
0x180001fe8  mov     [rsp+68h+lpcbData], rax; lpcbData
0x180001fed  lea     r9, [rbp+Type]; lpType
0x180001ff1  mov     ecx, r14d
0x180001ff4  xor     r8d, r8d; lpReserved
0x180001ff7  mov     [rsp+68h+phkResult], r13; lpData
0x180001ffc  mov     rcx, [rbp+rcx*8+hKey]; hKey
0x180002001  call    cs:__imp_RegQueryValueExW
0x180002007  mov     r15d, eax
0x18000200a  test    eax, eax
0x18000200c  jnz     short loc_180002040
0x18000200e  mov     eax, [rbp+Type]
0x180002011  cmp     cs:dword_18002A0B8, eax
0x180002017  jnz     short loc_180002021
0x180002019  mov     eax, [rbp+cbData]
0x18000201c  add     rdi, rax
0x18000201f  jmp     short loc_180002040
0x180002021  mov     eax, 80090005h
0x180002026  lea     rdx, aDwres; "dwRes"
0x18000202d  mov     ecx, eax
0x18000202f  mov     r9d, 0D0h
0x180002035  mov     r8, r12
0x180002038  mov     r15d, eax
0x18000203b  call    DebugTraceError
0x180002040  inc     r14d
0x180002043  cmp     r14d, esi
0x180002046  jb      short loc_180001FD8
0x180002048  cmp     rdi, 0FFFFFFh
0x18000204f  jbe     short loc_180002070
0x180002051  mov     r9d, 0DEh
0x180002057  mov     ecx, 80090005h
0x18000205c  mov     r8, r12
0x18000205f  lea     rdx, aStatus; "Status"
0x180002066  call    DebugTraceError
0x18000206b  jmp     loc_180002226
0x180002070  mov     rcx, rdi
0x180002073  call    SafeAllocaAllocateFromHeap
0x180002078  mov     rbx, rax
0x18000207b  test    rax, rax
0x18000207e  jnz     short loc_18000208D
0x180002080  mov     r9d, 0E6h
0x180002086  mov     ecx, 8009000Eh
0x18000208b  jmp     short loc_18000205C
0x18000208d  mov     r8, rdi; Size
0x180002090  xor     edx, edx; Val
0x180002092  mov     rcx, rbx; void *
0x180002095  call    memset_0
0x18000209a  lea     r9, [rbx+20h]
0x18000209e  mov     ecx, r13d
0x1800020a1  mov     [rbp+var_30], r9
0x1800020a5  lea     r15d, [rdi-20h]
0x1800020a9  lea     r10, lpValueName
0x1800020b0  mov     [rbp+arg_18], ecx
0x1800020b3  cmp     ecx, 1
0x1800020b6  jnb     loc_18000221C
0x1800020bc  mov     eax, 3
0x1800020c1  mov     edx, r13d
0x1800020c4  mov     [rbp+arg_10], edx
0x1800020c7  cmp     edx, esi
0x1800020c9  jnb     loc_1800021FE
0x1800020cf  test    eax, eax
0x1800020d1  jz      loc_1800021FE
0x1800020d7  mov     r14d, ecx
0x1800020da  shl     r14, 5
0x1800020de  lea     rdi, [r14+r10]
0x1800020e2  cmp     [r14+r10+14h], r13d
0x1800020e7  ja      short loc_180002107
0x1800020e9  cmp     [rdi+1Ch], r13d
0x1800020ed  ja      short loc_180002107
0x1800020ef  mov     eax, [r14+r10+10h]
0x1800020f4  lea     r13, [r10+18h]
0x1800020f8  add     r13, r14
0x1800020fb  mov     [rbp+cbData], eax
0x1800020fe  mov     r8d, [r13+0]
0x180002102  add     r8, rbx
0x180002105  jmp     short loc_180002130
0x180002107  lea     r13, [r10+18h]
0x18000210b  mov     r8, r9
0x18000210e  add     r13, r14
0x180002111  mov     eax, [r13+0]
0x180002115  mov     [rax+rbx], r9
0x180002119  cmp     dword ptr [rdi+1Ch], 0
0x18000211d  jz      short loc_18000212C
0x18000211f  mov     r12d, [rdi+1Ch]
0x180002123  add     r12, rbx
0x180002126  mov     [r12], r15d
0x18000212a  jmp     short loc_180002134
0x18000212c  mov     [rbp+cbData], r15d
0x180002130  lea     r12, [rbp+cbData]
0x180002134  mov     ecx, edx
0x180002136  lea     r9, [rbp+Type]; lpType
0x18000213a  mov     rdx, [r14+r10]; lpValueName
0x18000213e  mov     [rsp+68h+lpcbData], r12; lpcbData
0x180002143  mov     [rsp+68h+phkResult], r8; lpData
0x180002148  xor     r8d, r8d; lpReserved
0x18000214b  mov     rcx, [rbp+rcx*8+hKey]; hKey
0x180002150  call    cs:__imp_RegQueryValueExW
0x180002156  mov     [rbp+arg_8], eax
0x180002159  test    eax, eax
0x18000215b  jnz     short loc_1800021D4
0x18000215d  mov     ecx, [rbp+Type]
0x180002160  lea     r10, lpValueName
0x180002167  cmp     [r14+r10+8], ecx
0x18000216c  jnz     short loc_18000219D
0x18000216e  mov     edx, [r14+r10+14h]
0x180002173  xor     r13d, r13d
0x180002176  test    edx, edx
0x180002178  jnz     short loc_180002180
0x18000217a  cmp     [rdi+1Ch], r13d
0x18000217e  jbe     short loc_1800021ED
0x180002180  sub     r15d, [r12]
0x180002184  cmp     r15d, edx
0x180002187  jb      short loc_180002205
0x180002189  mov     r9d, [r12]
0x18000218d  add     r9, [rbp+var_30]
0x180002191  add     r9, rdx
0x180002194  mov     [rbp+var_30], r9
0x180002198  sub     r15d, edx
0x18000219b  jmp     short loc_1800021F1
0x18000219d  mov     eax, 80090005h
0x1800021a2  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800021a9  mov     ecx, eax
0x1800021ab  mov     [rbp+arg_8], eax
0x1800021ae  mov     r9d, 135h
0x1800021b4  lea     rdx, aDwres; "dwRes"
0x1800021bb  call    DebugTraceError
0x1800021c0  mov     eax, [r13+0]
0x1800021c4  mov     qword ptr [rax+rbx], 0
0x1800021cc  mov     dword ptr [r12], 0
0x1800021d4  mov     eax, [r13+0]
0x1800021d8  lea     r10, lpValueName
0x1800021df  xor     r13d, r13d
0x1800021e2  mov     [rax+rbx], r13
0x1800021e6  mov     eax, [rbp+arg_8]
0x1800021e9  mov     [r12], r13d
0x1800021ed  mov     r9, [rbp+var_30]
0x1800021f1  mov     edx, [rbp+arg_10]
0x1800021f4  mov     ecx, [rbp+arg_18]
0x1800021f7  inc     edx
0x1800021f9  jmp     loc_1800020C4
0x1800021fe  inc     ecx
0x180002200  jmp     loc_1800020B0
0x180002205  mov     r9d, 12Ah
0x18000220b  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180002212  mov     ecx, 80090028h
0x180002217  jmp     loc_18000205F
0x18000221c  mov     cs:qword_18002AF48, rbx
0x180002223  mov     rbx, r13
0x180002226  lea     rcx, g_csKeyProtectorLock; CriticalSection
0x18000222d  mov     cs:dword_18002AF50, 1
0x180002237  call    cs:__imp_RtlLeaveCriticalSection
0x18000223d  mov     rcx, [rbp+var_28]; hKey
0x180002241  test    rcx, rcx
0x180002244  jz      short loc_18000224C
0x180002246  call    cs:__imp_RegCloseKey
0x18000224c  mov     rcx, [rbp+var_20]; hKey
0x180002250  test    rcx, rcx
0x180002253  jz      short loc_18000225B
0x180002255  call    cs:__imp_RegCloseKey
0x18000225b  test    rbx, rbx
0x18000225e  jz      short loc_180002268
0x180002260  mov     rcx, rbx
0x180002263  call    MSCryptFree
0x180002268  add     rsp, 68h
0x18000226c  pop     r15
0x18000226e  pop     r14
0x180002270  pop     r13
0x180002272  pop     r12
0x180002274  pop     rdi
0x180002275  pop     rsi
0x180002276  pop     rbx
0x180002277  pop     rbp
0x180002278  retn
```
