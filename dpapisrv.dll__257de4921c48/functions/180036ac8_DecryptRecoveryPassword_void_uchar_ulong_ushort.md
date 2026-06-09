# DecryptRecoveryPassword(void *,uchar *,ulong,ushort * *)

- ea: `0x180036ac8`
- end: `0x180036db9`
- name: `?DecryptRecoveryPassword@@YAKPEAXPEAEKPEAPEAG@Z`
- size: `753`
- prototype: `__int64 __fastcall(void *, unsigned __int8 *, int, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180038d40`

## callees

- `0x1800029d0`
- `0x180007f10`
- `0x18001c9c0`
- `0x180036a18`
- `0x180036ac8`
- `0x1800382f4`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036d1f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036d88`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036d1f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180036d88`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180036c62`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180036c62`
- `bcrypt!BCryptDecrypt` at `0x180036cdf`
- `bcrypt!BCryptDecrypt` at `0x180036cdf`
- `bcrypt!BCryptDestroyKey` at `0x180036d9d`
- `bcrypt!BCryptDestroyKey` at `0x180036d9d`
- `bcrypt!BCryptImportKeyPair` at `0x180036c0a`
- `bcrypt!BCryptImportKeyPair` at `0x180036c0a`
- `ntdll!RtlNtStatusToDosError` at `0x180036c39`
- `ntdll!RtlNtStatusToDosError` at `0x180036d0e`
- `ntdll!RtlNtStatusToDosError` at `0x180036c39`
- `ntdll!RtlNtStatusToDosError` at `0x180036d0e`

## string_xrefs

- `0x180036c22`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\recovery.cpp`
- `0x180036cf7`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\recovery.cpp`
- `0x180036d56`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\recovery.cpp`

## pseudocode

```c
__int64 __fastcall DecryptRecoveryPassword(void *a1, unsigned __int8 *a2, int a3, unsigned __int8 **a4)
{
  ULONG SupplementalCredential; // eax
  _DWORD *v9; // rdi
  ULONG v10; // ebx
  __int64 v11; // r9
  __int64 v12; // rcx
  void *BCryptProviderHandle; // r10
  NTSTATUS v14; // eax
  NTSTATUS v15; // ebx
  unsigned __int8 *v16; // rax
  unsigned __int8 *v17; // rsi
  NTSTATUS v18; // eax
  NTSTATUS v19; // ebx
  __int64 v20; // rcx
  __int64 v21; // rcx
  _BYTE *v22; // rax
  size_t Size; // [rsp+50h] [rbp-28h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+58h] [rbp-20h] BYREF
  HLOCAL hMem[3]; // [rsp+60h] [rbp-18h] BYREF

  hMem[0] = 0;
  phKey = 0;
  Size = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 28, WPP_f5cee88f95423c4d1ee5d29d95c63987_Traceguids);
  SupplementalCredential = RecoveryRetrieveSupplementalCredential(a1, hMem, (char *)&Size + 4);
  v9 = hMem[0];
  v10 = SupplementalCredential;
  if ( SupplementalCredential )
  {
    v11 = 2045;
    v12 = SupplementalCredential;
LABEL_27:
    DebugTraceError(v12, "dwError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\recovery.cpp", v11);
    goto LABEL_28;
  }
  if ( !hMem[0] || HIDWORD(Size) < 0x10 )
  {
    v11 = 2058;
    goto LABEL_26;
  }
  if ( *(_DWORD *)hMem[0] != 1 )
  {
    v11 = 2065;
LABEL_26:
    v12 = 13;
    v10 = 13;
    goto LABEL_27;
  }
  if ( *((_DWORD *)hMem[0] + 1) > 0xFFFFu || *((_DWORD *)hMem[0] + 2) > 0xFFFFu || *((_DWORD *)hMem[0] + 3) > 0xFFFFu )
  {
    v11 = 2076;
    goto LABEL_26;
  }
  if ( HIDWORD(Size) < *((unsigned int *)hMem[0] + 1)
                     + 16LL
                     + *((unsigned int *)hMem[0] + 2)
                     + (unsigned __int64)*((unsigned int *)hMem[0] + 3) )
  {
    v11 = 2086;
    goto LABEL_26;
  }
  BCryptProviderHandle = (void *)GetBCryptProviderHandle(0xA400u);
  if ( !BCryptProviderHandle )
  {
    v11 = 2099;
    goto LABEL_26;
  }
  v14 = BCryptImportKeyPair(BCryptProviderHandle, 0, L"CAPIPRIVATEBLOB", &phKey, a2 + 8, a3 - 8, 0);
  v15 = v14;
  if ( v14 >= 0 )
  {
    LODWORD(Size) = HIDWORD(Size) - v9[2] - v9[1] - 16;
    v16 = (unsigned __int8 *)LocalAlloc(0x40u, (unsigned int)Size);
    v17 = v16;
    if ( v16 )
    {
      memcpy_0(v16, (char *)v9 + v9[2] + (unsigned int)v9[1] + 16, (unsigned int)Size);
      FMyReverseBytes(v17, Size);
      v18 = BCryptDecrypt(phKey, v17, Size, 0, 0, 0, v17, Size, (ULONG *)&Size, 2u);
      v19 = v18;
      if ( v18 >= 0 )
      {
        v20 = (unsigned int)Size & 0xFFFFFFFE;
        *a4 = v17;
        v10 = 0;
        *(_WORD *)&v17[v20] = 0;
      }
      else
      {
        DebugTraceError(
          (unsigned int)v18,
          "ntStatus",
          "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\recovery.cpp",
          2154);
        v10 = RtlNtStatusToDosError(v19);
        LocalFree(v17);
      }
    }
    else
    {
      v10 = 8;
    }
  }
  else
  {
    DebugTraceError(
      (unsigned int)v14,
      "ntStatus",
      "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\recovery.cpp",
      2112);
    v10 = RtlNtStatusToDosError(v15);
  }
