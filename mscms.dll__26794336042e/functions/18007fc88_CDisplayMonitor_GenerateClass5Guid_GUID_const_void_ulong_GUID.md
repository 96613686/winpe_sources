# CDisplayMonitor::GenerateClass5Guid(_GUID const *,void *,ulong,_GUID *)

- ea: `0x18007fc88`
- end: `0x18007fe8e`
- name: `?GenerateClass5Guid@CDisplayMonitor@@CAJPEBU_GUID@@PEAXKPEAU2@@Z`
- size: `518`
- prototype: `static int(const struct _GUID *, void *, unsigned int, struct _GUID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18002d518`

## callees

- `0x18002e5f0`
- `0x18002e614`
- `0x18002eab4`
- `0x18007fc88`

## import_xrefs

- `bcrypt!BCryptHashData` at `0x18007fdb2`
- `bcrypt!BCryptHashData` at `0x18007fdcb`
- `bcrypt!BCryptHashData` at `0x18007fdb2`
- `bcrypt!BCryptHashData` at `0x18007fdcb`
- `bcrypt!BCryptCreateHash` at `0x18007fd79`
- `bcrypt!BCryptCreateHash` at `0x18007fd79`
- `bcrypt!BCryptDestroyHash` at `0x18007fe35`
- `bcrypt!BCryptDestroyHash` at `0x18007fe35`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18007fe46`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18007fe46`
- `bcrypt!BCryptFinishHash` at `0x18007fde6`
- `bcrypt!BCryptFinishHash` at `0x18007fde6`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18007fd06`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18007fd06`
- `bcrypt!BCryptGetProperty` at `0x18007fd36`
- `bcrypt!BCryptGetProperty` at `0x18007fd36`

## pseudocode

```c
__int64 __fastcall CDisplayMonitor::GenerateClass5Guid(const struct _GUID *a1, UCHAR *a2, ULONG a3, struct _GUID *a4)
{
  UCHAR *v7; // rsi
  NTSTATUS Property; // ebx
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-29h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-21h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-19h] BYREF
  ULONG pcbResult; // [rsp+58h] [rbp-11h] BYREF
  UCHAR pbInput[16]; // [rsp+60h] [rbp-9h] BYREF
  UCHAR v15[16]; // [rsp+70h] [rbp+7h] BYREF

  *(_OWORD *)pbInput = 0;
  pcbResult = 0;
  *(_DWORD *)pbOutput = 0;
  phAlgorithm = 0;
  phHash = 0;
  if ( !a4 || !a2 && a3 )
    return 2147942487LL;
  v7 = 0;
  Property = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
  if ( Property >= 0 )
  {
    Property = BCryptGetProperty(phAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
    if ( Property >= 0 )
    {
      v7 = (UCHAR *)operator new[](*(unsigned int *)pbOutput);
      Property = BCryptCreateHash(phAlgorithm, &phHash, v7, *(ULONG *)pbOutput, 0, 0, 0);
      if ( Property >= 0 )
      {
        *(_QWORD *)&pbInput[8] = *(_QWORD *)GUID_ICC_FILENAME_GENERATOR.Data4;
        *(_DWORD *)pbInput = -419139547;
        *(_DWORD *)&pbInput[4] = -196711627;
        Property = BCryptHashData(phHash, pbInput, 0x10u, 0);
        if ( Property >= 0 )
        {
          Property = BCryptHashData(phHash, a2, a3, 0);
          if ( Property >= 0 )
          {
            Property = BCryptFinishHash(phHash, v15, 0x20u, 0);
            if ( Property >= 0 )
            {
              *a4 = *(struct _GUID *)v15;
              a4->Data1 = _byteswap_ulong(a4->Data1);
              a4->Data2 = __ROR2__(a4->Data2, 8);
              a4->Data3 = __ROR2__(a4->Data3, 8) & 0xFFF | 0x5000;
              a4->Data4[0] &= 0x3Fu;
              a4->Data4[0] |= 0x80u;
            }
          }
        }
      }
    }
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  if ( v7 )
    operator delete(v7);
  return (Property >> 31) & 0x80004005;
}

```

