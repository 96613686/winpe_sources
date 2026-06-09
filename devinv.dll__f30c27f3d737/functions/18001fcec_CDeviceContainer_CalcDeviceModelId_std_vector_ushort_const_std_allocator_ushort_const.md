# CDeviceContainer::CalcDeviceModelId(std::vector<ushort const *,std::allocator<ushort const *>> &)

- ea: `0x18001fcec`
- end: `0x18001fff7`
- name: `?CalcDeviceModelId@CDeviceContainer@@AEAAJAEAV?$vector@PEBGV?$allocator@PEBG@std@@@std@@@Z`
- size: `779`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180020ac8`

## callees

- `0x180005e40`
- `0x180006d02`
- `0x180007014`
- `0x18001fcec`
- `0x180037100`
- `0x180038368`
- `0x18006041c`
- `0x180066c10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fd5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fe93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001feba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fd5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fe93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001feba`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18001ffc8`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x18001ffc8`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18001fd4d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x18001fd4d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18001fe45`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x18001fe45`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18001fe85`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x18001fe85`

## string_xrefs

- `0x18001fd70`: `Failed to create hash 0x%08x`

## pseudocode

```c
__int64 __fastcall CDeviceContainer::CalcDeviceModelId(__int64 a1, __int64 *a2)
{
  __int64 v3; // rcx
  signed int LastError; // eax
  unsigned int v6; // edi
  const char *v7; // rbx
  __int64 v8; // r14
  FILE *v9; // rax
  FILE *v10; // rax
  FILE *v11; // rax
  __int64 v12; // rdx
  unsigned int v13; // ebx
  __int64 v14; // r15
  __int64 v15; // r8
  const BYTE *v16; // rdx
  unsigned int v17; // r8d
  signed int v18; // eax
  signed int v19; // eax
  FILE *v20; // rax
  __int64 v21; // rbx
  FILE *v22; // rax
  FILE *v23; // rax
  HCRYPTHASH *phHash; // [rsp+20h] [rbp-79h]
  __int64 pdwDataLen; // [rsp+30h] [rbp-69h] BYREF
  HCRYPTHASH hHash; // [rsp+38h] [rbp-61h] BYREF
  BYTE pbData[16]; // [rsp+40h] [rbp-59h] BYREF
  unsigned __int16 v29[48]; // [rsp+50h] [rbp-49h] BYREF

  v3 = *(_QWORD *)(a1 + 712);
  LODWORD(pdwDataLen) = 0;
  hHash = 0;
  *(_OWORD *)pbData = 0;
  if ( !CryptCreateHash(*(_QWORD *)(v3 + 96), 0x8003u, 0, 0, &hHash) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    v7 = "Failed to create hash 0x%08x";
    v8 = 1135;
LABEL_5:
    LODWORD(phHash) = v6;
    AslLogCallPrintf(2, "CDeviceContainer::CalcDeviceModelId", v8, v7, phHash);
    if ( EnableDevInvStdErrLog )
    {
      v9 = o___acrt_iob_func_0(2u);
      fprintf(v9, "Error: %s, %u: ", "CDeviceContainer::CalcDeviceModelId", v8);
      v10 = o___acrt_iob_func_0(2u);
      fprintf(v10, v7, v6);
      v11 = o___acrt_iob_func_0(2u);
      fprintf(v11, "\n");
    }
    if ( g_DeviceMapLogFunction )
      TraceMessageCallback(0x2000000, v7, v6);
    goto LABEL_28;
  }
  v12 = *a2;
  if ( !((a2[1] - *a2) >> 3) )
  {
LABEL_15:
    LODWORD(pdwDataLen) = 16;
    if ( CryptGetHashParam(hHash, 2u, pbData, (DWORD *)&pdwDataLen, 0) )
    {
      v6 = CDeviceMap::GuidToString((struct _GUID *)pbData, v29, v17);
      if ( (v6 & 0x80000000) == 0 )
      {
        v6 = CDeviceMap::LookupString(*(CDeviceMap **)(a1 + 712), v29, (const unsigned __int16 **)(a1 + 40));
        goto LABEL_28;
      }
      v7 = "Failed to convert hash to string 0x%08x";
      v8 = 1162;
    }
    else
    {
      v18 = GetLastError();
      v6 = v18;
      if ( v18 > 0 )
        v6 = (unsigned __int16)v18 | 0x80070000;
      v7 = "Failed to get hash value 0x%08x";
      v8 = 1155;
    }
    goto LABEL_5;
  }
  v13 = 0;
  while ( 1 )
  {
    v14 = v13;
    v15 = -1;
    v16 = *(const BYTE **)(v12 + 8LL * v13);
    do
      ++v15;
    while ( *(_WORD *)&v16[2 * v15] );
    if ( !CryptHashData(hHash, v16, 2 * v15, 0) )
      break;
    v12 = *a2;
    if ( ++v13 >= (unsigned __int64)((a2[1] - *a2) >> 3) )
      goto LABEL_15;
  }
  v19 = GetLastError();
  v6 = v19;
  if ( v19 > 0 )
    v6 = (unsigned __int16)v19 | 0x80070000;
  LODWORD(phHash) = v6;
  AslLogCallPrintf(
    2,
    "CDeviceContainer::CalcDeviceModelId",
    1145,
    "Failed to hash id 0x%08x [%ws]",
    phHash,
    *(_QWORD *)(*a2 + 8LL * v13),
    pdwDataLen);
  if ( EnableDevInvStdErrLog )
  {
    v20 = o___acrt_iob_func_0(2u);
    fprintf(v20, "Error: %s, %u: ", "CDeviceContainer::CalcDeviceModelId", 1145);
    v21 = *(_QWORD *)(*a2 + 8LL * v13);
    v22 = o___acrt_iob_func_0(2u);
    fprintf(v22, "Failed to hash id 0x%08x [%ws]", v6, v21);
    v23 = o___acrt_iob_func_0(2u);
    fprintf(v23, "\n");
  }
  if ( g_DeviceMapLogFunction )
    TraceMessageCallback(0x2000000, "Failed to hash id 0x%08x [%ws]", v6, *(_QWORD *)(*a2 + 8 * v14));
LABEL_28:
  if ( hHash )
    CryptDestroyHash(hHash);
  return v6;
}

