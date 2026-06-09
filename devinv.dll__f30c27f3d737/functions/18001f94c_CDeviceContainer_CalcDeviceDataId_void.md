# CDeviceContainer::CalcDeviceDataId(void)

- ea: `0x18001f94c`
- end: `0x18001fce5`
- name: `?CalcDeviceDataId@CDeviceContainer@@AEAAJXZ`
- size: `921`
- prototype: `__int64 __fastcall(CDeviceContainer *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180021670`

## callees

- `0x180005e40`
- `0x180006d02`
- `0x180007014`
- `0x18001f94c`
- `0x180037100`
- `0x180038368`
- `0x18006041c`
- `0x180066c10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fa7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fb9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fbc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fa7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fb9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fbc3`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18001fcc1`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18001fcc1`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18001fa6d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18001fa6d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18001fb5b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18001fb5b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18001fb8e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18001fb8e`

## string_xrefs

- `0x18001fa90`: `Failed to create hash 0x%08x`

## pseudocode

```c
__int64 __fastcall CDeviceContainer::CalcDeviceDataId(CDeviceContainer *this)
{
  BYTE *v1; // rax
  bool v2; // cc
  _QWORD *v4; // rax
  _QWORD *v5; // rax
  _QWORD *v6; // rax
  const wchar_t *v7; // rax
  const wchar_t *v8; // rax
  signed int v9; // eax
  unsigned int v10; // ebx
  const char *v11; // rdi
  __int64 v12; // r14
  FILE *v13; // rax
  FILE *v14; // rax
  FILE *v15; // rax
  unsigned int i; // ebx
  BYTE *v17; // r14
  __int64 v18; // r8
  unsigned int v19; // r8d
  signed int v20; // eax
  signed int LastError; // eax
  FILE *v22; // rax
  FILE *v23; // rax
  FILE *v24; // rax
  HCRYPTHASH *phHash; // [rsp+20h] [rbp-A9h]
  __int64 pdwDataLen; // [rsp+30h] [rbp-99h] BYREF
  HCRYPTHASH hHash; // [rsp+38h] [rbp-91h] BYREF
  BYTE *pbData; // [rsp+40h] [rbp-89h]
  _QWORD *v30; // [rsp+48h] [rbp-81h]
  _QWORD *v31; // [rsp+50h] [rbp-79h]
  _QWORD *v32; // [rsp+58h] [rbp-71h]
  const wchar_t *v33; // [rsp+60h] [rbp-69h]
  const wchar_t *v34; // [rsp+68h] [rbp-61h]
  BYTE v35[16]; // [rsp+70h] [rbp-59h] BYREF
  unsigned __int16 v36[48]; // [rsp+80h] [rbp-49h] BYREF

  v1 = (BYTE *)this + 56;
  v2 = *((_QWORD *)this + 10) <= 7u;
  LODWORD(pdwDataLen) = 0;
  *(_OWORD *)v35 = 0;
  hHash = 0;
  if ( !v2 )
    v1 = *(BYTE **)v1;
  pbData = v1;
  if ( *((_QWORD *)this + 13) )
  {
    v4 = (_QWORD *)((char *)this + 88);
    if ( *((_QWORD *)this + 14) > 7u )
      v4 = (_QWORD *)*v4;
    v30 = v4;
  }
  else
  {
    v30 = 0;
  }
  if ( *((_QWORD *)this + 17) )
  {
    v5 = (_QWORD *)((char *)this + 120);
    if ( *((_QWORD *)this + 18) > 7u )
      v5 = (_QWORD *)*v5;
    v31 = v5;
  }
  else
  {
    v31 = 0;
  }
  if ( *((_QWORD *)this + 21) )
  {
    v6 = (_QWORD *)((char *)this + 152);
    if ( *((_QWORD *)this + 22) > 7u )
      v6 = (_QWORD *)*v6;
    v32 = v6;
  }
  else
  {
    v32 = 0;
  }
  if ( *((_QWORD *)this + 29) )
  {
    v7 = (const wchar_t *)((char *)this + 216);
    if ( *((_QWORD *)this + 30) > 7u )
      v7 = *(const wchar_t **)v7;
    v33 = v7;
  }
  else
  {
    v33 = L"Unknown";
  }
  if ( *((_QWORD *)this + 25) )
  {
    v8 = (const wchar_t *)((char *)this + 184);
    if ( *((_QWORD *)this + 26) > 7u )
      v8 = *(const wchar_t **)v8;
    v34 = v8;
  }
  else
  {
    v34 = L"Unknown";
  }
  if ( CryptCreateHash(*(_QWORD *)(*((_QWORD *)this + 89) + 96LL), 0x8003u, 0, 0, &hHash) )
  {
    for ( i = 0; i < 6; ++i )
    {
      v17 = (&pbData)[i];
      if ( v17 )
      {
        v18 = -1;
        do
          ++v18;
        while ( *(_WORD *)&v17[2 * v18] );
        if ( !CryptHashData(hHash, (&pbData)[i], 2 * v18, 0) )
        {
          LastError = GetLastError();
          v10 = LastError;
          if ( LastError > 0 )
            v10 = (unsigned __int16)LastError | 0x80070000;
          LODWORD(phHash) = v10;
          AslLogCallPrintf(
            2,
            "CDeviceContainer::CalcDeviceDataId",
            1511,
            "Failed to hash id 0x%08x [%ws]",
            phHash,
            v17,
            pdwDataLen);
          if ( EnableDevInvStdErrLog )
          {
            v22 = o___acrt_iob_func_0(2u);
            fprintf(v22, "Error: %s, %u: ", "CDeviceContainer::CalcDeviceDataId", 1511);
            v23 = o___acrt_iob_func_0(2u);
            fprintf(v23, "Failed to hash id 0x%08x [%ws]", v10, v17);
            v24 = o___acrt_iob_func_0(2u);
            fprintf(v24, "\n");
          }
          if ( g_DeviceMapLogFunction )
            TraceMessageCallback(0x2000000, "Failed to hash id 0x%08x [%ws]", v10, v17);
          goto LABEL_55;
        }
      }
    }
    LODWORD(pdwDataLen) = 16;
    if ( !CryptGetHashParam(hHash, 2u, v35, (DWORD *)&pdwDataLen, 0) )
    {
      v20 = GetLastError();
      v10 = v20;
      if ( v20 > 0 )
        v10 = (unsigned __int16)v20 | 0x80070000;
      v11 = "Failed to get hash value 0x%08x";
      v12 = 1522;
      goto LABEL_32;
    }
    v10 = CDeviceMap::GuidToString((struct _GUID *)v35, v36, v19);
    if ( (v10 & 0x80000000) != 0 )
    {
      v11 = "Failed to convert hash to string 0x%08x";
      v12 = 1529;
      goto LABEL_32;
    }
    v10 = CDeviceMap::LookupString(*((CDeviceMap **)this + 89), v36, (const unsigned __int16 **)this + 6);
  }
  else
  {
    v9 = GetLastError();
    v10 = v9;
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
    v11 = "Failed to create hash 0x%08x";
    v12 = 1499;
LABEL_32:
    LODWORD(phHash) = v10;
    AslLogCallPrintf(2, "CDeviceContainer::CalcDeviceDataId", v12, v11, phHash);
    if ( EnableDevInvStdErrLog )
    {
      v13 = o___acrt_iob_func_0(2u);
      fprintf(v13, "Error: %s, %u: ", "CDeviceContainer::CalcDeviceDataId", v12);
      v14 = o___acrt_iob_func_0(2u);
      fprintf(v14, v11, v10);
      v15 = o___acrt_iob_func_0(2u);
      fprintf(v15, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, v11, v10);
  }
LABEL_55:
  if ( hHash )
    CryptDestroyHash(hHash);
  return v10;
}

```

## disassembly

```asm
0x18001f94c  push    rbp
0x18001f94e  push    rbx
0x18001f94f  push    rsi
0x18001f950  push    rdi
0x18001f951  push    r14
0x18001f953  push    r15
0x18001f955  lea     rbp, [rsp-2Fh]
0x18001f95a  sub     rsp, 0F8h
0x18001f961  mov     rax, cs:__security_cookie
0x18001f968  xor     rax, rsp
0x18001f96b  mov     [rbp+57h+var_40], rax
0x18001f96f  xor     r15d, r15d
0x18001f972  lea     rax, [rcx+38h]
0x18001f976  cmp     qword ptr [rax+18h], 7
0x18001f97b  xorps   xmm0, xmm0
0x18001f97e  mov     rdi, rcx
0x18001f981  mov     dword ptr [rsp+120h+pdwDataLen], r15d
0x18001f986  movups  xmmword ptr [rbp+57h+var_B0], xmm0
0x18001f98a  mov     [rsp+120h+hHash], r15
0x18001f98f  jbe     short loc_18001F994
0x18001f991  mov     rax, [rax]
0x18001f994  mov     [rsp+120h+pbData], rax
0x18001f999  cmp     [rcx+68h], r15
0x18001f99d  jz      short loc_18001F9B4
0x18001f99f  lea     rax, [rcx+58h]
0x18001f9a3  cmp     qword ptr [rax+18h], 7
0x18001f9a8  jbe     short loc_18001F9AD
0x18001f9aa  mov     rax, [rax]
0x18001f9ad  mov     [rsp+120h+var_D8], rax
0x18001f9b2  jmp     short loc_18001F9B9
0x18001f9b4  mov     [rsp+120h+var_D8], r15
0x18001f9b9  cmp     [rcx+88h], r15
0x18001f9c0  jz      short loc_18001F9D6
0x18001f9c2  lea     rax, [rcx+78h]
0x18001f9c6  cmp     qword ptr [rax+18h], 7
0x18001f9cb  jbe     short loc_18001F9D0
0x18001f9cd  mov     rax, [rax]
0x18001f9d0  mov     [rbp+57h+var_D0], rax
0x18001f9d4  jmp     short loc_18001F9DA
0x18001f9d6  mov     [rbp+57h+var_D0], r15
0x18001f9da  cmp     [rcx+0A8h], r15
0x18001f9e1  jz      short loc_18001F9FA
0x18001f9e3  lea     rax, [rcx+98h]
0x18001f9ea  cmp     qword ptr [rax+18h], 7
0x18001f9ef  jbe     short loc_18001F9F4
0x18001f9f1  mov     rax, [rax]
0x18001f9f4  mov     [rbp+57h+var_C8], rax
0x18001f9f8  jmp     short loc_18001F9FE
0x18001f9fa  mov     [rbp+57h+var_C8], r15
0x18001f9fe  lea     rcx, aUnknown; "Unknown"
0x18001fa05  cmp     [rdi+0E8h], r15
0x18001fa0c  jz      short loc_18001FA25
0x18001fa0e  lea     rax, [rdi+0D8h]
0x18001fa15  cmp     qword ptr [rax+18h], 7
0x18001fa1a  jbe     short loc_18001FA1F
0x18001fa1c  mov     rax, [rax]
0x18001fa1f  mov     [rbp+57h+var_C0], rax
0x18001fa23  jmp     short loc_18001FA29
0x18001fa25  mov     [rbp+57h+var_C0], rcx
0x18001fa29  cmp     [rdi+0C8h], r15
0x18001fa30  jz      short loc_18001FA49
0x18001fa32  lea     rax, [rdi+0B8h]
0x18001fa39  cmp     qword ptr [rax+18h], 7
0x18001fa3e  jbe     short loc_18001FA43
0x18001fa40  mov     rax, [rax]
0x18001fa43  mov     [rbp+57h+var_B8], rax
0x18001fa47  jmp     short loc_18001FA4D
0x18001fa49  mov     [rbp+57h+var_B8], rcx
0x18001fa4d  mov     rcx, [rdi+2C8h]
0x18001fa54  lea     rax, [rsp+120h+hHash]
0x18001fa59  xor     r9d, r9d; dwFlags
0x18001fa5c  mov     [rsp+120h+phHash], rax; phHash
0x18001fa61  xor     r8d, r8d; hKey
0x18001fa64  mov     edx, 8003h; Algid
0x18001fa69  mov     rcx, [rcx+60h]; hProv
0x18001fa6d  call    cs:__imp_CryptCreateHash
0x18001fa73  test    eax, eax
0x18001fa75  jnz     loc_18001FB30
0x18001fa7b  call    cs:__imp_GetLastError
0x18001fa81  mov     ebx, eax
0x18001fa83  test    eax, eax
0x18001fa85  jle     short loc_18001FA90
0x18001fa87  movzx   ebx, ax
0x18001fa8a  or      ebx, 80070000h
0x18001fa90  lea     rdi, aFailedToCreate_0; "Failed to create hash 0x%08x"
0x18001fa97  mov     r14d, 5DBh
0x18001fa9d  mov     esi, 2
0x18001faa2  mov     r9, rdi
0x18001faa5  mov     dword ptr [rsp+120h+phHash], ebx
0x18001faa9  mov     r8, r14
0x18001faac  lea     rdx, aCdevicecontain; "CDeviceContainer::CalcDeviceDataId"
0x18001fab3  mov     ecx, esi
0x18001fab5  call    AslLogCallPrintf
0x18001faba  cmp     cs:EnableDevInvStdErrLog, r15d
0x18001fac1  jz      short loc_18001FB0E
0x18001fac3  mov     ecx, esi; Ix
0x18001fac5  call    _o___acrt_iob_func_0
0x18001faca  mov     rcx, rax; Stream
0x18001facd  lea     r8, aCdevicecontain; "CDeviceContainer::CalcDeviceDataId"
0x18001fad4  mov     r9d, r14d
0x18001fad7  lea     rdx, Format; "Error: %s, %u: "
0x18001fade  call    fprintf
0x18001fae3  mov     ecx, esi; Ix
0x18001fae5  call    _o___acrt_iob_func_0
0x18001faea  mov     rcx, rax; Stream
0x18001faed  mov     r8d, ebx
0x18001faf0  mov     rdx, rdi; Format
0x18001faf3  call    fprintf
0x18001faf8  mov     ecx, esi; Ix
0x18001fafa  call    _o___acrt_iob_func_0
0x18001faff  mov     rcx, rax; Stream
0x18001fb02  lea     rdx, asc_18011EAD8; "\n"
0x18001fb09  call    fprintf
0x18001fb0e  cmp     cs:g_DeviceMapLogFunction, r15
0x18001fb15  jz      loc_18001FCB7
0x18001fb1b  mov     r8d, ebx
0x18001fb1e  mov     rdx, rdi
0x18001fb21  mov     ecx, 2000000h
0x18001fb26  call    TraceMessageCallback
0x18001fb2b  jmp     loc_18001FCB7
0x18001fb30  mov     ebx, r15d
0x18001fb33  mov     eax, ebx
0x18001fb35  mov     r14, [rsp+rax*8+120h+pbData]
0x18001fb3a  test    r14, r14
0x18001fb3d  jz      short loc_18001FB65
0x18001fb3f  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001fb43  inc     r8
0x18001fb46  cmp     [r14+r8*2], r15w
0x18001fb4b  jnz     short loc_18001FB43
0x18001fb4d  mov     rcx, [rsp+120h+hHash]; hHash
0x18001fb52  add     r8d, r8d; dwDataLen
0x18001fb55  xor     r9d, r9d; dwFlags
0x18001fb58  mov     rdx, r14; pbData
0x18001fb5b  call    cs:__imp_CryptHashData
0x18001fb61  test    eax, eax
0x18001fb63  jz      short loc_18001FBC3
0x18001fb65  inc     ebx
0x18001fb67  cmp     ebx, 6
0x18001fb6a  jb      short loc_18001FB33
0x18001fb6c  mov     rcx, [rsp+120h+hHash]; hHash
0x18001fb71  lea     r9, [rsp+120h+pdwDataLen]; pdwDataLen
0x18001fb76  mov     esi, 2
0x18001fb7b  mov     dword ptr [rsp+120h+pdwDataLen], 10h
0x18001fb83  mov     edx, esi; dwParam
0x18001fb85  mov     dword ptr [rsp+120h+phHash], r15d; dwFlags
0x18001fb8a  lea     r8, [rbp+57h+var_B0]; pbData
0x18001fb8e  call    cs:__imp_CryptGetHashParam
0x18001fb94  test    eax, eax
0x18001fb96  jnz     loc_18001FC7C
0x18001fb9c  call    cs:__imp_GetLastError
0x18001fba2  mov     ebx, eax
0x18001fba4  test    eax, eax
0x18001fba6  jle     short loc_18001FBB1
0x18001fba8  movzx   ebx, ax
0x18001fbab  or      ebx, 80070000h
0x18001fbb1  lea     rdi, aFailedToGetHas; "Failed to get hash value 0x%08x"
0x18001fbb8  mov     r14d, 5F2h
0x18001fbbe  jmp     loc_18001FAA2
0x18001fbc3  call    cs:__imp_GetLastError
0x18001fbc9  mov     ebx, eax
0x18001fbcb  test    eax, eax
0x18001fbcd  jle     short loc_18001FBD8
0x18001fbcf  movzx   ebx, ax
0x18001fbd2  or      ebx, 80070000h
0x18001fbd8  lea     rdi, aFailedToHashId; "Failed to hash id 0x%08x [%ws]"
0x18001fbdf  mov     [rsp+120h+var_F8], r14
0x18001fbe4  mov     esi, 2
0x18001fbe9  mov     dword ptr [rsp+120h+phHash], ebx
0x18001fbed  mov     r9, rdi
0x18001fbf0  lea     rdx, aCdevicecontain; "CDeviceContainer::CalcDeviceDataId"
0x18001fbf7  mov     ecx, esi
0x18001fbf9  mov     r8d, 5E7h
0x18001fbff  call    AslLogCallPrintf
0x18001fc04  cmp     cs:EnableDevInvStdErrLog, r15d
0x18001fc0b  jz      short loc_18001FC5E
0x18001fc0d  mov     ecx, esi; Ix
0x18001fc0f  call    _o___acrt_iob_func_0
0x18001fc14  mov     rcx, rax; Stream
0x18001fc17  lea     r8, aCdevicecontain; "CDeviceContainer::CalcDeviceDataId"
0x18001fc1e  mov     r9d, 5E7h
0x18001fc24  lea     rdx, Format; "Error: %s, %u: "
0x18001fc2b  call    fprintf
0x18001fc30  mov     ecx, esi; Ix
0x18001fc32  call    _o___acrt_iob_func_0
0x18001fc37  mov     r9, r14
0x18001fc3a  mov     r8d, ebx
0x18001fc3d  mov     rdx, rdi; Format
0x18001fc40  mov     rcx, rax; Stream
0x18001fc43  call    fprintf
0x18001fc48  mov     ecx, esi; Ix
0x18001fc4a  call    _o___acrt_iob_func_0
0x18001fc4f  mov     rcx, rax; Stream
0x18001fc52  lea     rdx, asc_18011EAD8; "\n"
0x18001fc59  call    fprintf
0x18001fc5e  cmp     cs:g_DeviceMapLogFunction, r15
0x18001fc65  jz      short loc_18001FCB7
0x18001fc67  mov     r9, r14
0x18001fc6a  mov     r8d, ebx
0x18001fc6d  mov     rdx, rdi
0x18001fc70  mov     ecx, 2000000h
0x18001fc75  call    TraceMessageCallback
0x18001fc7a  jmp     short loc_18001FCB7
0x18001fc7c  lea     rdx, [rbp+57h+var_A0]; unsigned __int16 *
0x18001fc80  lea     rcx, [rbp+57h+var_B0]; struct _GUID *
0x18001fc84  call    ?GuidToString@CDeviceMap@@SAJPEAU_GUID@@PEAGK@Z; CDeviceMap::GuidToString(_GUID *,ushort *,ulong)
0x18001fc89  mov     ebx, eax
0x18001fc8b  test    eax, eax
0x18001fc8d  jns     short loc_18001FCA1
0x18001fc8f  lea     rdi, aFailedToConver; "Failed to convert hash to string 0x%08x"
0x18001fc96  mov     r14d, 5F9h
0x18001fc9c  jmp     loc_18001FAA2
0x18001fca1  mov     rcx, [rdi+2C8h]; this
0x18001fca8  lea     r8, [rdi+30h]; unsigned __int16 **
0x18001fcac  lea     rdx, [rbp+57h+var_A0]; unsigned __int16 *
0x18001fcb0  call    ?LookupString@CDeviceMap@@QEAAJPEBGAEAPEBG@Z; CDeviceMap::LookupString(ushort const *,ushort const * &)
0x18001fcb5  mov     ebx, eax
0x18001fcb7  mov     rcx, [rsp+120h+hHash]; hHash
0x18001fcbc  test    rcx, rcx
0x18001fcbf  jz      short loc_18001FCC7
0x18001fcc1  call    cs:__imp_CryptDestroyHash
0x18001fcc7  mov     eax, ebx
0x18001fcc9  mov     rcx, [rbp+57h+var_40]
0x18001fccd  xor     rcx, rsp; StackCookie
0x18001fcd0  call    __security_check_cookie
0x18001fcd5  add     rsp, 0F8h
0x18001fcdc  pop     r15
0x18001fcde  pop     r14
0x18001fce0  pop     rdi
0x18001fce1  pop     rsi
0x18001fce2  pop     rbx
0x18001fce3  pop     rbp
0x18001fce4  retn
```
