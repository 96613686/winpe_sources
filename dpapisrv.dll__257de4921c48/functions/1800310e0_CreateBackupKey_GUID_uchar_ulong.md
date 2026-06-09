# CreateBackupKey(_GUID *,uchar * *,ulong *)

- ea: `0x1800310e0`
- end: `0x1800313c0`
- name: `?CreateBackupKey@@YAHPEAU_GUID@@PEAPEAEPEAK@Z`
- size: `736`
- prototype: `__int64 __fastcall(struct _GUID *, unsigned __int8 **, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180030f00`

## callees

- `0x1800029d0`
- `0x180007f10`
- `0x1800310e0`
- `0x180031984`
- `0x180034ff8`
- `0x18003c62c`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x180031129`
- `RPCRT4!UuidCreate` at `0x180031129`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800311ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031399`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800311ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180031399`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003134d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003137b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003134d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003137b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003126d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003126d`
- `bcrypt!BCryptDestroyKey` at `0x180031366`
- `bcrypt!BCryptDestroyKey` at `0x180031366`
- `bcrypt!BCryptFinalizeKeyPair` at `0x1800311c3`
- `bcrypt!BCryptFinalizeKeyPair` at `0x1800311c3`
- `bcrypt!BCryptGenerateKeyPair` at `0x18003117a`
- `bcrypt!BCryptGenerateKeyPair` at `0x18003117a`
- `bcrypt!BCryptExportKey` at `0x180031201`
- `bcrypt!BCryptExportKey` at `0x1800312c4`
- `bcrypt!BCryptExportKey` at `0x180031201`
- `bcrypt!BCryptExportKey` at `0x1800312c4`

## string_xrefs

- `0x180031193`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x18003123d`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x1800312dd`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`

## pseudocode

```c
__int64 __fastcall CreateBackupKey(struct _GUID *a1, unsigned __int8 **a2, unsigned int *a3)
{
  RPC_STATUS v6; // eax
  DWORD v7; // ecx
  unsigned int v8; // r15d
  void *BCryptProviderHandle; // rax
  NTSTATUS v10; // r14d
  __int64 v11; // r9
  DWORD v12; // ecx
  size_t v13; // r14
  unsigned int v14; // ecx
  unsigned __int8 *v15; // rax
  NTSTATUS v16; // eax
  NTSTATUS v17; // r12d
  BCRYPT_KEY_HANDLE v18; // rdx
  unsigned __int8 *v19; // rcx
  __int64 v20; // rdx
  BCRYPT_KEY_HANDLE phKey; // [rsp+40h] [rbp-10h] BYREF
  void *Src; // [rsp+48h] [rbp-8h] BYREF
  ULONG pcbResult; // [rsp+90h] [rbp+40h] BYREF
  size_t Size; // [rsp+A8h] [rbp+58h] BYREF

  phKey = 0;
  Src = 0;
  if ( !a1 )
  {
    if ( a2 )
      goto LABEL_34;
LABEL_35:
    v7 = 87;
    goto LABEL_36;
  }
  if ( !a2 )
    goto LABEL_35;
  if ( !a3 )
  {
LABEL_34:
    *a2 = 0;
    goto LABEL_35;
  }
  *a2 = 0;
  v6 = UuidCreate(a1);
  if ( v6 && v6 != 1824 )
  {
    v7 = v6;
LABEL_36:
    SetLastError(v7);
    return 0;
  }
  pcbResult = 0;
  LODWORD(Size) = 0;
  v8 = 0;
  BCryptProviderHandle = (void *)GetBCryptProviderHandle(0xA400u);
  if ( BCryptProviderHandle )
  {
    v10 = BCryptGenerateKeyPair(BCryptProviderHandle, &phKey, 0x800u, 0);
    if ( v10 >= 0 )
    {
      v10 = BCryptFinalizeKeyPair(phKey, 0);
      if ( v10 >= 0 )
      {
        v10 = BCryptExportKey(phKey, 0, L"CAPIPRIVATEBLOB", 0, 0, &pcbResult, 0);
        if ( v10 >= 0 )
        {
          if ( !(unsigned int)GeneratePublicKeyCert(phKey, a1, (unsigned int *)&Size, (unsigned __int8 **)&Src) )
          {
            DebugTraceError(
              2147500037LL,
              "E_FAIL",
              "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp",
              2475);
            goto LABEL_22;
          }
          v13 = (unsigned int)Size;
          v14 = Size + pcbResult + 12;
          *a3 = v14;
          v15 = (unsigned __int8 *)LocalAlloc(0, v14);
          *a2 = v15;
          if ( !v15 )
            goto LABEL_22;
          *(_DWORD *)v15 = 2;
          *((_DWORD *)*a2 + 1) = pcbResult;
          *((_DWORD *)*a2 + 2) = v13;
          v16 = BCryptExportKey(phKey, 0, L"CAPIPRIVATEBLOB", *a2 + 12, pcbResult, &pcbResult, 0);
          v17 = v16;
          if ( v16 >= 0 )
          {
            memcpy_0(&(*a2)[pcbResult + 12], Src, v13);
            v8 = SaveBackupKey(a1, *a2, *a3);
            goto LABEL_22;
          }
          DebugTraceError(
            (unsigned int)v16,
            "ntStatus",
            "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp",
            2505);
          v12 = v17;
          goto LABEL_11;
        }
        v11 = 2465;
      }
      else
      {
        v11 = 2448;
      }
    }
    else
    {
      v11 = 2439;
    }
    DebugTraceError(
      (unsigned int)v10,
      "ntStatus",
      "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp",
      v11);
    v12 = v10;
LABEL_11:
    SetLastError(v12);
  }
LABEL_22:
  v18 = phKey;
  if ( phKey )
  {
    if ( !v8 )
    {
      v19 = *a2;
      if ( *a2 )
      {
        v20 = *a3;
        if ( *a3 )
        {
          do
          {
            *v19++ = 0;
            --v20;
          }
          while ( v20 );
        }
        LocalFree(*a2);
        v18 = phKey;
        *a2 = 0;
      }
      *a3 = 0;
    }
    BCryptDestroyKey(v18);
  }
  if ( Src )
    LocalFree(Src);
  return v8;
}

