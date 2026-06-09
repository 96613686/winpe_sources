# RasEntryDlgW

- ea: `0x180014b40`
- end: `0x180014e39`
- name: `RasEntryDlgW`
- size: `761`
- prototype: `BOOL __stdcall(LPWSTR lpszPhonebook, LPWSTR lpszEntry, struct tagRASENTRYDLGW *lpInfo)`
- caller_count: `5`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c9c8`
- `0x180014820`
- `0x180015030`
- `0x180024ca4`
- `0x180025b48`

## callees

- `0x180012b78`
- `0x1800139b0`
- `0x180013b90`
- `0x1800149b4`
- `0x180014b40`
- `0x18001c2cc`
- `0x18001f728`
- `0x18002bd74`
- `0x18002bfc8`
- `0x18002cdb8`
- `0x18002d080`
- `0x18003bda0`
- `0x180048b6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014baa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014baa`
- `RASAPI32!GetPbkAndEntryName` at `0x180014d2c`
- `RASAPI32!GetPbkAndEntryName` at `0x180014d2c`
- `RASAPI32!ClosePhonebookFile` at `0x180014d8e`
- `RASAPI32!ClosePhonebookFile` at `0x180014dd6`
- `RASAPI32!ClosePhonebookFile` at `0x180014d8e`
- `RASAPI32!ClosePhonebookFile` at `0x180014dd6`
- `rtutils!TracePrintfExA` at `0x180014b8e`
- `rtutils!TracePrintfExA` at `0x180014d50`
- `rtutils!TracePrintfExA` at `0x180014d84`
- `rtutils!TracePrintfExA` at `0x180014b8e`
- `rtutils!TracePrintfExA` at `0x180014d50`
- `rtutils!TracePrintfExA` at `0x180014d84`
- `rasman!RasIsTrustedCustomDll` at `0x180014db0`
- `rasman!RasIsTrustedCustomDll` at `0x180014db0`

## string_xrefs

- `0x180014d78`: `RasEntryDlgW: Failed to read the entry`

## pseudocode

```c
BOOL __stdcall RasEntryDlgW(LPWSTR lpszPhonebook, LPWSTR lpszEntry, struct tagRASENTRYDLGW *lpInfo)
{
  DWORD v6; // edi
  ULONG_PTR reserved; // rax
  int v9; // r9d
  DWORD v10; // esi
  DWORD v11; // eax
  __int64 v12; // rdi
  DWORD v13; // r14d
  __int64 v14; // rax
  BOOL v15; // esi
  int PbkAndEntryName; // eax
  __int64 v17; // rdx
  __int64 v18; // rdx
  BOOL v19; // esi
  int v20; // [rsp+20h] [rbp-39h]
  int v21[2]; // [rsp+40h] [rbp-19h] BYREF
  __int64 v22; // [rsp+48h] [rbp-11h] BYREF
  _OWORD v23[3]; // [rsp+50h] [rbp-9h] BYREF
  __int64 v24; // [rsp+80h] [rbp+27h]
  UINT uID; // [rsp+D8h] [rbp+7Fh] BYREF

  *(_QWORD *)v21 = 0;
  uID = 0;
  RasDlgInit();
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "RasEntryDlgW");
  v6 = CheckRasEntryDlgWParams(lpszPhonebook, lpszEntry, lpInfo);
  if ( v6 )
    goto LABEL_4;
  reserved = lpInfo->reserved;
  v9 = 0;
  if ( reserved )
    LOBYTE(v9) = *(_QWORD *)(reserved + 72) != 0;
  v10 = lpInfo->dwFlags & 0x4B2;
  if ( !v9 )
  {
    uID = 0;
    if ( v10 )
    {
      if ( (lpInfo->dwFlags & 0x40000000) != 0 )
      {
        lpInfo->dwError = 816;
        return 0;
      }
      lpInfo->dwError = LaunchRASWizard((__int64)lpszPhonebook, (__int64)lpszEntry, (__int64)lpInfo, &uID);
      return uID;
    }
    if ( !FIsUserAdminOrNCO() )
    {
      v22 = 0;
      v24 = 0;
      memset(v23, 0, sizeof(v23));
      PbkAndEntryName = GetPbkAndEntryName(lpszPhonebook, lpszEntry, 1032, v23, &v22);
      if ( PbkAndEntryName )
      {
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "RasEntryDlgW: GetPbkAndEntryName failed %d", PbkAndEntryName);
LABEL_33:
        v6 = 623;
LABEL_4:
        SetLastError(v6);
        lpInfo->dwError = v6;
        return 0;
      }
      v17 = *(_QWORD *)(v22 + 16);
      if ( !v17 )
      {
        if ( g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "RasEntryDlgW: Failed to read the entry");
        ClosePhonebookFile(v23);
        goto LABEL_33;
      }
      v19 = !*(_DWORD *)(v17 + 548)
         && ((v18 = *(_QWORD *)(v17 + 448), v21[0] = 0, (unsigned int)RasIsTrustedCustomDll(0, v18, v21)) || !v21[0])
         && DWORD2(v23[0]) == 0;
      ClosePhonebookFile(v23);
      if ( v19 )
      {
        if ( (lpInfo->dwFlags & 0x40000000) != 0 )
        {
          lpInfo->dwError = 5;
          return 0;
        }
        LaunchRasPropertiesEditAsAdmin((__int64)lpszPhonebook, (__int64)lpszEntry, (__int64)lpInfo, &uID);
        return uID;
      }
    }
    return RasEntryDlgPropertiesEdit(lpszPhonebook, lpszEntry, lpInfo);
  }
  v11 = EuInit((_DWORD)lpszPhonebook, (_DWORD)lpszEntry, (_DWORD)lpInfo, v9, (__int64)v21, (__int64)&uID);
  v12 = *(_QWORD *)v21;
  v13 = v11;
  if ( v11 )
  {
    ErrorDlgUtil(lpInfo->hwndOwner, uID, v11, v20, 0x169u, 0xFAu);
    lpInfo->dwError = v13;
  }
  else if ( v10 )
  {
    AiWizard(*(_QWORD *)v21);
    if ( *(_DWORD *)(v12 + 56) && !lpInfo->dwError )
      PePropertySheet(v12);
    v14 = *(_QWORD *)(v12 + 16);
    if ( v14 )
      lpInfo->reserved2 |= *(_QWORD *)(v14 + 552);
  }
  else
  {
    PePropertySheet(*(_QWORD *)v21);
  }
  if ( !v12 )
    return 0;
  if ( !*(_DWORD *)(v12 + 24) || (v15 = 1, !(unsigned int)EuCommit(v12)) )
    v15 = 0;
  EuFree(v12);
  return v15;
}

