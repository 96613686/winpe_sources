# AllocateAndCreateWellKnownSid(WELL_KNOWN_SID_TYPE,void * *)

- ea: `0x18002b22c`
- end: `0x18002b4a1`
- name: `?AllocateAndCreateWellKnownSid@@YAKW4WELL_KNOWN_SID_TYPE@@PEAPEAX@Z`
- size: `629`
- prototype: `unsigned int __fastcall(WELL_KNOWN_SID_TYPE WellKnownSidType, void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18002b4a8`
- `0x18002b978`

## callees

- `0x1800094e4`
- `0x18001cdcc`
- `0x18001d31c`
- `0x18002b22c`

## import_xrefs

- `KERNEL32!GlobalAlloc` at `0x18002b367`
- `KERNEL32!GlobalAlloc` at `0x18002b367`
- `KERNEL32!GlobalFree` at `0x18002b475`
- `KERNEL32!GlobalFree` at `0x18002b475`
- `KERNEL32!GetLastError` at `0x18002b2cb`
- `KERNEL32!GetLastError` at `0x18002b3e8`
- `KERNEL32!GetLastError` at `0x18002b2cb`
- `KERNEL32!GetLastError` at `0x18002b3e8`
- `ADVAPI32!CreateWellKnownSid` at `0x18002b269`
- `ADVAPI32!CreateWellKnownSid` at `0x18002b3da`
- `ADVAPI32!CreateWellKnownSid` at `0x18002b269`
- `ADVAPI32!CreateWellKnownSid` at `0x18002b3da`

## string_xrefs

- `0x18002b292`: `Creating a sid worked with no memory allocated for it.( This is not good )`
- `0x18002b314`: `Getting the SID length failed, can't create the sid (Type = %d), error = %x`
- `0x18002b428`: `Creating SID failed ( SidType = %d ), Error %x`

## pseudocode

```c
__int64 __fastcall AllocateAndCreateWellKnownSid(__int32 WellKnownSidType, void **a2)
{
  signed int LastError; // ebx
  char v6; // di
  HGLOBAL v7; // rax
  void *v8; // rbp
  char v9; // di
  SIZE_T dwBytes; // [rsp+58h] [rbp+10h] BYREF

  if ( !a2 || *a2 )
    return 87;
  LODWORD(dwBytes) = 0;
  if ( CreateWellKnownSid((WELL_KNOWN_SID_TYPE)WellKnownSidType, 0, 0, (DWORD *)&dwBytes) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WppDbgPrint("Creating a sid worked with no memory allocated for it.( This is not good )");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids, "NAPBASE");
    }
    return 13;
  }
  LastError = GetLastError();
  if ( LastError != 122 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v6 = LastError;
      WppDbgPrint("Getting the SID length failed, can't create the sid (Type = %d), error = %x");
      if ( LastError <= 0 )
        v6 = LastError;
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        (unsigned int)WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids,
        (unsigned int)"NAPBASE",
        WellKnownSidType,
        v6);
    }
    return (unsigned int)LastError;
  }
  v7 = GlobalAlloc(0, (unsigned int)dwBytes);
  v8 = v7;
  if ( v7 )
  {
    LastError = 0;
    if ( CreateWellKnownSid((WELL_KNOWN_SID_TYPE)WellKnownSidType, 0, v7, (DWORD *)&dwBytes) )
      goto LABEL_32;
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v9 = LastError;
      WppDbgPrint("Creating SID failed ( SidType = %d ), Error %x");
      if ( LastError <= 0 )
        v9 = LastError;
      WPP_SF_sdD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        (unsigned int)WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids,
        (unsigned int)"NAPBASE",
        WellKnownSidType,
        v9);
    }
    if ( !LastError )
LABEL_32:
      *a2 = v8;
    else
      GlobalFree(v8);
    return (unsigned int)LastError;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WppDbgPrint("GlobalAlloc failed. Out of memory");
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids, "NAPBASE");
  }
  return 8;
}

```

## disassembly

