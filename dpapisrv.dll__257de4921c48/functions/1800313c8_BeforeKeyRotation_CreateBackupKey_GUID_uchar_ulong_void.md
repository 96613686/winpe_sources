# BeforeKeyRotation::CreateBackupKey(_GUID *,uchar * *,ulong *,void * *)

- ea: `0x1800313c8`
- end: `0x18003166d`
- name: `?CreateBackupKey@BeforeKeyRotation@@YAHPEAU_GUID@@PEAPEAEPEAKPEAPEAX@Z`
- size: `677`
- prototype: `__int64 __fastcall(BeforeKeyRotation *this, struct _GUID *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800354c8`

## callees

- `0x1800029d0`
- `0x180007f10`
- `0x1800313c8`
- `0x180031984`
- `0x180034ff8`
- `0x18003c62c`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180031408`
- `RPCRT4!UuidCreate` at `0x180031408`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031421`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031493`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031421`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031493`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031655`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031655`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031556`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031556`
- `bcrypt!BCryptDestroyKey` at `0x180031640`
- `bcrypt!BCryptDestroyKey` at `0x180031640`
- `bcrypt!BCryptFinalizeKeyPair` at `0x1800314aa`
- `bcrypt!BCryptFinalizeKeyPair` at `0x1800314aa`
- `bcrypt!BCryptGenerateKeyPair` at `0x180031464`
- `bcrypt!BCryptGenerateKeyPair` at `0x180031464`
- `bcrypt!BCryptExportKey` at `0x1800314e5`
- `bcrypt!BCryptExportKey` at `0x1800315bb`
- `bcrypt!BCryptExportKey` at `0x1800314e5`
- `bcrypt!BCryptExportKey` at `0x1800315bb`

## string_xrefs

- `0x18003147c`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x180031524`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x1800315d3`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`

## pseudocode

```c
__int64 __fastcall BeforeKeyRotation::CreateBackupKey(
        BeforeKeyRotation *this,
        struct _GUID *a2,
        unsigned __int8 **a3,
        unsigned int *a4)
{
  RPC_STATUS v4; // eax
  unsigned int v6; // esi
  void *BCryptProviderHandle; // rax
  NTSTATUS v8; // ebx
  __int64 v9; // r9
  DWORD v10; // ecx
  size_t v11; // rbx
  _DWORD *v12; // rax
  NTSTATUS v13; // eax
  NTSTATUS v14; // edi
  void *Src; // [rsp+70h] [rbp+28h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+78h] [rbp+30h] BYREF
  size_t Size; // [rsp+80h] [rbp+38h] BYREF
  unsigned int *pcbResult; // [rsp+88h] [rbp+40h] BYREF

  pcbResult = a4;
  Size = (size_t)a3;
  phKey = 0;
  Src = 0;
  BeforeKeyRotation::g_pbPreferredKey = 0;
  v4 = UuidCreate(&BeforeKeyRotation::g_guidPreferredKey);
  if ( v4 && v4 != 1824 )
  {
    SetLastError(v4);
    return 0;
  }
  v6 = 0;
  LODWORD(pcbResult) = 0;
  LODWORD(Size) = 0;
  BCryptProviderHandle = (void *)GetBCryptProviderHandle(0xA400u);
  if ( BCryptProviderHandle )
  {
    v8 = BCryptGenerateKeyPair(BCryptProviderHandle, &phKey, 0x800u, 0);
    if ( v8 >= 0 )
    {
      v8 = BCryptFinalizeKeyPair(phKey, 0);
      if ( v8 >= 0 )
      {
        v8 = BCryptExportKey(phKey, 0, L"CAPIPRIVATEBLOB", 0, 0, (ULONG *)&pcbResult, 0);
        if ( v8 >= 0 )
        {
          if ( !(unsigned int)GeneratePublicKeyCert(
                                phKey,
                                &BeforeKeyRotation::g_guidPreferredKey,
                                (unsigned int *)&Size,
                                (unsigned __int8 **)&Src) )
          {
            DebugTraceError(
              2147500037LL,
              "E_FAIL",
              "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp",
              4698);
            goto LABEL_19;
          }
          v11 = (unsigned int)Size;
          LODWORD(BeforeKeyRotation::g_cbPreferredKey) = Size + (_DWORD)pcbResult + 12;
          v12 = LocalAlloc(0, (unsigned int)(Size + (_DWORD)pcbResult + 12));
          BeforeKeyRotation::g_pbPreferredKey = v12;
          if ( !v12 )
            goto LABEL_19;
          *v12 = 2;
          *((_DWORD *)BeforeKeyRotation::g_pbPreferredKey + 1) = (_DWORD)pcbResult;
          *((_DWORD *)BeforeKeyRotation::g_pbPreferredKey + 2) = v11;
          v13 = BCryptExportKey(
                  phKey,
                  0,
                  L"CAPIPRIVATEBLOB",
                  (PUCHAR)BeforeKeyRotation::g_pbPreferredKey + 12,
                  (ULONG)pcbResult,
                  (ULONG *)&pcbResult,
                  0);
          v14 = v13;
          if ( v13 >= 0 )
          {
            memcpy_0((char *)BeforeKeyRotation::g_pbPreferredKey + (unsigned int)pcbResult + 12, Src, v11);
            *(_QWORD *)&BeforeKeyRotation::g_hKeyPreferredKey = phKey;
            phKey = 0;
            v6 = SaveBackupKey(
                   &BeforeKeyRotation::g_guidPreferredKey,
                   (unsigned __int8 *)BeforeKeyRotation::g_pbPreferredKey,
                   (unsigned int)BeforeKeyRotation::g_cbPreferredKey);
            goto LABEL_19;
          }
          DebugTraceError(
            (unsigned int)v13,
            "ntStatus",
            "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp",
            4726);
          v10 = v14;
          goto LABEL_8;
        }
        v9 = 4688;
      }
      else
      {
        v9 = 4671;
      }
    }
    else
    {
      v9 = 4662;
    }
    DebugTraceError((unsigned int)v8, "ntStatus", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", v9);
    v10 = v8;
LABEL_8:
    SetLastError(v10);
  }
LABEL_19:
  if ( phKey )
    BCryptDestroyKey(phKey);
  if ( Src )
    LocalFree(Src);
  return v6;
}

```

