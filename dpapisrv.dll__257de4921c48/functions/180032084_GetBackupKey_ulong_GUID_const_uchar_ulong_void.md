# GetBackupKey(ulong,_GUID const *,uchar * *,ulong *,void * *)

- ea: `0x180032084`
- end: `0x180032210`
- name: `?GetBackupKey@@YAHKPEBU_GUID@@PEAPEAEPEAKPEAPEAX@Z`
- size: `396`
- prototype: `__int64 __fastcall(unsigned int, const struct _GUID *, unsigned __int8 **, unsigned int *, BCRYPT_KEY_HANDLE *phKey)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18003325c`
- `0x18003442c`

## callees

- `0x1800029d0`
- `0x180007f10`
- `0x180030954`
- `0x180032084`
- `0x18003281c`
- `0x180032a9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032189`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032189`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800321cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800321cf`
- `bcrypt!BCryptImportKeyPair` at `0x180032163`
- `bcrypt!BCryptImportKeyPair` at `0x180032163`

## string_xrefs

- `0x1800321a2`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`
- `0x1800321ea`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysrv.cpp`

## pseudocode

```c
__int64 __fastcall GetBackupKey(
        unsigned int a1,
        const struct _GUID *a2,
        unsigned __int8 **a3,
        unsigned int *a4,
        BCRYPT_KEY_HANDLE *phKey)
{
  __int64 v9; // r9
  bool v10; // al
  unsigned int BackupKeyFromLsaSecret; // ebx
  bool IsValidKeyBuffer; // al
  unsigned __int8 *v13; // rbx
  ULONG cbInput; // ebp
  void *BCryptProviderHandle; // rax
  int LastError; // eax
  const char *v17; // rdx
  __int64 v18; // r9
  unsigned __int8 *v19; // rcx
  __int64 v20; // rdx
  unsigned __int8 *v21; // rax

  if ( !a2 || !a3 || !a4 )
  {
    v9 = 2234;
    goto LABEL_23;
  }
  if ( a1 - 1 <= 1 )
  {
    v10 = CPreferredKeys::CopyBufferIfMatch(a1, a2, a3, a4);
    BackupKeyFromLsaSecret = v10;
    if ( !v10 )
    {
      BackupKeyFromLsaSecret = ReadBackupKeyFromLsaSecret(a2, a3, a4);
      if ( !BackupKeyFromLsaSecret )
        return BackupKeyFromLsaSecret;
      IsValidKeyBuffer = CPreferredKeys::IsValidKeyBuffer(a1, *a3, *a4);
      BackupKeyFromLsaSecret = IsValidKeyBuffer;
      if ( !IsValidKeyBuffer )
        return BackupKeyFromLsaSecret;
    }
    if ( a1 != 2 || !phKey )
      return BackupKeyFromLsaSecret;
    v13 = *a3;
    *phKey = 0;
    cbInput = *((_DWORD *)v13 + 1);
    BCryptProviderHandle = (void *)GetBCryptProviderHandle(0xA400u);
    if ( BCryptProviderHandle )
    {
      LastError = BCryptImportKeyPair(BCryptProviderHandle, 0, L"CAPIPRIVATEBLOB", phKey, v13 + 12, cbInput, 0);
      if ( LastError >= 0 )
        return 1;
      v17 = "Status";
      v18 = 2277;
    }
    else
    {
      LastError = GetLastError();
      v17 = "GetLastError()";
      v18 = 2282;
    }
    BackupKeyFromLsaSecret = 0;
    DebugTraceError(
      (unsigned int)LastError,
      v17,
      "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp",
      v18);
    v19 = *a3;
    if ( *a3 )
    {
      v20 = *a4;
      v21 = *a3;
      if ( *a4 )
      {
        do
        {
          *v21++ = 0;
          --v20;
        }
        while ( v20 );
      }
      LocalFree(v19);
      *a3 = 0;
    }
    *a4 = 0;
    return BackupKeyFromLsaSecret;
  }
  v9 = 2240;
LABEL_23:
  DebugTraceError(
    3221225485LL,
    "STATUS_INVALID_PARAMETER",
    "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysrv.cpp",
    v9);
  return 0;
}

```

## disassembly

