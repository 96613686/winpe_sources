# CDeviceMap::GetIdProperty(CPropertyStore *,_tagpropertykey const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180036a64`
- end: `0x180036c4f`
- name: `?GetIdProperty@CDeviceMap@@QEAAJPEAVCPropertyStore@@AEBU_tagpropertykey@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `491`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18002133c`
- `0x180021670`

## callees

- `0x180005e40`
- `0x180006eb8`
- `0x1800103e0`
- `0x180036a64`
- `0x180037100`
- `0x180059f94`
- `0x180059fd4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036b1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036b1e`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180036c19`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptDestroyHash` at `0x180036c19`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180036b14`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptCreateHash` at `0x180036b14`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180036b62`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptHashData` at `0x180036b62`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180036b8c`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGetHashParam` at `0x180036b8c`

## pseudocode

```c
__int64 __fastcall CDeviceMap::GetIdProperty(
        __int64 a1,
        CPropertyStore *a2,
        const struct _tagpropertykey *a3,
        char **a4)
{
  CPropertyStore *v5; // r12
  signed int Value; // edi
  unsigned int v8; // r8d
  signed int LastError; // eax
  unsigned __int64 v10; // rbx
  __int64 v11; // r8
  unsigned int v12; // r8d
  __int64 v13; // r8
  char *v14; // r15
  size_t v15; // rbx
  FILE *v17; // rax
  FILE *v18; // rax
  FILE *v19; // rax
  HCRYPTHASH hHash; // [rsp+30h] [rbp-E8h] BYREF
  DWORD pdwDataLen[2]; // [rsp+38h] [rbp-E0h] BYREF
  CPropertyStore *v22; // [rsp+40h] [rbp-D8h]
  struct tagPROPVARIANT v23; // [rsp+48h] [rbp-D0h] BYREF
  BYTE v24[16]; // [rsp+60h] [rbp-B8h] BYREF
  unsigned __int16 pbData[48]; // [rsp+70h] [rbp-A8h] BYREF

  v5 = a2;
  v22 = a2;
  memset(&v23, 0, sizeof(v23));
  hHash = 0;
  *(_OWORD *)v24 = 0;
  Value = CPropertyStore::GetValue(a2, a3, &v23);
  if ( Value >= 0 )
  {
    if ( v23.vt == 72 && v23.hVal.QuadPart )
    {
      Value = CDeviceMap::GuidToString(v23.puuid, pbData, v8);
      if ( Value >= 0 )
      {
        if ( !CryptCreateHash(*(_QWORD *)(a1 + 96), 0x8003u, 0, 0, &hHash) )
          goto LABEL_6;
        v10 = -1;
        v11 = -1;
        do
          ++v11;
        while ( pbData[v11] );
        if ( CryptHashData(hHash, (const BYTE *)pbData, 2 * v11, 0)
          && (pdwDataLen[0] = 16, CryptGetHashParam(hHash, 2u, v24, pdwDataLen, 0)) )
        {
          Value = CDeviceMap::GuidToString((struct _GUID *)v24, pbData, v12);
          if ( Value >= 0 )
          {
            do
              ++v10;
            while ( pbData[v10] );
            if ( v10 > (unsigned __int64)a4[3] )
            {
              try
              {
                std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
                  a4,
                  v10,
                  v13,
                  pbData);
              }
              catch ( std::bad_alloc )
              {
                AslLogCallPrintf(2, "CDeviceMap::GetIdProperty", 868, "Out of memory");
                if ( EnableDevInvStdErrLog )
                {
                  v17 = o___acrt_iob_func_0(2u);
                  fprintf(v17, "Error: %s, %u: ", "CDeviceMap::GetIdProperty", 868);
                  v18 = o___acrt_iob_func_0(2u);
                  fprintf(v18, "Out of memory");
                  v19 = o___acrt_iob_func_0(2u);
                  fprintf(v19, "\n");
                }
                if ( g_DeviceMapLogFunction )
                  TraceMessageCallback(0x2000000, "Out of memory");
                pdwDataLen[1] = -2147024888;
                Value = -2147024888;
                v5 = v22;
              }
            }
            else
            {
              if ( (unsigned __int64)a4[3] <= 7 )
                v14 = (char *)a4;
              else
                v14 = *a4;
              a4[2] = (char *)v10;
              v15 = 2 * v10;
              memmove_0(v14, pbData, v15);
              *(_WORD *)&v14[v15] = 0;
            }
          }
        }
        else
        {
LABEL_6:
          LastError = GetLastError();
          Value = LastError;
          if ( LastError > 0 )
            Value = (unsigned __int16)LastError | 0x80070000;
        }
      }
    }
    else
    {
      Value = -2147024809;
    }
  }
  if ( hHash )
    CryptDestroyHash(hHash);
  CPropertyStore::ClearValue(v5, &v23);
  return (unsigned int)Value;
}

```

