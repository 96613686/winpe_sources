# WriteSharedPbkOptions

- ea: `0x1800c8358`
- end: `0x1800c884d`
- name: `WriteSharedPbkOptions`
- size: `1269`
- prototype: `__int64 __fastcall(LPCCH lpMultiByteStr, LPCCH, HANDLE hToken)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18007de80`

## callees

- `0x1800079c0`
- `0x18000b960`
- `0x180011450`
- `0x180020ac0`
- `0x1800279c0`
- `0x18004e580`
- `0x18007f18c`
- `0x180099398`
- `0x1800c6ecc`
- `0x1800c8028`
- `0x1800c82a8`
- `0x1800c8358`
- `0x1800ded06`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800c8730`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800c8730`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800c878a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800c878a`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800c85d7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800c85d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c85e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c8794`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c85e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c8794`
- `rtutils!TracePrintfExA` at `0x1800c8478`
- `rtutils!TracePrintfExA` at `0x1800c8784`
- `rtutils!TracePrintfExA` at `0x1800c87ea`
- `rtutils!TracePrintfExA` at `0x1800c8478`
- `rtutils!TracePrintfExA` at `0x1800c8784`
- `rtutils!TracePrintfExA` at `0x1800c87ea`

## string_xrefs

- `0x1800c846c`: `RasWriteSharedPbkOptions`
- `0x1800c870f`: `RasWriteSharedPbkOptions: Failed to get hidden phonebook path 0x%x.`
- `0x1800c869f`: `RasWriteSharedPbkOptions: Phonebook read failed 0x%x.`
- `0x1800c862c`: `RasWriteSharedPbkOptions: ImpersonateLoggedOnUser failed 0x%x`
- `0x1800c87db`: `RasWriteSharedPbkOptions: RevertToSelf Failed 0x%x.`
- `0x1800c8775`: `RasWriteSharedPbkOptions: RasUpdatePbkIpv6Info failed 0x%x.`

## pseudocode

```c
__int64 __fastcall WriteSharedPbkOptions(LPCCH lpMultiByteStr, LPCCH a2, HANDLE hToken, __int64 a4)
{
  _QWORD *v8; // rcx
  unsigned int updated; // ebx
  __int64 v10; // rdx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  unsigned __int64 v14; // rbx
  DWORD v15; // eax
  unsigned int PbkAndEntryName; // eax
  unsigned int LUAPhonebookPath; // eax
  DWORD LastError; // eax
  HGLOBAL hMem; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v20[8]; // [rsp+38h] [rbp-C8h] BYREF
  _OWORD v21[3]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v22; // [rsp+70h] [rbp-90h]
  WCHAR v23[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v24[524]; // [rsp+84h] [rbp-7Ch] BYREF
  WCHAR WideCharStr[2]; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v26[524]; // [rsp+294h] [rbp+194h] BYREF

  if ( lpMultiByteStr && a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
    {
      WPP_SF_ssq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)hToken,
        (_DWORD)lpMultiByteStr,
        (__int64)a2,
        (char)hToken);
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids);
  }
  v22 = 0;
  memset(v21, 0, sizeof(v21));
  *(_DWORD *)WideCharStr = 0;
  memset_0(v26, 0, 0x204u);
  *(_DWORD *)v23 = 0;
  memset_0(v24, 0, 0x1FEu);
  hMem = 0;
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "RasWriteSharedPbkOptions");
  if ( !(unsigned int)IsBadInputStringA(lpMultiByteStr, 261, 1) )
  {
    if ( (unsigned int)IsBadInputStringA(a2, 1537, 0) )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 87;
      }
      v12 = 27;
    }
    else
    {
      if ( a4 )
      {
        if ( lpMultiByteStr )
          StrncpyAtoW_0(WideCharStr, lpMultiByteStr);
        StrncpyAtoW_0(v23, a2);
        v14 = (unsigned __int64)WideCharStr & -(__int64)(lpMultiByteStr != 0);
        if ( (unsigned int)IsExistingEntry(v14, v23) )
        {
          RasUpdatePbkIpv6Info(v14, v23, a4);
          if ( ImpersonateLoggedOnUser(hToken) )
          {
            PbkAndEntryName = GetPbkAndEntryName(WideCharStr, (__int64)v20);
            updated = PbkAndEntryName;
            if ( PbkAndEntryName )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  31,
                  &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids,
                  PbkAndEntryName);
              }
              if ( g_dwTraceId != -1 )
                TracePrintfExA(g_dwTraceId, 0xCu, "RasWriteSharedPbkOptions: Phonebook read failed 0x%x.", updated);
            }
            else if ( (unsigned int)IsVirtualizationNeeded(v21) )
            {
              LUAPhonebookPath = GetLUAPhonebookPath(WideCharStr, (__int64 *)&hMem);
              updated = LUAPhonebookPath;
              if ( LUAPhonebookPath )
              {
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    32,
                    &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids,
                    LUAPhonebookPath);
                }
                if ( g_dwTraceId != -1 )
                  TracePrintfExA(
                    g_dwTraceId,
                    0xCu,
                    "RasWriteSharedPbkOptions: Failed to get hidden phonebook path 0x%x.",
                    updated);
              }
              else
              {
                updated = RasUpdatePbkIpv6Info(hMem, v23, a4);
                GlobalFree(hMem);
                if ( updated )
                {
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      33,
                      &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids,
                      updated);
                  }
                  if ( g_dwTraceId != -1 )
                    TracePrintfExA(
                      g_dwTraceId,
                      0xCu,
                      "RasWriteSharedPbkOptions: RasUpdatePbkIpv6Info failed 0x%x.",
                      updated);
                }
              }
            }
            if ( !RevertToSelf() )
            {
              LastError = GetLastError();
              updated = LastError;
              if ( LastError
                && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  34,
                  &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids,
                  LastError);
              }
              if ( g_dwTraceId != -1 )
                TracePrintfExA(g_dwTraceId, 0xCu, "RasWriteSharedPbkOptions: RevertToSelf Failed 0x%x.", updated);
            }
          }
          else
          {
            v15 = GetLastError();
            updated = v15;
            if ( v15
              && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, v15);
            }
            if ( g_dwTraceId != -1 )
              TracePrintfExA(
                g_dwTraceId,
                0xCu,
                "RasWriteSharedPbkOptions: ImpersonateLoggedOnUser failed 0x%x",
                updated);
          }
          ClosePhonebookFile((__int64)v21);
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 6u )
          {
            return updated;
          }
          v10 = 35;
        }
        else
        {
          v8 = WPP_GLOBAL_Control;
          updated = 623;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            return updated;
          }
          v10 = 29;
        }
        goto LABEL_79;
      }
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 87;
      }
      v12 = 28;
    }
    WPP_SF_d(v11[2], v12, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, 87);
    return 87;
  }
  v8 = WPP_GLOBAL_Control;
  updated = 621;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    return updated;
  }
  v10 = 26;