```

## disassembly

```asm
0x18001fcec  mov     [rsp-8+arg_10], rbx
0x18001fcf1  push    rbp
0x18001fcf2  push    rsi
0x18001fcf3  push    rdi
0x18001fcf4  push    r12
0x18001fcf6  push    r13
0x18001fcf8  push    r14
0x18001fcfa  push    r15
0x18001fcfc  lea     rbp, [rsp-27h]
0x18001fd01  sub     rsp, 0C0h
0x18001fd08  mov     rax, cs:__security_cookie
0x18001fd0f  xor     rax, rsp
0x18001fd12  mov     [rbp+57h+var_40], rax
0x18001fd16  mov     r13, rcx
0x18001fd19  lea     rax, [rbp+57h+hHash]
0x18001fd1d  mov     rcx, [rcx+2C8h]
0x18001fd24  xor     r12d, r12d
0x18001fd27  xorps   xmm0, xmm0
0x18001fd2a  mov     dword ptr [rbp+57h+pdwDataLen], r12d
0x18001fd2e  mov     r14, rdx
0x18001fd31  mov     [rbp+57h+hHash], r12
0x18001fd35  movups  xmmword ptr [rbp+57h+pbData], xmm0
0x18001fd39  mov     rcx, [rcx+60h]; hProv
0x18001fd3d  xor     r9d, r9d; dwFlags
0x18001fd40  xor     r8d, r8d; hKey
0x18001fd43  mov     [rsp+0F0h+phHash], rax; phHash
0x18001fd48  mov     edx, 8003h; Algid
0x18001fd4d  call    cs:__imp_CryptCreateHash
0x18001fd53  test    eax, eax
0x18001fd55  jnz     loc_18001FE10
0x18001fd5b  call    cs:__imp_GetLastError
0x18001fd61  mov     edi, eax
0x18001fd63  test    eax, eax
0x18001fd65  jle     short loc_18001FD70
0x18001fd67  movzx   edi, ax
0x18001fd6a  or      edi, 80070000h
0x18001fd70  lea     rbx, aFailedToCreate_0; "Failed to create hash 0x%08x"
0x18001fd77  mov     r14d, 46Fh
0x18001fd7d  mov     esi, 2
0x18001fd82  mov     r9, rbx
0x18001fd85  mov     dword ptr [rsp+0F0h+phHash], edi
0x18001fd89  mov     r8, r14
0x18001fd8c  lea     rdx, aCdevicecontain_5; "CDeviceContainer::CalcDeviceModelId"
0x18001fd93  mov     ecx, esi
0x18001fd95  call    AslLogCallPrintf
0x18001fd9a  cmp     cs:EnableDevInvStdErrLog, r12d
0x18001fda1  jz      short loc_18001FDEE
0x18001fda3  mov     ecx, esi; Ix
0x18001fda5  call    _o___acrt_iob_func_0
0x18001fdaa  mov     rcx, rax; Stream
0x18001fdad  lea     r8, aCdevicecontain_5; "CDeviceContainer::CalcDeviceModelId"
0x18001fdb4  mov     r9d, r14d
0x18001fdb7  lea     rdx, Format; "Error: %s, %u: "
0x18001fdbe  call    fprintf
0x18001fdc3  mov     ecx, esi; Ix
0x18001fdc5  call    _o___acrt_iob_func_0
0x18001fdca  mov     rcx, rax; Stream
0x18001fdcd  mov     r8d, edi
0x18001fdd0  mov     rdx, rbx; Format
0x18001fdd3  call    fprintf
0x18001fdd8  mov     ecx, esi; Ix
0x18001fdda  call    _o___acrt_iob_func_0
0x18001fddf  mov     rcx, rax; Stream
0x18001fde2  lea     rdx, asc_18011EAD8; "\n"
0x18001fde9  call    fprintf
0x18001fdee  cmp     cs:g_DeviceMapLogFunction, r12
0x18001fdf5  jz      loc_18001FFBF
0x18001fdfb  mov     r8d, edi
0x18001fdfe  mov     rdx, rbx
0x18001fe01  mov     ecx, 2000000h
0x18001fe06  call    TraceMessageCallback
0x18001fe0b  jmp     loc_18001FFBF
0x18001fe10  mov     rdx, [r14]
0x18001fe13  mov     rax, [r14+8]
0x18001fe17  sub     rax, rdx
0x18001fe1a  sar     rax, 3
0x18001fe1e  test    rax, rax
0x18001fe21  jz      short loc_18001FE66
0x18001fe23  mov     ebx, r12d
0x18001fe26  mov     r15d, ebx
0x18001fe29  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001fe2d  mov     rdx, [rdx+r15*8]; pbData
0x18001fe31  inc     r8
0x18001fe34  cmp     [rdx+r8*2], r12w
0x18001fe39  jnz     short loc_18001FE31
0x18001fe3b  mov     rcx, [rbp+57h+hHash]; hHash
0x18001fe3f  add     r8d, r8d; dwDataLen
0x18001fe42  xor     r9d, r9d; dwFlags
0x18001fe45  call    cs:__imp_CryptHashData
0x18001fe4b  test    eax, eax
0x18001fe4d  jz      short loc_18001FEBA
0x18001fe4f  mov     rdx, [r14]
0x18001fe52  inc     ebx
0x18001fe54  mov     rcx, [r14+8]
0x18001fe58  sub     rcx, rdx
0x18001fe5b  mov     eax, ebx
0x18001fe5d  sar     rcx, 3
0x18001fe61  cmp     rax, rcx
0x18001fe64  jb      short loc_18001FE26
0x18001fe66  mov     rcx, [rbp+57h+hHash]; hHash
0x18001fe6a  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x18001fe6e  mov     esi, 2
0x18001fe73  mov     dword ptr [rbp+57h+pdwDataLen], 10h
0x18001fe7a  mov     edx, esi; dwParam
0x18001fe7c  mov     dword ptr [rsp+0F0h+phHash], r12d; dwFlags
0x18001fe81  lea     r8, [rbp+57h+pbData]; pbData
0x18001fe85  call    cs:__imp_CryptGetHashParam
0x18001fe8b  test    eax, eax
0x18001fe8d  jnz     loc_18001FF84
0x18001fe93  call    cs:__imp_GetLastError
0x18001fe99  mov     edi, eax
0x18001fe9b  test    eax, eax
0x18001fe9d  jle     short loc_18001FEA8
0x18001fe9f  movzx   edi, ax
0x18001fea2  or      edi, 80070000h
0x18001fea8  lea     rbx, aFailedToGetHas; "Failed to get hash value 0x%08x"
0x18001feaf  mov     r14d, 483h
0x18001feb5  jmp     loc_18001FD82
0x18001feba  call    cs:__imp_GetLastError
0x18001fec0  mov     edi, eax
0x18001fec2  test    eax, eax
0x18001fec4  jle     short loc_18001FECF
0x18001fec6  movzx   edi, ax
0x18001fec9  or      edi, 80070000h
0x18001fecf  mov     rax, [r14]
0x18001fed2  lea     r13, aFailedToHashId; "Failed to hash id 0x%08x [%ws]"
0x18001fed9  mov     ebx, 479h
0x18001fede  lea     rdx, aCdevicecontain_5; "CDeviceContainer::CalcDeviceModelId"
0x18001fee5  mov     esi, 2
0x18001feea  mov     r9, r13
0x18001feed  mov     r8d, ebx
0x18001fef0  mov     rcx, [rax+r15*8]
0x18001fef4  mov     [rsp+0F0h+var_C8], rcx
0x18001fef9  mov     ecx, esi
0x18001fefb  mov     dword ptr [rsp+0F0h+phHash], edi
0x18001feff  call    AslLogCallPrintf
0x18001ff04  cmp     cs:EnableDevInvStdErrLog, r12d
0x18001ff0b  jz      short loc_18001FF62
0x18001ff0d  mov     ecx, esi; Ix
0x18001ff0f  call    _o___acrt_iob_func_0
0x18001ff14  mov     rcx, rax; Stream
0x18001ff17  lea     r8, aCdevicecontain_5; "CDeviceContainer::CalcDeviceModelId"
0x18001ff1e  mov     r9d, ebx
0x18001ff21  lea     rdx, Format; "Error: %s, %u: "
0x18001ff28  call    fprintf
0x18001ff2d  mov     rax, [r14]
0x18001ff30  mov     ecx, esi; Ix
0x18001ff32  mov     rbx, [rax+r15*8]
0x18001ff36  call    _o___acrt_iob_func_0
0x18001ff3b  mov     r9, rbx
0x18001ff3e  mov     r8d, edi
0x18001ff41  mov     rdx, r13; Format
0x18001ff44  mov     rcx, rax; Stream
0x18001ff47  call    fprintf
0x18001ff4c  mov     ecx, esi; Ix
0x18001ff4e  call    _o___acrt_iob_func_0
0x18001ff53  mov     rcx, rax; Stream
0x18001ff56  lea     rdx, asc_18011EAD8; "\n"
0x18001ff5d  call    fprintf
0x18001ff62  cmp     cs:g_DeviceMapLogFunction, r12
0x18001ff69  jz      short loc_18001FFBF
0x18001ff6b  mov     r9, [r14]
0x18001ff6e  mov     r8d, edi
0x18001ff71  mov     rdx, r13
0x18001ff74  mov     ecx, 2000000h
0x18001ff79  mov     r9, [r9+r15*8]
0x18001ff7d  call    TraceMessageCallback
0x18001ff82  jmp     short loc_18001FFBF
0x18001ff84  lea     rdx, [rbp+57h+var_A0]; unsigned __int16 *
0x18001ff88  lea     rcx, [rbp+57h+pbData]; struct _GUID *
0x18001ff8c  call    ?GuidToString@CDeviceMap@@SAJPEAU_GUID@@PEAGK@Z; CDeviceMap::GuidToString(_GUID *,ushort *,ulong)
0x18001ff91  mov     edi, eax
0x18001ff93  test    eax, eax
0x18001ff95  jns     short loc_18001FFA9
0x18001ff97  lea     rbx, aFailedToConver; "Failed to convert hash to string 0x%08x"
0x18001ff9e  mov     r14d, 48Ah
0x18001ffa4  jmp     loc_18001FD82
0x18001ffa9  mov     rcx, [r13+2C8h]; this
0x18001ffb0  lea     r8, [r13+28h]; unsigned __int16 **
0x18001ffb4  lea     rdx, [rbp+57h+var_A0]; unsigned __int16 *
0x18001ffb8  call    ?LookupString@CDeviceMap@@QEAAJPEBGAEAPEBG@Z; CDeviceMap::LookupString(ushort const *,ushort const * &)
0x18001ffbd  mov     edi, eax
0x18001ffbf  mov     rcx, [rbp+57h+hHash]; hHash
0x18001ffc3  test    rcx, rcx
0x18001ffc6  jz      short loc_18001FFCE
0x18001ffc8  call    cs:__imp_CryptDestroyHash
0x18001ffce  mov     eax, edi
0x18001ffd0  mov     rcx, [rbp+57h+var_40]
0x18001ffd4  xor     rcx, rsp; StackCookie
0x18001ffd7  call    __security_check_cookie
0x18001ffdc  mov     rbx, [rsp+0F0h+arg_10]
0x18001ffe4  add     rsp, 0C0h
0x18001ffeb  pop     r15
0x18001ffed  pop     r14
0x18001ffef  pop     r13
0x18001fff1  pop     r12
0x18001fff3  pop     rdi
0x18001fff4  pop     rsi
0x18001fff5  pop     rbp
0x18001fff6  retn
```
