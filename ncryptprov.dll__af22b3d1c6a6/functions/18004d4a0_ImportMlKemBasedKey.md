# ImportMlKemBasedKey

- ea: `0x18004d4a0`
- end: `0x18004d7da`
- name: `ImportMlKemBasedKey`
- size: `826`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18004d354`

## callees

- `0x1800086d0`
- `0x18000af80`
- `0x18004d4a0`
- `0x180062280`
- `0x180062310`
- `0x180063010`

## import_xrefs

- `bcrypt!BCryptImportKeyPair` at `0x18004d74e`
- `bcrypt!BCryptImportKeyPair` at `0x18004d74e`

## string_xrefs

- `0x18004d716`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18004d7ab`: `onecore\ds\security\cryptoapi\ncrypt\storage\provider.c`
- `0x18004d597`: `COMPMLKEMPUBLICBLOB`
- `0x18004d565`: `COMPMLKEMPRIVATELAMPSBLOB`
- `0x18004d53e`: `COMPMLKEMPRIVATEIRTFSEEDBLOB`

## pseudocode

```c
__int64 __fastcall ImportMlKemBasedKey(__int64 a1, char a2)
{
  _DWORD *v4; // r8
  __int64 v5; // r11
  unsigned int v6; // r10d
  __int64 v7; // r9
  const wchar_t *v8; // rdx
  const WCHAR *v9; // r14
  _QWORD *v10; // r15
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rcx
  __int64 v14; // rdx
  unsigned __int64 v15; // rbx
  ULONG *pbInput; // rdi
  unsigned __int64 v17; // rcx
  __int64 v18; // rcx
  unsigned __int64 v19; // rcx
  void *v20; // rsp
  void *v21; // rsp
  ULONG *v22; // rax
  NTSTATUS v23; // eax
  __int64 v24; // r9
  __int64 v25; // rax
  ULONG *v26; // rcx
  __int64 v28; // [rsp+0h] [rbp-40h] BYREF
  ULONG cbInput; // [rsp+40h] [rbp+0h] BYREF
  __int64 v30; // [rsp+48h] [rbp+8h] BYREF

  cbInput = 0;
  if ( !a1
    || (v4 = *(_DWORD **)(a1 + 208)) == 0
    || (v5 = *(_QWORD *)(a1 + 168)) == 0
    || (v6 = *(_DWORD *)(a1 + 216), v6 < 0xC) )
  {
    v7 = 7980;
    goto LABEL_50;
  }
  switch ( *v4 )
  {
    case 0x524B4C4D:
      v8 = L"MLKEMPRIVATEBLOB";
      break;
    case 0x524B4D43:
      v8 = L"COMPMLKEMPRIVATELAMPSBLOB";
      break;
    case 0x52505150:
      v6 = v4[2];
      v8 = (const wchar_t *)(v4 + 3);
      v4 = (_DWORD *)((char *)v4 + (unsigned int)v4[1] + 12);
      break;
    case 0x534B4C4D:
      v8 = L"MLKEMPRIVATESEEDBLOB";
      break;
    case 0x534B4D43:
      v8 = L"COMPMLKEMPRIVATEIRTFSEEDBLOB";
      break;
    default:
      v7 = 8009;
LABEL_50:
      v12 = -2146893779;
      v13 = 2148073517LL;
      goto LABEL_51;
  }
  if ( *(_DWORD *)(*(_QWORD *)(a1 + 64) + 32LL) == 458753 )
  {
    v9 = L"MLKEMPUBLICBLOB";
  }
  else
  {
    if ( *(_DWORD *)(*(_QWORD *)(a1 + 64) + 32LL) != 458754 )
    {
      v7 = 8029;
      goto LABEL_50;
    }
    v9 = L"COMPMLKEMPUBLICBLOB";
  }
  v10 = (_QWORD *)(a1 + 112);
  v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const wchar_t *, __int64, _DWORD *, unsigned int, int))(v5 + 112))(
          *(_QWORD *)(a1 + 152),
          *(_QWORD *)(a1 + 96),
          v8,
          a1 + 112,
          v4,
          v6,
          a2 & 0x77);
  v12 = v11;
  if ( v11 < 0 )
  {
    v7 = 8044;
LABEL_23:
    v13 = (unsigned int)v11;
LABEL_51:
    DebugTraceError(v13, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c", v7);
    return v12;
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const WCHAR *, _QWORD, _DWORD, ULONG *, _DWORD))(*(_QWORD *)(a1 + 168)
                                                                                                  + 120LL))(
          *v10,
          0,
          v9,
          0,
          0,
          &cbInput,
          0);
  v12 = v11;
  if ( v11 < 0 )
  {
    v7 = 8063;
    goto LABEL_23;
  }
  v15 = cbInput;
  pbInput = 0;
  if ( !cbInput )
    goto LABEL_55;
  if ( cbInput > (unsigned __int64)g_ulMaxStackAllocSize )
    goto LABEL_55;
  v17 = cbInput + g_ulAdditionalProbeSize + 8;
  if ( v17 < cbInput || !(unsigned int)VerifyStackAvailable(v17, v14) )
    goto LABEL_55;
  v18 = v15 + 23;
  if ( v15 + 23 <= v15 + 8 )
    v18 = 0xFFFFFFFFFFFFFF0LL;
  v19 = v18 & 0xFFFFFFFFFFFFFFF0uLL;
  v20 = alloca(v19);
  v21 = alloca(v19);
  pbInput = &cbInput;
  if ( &v28 == (__int64 *)-64LL || (cbInput = 1801679955, (pbInput = (ULONG *)&v30) == 0) )
  {
LABEL_55:
    if ( v15 + 8 >= v15 )
    {
      v22 = (ULONG *)((__int64 (*)(void))g_pfnAllocate)();
      pbInput = v22;
      if ( v22 )
      {
        *v22 = 1885431112;
        pbInput = v22 + 2;
      }
    }
  }
  if ( !pbInput )
  {
    v12 = -2146893810;
    v7 = 8072;
    v13 = 2148073486LL;
    goto LABEL_51;
  }
  v23 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const WCHAR *, ULONG *, ULONG, ULONG *, _DWORD))(*(_QWORD *)(a1 + 168)
                                                                                                  + 120LL))(
          *v10,
          0,
          v9,
          pbInput,
          cbInput,
          &cbInput,
          0);
  v12 = v23;
  if ( v23 >= 0 )
  {
    v23 = BCryptImportKeyPair(
            *(BCRYPT_ALG_HANDLE *)(a1 + 88),
            0,
            v9,
            (BCRYPT_KEY_HANDLE *)(a1 + 104),
            (PUCHAR)pbInput,
            cbInput,
            0);
    v12 = v23;
    if ( !v23 )
    {
      v12 = 0;
      goto LABEL_45;
    }
    v24 = 8105;
  }
  else
  {
    v24 = 8086;
  }
  DebugTraceError((unsigned int)v23, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\provider.c", v24);
LABEL_45:
  v25 = cbInput;
  v26 = pbInput;
  if ( cbInput )
  {
    do
    {
      *(_BYTE *)v26 = 0;
      v26 = (ULONG *)((char *)v26 + 1);
      --v25;
    }
    while ( v25 );
  }
  if ( *(pbInput - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  return v12;
}

```

