# CSCLogonInit::CryptCtx(uchar *,ulong)

- ea: `0x18007c610`
- end: `0x18007c7c5`
- name: `?CryptCtx@CSCLogonInit@@QEAA_KPEAEK@Z`
- size: `437`
- prototype: `HCRYPTPROV __fastcall(CSCLogonInit *this, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180029650`

## callees

- `0x180040a7c`
- `0x180040b30`
- `0x18007c610`
- `0x18007cf88`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c6e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c764`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c6e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c764`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18007c6df`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18007c75a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18007c6df`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18007c75a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007c7af`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18007c7af`
- `ncrypt!NCryptFreeObject` at `0x18007c772`
- `ncrypt!NCryptFreeObject` at `0x18007c78e`
- `ncrypt!NCryptFreeObject` at `0x18007c772`
- `ncrypt!NCryptFreeObject` at `0x18007c78e`
- `ncrypt!NCryptOpenKey` at `0x18007c73a`
- `ncrypt!NCryptOpenKey` at `0x18007c73a`
- `ncrypt!NCryptOpenStorageProvider` at `0x18007c71b`
- `ncrypt!NCryptOpenStorageProvider` at `0x18007c71b`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18007c67d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptAcquireContextW` at `0x18007c67d`
- `ntdll!NtClose` at `0x18007c7a6`
- `ntdll!NtClose` at `0x18007c7a6`
- `ntdll!NtOpenThreadToken` at `0x18007c6ab`
- `ntdll!NtOpenThreadToken` at `0x18007c6ab`

## pseudocode

```c
HCRYPTPROV __fastcall CSCLogonInit::CryptCtx(CSCLogonInit *this, unsigned __int8 *a2, unsigned int a3)
{
  HCRYPTPROV *v3; // rdi
  unsigned int v7; // edx
  unsigned __int8 *v8; // rcx
  WCHAR *KeyName; // rbp
  const WCHAR *CSPName; // rax
  bool v11; // zf
  unsigned int v12; // ebx
  signed int LastError; // eax
  const WCHAR *v14; // rax
  NCRYPT_HANDLE v15; // rcx
  void *TokenHandle; // [rsp+70h] [rbp+8h] BYREF

  v3 = (HCRYPTPROV *)((char *)this + 8);
  if ( !*((_QWORD *)this + 1) )
  {
    *(_DWORD *)this = ScHelperGetKeySpecFromCSPInfo(a2, a3);
    KeyName = (WCHAR *)ScHelperGetKeyName(v8, v7);
    if ( KeyName )
    {
      if ( (unsigned int)(*(_DWORD *)this - 1) <= 0xFFFFFFFD )
      {
        CSPName = GetCSPName(a2, a3);
        CryptAcquireContextW(v3, KeyName, CSPName, 1u, 0x60u);
LABEL_26:
        LocalFree(KeyName);
        return *v3;
      }
      v11 = *((_BYTE *)this + 26) == 0;
      TokenHandle = 0;
      if ( !v11 )
      {
        v12 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandle);
        if ( (int)(v12 + 0x80000000) >= 0 && v12 != -1073741700 )
        {
LABEL_24:
          if ( TokenHandle )
            NtClose(TokenHandle);
          goto LABEL_26;
        }
        if ( v12 == -1073741700 )
        {
          TokenHandle = 0;
        }
        else
        {
          if ( !SetThreadToken(0, 0) )
          {
            LastError = GetLastError();
            v12 = LastError;
            if ( LastError > 0 )
              v12 = (unsigned __int16)LastError | 0xC0070000;
          }
          if ( v12 )
            goto LABEL_24;
        }
      }
      v14 = GetCSPName(a2, a3);
      if ( NCryptOpenStorageProvider((NCRYPT_PROV_HANDLE *)this + 2, v14, 0) >= 0
        && NCryptOpenKey(*((_QWORD *)this + 2), v3, KeyName, 0, 0x60u) < 0 )
      {
        *v3 = 0;
      }
      if ( TokenHandle )
      {
        if ( !SetThreadToken(0, TokenHandle) )
        {
          GetLastError();
          if ( *v3 )
          {
            NCryptFreeObject(*v3);
            *v3 = 0;
          }
        }
      }
      if ( !*v3 )
      {
        v15 = *((_QWORD *)this + 2);
        if ( v15 )
        {
          NCryptFreeObject(v15);
          *((_QWORD *)this + 2) = 0;
        }
      }
      goto LABEL_24;
    }
  }
  return *v3;
}

