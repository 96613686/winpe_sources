# SignData(ushort const *,ushort const *,uchar *,ulong,ulong,uchar * *,ulong *)

- ea: `0x18004bf7c`
- end: `0x18004c177`
- name: `?SignData@@YAJPEBG0PEAEKKPEAPEAEPEAK@Z`
- size: `507`
- prototype: `__int64 __fastcall(LPCWSTR pszKeyName, LPCWSTR pszProviderName, PUCHAR pbInput, ULONG cbInput, unsigned int, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18005160c`

## callees

- `0x18000dd20`
- `0x1800140d0`
- `0x180014148`
- `0x1800206a8`
- `0x1800459a4`
- `0x18004bf7c`

## import_xrefs

- `ncrypt!NCryptSignHash` at `0x18004c095`
- `ncrypt!NCryptSignHash` at `0x18004c0fe`
- `ncrypt!NCryptSignHash` at `0x18004c095`
- `ncrypt!NCryptSignHash` at `0x18004c0fe`
- `ncrypt!NCryptFreeObject` at `0x18004c13f`
- `ncrypt!NCryptFreeObject` at `0x18004c14e`
- `ncrypt!NCryptFreeObject` at `0x18004c13f`
- `ncrypt!NCryptFreeObject` at `0x18004c14e`
- `ncrypt!NCryptOpenKey` at `0x18004c048`
- `ncrypt!NCryptOpenKey` at `0x18004c048`
- `ncrypt!NCryptOpenStorageProvider` at `0x18004c015`
- `ncrypt!NCryptOpenStorageProvider` at `0x18004c015`

## pseudocode

```c
__int64 __fastcall SignData(
        LPCWSTR pszKeyName,
        LPCWSTR pszProviderName,
        PUCHAR pbInput,
        ULONG cbInput,
        char a5,
        unsigned __int8 **a6,
        unsigned int *a7)
{
  SECURITY_STATUS v9; // eax
  __int64 v10; // rdx
  BYTE *v11; // rbx
  BYTE *v12; // rdi
  DWORD v13; // ecx
  unsigned int v14; // ebx
  int v16; // [rsp+48h] [rbp-11h] BYREF
  DWORD pcbResult; // [rsp+4Ch] [rbp-Dh] BYREF
  DWORD cbHashValue; // [rsp+50h] [rbp-9h] BYREF
  unsigned int v19; // [rsp+54h] [rbp-5h] BYREF
  DWORD v20; // [rsp+58h] [rbp-1h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+60h] [rbp+7h] BYREF
  const WCHAR *pPaddingInfo; // [rsp+68h] [rbp+Fh] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+70h] [rbp+17h] BYREF
  PBYTE pbHashValue; // [rsp+78h] [rbp+1Fh] BYREF
  _QWORD v25[3]; // [rsp+80h] [rbp+27h] BYREF

  v16 = 0;
  v20 = 0;
  pbHashValue = 0;
  v25[0] = "SignData";
  cbHashValue = 0;
  v25[1] = &v16;
  v19 = 0;
  phProvider = 0;
  phKey = 0;
  pcbResult = 0;
  pPaddingInfo = 0;
  v16 = HashData(pbInput, cbInput, (const unsigned __int16 *)pbInput, &pbHashValue, &cbHashValue);
  v9 = NCryptOpenStorageProvider(&phProvider, pszProviderName, 0);
  v11 = pbHashValue;
  v16 = v9;
  if ( v9 >= 0 )
  {
    v16 = NCryptOpenKey(phProvider, &phKey, pszKeyName, 0, 8 * (a5 & 4 | 8));
    if ( v16 >= 0 )
    {
      pPaddingInfo = L"SHA256";
      v16 = NCryptSignHash(phKey, &pPaddingInfo, v11, cbHashValue, 0, 0, &pcbResult, 2u);
      if ( v16 >= 0 )
      {
        v16 = ULongLongToULong(pcbResult, &v19);
        if ( v16 >= 0 )
        {
          v12 = (BYTE *)SafeHeapAlloc(v19);
          if ( v12 )
          {
            v16 = NCryptSignHash(phKey, &pPaddingInfo, v11, cbHashValue, v12, pcbResult, &v20, 2u);
            if ( v16 >= 0 )
            {
              v13 = pcbResult;
              if ( v20 == pcbResult )
              {
                *a6 = v12;
                *a7 = v13;
              }
              else
              {
                v16 = -2147418113;
              }
            }
          }
          else
          {
            v16 = -2147024882;
          }
        }
      }
    }
  }
  if ( v11 )
    SafeHeapFree(v11);
  if ( phKey )
    NCryptFreeObject(phKey);
  if ( phProvider )
    NCryptFreeObject(phProvider);
  v14 = v16;
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v25, v10);
  return v14;
}

```