```

## disassembly

```asm
0x180014b40  mov     [rsp-8+arg_0], rbx
0x180014b45  mov     [rsp-8+arg_8], rsi
0x180014b4a  push    rbp
0x180014b4b  push    rdi
0x180014b4c  push    r12
0x180014b4e  push    r14
0x180014b50  push    r15
0x180014b52  lea     rbp, [rsp-37h]
0x180014b57  sub     rsp, 90h
0x180014b5e  xor     r12d, r12d
0x180014b61  mov     rbx, r8
0x180014b64  mov     qword ptr [rbp+57h+var_70], r12
0x180014b68  mov     r14, rdx
0x180014b6b  mov     [rbp+57h+uID], r12d
0x180014b6f  mov     r15, rcx
0x180014b72  call    RasDlgInit
0x180014b77  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180014b7d  cmp     ecx, 0FFFFFFFFh
0x180014b80  jz      short loc_180014B94
0x180014b82  lea     r8, aRasentrydlgw_0; "RasEntryDlgW"
0x180014b89  lea     edx, [r12+0Ch]; dwFlags
0x180014b8e  call    cs:__imp_TracePrintfExA
0x180014b94  mov     r8, rbx
0x180014b97  mov     rdx, r14
0x180014b9a  mov     rcx, r15
0x180014b9d  call    CheckRasEntryDlgWParams
0x180014ba2  mov     edi, eax
0x180014ba4  test    eax, eax
0x180014ba6  jz      short loc_180014BBD
0x180014ba8  mov     ecx, edi; dwErrCode
0x180014baa  call    cs:__imp_SetLastError
0x180014bb0  mov     [rbx+21Ch], edi
0x180014bb6  xor     eax, eax
0x180014bb8  jmp     loc_180014E1D
0x180014bbd  mov     rax, [rbx+220h]
0x180014bc4  mov     r9d, r12d
0x180014bc7  test    rax, rax
0x180014bca  jz      short loc_180014BD4
0x180014bcc  cmp     [rax+48h], r12
0x180014bd0  setnz   r9b
0x180014bd4  mov     esi, [rbx+0Ch]
0x180014bd7  and     esi, 4B2h
0x180014bdd  test    r9d, r9d
0x180014be0  jz      loc_180014CB0
0x180014be6  lea     rax, [rbp+57h+uID]
0x180014bea  mov     r8, rbx
0x180014bed  mov     qword ptr [rsp+0B0h+var_88], rax
0x180014bf2  mov     rdx, r14
0x180014bf5  lea     rax, [rbp+57h+var_70]
0x180014bf9  mov     rcx, r15
0x180014bfc  mov     qword ptr [rsp+0B0h+var_90], rax; int
0x180014c01  call    EuInit
0x180014c06  mov     rdi, qword ptr [rbp+57h+var_70]
0x180014c0a  mov     r14d, eax
0x180014c0d  test    eax, eax
0x180014c0f  jnz     short loc_180014C54
0x180014c11  mov     rcx, rdi
0x180014c14  test    esi, esi
0x180014c16  jz      short loc_180014C4D
0x180014c18  call    AiWizard
0x180014c1d  cmp     [rdi+38h], r12d
0x180014c21  jz      short loc_180014C34
0x180014c23  cmp     [rbx+21Ch], r12d
0x180014c2a  jnz     short loc_180014C34
0x180014c2c  mov     rcx, rdi
0x180014c2f  call    PePropertySheet
0x180014c34  mov     rax, [rdi+10h]
0x180014c38  test    rax, rax
0x180014c3b  jz      short loc_180014C7D
0x180014c3d  mov     rax, [rax+228h]
0x180014c44  or      [rbx+228h], rax
0x180014c4b  jmp     short loc_180014C7D
0x180014c4d  call    PePropertySheet
0x180014c52  jmp     short loc_180014C7D
0x180014c54  mov     edx, [rbp+57h+uID]; uID
0x180014c57  xor     r9d, r9d
0x180014c5a  mov     rcx, [rbx+4]; hWnd
0x180014c5e  mov     r8d, r14d; dwMessageId
0x180014c61  mov     [rsp+0B0h+var_80], 0FAh; UINT
0x180014c69  mov     [rsp+0B0h+var_88], 169h; UINT
0x180014c71  call    ErrorDlgUtil
0x180014c76  mov     [rbx+21Ch], r14d
0x180014c7d  test    rdi, rdi
0x180014c80  jz      short loc_180014CA6
0x180014c82  cmp     [rdi+18h], r12d
0x180014c86  jz      short loc_180014C99
0x180014c88  mov     rcx, rdi
0x180014c8b  call    EuCommit
0x180014c90  mov     esi, 1
0x180014c95  test    eax, eax
0x180014c97  jnz     short loc_180014C9C
0x180014c99  mov     esi, r12d
0x180014c9c  mov     rcx, rdi
0x180014c9f  call    EuFree
0x180014ca4  jmp     short loc_180014CA9
0x180014ca6  mov     esi, r12d
0x180014ca9  mov     eax, esi
0x180014cab  jmp     loc_180014E1D
0x180014cb0  mov     [rbp+57h+uID], r12d
0x180014cb4  test    esi, esi
0x180014cb6  jz      short loc_180014CED
0x180014cb8  test    dword ptr [rbx+0Ch], 40000000h
0x180014cbf  jz      short loc_180014CD0
0x180014cc1  mov     dword ptr [rbx+21Ch], 330h
0x180014ccb  jmp     loc_180014BB6
0x180014cd0  lea     r9, [rbp+57h+uID]
0x180014cd4  mov     r8, rbx
0x180014cd7  mov     rdx, r14
0x180014cda  mov     rcx, r15
0x180014cdd  call    LaunchRASWizard
0x180014ce2  mov     [rbx+21Ch], eax
0x180014ce8  jmp     loc_180014E0A
0x180014ced  call    FIsUserAdminOrNCO
0x180014cf2  test    eax, eax
0x180014cf4  jnz     loc_180014E0F
0x180014cfa  xorps   xmm0, xmm0
0x180014cfd  mov     [rbp+57h+var_68], r12
0x180014d01  xor     eax, eax
0x180014d03  lea     r9, [rbp+57h+var_60]
0x180014d07  mov     [rbp+57h+var_30], rax
0x180014d0b  mov     r8d, 408h
0x180014d11  lea     rax, [rbp+57h+var_68]
0x180014d15  mov     rdx, r14
0x180014d18  mov     rcx, r15
0x180014d1b  mov     qword ptr [rsp+0B0h+var_90], rax
0x180014d20  movups  [rbp+57h+var_60], xmm0
0x180014d24  movups  [rbp+57h+var_50], xmm0
0x180014d28  movups  [rbp+57h+var_40], xmm0
0x180014d2c  call    cs:__imp_GetPbkAndEntryName
0x180014d32  test    eax, eax
0x180014d34  jz      short loc_180014D60
0x180014d36  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180014d3c  cmp     ecx, 0FFFFFFFFh
0x180014d3f  jz      short loc_180014D56
0x180014d41  mov     r9d, eax
0x180014d44  lea     r8, aRasentrydlgwGe; "RasEntryDlgW: GetPbkAndEntryName failed"...
0x180014d4b  mov     edx, 0Ch; dwFlags
0x180014d50  call    cs:__imp_TracePrintfExA
0x180014d56  mov     edi, 26Fh
0x180014d5b  jmp     loc_180014BA8
0x180014d60  mov     rax, [rbp+57h+var_68]
0x180014d64  mov     rdx, [rax+10h]
0x180014d68  test    rdx, rdx
0x180014d6b  jnz     short loc_180014D96
0x180014d6d  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180014d73  cmp     ecx, 0FFFFFFFFh
0x180014d76  jz      short loc_180014D8A
0x180014d78  lea     r8, aRasentrydlgwFa; "RasEntryDlgW: Failed to read the entry"
0x180014d7f  mov     edx, 0Ch; dwFlags
0x180014d84  call    cs:__imp_TracePrintfExA
0x180014d8a  lea     rcx, [rbp+57h+var_60]
0x180014d8e  call    cs:__imp_ClosePhonebookFile
0x180014d94  jmp     short loc_180014D56
0x180014d96  cmp     [rdx+224h], r12d
0x180014d9d  jnz     short loc_180014DC0
0x180014d9f  mov     rdx, [rdx+1C0h]
0x180014da6  lea     r8, [rbp+57h+var_70]
0x180014daa  xor     ecx, ecx
0x180014dac  mov     [rbp+57h+var_70], r12d
0x180014db0  call    cs:__imp_RasIsTrustedCustomDll
0x180014db6  test    eax, eax
0x180014db8  jnz     short loc_180014DC5
0x180014dba  cmp     [rbp+57h+var_70], r12d
0x180014dbe  jz      short loc_180014DC5
0x180014dc0  mov     esi, r12d
0x180014dc3  jmp     short loc_180014DD2
0x180014dc5  cmp     dword ptr [rbp+57h+var_60+8], r12d
0x180014dc9  mov     esi, 1
0x180014dce  cmovnz  esi, r12d
0x180014dd2  lea     rcx, [rbp+57h+var_60]
0x180014dd6  call    cs:__imp_ClosePhonebookFile
0x180014ddc  test    esi, esi
0x180014dde  jz      short loc_180014E0F
0x180014de0  test    dword ptr [rbx+0Ch], 40000000h
0x180014de7  jz      short loc_180014DF8
0x180014de9  mov     dword ptr [rbx+21Ch], 5
0x180014df3  jmp     loc_180014BB6
0x180014df8  lea     r9, [rbp+57h+uID]
0x180014dfc  mov     r8, rbx
0x180014dff  mov     rdx, r14
0x180014e02  mov     rcx, r15
0x180014e05  call    LaunchRasPropertiesEditAsAdmin
0x180014e0a  mov     eax, [rbp+57h+uID]
0x180014e0d  jmp     short loc_180014E1D
0x180014e0f  mov     r8, rbx
0x180014e12  mov     rdx, r14
0x180014e15  mov     rcx, r15
0x180014e18  call    RasEntryDlgPropertiesEdit
0x180014e1d  lea     r11, [rsp+0B0h+var_20]
0x180014e25  mov     rbx, [r11+30h]
0x180014e29  mov     rsi, [r11+38h]
0x180014e2d  mov     rsp, r11
0x180014e30  pop     r15
0x180014e32  pop     r14
0x180014e34  pop     r12
0x180014e36  pop     rdi
0x180014e37  pop     rbp
0x180014e38  retn
```