```

## disassembly

```asm
0x18007c610  push    rbx
0x18007c612  push    rbp
0x18007c613  push    rsi
0x18007c614  push    rdi
0x18007c615  push    r14
0x18007c617  push    r15
0x18007c619  sub     rsp, 38h
0x18007c61d  lea     rdi, [rcx+8]
0x18007c621  mov     r14d, r8d
0x18007c624  cmp     qword ptr [rdi], 0
0x18007c628  mov     r15, rdx
0x18007c62b  mov     rsi, rcx
0x18007c62e  jnz     loc_18007C7B5
0x18007c634  mov     edx, r8d
0x18007c637  mov     rcx, r15
0x18007c63a  call    ScHelperGetKeySpecFromCSPInfo
0x18007c63f  mov     [rsi], eax
0x18007c641  call    ?ScHelperGetKeyName@@YAPEBGPEAEK@Z; ScHelperGetKeyName(uchar *,ulong)
0x18007c646  mov     rbp, rax
0x18007c649  test    rax, rax
0x18007c64c  jz      loc_18007C7B5
0x18007c652  mov     ecx, [rsi]
0x18007c654  dec     ecx
0x18007c656  cmp     ecx, 0FFFFFFFDh
0x18007c659  ja      short loc_18007C688
0x18007c65b  mov     edx, r14d; unsigned int
0x18007c65e  mov     rcx, r15; unsigned __int8 *
0x18007c661  call    ?GetCSPName@@YAPEBGPEAEK@Z; GetCSPName(uchar *,ulong)
0x18007c666  mov     r8, rax; szProvider
0x18007c669  mov     [rsp+68h+dwFlags], 60h ; '`'; dwFlags
0x18007c671  mov     r9d, 1; dwProvType
0x18007c677  mov     rdx, rbp; szContainer
0x18007c67a  mov     rcx, rdi; phProv
0x18007c67d  call    cs:__imp_CryptAcquireContextW
0x18007c683  jmp     loc_18007C7AC
0x18007c688  cmp     byte ptr [rsi+1Ah], 0
0x18007c68c  mov     [rsp+68h+TokenHandle], 0
0x18007c695  jz      short loc_18007C706
0x18007c697  lea     r9, [rsp+68h+TokenHandle]; TokenHandle
0x18007c69c  mov     r8b, 1; OpenAsSelf
0x18007c69f  mov     edx, 0Ch; DesiredAccess
0x18007c6a4  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18007c6ab  call    cs:__imp_NtOpenThreadToken
0x18007c6b1  mov     ebx, eax
0x18007c6b3  mov     edx, 0C000007Ch
0x18007c6b8  mov     eax, 80000000h
0x18007c6bd  lea     ecx, [rbx+rax]
0x18007c6c0  test    eax, ecx
0x18007c6c2  jnz     short loc_18007C6CC
0x18007c6c4  cmp     ebx, edx
0x18007c6c6  jnz     loc_18007C79C
0x18007c6cc  cmp     ebx, edx
0x18007c6ce  jnz     short loc_18007C6DB
0x18007c6d0  mov     [rsp+68h+TokenHandle], 0
0x18007c6d9  jmp     short loc_18007C706
0x18007c6db  xor     edx, edx; Token
0x18007c6dd  xor     ecx, ecx; Thread
0x18007c6df  call    cs:__imp_SetThreadToken
0x18007c6e5  test    eax, eax
0x18007c6e7  jnz     short loc_18007C6FE
0x18007c6e9  call    cs:__imp_GetLastError
0x18007c6ef  mov     ebx, eax
0x18007c6f1  test    eax, eax
0x18007c6f3  jle     short loc_18007C6FE
0x18007c6f5  movzx   ebx, ax
0x18007c6f8  or      ebx, 0C0070000h
0x18007c6fe  test    ebx, ebx
0x18007c700  jnz     loc_18007C79C
0x18007c706  mov     edx, r14d; unsigned int
0x18007c709  mov     rcx, r15; unsigned __int8 *
0x18007c70c  call    ?GetCSPName@@YAPEBGPEAEK@Z; GetCSPName(uchar *,ulong)
0x18007c711  mov     rdx, rax; pszProviderName
0x18007c714  lea     rcx, [rsi+10h]; phProvider
0x18007c718  xor     r8d, r8d; dwFlags
0x18007c71b  call    cs:__imp_NCryptOpenStorageProvider
0x18007c721  test    eax, eax
0x18007c723  js      short loc_18007C74B
0x18007c725  mov     rcx, [rsi+10h]; hProvider
0x18007c729  xor     r9d, r9d; dwLegacyKeySpec
0x18007c72c  mov     r8, rbp; pszKeyName
0x18007c72f  mov     [rsp+68h+dwFlags], 60h ; '`'; dwFlags
0x18007c737  mov     rdx, rdi; phKey
0x18007c73a  call    cs:__imp_NCryptOpenKey
0x18007c740  test    eax, eax
0x18007c742  jns     short loc_18007C74B
0x18007c744  mov     qword ptr [rdi], 0
0x18007c74b  mov     rcx, [rsp+68h+TokenHandle]
0x18007c750  test    rcx, rcx
0x18007c753  jz      short loc_18007C77F
0x18007c755  mov     rdx, rcx; Token
0x18007c758  xor     ecx, ecx; Thread
0x18007c75a  call    cs:__imp_SetThreadToken
0x18007c760  test    eax, eax
0x18007c762  jnz     short loc_18007C77F
0x18007c764  call    cs:__imp_GetLastError
0x18007c76a  mov     rcx, [rdi]; hObject
0x18007c76d  test    rcx, rcx
0x18007c770  jz      short loc_18007C77F
0x18007c772  call    cs:__imp_NCryptFreeObject
0x18007c778  mov     qword ptr [rdi], 0
0x18007c77f  cmp     qword ptr [rdi], 0
0x18007c783  jnz     short loc_18007C79C
0x18007c785  mov     rcx, [rsi+10h]; hObject
0x18007c789  test    rcx, rcx
0x18007c78c  jz      short loc_18007C79C
0x18007c78e  call    cs:__imp_NCryptFreeObject
0x18007c794  mov     qword ptr [rsi+10h], 0
0x18007c79c  mov     rcx, [rsp+68h+TokenHandle]; Handle
0x18007c7a1  test    rcx, rcx
0x18007c7a4  jz      short loc_18007C7AC
0x18007c7a6  call    cs:__imp_NtClose
0x18007c7ac  mov     rcx, rbp; hMem
0x18007c7af  call    cs:__imp_LocalFree
0x18007c7b5  mov     rax, [rdi]
0x18007c7b8  add     rsp, 38h
0x18007c7bc  pop     r15
0x18007c7be  pop     r14
0x18007c7c0  pop     rdi
0x18007c7c1  pop     rsi
0x18007c7c2  pop     rbp
0x18007c7c3  pop     rbx
0x18007c7c4  retn
```
