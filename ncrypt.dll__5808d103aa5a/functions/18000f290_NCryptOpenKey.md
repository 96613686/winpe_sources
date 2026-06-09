# NCryptOpenKey

- ea: `0x18000f290`
- end: `0x18000f5ba`
- name: `NCryptOpenKey`
- size: `810`
- prototype: `SECURITY_STATUS __stdcall(NCRYPT_PROV_HANDLE hProvider, NCRYPT_KEY_HANDLE *phKey, LPCWSTR pszKeyName, DWORD dwLegacyKeySpec, DWORD dwFlags)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18000fb20`

## callees

- `0x180009cd0`
- `0x18000a770`
- `0x18000c8e0`
- `0x18000cb50`
- `0x18000d02c`
- `0x18000e120`
- `0x18000f290`
- `0x18000f6f0`
- `0x180019b84`
- `0x18001f15d`
- `0x18001f175`
- `0x180020010`

## string_xrefs

- `0x18000f2ee`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x18000f35b`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x18000f4bf`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x18000f536`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x18000f58a`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x18000f47f`: `NCryptOpenKey`

## pseudocode

```c
SECURITY_STATUS __stdcall NCryptOpenKey(
        NCRYPT_PROV_HANDLE hProvider,
        NCRYPT_KEY_HANDLE *phKey,
        LPCWSTR pszKeyName,
        DWORD dwLegacyKeySpec,
        DWORD dwFlags)
{
  PVOID *v8; // rcx
  unsigned int v9; // esi
  unsigned int v10; // esi
  __int64 v11; // rax
  void *v14; // rax
  int v15; // edx
  NCRYPT_KEY_HANDLE v16; // r14
  unsigned int v17; // eax
  __int64 v18; // rcx
  _BYTE *v19; // rax

  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_PSDD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)phKey,
      (_DWORD)pszKeyName,
      hProvider,
      (__int64)pszKeyName,
      dwLegacyKeySpec,
      dwFlags);
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( phKey )
  {
    if ( hProvider && *(_DWORD *)hProvider == 1145307137 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(hProvider + 4));
      v10 = 0;
      if ( pszKeyName )
      {
        v11 = -1;
        while ( pszKeyName[++v11] != 0 )
          ;
        v10 = 2 * v11 + 2;
      }
      if ( v10 < 0xFFFFFFD0 )
      {
        v14 = (void *)SafeAllocaAllocateFromHeap(v10 + 48);
        v16 = (NCRYPT_KEY_HANDLE)v14;
        if ( v14 )
        {
          memset_0(v14, 0, v10 + 48);
          *(_DWORD *)v16 = 1145307138;
          *(_QWORD *)(v16 + 8) = hProvider;
          if ( v10 <= 1 )
          {
            *(_QWORD *)(v16 + 24) = 0;
          }
          else
          {
            *(_QWORD *)(v16 + 24) = v16 + 48;
            memcpy_0((void *)(v16 + 48), pszKeyName, v10);
          }
          while ( 1 )
          {
            v17 = (*(__int64 (__fastcall **)(_QWORD, NCRYPT_KEY_HANDLE, LPCWSTR, _QWORD, DWORD))(hProvider + 32))(
                    *(_QWORD *)(hProvider + 272),
                    v16 + 16,
                    pszKeyName,
                    dwLegacyKeySpec,
                    dwFlags);
            v9 = v17;
            if ( v17 != -2146893778 )
              break;
            if ( (dwFlags & 0x40) != 0 )
            {
              v9 = -2146893790;
              goto LABEL_30;
            }
            v9 = (*(__int64 (__fastcall **)(_QWORD, NCRYPT_KEY_HANDLE, const wchar_t *, _QWORD))(hProvider + 192))(
                   *(_QWORD *)(hProvider + 272),
                   v16,
                   L"NCryptOpenKey",
                   0);
            if ( v9 )
              goto LABEL_26;
          }
          if ( !v17 )
          {
            *phKey = v16;
            return NormalizeNteStatus(v9, phKey, pszKeyName, dwLegacyKeySpec, dwFlags);
          }
LABEL_26:
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (_DWORD)phKey,
              (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
              (unsigned int)"Status",
              v9,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
              137);
          EtwLogNCryptOpenKeyFailed(*(_QWORD *)(hProvider + 280), pszKeyName, v9);
LABEL_30:
          v18 = 48;
          v19 = (_BYTE *)v16;
          do
          {
            *v19++ = 0;
            --v18;
          }
          while ( v18 );
          MSCryptFree(v16);
        }
        else
        {
          v9 = -2146893810;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v15,
              (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
              (unsigned int)"Status",
              14,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
              81);
        }
      }
      else
      {
        v9 = -1073741675;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (_DWORD)phKey,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
            (unsigned int)"Status",
            149,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
            72);
      }
      DereferenceProvider(hProvider);
    }
    else
    {
      v9 = -2146893786;
      DebugTraceError(
        2148073510LL,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
        1081);
    }
  }
  else
  {
    v9 = -2146893785;
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        (unsigned int)v8[2],
        (_DWORD)phKey,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
        48);
  }
  return NormalizeNteStatus(v9, phKey, pszKeyName, dwLegacyKeySpec, dwFlags);
}

