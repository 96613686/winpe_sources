# GetSidFromToken

- ea: `0x18005f32c`
- end: `0x18005f6ec`
- name: `GetSidFromToken`
- size: `960`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005f6f4`
- `0x18006cc28`
- `0x18006d4c4`
- `0x180085424`

## callees

- `0x180005bfc`
- `0x180005cf8`
- `0x18000eae0`
- `0x18005f32c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f3d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f471`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f4de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f53d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f3d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f471`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f4de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f53d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005f3c6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005f4ce`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005f3c6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005f4ce`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005f61a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005f691`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005f61a`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005f691`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18005f45d`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18005f59c`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18005f45d`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18005f59c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f668`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005f668`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18005f583`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18005f583`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005f52d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005f52d`

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
0x18005f32c  mov     [rsp+arg_8], rbx
0x18005f331  mov     [rsp+arg_18], rsi
0x18005f336  push    r13
0x18005f338  push    r14
0x18005f33a  push    r15
0x18005f33c  sub     rsp, 30h
0x18005f340  mov     r15, rdx
0x18005f343  mov     rsi, rcx
0x18005f346  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f34d  lea     r13, WPP_GLOBAL_Control
0x18005f354  cmp     rcx, r13
0x18005f357  jz      short loc_18005F384
0x18005f359  test    byte ptr [rcx+1Ch], 4
0x18005f35d  jz      short loc_18005F384
0x18005f35f  cmp     byte ptr [rcx+19h], 6
0x18005f363  jb      short loc_18005F384
0x18005f365  mov     rcx, [rcx+10h]
0x18005f369  lea     r8, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids
0x18005f370  mov     edx, 13h
0x18005f375  mov     r9, rsi
0x18005f378  call    WPP_SF_q
0x18005f37d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f384  mov     [rsp+48h+StringSid], 0
0x18005f38d  mov     [rsp+48h+TokenInformationLength], 0
0x18005f395  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18005f399  jz      loc_18005F628
0x18005f39f  test    r15, r15
0x18005f3a2  jz      loc_18005F628
0x18005f3a8  xor     r9d, r9d; TokenInformationLength
0x18005f3ab  mov     qword ptr [r15], 0
0x18005f3b2  lea     rax, [rsp+48h+TokenInformationLength]
0x18005f3b7  xor     r8d, r8d; TokenInformation
0x18005f3ba  mov     rcx, rsi; TokenHandle
0x18005f3bd  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18005f3c2  lea     edx, [r9+1]; TokenInformationClass
0x18005f3c6  call    cs:__imp_GetTokenInformation
0x18005f3cd  nop     dword ptr [rax+rax+00h]
0x18005f3d2  test    eax, eax
0x18005f3d4  jnz     short loc_18005F454
0x18005f3d6  call    cs:__imp_GetLastError
0x18005f3dd  nop     dword ptr [rax+rax+00h]
0x18005f3e2  mov     r9d, 7Ah ; 'z'
0x18005f3e8  mov     ebx, eax
0x18005f3ea  cmp     eax, r9d
0x18005f3ed  jz      short loc_18005F427
0x18005f3ef  test    eax, eax
0x18005f3f1  jz      loc_18005F654
0x18005f3f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f3fe  cmp     rcx, r13
0x18005f401  jz      loc_18005F65B
0x18005f407  test    byte ptr [rcx+1Ch], 4
0x18005f40b  jz      loc_18005F65B
0x18005f411  cmp     byte ptr [rcx+19h], 2
0x18005f415  jb      loc_18005F65B
0x18005f41b  lea     edx, [r9-65h]
0x18005f41f  mov     r9d, eax
0x18005f422  jmp     loc_18005F644
0x18005f427  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f42e  cmp     rcx, r13
0x18005f431  jz      short loc_18005F454
0x18005f433  test    byte ptr [rcx+1Ch], 4
0x18005f437  jz      short loc_18005F454
0x18005f439  cmp     byte ptr [rcx+19h], 2
0x18005f43d  jb      short loc_18005F454
0x18005f43f  mov     rcx, [rcx+10h]
0x18005f443  lea     r8, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids
0x18005f44a  mov     edx, 16h
0x18005f44f  call    WPP_SF_d
0x18005f454  mov     edx, [rsp+48h+TokenInformationLength]; dwBytes
0x18005f458  mov     ecx, 40h ; '@'; uFlags
0x18005f45d  call    cs:__imp_GlobalAlloc
0x18005f464  nop     dword ptr [rax+rax+00h]
0x18005f469  mov     r14, rax
0x18005f46c  test    rax, rax
0x18005f46f  jnz     short loc_18005F4B4
0x18005f471  call    cs:__imp_GetLastError
0x18005f478  nop     dword ptr [rax+rax+00h]
0x18005f47d  mov     ebx, eax
0x18005f47f  test    eax, eax
0x18005f481  jz      loc_18005F654
0x18005f487  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f48e  cmp     rcx, r13
0x18005f491  jz      loc_18005F65B
0x18005f497  test    byte ptr [rcx+1Ch], 4
0x18005f49b  jz      loc_18005F65B
0x18005f4a1  cmp     byte ptr [rcx+19h], 2
0x18005f4a5  jb      loc_18005F65B
0x18005f4ab  lea     edx, [r14+17h]
0x18005f4af  jmp     loc_18005F41F
0x18005f4b4  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18005f4b9  lea     rax, [rsp+48h+TokenInformationLength]
0x18005f4be  mov     r8, r14; TokenInformation
0x18005f4c1  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18005f4c6  mov     edx, 1; TokenInformationClass
0x18005f4cb  mov     rcx, rsi; TokenHandle
0x18005f4ce  call    cs:__imp_GetTokenInformation
0x18005f4d5  nop     dword ptr [rax+rax+00h]
0x18005f4da  test    eax, eax
0x18005f4dc  jnz     short loc_18005F525
0x18005f4de  call    cs:__imp_GetLastError
0x18005f4e5  nop     dword ptr [rax+rax+00h]
0x18005f4ea  mov     ebx, eax
0x18005f4ec  test    eax, eax
0x18005f4ee  jz      loc_18005F617
0x18005f4f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f4fb  cmp     rcx, r13
0x18005f4fe  jz      loc_18005F617
0x18005f504  test    byte ptr [rcx+1Ch], 4
0x18005f508  jz      loc_18005F617
0x18005f50e  cmp     byte ptr [rcx+19h], 2
0x18005f512  jb      loc_18005F617
0x18005f518  mov     edx, 18h
0x18005f51d  mov     r9d, eax
0x18005f520  jmp     loc_18005F607
0x18005f525  mov     rcx, [r14]; Sid
0x18005f528  lea     rdx, [rsp+48h+StringSid]; StringSid
0x18005f52d  call    cs:__imp_ConvertSidToStringSidW
0x18005f534  nop     dword ptr [rax+rax+00h]
0x18005f539  test    eax, eax
0x18005f53b  jnz     short loc_18005F57E
0x18005f53d  call    cs:__imp_GetLastError
0x18005f544  nop     dword ptr [rax+rax+00h]
0x18005f549  mov     ebx, eax
0x18005f54b  test    eax, eax
0x18005f54d  jz      loc_18005F617
0x18005f553  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f55a  cmp     rcx, r13
0x18005f55d  jz      loc_18005F617
0x18005f563  test    byte ptr [rcx+1Ch], 4
0x18005f567  jz      loc_18005F617
0x18005f56d  cmp     byte ptr [rcx+19h], 2
0x18005f571  jb      loc_18005F617
0x18005f577  mov     edx, 19h
0x18005f57c  jmp     short loc_18005F51D
0x18005f57e  mov     rcx, [rsp+48h+StringSid]; lpString
0x18005f583  call    cs:__imp_lstrlenW
0x18005f58a  nop     dword ptr [rax+rax+00h]
0x18005f58f  inc     eax
0x18005f591  mov     ecx, 40h ; '@'; uFlags
0x18005f596  mov     ebx, eax
0x18005f598  lea     rdx, [rax+rax]; dwBytes
0x18005f59c  call    cs:__imp_GlobalAlloc
0x18005f5a3  nop     dword ptr [rax+rax+00h]
0x18005f5a8  mov     [r15], rax
0x18005f5ab  test    rax, rax
0x18005f5ae  jnz     short loc_18005F5D0
0x18005f5b0  lea     ebx, [rax+0Eh]
0x18005f5b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f5ba  cmp     rcx, r13
0x18005f5bd  jz      short loc_18005F617
0x18005f5bf  test    byte ptr [rcx+1Ch], 4
0x18005f5c3  jz      short loc_18005F617
0x18005f5c5  cmp     byte ptr [rcx+19h], 2
0x18005f5c9  jb      short loc_18005F617
0x18005f5cb  lea     edx, [rax+1Ah]
0x18005f5ce  jmp     short loc_18005F604
0x18005f5d0  mov     r8, [rsp+48h+StringSid]; pszSrc
0x18005f5d5  mov     rdx, rbx; cchDest
0x18005f5d8  mov     rcx, rax; pszDest
0x18005f5db  call    StringCchCopyW
0x18005f5e0  movzx   ebx, ax
0x18005f5e3  test    ebx, ebx
0x18005f5e5  jz      short loc_18005F617
0x18005f5e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f5ee  cmp     rcx, r13
0x18005f5f1  jz      short loc_18005F617
0x18005f5f3  test    byte ptr [rcx+1Ch], 4
0x18005f5f7  jz      short loc_18005F617
0x18005f5f9  cmp     byte ptr [rcx+19h], 2
0x18005f5fd  jb      short loc_18005F617
0x18005f5ff  mov     edx, 1Bh
0x18005f604  mov     r9d, ebx
0x18005f607  mov     rcx, [rcx+10h]
0x18005f60b  lea     r8, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids
0x18005f612  call    WPP_SF_d
0x18005f617  mov     rcx, r14; hMem
0x18005f61a  call    cs:__imp_GlobalFree
0x18005f621  nop     dword ptr [rax+rax+00h]
0x18005f626  jmp     short loc_18005F654
0x18005f628  mov     ebx, 57h ; 'W'
0x18005f62d  cmp     rcx, r13
0x18005f630  jz      short loc_18005F688
0x18005f632  test    byte ptr [rcx+1Ch], 4
0x18005f636  jz      short loc_18005F688
0x18005f638  cmp     byte ptr [rcx+19h], 2
0x18005f63c  jb      short loc_18005F688
0x18005f63e  lea     edx, [rbx-43h]
0x18005f641  mov     r9d, ebx
0x18005f644  mov     rcx, [rcx+10h]
0x18005f648  lea     r8, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids
0x18005f64f  call    WPP_SF_d
0x18005f654  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f65b  mov     rax, [rsp+48h+StringSid]
0x18005f660  test    rax, rax
0x18005f663  jz      short loc_18005F684
0x18005f665  mov     rcx, rax; hMem
0x18005f668  call    cs:__imp_LocalFree
0x18005f66f  nop     dword ptr [rax+rax+00h]
0x18005f674  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f67b  mov     [rsp+48h+StringSid], 0
0x18005f684  test    ebx, ebx
0x18005f686  jz      short loc_18005F6AB
0x18005f688  cmp     qword ptr [r15], 0
0x18005f68c  jz      short loc_18005F6AB
0x18005f68e  mov     rcx, [r15]; hMem
0x18005f691  call    cs:__imp_GlobalFree
0x18005f698  nop     dword ptr [rax+rax+00h]
0x18005f69d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f6a4  mov     qword ptr [r15], 0
0x18005f6ab  cmp     rcx, r13
0x18005f6ae  jz      short loc_18005F6D4
0x18005f6b0  test    byte ptr [rcx+1Ch], 4
0x18005f6b4  jz      short loc_18005F6D4
0x18005f6b6  cmp     byte ptr [rcx+19h], 6
0x18005f6ba  jb      short loc_18005F6D4
0x18005f6bc  mov     rcx, [rcx+10h]
0x18005f6c0  lea     r8, WPP_439d79843ff53ef8fc824a92e5327ed2_Traceguids
0x18005f6c7  mov     edx, 1Ch
0x18005f6cc  mov     r9d, ebx
0x18005f6cf  call    WPP_SF_d
0x18005f6d4  mov     rsi, [rsp+48h+arg_18]
0x18005f6d9  mov     eax, ebx
0x18005f6db  mov     rbx, [rsp+48h+arg_8]
0x18005f6e0  add     rsp, 30h
0x18005f6e4  pop     r15
0x18005f6e6  pop     r14
0x18005f6e8  pop     r13
0x18005f6ea  retn
```
