# CSCLogonInit::CryptCtx(uchar *,ulong)

- ea: `0x180010884`
- end: `0x180010b5b`
- name: `?CryptCtx@CSCLogonInit@@QEAA_KPEAEK@Z`
- size: `727`
- prototype: `unsigned __int64(CSCLogonInit *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180010844`

## callees

- `0x180010884`
- `0x180034e08`
- `0x180071150`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010a5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010afa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010a5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010afa`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180010a54`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180010af0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180010a54`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180010af0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001095b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001095b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010b3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010b3d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180010938`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180010943`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180010938`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180010943`
- `ntdll!NtClose` at `0x180010b34`
- `ntdll!NtClose` at `0x180010b34`
- `ntdll!NtOpenThreadToken` at `0x180010a1e`
- `ntdll!NtOpenThreadToken` at `0x180010a1e`
- `ncrypt!NCryptOpenKey` at `0x180010ad1`
- `ncrypt!NCryptOpenKey` at `0x180010ad1`
- `ncrypt!NCryptOpenStorageProvider` at `0x180010aae`
- `ncrypt!NCryptOpenStorageProvider` at `0x180010aae`
- `ncrypt!NCryptFreeObject` at `0x180010b08`
- `ncrypt!NCryptFreeObject` at `0x180010b1e`
- `ncrypt!NCryptFreeObject` at `0x180010b08`
- `ncrypt!NCryptFreeObject` at `0x180010b1e`
- `CRYPTSP!CryptAcquireContextW` at `0x1800109f1`
- `CRYPTSP!CryptAcquireContextW` at `0x1800109f1`

## pseudocode

```c
HCRYPTPROV __fastcall CSCLogonInit::CryptCtx(CSCLogonInit *this, unsigned __int8 *a2, unsigned int a3)
{
  HCRYPTPROV *v3; // rsi
  unsigned __int8 *v7; // r14
  const WCHAR *v8; // rbp
  const WCHAR *v9; // r15
  __int64 v10; // rbp
  __int64 v11; // r15
  int v12; // ebx
  SIZE_T v13; // rbx
  wchar_t *v14; // rax
  const WCHAR *CSPName; // rax
  WCHAR *v16; // rdi
  unsigned int v17; // ebx
  const WCHAR *v18; // rdx
  signed int LastError; // eax
  __int64 v20; // rdx
  NCRYPT_PROV_HANDLE *v21; // rbx
  const WCHAR *szContainer; // [rsp+70h] [rbp+8h]
  void *TokenHandle; // [rsp+88h] [rbp+20h] BYREF

  v3 = (HCRYPTPROV *)((char *)this + 8);
  if ( *((_QWORD *)this + 1) )
    return *v3;
  if ( a3 >= 0x28 && *(_DWORD *)a2 == a3 && (v7 = a2 + 4, (unsigned int)(*((_DWORD *)a2 + 1) - 1) <= 8) )
  {
    *(_DWORD *)this = *((_DWORD *)a2 + 5);
  }
  else
  {
    *(_DWORD *)this = 1;
    v7 = a2 + 4;
    if ( !a2 )
    {
      v8 = 0;
LABEL_10:
      v9 = 0;
      goto LABEL_20;
    }
  }
  if ( *(_DWORD *)a2 == a3 )
  {
    if ( (unsigned int)(*(_DWORD *)v7 - 1) > 8 )
      v10 = *((unsigned int *)a2 + 5) + 16LL;
    else
      v10 = *((unsigned int *)a2 + 7) + 20LL;
    v8 = (const WCHAR *)&a2[2 * v10];
  }
  else
  {
    v8 = 0;
  }
  if ( *(_DWORD *)a2 != a3 )
    goto LABEL_10;
  if ( (unsigned int)(*(_DWORD *)v7 - 1) > 8 )
    v11 = *((unsigned int *)a2 + 6) + 16LL;
  else
    v11 = *((unsigned int *)a2 + 8) + 20LL;
  v9 = (const WCHAR *)&a2[2 * v11];
LABEL_20:
  v12 = lstrlenW(v9);
  v13 = (unsigned int)(2 * (lstrlenW(v8) + v12) + 20);
  v14 = (wchar_t *)LocalAlloc(0x40u, v13);
  szContainer = v14;
  if ( v14 )
  {
    if ( v8 && *v8 )
      snwprintf_s(v14, v13 >> 1, (v13 >> 1) - 1, L"\\\\.\\%s\\%s", v8, v9);
    else
      snwprintf_s(v14, v13 >> 1, (v13 >> 1) - 1, L"%s", v9);
    if ( (unsigned int)(*(_DWORD *)this - 1) <= 0xFFFFFFFD )
    {
      CSPName = GetCSPName(a2, a3);
      v16 = (WCHAR *)szContainer;
      CryptAcquireContextW(v3, szContainer, CSPName, 1u, 0x60u);
LABEL_56:
      LocalFree(v16);
      return *v3;
    }
    TokenHandle = 0;
    if ( !*((_BYTE *)this + 26) )
      goto LABEL_32;
    v17 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandle);
    if ( (int)(v17 + 0x80000000) < 0 || v17 == -1073741700 )
    {
      if ( v17 == -1073741700 )
      {
        TokenHandle = 0;
LABEL_32:
        if ( a2 && *(_DWORD *)a2 == a3 )
        {
          if ( (unsigned int)(*(_DWORD *)v7 - 1) > 8 )
            v20 = *((unsigned int *)a2 + 7) + 16LL;
          else
            v20 = *((unsigned int *)a2 + 9) + 20LL;
          v18 = (const WCHAR *)&a2[2 * v20];
        }
        else
        {
          v18 = 0;
        }
        v21 = (NCRYPT_PROV_HANDLE *)((char *)this + 16);
        v16 = (WCHAR *)szContainer;
        if ( NCryptOpenStorageProvider((NCRYPT_PROV_HANDLE *)this + 2, v18, 0) >= 0
          && NCryptOpenKey(*v21, v3, szContainer, 0, 0x60u) < 0 )
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
        if ( !*v3 && *v21 )
        {
          NCryptFreeObject(*v21);
          *v21 = 0;
        }
        goto LABEL_54;
      }
      if ( !SetThreadToken(0, 0) )
      {
        LastError = GetLastError();
        v17 = LastError;
        if ( LastError > 0 )
          v17 = (unsigned __int16)LastError | 0xC0070000;
      }
      if ( !v17 )
        goto LABEL_32;
    }
    v16 = (WCHAR *)szContainer;
LABEL_54:
    if ( TokenHandle )
      NtClose(TokenHandle);
    goto LABEL_56;
  }
  return *v3;
}

