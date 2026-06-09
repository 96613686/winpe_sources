# UDCreateDigest(uint,uint,uchar *,uint *,uchar *)

- ea: `0x18004be30`
- end: `0x18004bfac`
- name: `?UDCreateDigest@@YAJIIPEAEPEAI0@Z`
- size: `380`
- prototype: `int(unsigned int, unsigned int, unsigned __int8 *, unsigned int *, unsigned __int8 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000fee4`
- `0x18001dc2c`
- `0x18003d3d0`
- `0x18004c2bc`

## callees

- `0x18004be30`
- `0x18004c854`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bf54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bf54`
- `CRYPTSP!CryptDestroyHash` at `0x18004bf8b`
- `CRYPTSP!CryptDestroyHash` at `0x18004bf8b`
- `CRYPTSP!CryptGetHashParam` at `0x18004beff`
- `CRYPTSP!CryptGetHashParam` at `0x18004bf4a`
- `CRYPTSP!CryptGetHashParam` at `0x18004beff`
- `CRYPTSP!CryptGetHashParam` at `0x18004bf4a`
- `CRYPTSP!CryptHashData` at `0x18004bf28`
- `CRYPTSP!CryptHashData` at `0x18004bf28`
- `CRYPTSP!CryptCreateHash` at `0x18004bed7`
- `CRYPTSP!CryptCreateHash` at `0x18004bed7`

## pseudocode

```c
__int64 __fastcall UDCreateDigest(int a1, DWORD a2, unsigned __int8 *a3, BYTE *a4, unsigned __int8 *pbData)
{
  BYTE *v5; // rsi
  unsigned int v9; // ebp
  ALG_ID v10; // r14d
  signed int Context; // ebx
  signed int LastError; // eax
  HCRYPTHASH hHash; // [rsp+30h] [rbp-38h] BYREF
  HCRYPTPROV hProv; // [rsp+38h] [rbp-30h] BYREF
  DWORD pdwDataLen; // [rsp+78h] [rbp+10h] BYREF

  v5 = pbData;
  hProv = 0;
  hHash = 0;
  if ( pbData )
    v9 = *(_DWORD *)a4;
  else
    v9 = 0;
  if ( a2 && a3 && a4 )
  {
    if ( a1 == 4 )
    {
      v10 = 32772;
    }
    else
    {
      if ( a1 != 12 )
        return (unsigned int)-2146893816;
      v10 = 32780;
    }
    Context = UDCAPI_GetContext(&hProv);
    if ( Context >= 0 )
    {
      if ( !CryptCreateHash(hProv, v10, 0, 0, &hHash) )
        goto LABEL_18;
      pdwDataLen = 4;
      if ( !CryptGetHashParam(hHash, 4u, a4, &pdwDataLen, 0) )
        goto LABEL_18;
      if ( *(_DWORD *)a4 > v9 )
      {
        Context = v5 != 0 ? 0x8007007A : 0;
        goto LABEL_25;
      }
      if ( !CryptHashData(hHash, a3, a2, 0) || !CryptGetHashParam(hHash, 2u, v5, (DWORD *)a4, 0) )
      {
LABEL_18:
        LastError = GetLastError();
        Context = LastError;
        if ( LastError > 0 )
          Context = (unsigned __int16)LastError | 0x80070000;
        if ( Context >= 0 )
          Context = -2147467259;
      }
    }
  }
  else
  {
    Context = -2147024809;
  }
LABEL_25:
  if ( hHash )
    CryptDestroyHash(hHash);
  return (unsigned int)Context;
}

