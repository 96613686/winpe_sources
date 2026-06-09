# IsUserSecuritySetInKey(HKEY__ *,ushort const *,bool *)

- ea: `0x180018030`
- end: `0x1800181c1`
- name: `?IsUserSecuritySetInKey@@YAJPEAUHKEY__@@PEBGPEA_N@Z`
- size: `401`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180016150`

## callees

- `0x180018030`
- `0x18002df48`
- `0x180031060`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800180da`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1800180da`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180018103`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180018103`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018123`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018138`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018180`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018190`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018123`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018138`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018180`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018190`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800180aa`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800180aa`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180018087`
- `api-ms-win-security-provider-l1-1-0!GetSecurityInfo` at `0x180018087`

## string_xrefs

- `0x18001815b`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x1800181a2`: `onecore\ds\security\gina\profile\profsvc\util.cpp`

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
0x180018030  mov     r11, rsp
0x180018033  mov     [r11+8], rbx
0x180018037  mov     [r11+10h], rdi
0x18001803b  push    rbp
0x18001803c  mov     rbp, rsp
0x18001803f  sub     rsp, 50h
0x180018043  xor     r9d, r9d; ppsidOwner
0x180018046  mov     byte ptr [r8], 0
0x18001804a  lea     rax, [rbp+hMem]
0x18001804e  mov     [rbp+pAcl], 0
0x180018056  mov     [r11-20h], rax
0x18001805a  mov     rbx, rdx
0x18001805d  mov     qword ptr [r11-28h], 0
0x180018065  lea     rax, [rbp+pAcl]
0x180018069  lea     edx, [r9+4]; ObjectType
0x18001806d  mov     [r11-30h], rax
0x180018071  mov     rdi, r8
0x180018074  mov     [rbp+hMem], 0
0x18001807c  mov     r8d, edx; SecurityInfo
0x18001807f  mov     qword ptr [r11-38h], 0
0x180018087  call    cs:__imp_GetSecurityInfo
0x18001808e  nop     dword ptr [rax+rax+00h]
0x180018093  test    eax, eax
0x180018095  jnz     loc_18001819E
0x18001809b  lea     rdx, [rbp+Sid]; Sid
0x18001809f  mov     [rbp+Sid], 0
0x1800180a7  mov     rcx, rbx; StringSid
0x1800180aa  call    cs:__imp_ConvertStringSidToSidW
0x1800180b1  nop     dword ptr [rax+rax+00h]
0x1800180b6  test    eax, eax
0x1800180b8  jz      loc_180018157
0x1800180be  xor     ebx, ebx
0x1800180c0  mov     rcx, [rbp+pAcl]; pAcl
0x1800180c4  movzx   eax, word ptr [rcx+4]
0x1800180c8  cmp     ebx, eax
0x1800180ca  jnb     short loc_18001811A
0x1800180cc  lea     r8, [rbp+pAce]; pAce
0x1800180d0  mov     [rbp+pAce], 0
0x1800180d8  mov     edx, ebx; dwAceIndex
0x1800180da  call    cs:__imp_GetAce
0x1800180e1  nop     dword ptr [rax+rax+00h]
0x1800180e6  test    eax, eax
0x1800180e8  jz      loc_1800181BA
0x1800180ee  mov     rcx, [rbp+pAce]
0x1800180f2  cmp     byte ptr [rcx], 0
0x1800180f5  jnz     loc_1800181BA
0x1800180fb  mov     rdx, [rbp+Sid]; pSid2
0x1800180ff  add     rcx, 8; pSid1
0x180018103  call    cs:__imp_EqualSid
0x18001810a  nop     dword ptr [rax+rax+00h]
0x18001810f  test    eax, eax
0x180018111  jz      loc_1800181BA
0x180018117  mov     byte ptr [rdi], 1
0x18001811a  mov     rcx, [rbp+Sid]; hMem
0x18001811e  test    rcx, rcx
0x180018121  jz      short loc_18001812F
0x180018123  call    cs:__imp_LocalFree
0x18001812a  nop     dword ptr [rax+rax+00h]
0x18001812f  mov     rcx, [rbp+hMem]; hMem
0x180018133  test    rcx, rcx
0x180018136  jz      short loc_180018144
0x180018138  call    cs:__imp_LocalFree
0x18001813f  nop     dword ptr [rax+rax+00h]
0x180018144  xor     eax, eax
0x180018146  mov     rbx, [rsp+50h+arg_0]
0x18001814b  mov     rdi, [rsp+50h+arg_8]
0x180018150  add     rsp, 50h
0x180018154  pop     rbp
0x180018155  retn
0x180018157  mov     rcx, [rbp+8]; this
0x18001815b  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180018162  mov     edx, 63Eh; void *
0x180018167  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001816c  mov     rcx, [rbp+Sid]; hMem
0x180018170  mov     ebx, eax
0x180018172  test    rcx, rcx
0x180018175  jnz     short loc_180018190
0x180018177  mov     rcx, [rbp+hMem]; hMem
0x18001817b  test    rcx, rcx
0x18001817e  jz      short loc_18001818C
0x180018180  call    cs:__imp_LocalFree
0x180018187  nop     dword ptr [rax+rax+00h]
0x18001818c  mov     eax, ebx
0x18001818e  jmp     short loc_180018146
0x180018190  call    cs:__imp_LocalFree
0x180018197  nop     dword ptr [rax+rax+00h]
0x18001819c  jmp     short loc_180018177
0x18001819e  mov     rcx, [rbp+8]; this
0x1800181a2  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800181a9  mov     r9d, eax; char *
0x1800181ac  mov     edx, 63Bh; void *
0x1800181b1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800181b6  mov     ebx, eax
0x1800181b8  jmp     short loc_180018177
0x1800181ba  inc     ebx
0x1800181bc  jmp     loc_1800180C0
```