LABEL_79:
  WPP_SF_d(v8[2], v10, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, updated);
  return updated;
}

```

## disassembly

```asm
0x1800c8358  push    rbp
0x1800c835a  push    rbx
0x1800c835b  push    rsi
0x1800c835c  push    rdi
0x1800c835d  push    r13
0x1800c835f  push    r14
0x1800c8361  push    r15
0x1800c8363  lea     rbp, [rsp-3B0h]
0x1800c836b  sub     rsp, 4B0h
0x1800c8372  mov     rax, cs:__security_cookie
0x1800c8379  xor     rax, rsp
0x1800c837c  mov     [rbp+3E0h+var_40], rax
0x1800c8383  mov     r15, r9
0x1800c8386  mov     r14, r8
0x1800c8389  mov     rsi, rdx
0x1800c838c  mov     rbx, rcx
0x1800c838f  mov     r13d, 1000h
0x1800c8395  test    rcx, rcx
0x1800c8398  jz      short loc_1800C83D6
0x1800c839a  test    rdx, rdx
0x1800c839d  jz      short loc_1800C83D6
0x1800c839f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c83a6  lea     rdi, WPP_GLOBAL_Control
0x1800c83ad  cmp     rcx, rdi
0x1800c83b0  jz      short loc_1800C840D
0x1800c83b2  test    [rcx+1Ch], r13d
0x1800c83b6  jz      short loc_1800C840D
0x1800c83b8  cmp     byte ptr [rcx+19h], 6
0x1800c83bc  jb      short loc_1800C840D
0x1800c83be  mov     rcx, [rcx+10h]
0x1800c83c2  mov     r9, rbx
0x1800c83c5  mov     [rsp+4E0h+var_4B8], r8
0x1800c83ca  mov     [rsp+4E0h+var_4C0], rdx
0x1800c83cf  call    WPP_SF_ssq
0x1800c83d4  jmp     short loc_1800C840D
0x1800c83d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c83dd  lea     rdi, WPP_GLOBAL_Control
0x1800c83e4  cmp     rcx, rdi
0x1800c83e7  jz      short loc_1800C840D
0x1800c83e9  test    [rcx+1Ch], r13d
0x1800c83ed  jz      short loc_1800C840D
0x1800c83ef  cmp     byte ptr [rcx+19h], 6
0x1800c83f3  jb      short loc_1800C840D
0x1800c83f5  mov     rcx, [rcx+10h]
0x1800c83f9  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x1800c8400  mov     edx, 19h
0x1800c8405  mov     r9, r14
0x1800c8408  call    WPP_SF_q
0x1800c840d  xorps   xmm0, xmm0
0x1800c8410  lea     rcx, [rbp+3E0h+var_24C]; void *
0x1800c8417  xor     eax, eax
0x1800c8419  xor     edx, edx; Val
0x1800c841b  mov     r8d, 204h; Size
0x1800c8421  mov     [rsp+4E0h+var_470], rax
0x1800c8426  movups  [rsp+4E0h+var_4A0], xmm0
0x1800c842b  mov     dword ptr [rbp+3E0h+WideCharStr], eax
0x1800c8431  movups  [rsp+4E0h+var_490], xmm0
0x1800c8436  movups  [rsp+4E0h+var_480], xmm0
0x1800c843b  call    memset_0
0x1800c8440  xor     edx, edx; Val
0x1800c8442  mov     dword ptr [rbp+3E0h+var_460], 0
0x1800c8449  mov     r8d, 1FEh; Size
0x1800c844f  lea     rcx, [rbp+3E0h+var_45C]; void *
0x1800c8453  call    memset_0
0x1800c8458  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c845e  mov     [rsp+4E0h+hMem], 0
0x1800c8467  cmp     ecx, 0FFFFFFFFh
0x1800c846a  jz      short loc_1800C847E
0x1800c846c  lea     r8, aRaswriteshared_2; "RasWriteSharedPbkOptions"
0x1800c8473  mov     edx, 0Ch; dwFlags
0x1800c8478  call    cs:__imp_TracePrintfExA
0x1800c847e  mov     edx, 105h
0x1800c8483  mov     r8d, 1
0x1800c8489  mov     rcx, rbx
0x1800c848c  call    IsBadInputStringA
0x1800c8491  test    eax, eax
0x1800c8493  jz      short loc_1800C84C8
0x1800c8495  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c849c  mov     ebx, 26Dh
0x1800c84a1  cmp     rcx, rdi
0x1800c84a4  jz      loc_1800C882A
0x1800c84aa  test    [rcx+1Ch], r13d
0x1800c84ae  jz      loc_1800C882A
0x1800c84b4  cmp     byte ptr [rcx+19h], 2
0x1800c84b8  jb      loc_1800C882A
0x1800c84be  mov     edx, 1Ah
0x1800c84c3  jmp     loc_1800C8817
0x1800c84c8  xor     r8d, r8d
0x1800c84cb  mov     edx, 601h
0x1800c84d0  mov     rcx, rsi
0x1800c84d3  call    IsBadInputStringA
0x1800c84d8  test    eax, eax
0x1800c84da  jz      short loc_1800C84FB
0x1800c84dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c84e3  cmp     rcx, rdi
0x1800c84e6  jz      short loc_1800C8532
0x1800c84e8  test    [rcx+1Ch], r13d
0x1800c84ec  jz      short loc_1800C8532
0x1800c84ee  cmp     byte ptr [rcx+19h], 2
0x1800c84f2  jb      short loc_1800C8532
0x1800c84f4  mov     edx, 1Bh
0x1800c84f9  jmp     short loc_1800C851C
0x1800c84fb  test    r15, r15
0x1800c84fe  jnz     short loc_1800C853C
0x1800c8500  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c8507  cmp     rcx, rdi
0x1800c850a  jz      short loc_1800C8532
0x1800c850c  test    [rcx+1Ch], r13d
0x1800c8510  jz      short loc_1800C8532
0x1800c8512  cmp     byte ptr [rcx+19h], 2
0x1800c8516  jb      short loc_1800C8532
0x1800c8518  lea     edx, [r15+1Ch]
0x1800c851c  mov     rcx, [rcx+10h]
0x1800c8520  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x1800c8527  mov     r9d, 57h ; 'W'
0x1800c852d  call    WPP_SF_d
0x1800c8532  mov     eax, 57h ; 'W'
0x1800c8537  jmp     loc_1800C882C
0x1800c853c  test    rbx, rbx
0x1800c853f  jz      short loc_1800C855C
0x1800c8541  mov     r9d, 0FDE9h
0x1800c8547  lea     rcx, [rbp+3E0h+WideCharStr]; lpWideCharStr
0x1800c854e  mov     r8d, 104h
0x1800c8554  mov     rdx, rbx; lpMultiByteStr
0x1800c8557  call    StrncpyAtoW_0
0x1800c855c  mov     r9d, 0FDE9h
0x1800c8562  lea     rcx, [rbp+3E0h+var_460]; lpWideCharStr
0x1800c8566  mov     r8d, 101h
0x1800c856c  mov     rdx, rsi; lpMultiByteStr
0x1800c856f  call    StrncpyAtoW_0
0x1800c8574  neg     rbx
0x1800c8577  lea     rax, [rbp+3E0h+WideCharStr]
0x1800c857e  lea     rdx, [rbp+3E0h+var_460]
0x1800c8582  sbb     rbx, rbx
0x1800c8585  and     rbx, rax
0x1800c8588  mov     rcx, rbx
0x1800c858b  call    IsExistingEntry
0x1800c8590  test    eax, eax
0x1800c8592  jnz     short loc_1800C85C5
0x1800c8594  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c859b  mov     ebx, 26Fh
0x1800c85a0  cmp     rcx, rdi
0x1800c85a3  jz      loc_1800C882A
0x1800c85a9  test    [rcx+1Ch], r13d
0x1800c85ad  jz      loc_1800C882A
0x1800c85b3  cmp     byte ptr [rcx+19h], 2
0x1800c85b7  jb      loc_1800C882A
0x1800c85bd  lea     edx, [rax+1Dh]
0x1800c85c0  jmp     loc_1800C8817
0x1800c85c5  mov     r8, r15
0x1800c85c8  lea     rdx, [rbp+3E0h+var_460]
0x1800c85cc  mov     rcx, rbx
0x1800c85cf  call    RasUpdatePbkIpv6Info
0x1800c85d4  mov     rcx, r14; hToken
0x1800c85d7  call    cs:__imp_ImpersonateLoggedOnUser
0x1800c85dd  test    eax, eax
0x1800c85df  jnz     short loc_1800C8638
0x1800c85e1  call    cs:__imp_GetLastError
0x1800c85e7  mov     ebx, eax
0x1800c85e9  test    eax, eax
0x1800c85eb  jz      short loc_1800C861D
0x1800c85ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c85f4  cmp     rcx, rdi
0x1800c85f7  jz      short loc_1800C861D
0x1800c85f9  test    [rcx+1Ch], r13d
0x1800c85fd  jz      short loc_1800C861D
0x1800c85ff  cmp     byte ptr [rcx+19h], 2
0x1800c8603  jb      short loc_1800C861D
0x1800c8605  mov     rcx, [rcx+10h]
0x1800c8609  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x1800c8610  mov     edx, 1Eh
0x1800c8615  mov     r9d, eax
0x1800c8618  call    WPP_SF_d
0x1800c861d  mov     ecx, cs:g_dwTraceId
0x1800c8623  cmp     ecx, 0FFFFFFFFh
0x1800c8626  jz      loc_1800C87F0
0x1800c862c  lea     r8, aRaswriteshared_0; "RasWriteSharedPbkOptions: ImpersonateLo"...
0x1800c8633  jmp     loc_1800C87E2
0x1800c8638  lea     rax, [rsp+4E0h+var_4A8]
0x1800c863d  xor     r8d, r8d
0x1800c8640  lea     r9, [rsp+4E0h+var_4A0]
0x1800c8645  mov     [rsp+4E0h+var_4C0], rax
0x1800c864a  lea     rdx, [rbp+3E0h+var_460]
0x1800c864e  lea     rcx, [rbp+3E0h+WideCharStr]
0x1800c8655  call    GetPbkAndEntryName
0x1800c865a  mov     ebx, eax
0x1800c865c  test    eax, eax
0x1800c865e  jz      short loc_1800C86AB
0x1800c8660  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c8667  cmp     rcx, rdi
0x1800c866a  jz      short loc_1800C8690
0x1800c866c  test    [rcx+1Ch], r13d
0x1800c8670  jz      short loc_1800C8690
0x1800c8672  cmp     byte ptr [rcx+19h], 2
0x1800c8676  jb      short loc_1800C8690
0x1800c8678  mov     rcx, [rcx+10h]
0x1800c867c  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x1800c8683  mov     edx, 1Fh
0x1800c8688  mov     r9d, eax
0x1800c868b  call    WPP_SF_d
0x1800c8690  mov     ecx, cs:g_dwTraceId
0x1800c8696  cmp     ecx, 0FFFFFFFFh
0x1800c8699  jz      loc_1800C878A
0x1800c869f  lea     r8, aRaswriteshared_4; "RasWriteSharedPbkOptions: Phonebook rea"...
0x1800c86a6  jmp     loc_1800C877C
0x1800c86ab  lea     rcx, [rsp+4E0h+var_4A0]
0x1800c86b0  call    IsVirtualizationNeeded
0x1800c86b5  test    eax, eax
0x1800c86b7  jz      loc_1800C878A
0x1800c86bd  lea     rdx, [rsp+4E0h+hMem]
0x1800c86c2  lea     rcx, [rbp+3E0h+WideCharStr]; lpFileName
0x1800c86c9  call    GetLUAPhonebookPath
0x1800c86ce  mov     ebx, eax
0x1800c86d0  test    eax, eax
0x1800c86d2  jz      short loc_1800C8718
0x1800c86d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c86db  cmp     rcx, rdi
0x1800c86de  jz      short loc_1800C8704
0x1800c86e0  test    [rcx+1Ch], r13d
0x1800c86e4  jz      short loc_1800C8704
0x1800c86e6  cmp     byte ptr [rcx+19h], 2
0x1800c86ea  jb      short loc_1800C8704
0x1800c86ec  mov     rcx, [rcx+10h]
0x1800c86f0  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x1800c86f7  mov     edx, 20h ; ' '
0x1800c86fc  mov     r9d, eax
0x1800c86ff  call    WPP_SF_d
0x1800c8704  mov     ecx, cs:g_dwTraceId
0x1800c870a  cmp     ecx, 0FFFFFFFFh
0x1800c870d  jz      short loc_1800C878A
0x1800c870f  lea     r8, aRaswriteshared_1; "RasWriteSharedPbkOptions: Failed to get"...
0x1800c8716  jmp     short loc_1800C877C
0x1800c8718  mov     rcx, [rsp+4E0h+hMem]
0x1800c871d  lea     rdx, [rbp+3E0h+var_460]
0x1800c8721  mov     r8, r15
0x1800c8724  call    RasUpdatePbkIpv6Info
0x1800c8729  mov     rcx, [rsp+4E0h+hMem]; hMem
0x1800c872e  mov     ebx, eax
0x1800c8730  call    cs:__imp_GlobalFree
0x1800c8736  test    ebx, ebx
0x1800c8738  jz      short loc_1800C878A
0x1800c873a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c8741  cmp     rcx, rdi
0x1800c8744  jz      short loc_1800C876A
0x1800c8746  test    [rcx+1Ch], r13d
0x1800c874a  jz      short loc_1800C876A
0x1800c874c  cmp     byte ptr [rcx+19h], 2
0x1800c8750  jb      short loc_1800C876A
0x1800c8752  mov     rcx, [rcx+10h]
0x1800c8756  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x1800c875d  mov     edx, 21h ; '!'
0x1800c8762  mov     r9d, ebx
0x1800c8765  call    WPP_SF_d
0x1800c876a  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c8770  cmp     ecx, 0FFFFFFFFh
0x1800c8773  jz      short loc_1800C878A
0x1800c8775  lea     r8, aRaswriteshared_3; "RasWriteSharedPbkOptions: RasUpdatePbkI"...
0x1800c877c  mov     r9d, ebx
0x1800c877f  mov     edx, 0Ch; dwFlags
0x1800c8784  call    cs:__imp_TracePrintfExA
0x1800c878a  call    cs:__imp_RevertToSelf
0x1800c8790  test    eax, eax
0x1800c8792  jnz     short loc_1800C87F0
0x1800c8794  call    cs:__imp_GetLastError
0x1800c879a  mov     ebx, eax
0x1800c879c  test    eax, eax
0x1800c879e  jz      short loc_1800C87D0
0x1800c87a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c87a7  cmp     rcx, rdi
0x1800c87aa  jz      short loc_1800C87D0
0x1800c87ac  test    [rcx+1Ch], r13d
0x1800c87b0  jz      short loc_1800C87D0
0x1800c87b2  cmp     byte ptr [rcx+19h], 2
0x1800c87b6  jb      short loc_1800C87D0
0x1800c87b8  mov     rcx, [rcx+10h]
0x1800c87bc  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x1800c87c3  mov     edx, 22h ; '"'
0x1800c87c8  mov     r9d, eax
0x1800c87cb  call    WPP_SF_d
0x1800c87d0  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c87d6  cmp     ecx, 0FFFFFFFFh
0x1800c87d9  jz      short loc_1800C87F0
0x1800c87db  lea     r8, aRaswriteshared_5; "RasWriteSharedPbkOptions: RevertToSelf "...
0x1800c87e2  mov     r9d, ebx
0x1800c87e5  mov     edx, 0Ch; dwFlags
0x1800c87ea  call    cs:__imp_TracePrintfExA
0x1800c87f0  lea     rcx, [rsp+4E0h+var_4A0]
0x1800c87f5  call    ClosePhonebookFile
0x1800c87fa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c8801  cmp     rcx, rdi
0x1800c8804  jz      short loc_1800C882A
0x1800c8806  test    [rcx+1Ch], r13d
0x1800c880a  jz      short loc_1800C882A
0x1800c880c  cmp     byte ptr [rcx+19h], 6
0x1800c8810  jb      short loc_1800C882A
0x1800c8812  mov     edx, 23h ; '#'
0x1800c8817  mov     rcx, [rcx+10h]
0x1800c881b  lea     r8, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x1800c8822  mov     r9d, ebx
0x1800c8825  call    WPP_SF_d
  ... truncated ...
```
