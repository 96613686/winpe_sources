# BeforeKeyRotation::GetBackupKey(_GUID *,uchar * *,ulong *,void * *)

- ea: `0x180032218`
- end: `0x18003246e`
- name: `?GetBackupKey@BeforeKeyRotation@@YAHPEAU_GUID@@PEAPEAEPEAKPEAPEAX@Z`
- size: `598`
- prototype: `__int64 __fastcall(BeforeKeyRotation *this, struct _GUID *, unsigned __int8 **, BCRYPT_KEY_HANDLE *)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180033b04`
- `0x1800349e4`
- `0x1800354c8`

## callees

- `0x1800029d0`
- `0x180007f10`
- `0x18000dcb0`
- `0x18001d810`
- `0x180032218`
- `0x180032898`
- `0x1800367a4`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180032423`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180032443`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180032423`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180032443`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003232c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003232c`
- `bcrypt!BCryptImportKeyPair` at `0x1800323bb`
- `bcrypt!BCryptImportKeyPair` at `0x1800323bb`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180032306`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x180032306`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180032411`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180032411`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRetrievePrivateData` at `0x1800322f4`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRetrievePrivateData` at `0x1800322f4`

## string_xrefs

- `0x1800322cc`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x1800323d3`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`

## pseudocode

```c
__int64 __fastcall BeforeKeyRotation::GetBackupKey(
        BeforeKeyRotation *this,
        struct _GUID *a2,
        unsigned __int8 **a3,
        BCRYPT_KEY_HANDLE *a4)
{
  DWORD v7; // ecx
  unsigned __int16 *v8; // rcx
  NTSTATUS v9; // ebx
  __int64 v10; // r9
  HLOCAL v11; // rax
  PLSA_UNICODE_STRING v12; // rdx
  unsigned int v13; // edi
  void *BCryptProviderHandle; // r10
  NTSTATUS v15; // eax
  PLSA_UNICODE_STRING v16; // rcx
  __int64 Length; // rdx
  PWSTR Buffer; // rax
  PLSA_UNICODE_STRING PrivateData; // [rsp+40h] [rbp-79h] BYREF
  LSA_HANDLE PolicyHandle; // [rsp+48h] [rbp-71h] BYREF
  struct _LSA_UNICODE_STRING KeyName; // [rsp+50h] [rbp-69h] BYREF
  unsigned __int16 v23[8]; // [rsp+60h] [rbp-59h] BYREF
  __int64 v24; // [rsp+70h] [rbp-49h] BYREF

  PolicyHandle = 0;
  PrivateData = 0;
  KeyName = 0;
  if ( !this || !a2 || !a3 )
  {
    v7 = 87;
    goto LABEL_28;
  }
  *(_OWORD *)v23 = *(_OWORD *)L"G$BCKUPKEY_";
  v24 = *(_QWORD *)L"EY_";
  if ( (unsigned int)MyGuidToStringW(this, (char *)&v24 + 6) )
  {
    v7 = 2;
LABEL_28:
    SetLastError(v7);
    return 0;
  }
  InitLsaString((struct _UNICODE_STRING *)&KeyName, v23);
  v9 = OpenPolicy(v8, 4u, &PolicyHandle);
  if ( v9 < 0 )
  {
    v10 = 4526;
LABEL_8:
    DebugTraceError((unsigned int)v9, "Status", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp", v10);
    v7 = v9;
    goto LABEL_28;
  }
  v9 = LsaRetrievePrivateData(PolicyHandle, &KeyName, &PrivateData);
  LsaClose(PolicyHandle);
  if ( v9 < 0 || !PrivateData )
  {
    v10 = 4541;
    goto LABEL_8;
  }
  v11 = LocalAlloc(0, PrivateData->Length);
  *(_QWORD *)&a2->Data1 = v11;
  if ( v11 )
  {
    v12 = PrivateData;
    *(_DWORD *)a3 = PrivateData->Length;
    memcpy_0(*(void **)&a2->Data1, v12->Buffer, v12->Length);
    v13 = 1;
    if ( *(_DWORD *)a3 < 4u || **(_DWORD **)&a2->Data1 != 2 )
      goto LABEL_20;
    BCryptProviderHandle = (void *)GetBCryptProviderHandle(0xA400u);
    if ( BCryptProviderHandle )
    {
      if ( !a4 )
        goto LABEL_20;
      v15 = BCryptImportKeyPair(
              BCryptProviderHandle,
              0,
              L"CAPIPRIVATEBLOB",
              a4,
              (PUCHAR)(*(_QWORD *)&a2->Data1 + 12LL),
              *(_DWORD *)(*(_QWORD *)&a2->Data1 + 4LL),
              0);
      v9 = v15;
      if ( v15 >= 0 )
        goto LABEL_20;
      DebugTraceError(
        (unsigned int)v15,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp",
        4583);
    }
  }
  else
  {
    v9 = 8;
  }
  v13 = 0;
LABEL_20:
  v16 = PrivateData;
  Length = PrivateData->Length;
  Buffer = PrivateData->Buffer;
  if ( PrivateData->Length )
  {
    do
    {
      *(_BYTE *)Buffer = 0;
      Buffer = (PWSTR)((char *)Buffer + 1);
      --Length;
    }
    while ( Length );
    v16 = PrivateData;
  }
  LsaFreeMemory(v16);
  if ( !v13 )
    SetLastError(v9);
  return v13;
}

```

## disassembly

```asm
0x180032218  push    rbp
0x18003221a  push    rbx
0x18003221b  push    rsi
0x18003221c  push    rdi
0x18003221d  push    r14
0x18003221f  push    r15
0x180032221  lea     rbp, [rsp-2Fh]
0x180032226  sub     rsp, 0E8h
0x18003222d  mov     rax, cs:__security_cookie
0x180032234  xor     rax, rsp
0x180032237  mov     [rbp+57h+var_40], rax
0x18003223b  mov     [rbp+57h+PolicyHandle], 0
0x180032243  xorps   xmm0, xmm0
0x180032246  mov     [rbp+57h+PrivateData], 0
0x18003224e  mov     r15, r9
0x180032251  mov     r14, r8
0x180032254  mov     rsi, rdx
0x180032257  movups  xmmword ptr [rbp+57h+KeyName.Length], xmm0
0x18003225b  test    rcx, rcx
0x18003225e  jz      loc_18003243E
0x180032264  test    rdx, rdx
0x180032267  jz      loc_18003243E
0x18003226d  test    r8, r8
0x180032270  jz      loc_18003243E
0x180032276  movups  xmm0, xmmword ptr cs:aGBckupkey; "G$BCKUPKEY_"
0x18003227d  lea     rdx, [rbp+57h+var_9A]
0x180032281  movsd   xmm1, qword ptr cs:aGBckupkey+10h; "EY_"
0x180032289  movaps  xmmword ptr [rbp+57h+var_B0], xmm0
0x18003228d  movsd   qword ptr [rbp-49h], xmm1
0x180032292  call    MyGuidToStringW
0x180032297  test    eax, eax
0x180032299  jz      short loc_1800322A5
0x18003229b  mov     ecx, 2
0x1800322a0  jmp     loc_180032443
0x1800322a5  lea     rdx, [rbp+57h+var_B0]; unsigned __int16 *
0x1800322a9  lea     rcx, [rbp+57h+KeyName]; struct _UNICODE_STRING *
0x1800322ad  call    ?InitLsaString@@YAXPEAU_UNICODE_STRING@@PEAG@Z; InitLsaString(_UNICODE_STRING *,ushort *)
0x1800322b2  lea     r8, [rbp+57h+PolicyHandle]; void **
0x1800322b6  mov     edx, 4; unsigned int
0x1800322bb  call    ?OpenPolicy@@YAJPEAGKPEAPEAX@Z; OpenPolicy(ushort *,ulong,void * *)
0x1800322c0  mov     ebx, eax
0x1800322c2  test    eax, eax
0x1800322c4  jns     short loc_1800322E8
0x1800322c6  mov     r9d, 11AEh
0x1800322cc  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800322d3  mov     ecx, ebx
0x1800322d5  lea     rdx, aStatus; "Status"
0x1800322dc  call    DebugTraceError
0x1800322e1  mov     ecx, ebx
0x1800322e3  jmp     loc_180032443
0x1800322e8  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x1800322ec  lea     r8, [rbp+57h+PrivateData]; PrivateData
0x1800322f0  lea     rdx, [rbp+57h+KeyName]; KeyName
0x1800322f4  call    cs:__imp_LsaRetrievePrivateData
0x1800322fb  nop     dword ptr [rax+rax+00h]
0x180032300  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x180032304  mov     ebx, eax
0x180032306  call    cs:__imp_LsaClose
0x18003230d  nop     dword ptr [rax+rax+00h]
0x180032312  test    ebx, ebx
0x180032314  js      loc_180032433
0x18003231a  mov     rax, [rbp+57h+PrivateData]
0x18003231e  test    rax, rax
0x180032321  jz      loc_180032433
0x180032327  movzx   edx, word ptr [rax]; uBytes
0x18003232a  xor     ecx, ecx; uFlags
0x18003232c  call    cs:__imp_LocalAlloc
0x180032333  nop     dword ptr [rax+rax+00h]
0x180032338  mov     [rsi], rax
0x18003233b  test    rax, rax
0x18003233e  jz      loc_1800323EA
0x180032344  mov     rdx, [rbp+57h+PrivateData]
0x180032348  movzx   eax, word ptr [rdx]
0x18003234b  mov     [r14], eax
0x18003234e  movzx   r8d, word ptr [rdx]; Size
0x180032352  mov     rdx, [rdx+8]; Src
0x180032356  mov     rcx, [rsi]; void *
0x180032359  call    memcpy_0
0x18003235e  cmp     dword ptr [r14], 4
0x180032362  mov     edi, 1
0x180032367  jb      loc_1800323F1
0x18003236d  mov     rax, [rsi]
0x180032370  cmp     dword ptr [rax], 2
0x180032373  jnz     short loc_1800323F1
0x180032375  xor     r8d, r8d
0x180032378  xor     edx, edx
0x18003237a  mov     ecx, 0A400h; unsigned int
0x18003237f  call    GetBCryptProviderHandle
0x180032384  mov     r10, rax
0x180032387  test    rax, rax
0x18003238a  jz      short loc_1800323EF
0x18003238c  test    r15, r15
0x18003238f  jz      short loc_1800323F1
0x180032391  mov     rax, [rsi]
0x180032394  lea     r8, pszBlobType; "CAPIPRIVATEBLOB"
0x18003239b  mov     [rsp+110h+dwFlags], 0; dwFlags
0x1800323a3  mov     r9, r15; phKey
0x1800323a6  xor     edx, edx; hImportKey
0x1800323a8  lea     rcx, [rax+0Ch]
0x1800323ac  mov     eax, [rax+4]
0x1800323af  mov     [rsp+110h+cbInput], eax; cbInput
0x1800323b3  mov     [rsp+110h+pbInput], rcx; pbInput
0x1800323b8  mov     rcx, r10; hAlgorithm
0x1800323bb  call    cs:__imp_BCryptImportKeyPair
0x1800323c2  nop     dword ptr [rax+rax+00h]
0x1800323c7  mov     ebx, eax
0x1800323c9  test    eax, eax
0x1800323cb  jns     short loc_1800323F1
0x1800323cd  mov     r9d, 11E7h
0x1800323d3  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800323da  lea     rdx, aStatus; "Status"
0x1800323e1  mov     ecx, eax
0x1800323e3  call    DebugTraceError
0x1800323e8  jmp     short loc_1800323EF
0x1800323ea  mov     ebx, 8
0x1800323ef  xor     edi, edi
0x1800323f1  mov     rcx, [rbp+57h+PrivateData]
0x1800323f5  movzx   edx, word ptr [rcx]
0x1800323f8  mov     rax, [rcx+8]
0x1800323fc  test    rdx, rdx
0x1800323ff  jz      short loc_180032411
0x180032401  mov     byte ptr [rax], 0
0x180032404  inc     rax
0x180032407  sub     rdx, 1
0x18003240b  jnz     short loc_180032401
0x18003240d  mov     rcx, [rbp+57h+PrivateData]; Buffer
0x180032411  call    cs:__imp_LsaFreeMemory
0x180032418  nop     dword ptr [rax+rax+00h]
0x18003241d  test    edi, edi
0x18003241f  jnz     short loc_18003242F
0x180032421  mov     ecx, ebx; dwErrCode
0x180032423  call    cs:__imp_SetLastError
0x18003242a  nop     dword ptr [rax+rax+00h]
0x18003242f  mov     eax, edi
0x180032431  jmp     short loc_180032451
0x180032433  mov     r9d, 11BDh
0x180032439  jmp     loc_1800322CC
0x18003243e  mov     ecx, 57h ; 'W'; dwErrCode
0x180032443  call    cs:__imp_SetLastError
0x18003244a  nop     dword ptr [rax+rax+00h]
0x18003244f  xor     eax, eax
0x180032451  mov     rcx, [rbp+57h+var_40]
0x180032455  xor     rcx, rsp; StackCookie
0x180032458  call    __security_check_cookie
0x18003245d  add     rsp, 0E8h
0x180032464  pop     r15
0x180032466  pop     r14
0x180032468  pop     rdi
0x180032469  pop     rsi
0x18003246a  pop     rbx
0x18003246b  pop     rbp
0x18003246c  retn
```