```

## disassembly

```asm
0x1800310e0  mov     [rsp-38h+arg_8], rbx
0x1800310e5  push    rbp
0x1800310e6  push    rsi
0x1800310e7  push    rdi
0x1800310e8  push    r12
0x1800310ea  push    r13
0x1800310ec  push    r14
0x1800310ee  push    r15
0x1800310f0  mov     rbp, rsp
0x1800310f3  sub     rsp, 50h
0x1800310f7  xor     r13d, r13d
0x1800310fa  mov     rdi, r8
0x1800310fd  mov     [rbp+phKey], r13
0x180031101  mov     rbx, rdx
0x180031104  mov     [rbp+Src], r13
0x180031108  mov     rsi, rcx
0x18003110b  test    rcx, rcx
0x18003110e  jz      loc_18003138C
0x180031114  test    rdx, rdx
0x180031117  jz      loc_180031394
0x18003111d  test    r8, r8
0x180031120  jz      loc_180031391
0x180031126  mov     [rdx], r13
0x180031129  call    cs:__imp_UuidCreate
0x180031130  nop     dword ptr [rax+rax+00h]
0x180031135  test    eax, eax
0x180031137  jz      short loc_180031147
0x180031139  cmp     eax, 720h
0x18003113e  jz      short loc_180031147
0x180031140  mov     ecx, eax
0x180031142  jmp     loc_180031399
0x180031147  xor     r8d, r8d
0x18003114a  mov     [rbp+arg_0], r13d
0x18003114e  xor     edx, edx
0x180031150  mov     dword ptr [rbp+Size], r13d
0x180031154  mov     ecx, 0A400h; unsigned int
0x180031159  mov     r15d, r13d
0x18003115c  call    GetBCryptProviderHandle
0x180031161  test    rax, rax
0x180031164  jz      loc_180031321
0x18003116a  xor     r9d, r9d; dwFlags
0x18003116d  lea     rdx, [rbp+phKey]; phKey
0x180031171  mov     r8d, 800h; dwLength
0x180031177  mov     rcx, rax; hAlgorithm
0x18003117a  call    cs:__imp_BCryptGenerateKeyPair
0x180031181  nop     dword ptr [rax+rax+00h]
0x180031186  mov     r14d, eax
0x180031189  test    eax, eax
0x18003118b  jns     short loc_1800311BD
0x18003118d  mov     r9d, 987h
0x180031193  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18003119a  mov     ecx, r14d
0x18003119d  lea     rdx, aNtstatus; "ntStatus"
0x1800311a4  call    DebugTraceError
0x1800311a9  mov     ecx, r14d; dwErrCode
0x1800311ac  call    cs:__imp_SetLastError
0x1800311b3  nop     dword ptr [rax+rax+00h]
0x1800311b8  jmp     loc_180031321
0x1800311bd  mov     rcx, [rbp+phKey]; hKey
0x1800311c1  xor     edx, edx; dwFlags
0x1800311c3  call    cs:__imp_BCryptFinalizeKeyPair
0x1800311ca  nop     dword ptr [rax+rax+00h]
0x1800311cf  mov     r14d, eax
0x1800311d2  test    eax, eax
0x1800311d4  jns     short loc_1800311DE
0x1800311d6  mov     r9d, 990h
0x1800311dc  jmp     short loc_180031193
0x1800311de  mov     rcx, [rbp+phKey]; hKey
0x1800311e2  lea     rax, [rbp+arg_0]
0x1800311e6  mov     [rsp+50h+dwFlags], r13d; dwFlags
0x1800311eb  lea     r8, pszBlobType; "CAPIPRIVATEBLOB"
0x1800311f2  mov     [rsp+50h+pcbResult], rax; pcbResult
0x1800311f7  xor     r9d, r9d; pbOutput
0x1800311fa  xor     edx, edx; hExportKey
0x1800311fc  mov     [rsp+50h+cbOutput], r13d; cbOutput
0x180031201  call    cs:__imp_BCryptExportKey
0x180031208  nop     dword ptr [rax+rax+00h]
0x18003120d  mov     r14d, eax
0x180031210  test    eax, eax
0x180031212  jns     short loc_18003121F
0x180031214  mov     r9d, 9A1h
0x18003121a  jmp     loc_180031193
0x18003121f  mov     rcx, [rbp+phKey]; hKey
0x180031223  lea     r9, [rbp+Src]; unsigned __int8 **
0x180031227  lea     r8, [rbp+Size]; unsigned int *
0x18003122b  mov     rdx, rsi; struct _GUID *
0x18003122e  call    ?GeneratePublicKeyCert@@YAHPEAXPEAU_GUID@@PEAKPEAPEAE@Z; GeneratePublicKeyCert(void *,_GUID *,ulong *,uchar * *)
0x180031233  test    eax, eax
0x180031235  jnz     short loc_18003125A
0x180031237  mov     r9d, 9ABh
0x18003123d  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x180031244  lea     rdx, aEFail; "E_FAIL"
0x18003124b  mov     ecx, 80004005h
0x180031250  call    DebugTraceError
0x180031255  jmp     loc_180031321
0x18003125a  mov     ecx, [rbp+arg_0]
0x18003125d  mov     r14d, dword ptr [rbp+Size]
0x180031261  add     ecx, 0Ch
0x180031264  add     ecx, r14d
0x180031267  mov     [rdi], ecx
0x180031269  mov     edx, ecx; uBytes
0x18003126b  xor     ecx, ecx; uFlags
0x18003126d  call    cs:__imp_LocalAlloc
0x180031274  nop     dword ptr [rax+rax+00h]
0x180031279  mov     [rbx], rax
0x18003127c  test    rax, rax
0x18003127f  jz      loc_180031321
0x180031285  mov     dword ptr [rax], 2
0x18003128b  lea     r8, pszBlobType; "CAPIPRIVATEBLOB"
0x180031292  mov     rcx, [rbx]
0x180031295  xor     edx, edx; hExportKey
0x180031297  mov     eax, [rbp+arg_0]
0x18003129a  mov     [rsp+50h+dwFlags], r13d; dwFlags
0x18003129f  mov     [rcx+4], eax
0x1800312a2  mov     rax, [rbx]
0x1800312a5  mov     [rax+8], r14d
0x1800312a9  lea     rax, [rbp+arg_0]
0x1800312ad  mov     r9, [rbx]
0x1800312b0  mov     rcx, [rbp+phKey]; hKey
0x1800312b4  add     r9, 0Ch; pbOutput
0x1800312b8  mov     [rsp+50h+pcbResult], rax; pcbResult
0x1800312bd  mov     eax, [rbp+arg_0]
0x1800312c0  mov     [rsp+50h+cbOutput], eax; cbOutput
0x1800312c4  call    cs:__imp_BCryptExportKey
0x1800312cb  nop     dword ptr [rax+rax+00h]
0x1800312d0  mov     r12d, eax
0x1800312d3  test    eax, eax
0x1800312d5  jns     short loc_1800312FA
0x1800312d7  mov     r9d, 9C9h
0x1800312dd  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800312e4  lea     rdx, aNtstatus; "ntStatus"
0x1800312eb  mov     ecx, eax
0x1800312ed  call    DebugTraceError
0x1800312f2  mov     ecx, r12d
0x1800312f5  jmp     loc_1800311AC
0x1800312fa  mov     ecx, [rbp+arg_0]
0x1800312fd  mov     r8, r14; Size
0x180031300  mov     rdx, [rbp+Src]; Src
0x180031304  add     rcx, 0Ch
0x180031308  add     rcx, [rbx]; void *
0x18003130b  call    memcpy_0
0x180031310  mov     r8d, [rdi]; unsigned int
0x180031313  mov     rcx, rsi; struct _GUID *
0x180031316  mov     rdx, [rbx]; unsigned __int8 *
0x180031319  call    ?SaveBackupKey@@YAHPEAU_GUID@@PEAEK@Z; SaveBackupKey(_GUID *,uchar *,ulong)
0x18003131e  mov     r15d, eax
0x180031321  mov     rdx, [rbp+phKey]
0x180031325  test    rdx, rdx
0x180031328  jz      short loc_180031372
0x18003132a  test    r15d, r15d
0x18003132d  jnz     short loc_180031363
0x18003132f  mov     rcx, [rbx]
0x180031332  test    rcx, rcx
0x180031335  jz      short loc_180031360
0x180031337  mov     edx, [rdi]
0x180031339  test    rdx, rdx
0x18003133c  jz      short loc_18003134A
0x18003133e  mov     [rcx], r13b
0x180031341  inc     rcx
0x180031344  sub     rdx, 1
0x180031348  jnz     short loc_18003133E
0x18003134a  mov     rcx, [rbx]; hMem
0x18003134d  call    cs:__imp_LocalFree
0x180031354  nop     dword ptr [rax+rax+00h]
0x180031359  mov     rdx, [rbp+phKey]
0x18003135d  mov     [rbx], r13
0x180031360  mov     [rdi], r13d
0x180031363  mov     rcx, rdx; hKey
0x180031366  call    cs:__imp_BCryptDestroyKey
0x18003136d  nop     dword ptr [rax+rax+00h]
0x180031372  mov     rcx, [rbp+Src]; hMem
0x180031376  test    rcx, rcx
0x180031379  jz      short loc_180031387
0x18003137b  call    cs:__imp_LocalFree
0x180031382  nop     dword ptr [rax+rax+00h]
0x180031387  mov     eax, r15d
0x18003138a  jmp     short loc_1800313A7
0x18003138c  test    rbx, rbx
0x18003138f  jz      short loc_180031394
0x180031391  mov     [rdx], r13
0x180031394  mov     ecx, 57h ; 'W'; dwErrCode
0x180031399  call    cs:__imp_SetLastError
0x1800313a0  nop     dword ptr [rax+rax+00h]
0x1800313a5  xor     eax, eax
0x1800313a7  mov     rbx, [rsp+50h+arg_8]
0x1800313af  add     rsp, 50h
0x1800313b3  pop     r15
0x1800313b5  pop     r14
0x1800313b7  pop     r13
0x1800313b9  pop     r12
0x1800313bb  pop     rdi
0x1800313bc  pop     rsi
0x1800313bd  pop     rbp
0x1800313be  retn
```
