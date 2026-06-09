# SetSecurityOnKeyFile

- ea: `0x180047254`
- end: `0x180047498`
- name: `SetSecurityOnKeyFile`
- size: `580`
- prototype: `__int64 __fastcall(__int64, SECURITY_INFORMATION, void *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180029004`

## callees

- `0x180004c04`
- `0x1800060e0`
- `0x180006744`
- `0x18000af80`
- `0x18000d3d0`
- `0x18004679c`
- `0x180047254`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800473ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047437`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800473ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047437`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x1800473be`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x1800473be`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180047427`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180047427`

## string_xrefs

- `0x1800472a4`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x1800472e2`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x180047323`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`
- `0x180047394`: `onecore\ds\security\cryptoapi\ncrypt\storage\files.c`

## pseudocode

```c
__int64 __fastcall SetSecurityOnKeyFile(__int64 a1, SECURITY_INFORMATION a2, void *a3, int a4)
{
  void *v6; // r14
  unsigned int v7; // ebx
  unsigned int NestedDirectories; // eax
  __int64 v9; // r9
  unsigned int UserDirectory; // eax
  _WORD *v11; // rcx
  __int64 v12; // rax
  void *Src; // [rsp+38h] [rbp-8h] BYREF
  DWORD dwRevision; // [rsp+70h] [rbp+30h] BYREF
  WORD pControl; // [rsp+88h] [rbp+48h] BYREF
  __int16 v17; // [rsp+8Ah] [rbp+4Ah]

  v17 = HIWORD(a4);
  v6 = 0;
  Src = 0;
  pControl = 0;
  dwRevision = 0;
  if ( !*(_QWORD *)(a1 + 16) )
  {
    v7 = -2146893786;
    DebugTraceError(2148073510LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c", 4450);
    return v7;
  }
  NestedDirectories = ConvertContainerSecurityDescriptor(a3);
  v7 = NestedDirectories;
  if ( NestedDirectories )
  {
    v9 = 4465;
LABEL_13:
    DebugTraceError(NestedDirectories, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c", v9);
    goto LABEL_27;
  }
  UserDirectory = GetUserDirectory(*(unsigned int *)(a1 + 32), *(_QWORD *)(a1 + 80) != 0, *(_WORD **)(a1 + 72), &Src);
  v7 = UserDirectory;
  if ( UserDirectory )
  {
    DebugTraceError(UserDirectory, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\files.c", 4484);
    v6 = Src;
    goto LABEL_27;
  }
  v11 = *(_WORD **)(a1 + 72);
  v12 = -1;
  do
    ++v12;
  while ( v11[v12] );
  v6 = Src;
  NestedDirectories = CreateNestedDirectories(v11, (_WORD *)Src + v12 + 1, *(_DWORD *)(a1 + 32));
  v7 = NestedDirectories;
  if ( NestedDirectories )
  {
    v9 = 4499;
    goto LABEL_13;
  }
  NestedDirectories = GetKeyFileFullPath(v6, *(void **)(a1 + 16));
  v7 = NestedDirectories;
  if ( NestedDirectories )
  {
    v9 = 4509;
    goto LABEL_13;
  }
  if ( !GetSecurityDescriptorControl(0, &pControl, &dwRevision) )
  {
    NestedDirectories = GetLastError();
    v7 = NestedDirectories;
    v9 = 4517;
    goto LABEL_13;
  }
  if ( (a2 & 4) != 0 )
  {
    if ( (pControl & 0x1000) != 0 )
      a2 |= 0x80000000;
    else
      a2 |= 0x20000000u;
  }
  if ( (a2 & 8) != 0 )
  {
    if ( (pControl & 0x2000) != 0 )
      a2 |= 0x40000000u;
    else
      a2 |= 0x10000000u;
  }
  if ( !SetFileSecurityW(0, a2, 0) )
  {
    NestedDirectories = GetLastError();
    v7 = NestedDirectories;
    v9 = 4551;
    goto LABEL_13;
  }
  v7 = 0;
LABEL_27:
  if ( v6 )
    MSCryptFree(v6);
  return v7;
}

```

## disassembly

```asm
0x180047254  mov     [rsp-28h+arg_8], rbx
0x180047259  mov     [rsp-28h+arg_10], rsi
0x18004725e  mov     dword ptr [rsp-28h+pControl], r9d
0x180047263  push    rbp
0x180047264  push    rdi
0x180047265  push    r13
0x180047267  push    r14
0x180047269  push    r15
0x18004726b  mov     rbp, rsp
0x18004726e  sub     rsp, 40h
0x180047272  xor     r13d, r13d
0x180047275  mov     r9, r8
0x180047278  mov     edi, edx
0x18004727a  mov     r15, rcx
0x18004727d  mov     r14d, r13d
0x180047280  mov     [rbp+Src], r13
0x180047284  mov     esi, r13d
0x180047287  mov     [rbp+lpFileName], r13
0x18004728b  mov     [rbp+pSecurityDescriptor], r13
0x18004728f  mov     [rbp+pControl], r13w
0x180047294  mov     [rbp+dwRevision], r13d
0x180047298  cmp     [rcx+10h], r13
0x18004729c  jnz     short loc_1800472C6
0x18004729e  mov     r9d, 1162h
0x1800472a4  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800472ab  lea     rdx, aStatus; "Status"
0x1800472b2  mov     ecx, 80090026h
0x1800472b7  mov     ebx, 80090026h
0x1800472bc  call    DebugTraceError
0x1800472c1  jmp     loc_18004747C
0x1800472c6  lea     r8, [rbp+var_20]
0x1800472ca  mov     rcx, r9; AbsoluteSecurityDescriptor
0x1800472cd  lea     rdx, [rbp+pSecurityDescriptor]
0x1800472d1  call    ConvertContainerSecurityDescriptor
0x1800472d6  mov     ebx, eax
0x1800472d8  test    eax, eax
0x1800472da  jz      short loc_1800472FC
0x1800472dc  mov     r9d, 1171h
0x1800472e2  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800472e9  mov     ecx, eax
0x1800472eb  lea     rdx, aStatus; "Status"
0x1800472f2  call    DebugTraceError
0x1800472f7  jmp     loc_180047453
0x1800472fc  cmp     [r15+50h], r13
0x180047300  lea     r9, [rbp+Src]
0x180047304  mov     r8, [r15+48h]
0x180047308  mov     edx, r13d
0x18004730b  mov     ecx, [r15+20h]
0x18004730f  setnz   dl
0x180047312  call    GetUserDirectory
0x180047317  mov     ebx, eax
0x180047319  test    eax, eax
0x18004731b  jz      short loc_180047341
0x18004731d  mov     r9d, 1184h
0x180047323  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004732a  lea     rdx, aStatus; "Status"
0x180047331  mov     ecx, eax
0x180047333  call    DebugTraceError
0x180047338  mov     r14, [rbp+Src]
0x18004733c  jmp     loc_180047453
0x180047341  mov     rcx, [r15+48h]; Src
0x180047345  or      rax, 0FFFFFFFFFFFFFFFFh
0x180047349  inc     rax
0x18004734c  cmp     [rcx+rax*2], r13w
0x180047351  jnz     short loc_180047349
0x180047353  mov     r14, [rbp+Src]
0x180047357  inc     rax
0x18004735a  mov     r8d, [r15+20h]
0x18004735e  lea     rdx, [r14+rax*2]; void *
0x180047362  call    CreateNestedDirectories
0x180047367  mov     ebx, eax
0x180047369  test    eax, eax
0x18004736b  jz      short loc_180047378
0x18004736d  mov     r9d, 1193h
0x180047373  jmp     loc_1800472E2
0x180047378  mov     rdx, [r15+10h]; void *
0x18004737c  lea     r8, [rbp+lpFileName]
0x180047380  mov     rcx, r14; Src
0x180047383  call    GetKeyFileFullPath
0x180047388  mov     ebx, eax
0x18004738a  test    eax, eax
0x18004738c  jz      short loc_1800473B2
0x18004738e  mov     r9d, 119Dh
0x180047394  lea     r8, aOnecoreDsSecur_23; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004739b  mov     ecx, eax
0x18004739d  lea     rdx, aStatus; "Status"
0x1800473a4  call    DebugTraceError
0x1800473a9  mov     rsi, [rbp+lpFileName]
0x1800473ad  jmp     loc_180047453
0x1800473b2  mov     rcx, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x1800473b6  lea     r8, [rbp+dwRevision]; lpdwRevision
0x1800473ba  lea     rdx, [rbp+pControl]; pControl
0x1800473be  call    cs:__imp_GetSecurityDescriptorControl
0x1800473c5  nop     dword ptr [rax+rax+00h]
0x1800473ca  test    eax, eax
0x1800473cc  jnz     short loc_1800473E4
0x1800473ce  call    cs:__imp_GetLastError
0x1800473d5  nop     dword ptr [rax+rax+00h]
0x1800473da  mov     ebx, eax
0x1800473dc  mov     r9d, 11A5h
0x1800473e2  jmp     short loc_180047394
0x1800473e4  test    dil, 4
0x1800473e8  jz      short loc_1800473FF
0x1800473ea  mov     eax, 1000h
0x1800473ef  test    [rbp+pControl], ax
0x1800473f3  jz      short loc_1800473FB
0x1800473f5  bts     edi, 1Fh
0x1800473f9  jmp     short loc_1800473FF
0x1800473fb  bts     edi, 1Dh
0x1800473ff  test    dil, 8
0x180047403  jz      short loc_18004741A
0x180047405  mov     eax, 2000h
0x18004740a  test    [rbp+pControl], ax
0x18004740e  jz      short loc_180047416
0x180047410  bts     edi, 1Eh
0x180047414  jmp     short loc_18004741A
0x180047416  bts     edi, 1Ch
0x18004741a  mov     rsi, [rbp+lpFileName]
0x18004741e  mov     edx, edi; SecurityInformation
0x180047420  mov     r8, [rbp+pSecurityDescriptor]; pSecurityDescriptor
0x180047424  mov     rcx, rsi; lpFileName
0x180047427  call    cs:__imp_SetFileSecurityW
0x18004742e  nop     dword ptr [rax+rax+00h]
0x180047433  test    eax, eax
0x180047435  jnz     short loc_180047450
0x180047437  call    cs:__imp_GetLastError
0x18004743e  nop     dword ptr [rax+rax+00h]
0x180047443  mov     ebx, eax
0x180047445  mov     r9d, 11C7h
0x18004744b  jmp     loc_1800472E2
0x180047450  mov     ebx, r13d
0x180047453  cmp     [rbp+pSecurityDescriptor], r13
0x180047457  jz      short loc_180047462
0x180047459  mov     rcx, [rbp+pSecurityDescriptor]
0x18004745d  call    MSCryptFree
0x180047462  test    r14, r14
0x180047465  jz      short loc_18004746F
0x180047467  mov     rcx, r14
0x18004746a  call    MSCryptFree
0x18004746f  test    rsi, rsi
0x180047472  jz      short loc_18004747C
0x180047474  mov     rcx, rsi
0x180047477  call    MSCryptFree
0x18004747c  lea     r11, [rsp+40h+var_s0]
0x180047481  mov     eax, ebx
0x180047483  mov     rbx, [r11+38h]
0x180047487  mov     rsi, [r11+40h]
0x18004748b  mov     rsp, r11
0x18004748e  pop     r15
0x180047490  pop     r14
0x180047492  pop     r13
0x180047494  pop     rdi
0x180047495  pop     rbp
0x180047496  retn
```
