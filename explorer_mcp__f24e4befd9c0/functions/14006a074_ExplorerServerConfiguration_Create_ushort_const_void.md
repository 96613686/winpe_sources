# ExplorerServerConfiguration::Create(ushort const *,void * *)

- ea: `0x14006a074`
- end: `0x14006a2ca`
- name: `?Create@ExplorerServerConfiguration@@SA?AV1@PEBGPEAPEAX@Z`
- size: `598`
- prototype: `static struct ExplorerServerConfiguration __high(const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400a3f04`

## callees

- `0x14006a074`
- `0x14006a2d0`
- `0x14006a318`
- `0x1400b9294`
- `0x14010e160`
- `0x14010ed6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14006a2b9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14006a2b9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x14006a1e8`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x14006a1e8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14006a0d2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14006a0fd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14006a262`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14006a291`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14006a0d2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14006a0fd`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14006a262`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14006a291`
- `api-ms-win-shcore-sysinfo-l1-1-0!IsOS` at `0x14006a1cd`
- `api-ms-win-shcore-sysinfo-l1-1-0!IsOS` at `0x14006a1cd`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x14006a191`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x14006a191`

## pseudocode

```c
__int64 __fastcall ExplorerServerConfiguration::Create(__int64 a1, WCHAR *a2, _QWORD *a3)
{
  int v6; // ebx
  char v7; // bp
  char v8; // di
  HANDLE MutexW; // rax
  HANDLE v11; // r14
  char v12; // bl
  LPITEMIDLIST pidl[2]; // [rsp+30h] [rbp-68h] BYREF
  __int128 Buf1; // [rsp+40h] [rbp-58h] BYREF
  __int64 v15; // [rsp+50h] [rbp-48h]

  *a3 = 0;
  *(_BYTE *)(a1 + 3) = 0;
  *(_DWORD *)(a1 + 4) = 0;
  v6 = 2;
  if ( !*a2 )
  {
    v7 = 0;
    goto LABEL_5;
  }
  if ( CompareStringOrdinal(a2, -1, L"/LOADSAVEDWINDOWS", -1, 1) == 2 )
  {
    v12 = 1;
    v7 = 0;
    v8 = 0;
    goto LABEL_14;
  }
  if ( CompareStringOrdinal(a2, -1, L"/NoUACCheck", -1, 1) == 2 )
  {
    v7 = 1;
LABEL_5:
    v8 = 0;
    if ( !ExplorerServerConfiguration::IsCurrentProcessRegisteredShellProgram() )
      goto LABEL_6;
    v12 = 0;
    goto LABEL_14;
  }
  if ( CompareStringOrdinal(a2, -1, L"/NoShellRegistrationCheck", -1, 1) == 2 )
  {
    v7 = 0;
    v8 = 1;
LABEL_28:
    v12 = 0;
LABEL_14:
    if ( IsDesktopWindowAlreadyPresent() || IsOS(0x1Eu) )
      goto LABEL_20;
    MutexW = CreateMutexW(0, 0, L"Local\\ExplorerIsShellMutex");
    v11 = MutexW;
    if ( MutexW )
      WaitForSingleObject(MutexW, 0xFFFFFFFF);
    *a3 = v11;
    if ( IsDesktopWindowAlreadyPresent() )
    {
LABEL_20:
      v6 = 5;
    }
    else
    {
      *(_BYTE *)a1 = v12;
      v6 = 3;
      *(_BYTE *)(a1 + 1) = v7;
      *(_BYTE *)(a1 + 2) = v8;
      *(_BYTE *)(a1 + 3) = 1;
    }
    goto LABEL_6;
  }
  if ( CompareStringOrdinal(a2, -1, L"/NoShellRegistrationAndUACCheck", -1, 1) == 2 )
  {
    v7 = 1;
    v8 = 1;
    goto LABEL_28;
  }
  *(_OWORD *)pidl = 0;
  v15 = 0;
  Buf1 = 0;
  if ( (unsigned int)SHExplorerParseCmdLine(a2, pidl) )
  {
    if ( !memcmp_0((char *)&Buf1 + 8, &GUID_5bd95610_9434_43c2_886c_57852cc8a120, 0x10u) )
    {
      v6 = 6;
    }
    else if ( memcmp_0((char *)&Buf1 + 8, &GUID_NULL, 0x10u) )
    {
      v6 = 4;
    }
    ILFree(pidl[0]);
  }
LABEL_6:
  *(_DWORD *)(a1 + 4) = v6;
  return a1;
}

