# NCryptEnumKeys

- ea: `0x180011950`
- end: `0x180011ca9`
- name: `NCryptEnumKeys`
- size: `857`
- prototype: `SECURITY_STATUS __stdcall(NCRYPT_PROV_HANDLE hProvider, LPCWSTR pszScope, NCryptKeyName **ppKeyName, PVOID *ppEnumState, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `11`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x180009cd0`
- `0x18000a670`
- `0x18000a770`
- `0x18000c8e0`
- `0x18000cb50`
- `0x18000d02c`
- `0x18000e120`
- `0x180011950`
- `0x180011cb0`
- `0x180011cd0`
- `0x180020010`

## string_xrefs

- `0x180011ae9`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x180011b84`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x180011c21`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x180011c63`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x180011c7a`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`

## pseudocode

```c
SECURITY_STATUS __stdcall NCryptEnumKeys(
        NCRYPT_PROV_HANDLE hProvider,
        LPCWSTR pszScope,
        NCryptKeyName **ppKeyName,
        PVOID *ppEnumState,
        DWORD dwFlags)
{
  __int64 *v5; // rdi
  __int64 v9; // rbp
  __int64 v10; // rcx
  __int64 v11; // rax
  NCRYPT_KEY_HANDLE *v12; // rdx
  NCryptKeyName **v13; // r8
  PVOID *v14; // r9
  __int64 v15; // r15
  __int64 *v16; // rax
  __int64 *v17; // rsi
  unsigned int v18; // eax
  int v19; // edx
  int v20; // r8d
  unsigned int v21; // ebx
  __int64 *v23; // rax
  __int64 v24; // r9
  __int64 v25; // rcx
  PVOID v26[11]; // [rsp+40h] [rbp-58h] BYREF

  v5 = 0;
  v26[0] = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_PSD(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, (_DWORD)ppKeyName, hProvider, (__int64)pszScope, dwFlags);
  v9 = ValidateAndReferenceProvider(hProvider);
  v11 = ValidateAndReferenceProvider(v10);
  v15 = v11;
  if ( !v9 || !v11 )
  {
    v21 = -2146893786;
    if ( WPP_GLOBAL_Control != v12 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)v12,
        (_DWORD)v13,
        (unsigned int)"Status",
        38,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
        3);
    if ( !v9 )
      goto LABEL_24;
    goto LABEL_35;
  }
  if ( ppKeyName && ppEnumState )
  {
    v26[0] = *ppEnumState;
    if ( v26[0] )
      goto LABEL_9;
    v23 = (__int64 *)SafeAllocaAllocateFromHeap(32);
    v5 = v23;
    if ( v23 )
    {
      *(_OWORD *)v23 = 0;
      *((_OWORD *)v23 + 1) = 0;
LABEL_9:
      v16 = (__int64 *)SafeAllocaAllocateFromHeap(32);
      v17 = v16;
      if ( !v16 )
      {
        v21 = -2146893810;
        DebugTraceError(
          2148073486LL,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
          2863);
        goto LABEL_31;
      }
      *(_OWORD *)v16 = 0;
      *((_OWORD *)v16 + 1) = 0;
      while ( 1 )
      {
        v18 = (*(__int64 (__fastcall **)(_QWORD, LPCWSTR, NCryptKeyName **, PVOID *, DWORD))(v9 + 152))(
                *(_QWORD *)(v9 + 272),
                pszScope,
                ppKeyName,
                v26,
                dwFlags);
        v21 = v18;
        if ( v18 != -2146893778 )
        {
          if ( v18 )
          {
LABEL_28:
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sDsd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v19,
                v20,
                (unsigned int)"Status",
                v21,
                (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
                89);
            goto LABEL_31;
          }
          if ( v5 )
          {
            v5[1] = (__int64)v26[0];
            *v5 = v9;
            MSCryptAddMemoryBuffer(KspRouterBufferList, v5);
          }
          else if ( v26[0] != *ppEnumState )
          {
            v21 = -2146893792;
            goto LABEL_34;
          }
          v17[1] = (__int64)*ppKeyName;
          *v17 = v15;
          MSCryptAddMemoryBuffer(KspRouterBufferList, v17);
          v21 = 0;
          *ppEnumState = v26[0];
          goto LABEL_16;
        }
        if ( (dwFlags & 0x40) != 0 )
          break;
        v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const wchar_t *, _QWORD))(v9 + 192))(
                *(_QWORD *)(v9 + 272),
                0,
                L"NCryptEnumKeys",
                0);
        if ( v21 )
          goto LABEL_28;
      }
      v21 = -2146893790;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v19,
          v20,
          (unsigned int)"Status",
          34,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
          71);