```

## disassembly

```asm
0x18004be30  mov     rax, rsp
0x18004be33  mov     [rax+8], rbx
0x18004be37  mov     [rax+18h], rbp
0x18004be3b  push    rsi
0x18004be3c  push    rdi
0x18004be3d  push    r12
0x18004be3f  push    r14
0x18004be41  push    r15
0x18004be43  sub     rsp, 40h
0x18004be47  mov     rsi, [rsp+68h+pbData]
0x18004be4f  mov     rdi, r9
0x18004be52  mov     qword ptr [rax-30h], 0
0x18004be5a  mov     r15, r8
0x18004be5d  mov     qword ptr [rax-38h], 0
0x18004be65  mov     r12d, edx
0x18004be68  test    rsi, rsi
0x18004be6b  jz      short loc_18004BE72
0x18004be6d  mov     ebp, [r9]
0x18004be70  jmp     short loc_18004BE74
0x18004be72  xor     ebp, ebp
0x18004be74  test    r12d, r12d
0x18004be77  jz      loc_18004BF7C
0x18004be7d  test    r15, r15
0x18004be80  jz      loc_18004BF7C
0x18004be86  test    rdi, rdi
0x18004be89  jz      loc_18004BF7C
0x18004be8f  cmp     ecx, 4
0x18004be92  jnz     short loc_18004BE9C
0x18004be94  mov     r14d, 8004h
0x18004be9a  jmp     short loc_18004BEAB
0x18004be9c  cmp     ecx, 0Ch
0x18004be9f  jnz     loc_18004BF75
0x18004bea5  mov     r14d, 800Ch
0x18004beab  lea     rcx, [rsp+68h+hProv]; unsigned __int64 *
0x18004beb0  call    ?UDCAPI_GetContext@@YAJPEA_K@Z; UDCAPI_GetContext(unsigned __int64 *)
0x18004beb5  mov     ebx, eax
0x18004beb7  test    eax, eax
0x18004beb9  js      loc_18004BF81
0x18004bebf  mov     rcx, [rsp+68h+hProv]; hProv
0x18004bec4  lea     rax, [rsp+68h+hHash]
0x18004bec9  xor     r9d, r9d; dwFlags
0x18004becc  mov     [rsp+68h+phHash], rax; phHash
0x18004bed1  xor     r8d, r8d; hKey
0x18004bed4  mov     edx, r14d; Algid
0x18004bed7  call    cs:__imp_CryptCreateHash
0x18004bedd  test    eax, eax
0x18004bedf  jz      short loc_18004BF54
0x18004bee1  mov     rcx, [rsp+68h+hHash]; hHash
0x18004bee6  lea     r9, [rsp+68h+pdwDataLen]; pdwDataLen
0x18004beeb  mov     edx, 4; dwParam
0x18004bef0  mov     dword ptr [rsp+68h+phHash], 0; dwFlags
0x18004bef8  mov     r8, rdi; pbData
0x18004befb  mov     [rsp+68h+pdwDataLen], edx
0x18004beff  call    cs:__imp_CryptGetHashParam
0x18004bf05  test    eax, eax
0x18004bf07  jz      short loc_18004BF54
0x18004bf09  cmp     [rdi], ebp
0x18004bf0b  jbe     short loc_18004BF1A
0x18004bf0d  neg     rsi
0x18004bf10  sbb     ebx, ebx
0x18004bf12  and     ebx, 8007007Ah
0x18004bf18  jmp     short loc_18004BF81
0x18004bf1a  mov     rcx, [rsp+68h+hHash]; hHash
0x18004bf1f  xor     r9d, r9d; dwFlags
0x18004bf22  mov     r8d, r12d; dwDataLen
0x18004bf25  mov     rdx, r15; pbData
0x18004bf28  call    cs:__imp_CryptHashData
0x18004bf2e  test    eax, eax
0x18004bf30  jz      short loc_18004BF54
0x18004bf32  mov     rcx, [rsp+68h+hHash]; hHash
0x18004bf37  mov     r9, rdi; pdwDataLen
0x18004bf3a  mov     r8, rsi; pbData
0x18004bf3d  mov     dword ptr [rsp+68h+phHash], 0; dwFlags
0x18004bf45  mov     edx, 2; dwParam
0x18004bf4a  call    cs:__imp_CryptGetHashParam
0x18004bf50  test    eax, eax
0x18004bf52  jnz     short loc_18004BF81
0x18004bf54  call    cs:__imp_GetLastError
0x18004bf5a  mov     ebx, eax
0x18004bf5c  test    eax, eax
0x18004bf5e  jle     short loc_18004BF69
0x18004bf60  movzx   ebx, ax
0x18004bf63  or      ebx, 80070000h
0x18004bf69  test    ebx, ebx
0x18004bf6b  mov     eax, 80004005h
0x18004bf70  cmovns  ebx, eax
0x18004bf73  jmp     short loc_18004BF81
0x18004bf75  mov     ebx, 80090008h
0x18004bf7a  jmp     short loc_18004BF91
0x18004bf7c  mov     ebx, 80070057h
0x18004bf81  mov     rcx, [rsp+68h+hHash]; hHash
0x18004bf86  test    rcx, rcx
0x18004bf89  jz      short loc_18004BF91
0x18004bf8b  call    cs:__imp_CryptDestroyHash
0x18004bf91  lea     r11, [rsp+68h+var_28]
0x18004bf96  mov     eax, ebx
0x18004bf98  mov     rbx, [r11+30h]
0x18004bf9c  mov     rbp, [r11+40h]
0x18004bfa0  mov     rsp, r11
0x18004bfa3  pop     r15
0x18004bfa5  pop     r14
0x18004bfa7  pop     r12
0x18004bfa9  pop     rdi
0x18004bfaa  pop     rsi
0x18004bfab  retn
```
