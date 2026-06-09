# ValidateAutoUpdateCabPreFetchContent

- ea: `0x180008df0`
- end: `0x180009029`
- name: `ValidateAutoUpdateCabPreFetchContent`
- size: `569`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180003c90`

## callees

- `0x180002220`
- `0x180004180`
- `0x1800068b0`
- `0x180007980`
- `0x180007dc0`
- `0x180008df0`
- `0x180009428`
- `0x1800174f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e4d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fa7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008faf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008faf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008e43`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008e43`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180008e6b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180008e6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008e25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008e25`
- `CRYPT32!I_CertSrvProtectFunction` at `0x180008f1b`
- `CRYPT32!I_CertSrvProtectFunction` at `0x180008f1b`

## pseudocode

```c
__int64 __fastcall ValidateAutoUpdateCabPreFetchContent(__int64 a1)
{
  void **v1; // rax
  int v2; // ebp
  int v3; // r13d
  const void *v5; // r12
  int v6; // r14d
  void *v7; // rsi
  HANDLE CurrentThread; // rax
  unsigned int v9; // edi
  DWORD LastError; // eax
  void *v11; // r15
  _QWORD *CryptBlobArray; // rax
  void *v13; // rsi
  __int64 v14; // rax
  const void *v16; // r15
  size_t v17; // rbp
  DWORD v18; // ecx
  int *v19; // rax
  unsigned int *v20; // r15
  int v21; // eax
  _DWORD v22[2]; // [rsp+50h] [rbp-58h] BYREF
  const void *v23; // [rsp+58h] [rbp-50h]
  void *TokenHandle; // [rsp+B0h] [rbp+8h] BYREF

  v1 = *(void ***)(a1 + 128);
  v2 = 0;
  v3 = *(_DWORD *)(a1 + 140);
  v5 = 0;
  TokenHandle = 0;
  v6 = 0;
  v7 = *v1;
  CurrentThread = GetCurrentThread();
  v9 = 1;
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle)
    || (LastError = GetLastError(), TokenHandle = 0, LastError == 1008) )
  {
    if ( SetThreadToken(0, v7) )
    {
      v11 = TokenHandle;
      v2 = 1;
      goto LABEL_5;
    }
    LastError = GetLastError();
  }
  SetLastError(LastError);
  v11 = TokenHandle;
  if ( TokenHandle )
  {
    I_UrlCacheCloseHandle(TokenHandle);
    v11 = 0;
    TokenHandle = 0;
  }
LABEL_5:
  CryptBlobArray = I_UrlCacheReadCryptBlobArray(
                     *(_WORD **)(*(_QWORD *)(a1 + 48) + 32LL),
                     *(void **)(a1 + 80),
                     *(_QWORD *)(a1 + 72));
  v13 = CryptBlobArray;
  if ( CryptBlobArray )
  {
    if ( *(_DWORD *)CryptBlobArray )
    {
      v19 = (int *)CryptBlobArray[1];
      if ( *v19 )
      {
        v5 = (const void *)*((_QWORD *)v19 + 1);
        v6 = *v19;
      }
    }
  }
  if ( v2 )
    RestoreToken(v11);
  v14 = *(_QWORD *)(a1 + 216);
  if ( !v14 || !*(_DWORD *)v14 || (v20 = *(unsigned int **)(v14 + 8), v17 = *v20, !(_DWORD)v17) )
  {
    if ( !v6 )
    {
LABEL_10:
      v9 = -1;
      goto LABEL_11;
    }
    v16 = v5;
    LODWORD(v17) = v6;
    goto LABEL_13;
  }
  v16 = (const void *)*((_QWORD *)v20 + 1);
  if ( v6 == (_DWORD)v17 && !memcmp_0(v16, v5, v17) )