## disassembly

```asm
0x18004d4a0  push    rbp
0x18004d4a2  push    rbx
0x18004d4a3  push    rsi
0x18004d4a4  push    rdi
0x18004d4a5  push    r14
0x18004d4a7  push    r15
0x18004d4a9  sub     rsp, 68h
0x18004d4ad  lea     rbp, [rsp+40h]
0x18004d4b2  mov     rax, cs:__security_cookie
0x18004d4b9  xor     rax, rbp
0x18004d4bc  mov     [rbp+50h+var_40], rax
0x18004d4c0  mov     [rbp+50h+var_50], 0
0x18004d4c7  mov     ebx, edx
0x18004d4c9  mov     rsi, rcx
0x18004d4cc  test    rcx, rcx
0x18004d4cf  jz      loc_18004D79B
0x18004d4d5  mov     r8, [rcx+0D0h]
0x18004d4dc  test    r8, r8
0x18004d4df  jz      loc_18004D79B
0x18004d4e5  mov     r11, [rcx+0A8h]
0x18004d4ec  test    r11, r11
0x18004d4ef  jz      loc_18004D79B
0x18004d4f5  mov     r10d, [rcx+0D8h]
0x18004d4fc  cmp     r10d, 0Ch
0x18004d500  jb      loc_18004D79B
0x18004d506  cmp     dword ptr [r8], 524B4C4Dh
0x18004d50d  jz      short loc_18004D56E
0x18004d50f  cmp     dword ptr [r8], 524B4D43h
0x18004d516  jz      short loc_18004D565
0x18004d518  cmp     dword ptr [r8], 52505150h
0x18004d51f  jz      short loc_18004D550
0x18004d521  cmp     dword ptr [r8], 534B4C4Dh
0x18004d528  jz      short loc_18004D547
0x18004d52a  cmp     dword ptr [r8], 534B4D43h
0x18004d531  jz      short loc_18004D53E
0x18004d533  mov     r9d, 1F49h
0x18004d539  jmp     loc_18004D7A1
0x18004d53e  lea     rdx, aCompmlkempriva_0; "COMPMLKEMPRIVATEIRTFSEEDBLOB"
0x18004d545  jmp     short loc_18004D575
0x18004d547  lea     rdx, aMlkemprivatese; "MLKEMPRIVATESEEDBLOB"
0x18004d54e  jmp     short loc_18004D575
0x18004d550  mov     r10d, [r8+8]
0x18004d554  lea     rdx, [r8+0Ch]
0x18004d558  mov     eax, [r8+4]
0x18004d55c  add     r8, 0Ch
0x18004d560  add     r8, rax
0x18004d563  jmp     short loc_18004D575
0x18004d565  lea     rdx, aCompmlkempriva; "COMPMLKEMPRIVATELAMPSBLOB"
0x18004d56c  jmp     short loc_18004D575
0x18004d56e  lea     rdx, aMlkemprivatebl; "MLKEMPRIVATEBLOB"
0x18004d575  mov     rcx, [rcx+40h]
0x18004d579  mov     r9d, [rcx+20h]
0x18004d57d  sub     r9d, 70001h
0x18004d584  jz      short loc_18004D5A0
0x18004d586  cmp     r9d, 1
0x18004d58a  jz      short loc_18004D597
0x18004d58c  mov     r9d, 1F5Dh
0x18004d592  jmp     loc_18004D7A1
0x18004d597  lea     r14, aCompmlkempubli; "COMPMLKEMPUBLICBLOB"
0x18004d59e  jmp     short loc_18004D5A7
0x18004d5a0  lea     r14, aMlkempublicblo; "MLKEMPUBLICBLOB"
0x18004d5a7  mov     rcx, [rsi+98h]
0x18004d5ae  lea     r15, [rsi+70h]
0x18004d5b2  mov     rax, [r11+70h]
0x18004d5b6  and     ebx, 77h
0x18004d5b9  mov     [rsp+90h+dwFlags], ebx
0x18004d5bd  mov     r9, r15
0x18004d5c0  mov     [rsp+90h+cbInput], r10d
0x18004d5c5  mov     [rsp+90h+pbInput], r8
0x18004d5ca  mov     r8, rdx
0x18004d5cd  mov     rdx, [rsi+60h]
0x18004d5d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d5d6  mov     ebx, eax
0x18004d5d8  test    eax, eax
0x18004d5da  jns     short loc_18004D5E9
0x18004d5dc  mov     r9d, 1F6Ch
0x18004d5e2  mov     ecx, eax
0x18004d5e4  jmp     loc_18004D7AB
0x18004d5e9  mov     rax, [rsi+0A8h]
0x18004d5f0  lea     rcx, [rbp+50h+var_50]
0x18004d5f4  mov     [rsp+90h+dwFlags], 0
0x18004d5fc  xor     r9d, r9d
0x18004d5ff  mov     qword ptr [rsp+90h+cbInput], rcx
0x18004d604  mov     r8, r14
0x18004d607  mov     rcx, [r15]
0x18004d60a  xor     edx, edx
0x18004d60c  mov     rax, [rax+78h]
0x18004d610  mov     dword ptr [rsp+90h+pbInput], 0
0x18004d618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d61d  mov     ebx, eax
0x18004d61f  test    eax, eax
0x18004d621  jns     short loc_18004D62B
0x18004d623  mov     r9d, 1F7Fh
0x18004d629  jmp     short loc_18004D5E2
0x18004d62b  mov     ebx, [rbp+50h+var_50]
0x18004d62e  xor     edi, edi
0x18004d630  test    rbx, rbx
0x18004d633  jz      short loc_18004D696
0x18004d635  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18004d63c  ja      short loc_18004D696
0x18004d63e  mov     rcx, cs:g_ulAdditionalProbeSize
0x18004d645  add     rcx, 8
0x18004d649  add     rcx, rbx
0x18004d64c  cmp     rcx, rbx
0x18004d64f  jb      short loc_18004D696
0x18004d651  call    VerifyStackAvailable
0x18004d656  test    eax, eax
0x18004d658  jz      short loc_18004D696
0x18004d65a  lea     rax, [rbx+8]
0x18004d65e  lea     rcx, [rax+0Fh]
0x18004d662  cmp     rcx, rax
0x18004d665  ja      short loc_18004D671
0x18004d667  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18004d671  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18004d675  mov     rax, rcx
0x18004d678  call    _alloca_probe
0x18004d67d  sub     rsp, rcx
0x18004d680  lea     rdi, [rsp+90h+var_50]
0x18004d685  test    rdi, rdi
0x18004d688  jz      short loc_18004D696
0x18004d68a  mov     dword ptr [rdi], 6B637453h
0x18004d690  add     rdi, 8
0x18004d694  jnz     short loc_18004D6BD
0x18004d696  lea     rcx, [rbx+8]
0x18004d69a  cmp     rcx, rbx
0x18004d69d  jb      short loc_18004D6BD
0x18004d69f  mov     rax, cs:g_pfnAllocate
0x18004d6a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d6ab  mov     rdi, rax
0x18004d6ae  test    rax, rax
0x18004d6b1  jz      short loc_18004D6BD
0x18004d6b3  mov     dword ptr [rax], 70616548h
0x18004d6b9  add     rdi, 8
0x18004d6bd  test    rdi, rdi
0x18004d6c0  jnz     short loc_18004D6D7
0x18004d6c2  mov     ebx, 8009000Eh
0x18004d6c7  mov     r9d, 1F88h
0x18004d6cd  mov     ecx, 8009000Eh
0x18004d6d2  jmp     loc_18004D7AB
0x18004d6d7  mov     edx, [rbp+50h+var_50]
0x18004d6da  lea     rcx, [rbp+50h+var_50]
0x18004d6de  mov     rax, [rsi+0A8h]
0x18004d6e5  mov     r9, rdi
0x18004d6e8  mov     [rsp+90h+dwFlags], 0
0x18004d6f0  mov     r8, r14
0x18004d6f3  mov     qword ptr [rsp+90h+cbInput], rcx
0x18004d6f8  mov     rcx, [r15]
0x18004d6fb  mov     rax, [rax+78h]
0x18004d6ff  mov     dword ptr [rsp+90h+pbInput], edx
0x18004d703  xor     edx, edx
0x18004d705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d70a  mov     ebx, eax
0x18004d70c  test    eax, eax
0x18004d70e  jns     short loc_18004D72D
0x18004d710  mov     r9d, 1F96h
0x18004d716  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004d71d  mov     ecx, eax
0x18004d71f  lea     rdx, aStatus; "Status"
0x18004d726  call    DebugTraceError
0x18004d72b  jmp     short loc_18004D76A
0x18004d72d  mov     eax, [rbp+50h+var_50]
0x18004d730  lea     r9, [rsi+68h]; phKey
0x18004d734  mov     rcx, [rsi+58h]; hAlgorithm
0x18004d738  mov     r8, r14; pszBlobType
0x18004d73b  mov     [rsp+90h+dwFlags], 0; dwFlags
0x18004d743  xor     edx, edx; hImportKey
0x18004d745  mov     [rsp+90h+cbInput], eax; cbInput
0x18004d749  mov     [rsp+90h+pbInput], rdi; pbInput
0x18004d74e  call    cs:__imp_BCryptImportKeyPair
0x18004d755  nop     dword ptr [rax+rax+00h]
0x18004d75a  mov     ebx, eax
0x18004d75c  test    eax, eax
0x18004d75e  jz      short loc_18004D768
0x18004d760  mov     r9d, 1FA9h
0x18004d766  jmp     short loc_18004D716
0x18004d768  xor     ebx, ebx
0x18004d76a  mov     eax, [rbp+50h+var_50]
0x18004d76d  mov     rcx, rdi
0x18004d770  test    rax, rax
0x18004d773  jz      short loc_18004D781
0x18004d775  mov     byte ptr [rcx], 0
0x18004d778  inc     rcx
0x18004d77b  sub     rax, 1
0x18004d77f  jnz     short loc_18004D775
0x18004d781  lea     rcx, [rdi-8]
0x18004d785  cmp     dword ptr [rcx], 70616548h
0x18004d78b  jnz     short loc_18004D7BE
0x18004d78d  mov     rax, cs:g_pfnFree
0x18004d794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d799  jmp     short loc_18004D7BE
0x18004d79b  mov     r9d, 1F2Ch
0x18004d7a1  mov     ebx, 8009002Dh
0x18004d7a6  mov     ecx, 8009002Dh
0x18004d7ab  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004d7b2  lea     rdx, aStatus; "Status"
0x18004d7b9  call    DebugTraceError
0x18004d7be  mov     eax, ebx
0x18004d7c0  mov     rcx, [rbp+50h+var_40]
0x18004d7c4  xor     rcx, rbp; StackCookie
0x18004d7c7  call    __security_check_cookie
0x18004d7cc  lea     rsp, [rbp+28h]
0x18004d7d0  pop     r15
0x18004d7d2  pop     r14
0x18004d7d4  pop     rdi
0x18004d7d5  pop     rsi
0x18004d7d6  pop     rbx
0x18004d7d7  pop     rbp
0x18004d7d8  retn
```