LABEL_31:
      if ( v5 )
        MSCryptFree(v5);
      if ( v17 )
LABEL_34:
        MSCryptFree(v17);
      goto LABEL_35;
    }
    v21 = -2146893810;
    v24 = 2846;
    v25 = 2148073486LL;
  }
  else
  {
    v21 = -2146893785;
    v24 = 2826;
    v25 = 2148073511LL;
  }
  DebugTraceError(v25, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", v24);
LABEL_35:
  DereferenceProvider(v9);
LABEL_24:
  if ( v15 )
    DereferenceProvider(v15);
LABEL_16:
  if ( !v5 && !v21 )
    DereferenceProvider(v9);
  return NormalizeNteStatus(v21, v12, v13, v14, dwFlags);
}

```

## disassembly

```asm
0x180011950  mov     r11, rsp
0x180011953  mov     [r11+10h], rdx
0x180011957  push    rbx
0x180011958  push    rbp
0x180011959  push    rsi
0x18001195a  push    rdi
0x18001195b  push    r12
0x18001195d  push    r13
0x18001195f  push    r14
0x180011961  push    r15
0x180011963  sub     rsp, 58h
0x180011967  xor     edi, edi
0x180011969  mov     r14, r9
0x18001196c  mov     [r11-58h], rdi
0x180011970  mov     r13, r8
0x180011973  mov     rax, rdx
0x180011976  mov     rbx, rcx
0x180011979  mov     rcx, cs:WPP_GLOBAL_Control
0x180011980  lea     rdx, WPP_GLOBAL_Control
0x180011987  mov     r12d, [rsp+98h+dwFlags]
0x18001198f  cmp     rcx, rdx
0x180011992  jz      short loc_1800119B8
0x180011994  test    byte ptr [rcx+1Ch], 4
0x180011998  jz      short loc_1800119B8
0x18001199a  mov     rcx, [rcx+10h]
0x18001199e  lea     edx, [rdi+1Ah]
0x1800119a1  mov     [r11-70h], r12d
0x1800119a5  mov     r9, rbx
0x1800119a8  mov     [r11-78h], rax
0x1800119ac  call    WPP_SF_PSD
0x1800119b1  lea     rdx, WPP_GLOBAL_Control
0x1800119b8  mov     rcx, rbx
0x1800119bb  call    ValidateAndReferenceProvider
0x1800119c0  mov     rbp, rax
0x1800119c3  call    ValidateAndReferenceProvider
0x1800119c8  mov     r15, rax
0x1800119cb  test    rbp, rbp
0x1800119ce  jz      loc_180011AD2
0x1800119d4  test    rax, rax
0x1800119d7  jz      loc_180011AD2
0x1800119dd  test    r13, r13
0x1800119e0  jz      loc_180011C4C
0x1800119e6  test    r14, r14
0x1800119e9  jz      loc_180011C4C
0x1800119ef  mov     rax, [r14]
0x1800119f2  mov     ebx, 20h ; ' '
0x1800119f7  mov     [rsp+98h+var_58], rax
0x1800119fc  test    rax, rax
0x1800119ff  jz      loc_180011BC7
0x180011a05  mov     rcx, rbx
0x180011a08  call    SafeAllocaAllocateFromHeap
0x180011a0d  mov     rsi, rax
0x180011a10  test    rax, rax
0x180011a13  jz      loc_180011C74
0x180011a19  xorps   xmm0, xmm0
0x180011a1c  movups  xmmword ptr [rax], xmm0
0x180011a1f  movups  xmmword ptr [rax+10h], xmm0
0x180011a23  mov     rdx, [rsp+98h+arg_8]
0x180011a2b  lea     r9, [rsp+98h+var_58]
0x180011a30  mov     rcx, [rbp+110h]
0x180011a37  mov     r8, r13
0x180011a3a  mov     rax, [rbp+98h]
0x180011a41  mov     [rsp+98h+var_78], r12d
0x180011a46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a4b  mov     ebx, eax
0x180011a4d  cmp     eax, 8009002Eh
0x180011a52  jz      loc_180011B30
0x180011a58  test    eax, eax
0x180011a5a  jnz     loc_180011B63
0x180011a60  test    rdi, rdi
0x180011a63  jz      loc_180011BE6
0x180011a69  mov     rax, [rsp+98h+var_58]
0x180011a6e  lea     rcx, KspRouterBufferList
0x180011a75  mov     rdx, rdi
0x180011a78  mov     [rdi+8], rax
0x180011a7c  mov     [rdi], rbp
0x180011a7f  call    MSCryptAddMemoryBuffer
0x180011a84  mov     rax, [r13+0]
0x180011a88  lea     rcx, KspRouterBufferList
0x180011a8f  mov     rdx, rsi
0x180011a92  mov     [rsi+8], rax
0x180011a96  mov     [rsi], r15
0x180011a99  call    MSCryptAddMemoryBuffer
0x180011a9e  mov     rax, [rsp+98h+var_58]
0x180011aa3  xor     ebx, ebx
0x180011aa5  mov     [r14], rax
0x180011aa8  test    rdi, rdi
0x180011aab  jz      short loc_180011AC4
0x180011aad  mov     ecx, ebx
0x180011aaf  add     rsp, 58h
0x180011ab3  pop     r15
0x180011ab5  pop     r14
0x180011ab7  pop     r13
0x180011ab9  pop     r12
0x180011abb  pop     rdi
0x180011abc  pop     rsi
0x180011abd  pop     rbp
0x180011abe  pop     rbx
0x180011abf  jmp     NormalizeNteStatus
0x180011ac4  test    ebx, ebx
0x180011ac6  jnz     short loc_180011AAD
0x180011ac8  mov     rcx, rbp
0x180011acb  call    DereferenceProvider
0x180011ad0  jmp     short loc_180011AAD
0x180011ad2  mov     ebx, 80090026h
0x180011ad7  mov     rax, cs:WPP_GLOBAL_Control
0x180011ade  cmp     rax, rdx
0x180011ae1  jz      short loc_180011B15
0x180011ae3  test    byte ptr [rax+1Ch], 1
0x180011ae7  jz      short loc_180011B15
0x180011ae9  lea     rcx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011af0  mov     [rsp+98h+var_68], 0B03h
0x180011af8  mov     [rsp+98h+var_70], rcx
0x180011afd  lea     r9, aStatus; "Status"
0x180011b04  mov     rcx, [rax+10h]
0x180011b08  mov     [rsp+98h+var_78], 80090026h
0x180011b10  call    WPP_SF_sDsd
0x180011b15  test    rbp, rbp
0x180011b18  jnz     loc_180011BBA
0x180011b1e  test    r15, r15
0x180011b21  jz      short loc_180011AA8
0x180011b23  mov     rcx, r15
0x180011b26  call    DereferenceProvider
0x180011b2b  jmp     loc_180011AA8
0x180011b30  test    r12b, 40h
0x180011b34  jnz     loc_180011BFB
0x180011b3a  mov     rcx, [rbp+110h]
0x180011b41  lea     r8, aNcryptenumkeys_0; "NCryptEnumKeys"
0x180011b48  mov     rax, [rbp+0C0h]
0x180011b4f  xor     r9d, r9d
0x180011b52  xor     edx, edx
0x180011b54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b59  mov     ebx, eax
0x180011b5b  test    eax, eax
0x180011b5d  jz      loc_180011A23
0x180011b63  mov     rax, cs:WPP_GLOBAL_Control
0x180011b6a  lea     rcx, WPP_GLOBAL_Control
0x180011b71  cmp     rax, rcx
0x180011b74  jz      short loc_180011BA4
0x180011b76  test    byte ptr [rax+1Ch], 1
0x180011b7a  jz      short loc_180011BA4
0x180011b7c  mov     [rsp+98h+var_68], 0B59h
0x180011b84  lea     rcx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011b8b  mov     [rsp+98h+var_70], rcx
0x180011b90  mov     [rsp+98h+var_78], ebx
0x180011b94  mov     rcx, [rax+10h]
0x180011b98  lea     r9, aStatus; "Status"
0x180011b9f  call    WPP_SF_sDsd
0x180011ba4  test    rdi, rdi
0x180011ba7  jnz     loc_180011C9C
0x180011bad  test    rsi, rsi
0x180011bb0  jz      short loc_180011BBA
0x180011bb2  mov     rcx, rsi
0x180011bb5  call    MSCryptFree
0x180011bba  mov     rcx, rbp
0x180011bbd  call    DereferenceProvider
0x180011bc2  jmp     loc_180011B1E
0x180011bc7  mov     rcx, rbx
0x180011bca  call    SafeAllocaAllocateFromHeap
0x180011bcf  mov     rdi, rax
0x180011bd2  test    rax, rax
0x180011bd5  jz      short loc_180011C3A
0x180011bd7  xorps   xmm0, xmm0
0x180011bda  movups  xmmword ptr [rax], xmm0
0x180011bdd  movups  xmmword ptr [rax+10h], xmm0
0x180011be1  jmp     loc_180011A05
0x180011be6  mov     rax, [r14]
0x180011be9  cmp     [rsp+98h+var_58], rax
0x180011bee  jz      loc_180011A84
0x180011bf4  mov     ebx, 80090020h
0x180011bf9  jmp     short loc_180011BB2
0x180011bfb  mov     ebx, 80090022h
0x180011c00  mov     rax, cs:WPP_GLOBAL_Control
0x180011c07  lea     rcx, WPP_GLOBAL_Control
0x180011c0e  cmp     rax, rcx
0x180011c11  jz      short loc_180011BA4
0x180011c13  test    byte ptr [rax+1Ch], 1
0x180011c17  jz      short loc_180011BA4
0x180011c19  mov     [rsp+98h+var_68], 0B47h
0x180011c21  lea     rcx, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011c28  mov     [rsp+98h+var_70], rcx
0x180011c2d  mov     [rsp+98h+var_78], 80090022h
0x180011c35  jmp     loc_180011B94
0x180011c3a  mov     ebx, 8009000Eh
0x180011c3f  mov     r9d, 0B1Eh
0x180011c45  mov     ecx, 8009000Eh
0x180011c4a  jmp     short loc_180011C5C
0x180011c4c  mov     ebx, 80090027h
0x180011c51  mov     r9d, 0B0Ah
0x180011c57  mov     ecx, 80090027h
0x180011c5c  lea     rdx, aStatus; "Status"
0x180011c63  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011c6a  call    DebugTraceError
0x180011c6f  jmp     loc_180011BBA
0x180011c74  mov     r9d, 0B2Fh
0x180011c7a  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011c81  lea     rdx, aStatus; "Status"
0x180011c88  mov     ecx, 8009000Eh
0x180011c8d  mov     ebx, 8009000Eh
0x180011c92  call    DebugTraceError
0x180011c97  jmp     loc_180011BA4
0x180011c9c  mov     rcx, rdi
0x180011c9f  call    MSCryptFree
0x180011ca4  jmp     loc_180011BAD
```