LABEL_13:
    v9 = 0;
  v18 = I_CertSrvProtectFunction(0);
  if ( v18 )
  {
    if ( v3 == 7 )
    {
      v21 = 256;
      v22[1] = 0;
      v23 = v16;
      if ( (unsigned int)v17 < 0x100 )
        v21 = v17;
      v22[0] = v21;
      SetPinRulesLastError(v18, 0, (__int64)v22);
    }
    goto LABEL_10;
  }
  TokenHandle = 0;
  if ( (unsigned int)I_CertGetAutoUpdateLastSyncTime(v3, (BYTE *)&TokenHandle) )
    *(_QWORD *)(a1 + 232) = TokenHandle;
LABEL_11:
  PkiFree(v13);
  return v9;
}

```

## disassembly

```asm
0x180008df0  push    rbx
0x180008df2  push    rbp
0x180008df3  push    rsi
0x180008df4  push    rdi
0x180008df5  push    r12
0x180008df7  push    r13
0x180008df9  push    r14
0x180008dfb  push    r15
0x180008dfd  sub     rsp, 68h
0x180008e01  mov     rax, [rcx+80h]
0x180008e08  xor     ebp, ebp
0x180008e0a  mov     r13d, [rcx+8Ch]
0x180008e11  mov     rbx, rcx
0x180008e14  mov     r12d, ebp
0x180008e17  mov     [rsp+0A8h+TokenHandle], rbp
0x180008e1f  mov     r14d, ebp
0x180008e22  mov     rsi, [rax]
0x180008e25  call    cs:__imp_GetCurrentThread
0x180008e2b  mov     edi, 1
0x180008e30  lea     r9, [rsp+0A8h+TokenHandle]; TokenHandle
0x180008e38  mov     rcx, rax; ThreadHandle
0x180008e3b  mov     r8d, edi; OpenAsSelf
0x180008e3e  mov     edx, 0Ch; DesiredAccess
0x180008e43  call    cs:__imp_OpenThreadToken
0x180008e49  test    eax, eax
0x180008e4b  jnz     short loc_180008E66
0x180008e4d  call    cs:__imp_GetLastError
0x180008e53  mov     [rsp+0A8h+TokenHandle], rbp
0x180008e5b  cmp     eax, 3F0h
0x180008e60  jnz     loc_180008FAD
0x180008e66  mov     rdx, rsi; Token
0x180008e69  xor     ecx, ecx; Thread
0x180008e6b  call    cs:__imp_SetThreadToken
0x180008e71  test    eax, eax
0x180008e73  jz      loc_180008FA7
0x180008e79  mov     r15, [rsp+0A8h+TokenHandle]
0x180008e81  mov     ebp, edi
0x180008e83  mov     rcx, [rbx+30h]
0x180008e87  mov     r8, [rbx+48h]
0x180008e8b  mov     rdx, [rbx+50h]
0x180008e8f  mov     rcx, [rcx+20h]; Src
0x180008e93  call    I_UrlCacheReadCryptBlobArray
0x180008e98  mov     rsi, rax
0x180008e9b  test    rax, rax
0x180008e9e  jnz     loc_180008F5B
0x180008ea4  test    ebp, ebp
0x180008ea6  jz      short loc_180008EB0
0x180008ea8  mov     rcx, r15; hObject
0x180008eab  call    ?RestoreToken@@YAXPEAX@Z; RestoreToken(void *)
0x180008eb0  mov     rax, [rbx+0D8h]
0x180008eb7  test    rax, rax
0x180008eba  jnz     loc_180008F7E
0x180008ec0  test    r14d, r14d
0x180008ec3  jnz     short loc_180008EE5
0x180008ec5  mov     edi, 0FFFFFFFFh
0x180008eca  mov     rcx, rsi; hMem
0x180008ecd  call    PkiFree
0x180008ed2  mov     eax, edi
0x180008ed4  add     rsp, 68h
0x180008ed8  pop     r15
0x180008eda  pop     r14
0x180008edc  pop     r13
0x180008ede  pop     r12
0x180008ee0  pop     rdi
0x180008ee1  pop     rsi
0x180008ee2  pop     rbp
0x180008ee3  pop     rbx
0x180008ee4  retn
0x180008ee5  mov     r15, r12
0x180008ee8  mov     ebp, r14d
0x180008eeb  xor     r14d, r14d
0x180008eee  mov     edi, r14d
0x180008ef1  mov     [rsp+0A8h+var_60], r14
0x180008ef6  xor     r9d, r9d
0x180008ef9  mov     [rsp+0A8h+var_68], r14
0x180008efe  mov     r8d, r13d
0x180008f01  mov     [rsp+0A8h+var_70], r14
0x180008f06  mov     edx, 0Dh
0x180008f0b  mov     [rsp+0A8h+var_78], r14
0x180008f10  xor     ecx, ecx
0x180008f12  mov     [rsp+0A8h+var_80], ebp
0x180008f16  mov     [rsp+0A8h+var_88], r15
0x180008f1b  call    cs:__imp_I_CertSrvProtectFunction
0x180008f21  mov     ecx, eax
0x180008f23  test    eax, eax
0x180008f25  jnz     loc_180008FF6
0x180008f2b  lea     rdx, [rsp+0A8h+TokenHandle]
0x180008f33  mov     [rsp+0A8h+TokenHandle], r14
0x180008f3b  mov     ecx, r13d
0x180008f3e  call    I_CertGetAutoUpdateLastSyncTime
0x180008f43  test    eax, eax
0x180008f45  jz      short loc_180008ECA
0x180008f47  mov     rax, [rsp+0A8h+TokenHandle]
0x180008f4f  mov     [rbx+0E8h], rax
0x180008f56  jmp     loc_180008ECA
0x180008f5b  cmp     [rax], r12d
0x180008f5e  jz      loc_180008EA4
0x180008f64  mov     rax, [rax+8]
0x180008f68  mov     ecx, [rax]
0x180008f6a  test    ecx, ecx
0x180008f6c  jz      loc_180008EA4
0x180008f72  mov     r12, [rax+8]
0x180008f76  mov     r14d, ecx
0x180008f79  jmp     loc_180008EA4
0x180008f7e  cmp     dword ptr [rax], 0
0x180008f81  jz      loc_180008EC0
0x180008f87  mov     r15, [rax+8]
0x180008f8b  mov     ebp, [r15]
0x180008f8e  test    ebp, ebp
0x180008f90  jz      loc_180008EC0
0x180008f96  mov     r15, [r15+8]
0x180008f9a  cmp     r14d, ebp
0x180008f9d  jz      short loc_180008FDE
0x180008f9f  xor     r14d, r14d
0x180008fa2  jmp     loc_180008EF1
0x180008fa7  call    cs:__imp_GetLastError
0x180008fad  mov     ecx, eax; dwErrCode
0x180008faf  call    cs:__imp_SetLastError
0x180008fb5  mov     r15, [rsp+0A8h+TokenHandle]
0x180008fbd  test    r15, r15
0x180008fc0  jz      loc_180008E83
0x180008fc6  mov     rcx, r15; hObject
0x180008fc9  call    I_UrlCacheCloseHandle
0x180008fce  mov     r15, rbp
0x180008fd1  mov     [rsp+0A8h+TokenHandle], rbp
0x180008fd9  jmp     loc_180008E83
0x180008fde  mov     r8, rbp; Size
0x180008fe1  mov     rdx, r12; Buf2
0x180008fe4  mov     rcx, r15; Buf1
0x180008fe7  call    memcmp_0
0x180008fec  test    eax, eax
0x180008fee  jz      loc_180008EEB
0x180008ff4  jmp     short loc_180008F9F
0x180008ff6  cmp     r13d, 7
0x180008ffa  jnz     loc_180008EC5
0x180009000  mov     eax, 100h
0x180009005  mov     [rsp+0A8h+var_54], r14d
0x18000900a  cmp     ebp, eax
0x18000900c  mov     [rsp+0A8h+var_50], r15
0x180009011  lea     r8, [rsp+0A8h+var_58]
0x180009016  cmovb   eax, ebp
0x180009019  xor     edx, edx
0x18000901b  mov     [rsp+0A8h+var_58], eax
0x18000901f  call    _SetPinRulesLastError
0x180009024  jmp     loc_180008EC5
```