## disassembly

```asm
0x180036a64  push    rbx
0x180036a66  push    rsi
0x180036a67  push    rdi
0x180036a68  push    r12
0x180036a6a  push    r14
0x180036a6c  push    r15
0x180036a6e  sub     rsp, 0E8h
0x180036a75  mov     rax, cs:__security_cookie
0x180036a7c  xor     rax, rsp
0x180036a7f  mov     [rsp+118h+var_48], rax
0x180036a87  mov     r14, r9
0x180036a8a  mov     rax, r8
0x180036a8d  mov     r12, rdx
0x180036a90  mov     rbx, rcx
0x180036a93  mov     [rsp+118h+var_D8], rdx
0x180036a98  xorps   xmm0, xmm0
0x180036a9b  xor     ecx, ecx
0x180036a9d  movups  xmmword ptr [rsp+118h+var_D0], xmm0
0x180036aa2  mov     qword ptr [rsp+118h+var_D0+10h], rcx
0x180036aa7  xor     esi, esi
0x180036aa9  mov     [rsp+118h+hHash], rsi
0x180036aae  movups  xmmword ptr [rsp+118h+var_B8], xmm0
0x180036ab3  lea     r8, [rsp+118h+var_D0]; struct tagPROPVARIANT *
0x180036ab8  mov     rdx, rax; struct _tagpropertykey *
0x180036abb  mov     rcx, r12; this
0x180036abe  call    ?GetValue@CPropertyStore@@QEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; CPropertyStore::GetValue(_tagpropertykey const &,tagPROPVARIANT *)
0x180036ac3  mov     edi, eax
0x180036ac5  test    eax, eax
0x180036ac7  js      loc_180036C0F
0x180036acd  cmp     word ptr [rsp+118h+var_D0], 48h ; 'H'
0x180036ad3  jnz     loc_180036C0A
0x180036ad9  mov     rcx, qword ptr [rsp+118h+var_D0+8]; struct _GUID *
0x180036ade  test    rcx, rcx
0x180036ae1  jz      loc_180036C0A
0x180036ae7  lea     rdx, [rsp+118h+pbData]; unsigned __int16 *
0x180036aec  call    ?GuidToString@CDeviceMap@@SAJPEAU_GUID@@PEAGK@Z; CDeviceMap::GuidToString(_GUID *,ushort *,ulong)
0x180036af1  mov     edi, eax
0x180036af3  test    eax, eax
0x180036af5  js      loc_180036C0F
0x180036afb  lea     rax, [rsp+118h+hHash]
0x180036b00  mov     [rsp+118h+phHash], rax; phHash
0x180036b05  xor     r9d, r9d; dwFlags
0x180036b08  xor     r8d, r8d; hKey
0x180036b0b  mov     edx, 8003h; Algid
0x180036b10  mov     rcx, [rbx+60h]; hProv
0x180036b14  call    cs:__imp_CryptCreateHash
0x180036b1a  test    eax, eax
0x180036b1c  jnz     short loc_180036B3C
0x180036b1e  call    cs:__imp_GetLastError
0x180036b24  mov     edi, eax
0x180036b26  test    eax, eax
0x180036b28  jle     loc_180036C0F
0x180036b2e  movzx   edi, ax
0x180036b31  or      edi, 80070000h
0x180036b37  jmp     loc_180036C0F
0x180036b3c  lea     rax, [rsp+118h+pbData]
0x180036b41  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180036b45  mov     r8, rbx
0x180036b48  inc     r8
0x180036b4b  cmp     [rax+r8*2], si
0x180036b50  jnz     short loc_180036B48
0x180036b52  add     r8d, r8d; dwDataLen
0x180036b55  xor     r9d, r9d; dwFlags
0x180036b58  lea     rdx, [rsp+118h+pbData]; pbData
0x180036b5d  mov     rcx, [rsp+118h+hHash]; hHash
0x180036b62  call    cs:__imp_CryptHashData
0x180036b68  test    eax, eax
0x180036b6a  jz      short loc_180036B1E
0x180036b6c  mov     [rsp+118h+pdwDataLen], 10h
0x180036b74  mov     dword ptr [rsp+118h+phHash], esi; dwFlags
0x180036b78  lea     r9, [rsp+118h+pdwDataLen]; pdwDataLen
0x180036b7d  lea     r8, [rsp+118h+var_B8]; pbData
0x180036b82  mov     edx, 2; dwParam
0x180036b87  mov     rcx, [rsp+118h+hHash]; hHash
0x180036b8c  call    cs:__imp_CryptGetHashParam
0x180036b92  test    eax, eax
0x180036b94  jz      short loc_180036B1E
0x180036b96  lea     rdx, [rsp+118h+pbData]; unsigned __int16 *
0x180036b9b  lea     rcx, [rsp+118h+var_B8]; struct _GUID *
0x180036ba0  call    ?GuidToString@CDeviceMap@@SAJPEAU_GUID@@PEAGK@Z; CDeviceMap::GuidToString(_GUID *,ushort *,ulong)
0x180036ba5  mov     edi, eax
0x180036ba7  test    eax, eax
0x180036ba9  js      short loc_180036C0F
0x180036bab  lea     rax, [rsp+118h+pbData]
0x180036bb0  inc     rbx
0x180036bb3  cmp     [rax+rbx*2], si
0x180036bb7  jnz     short loc_180036BB0
0x180036bb9  cmp     rbx, [r14+18h]
0x180036bbd  ja      short loc_180036BEC
0x180036bbf  cmp     qword ptr [r14+18h], 7
0x180036bc4  jbe     short loc_180036BCB
0x180036bc6  mov     r15, [r14]
0x180036bc9  jmp     short loc_180036BCE
0x180036bcb  mov     r15, r14
0x180036bce  mov     [r14+10h], rbx
0x180036bd2  add     rbx, rbx
0x180036bd5  mov     r8, rbx; Size
0x180036bd8  lea     rdx, [rsp+118h+pbData]; Src
0x180036bdd  mov     rcx, r15; void *
0x180036be0  call    memmove_0
0x180036be5  mov     [rbx+r15], si
0x180036bea  jmp     short loc_180036BFD
0x180036bec  lea     r9, [rsp+118h+pbData]
0x180036bf1  mov     rdx, rbx
0x180036bf4  mov     rcx, r14
0x180036bf7  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180036bfc  nop
0x180036bfd  jmp     short loc_180036C0F
0x180036bff  mov     edi, [rsp+118h+var_DC]
0x180036c03  mov     r12, [rsp+118h+var_D8]
0x180036c08  jmp     short loc_180036C0F
0x180036c0a  mov     edi, 80070057h
0x180036c0f  mov     rcx, [rsp+118h+hHash]; hHash
0x180036c14  test    rcx, rcx
0x180036c17  jz      short loc_180036C1F
0x180036c19  call    cs:__imp_CryptDestroyHash
0x180036c1f  lea     rdx, [rsp+118h+var_D0]; struct tagPROPVARIANT *
0x180036c24  mov     rcx, r12; this
0x180036c27  call    ?ClearValue@CPropertyStore@@QEAAXPEAUtagPROPVARIANT@@@Z; CPropertyStore::ClearValue(tagPROPVARIANT *)
0x180036c2c  mov     eax, edi
0x180036c2e  mov     rcx, [rsp+118h+var_48]
0x180036c36  xor     rcx, rsp; StackCookie
0x180036c39  call    __security_check_cookie
0x180036c3e  add     rsp, 0E8h
0x180036c45  pop     r15
0x180036c47  pop     r14
0x180036c49  pop     r12
0x180036c4b  pop     rdi
0x180036c4c  pop     rsi
0x180036c4d  pop     rbx
0x180036c4e  retn
```