LABEL_28:
  if ( v9 )
  {
    v21 = HIDWORD(Size);
    v22 = v9;
    if ( HIDWORD(Size) )
    {
      do
      {
        *v22++ = 0;
        --v21;
      }
      while ( v21 );
    }
    LocalFree(v9);
  }
  if ( phKey )
    BCryptDestroyKey(phKey);
  return v10;
}

```

## disassembly

```asm
0x180036ac8  push    rbp
0x180036aca  push    rbx
0x180036acb  push    rsi
0x180036acc  push    rdi
0x180036acd  push    r13
0x180036acf  push    r15
0x180036ad1  mov     rbp, rsp
0x180036ad4  sub     rsp, 78h
0x180036ad8  mov     r15, r9
0x180036adb  mov     [rbp+hMem], 0
0x180036ae3  mov     esi, r8d
0x180036ae6  mov     dword ptr [rbp+Size+4], 0
0x180036aed  mov     r13, rdx
0x180036af0  mov     [rbp+phKey], 0
0x180036af8  mov     rbx, rcx
0x180036afb  mov     dword ptr [rbp+Size], 0
0x180036b02  mov     rcx, cs:WPP_GLOBAL_Control
0x180036b09  lea     rax, WPP_GLOBAL_Control
0x180036b10  cmp     rcx, rax
0x180036b13  jz      short loc_180036B30
0x180036b15  test    byte ptr [rcx+1Ch], 8
0x180036b19  jz      short loc_180036B30
0x180036b1b  mov     rcx, [rcx+10h]
0x180036b1f  lea     r8, WPP_f5cee88f95423c4d1ee5d29d95c63987_Traceguids
0x180036b26  mov     edx, 1Ch
0x180036b2b  call    WPP_SF_
0x180036b30  lea     r8, [rbp+Size+4]
0x180036b34  mov     rcx, rbx
0x180036b37  lea     rdx, [rbp+hMem]
0x180036b3b  call    RecoveryRetrieveSupplementalCredential
0x180036b40  mov     rdi, [rbp+hMem]
0x180036b44  mov     ebx, eax
0x180036b46  test    eax, eax
0x180036b48  jz      short loc_180036B57
0x180036b4a  mov     r9d, 7FDh
0x180036b50  mov     ecx, eax
0x180036b52  jmp     loc_180036D56
0x180036b57  test    rdi, rdi
0x180036b5a  jz      loc_180036D49
0x180036b60  cmp     dword ptr [rbp+Size+4], 10h
0x180036b64  jb      loc_180036D49
0x180036b6a  cmp     dword ptr [rdi], 1
0x180036b6d  jz      short loc_180036B7A
0x180036b6f  mov     r9d, 811h
0x180036b75  jmp     loc_180036D4F
0x180036b7a  mov     eax, 0FFFFh
0x180036b7f  cmp     [rdi+4], eax
0x180036b82  ja      loc_180036D41
0x180036b88  cmp     [rdi+8], eax
0x180036b8b  ja      loc_180036D41
0x180036b91  cmp     [rdi+0Ch], eax
0x180036b94  ja      loc_180036D41
0x180036b9a  mov     eax, [rdi+8]
0x180036b9d  mov     ecx, [rdi+0Ch]
0x180036ba0  add     rcx, rax
0x180036ba3  mov     eax, [rdi+4]
0x180036ba6  add     rax, 10h
0x180036baa  add     rcx, rax
0x180036bad  mov     eax, dword ptr [rbp+Size+4]
0x180036bb0  cmp     rax, rcx
0x180036bb3  jnb     short loc_180036BC0
0x180036bb5  mov     r9d, 826h
0x180036bbb  jmp     loc_180036D4F
0x180036bc0  xor     r8d, r8d
0x180036bc3  xor     edx, edx
0x180036bc5  mov     ecx, 0A400h; unsigned int
0x180036bca  call    GetBCryptProviderHandle
0x180036bcf  mov     r10, rax
0x180036bd2  test    rax, rax
0x180036bd5  jnz     short loc_180036BE2
0x180036bd7  mov     r9d, 833h
0x180036bdd  jmp     loc_180036D4F
0x180036be2  lea     eax, [rsi-8]
0x180036be5  mov     [rsp+78h+dwFlags], 0; dwFlags
0x180036bed  lea     rcx, [r13+8]
0x180036bf1  mov     [rsp+78h+cbInput], eax; cbInput
0x180036bf5  mov     [rsp+78h+pbInput], rcx; pbInput
0x180036bfa  lea     r9, [rbp+phKey]; phKey
0x180036bfe  mov     rcx, r10; hAlgorithm
0x180036c01  lea     r8, pszBlobType; "CAPIPRIVATEBLOB"
0x180036c08  xor     edx, edx; hImportKey
0x180036c0a  call    cs:__imp_BCryptImportKeyPair
0x180036c11  nop     dword ptr [rax+rax+00h]
0x180036c16  mov     ebx, eax
0x180036c18  test    eax, eax
0x180036c1a  jns     short loc_180036C4C
0x180036c1c  mov     r9d, 840h
0x180036c22  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180036c29  lea     rdx, aNtstatus; "ntStatus"
0x180036c30  mov     ecx, eax
0x180036c32  call    DebugTraceError
0x180036c37  mov     ecx, ebx; Status
0x180036c39  call    cs:__imp_RtlNtStatusToDosError
0x180036c40  nop     dword ptr [rax+rax+00h]
0x180036c45  mov     ebx, eax
0x180036c47  jmp     loc_180036D69
0x180036c4c  mov     eax, dword ptr [rbp+Size+4]
0x180036c4f  mov     ecx, 40h ; '@'; uFlags
0x180036c54  sub     eax, [rdi+8]
0x180036c57  sub     eax, [rdi+4]
0x180036c5a  add     eax, 0FFFFFFF0h
0x180036c5d  mov     edx, eax; uBytes
0x180036c5f  mov     dword ptr [rbp+Size], eax
0x180036c62  call    cs:__imp_LocalAlloc
0x180036c69  nop     dword ptr [rax+rax+00h]
0x180036c6e  mov     rsi, rax
0x180036c71  test    rax, rax
0x180036c74  jnz     short loc_180036C7E
0x180036c76  lea     ebx, [rax+8]
0x180036c79  jmp     loc_180036D69
0x180036c7e  mov     edx, [rdi+8]
0x180036c81  mov     ecx, [rdi+4]
0x180036c84  add     rdx, rdi
0x180036c87  mov     r8d, dword ptr [rbp+Size]; Size
0x180036c8b  add     rcx, 10h
0x180036c8f  add     rdx, rcx; Src
0x180036c92  mov     rcx, rsi; void *
0x180036c95  call    memcpy_0
0x180036c9a  mov     edx, dword ptr [rbp+Size]; unsigned int
0x180036c9d  mov     rcx, rsi; unsigned __int8 *
0x180036ca0  call    ?FMyReverseBytes@@YAXPEAEK@Z; FMyReverseBytes(uchar *,ulong)
0x180036ca5  mov     r8d, dword ptr [rbp+Size]; cbInput
0x180036ca9  lea     rax, [rbp+Size]
0x180036cad  mov     rcx, [rbp+phKey]; hKey
0x180036cb1  xor     r9d, r9d; pPaddingInfo
0x180036cb4  mov     [rsp+78h+var_30], 2; dwFlags
0x180036cbc  mov     rdx, rsi; pbInput
0x180036cbf  mov     [rsp+78h+pcbResult], rax; pcbResult
0x180036cc4  mov     [rsp+78h+cbOutput], r8d; cbOutput
0x180036cc9  mov     qword ptr [rsp+78h+dwFlags], rsi; pbOutput
0x180036cce  mov     [rsp+78h+cbInput], 0; cbIV
0x180036cd6  mov     [rsp+78h+pbInput], 0; pbIV
0x180036cdf  call    cs:__imp_BCryptDecrypt
0x180036ce6  nop     dword ptr [rax+rax+00h]
0x180036ceb  mov     ebx, eax
0x180036ced  test    eax, eax
0x180036cef  jns     short loc_180036D2D
0x180036cf1  mov     r9d, 86Ah
0x180036cf7  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180036cfe  lea     rdx, aNtstatus; "ntStatus"
0x180036d05  mov     ecx, eax
0x180036d07  call    DebugTraceError
0x180036d0c  mov     ecx, ebx; Status
0x180036d0e  call    cs:__imp_RtlNtStatusToDosError
0x180036d15  nop     dword ptr [rax+rax+00h]
0x180036d1a  mov     rcx, rsi; hMem
0x180036d1d  mov     ebx, eax
0x180036d1f  call    cs:__imp_LocalFree
0x180036d26  nop     dword ptr [rax+rax+00h]
0x180036d2b  jmp     short loc_180036D69
0x180036d2d  mov     ecx, dword ptr [rbp+Size]
0x180036d30  xor     eax, eax
0x180036d32  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180036d36  mov     [r15], rsi
0x180036d39  xor     ebx, ebx
0x180036d3b  mov     [rcx+rsi], ax
0x180036d3f  jmp     short loc_180036D69
0x180036d41  mov     r9d, 81Ch
0x180036d47  jmp     short loc_180036D4F
0x180036d49  mov     r9d, 80Ah
0x180036d4f  mov     ecx, 0Dh
0x180036d54  mov     ebx, ecx
0x180036d56  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180036d5d  lea     rdx, aDwerror; "dwError"
0x180036d64  call    DebugTraceError
0x180036d69  test    rdi, rdi
0x180036d6c  jz      short loc_180036D94
0x180036d6e  mov     ecx, dword ptr [rbp+Size+4]
0x180036d71  mov     rax, rdi
0x180036d74  test    rcx, rcx
0x180036d77  jz      short loc_180036D85
0x180036d79  mov     byte ptr [rax], 0
0x180036d7c  inc     rax
0x180036d7f  sub     rcx, 1
0x180036d83  jnz     short loc_180036D79
0x180036d85  mov     rcx, rdi; hMem
0x180036d88  call    cs:__imp_LocalFree
0x180036d8f  nop     dword ptr [rax+rax+00h]
0x180036d94  mov     rcx, [rbp+phKey]; hKey
0x180036d98  test    rcx, rcx
0x180036d9b  jz      short loc_180036DA9
0x180036d9d  call    cs:__imp_BCryptDestroyKey
0x180036da4  nop     dword ptr [rax+rax+00h]
0x180036da9  mov     eax, ebx
0x180036dab  add     rsp, 78h
0x180036daf  pop     r15
0x180036db1  pop     r13
0x180036db3  pop     rdi
0x180036db4  pop     rsi
0x180036db5  pop     rbx
0x180036db6  pop     rbp
0x180036db7  retn
```