```

## disassembly

```asm
0x18000f290  mov     [rsp+arg_18], r9d
0x18000f295  push    rbx
0x18000f296  push    rsi
0x18000f297  push    rdi
0x18000f298  push    r12
0x18000f29a  push    r15
0x18000f29c  sub     rsp, 40h
0x18000f2a0  mov     rbx, r8
0x18000f2a3  mov     r15, rdx
0x18000f2a6  mov     rdi, rcx
0x18000f2a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f2b0  lea     r12, WPP_GLOBAL_Control
0x18000f2b7  cmp     rcx, r12
0x18000f2ba  jnz     loc_18000F433
0x18000f2c0  mov     [rsp+68h+arg_0], rbp
0x18000f2c5  mov     [rsp+68h+arg_8], r13
0x18000f2ca  mov     [rsp+68h+arg_10], r14
0x18000f2d2  test    r15, r15
0x18000f2d5  jz      loc_18000F51A
0x18000f2db  test    rdi, rdi
0x18000f2de  jz      short loc_18000F2E8
0x18000f2e0  cmp     dword ptr [rdi], 44440001h
0x18000f2e6  jz      short loc_18000F310
0x18000f2e8  mov     r9d, 439h
0x18000f2ee  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f2f5  lea     rdx, aStatus; "Status"
0x18000f2fc  mov     ecx, 80090026h
0x18000f301  mov     esi, 80090026h
0x18000f306  call    DebugTraceError
0x18000f30b  jmp     loc_18000F387
0x18000f310  lock inc dword ptr [rdi+4]
0x18000f314  xor     esi, esi
0x18000f316  test    rbx, rbx
0x18000f319  jz      short loc_18000F334
0x18000f31b  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000f322  cmp     [rbx+rax*2+2], si
0x18000f327  lea     rax, [rax+1]
0x18000f32b  jnz     short loc_18000F322
0x18000f32d  lea     esi, ds:2[rax*2]
0x18000f334  lea     eax, [rsi+30h]
0x18000f337  cmp     eax, 30h ; '0'
0x18000f33a  jnb     short loc_18000F3AB
0x18000f33c  mov     esi, 0C0000095h
0x18000f341  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f348  cmp     rcx, r12
0x18000f34b  jz      short loc_18000F37F
0x18000f34d  test    byte ptr [rcx+1Ch], 1
0x18000f351  jz      short loc_18000F37F
0x18000f353  mov     [rsp+68h+var_38], 448h
0x18000f35b  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f362  mov     [rsp+68h+var_40], r8
0x18000f367  mov     dword ptr [rsp+68h+var_48], 0C0000095h
0x18000f36f  mov     rcx, [rcx+10h]
0x18000f373  lea     r9, aStatus; "Status"
0x18000f37a  call    WPP_SF_sDsd
0x18000f37f  mov     rcx, rdi
0x18000f382  call    DereferenceProvider
0x18000f387  mov     ecx, esi
0x18000f389  mov     r14, [rsp+68h+arg_10]
0x18000f391  mov     r13, [rsp+68h+arg_8]
0x18000f396  mov     rbp, [rsp+68h+arg_0]
0x18000f39b  add     rsp, 40h
0x18000f39f  pop     r15
0x18000f3a1  pop     r12
0x18000f3a3  pop     rdi
0x18000f3a4  pop     rsi
0x18000f3a5  pop     rbx
0x18000f3a6  jmp     NormalizeNteStatus
0x18000f3ab  mov     ecx, eax
0x18000f3ad  mov     ebp, eax
0x18000f3af  call    SafeAllocaAllocateFromHeap
0x18000f3b4  mov     r14, rax
0x18000f3b7  test    rax, rax
0x18000f3ba  jz      loc_18000F563
0x18000f3c0  mov     r8d, ebp; Size
0x18000f3c3  xor     edx, edx; Val
0x18000f3c5  mov     rcx, rax; void *
0x18000f3c8  call    memset_0
0x18000f3cd  mov     dword ptr [r14], 44440002h
0x18000f3d4  mov     [r14+8], rdi
0x18000f3d8  cmp     esi, 1
0x18000f3db  jbe     loc_18000F5A3
0x18000f3e1  lea     rcx, [r14+30h]; void *
0x18000f3e5  mov     r8d, esi; Size
0x18000f3e8  mov     rdx, rbx; Src
0x18000f3eb  mov     [r14+18h], rcx
0x18000f3ef  call    memcpy_0
0x18000f3f4  mov     eax, [rsp+68h+dwFlags]
0x18000f3fb  lea     rdx, [r14+10h]
0x18000f3ff  mov     r9d, [rsp+68h+arg_18]
0x18000f407  mov     r8, rbx
0x18000f40a  mov     rcx, [rdi+110h]
0x18000f411  mov     dword ptr [rsp+68h+var_48], eax
0x18000f415  mov     rax, [rdi+20h]
0x18000f419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f41e  mov     esi, eax
0x18000f420  cmp     eax, 8009002Eh
0x18000f425  jz      short loc_18000F46A
0x18000f427  test    eax, eax
0x18000f429  jnz     short loc_18000F4A2
0x18000f42b  mov     [r15], r14
0x18000f42e  jmp     loc_18000F387
0x18000f433  test    byte ptr [rcx+1Ch], 4
0x18000f437  jz      loc_18000F2C0
0x18000f43d  mov     eax, [rsp+68h+dwFlags]
0x18000f444  mov     rcx, [rcx+10h]
0x18000f448  mov     [rsp+68h+var_38], eax
0x18000f44c  mov     dword ptr [rsp+68h+var_40], r9d
0x18000f451  mov     r9, rdi
0x18000f454  mov     [rsp+68h+var_48], rbx
0x18000f459  call    WPP_SF_PSDD
0x18000f45e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f465  jmp     loc_18000F2C0
0x18000f46a  test    byte ptr [rsp+68h+dwFlags], 40h
0x18000f472  jnz     loc_18000F5B0
0x18000f478  mov     rcx, [rdi+110h]
0x18000f47f  lea     r8, aNcryptopenkey_0; "NCryptOpenKey"
0x18000f486  mov     rax, [rdi+0C0h]
0x18000f48d  xor     r9d, r9d
0x18000f490  mov     rdx, r14
0x18000f493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f498  mov     esi, eax
0x18000f49a  test    eax, eax
0x18000f49c  jz      loc_18000F3F4
0x18000f4a2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f4a9  lea     rax, WPP_GLOBAL_Control
0x18000f4b0  cmp     rcx, rax
0x18000f4b3  jz      short loc_18000F4E3
0x18000f4b5  test    byte ptr [rcx+1Ch], 1
0x18000f4b9  jz      short loc_18000F4E3
0x18000f4bb  mov     rcx, [rcx+10h]
0x18000f4bf  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f4c6  mov     [rsp+68h+var_38], 489h
0x18000f4ce  lea     r9, aStatus; "Status"
0x18000f4d5  mov     [rsp+68h+var_40], r8
0x18000f4da  mov     dword ptr [rsp+68h+var_48], esi
0x18000f4de  call    WPP_SF_sDsd
0x18000f4e3  mov     rcx, [rdi+118h]
0x18000f4ea  mov     r8d, esi
0x18000f4ed  mov     rdx, rbx
0x18000f4f0  call    EtwLogNCryptOpenKeyFailed
0x18000f4f5  mov     ecx, 30h ; '0'
0x18000f4fa  mov     rax, r14
0x18000f4fd  nop     dword ptr [rax]
0x18000f500  mov     byte ptr [rax], 0
0x18000f503  lea     rax, [rax+1]
0x18000f507  sub     rcx, 1
0x18000f50b  jnz     short loc_18000F500
0x18000f50d  mov     rcx, r14
0x18000f510  call    MSCryptFree
0x18000f515  jmp     loc_18000F37F
0x18000f51a  mov     esi, 80090027h
0x18000f51f  cmp     rcx, r12
0x18000f522  jz      loc_18000F387
0x18000f528  test    byte ptr [rcx+1Ch], 1
0x18000f52c  jz      loc_18000F387
0x18000f532  mov     rcx, [rcx+10h]
0x18000f536  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f53d  mov     [rsp+68h+var_38], 430h
0x18000f545  lea     r9, aStatus; "Status"
0x18000f54c  mov     [rsp+68h+var_40], r8
0x18000f551  mov     dword ptr [rsp+68h+var_48], 80090027h
0x18000f559  call    WPP_SF_sDsd
0x18000f55e  jmp     loc_18000F387
0x18000f563  mov     esi, 8009000Eh
0x18000f568  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f56f  cmp     rcx, r12
0x18000f572  jz      loc_18000F37F
0x18000f578  test    byte ptr [rcx+1Ch], 1
0x18000f57c  jz      loc_18000F37F
0x18000f582  mov     [rsp+68h+var_38], 451h
0x18000f58a  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000f591  mov     [rsp+68h+var_40], r8
0x18000f596  mov     dword ptr [rsp+68h+var_48], 8009000Eh
0x18000f59e  jmp     loc_18000F36F
0x18000f5a3  mov     qword ptr [r14+18h], 0
0x18000f5ab  jmp     loc_18000F3F4
0x18000f5b0  mov     esi, 80090022h
0x18000f5b5  jmp     loc_18000F4F5
```
