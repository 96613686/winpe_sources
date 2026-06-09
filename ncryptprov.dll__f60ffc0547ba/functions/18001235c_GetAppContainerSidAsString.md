# GetAppContainerSidAsString

- ea: `0x18001235c`
- end: `0x18001255f`
- name: `GetAppContainerSidAsString`
- size: `515`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800121e4`
- `0x180052480`

## callees

- `0x18000af80`
- `0x18000b250`
- `0x18000d3d0`
- `0x18000def0`
- `0x18001235c`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x1800123f7`
- `ntdll!NtQueryInformationToken` at `0x180012458`
- `ntdll!NtQueryInformationToken` at `0x1800123f7`
- `ntdll!NtQueryInformationToken` at `0x180012458`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800124a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800124a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012542`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012542`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180012492`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180012492`

## string_xrefs

- `0x1800123b6`: `onecore\ds\security\cryptoapi\ncrypt\storage\appcontainer.c`
- `0x180012470`: `onecore\ds\security\cryptoapi\ncrypt\storage\appcontainer.c`
- `0x1800124da`: `onecore\ds\security\cryptoapi\ncrypt\storage\appcontainer.c`
- `0x180012525`: `onecore\ds\security\cryptoapi\ncrypt\storage\appcontainer.c`

## pseudocode

```c
__int64 __fastcall GetAppContainerSidAsString(HANDLE TokenHandle, LPWSTR *a2)
{
  unsigned int v4; // ebx
  PSID *v5; // rdi
  __int64 v6; // r9
  __int64 v7; // rcx
  unsigned int v8; // eax
  signed int LastError; // eax
  int v10; // edx
  ULONG TokenInformationLength; // [rsp+60h] [rbp+8h] BYREF
  LPWSTR StringSid; // [rsp+68h] [rbp+10h] BYREF

  TokenInformationLength = 0;
  StringSid = 0;
  *a2 = 0;
  if ( TokenHandle )
  {
    v4 = NtQueryInformationToken(TokenHandle, TokenAppContainerSid, 0, 0, &TokenInformationLength);
    if ( v4 == -1073741789 && TokenInformationLength )
    {
      v5 = (PSID *)SafeAllocaAllocateFromHeap(TokenInformationLength);
      if ( v5 )
      {
        v8 = NtQueryInformationToken(
               TokenHandle,
               TokenAppContainerSid,
               v5,
               TokenInformationLength,
               &TokenInformationLength);
        v4 = v8;
        if ( v8 )
        {
          DebugTraceError(v8, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\appcontainer.c", 109);
        }
        else if ( ConvertSidToStringSidW(*v5, &StringSid) )
        {
          v4 = 0;
          *a2 = StringSid;
          StringSid = 0;
        }
        else
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError > 0 )
            v4 = (unsigned __int16)LastError | 0x80070000;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v10,
              (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\appcontainer.c",
              (unsigned int)"Status",
              v4,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\appcontainer.c",
              121);
        }
        MSCryptFree(v5);
        goto LABEL_21;
      }
      v4 = -2146893810;
      v6 = 96;
      v7 = 2148073486LL;
    }
    else
    {
      v6 = 88;
      v7 = v4;
    }
    DebugTraceError(v7, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\appcontainer.c", v6);
  }
  else
  {
    v4 = -2146893785;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return v4;
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)a2,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\appcontainer.c",
      (unsigned int)"Status",
      39,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\appcontainer.c",
      73);
  }
LABEL_21:
  if ( StringSid )
    LocalFree(StringSid);
  return v4;
}

```

## disassembly