## disassembly

```asm
0x18004bf7c  mov     r11, rsp
0x18004bf7f  mov     [r11+8], rbx
0x18004bf83  mov     [r11+10h], rdi
0x18004bf87  push    rbp
0x18004bf88  lea     rbp, [r11-47h]
0x18004bf8c  sub     rsp, 90h
0x18004bf93  mov     rdi, rcx
0x18004bf96  mov     [rbp+3Fh+var_50], 0
0x18004bf9d  mov     eax, r9d
0x18004bfa0  mov     [rbp+3Fh+var_40], 0
0x18004bfa7  lea     rcx, aSigndata; "SignData"
0x18004bfae  mov     [rbp+3Fh+pbHashValue], 0
0x18004bfb6  mov     [rbp+3Fh+var_18], rcx
0x18004bfba  lea     r9, [rbp+3Fh+pbHashValue]; unsigned __int8 **
0x18004bfbe  lea     rcx, [rbp+3Fh+var_50]
0x18004bfc2  mov     [rbp+3Fh+cbHashValue], 0
0x18004bfc9  mov     [rbp+3Fh+var_10], rcx
0x18004bfcd  mov     rbx, rdx
0x18004bfd0  lea     rcx, [rbp+3Fh+cbHashValue]
0x18004bfd4  mov     [rbp+3Fh+var_44], 0
0x18004bfdb  mov     [r11-78h], rcx
0x18004bfdf  mov     edx, eax; cbInput
0x18004bfe1  mov     rcx, r8; pbInput
0x18004bfe4  mov     [rbp+3Fh+phProvider], 0
0x18004bfec  mov     [rbp+3Fh+phKey], 0
0x18004bff4  mov     [rbp+3Fh+var_4C], 0
0x18004bffb  mov     [rbp+3Fh+pPaddingInfo], 0
0x18004c003  call    ?HashData@@YAJPEAEKPEBGPEAPEAEPEAK@Z; HashData(uchar *,ulong,ushort const *,uchar * *,ulong *)
0x18004c008  xor     r8d, r8d; dwFlags
0x18004c00b  mov     [rbp+3Fh+var_50], eax
0x18004c00e  mov     rdx, rbx; pszProviderName
0x18004c011  lea     rcx, [rbp+3Fh+phProvider]; phProvider
0x18004c015  call    cs:__imp_NCryptOpenStorageProvider
0x18004c01b  mov     rbx, [rbp+3Fh+pbHashValue]
0x18004c01f  mov     [rbp+3Fh+var_50], eax
0x18004c022  test    eax, eax
0x18004c024  js      loc_18004C129
0x18004c02a  mov     eax, dword ptr [rbp+3Fh+arg_20]
0x18004c02d  lea     rdx, [rbp+3Fh+phKey]; phKey
0x18004c031  mov     rcx, [rbp+3Fh+phProvider]; hProvider
0x18004c035  and     eax, 4
0x18004c038  or      eax, 8
0x18004c03b  xor     r9d, r9d; dwLegacyKeySpec
0x18004c03e  shl     eax, 3
0x18004c041  mov     r8, rdi; pszKeyName
0x18004c044  mov     [rsp+90h+dwFlags], eax; dwFlags
0x18004c048  call    cs:__imp_NCryptOpenKey
0x18004c04e  mov     [rbp+3Fh+var_50], eax
0x18004c051  test    eax, eax
0x18004c053  js      loc_18004C129
0x18004c059  mov     r9d, [rbp+3Fh+cbHashValue]; cbHashValue
0x18004c05d  lea     rax, aSha256; "SHA256"
0x18004c064  mov     rcx, [rbp+3Fh+phKey]; hKey
0x18004c068  lea     rdx, [rbp+3Fh+pPaddingInfo]; pPaddingInfo
0x18004c06c  mov     [rsp+90h+var_58], 2; dwFlags
0x18004c074  mov     r8, rbx; pbHashValue
0x18004c077  mov     [rbp+3Fh+pPaddingInfo], rax
0x18004c07b  lea     rax, [rbp+3Fh+var_4C]
0x18004c07f  mov     [rsp+90h+pcbResult], rax; pcbResult
0x18004c084  mov     [rsp+90h+cbSignature], 0; cbSignature
0x18004c08c  mov     qword ptr [rsp+90h+dwFlags], 0; pbSignature
0x18004c095  call    cs:__imp_NCryptSignHash
0x18004c09b  mov     [rbp+3Fh+var_50], eax
0x18004c09e  test    eax, eax
0x18004c0a0  js      loc_18004C129
0x18004c0a6  mov     ecx, [rbp+3Fh+var_4C]; unsigned __int64
0x18004c0a9  lea     rdx, [rbp+3Fh+var_44]; unsigned int *
0x18004c0ad  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18004c0b2  mov     [rbp+3Fh+var_50], eax
0x18004c0b5  test    eax, eax
0x18004c0b7  js      short loc_18004C129
0x18004c0b9  mov     ecx, [rbp+3Fh+var_44]; unsigned __int64
0x18004c0bc  call    ?SafeHeapAlloc@@YAPEAX_K@Z; SafeHeapAlloc(unsigned __int64)
0x18004c0c1  mov     rdi, rax
0x18004c0c4  test    rax, rax
0x18004c0c7  jnz     short loc_18004C0D2
0x18004c0c9  mov     [rbp+3Fh+var_50], 8007000Eh
0x18004c0d0  jmp     short loc_18004C129
0x18004c0d2  mov     r9d, [rbp+3Fh+cbHashValue]; cbHashValue
0x18004c0d6  lea     rax, [rbp+3Fh+var_40]
0x18004c0da  mov     rcx, [rbp+3Fh+phKey]; hKey
0x18004c0de  lea     rdx, [rbp+3Fh+pPaddingInfo]; pPaddingInfo
0x18004c0e2  mov     [rsp+90h+var_58], 2; dwFlags
0x18004c0ea  mov     r8, rbx; pbHashValue
0x18004c0ed  mov     [rsp+90h+pcbResult], rax; pcbResult
0x18004c0f2  mov     eax, [rbp+3Fh+var_4C]
0x18004c0f5  mov     [rsp+90h+cbSignature], eax; cbSignature
0x18004c0f9  mov     qword ptr [rsp+90h+dwFlags], rdi; pbSignature
0x18004c0fe  call    cs:__imp_NCryptSignHash
0x18004c104  mov     [rbp+3Fh+var_50], eax
0x18004c107  test    eax, eax
0x18004c109  js      short loc_18004C129
0x18004c10b  mov     ecx, [rbp+3Fh+var_4C]
0x18004c10e  cmp     [rbp+3Fh+var_40], ecx
0x18004c111  jz      short loc_18004C11C
0x18004c113  mov     [rbp+3Fh+var_50], 8000FFFFh
0x18004c11a  jmp     short loc_18004C129
0x18004c11c  mov     rax, [rbp+3Fh+arg_28]
0x18004c120  mov     [rax], rdi
0x18004c123  mov     rax, [rbp+3Fh+arg_30]
0x18004c127  mov     [rax], ecx
0x18004c129  test    rbx, rbx
0x18004c12c  jz      short loc_18004C136
0x18004c12e  mov     rcx, rbx; void *
0x18004c131  call    ?SafeHeapFree@@YAHPEAX@Z; SafeHeapFree(void *)
0x18004c136  mov     rcx, [rbp+3Fh+phKey]; hObject
0x18004c13a  test    rcx, rcx
0x18004c13d  jz      short loc_18004C145
0x18004c13f  call    cs:__imp_NCryptFreeObject
0x18004c145  mov     rcx, [rbp+3Fh+phProvider]; hObject
0x18004c149  test    rcx, rcx
0x18004c14c  jz      short loc_18004C154
0x18004c14e  call    cs:__imp_NCryptFreeObject
0x18004c154  mov     ebx, [rbp+3Fh+var_50]
0x18004c157  lea     rcx, [rbp+3Fh+var_18]; this
0x18004c15b  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18004c160  lea     r11, [rsp+90h+var_s0]
0x18004c168  mov     eax, ebx
0x18004c16a  mov     rbx, [r11+10h]
0x18004c16e  mov     rdi, [r11+18h]
0x18004c172  mov     rsp, r11
0x18004c175  pop     rbp
0x18004c176  retn
```
