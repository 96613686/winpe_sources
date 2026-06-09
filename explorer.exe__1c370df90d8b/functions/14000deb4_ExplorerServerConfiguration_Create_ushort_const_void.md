# ExplorerServerConfiguration::Create(ushort const *,void * *)

- ea: `0x14000deb4`
- end: `0x14000e0d3`
- name: `?Create@ExplorerServerConfiguration@@SA?AV1@PEBGPEAPEAX@Z`
- size: `543`
- prototype: `static struct ExplorerServerConfiguration __high(const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14009ae00`

## callees

- `0x14000deb4`
- `0x14000e0dc`
- `0x14000e118`
- `0x1400b3194`
- `0x1401040e0`
- `0x140104cbc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000e0c8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000e0c8`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x14000e00f`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x14000e00f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14000df12`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14000df37`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14000e07d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14000e0a6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14000df12`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14000df37`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14000e07d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14000e0a6`
- `api-ms-win-shcore-sysinfo-l1-1-0!IsOS` at `0x14000dffa`
- `api-ms-win-shcore-sysinfo-l1-1-0!IsOS` at `0x14000dffa`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x14000dfc4`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x14000dfc4`

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
0x14000deb4  push    rbx
0x14000deb6  push    rbp
0x14000deb7  push    rsi
0x14000deb8  push    rdi
0x14000deb9  push    r12
0x14000debb  push    r14
0x14000debd  push    r15
0x14000debf  sub     rsp, 60h
0x14000dec3  mov     rax, cs:__security_cookie
0x14000deca  xor     rax, rsp
0x14000decd  mov     [rsp+98h+var_40], rax
0x14000ded2  xor     r12d, r12d
0x14000ded5  mov     r15, r8
0x14000ded8  mov     [r8], r12
0x14000dedb  mov     rdi, rdx
0x14000dede  mov     [rcx+3], r12b
0x14000dee2  mov     rsi, rcx
0x14000dee5  mov     [rcx+4], r12d
0x14000dee9  lea     ebx, [r12+2]
0x14000deee  cmp     [rdx], r12w
0x14000def2  jz      loc_14000E04F
0x14000def8  or      ebp, 0FFFFFFFFh
0x14000defb  mov     [rsp+98h+bIgnoreCase], 1; bIgnoreCase
0x14000df03  mov     r9d, ebp; cchCount2
0x14000df06  lea     r8, pwzCommandline; "/LOADSAVEDWINDOWS"
0x14000df0d  mov     edx, ebp; cchCount1
0x14000df0f  mov     rcx, rdi; lpString1
0x14000df12  call    cs:__imp_CompareStringOrdinal
0x14000df18  cmp     eax, ebx
0x14000df1a  jz      loc_14000E057
0x14000df20  mov     r9d, ebp; cchCount2
0x14000df23  mov     [rsp+98h+bIgnoreCase], 1; bIgnoreCase
0x14000df2b  lea     r8, aNouaccheck; "/NoUACCheck"
0x14000df32  mov     edx, ebp; cchCount1
0x14000df34  mov     rcx, rdi; lpString1
0x14000df37  call    cs:__imp_CompareStringOrdinal
0x14000df3d  cmp     eax, ebx
0x14000df3f  jnz     loc_14000E066
0x14000df45  mov     bpl, 1
0x14000df48  mov     dil, r12b
0x14000df4b  call    ?IsCurrentProcessRegisteredShellProgram@ExplorerServerConfiguration@@CA_NXZ; ExplorerServerConfiguration::IsCurrentProcessRegisteredShellProgram(void)
0x14000df50  test    al, al
0x14000df52  jnz     loc_14000E061
0x14000df58  mov     [rsi+4], ebx
0x14000df5b  mov     rax, rsi
0x14000df5e  mov     rcx, [rsp+98h+var_40]
0x14000df63  xor     rcx, rsp; StackCookie
0x14000df66  call    __security_check_cookie
0x14000df6b  add     rsp, 60h
0x14000df6f  pop     r15
0x14000df71  pop     r14
0x14000df73  pop     r12
0x14000df75  pop     rdi
0x14000df76  pop     rsi
0x14000df77  pop     rbp
0x14000df78  pop     rbx
0x14000df79  retn
0x14000df7a  xorps   xmm0, xmm0
0x14000df7d  lea     rdx, [rsp+98h+pidl]; ppidl
0x14000df82  xor     eax, eax
0x14000df84  mov     rcx, rdi; unsigned __int16 *
0x14000df87  movups  xmmword ptr [rsp+98h+pidl], xmm0
0x14000df8c  mov     [rsp+98h+var_48], rax
0x14000df91  movups  [rsp+98h+Buf1], xmm0
0x14000df96  call    SHExplorerParseCmdLine
0x14000df9b  test    eax, eax
0x14000df9d  jz      short loc_14000DF58
0x14000df9f  mov     edi, 10h
0x14000dfa4  lea     rdx, _GUID_5bd95610_9434_43c2_886c_57852cc8a120; Buf2
0x14000dfab  mov     r8d, edi; Size
0x14000dfae  lea     rcx, [rsp+98h+Buf1+8]; Buf1
0x14000dfb3  call    memcmp_0
0x14000dfb8  test    eax, eax
0x14000dfba  jnz     short loc_14000DFCC
0x14000dfbc  lea     ebx, [rdi-0Ah]
0x14000dfbf  mov     rcx, [rsp+98h+pidl]; pidl
0x14000dfc4  call    cs:__imp_ILFree
0x14000dfca  jmp     short loc_14000DF58
0x14000dfcc  mov     r8, rdi; Size
0x14000dfcf  lea     rdx, GUID_NULL; Buf2
0x14000dfd6  lea     rcx, [rsp+98h+Buf1+8]; Buf1
0x14000dfdb  call    memcmp_0
0x14000dfe0  test    eax, eax
0x14000dfe2  mov     ecx, 4
0x14000dfe7  cmovnz  ebx, ecx
0x14000dfea  jmp     short loc_14000DFBF
0x14000dfec  call    ?IsDesktopWindowAlreadyPresent@@YA_NXZ; IsDesktopWindowAlreadyPresent(void)
0x14000dff1  test    al, al
0x14000dff3  jnz     short loc_14000E045
0x14000dff5  mov     ecx, 1Eh; dwOS
0x14000dffa  call    cs:__imp_IsOS
0x14000e000  test    eax, eax
0x14000e002  jnz     short loc_14000E045
0x14000e004  lea     r8, aLocalExploreri; "Local\\ExplorerIsShellMutex"
0x14000e00b  xor     edx, edx; bInitialOwner
0x14000e00d  xor     ecx, ecx; lpMutexAttributes
0x14000e00f  call    cs:__imp_CreateMutexW
0x14000e015  mov     r14, rax
0x14000e018  test    rax, rax
0x14000e01b  jnz     loc_14000E0C2
0x14000e021  mov     [r15], r14
0x14000e024  call    ?IsDesktopWindowAlreadyPresent@@YA_NXZ; IsDesktopWindowAlreadyPresent(void)
0x14000e029  test    al, al
0x14000e02b  jnz     short loc_14000E045
0x14000e02d  mov     [rsi], bl
0x14000e02f  mov     ebx, 3
0x14000e034  mov     [rsi+1], bpl
0x14000e038  mov     [rsi+2], dil
0x14000e03c  mov     byte ptr [rsi+3], 1
0x14000e040  jmp     loc_14000DF58
0x14000e045  mov     ebx, 5
0x14000e04a  jmp     loc_14000DF58
0x14000e04f  mov     bpl, r12b
0x14000e052  jmp     loc_14000DF48
0x14000e057  mov     bl, 1
0x14000e059  mov     bpl, r12b
0x14000e05c  mov     dil, r12b
0x14000e05f  jmp     short loc_14000DFEC
0x14000e061  mov     bl, dil
0x14000e064  jmp     short loc_14000DFEC
0x14000e066  mov     r9d, ebp; cchCount2
0x14000e069  mov     [rsp+98h+bIgnoreCase], 1; bIgnoreCase
0x14000e071  lea     r8, aNoshellregistr; "/NoShellRegistrationCheck"
0x14000e078  mov     edx, ebp; cchCount1
0x14000e07a  mov     rcx, rdi; lpString1
0x14000e07d  call    cs:__imp_CompareStringOrdinal
0x14000e083  cmp     eax, ebx
0x14000e085  jnz     short loc_14000E08F
0x14000e087  mov     bpl, r12b
0x14000e08a  mov     dil, 1
0x14000e08d  jmp     short loc_14000E0BA
0x14000e08f  mov     r9d, ebp; cchCount2
0x14000e092  mov     [rsp+98h+bIgnoreCase], 1; bIgnoreCase
0x14000e09a  lea     r8, aNoshellregistr_0; "/NoShellRegistrationAndUACCheck"
0x14000e0a1  mov     edx, ebp; cchCount1
0x14000e0a3  mov     rcx, rdi; lpString1
0x14000e0a6  call    cs:__imp_CompareStringOrdinal
0x14000e0ac  cmp     eax, ebx
0x14000e0ae  jnz     loc_14000DF7A
0x14000e0b4  mov     bpl, 1
0x14000e0b7  mov     dil, bpl
0x14000e0ba  mov     bl, r12b
0x14000e0bd  jmp     loc_14000DFEC
0x14000e0c2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x14000e0c5  mov     rcx, r14; hHandle
0x14000e0c8  call    cs:__imp_WaitForSingleObject
0x14000e0ce  jmp     loc_14000E021
```