```

## disassembly

```asm
0x180010884  mov     [rsp+arg_8], rbx
0x180010889  push    rbp
0x18001088a  push    rsi
0x18001088b  push    rdi
0x18001088c  push    r12
0x18001088e  push    r13
0x180010890  push    r14
0x180010892  push    r15
0x180010894  sub     rsp, 30h
0x180010898  lea     rsi, [rcx+8]
0x18001089c  mov     r13, rcx
0x18001089f  xor     ecx, ecx
0x1800108a1  mov     r12d, r8d
0x1800108a4  mov     rdi, rdx
0x1800108a7  cmp     [rsi], rcx
0x1800108aa  jnz     loc_180010B43
0x1800108b0  lea     edx, [rcx+1]
0x1800108b3  cmp     r8d, 28h ; '('
0x1800108b7  jb      short loc_1800108DD
0x1800108b9  cmp     [rdi], r8d
0x1800108bc  jnz     short loc_1800108DD
0x1800108be  lea     r14, [rdi+4]
0x1800108c2  mov     eax, [r14]
0x1800108c5  sub     eax, edx
0x1800108c7  cmp     eax, 8
0x1800108ca  ja      short loc_1800108DD
0x1800108cc  mov     eax, [rdi+14h]
0x1800108cf  mov     [r13+0], eax
0x1800108d3  cmp     [rdi], r12d
0x1800108d6  jz      short loc_1800108F2
0x1800108d8  mov     rbp, rcx
0x1800108db  jmp     short loc_180010910
0x1800108dd  mov     [r13+0], edx
0x1800108e1  lea     r14, [rdi+4]
0x1800108e5  test    rdi, rdi
0x1800108e8  jnz     short loc_1800108D3
0x1800108ea  mov     rbp, rcx
0x1800108ed  mov     r15, rcx
0x1800108f0  jmp     short loc_180010935
0x1800108f2  mov     eax, [r14]
0x1800108f5  sub     eax, edx
0x1800108f7  cmp     eax, 8
0x1800108fa  ja      short loc_180010905
0x1800108fc  mov     ebp, [rdi+1Ch]
0x1800108ff  add     rbp, 14h
0x180010903  jmp     short loc_18001090C
0x180010905  mov     ebp, [rdi+14h]
0x180010908  add     rbp, 10h
0x18001090c  lea     rbp, [rdi+rbp*2]
0x180010910  cmp     [rdi], r12d
0x180010913  jnz     short loc_1800108ED
0x180010915  mov     eax, [r14]
0x180010918  sub     eax, edx
0x18001091a  cmp     eax, 8
0x18001091d  ja      short loc_180010929
0x18001091f  mov     r15d, [rdi+20h]
0x180010923  add     r15, 14h
0x180010927  jmp     short loc_180010931
0x180010929  mov     r15d, [rdi+18h]
0x18001092d  add     r15, 10h
0x180010931  lea     r15, [rdi+r15*2]
0x180010935  mov     rcx, r15; lpString
0x180010938  call    cs:__imp_lstrlenW
0x18001093e  mov     rcx, rbp; lpString
0x180010941  mov     ebx, eax
0x180010943  call    cs:__imp_lstrlenW
0x180010949  add     ebx, eax
0x18001094b  mov     ecx, 40h ; '@'; uFlags
0x180010950  lea     eax, ds:14h[rbx*2]
0x180010957  mov     edx, eax; uBytes
0x180010959  mov     ebx, eax
0x18001095b  call    cs:__imp_LocalAlloc
0x180010961  xor     ecx, ecx
0x180010963  mov     [rsp+68h+szContainer], rax
0x180010968  test    rax, rax
0x18001096b  jz      loc_180010B43
0x180010971  test    rbp, rbp
0x180010974  jz      short loc_1800109A1
0x180010976  cmp     [rbp+0], cx
0x18001097a  jz      short loc_1800109A1
0x18001097c  shr     rbx, 1
0x18001097f  lea     r9, aSS_0; "\\\\.\\%s\\%s"
0x180010986  mov     [rsp+68h+var_40], r15
0x18001098b  mov     rdx, rbx; BufferCount
0x18001098e  mov     rcx, rax; Buffer
0x180010991  mov     qword ptr [rsp+68h+dwFlags], rbp
0x180010996  lea     r8, [rbx-1]; MaxCount
0x18001099a  call    _snwprintf_s
0x18001099f  jmp     short loc_1800109BF
0x1800109a1  shr     rbx, 1
0x1800109a4  lea     r9, aS; "%s"
0x1800109ab  mov     rdx, rbx; BufferCount
0x1800109ae  mov     qword ptr [rsp+68h+dwFlags], r15
0x1800109b3  mov     rcx, rax; Buffer
0x1800109b6  lea     r8, [rbx-1]; MaxCount
0x1800109ba  call    _snwprintf_s
0x1800109bf  mov     eax, [r13+0]
0x1800109c3  dec     eax
0x1800109c5  cmp     eax, 0FFFFFFFDh
0x1800109c8  ja      short loc_1800109FC
0x1800109ca  mov     edx, r12d; unsigned int
0x1800109cd  mov     rcx, rdi; unsigned __int8 *
0x1800109d0  call    ?GetCSPName@@YAPEBGPEAEK@Z; GetCSPName(uchar *,ulong)
0x1800109d5  mov     rdi, [rsp+68h+szContainer]
0x1800109da  mov     r8, rax; szProvider
0x1800109dd  mov     rdx, rdi; szContainer
0x1800109e0  mov     [rsp+68h+dwFlags], 60h ; '`'; dwFlags
0x1800109e8  mov     r9d, 1; dwProvType
0x1800109ee  mov     rcx, rsi; phProv
0x1800109f1  call    cs:__imp_CryptAcquireContextW
0x1800109f7  jmp     loc_180010B3A
0x1800109fc  xor     ebp, ebp
0x1800109fe  mov     [rsp+68h+TokenHandle], rbp
0x180010a06  cmp     [r13+1Ah], bpl
0x180010a0a  jz      short loc_180010A46
0x180010a0c  lea     r9, [rsp+68h+TokenHandle]; TokenHandle
0x180010a14  mov     r8b, 1; OpenAsSelf
0x180010a17  lea     edx, [rbp+0Ch]; DesiredAccess
0x180010a1a  lea     rcx, [rbp-2]; ThreadHandle
0x180010a1e  call    cs:__imp_NtOpenThreadToken
0x180010a24  mov     ecx, 80000000h
0x180010a29  mov     edx, 0C000007Ch
0x180010a2e  mov     ebx, eax
0x180010a30  add     eax, ecx
0x180010a32  test    ecx, eax
0x180010a34  jnz     short loc_180010A3A
0x180010a36  cmp     ebx, edx
0x180010a38  jnz     short loc_180010A77
0x180010a3a  cmp     ebx, edx
0x180010a3c  jnz     short loc_180010A50
0x180010a3e  mov     [rsp+68h+TokenHandle], rbp
0x180010a46  test    rdi, rdi
0x180010a49  jnz     short loc_180010A81
0x180010a4b  mov     rdx, rbp
0x180010a4e  jmp     short loc_180010AA4
0x180010a50  xor     edx, edx; Token
0x180010a52  xor     ecx, ecx; Thread
0x180010a54  call    cs:__imp_SetThreadToken
0x180010a5a  test    eax, eax
0x180010a5c  jnz     short loc_180010A73
0x180010a5e  call    cs:__imp_GetLastError
0x180010a64  mov     ebx, eax
0x180010a66  test    eax, eax
0x180010a68  jle     short loc_180010A73
0x180010a6a  movzx   ebx, ax
0x180010a6d  or      ebx, 0C0070000h
0x180010a73  test    ebx, ebx
0x180010a75  jz      short loc_180010A46
0x180010a77  mov     rdi, [rsp+68h+szContainer]
0x180010a7c  jmp     loc_180010B27
0x180010a81  cmp     [rdi], r12d
0x180010a84  jnz     short loc_180010A4B
0x180010a86  mov     eax, [r14]
0x180010a89  dec     eax
0x180010a8b  cmp     eax, 8
0x180010a8e  ja      short loc_180010A99
0x180010a90  mov     edx, [rdi+24h]
0x180010a93  add     rdx, 14h
0x180010a97  jmp     short loc_180010AA0
0x180010a99  mov     edx, [rdi+1Ch]
0x180010a9c  add     rdx, 10h
0x180010aa0  lea     rdx, [rdi+rdx*2]; pszProviderName
0x180010aa4  lea     rbx, [r13+10h]
0x180010aa8  xor     r8d, r8d; dwFlags
0x180010aab  mov     rcx, rbx; phProvider
0x180010aae  call    cs:__imp_NCryptOpenStorageProvider
0x180010ab4  mov     rdi, [rsp+68h+szContainer]
0x180010ab9  test    eax, eax
0x180010abb  js      short loc_180010ADE
0x180010abd  mov     rcx, [rbx]; hProvider
0x180010ac0  xor     r9d, r9d; dwLegacyKeySpec
0x180010ac3  mov     r8, rdi; pszKeyName
0x180010ac6  mov     [rsp+68h+dwFlags], 60h ; '`'; dwFlags
0x180010ace  mov     rdx, rsi; phKey
0x180010ad1  call    cs:__imp_NCryptOpenKey
0x180010ad7  test    eax, eax
0x180010ad9  jns     short loc_180010ADE
0x180010adb  mov     [rsi], rbp
0x180010ade  mov     rcx, [rsp+68h+TokenHandle]
0x180010ae6  test    rcx, rcx
0x180010ae9  jz      short loc_180010B11
0x180010aeb  mov     rdx, rcx; Token
0x180010aee  xor     ecx, ecx; Thread
0x180010af0  call    cs:__imp_SetThreadToken
0x180010af6  test    eax, eax
0x180010af8  jnz     short loc_180010B11
0x180010afa  call    cs:__imp_GetLastError
0x180010b00  mov     rcx, [rsi]; hObject
0x180010b03  test    rcx, rcx
0x180010b06  jz      short loc_180010B11
0x180010b08  call    cs:__imp_NCryptFreeObject
0x180010b0e  mov     [rsi], rbp
0x180010b11  cmp     [rsi], rbp
0x180010b14  jnz     short loc_180010B27
0x180010b16  mov     rcx, [rbx]; hObject
0x180010b19  test    rcx, rcx
0x180010b1c  jz      short loc_180010B27
0x180010b1e  call    cs:__imp_NCryptFreeObject
0x180010b24  mov     [rbx], rbp
0x180010b27  mov     rcx, [rsp+68h+TokenHandle]; Handle
0x180010b2f  test    rcx, rcx
0x180010b32  jz      short loc_180010B3A
0x180010b34  call    cs:__imp_NtClose
0x180010b3a  mov     rcx, rdi; hMem
0x180010b3d  call    cs:__imp_LocalFree
0x180010b43  mov     rax, [rsi]
0x180010b46  mov     rbx, [rsp+68h+arg_8]
0x180010b4b  add     rsp, 30h
0x180010b4f  pop     r15
0x180010b51  pop     r14
0x180010b53  pop     r13
0x180010b55  pop     r12
0x180010b57  pop     rdi
0x180010b58  pop     rsi
0x180010b59  pop     rbp
0x180010b5a  retn
```
