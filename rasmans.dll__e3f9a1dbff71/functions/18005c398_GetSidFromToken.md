# GetSidFromToken

- ea: `0x18005c398`
- end: `0x18005c709`
- name: `GetSidFromToken`
- size: `881`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005c710`
- `0x180069260`
- `0x180069ab4`
- `0x18008117c`

## callees

- `0x180005e34`
- `0x180005f1c`
- `0x18000e4f0`
- `0x18005c398`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c43c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c4cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c52c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c57f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c43c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c4cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c52c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c57f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005c432`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005c522`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005c432`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005c522`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18005c4bd`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18005c5d2`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18005c4bd`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18005c5d2`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005c64a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005c6b5`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005c64a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005c6b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c692`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c692`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18005c5bf`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18005c5bf`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005c575`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005c575`

## pseudocode

```c
__int64 __fastcall GetSidFromToken(HANDLE TokenHandle, HGLOBAL *a2)
{
  struct _LIST_ENTRY *v4; // rcx
  DWORD LastError; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // r9
  PSID *v9; // r14
  DWORD v10; // eax
  struct _LIST_ENTRY *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  size_t v14; // rbx
  wchar_t *v15; // rax
  unsigned __int16 v16; // ax
  DWORD TokenInformationLength; // [rsp+50h] [rbp+8h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp+18h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_q(WPP_GLOBAL_Control[1].Flink, 19, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids, TokenHandle);
    v4 = WPP_GLOBAL_Control;
  }
  StringSid = 0;
  TokenInformationLength = 0;
  if ( TokenHandle == (HANDLE)-1LL || !a2 )
  {
    v6 = 87;
    if ( v4 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v4[1].Blink) & 4) == 0 || BYTE1(v4[1].Blink) < 2u )
    {
LABEL_60:
      if ( *a2 )
      {
        GlobalFree(*a2);
        v4 = WPP_GLOBAL_Control;
        *a2 = 0;
      }
      goto LABEL_62;
    }
    v7 = 20;
    v8 = 87;
    goto LABEL_55;
  }
  *a2 = 0;
  if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError != 122 )
    {
      if ( LastError )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          v7 = 21;
LABEL_14:
          v8 = LastError;
LABEL_55:
          WPP_SF_d(v4[1].Flink, v7, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids, v8);
          goto LABEL_56;
        }
        goto LABEL_57;
      }
LABEL_56:
      v4 = WPP_GLOBAL_Control;
      goto LABEL_57;
    }
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 22, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids, 122);
    }
  }
  v9 = (PSID *)GlobalAlloc(0x40u, TokenInformationLength);
  if ( v9 )
  {
    if ( GetTokenInformation(TokenHandle, TokenUser, v9, TokenInformationLength, &TokenInformationLength) )
    {
      if ( ConvertSidToStringSidW(*v9, &StringSid) )
      {
        v14 = (unsigned int)(lstrlenW(StringSid) + 1);
        v15 = (wchar_t *)GlobalAlloc(0x40u, 2 * v14);
        *a2 = v15;
        if ( v15 )
        {
          v16 = StringCchCopyW(v15, v14, StringSid);
          v6 = v16;
          if ( !v16 )
            goto LABEL_50;
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) == 0
            || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          {
            goto LABEL_50;
          }
          v12 = 27;
        }
        else
        {
          v6 = 14;
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) == 0
            || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
          {
            goto LABEL_50;
          }
          v12 = 26;
        }
        v13 = v6;
        goto LABEL_49;
      }
      v10 = GetLastError();
      v6 = v10;
      if ( !v10 )
        goto LABEL_50;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_50;
      }
      v12 = 25;
    }
    else
    {
      v10 = GetLastError();
      v6 = v10;
      if ( !v10 )
        goto LABEL_50;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_50;
      }
      v12 = 24;
    }
    v13 = v10;
LABEL_49:
    WPP_SF_d(v11[1].Flink, v12, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids, v13);
LABEL_50:
    GlobalFree(v9);
    goto LABEL_56;
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( !LastError )
    goto LABEL_56;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    v7 = 23;
    goto LABEL_14;
  }
LABEL_57:
  if ( StringSid )
  {
    LocalFree(StringSid);
    v4 = WPP_GLOBAL_Control;
    StringSid = 0;
  }
  if ( v6 )
    goto LABEL_60;
LABEL_62:
  if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v4[1].Blink) & 4) != 0 && BYTE1(v4[1].Blink) >= 6u )
    WPP_SF_d(v4[1].Flink, 28, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x18005c398  mov     [rsp+arg_8], rbx
0x18005c39d  mov     [rsp+arg_18], rsi
0x18005c3a2  push    r13
0x18005c3a4  push    r14
0x18005c3a6  push    r15
0x18005c3a8  sub     rsp, 30h
0x18005c3ac  mov     r15, rdx
0x18005c3af  mov     rsi, rcx
0x18005c3b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c3b9  lea     r13, WPP_GLOBAL_Control
0x18005c3c0  cmp     rcx, r13
0x18005c3c3  jz      short loc_18005C3F0
0x18005c3c5  test    byte ptr [rcx+1Ch], 4
0x18005c3c9  jz      short loc_18005C3F0
0x18005c3cb  cmp     byte ptr [rcx+19h], 6
0x18005c3cf  jb      short loc_18005C3F0
0x18005c3d1  mov     rcx, [rcx+10h]
0x18005c3d5  lea     r8, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids
0x18005c3dc  mov     edx, 13h
0x18005c3e1  mov     r9, rsi
0x18005c3e4  call    WPP_SF_q
0x18005c3e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c3f0  mov     [rsp+48h+StringSid], 0
0x18005c3f9  mov     [rsp+48h+TokenInformationLength], 0
0x18005c401  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18005c405  jz      loc_18005C652
0x18005c40b  test    r15, r15
0x18005c40e  jz      loc_18005C652
0x18005c414  xor     r9d, r9d; TokenInformationLength
0x18005c417  mov     qword ptr [r15], 0
0x18005c41e  lea     rax, [rsp+48h+TokenInformationLength]
0x18005c423  xor     r8d, r8d; TokenInformation
0x18005c426  mov     rcx, rsi; TokenHandle
0x18005c429  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18005c42e  lea     edx, [r9+1]; TokenInformationClass
0x18005c432  call    cs:__imp_GetTokenInformation
0x18005c438  test    eax, eax
0x18005c43a  jnz     short loc_18005C4B4
0x18005c43c  call    cs:__imp_GetLastError
0x18005c442  mov     r9d, 7Ah ; 'z'
0x18005c448  mov     ebx, eax
0x18005c44a  cmp     eax, r9d
0x18005c44d  jz      short loc_18005C487
0x18005c44f  test    eax, eax
0x18005c451  jz      loc_18005C67E
0x18005c457  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c45e  cmp     rcx, r13
0x18005c461  jz      loc_18005C685
0x18005c467  test    byte ptr [rcx+1Ch], 4
0x18005c46b  jz      loc_18005C685
0x18005c471  cmp     byte ptr [rcx+19h], 2
0x18005c475  jb      loc_18005C685
0x18005c47b  lea     edx, [r9-65h]
0x18005c47f  mov     r9d, eax
0x18005c482  jmp     loc_18005C66E
0x18005c487  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c48e  cmp     rcx, r13
0x18005c491  jz      short loc_18005C4B4
0x18005c493  test    byte ptr [rcx+1Ch], 4
0x18005c497  jz      short loc_18005C4B4
0x18005c499  cmp     byte ptr [rcx+19h], 2
0x18005c49d  jb      short loc_18005C4B4
0x18005c49f  mov     rcx, [rcx+10h]
0x18005c4a3  lea     r8, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids
0x18005c4aa  mov     edx, 16h
0x18005c4af  call    WPP_SF_d
0x18005c4b4  mov     edx, [rsp+48h+TokenInformationLength]; dwBytes
0x18005c4b8  mov     ecx, 40h ; '@'; uFlags
0x18005c4bd  call    cs:__imp_GlobalAlloc
0x18005c4c3  mov     r14, rax
0x18005c4c6  test    rax, rax
0x18005c4c9  jnz     short loc_18005C508
0x18005c4cb  call    cs:__imp_GetLastError
0x18005c4d1  mov     ebx, eax
0x18005c4d3  test    eax, eax
0x18005c4d5  jz      loc_18005C67E
0x18005c4db  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c4e2  cmp     rcx, r13
0x18005c4e5  jz      loc_18005C685
0x18005c4eb  test    byte ptr [rcx+1Ch], 4
0x18005c4ef  jz      loc_18005C685
0x18005c4f5  cmp     byte ptr [rcx+19h], 2
0x18005c4f9  jb      loc_18005C685
0x18005c4ff  lea     edx, [r14+17h]
0x18005c503  jmp     loc_18005C47F
0x18005c508  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18005c50d  lea     rax, [rsp+48h+TokenInformationLength]
0x18005c512  mov     r8, r14; TokenInformation
0x18005c515  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18005c51a  mov     edx, 1; TokenInformationClass
0x18005c51f  mov     rcx, rsi; TokenHandle
0x18005c522  call    cs:__imp_GetTokenInformation
0x18005c528  test    eax, eax
0x18005c52a  jnz     short loc_18005C56D
0x18005c52c  call    cs:__imp_GetLastError
0x18005c532  mov     ebx, eax
0x18005c534  test    eax, eax
0x18005c536  jz      loc_18005C647
0x18005c53c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c543  cmp     rcx, r13
0x18005c546  jz      loc_18005C647
0x18005c54c  test    byte ptr [rcx+1Ch], 4
0x18005c550  jz      loc_18005C647
0x18005c556  cmp     byte ptr [rcx+19h], 2
0x18005c55a  jb      loc_18005C647
0x18005c560  mov     edx, 18h
0x18005c565  mov     r9d, eax
0x18005c568  jmp     loc_18005C637
0x18005c56d  mov     rcx, [r14]; Sid
0x18005c570  lea     rdx, [rsp+48h+StringSid]; StringSid
0x18005c575  call    cs:__imp_ConvertSidToStringSidW
0x18005c57b  test    eax, eax
0x18005c57d  jnz     short loc_18005C5BA
0x18005c57f  call    cs:__imp_GetLastError
0x18005c585  mov     ebx, eax
0x18005c587  test    eax, eax
0x18005c589  jz      loc_18005C647
0x18005c58f  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c596  cmp     rcx, r13
0x18005c599  jz      loc_18005C647
0x18005c59f  test    byte ptr [rcx+1Ch], 4
0x18005c5a3  jz      loc_18005C647
0x18005c5a9  cmp     byte ptr [rcx+19h], 2
0x18005c5ad  jb      loc_18005C647
0x18005c5b3  mov     edx, 19h
0x18005c5b8  jmp     short loc_18005C565
0x18005c5ba  mov     rcx, [rsp+48h+StringSid]; lpString
0x18005c5bf  call    cs:__imp_lstrlenW
0x18005c5c5  inc     eax
0x18005c5c7  mov     ecx, 40h ; '@'; uFlags
0x18005c5cc  mov     ebx, eax
0x18005c5ce  lea     rdx, [rax+rax]; dwBytes
0x18005c5d2  call    cs:__imp_GlobalAlloc
0x18005c5d8  mov     [r15], rax
0x18005c5db  test    rax, rax
0x18005c5de  jnz     short loc_18005C600
0x18005c5e0  lea     ebx, [rax+0Eh]
0x18005c5e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c5ea  cmp     rcx, r13
0x18005c5ed  jz      short loc_18005C647
0x18005c5ef  test    byte ptr [rcx+1Ch], 4
0x18005c5f3  jz      short loc_18005C647
0x18005c5f5  cmp     byte ptr [rcx+19h], 2
0x18005c5f9  jb      short loc_18005C647
0x18005c5fb  lea     edx, [rax+1Ah]
0x18005c5fe  jmp     short loc_18005C634
0x18005c600  mov     r8, [rsp+48h+StringSid]; pszSrc
0x18005c605  mov     rdx, rbx; cchDest
0x18005c608  mov     rcx, rax; pszDest
0x18005c60b  call    StringCchCopyW
0x18005c610  movzx   ebx, ax
0x18005c613  test    ebx, ebx
0x18005c615  jz      short loc_18005C647
0x18005c617  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c61e  cmp     rcx, r13
0x18005c621  jz      short loc_18005C647
0x18005c623  test    byte ptr [rcx+1Ch], 4
0x18005c627  jz      short loc_18005C647
0x18005c629  cmp     byte ptr [rcx+19h], 2
0x18005c62d  jb      short loc_18005C647
0x18005c62f  mov     edx, 1Bh
0x18005c634  mov     r9d, ebx
0x18005c637  mov     rcx, [rcx+10h]
0x18005c63b  lea     r8, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids
0x18005c642  call    WPP_SF_d
0x18005c647  mov     rcx, r14; hMem
0x18005c64a  call    cs:__imp_GlobalFree
0x18005c650  jmp     short loc_18005C67E
0x18005c652  mov     ebx, 57h ; 'W'
0x18005c657  cmp     rcx, r13
0x18005c65a  jz      short loc_18005C6AC
0x18005c65c  test    byte ptr [rcx+1Ch], 4
0x18005c660  jz      short loc_18005C6AC
0x18005c662  cmp     byte ptr [rcx+19h], 2
0x18005c666  jb      short loc_18005C6AC
0x18005c668  lea     edx, [rbx-43h]
0x18005c66b  mov     r9d, ebx
0x18005c66e  mov     rcx, [rcx+10h]
0x18005c672  lea     r8, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids
0x18005c679  call    WPP_SF_d
0x18005c67e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c685  mov     rax, [rsp+48h+StringSid]
0x18005c68a  test    rax, rax
0x18005c68d  jz      short loc_18005C6A8
0x18005c68f  mov     rcx, rax; hMem
0x18005c692  call    cs:__imp_LocalFree
0x18005c698  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c69f  mov     [rsp+48h+StringSid], 0
0x18005c6a8  test    ebx, ebx
0x18005c6aa  jz      short loc_18005C6C9
0x18005c6ac  cmp     qword ptr [r15], 0
0x18005c6b0  jz      short loc_18005C6C9
0x18005c6b2  mov     rcx, [r15]; hMem
0x18005c6b5  call    cs:__imp_GlobalFree
0x18005c6bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c6c2  mov     qword ptr [r15], 0
0x18005c6c9  cmp     rcx, r13
0x18005c6cc  jz      short loc_18005C6F2
0x18005c6ce  test    byte ptr [rcx+1Ch], 4
0x18005c6d2  jz      short loc_18005C6F2
0x18005c6d4  cmp     byte ptr [rcx+19h], 6
0x18005c6d8  jb      short loc_18005C6F2
0x18005c6da  mov     rcx, [rcx+10h]
0x18005c6de  lea     r8, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids
0x18005c6e5  mov     edx, 1Ch
0x18005c6ea  mov     r9d, ebx
0x18005c6ed  call    WPP_SF_d
0x18005c6f2  mov     rsi, [rsp+48h+arg_18]
0x18005c6f7  mov     eax, ebx
0x18005c6f9  mov     rbx, [rsp+48h+arg_8]
0x18005c6fe  add     rsp, 30h
0x18005c702  pop     r15
0x18005c704  pop     r14
0x18005c706  pop     r13
0x18005c708  retn
```