## disassembly

```asm
0x18007fc88  mov     [rsp-8+arg_0], rbx
0x18007fc8d  push    rbp
0x18007fc8e  push    rsi
0x18007fc8f  push    rdi
0x18007fc90  push    r14
0x18007fc92  push    r15
0x18007fc94  lea     rbp, [rsp-37h]
0x18007fc99  sub     rsp, 0A0h
0x18007fca0  mov     rax, cs:__security_cookie
0x18007fca7  xor     rax, rsp
0x18007fcaa  mov     [rbp+57h+var_30], rax
0x18007fcae  mov     rdi, r9
0x18007fcb1  mov     r15d, r8d
0x18007fcb4  mov     r14, rdx
0x18007fcb7  xorps   xmm0, xmm0
0x18007fcba  movups  xmmword ptr [rbp+57h+pbInput], xmm0
0x18007fcbe  mov     [rbp+57h+var_68], 0
0x18007fcc5  mov     dword ptr [rbp+57h+pbOutput], 0
0x18007fccc  mov     [rbp+57h+phAlgorithm], 0
0x18007fcd4  mov     [rbp+57h+phHash], 0
0x18007fcdc  test    r9, r9
0x18007fcdf  jz      loc_18007FE66
0x18007fce5  test    rdx, rdx
0x18007fce8  jnz     short loc_18007FCF3
0x18007fcea  test    r8d, r8d
0x18007fced  jnz     loc_18007FE66
0x18007fcf3  xor     esi, esi
0x18007fcf5  xor     r9d, r9d; dwFlags
0x18007fcf8  xor     r8d, r8d; pszImplementation
0x18007fcfb  lea     rdx, pszAlgId; "SHA256"
0x18007fd02  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x18007fd06  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18007fd0c  mov     ebx, eax
0x18007fd0e  test    eax, eax
0x18007fd10  js      loc_18007FE2C
0x18007fd16  mov     [rsp+0C0h+dwFlags], esi; dwFlags
0x18007fd1a  lea     rax, [rbp+57h+var_68]
0x18007fd1e  mov     [rsp+0C0h+pcbResult], rax; pcbResult
0x18007fd23  lea     r9d, [rsi+4]; cbOutput
0x18007fd27  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x18007fd2b  lea     rdx, pszProperty; "ObjectLength"
0x18007fd32  mov     rcx, [rbp+57h+phAlgorithm]; hObject
0x18007fd36  call    cs:__imp_BCryptGetProperty
0x18007fd3c  mov     ebx, eax
0x18007fd3e  test    eax, eax
0x18007fd40  js      loc_18007FE2C
0x18007fd46  mov     ecx, dword ptr [rbp+57h+pbOutput]; unsigned __int64
0x18007fd49  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18007fd4e  mov     rsi, rax
0x18007fd51  mov     [rsp+0C0h+var_90], 0; dwFlags
0x18007fd59  mov     [rsp+0C0h+dwFlags], 0; cbSecret
0x18007fd61  mov     [rsp+0C0h+pcbResult], 0; pbSecret
0x18007fd6a  mov     r9d, dword ptr [rbp+57h+pbOutput]; cbHashObject
0x18007fd6e  mov     r8, rax; pbHashObject
0x18007fd71  lea     rdx, [rbp+57h+phHash]; phHash
0x18007fd75  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x18007fd79  call    cs:__imp_BCryptCreateHash
0x18007fd7f  mov     ebx, eax
0x18007fd81  test    eax, eax
0x18007fd83  js      loc_18007FE2C
0x18007fd89  movups  xmm0, xmmword ptr cs:GUID_ICC_FILENAME_GENERATOR.Data1
0x18007fd90  movdqu  xmmword ptr [rbp+57h+pbInput], xmm0
0x18007fd95  mov     dword ptr [rbp+57h+pbInput], 0E7047025h
0x18007fd9c  mov     dword ptr [rbp+57h+pbInput+4], 0F4466B35h
0x18007fda3  xor     r9d, r9d; dwFlags
0x18007fda6  lea     r8d, [r9+10h]; cbInput
0x18007fdaa  lea     rdx, [rbp+57h+pbInput]; pbInput
0x18007fdae  mov     rcx, [rbp+57h+phHash]; hHash
0x18007fdb2  call    cs:__imp_BCryptHashData
0x18007fdb8  mov     ebx, eax
0x18007fdba  test    eax, eax
0x18007fdbc  js      short loc_18007FE2C
0x18007fdbe  xor     r9d, r9d; dwFlags
0x18007fdc1  mov     r8d, r15d; cbInput
0x18007fdc4  mov     rdx, r14; pbInput
0x18007fdc7  mov     rcx, [rbp+57h+phHash]; hHash
0x18007fdcb  call    cs:__imp_BCryptHashData
0x18007fdd1  mov     ebx, eax
0x18007fdd3  test    eax, eax
0x18007fdd5  js      short loc_18007FE2C
0x18007fdd7  xor     r9d, r9d; dwFlags
0x18007fdda  lea     r8d, [r9+20h]; cbOutput
0x18007fdde  lea     rdx, [rbp+57h+var_50]; pbOutput
0x18007fde2  mov     rcx, [rbp+57h+phHash]; hHash
0x18007fde6  call    cs:__imp_BCryptFinishHash
0x18007fdec  mov     ebx, eax
0x18007fdee  test    eax, eax
0x18007fdf0  js      short loc_18007FE2C
0x18007fdf2  movups  xmm0, xmmword ptr [rbp+57h+var_50]
0x18007fdf6  movdqu  xmmword ptr [rdi], xmm0
0x18007fdfa  mov     eax, [rdi]
0x18007fdfc  bswap   eax
0x18007fdfe  mov     [rdi], eax
0x18007fe00  movzx   eax, word ptr [rdi+4]
0x18007fe04  ror     ax, 8
0x18007fe08  mov     [rdi+4], ax
0x18007fe0c  movzx   eax, word ptr [rdi+6]
0x18007fe10  ror     ax, 8
0x18007fe14  mov     ecx, 0FFFh
0x18007fe19  and     ax, cx
0x18007fe1c  or      ax, 5000h
0x18007fe20  mov     [rdi+6], ax
0x18007fe24  and     byte ptr [rdi+8], 3Fh
0x18007fe28  or      byte ptr [rdi+8], 80h
0x18007fe2c  mov     rcx, [rbp+57h+phHash]; hHash
0x18007fe30  test    rcx, rcx
0x18007fe33  jz      short loc_18007FE3B
0x18007fe35  call    cs:__imp_BCryptDestroyHash
0x18007fe3b  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x18007fe3f  test    rcx, rcx
0x18007fe42  jz      short loc_18007FE4C
0x18007fe44  xor     edx, edx; dwFlags
0x18007fe46  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18007fe4c  test    rsi, rsi
0x18007fe4f  jz      short loc_18007FE59
0x18007fe51  mov     rcx, rsi; void *
0x18007fe54  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18007fe59  sar     ebx, 1Fh
0x18007fe5c  and     ebx, 80004005h
0x18007fe62  mov     eax, ebx
0x18007fe64  jmp     short loc_18007FE6B
0x18007fe66  mov     eax, 80070057h
0x18007fe6b  mov     rcx, [rbp+57h+var_30]
0x18007fe6f  xor     rcx, rsp; StackCookie
0x18007fe72  call    __security_check_cookie
0x18007fe77  mov     rbx, [rsp+0C0h+arg_0]
0x18007fe7f  add     rsp, 0A0h
0x18007fe86  pop     r15
0x18007fe88  pop     r14
0x18007fe8a  pop     rdi
0x18007fe8b  pop     rsi
0x18007fe8c  pop     rbp
0x18007fe8d  retn
```