```asm
0x18001235c  mov     [rsp+arg_10], rbx
0x180012361  push    rsi
0x180012362  push    rdi
0x180012363  push    r14
0x180012365  sub     rsp, 40h
0x180012369  mov     [rsp+58h+TokenInformationLength], 0
0x180012371  mov     r14, rdx
0x180012374  mov     [rsp+58h+StringSid], 0
0x18001237d  mov     rsi, rcx
0x180012380  mov     qword ptr [rdx], 0
0x180012387  test    rcx, rcx
0x18001238a  jnz     short loc_1800123E3
0x18001238c  mov     ebx, 80090027h
0x180012391  mov     rcx, cs:WPP_GLOBAL_Control
0x180012398  lea     rax, WPP_GLOBAL_Control
0x18001239f  cmp     rcx, rax
0x1800123a2  jz      loc_18001254E
0x1800123a8  test    byte ptr [rcx+1Ch], 1
0x1800123ac  jz      loc_18001254E
0x1800123b2  mov     rcx, [rcx+10h]
0x1800123b6  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800123bd  mov     [rsp+58h+var_28], 49h ; 'I'
0x1800123c5  lea     r9, aStatus; "Status"
0x1800123cc  mov     [rsp+58h+var_30], r8
0x1800123d1  mov     dword ptr [rsp+58h+ReturnLength], 80090027h
0x1800123d9  call    WPP_SF_sDsd
0x1800123de  jmp     loc_180012538
0x1800123e3  xor     r9d, r9d; TokenInformationLength
0x1800123e6  lea     rax, [rsp+58h+TokenInformationLength]
0x1800123eb  xor     r8d, r8d; TokenInformation
0x1800123ee  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1800123f3  lea     edx, [r9+1Fh]; TokenInformationClass
0x1800123f7  call    cs:__imp_NtQueryInformationToken
0x1800123fe  nop     dword ptr [rax+rax+00h]
0x180012403  mov     ebx, eax
0x180012405  cmp     eax, 0C0000023h
0x18001240a  jnz     loc_18001251D
0x180012410  mov     eax, [rsp+58h+TokenInformationLength]
0x180012414  test    eax, eax
0x180012416  jz      loc_18001251D
0x18001241c  mov     ecx, eax
0x18001241e  call    SafeAllocaAllocateFromHeap
0x180012423  mov     rdi, rax
0x180012426  test    rax, rax
0x180012429  jnz     short loc_18001243E
0x18001242b  mov     ebx, 8009000Eh
0x180012430  lea     r9d, [rax+60h]
0x180012434  mov     ecx, 8009000Eh
0x180012439  jmp     loc_180012525
0x18001243e  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x180012443  lea     rax, [rsp+58h+TokenInformationLength]
0x180012448  mov     r8, rdi; TokenInformation
0x18001244b  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180012450  mov     edx, 1Fh; TokenInformationClass
0x180012455  mov     rcx, rsi; TokenHandle
0x180012458  call    cs:__imp_NtQueryInformationToken
0x18001245f  nop     dword ptr [rax+rax+00h]
0x180012464  mov     ebx, eax
0x180012466  test    eax, eax
0x180012468  jz      short loc_18001248A
0x18001246a  mov     r9d, 6Dh ; 'm'
0x180012470  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180012477  lea     rdx, aStatus; "Status"
0x18001247e  mov     ecx, eax
0x180012480  call    DebugTraceError
0x180012485  jmp     loc_180012513
0x18001248a  mov     rcx, [rdi]; Sid
0x18001248d  lea     rdx, [rsp+58h+StringSid]; StringSid
0x180012492  call    cs:__imp_ConvertSidToStringSidW
0x180012499  nop     dword ptr [rax+rax+00h]
0x18001249e  test    eax, eax
0x1800124a0  jnz     short loc_180012500
0x1800124a2  call    cs:__imp_GetLastError
0x1800124a9  nop     dword ptr [rax+rax+00h]
0x1800124ae  mov     ebx, eax
0x1800124b0  test    eax, eax
0x1800124b2  jle     short loc_1800124BD
0x1800124b4  movzx   ebx, ax
0x1800124b7  or      ebx, 80070000h
0x1800124bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800124c4  lea     rax, WPP_GLOBAL_Control
0x1800124cb  cmp     rcx, rax
0x1800124ce  jz      short loc_180012513
0x1800124d0  test    byte ptr [rcx+1Ch], 1
0x1800124d4  jz      short loc_180012513
0x1800124d6  mov     rcx, [rcx+10h]
0x1800124da  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800124e1  mov     [rsp+58h+var_28], 79h ; 'y'
0x1800124e9  lea     r9, aStatus; "Status"
0x1800124f0  mov     [rsp+58h+var_30], r8
0x1800124f5  mov     dword ptr [rsp+58h+ReturnLength], ebx
0x1800124f9  call    WPP_SF_sDsd
0x1800124fe  jmp     short loc_180012513
0x180012500  mov     rax, [rsp+58h+StringSid]
0x180012505  xor     ebx, ebx
0x180012507  mov     [r14], rax
0x18001250a  mov     [rsp+58h+StringSid], 0
0x180012513  mov     rcx, rdi
0x180012516  call    MSCryptFree
0x18001251b  jmp     short loc_180012538
0x18001251d  mov     r9d, 58h ; 'X'
0x180012523  mov     ecx, ebx
0x180012525  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001252c  lea     rdx, aStatus; "Status"
0x180012533  call    DebugTraceError
0x180012538  mov     rcx, [rsp+58h+StringSid]; hMem
0x18001253d  test    rcx, rcx
0x180012540  jz      short loc_18001254E
0x180012542  call    cs:__imp_LocalFree
0x180012549  nop     dword ptr [rax+rax+00h]
0x18001254e  mov     eax, ebx
0x180012550  mov     rbx, [rsp+58h+arg_10]
0x180012555  add     rsp, 40h
0x180012559  pop     r14
0x18001255b  pop     rdi
0x18001255c  pop     rsi
0x18001255d  retn
```