```

## disassembly

```asm
0x14006a074  push    rbx
0x14006a076  push    rbp
0x14006a077  push    rsi
0x14006a078  push    rdi
0x14006a079  push    r12
0x14006a07b  push    r14
0x14006a07d  push    r15
0x14006a07f  sub     rsp, 60h
0x14006a083  mov     rax, cs:__security_cookie
0x14006a08a  xor     rax, rsp
0x14006a08d  mov     [rsp+98h+var_40], rax
0x14006a092  xor     r12d, r12d
0x14006a095  mov     r15, r8
0x14006a098  mov     [r8], r12
0x14006a09b  mov     rdi, rdx
0x14006a09e  mov     [rcx+3], r12b
0x14006a0a2  mov     rsi, rcx
0x14006a0a5  mov     [rcx+4], r12d
0x14006a0a9  lea     ebx, [r12+2]
0x14006a0ae  cmp     [rdx], r12w
0x14006a0b2  jz      loc_14006A22E
0x14006a0b8  or      ebp, 0FFFFFFFFh
0x14006a0bb  mov     [rsp+98h+bIgnoreCase], 1; bIgnoreCase
0x14006a0c3  mov     r9d, ebp; cchCount2
0x14006a0c6  lea     r8, pwzCommandline; "/LOADSAVEDWINDOWS"
0x14006a0cd  mov     edx, ebp; cchCount1
0x14006a0cf  mov     rcx, rdi; lpString1
0x14006a0d2  call    cs:__imp_CompareStringOrdinal
0x14006a0d9  nop     dword ptr [rax+rax+00h]
0x14006a0de  cmp     eax, ebx
0x14006a0e0  jz      loc_14006A236
0x14006a0e6  mov     r9d, ebp; cchCount2
0x14006a0e9  mov     [rsp+98h+bIgnoreCase], 1; bIgnoreCase
0x14006a0f1  lea     r8, aNouaccheck; "/NoUACCheck"
0x14006a0f8  mov     edx, ebp; cchCount1
0x14006a0fa  mov     rcx, rdi; lpString1
0x14006a0fd  call    cs:__imp_CompareStringOrdinal
0x14006a104  nop     dword ptr [rax+rax+00h]
0x14006a109  cmp     eax, ebx
0x14006a10b  jnz     loc_14006A24B
0x14006a111  mov     bpl, 1
0x14006a114  mov     dil, r12b
0x14006a117  call    ?IsCurrentProcessRegisteredShellProgram@ExplorerServerConfiguration@@CA_NXZ; ExplorerServerConfiguration::IsCurrentProcessRegisteredShellProgram(void)
0x14006a11c  test    al, al
0x14006a11e  jnz     loc_14006A243
0x14006a124  mov     [rsi+4], ebx
0x14006a127  mov     rax, rsi
0x14006a12a  mov     rcx, [rsp+98h+var_40]
0x14006a12f  xor     rcx, rsp; StackCookie
0x14006a132  call    __security_check_cookie
0x14006a137  add     rsp, 60h
0x14006a13b  pop     r15
0x14006a13d  pop     r14
0x14006a13f  pop     r12
0x14006a141  pop     rdi
0x14006a142  pop     rsi
0x14006a143  pop     rbp
0x14006a144  pop     rbx
0x14006a145  retn
0x14006a147  xorps   xmm0, xmm0
0x14006a14a  lea     rdx, [rsp+98h+pidl]; ppidl
0x14006a14f  xor     eax, eax
0x14006a151  mov     rcx, rdi; unsigned __int16 *
0x14006a154  movups  xmmword ptr [rsp+98h+pidl], xmm0
0x14006a159  mov     [rsp+98h+var_48], rax
0x14006a15e  movups  [rsp+98h+Buf1], xmm0
0x14006a163  call    SHExplorerParseCmdLine
0x14006a168  test    eax, eax
0x14006a16a  jz      short loc_14006A124
0x14006a16c  mov     edi, 10h
0x14006a171  lea     rdx, _GUID_5bd95610_9434_43c2_886c_57852cc8a120; Buf2
0x14006a178  mov     r8d, edi; Size
0x14006a17b  lea     rcx, [rsp+98h+Buf1+8]; Buf1
0x14006a180  call    memcmp_0
0x14006a185  test    eax, eax
0x14006a187  jnz     short loc_14006A19F
0x14006a189  lea     ebx, [rdi-0Ah]
0x14006a18c  mov     rcx, [rsp+98h+pidl]; pidl
0x14006a191  call    cs:__imp_ILFree
0x14006a198  nop     dword ptr [rax+rax+00h]
0x14006a19d  jmp     short loc_14006A124
0x14006a19f  mov     r8, rdi; Size
0x14006a1a2  lea     rdx, GUID_NULL; Buf2
0x14006a1a9  lea     rcx, [rsp+98h+Buf1+8]; Buf1
0x14006a1ae  call    memcmp_0
0x14006a1b3  test    eax, eax
0x14006a1b5  mov     ecx, 4
0x14006a1ba  cmovnz  ebx, ecx
0x14006a1bd  jmp     short loc_14006A18C
0x14006a1bf  call    ?IsDesktopWindowAlreadyPresent@@YA_NXZ; IsDesktopWindowAlreadyPresent(void)
0x14006a1c4  test    al, al
0x14006a1c6  jnz     short loc_14006A224
0x14006a1c8  mov     ecx, 1Eh; dwOS
0x14006a1cd  call    cs:__imp_IsOS
0x14006a1d4  nop     dword ptr [rax+rax+00h]
0x14006a1d9  test    eax, eax
0x14006a1db  jnz     short loc_14006A224
0x14006a1dd  lea     r8, aLocalExploreri; "Local\\ExplorerIsShellMutex"
0x14006a1e4  xor     edx, edx; bInitialOwner
0x14006a1e6  xor     ecx, ecx; lpMutexAttributes
0x14006a1e8  call    cs:__imp_CreateMutexW
0x14006a1ef  nop     dword ptr [rax+rax+00h]
0x14006a1f4  mov     r14, rax
0x14006a1f7  test    rax, rax
0x14006a1fa  jnz     loc_14006A2B3
0x14006a200  mov     [r15], r14
0x14006a203  call    ?IsDesktopWindowAlreadyPresent@@YA_NXZ; IsDesktopWindowAlreadyPresent(void)
0x14006a208  test    al, al
0x14006a20a  jnz     short loc_14006A224
0x14006a20c  mov     [rsi], bl
0x14006a20e  mov     ebx, 3
0x14006a213  mov     [rsi+1], bpl
0x14006a217  mov     [rsi+2], dil
0x14006a21b  mov     byte ptr [rsi+3], 1
0x14006a21f  jmp     loc_14006A124
0x14006a224  mov     ebx, 5
0x14006a229  jmp     loc_14006A124
0x14006a22e  mov     bpl, r12b
0x14006a231  jmp     loc_14006A114
0x14006a236  mov     bl, 1
0x14006a238  mov     bpl, r12b
0x14006a23b  mov     dil, r12b
0x14006a23e  jmp     loc_14006A1BF
0x14006a243  mov     bl, dil
0x14006a246  jmp     loc_14006A1BF
0x14006a24b  mov     r9d, ebp; cchCount2
0x14006a24e  mov     [rsp+98h+bIgnoreCase], 1; bIgnoreCase
0x14006a256  lea     r8, aNoshellregistr; "/NoShellRegistrationCheck"
0x14006a25d  mov     edx, ebp; cchCount1
0x14006a25f  mov     rcx, rdi; lpString1
0x14006a262  call    cs:__imp_CompareStringOrdinal
0x14006a269  nop     dword ptr [rax+rax+00h]
0x14006a26e  cmp     eax, ebx
0x14006a270  jnz     short loc_14006A27A
0x14006a272  mov     bpl, r12b
0x14006a275  mov     dil, 1
0x14006a278  jmp     short loc_14006A2AB
0x14006a27a  mov     r9d, ebp; cchCount2
0x14006a27d  mov     [rsp+98h+bIgnoreCase], 1; bIgnoreCase
0x14006a285  lea     r8, aNoshellregistr_0; "/NoShellRegistrationAndUACCheck"
0x14006a28c  mov     edx, ebp; cchCount1
0x14006a28e  mov     rcx, rdi; lpString1
0x14006a291  call    cs:__imp_CompareStringOrdinal
0x14006a298  nop     dword ptr [rax+rax+00h]
0x14006a29d  cmp     eax, ebx
0x14006a29f  jnz     loc_14006A147
0x14006a2a5  mov     bpl, 1
0x14006a2a8  mov     dil, bpl
0x14006a2ab  mov     bl, r12b
0x14006a2ae  jmp     loc_14006A1BF
0x14006a2b3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14006a2b6  mov     rcx, r14; hHandle
0x14006a2b9  call    cs:__imp_WaitForSingleObject
0x14006a2c0  nop     dword ptr [rax+rax+00h]
0x14006a2c5  jmp     loc_14006A200
```
