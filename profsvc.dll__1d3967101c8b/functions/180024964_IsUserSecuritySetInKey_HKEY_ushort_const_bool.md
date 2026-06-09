# IsUserSecuritySetInKey(HKEY__ *,ushort const *,bool *)

- ea: `0x180024964`
- end: `0x180024ac4`
- name: `?IsUserSecuritySetInKey@@YAJPEAUHKEY__@@PEBGPEA_N@Z`
- size: `352`
- prototype: `int(HKEY, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180011200`

## callees

- `0x180024964`
- `0x18002db38`
- `0x18002e648`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180024a02`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180024a02`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180024a25`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180024a25`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024a3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024a4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024a8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024a99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024a3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024a4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024a8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024a99`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800249d8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800249d8`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x1800249bb`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x1800249bb`

## string_xrefs

- `0x180024a6a`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180024aa5`: `onecore\ds\security\gina\profile\profsvc\util.cpp`

## pseudocode

```c
__int64 __fastcall IsUserSecuritySetInKey(HKEY a1, const unsigned __int16 *a2, bool *a3)
{
  DWORD SecurityInfo; // eax
  const char *v6; // r9
  DWORD i; // ebx
  unsigned int LastError; // ebx
  unsigned int v10; // [rsp+20h] [rbp-30h]
  PACL pAcl; // [rsp+40h] [rbp-10h] BYREF
  LPVOID pAce; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  PSID Sid; // [rsp+70h] [rbp+20h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp+28h] BYREF

  *a3 = 0;
  pAcl = 0;
  hMem = 0;
  SecurityInfo = GetSecurityInfo(a1, SE_REGISTRY_KEY, 4u, 0, 0, &pAcl, 0, &hMem);
  if ( SecurityInfo )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x63B,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
                  (const char *)SecurityInfo,
                  v10);
LABEL_16:
    if ( hMem )
      LocalFree(hMem);
    return LastError;
  }
  Sid = 0;
  if ( !ConvertStringSidToSidW(a2, &Sid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x63E,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
                  v6);
    if ( Sid )
      LocalFree(Sid);
    goto LABEL_16;
  }
  for ( i = 0; i < pAcl->AceCount; ++i )
  {
    pAce = 0;
    if ( GetAce(pAcl, i, &pAce) && !*(_BYTE *)pAce && EqualSid((char *)pAce + 8, Sid) )
    {
      *a3 = 1;
      break;
    }
  }
  if ( Sid )
    LocalFree(Sid);
  if ( hMem )
    LocalFree(hMem);
  return 0;
}

```

## disassembly

```asm
0x180024964  mov     r11, rsp
0x180024967  mov     [r11+8], rbx
0x18002496b  mov     [r11+10h], rdi
0x18002496f  push    rbp
0x180024970  mov     rbp, rsp
0x180024973  sub     rsp, 50h
0x180024977  xor     r9d, r9d; ppsidOwner
0x18002497a  mov     byte ptr [r8], 0
0x18002497e  lea     rax, [rbp+hMem]
0x180024982  mov     [rbp+pAcl], 0
0x18002498a  mov     [r11-20h], rax
0x18002498e  mov     rbx, rdx
0x180024991  mov     qword ptr [r11-28h], 0
0x180024999  lea     rax, [rbp+pAcl]
0x18002499d  lea     edx, [r9+4]; ObjectType
0x1800249a1  mov     [r11-30h], rax
0x1800249a5  mov     rdi, r8
0x1800249a8  mov     [rbp+hMem], 0
0x1800249b0  mov     r8d, edx; SecurityInfo
0x1800249b3  mov     qword ptr [r11-38h], 0
0x1800249bb  call    cs:__imp_GetSecurityInfo
0x1800249c1  test    eax, eax
0x1800249c3  jnz     loc_180024AA1
0x1800249c9  lea     rdx, [rbp+Sid]; Sid
0x1800249cd  mov     [rbp+Sid], 0
0x1800249d5  mov     rcx, rbx; StringSid
0x1800249d8  call    cs:__imp_ConvertStringSidToSidW
0x1800249de  test    eax, eax
0x1800249e0  jz      loc_180024A66
0x1800249e6  xor     ebx, ebx
0x1800249e8  mov     rcx, [rbp+pAcl]; pAcl
0x1800249ec  movzx   eax, word ptr [rcx+4]
0x1800249f0  cmp     ebx, eax
0x1800249f2  jnb     short loc_180024A36
0x1800249f4  lea     r8, [rbp+pAce]; pAce
0x1800249f8  mov     [rbp+pAce], 0
0x180024a00  mov     edx, ebx; dwAceIndex
0x180024a02  call    cs:__imp_GetAce
0x180024a08  test    eax, eax
0x180024a0a  jz      loc_180024ABD
0x180024a10  mov     rcx, [rbp+pAce]
0x180024a14  cmp     byte ptr [rcx], 0
0x180024a17  jnz     loc_180024ABD
0x180024a1d  mov     rdx, [rbp+Sid]; pSid2
0x180024a21  add     rcx, 8; pSid1
0x180024a25  call    cs:__imp_EqualSid
0x180024a2b  test    eax, eax
0x180024a2d  jz      loc_180024ABD
0x180024a33  mov     byte ptr [rdi], 1
0x180024a36  mov     rcx, [rbp+Sid]; hMem
0x180024a3a  test    rcx, rcx
0x180024a3d  jz      short loc_180024A45
0x180024a3f  call    cs:__imp_LocalFree
0x180024a45  mov     rcx, [rbp+hMem]; hMem
0x180024a49  test    rcx, rcx
0x180024a4c  jz      short loc_180024A54
0x180024a4e  call    cs:__imp_LocalFree
0x180024a54  xor     eax, eax
0x180024a56  mov     rbx, [rsp+50h+arg_0]
0x180024a5b  mov     rdi, [rsp+50h+arg_8]
0x180024a60  add     rsp, 50h
0x180024a64  pop     rbp
0x180024a65  retn
0x180024a66  mov     rcx, [rbp+8]; this
0x180024a6a  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180024a71  mov     edx, 63Eh; void *
0x180024a76  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180024a7b  mov     rcx, [rbp+Sid]; hMem
0x180024a7f  mov     ebx, eax
0x180024a81  test    rcx, rcx
0x180024a84  jnz     short loc_180024A99
0x180024a86  mov     rcx, [rbp+hMem]; hMem
0x180024a8a  test    rcx, rcx
0x180024a8d  jz      short loc_180024A95
0x180024a8f  call    cs:__imp_LocalFree
0x180024a95  mov     eax, ebx
0x180024a97  jmp     short loc_180024A56
0x180024a99  call    cs:__imp_LocalFree
0x180024a9f  jmp     short loc_180024A86
0x180024aa1  mov     rcx, [rbp+8]; this
0x180024aa5  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180024aac  mov     r9d, eax; char *
0x180024aaf  mov     edx, 63Bh; void *
0x180024ab4  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180024ab9  mov     ebx, eax
0x180024abb  jmp     short loc_180024A86
0x180024abd  inc     ebx
0x180024abf  jmp     loc_1800249E8
```