## disassembly

```asm
0x1800313c8  mov     rax, rsp
0x1800313cb  mov     [rax+20h], r9
0x1800313cf  mov     [rax+18h], r8
0x1800313d3  mov     [rax+10h], rdx
0x1800313d7  mov     [rax+8], rcx
0x1800313db  push    rbp
0x1800313dc  push    rbx
0x1800313dd  push    rsi
0x1800313de  push    rdi
0x1800313df  mov     rbp, rsp
0x1800313e2  sub     rsp, 48h
0x1800313e6  lea     rcx, ?g_guidPreferredKey@BeforeKeyRotation@@3U_GUID@@A; Uuid
0x1800313ed  mov     [rbp+phKey], 0
0x1800313f5  mov     [rbp+Src], 0
0x1800313fd  mov     cs:?g_pbPreferredKey@BeforeKeyRotation@@3PEAEEA, 0; uchar * BeforeKeyRotation::g_pbPreferredKey
0x180031408  call    cs:__imp_UuidCreate
0x18003140f  nop     dword ptr [rax+rax+00h]
0x180031414  test    eax, eax
0x180031416  jz      short loc_180031434
0x180031418  cmp     eax, 720h
0x18003141d  jz      short loc_180031434
0x18003141f  mov     ecx, eax; dwErrCode
0x180031421  call    cs:__imp_SetLastError
0x180031428  nop     dword ptr [rax+rax+00h]
0x18003142d  xor     eax, eax
0x18003142f  jmp     loc_180031663
0x180031434  xor     esi, esi
0x180031436  xor     r8d, r8d
0x180031439  xor     edx, edx
0x18003143b  mov     dword ptr [rbp+arg_18], esi
0x18003143e  mov     ecx, 0A400h; unsigned int
0x180031443  mov     dword ptr [rbp+Size], esi
0x180031446  call    GetBCryptProviderHandle
0x18003144b  test    rax, rax
0x18003144e  jz      loc_180031637
0x180031454  xor     r9d, r9d; dwFlags
0x180031457  lea     rdx, [rbp+phKey]; phKey
0x18003145b  mov     r8d, 800h; dwLength
0x180031461  mov     rcx, rax; hAlgorithm
0x180031464  call    cs:__imp_BCryptGenerateKeyPair
0x18003146b  nop     dword ptr [rax+rax+00h]
0x180031470  mov     ebx, eax
0x180031472  test    eax, eax
0x180031474  jns     short loc_1800314A4
0x180031476  mov     r9d, 1236h
0x18003147c  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180031483  mov     ecx, ebx
0x180031485  lea     rdx, aNtstatus; "ntStatus"
0x18003148c  call    DebugTraceError
0x180031491  mov     ecx, ebx; dwErrCode
0x180031493  call    cs:__imp_SetLastError
0x18003149a  nop     dword ptr [rax+rax+00h]
0x18003149f  jmp     loc_180031637
0x1800314a4  mov     rcx, [rbp+phKey]; hKey
0x1800314a8  xor     edx, edx; dwFlags
0x1800314aa  call    cs:__imp_BCryptFinalizeKeyPair
0x1800314b1  nop     dword ptr [rax+rax+00h]
0x1800314b6  mov     ebx, eax
0x1800314b8  test    eax, eax
0x1800314ba  jns     short loc_1800314C4
0x1800314bc  mov     r9d, 123Fh
0x1800314c2  jmp     short loc_18003147C
0x1800314c4  mov     rcx, [rbp+phKey]; hKey
0x1800314c8  lea     rax, [rbp+arg_18]
0x1800314cc  mov     [rsp+48h+dwFlags], esi; dwFlags
0x1800314d0  lea     r8, pszBlobType; "CAPIPRIVATEBLOB"
0x1800314d7  mov     [rsp+48h+pcbResult], rax; pcbResult
0x1800314dc  xor     r9d, r9d; pbOutput
0x1800314df  xor     edx, edx; hExportKey
0x1800314e1  mov     [rsp+48h+cbOutput], esi; cbOutput
0x1800314e5  call    cs:__imp_BCryptExportKey
0x1800314ec  nop     dword ptr [rax+rax+00h]
0x1800314f1  mov     ebx, eax
0x1800314f3  test    eax, eax
0x1800314f5  jns     short loc_180031502
0x1800314f7  mov     r9d, 1250h
0x1800314fd  jmp     loc_18003147C
0x180031502  mov     rcx, [rbp+phKey]; hKey
0x180031506  lea     r9, [rbp+Src]; unsigned __int8 **
0x18003150a  lea     r8, [rbp+Size]; unsigned int *
0x18003150e  lea     rdx, ?g_guidPreferredKey@BeforeKeyRotation@@3U_GUID@@A; struct _GUID *
0x180031515  call    ?GeneratePublicKeyCert@@YAHPEAXPEAU_GUID@@PEAKPEAPEAE@Z; GeneratePublicKeyCert(void *,_GUID *,ulong *,uchar * *)
0x18003151a  test    eax, eax
0x18003151c  jnz     short loc_180031541
0x18003151e  mov     r9d, 125Ah
0x180031524  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18003152b  lea     rdx, aEFail; "E_FAIL"
0x180031532  mov     ecx, 80004005h
0x180031537  call    DebugTraceError
0x18003153c  jmp     loc_180031637
0x180031541  mov     ecx, dword ptr [rbp+arg_18]
0x180031544  mov     ebx, dword ptr [rbp+Size]
0x180031547  add     ecx, 0Ch
0x18003154a  add     ecx, ebx
0x18003154c  mov     cs:?g_cbPreferredKey@BeforeKeyRotation@@3KA, ecx; ulong BeforeKeyRotation::g_cbPreferredKey
0x180031552  mov     edx, ecx; uBytes
0x180031554  xor     ecx, ecx; uFlags
0x180031556  call    cs:__imp_LocalAlloc
0x18003155d  nop     dword ptr [rax+rax+00h]
0x180031562  mov     cs:?g_pbPreferredKey@BeforeKeyRotation@@3PEAEEA, rax; uchar * BeforeKeyRotation::g_pbPreferredKey
0x180031569  test    rax, rax
0x18003156c  jz      loc_180031637
0x180031572  mov     dword ptr [rax], 2
0x180031578  lea     r8, pszBlobType; "CAPIPRIVATEBLOB"
0x18003157f  mov     rax, cs:?g_pbPreferredKey@BeforeKeyRotation@@3PEAEEA; uchar * BeforeKeyRotation::g_pbPreferredKey
0x180031586  xor     edx, edx; hExportKey
0x180031588  mov     ecx, dword ptr [rbp+arg_18]
0x18003158b  mov     [rsp+48h+dwFlags], esi; dwFlags
0x18003158f  mov     [rax+4], ecx
0x180031592  mov     rax, cs:?g_pbPreferredKey@BeforeKeyRotation@@3PEAEEA; uchar * BeforeKeyRotation::g_pbPreferredKey
0x180031599  mov     [rax+8], ebx
0x18003159c  lea     rax, [rbp+arg_18]
0x1800315a0  mov     r9, cs:?g_pbPreferredKey@BeforeKeyRotation@@3PEAEEA; uchar * BeforeKeyRotation::g_pbPreferredKey
0x1800315a7  mov     rcx, [rbp+phKey]; hKey
0x1800315ab  add     r9, 0Ch; pbOutput
0x1800315af  mov     [rsp+48h+pcbResult], rax; pcbResult
0x1800315b4  mov     eax, dword ptr [rbp+arg_18]
0x1800315b7  mov     [rsp+48h+cbOutput], eax; cbOutput
0x1800315bb  call    cs:__imp_BCryptExportKey
0x1800315c2  nop     dword ptr [rax+rax+00h]
0x1800315c7  mov     edi, eax
0x1800315c9  test    eax, eax
0x1800315cb  jns     short loc_1800315EF
0x1800315cd  mov     r9d, 1276h
0x1800315d3  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800315da  lea     rdx, aNtstatus; "ntStatus"
0x1800315e1  mov     ecx, eax
0x1800315e3  call    DebugTraceError
0x1800315e8  mov     ecx, edi
0x1800315ea  jmp     loc_180031493
0x1800315ef  mov     edx, dword ptr [rbp+arg_18]
0x1800315f2  mov     r8, rbx; Size
0x1800315f5  mov     rcx, cs:?g_pbPreferredKey@BeforeKeyRotation@@3PEAEEA; uchar * BeforeKeyRotation::g_pbPreferredKey
0x1800315fc  add     rdx, 0Ch
0x180031600  add     rcx, rdx; void *
0x180031603  mov     rdx, [rbp+Src]; Src
0x180031607  call    memcpy_0
0x18003160c  mov     rax, [rbp+phKey]
0x180031610  lea     rcx, ?g_guidPreferredKey@BeforeKeyRotation@@3U_GUID@@A; struct _GUID *
0x180031617  mov     r8d, cs:?g_cbPreferredKey@BeforeKeyRotation@@3KA; unsigned int
0x18003161e  mov     rdx, cs:?g_pbPreferredKey@BeforeKeyRotation@@3PEAEEA; unsigned __int8 *
0x180031625  mov     cs:?g_hKeyPreferredKey@BeforeKeyRotation@@3PEAXEA, rax; void * BeforeKeyRotation::g_hKeyPreferredKey
0x18003162c  mov     [rbp+phKey], rsi
0x180031630  call    ?SaveBackupKey@@YAHPEAU_GUID@@PEAEK@Z; SaveBackupKey(_GUID *,uchar *,ulong)
0x180031635  mov     esi, eax
0x180031637  mov     rcx, [rbp+phKey]; hKey
0x18003163b  test    rcx, rcx
0x18003163e  jz      short loc_18003164C
0x180031640  call    cs:__imp_BCryptDestroyKey
0x180031647  nop     dword ptr [rax+rax+00h]
0x18003164c  mov     rcx, [rbp+Src]; hMem
0x180031650  test    rcx, rcx
0x180031653  jz      short loc_180031661
0x180031655  call    cs:__imp_LocalFree
0x18003165c  nop     dword ptr [rax+rax+00h]
0x180031661  mov     eax, esi
0x180031663  add     rsp, 48h
0x180031667  pop     rdi
0x180031668  pop     rsi
0x180031669  pop     rbx
0x18003166a  pop     rbp
0x18003166b  retn
```