```asm
0x18002b22c  mov     rax, rsp
0x18002b22f  mov     [rax+8], rbx
0x18002b233  mov     [rax+18h], rbp
0x18002b237  push    rdi
0x18002b238  push    r14
0x18002b23a  push    r15
0x18002b23c  sub     rsp, 30h
0x18002b240  mov     r14, rdx
0x18002b243  mov     r15d, ecx
0x18002b246  test    rdx, rdx
0x18002b249  jz      loc_18002B488
0x18002b24f  cmp     qword ptr [rdx], 0
0x18002b253  jnz     loc_18002B488
0x18002b259  lea     r9, [rax+10h]; cbSid
0x18002b25d  mov     dword ptr [rax+10h], 0
0x18002b264  xor     r8d, r8d; pSid
0x18002b267  xor     edx, edx; DomainSid
0x18002b269  call    cs:__imp_CreateWellKnownSid
0x18002b26f  test    eax, eax
0x18002b271  jz      short loc_18002B2CB
0x18002b273  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b27a  lea     rax, WPP_GLOBAL_Control
0x18002b281  cmp     rcx, rax
0x18002b284  jz      short loc_18002B2C1
0x18002b286  cmp     byte ptr [rcx+19h], 2
0x18002b28a  jb      short loc_18002B2C1
0x18002b28c  test    byte ptr [rcx+1Ch], 1
0x18002b290  jz      short loc_18002B2C1
0x18002b292  lea     rcx, aCreatingASidWo; "Creating a sid worked with no memory al"...
0x18002b299  call    WppDbgPrint
0x18002b29e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b2a5  lea     r9, aNapbase; "NAPBASE"
0x18002b2ac  mov     edx, 11h
0x18002b2b1  lea     r8, WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids
0x18002b2b8  mov     rcx, [rcx+10h]
0x18002b2bc  call    WPP_SF_s
0x18002b2c1  mov     eax, 0Dh
0x18002b2c6  jmp     loc_18002B48D
0x18002b2cb  call    cs:__imp_GetLastError
0x18002b2d1  mov     ebx, eax
0x18002b2d3  cmp     eax, 7Ah ; 'z'
0x18002b2d6  jz      loc_18002B361
0x18002b2dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b2e3  lea     rax, WPP_GLOBAL_Control
0x18002b2ea  cmp     rcx, rax
0x18002b2ed  jz      short loc_18002B35A
0x18002b2ef  cmp     byte ptr [rcx+19h], 2
0x18002b2f3  jb      short loc_18002B35A
0x18002b2f5  test    byte ptr [rcx+1Ch], 1
0x18002b2f9  jz      short loc_18002B35A
0x18002b2fb  movzx   edi, bx
0x18002b2fe  test    ebx, ebx
0x18002b300  jg      short loc_18002B307
0x18002b302  mov     r8d, ebx
0x18002b305  jmp     short loc_18002B311
0x18002b307  mov     r8d, edi
0x18002b30a  or      r8d, 80070000h
0x18002b311  mov     edx, r15d
0x18002b314  lea     rcx, aGettingTheSidL; "Getting the SID length failed, can't cr"...
0x18002b31b  call    WppDbgPrint
0x18002b320  test    ebx, ebx
0x18002b322  jg      short loc_18002B328
0x18002b324  mov     edi, ebx
0x18002b326  jmp     short loc_18002B32E
0x18002b328  or      edi, 80070000h
0x18002b32e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b335  lea     r9, aNapbase; "NAPBASE"
0x18002b33c  mov     edx, 12h
0x18002b341  mov     [rsp+48h+var_20], edi
0x18002b345  lea     r8, WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids
0x18002b34c  mov     [rsp+48h+var_28], r15d
0x18002b351  mov     rcx, [rcx+10h]
0x18002b355  call    WPP_SF_sdD
0x18002b35a  mov     eax, ebx
0x18002b35c  jmp     loc_18002B48D
0x18002b361  mov     edx, dword ptr [rsp+48h+dwBytes]; dwBytes
0x18002b365  xor     ecx, ecx; uFlags
0x18002b367  call    cs:__imp_GlobalAlloc
0x18002b36d  mov     rbp, rax
0x18002b370  test    rax, rax
0x18002b373  jnz     short loc_18002B3CB
0x18002b375  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b37c  lea     rax, WPP_GLOBAL_Control
0x18002b383  cmp     rcx, rax
0x18002b386  jz      short loc_18002B3C1
0x18002b388  cmp     byte ptr [rcx+19h], 2
0x18002b38c  jb      short loc_18002B3C1
0x18002b38e  test    byte ptr [rcx+1Ch], 1
0x18002b392  jz      short loc_18002B3C1
0x18002b394  lea     rcx, aGlobalallocFai; "GlobalAlloc failed. Out of memory"
0x18002b39b  call    WppDbgPrint
0x18002b3a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b3a7  lea     edx, [rbp+13h]
0x18002b3aa  lea     r9, aNapbase; "NAPBASE"
0x18002b3b1  lea     r8, WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids
0x18002b3b8  mov     rcx, [rcx+10h]
0x18002b3bc  call    WPP_SF_s
0x18002b3c1  mov     eax, 8
0x18002b3c6  jmp     loc_18002B48D
0x18002b3cb  lea     r9, [rsp+48h+dwBytes]; cbSid
0x18002b3d0  mov     r8, rbp; pSid
0x18002b3d3  xor     edx, edx; DomainSid
0x18002b3d5  mov     ecx, r15d; WellKnownSidType
0x18002b3d8  xor     ebx, ebx
0x18002b3da  call    cs:__imp_CreateWellKnownSid
0x18002b3e0  test    eax, eax
0x18002b3e2  jnz     loc_18002B480
0x18002b3e8  call    cs:__imp_GetLastError
0x18002b3ee  mov     ebx, eax
0x18002b3f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b3f7  lea     rax, WPP_GLOBAL_Control
0x18002b3fe  cmp     rcx, rax
0x18002b401  jz      short loc_18002B46E
0x18002b403  cmp     byte ptr [rcx+19h], 2
0x18002b407  jb      short loc_18002B46E
0x18002b409  test    byte ptr [rcx+1Ch], 1
0x18002b40d  jz      short loc_18002B46E
0x18002b40f  movzx   edi, bx
0x18002b412  test    ebx, ebx
0x18002b414  jg      short loc_18002B41B
0x18002b416  mov     r8d, ebx
0x18002b419  jmp     short loc_18002B425
0x18002b41b  mov     r8d, edi
0x18002b41e  or      r8d, 80070000h
0x18002b425  mov     edx, r15d
0x18002b428  lea     rcx, aCreatingSidFai; "Creating SID failed ( SidType = %d ), E"...
0x18002b42f  call    WppDbgPrint
0x18002b434  test    ebx, ebx
0x18002b436  jg      short loc_18002B43C
0x18002b438  mov     edi, ebx
0x18002b43a  jmp     short loc_18002B442
0x18002b43c  or      edi, 80070000h
0x18002b442  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b449  lea     r9, aNapbase; "NAPBASE"
0x18002b450  mov     edx, 14h
0x18002b455  mov     [rsp+48h+var_20], edi
0x18002b459  lea     r8, WPP_2123c38dc5df3aafd8eedf6f403fe5a8_Traceguids
0x18002b460  mov     [rsp+48h+var_28], r15d
0x18002b465  mov     rcx, [rcx+10h]
0x18002b469  call    WPP_SF_sdD
0x18002b46e  test    ebx, ebx
0x18002b470  jz      short loc_18002B480
0x18002b472  mov     rcx, rbp; hMem
0x18002b475  call    cs:__imp_GlobalFree
0x18002b47b  jmp     loc_18002B35A
0x18002b480  mov     [r14], rbp
0x18002b483  jmp     loc_18002B35A
0x18002b488  mov     eax, 57h ; 'W'
0x18002b48d  mov     rbx, [rsp+48h+arg_0]
0x18002b492  mov     rbp, [rsp+48h+arg_10]
0x18002b497  add     rsp, 30h
0x18002b49b  pop     r15
0x18002b49d  pop     r14
0x18002b49f  pop     rdi
0x18002b4a0  retn
```