```asm
0x180032084  push    rbx
0x180032086  push    rbp
0x180032087  push    rsi
0x180032088  push    rdi
0x180032089  push    r14
0x18003208b  sub     rsp, 40h
0x18003208f  mov     rsi, r9
0x180032092  mov     rdi, r8
0x180032095  mov     r14, rdx
0x180032098  mov     ebp, ecx
0x18003209a  test    rdx, rdx
0x18003209d  jz      loc_1800321E4
0x1800320a3  test    r8, r8
0x1800320a6  jz      loc_1800321E4
0x1800320ac  test    r9, r9
0x1800320af  jz      loc_1800321E4
0x1800320b5  lea     eax, [rcx-1]
0x1800320b8  cmp     eax, 1
0x1800320bb  jbe     short loc_1800320C8
0x1800320bd  mov     r9d, 8C0h; unsigned int *
0x1800320c3  jmp     loc_1800321EA
0x1800320c8  call    ?CopyBufferIfMatch@CPreferredKeys@@SA_NKPEBU_GUID@@PEAPEAEPEAK@Z; CPreferredKeys::CopyBufferIfMatch(ulong,_GUID const *,uchar * *,ulong *)
0x1800320cd  movzx   ebx, al
0x1800320d0  test    al, al
0x1800320d2  jnz     short loc_180032104
0x1800320d4  mov     r8, rsi; unsigned int *
0x1800320d7  mov     rdx, rdi; unsigned __int8 **
0x1800320da  mov     rcx, r14; struct _GUID *
0x1800320dd  call    ?ReadBackupKeyFromLsaSecret@@YAHPEBU_GUID@@PEAPEAEPEAK@Z; ReadBackupKeyFromLsaSecret(_GUID const *,uchar * *,ulong *)
0x1800320e2  mov     ebx, eax
0x1800320e4  test    eax, eax
0x1800320e6  jz      loc_1800321E0
0x1800320ec  mov     r8d, [rsi]; unsigned int
0x1800320ef  mov     ecx, ebp; unsigned int
0x1800320f1  mov     rdx, [rdi]; unsigned __int8 *
0x1800320f4  call    ?IsValidKeyBuffer@CPreferredKeys@@SA_NKQEAEK@Z; CPreferredKeys::IsValidKeyBuffer(ulong,uchar * const,ulong)
0x1800320f9  movzx   ebx, al
0x1800320fc  test    al, al
0x1800320fe  jz      loc_1800321E0
0x180032104  cmp     ebp, 2
0x180032107  jnz     loc_1800321E0
0x18003210d  mov     r14, [rsp+68h+phKey]
0x180032115  test    r14, r14
0x180032118  jz      loc_1800321E0
0x18003211e  mov     rbx, [rdi]
0x180032121  xor     r8d, r8d
0x180032124  mov     qword ptr [r14], 0
0x18003212b  xor     edx, edx
0x18003212d  mov     ecx, 0A400h; unsigned int
0x180032132  mov     ebp, [rbx+4]
0x180032135  call    GetBCryptProviderHandle
0x18003213a  test    rax, rax
0x18003213d  jz      short loc_180032189
0x18003213f  lea     rcx, [rbx+0Ch]
0x180032143  mov     [rsp+68h+dwFlags], 0; dwFlags
0x18003214b  mov     [rsp+68h+cbInput], ebp; cbInput
0x18003214f  lea     r8, pszBlobType; "CAPIPRIVATEBLOB"
0x180032156  mov     [rsp+68h+pbInput], rcx; pbInput
0x18003215b  mov     r9, r14; phKey
0x18003215e  mov     rcx, rax; hAlgorithm
0x180032161  xor     edx, edx; hImportKey
0x180032163  call    cs:__imp_BCryptImportKeyPair
0x18003216a  nop     dword ptr [rax+rax+00h]
0x18003216f  test    eax, eax
0x180032171  js      short loc_18003217A
0x180032173  mov     ebx, 1
0x180032178  jmp     short loc_1800321E0
0x18003217a  lea     rdx, aStatus; "Status"
0x180032181  mov     r9d, 8E5h
0x180032187  jmp     short loc_1800321A2
0x180032189  call    cs:__imp_GetLastError
0x180032190  nop     dword ptr [rax+rax+00h]
0x180032195  lea     rdx, aGetlasterror; "GetLastError()"
0x18003219c  mov     r9d, 8EAh
0x1800321a2  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800321a9  mov     ecx, eax
0x1800321ab  xor     ebx, ebx
0x1800321ad  call    DebugTraceError
0x1800321b2  mov     rcx, [rdi]; hMem
0x1800321b5  test    rcx, rcx
0x1800321b8  jz      short loc_1800321DE
0x1800321ba  mov     edx, [rsi]
0x1800321bc  mov     rax, rcx
0x1800321bf  test    rdx, rdx
0x1800321c2  jz      short loc_1800321CF
0x1800321c4  mov     [rax], bl
0x1800321c6  inc     rax
0x1800321c9  sub     rdx, 1
0x1800321cd  jnz     short loc_1800321C4
0x1800321cf  call    cs:__imp_LocalFree
0x1800321d6  nop     dword ptr [rax+rax+00h]
0x1800321db  mov     [rdi], rbx
0x1800321de  mov     [rsi], ebx
0x1800321e0  mov     eax, ebx
0x1800321e2  jmp     short loc_180032204
0x1800321e4  mov     r9d, 8BAh
0x1800321ea  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\secst"...
0x1800321f1  mov     ecx, 0C000000Dh
0x1800321f6  lea     rdx, aStatusInvalidP; "STATUS_INVALID_PARAMETER"
0x1800321fd  call    DebugTraceError
0x180032202  xor     eax, eax
0x180032204  add     rsp, 40h
0x180032208  pop     r14
0x18003220a  pop     rdi
0x18003220b  pop     rsi
0x18003220c  pop     rbp
0x18003220d  pop     rbx
0x18003220e  retn
```
