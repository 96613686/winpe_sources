# EfsCheckInitializeDecryptionRequestForUser(HKEY__ *,ushort const *,ushort const *,_EFS_DECRYPT_REQUEST_TYPE,_EFS_DECRYPT_REQUEST * *)

- ea: `0x180051be0`
- end: `0x180052327`
- name: `?EfsCheckInitializeDecryptionRequestForUser@@YAJPEAUHKEY__@@PEBG1W4_EFS_DECRYPT_REQUEST_TYPE@@PEAPEAU_EFS_DECRYPT_REQUEST@@@Z`
- size: `1863`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180053970`

## callees

- `0x1800124d8`
- `0x180048b58`
- `0x180051be0`
- `0x180052330`
- `0x1800567c8`
- `0x180062320`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180051e8a`
- `msvcrt!_wcsicmp` at `0x180051e8a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180051d7b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180051e4a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180051fbd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180051d7b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180051e4a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180051fbd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180051d6c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180051e38`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180051fac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005227c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005229a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180051d6c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180051e38`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180051fac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005227c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18005229a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005228a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800522a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18005228a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800522a8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051cdb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051d50`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051dcc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051f91`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005201e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005208e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051cdb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051d50`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051dcc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180051f91`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005201e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005208e`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180052217`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180052217`

## string_xrefs

- `0x180051d39`: `CompletedUsers`
- `0x180051db5`: `CompletedUsers`
- `0x180051cc4`: `Completed`
- `0x180051f74`: `DecryptPaths`
- `0x180052001`: `DecryptPaths`

## pseudocode

```c
__int64 __fastcall EfsCheckInitializeDecryptionRequestForUser(
        HKEY a1,
        const wchar_t *a2,
        const WCHAR *a3,
        int a4,
        unsigned __int16 ***a5)
{
  void *v9; // r13
  int v10; // edi
  int v11; // r8d
  LSTATUS ValueW; // eax
  LSTATUS v13; // eax
  DWORD v14; // ebx
  HANDLE ProcessHeap; // rax
  void *pvData; // rsi
  HANDLE v17; // rax
  unsigned __int16 **v18; // rax
  int v19; // ecx
  unsigned __int16 **v20; // r15
  const wchar_t *i; // rbx
  __int64 v22; // rax
  HKEY v23; // rbx
  LSTATUS v24; // eax
  DWORD v25; // ebx
  HANDLE v26; // rax
  unsigned __int16 *v27; // rax
  int v28; // r8d
  __int64 *v29; // rdx
  LSTATUS v30; // eax
  unsigned __int64 v31; // rax
  int v32; // eax
  int v33; // ecx
  unsigned __int64 v34; // rax
  int v35; // eax
  int v36; // ecx
  int v37; // eax
  HANDLE v38; // rax
  HANDLE v39; // rax
  char pdwType; // [rsp+20h] [rbp-30h]
  char pdwTypea; // [rsp+20h] [rbp-30h]
  DWORD cbData; // [rsp+40h] [rbp-10h] BYREF
  LPCVOID lpData; // [rsp+48h] [rbp-8h] BYREF

  cbData = 0;
  lpData = 0;
  v9 = 0;
  fnEfsLogTrace1Strings((_DWORD)a1, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 45, 95);
  if ( a5 )
    *a5 = 0;
  if ( !a2 )
  {
    pdwType = 98;
LABEL_5:
    v10 = -2147024809;
    v11 = -2147024809;
LABEL_6:
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v11, 45, pdwType);
    goto LABEL_74;
  }
  if ( !a3 )
  {
    pdwType = 99;
    goto LABEL_5;
  }
  if ( !a5 )
  {
    v10 = -2147467261;
    pdwType = 100;
    v11 = -2147467261;
    goto LABEL_6;
  }
  if ( a4 == 1 )
  {
    ValueW = RegGetValueW(a1, a3, L"Completed", 0x20000002u, 0, 0, &cbData);
    v10 = ValueW;
    if ( ValueW )
    {
      if ( ValueW != 2 )
      {
        if ( ValueW > 0 )
          v10 = (unsigned __int16)ValueW | 0x80070000;
        pdwType = -124;
        v11 = v10;
        goto LABEL_6;
      }
    }
    else if ( cbData )
    {
      v10 = 1;
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, 1, 45, 126);
      goto LABEL_74;
    }
    v13 = RegGetValueW(a1, a3, L"CompletedUsers", 0x20000020u, 0, 0, &cbData);
    v10 = v13;
    if ( v13 )
    {
      pvData = 0;
      if ( v13 == 2 )
      {
        fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, 0, 45, 162);
        goto LABEL_31;
      }
    }
    else
    {
      v14 = cbData;
      ProcessHeap = GetProcessHeap();
      pvData = HeapAlloc(ProcessHeap, 8u, v14);
      if ( !pvData )
      {
        v10 = -2147024882;
        pdwType = -106;
        v11 = -2147024882;
        goto LABEL_6;
      }
      v10 = RegGetValueW(a1, a3, L"CompletedUsers", 0x20000020u, 0, pvData, &cbData);
    }
    if ( v10 )
    {
      if ( v10 > 0 )
        v10 = (unsigned __int16)v10 | 0x80070000;
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v10, 45, 167);
      goto LABEL_70;
    }
    if ( pvData )
    {
      for ( i = (const wchar_t *)pvData; *i; i += v22 + 1 )
      {
        if ( !_wcsicmp(i, a2) )
        {
          v10 = 1;
          fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, 1, 45, 182);
          goto LABEL_71;
        }
        v22 = -1;
        do
          ++v22;
        while ( i[v22] );
      }
    }
LABEL_31:
    v17 = GetProcessHeap();
    v18 = (unsigned __int16 **)HeapAlloc(v17, 8u, 0x38u);
    v20 = v18;
    if ( !v18 )
    {
      v10 = -2147024882;
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024882, 45, 194);
      goto LABEL_70;
    }
    *(_OWORD *)v18 = 0;
    *((_OWORD *)v18 + 1) = 0;
    *((_OWORD *)v18 + 2) = 0;
    v18[6] = 0;
    v18[1] = (unsigned __int16 *)v18;
    *v18 = (unsigned __int16 *)v18;
    fnEfsLogTrace1Strings(v19, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 45, 199);
    v10 = EfsStringDup(v20 + 2, a3, EfsStringDupDefaultAllocate, (void (*)(void *))EfsStringDupDefaultFree);
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                v10,
                45,
                199) < 0 )
      goto LABEL_69;
    v23 = a1;
    v24 = RegGetValueW(a1, a3, L"DecryptPaths", 0x20000020u, 0, 0, &cbData);
    if ( v24 )
    {
      if ( v24 != 2 && cbData )
        goto LABEL_50;
    }
    else if ( cbData )
    {
      v25 = cbData;
      v26 = GetProcessHeap();
      v27 = (unsigned __int16 *)HeapAlloc(v26, 8u, v25);
      v20[3] = v27;
      if ( !v27 )
      {
        v10 = -2147024882;
        pdwTypea = -44;
        v28 = -2147024882;
LABEL_46:
        v29 = EFS_TRACE_ERROR;
LABEL_68:
        fnEfsLogTrace1(g_hPublisher, (_DWORD)v29, v28, 45, pdwTypea);
LABEL_69:
        EfsCheckUpdateFreeDecryptionReuestForUser(a2, (struct _EFS_DECRYPT_REQUEST *)v20);
        goto LABEL_70;
      }
      v23 = a1;
      v24 = RegGetValueW(a1, a3, L"DecryptPaths", 0x20000020u, 0, v27, &cbData);
LABEL_50:
      if ( !v24 )
      {
        *((_DWORD *)v20 + 13) = a4;
        *a5 = v20;
        v30 = RegGetValueW(v23, a3, L"Initialized", 0x20000002u, 0, 0, &cbData);
        if ( !v30 && cbData )
          goto LABEL_70;
        if ( v30 == 2 || !cbData )
        {
          fnEfsLogTrace1Strings(cbData, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 45, 12);
          v31 = EfsUtcTimestamp();
          v32 = EfsUtcTimestampToLocalTimeString(v31, (unsigned __int16 **)&lpData);
          if ( (int)fnEfsLogTrace1String1Dword(
                      g_hPublisher,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                      (unsigned int)&sourceString,
                      v32,
                      45,
                      12) < 0 )
          {
            v9 = (void *)lpData;
            goto LABEL_70;
          }
          fnEfsLogTrace1Strings(v33, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 45, 14);
          v9 = (void *)lpData;
          v34 = -1;
          do
            ++v34;
          while ( *((_WORD *)lpData + v34) );
          v35 = ULongLongToULong(v34, &cbData);
          if ( (int)fnEfsLogTrace1String1Dword(
                      g_hPublisher,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                      (unsigned int)&sourceString,
                      v35,
                      45,
                      14) < 0
            || (fnEfsLogTrace1Strings(v36, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 45, 15),
                v37 = ULongLongToULong(2LL * cbData, &cbData),
                (int)fnEfsLogTrace1String1Dword(
                       g_hPublisher,
                       (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                       (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                       (unsigned int)&sourceString,
                       v37,
                       45,
                       15) < 0) )
          {
LABEL_70:
            if ( pvData )
            {
LABEL_71:
              v38 = GetProcessHeap();
              HeapFree(v38, 0, pvData);
            }
            goto LABEL_72;
          }
          RegSetKeyValueW(v23, a3, L"Initialized", 1u, v9, cbData);
        }
        v10 = 0;
        goto LABEL_70;
      }
      if ( v24 > 0 )
        v10 = (unsigned __int16)v24 | 0x80070000;
      else
        v10 = v24;
      pdwTypea = -20;
      v28 = v10;
      goto LABEL_46;
    }
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, 0, 45, 224);
    v28 = 1;
    pdwTypea = -26;
    v10 = 1;
    v29 = EFS_TRACE_STATUS;
    goto LABEL_68;
  }
  v10 = -2147024809;
  fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024809, 45, 104);
LABEL_72:
  if ( v9 )
  {
    v39 = GetProcessHeap();
    HeapFree(v39, 0, v9);
  }
LABEL_74:
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    v10,
    45,
    37);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180051be0  mov     rax, rsp
0x180051be3  mov     [rax+18h], rbx
0x180051be7  mov     [rax+20h], r9d
0x180051beb  mov     [rax+10h], rdx
0x180051bef  mov     [rax+8], rcx
0x180051bf3  push    rbp
0x180051bf4  push    rsi
0x180051bf5  push    rdi
0x180051bf6  push    r12
0x180051bf8  push    r13
0x180051bfa  push    r14
0x180051bfc  push    r15
0x180051bfe  mov     rbp, rsp
0x180051c01  sub     rsp, 50h
0x180051c05  xor     r14d, r14d
0x180051c08  mov     dword ptr [rax-68h], 25Fh
0x180051c0f  mov     edi, r9d
0x180051c12  mov     [rbp+cbData], r14d
0x180051c16  mov     r12, r8
0x180051c19  mov     [rbp+lpData], r14
0x180051c1d  mov     rbx, rdx
0x180051c20  lea     r8, sourceString
0x180051c27  lea     esi, [r14+2Dh]
0x180051c2b  mov     r15, rcx
0x180051c2e  mov     r9d, esi
0x180051c31  lea     rdx, EFS_TRACE_ENTER_EVENT
0x180051c38  mov     r13d, r14d
0x180051c3b  call    fnEfsLogTrace1Strings
0x180051c40  mov     rax, [rbp+arg_20]
0x180051c44  test    rax, rax
0x180051c47  jz      short loc_180051C4E
0x180051c49  xor     ecx, ecx
0x180051c4b  mov     [rax], rcx
0x180051c4e  test    rbx, rbx
0x180051c51  jnz     short loc_180051C81
0x180051c53  mov     dword ptr [rsp+50h+pdwType], 262h
0x180051c5b  mov     edi, 80070057h
0x180051c60  mov     r8d, 80070057h
0x180051c66  lea     rdx, EFS_TRACE_ERROR
0x180051c6d  mov     rcx, cs:g_hPublisher
0x180051c74  mov     r9d, esi
0x180051c77  call    fnEfsLogTrace1
0x180051c7c  jmp     loc_1800522AE
0x180051c81  test    r12, r12
0x180051c84  jnz     short loc_180051C90
0x180051c86  mov     dword ptr [rsp+50h+pdwType], 263h
0x180051c8e  jmp     short loc_180051C5B
0x180051c90  test    rax, rax
0x180051c93  jnz     short loc_180051CAA
0x180051c95  mov     edi, 80004003h
0x180051c9a  mov     dword ptr [rsp+50h+pdwType], 264h
0x180051ca2  mov     r8d, 80004003h
0x180051ca8  jmp     short loc_180051C66
0x180051caa  lea     eax, [rdi-1]
0x180051cad  test    eax, eax
0x180051caf  jnz     loc_1800522F9
0x180051cb5  lea     rax, [rbp+cbData]
0x180051cb9  mov     r9d, 20000002h; dwFlags
0x180051cbf  mov     [rsp+50h+pcbData], rax; pcbData
0x180051cc4  lea     r8, aCompleted; "Completed"
0x180051ccb  mov     [rsp+50h+pvData], r14; pvData
0x180051cd0  mov     rdx, r12; lpSubKey
0x180051cd3  mov     rcx, r15; hkey
0x180051cd6  mov     [rsp+50h+pdwType], r14; pdwType
0x180051cdb  call    cs:__imp_RegGetValueW
0x180051ce1  mov     edi, eax
0x180051ce3  test    eax, eax
0x180051ce5  jnz     short loc_180051D08
0x180051ce7  cmp     [rbp+cbData], r14d
0x180051ceb  jbe     short loc_180051D2A
0x180051ced  lea     r8d, [rax+1]
0x180051cf1  mov     dword ptr [rsp+50h+pdwType], 27Eh
0x180051cf9  mov     edi, r8d
0x180051cfc  lea     rdx, EFS_TRACE_STATUS
0x180051d03  jmp     loc_180051C6D
0x180051d08  cmp     eax, 2
0x180051d0b  jz      short loc_180051D2A
0x180051d0d  test    eax, eax
0x180051d0f  jle     short loc_180051D1A
0x180051d11  movzx   edi, ax
0x180051d14  or      edi, 80070000h
0x180051d1a  mov     dword ptr [rsp+50h+pdwType], 284h
0x180051d22  mov     r8d, edi
0x180051d25  jmp     loc_180051C66
0x180051d2a  lea     rax, [rbp+cbData]
0x180051d2e  mov     r9d, 20000020h; dwFlags
0x180051d34  mov     [rsp+50h+pcbData], rax; pcbData
0x180051d39  lea     r8, aCompletedusers; "CompletedUsers"
0x180051d40  mov     [rsp+50h+pvData], r14; pvData
0x180051d45  mov     rdx, r12; lpSubKey
0x180051d48  mov     rcx, r15; hkey
0x180051d4b  mov     [rsp+50h+pdwType], r14; pdwType
0x180051d50  call    cs:__imp_RegGetValueW
0x180051d56  xor     ecx, ecx
0x180051d58  lea     r14, EFS_TRACE_STATUS
0x180051d5f  mov     edi, eax
0x180051d61  test    eax, eax
0x180051d63  jnz     loc_180051E12
0x180051d69  mov     ebx, [rbp+cbData]
0x180051d6c  call    cs:__imp_GetProcessHeap
0x180051d72  mov     r8d, ebx; dwBytes
0x180051d75  lea     edx, [rdi+8]; dwFlags
0x180051d78  mov     rcx, rax; hHeap
0x180051d7b  call    cs:__imp_HeapAlloc
0x180051d81  xor     edx, edx
0x180051d83  mov     rsi, rax
0x180051d86  test    rax, rax
0x180051d89  jnz     short loc_180051DA6
0x180051d8b  mov     edi, 8007000Eh
0x180051d90  mov     dword ptr [rsp+50h+pdwType], 296h
0x180051d98  lea     esi, [rax+2Dh]
0x180051d9b  mov     r8d, 8007000Eh
0x180051da1  jmp     loc_180051C66
0x180051da6  lea     rax, [rbp+cbData]
0x180051daa  mov     r9d, 20000020h; dwFlags
0x180051db0  mov     [rsp+50h+pcbData], rax; pcbData
0x180051db5  lea     r8, aCompletedusers; "CompletedUsers"
0x180051dbc  mov     [rsp+50h+pvData], rsi; pvData
0x180051dc1  mov     rcx, r15; hkey
0x180051dc4  mov     [rsp+50h+pdwType], rdx; pdwType
0x180051dc9  mov     rdx, r12; lpSubKey
0x180051dcc  call    cs:__imp_RegGetValueW
0x180051dd2  mov     edi, eax
0x180051dd4  xor     ecx, ecx
0x180051dd6  test    edi, edi
0x180051dd8  jz      loc_180051E73
0x180051dde  jle     short loc_180051DE9
0x180051de0  movzx   edi, di
0x180051de3  or      edi, 80070000h
0x180051de9  mov     dword ptr [rsp+50h+pdwType], 2A7h
0x180051df1  mov     r9d, 2Dh ; '-'
0x180051df7  mov     r8d, edi
0x180051dfa  mov     rcx, cs:g_hPublisher
0x180051e01  lea     rdx, EFS_TRACE_ERROR
0x180051e08  call    fnEfsLogTrace1
0x180051e0d  jmp     loc_180052277
0x180051e12  mov     rsi, rcx
0x180051e15  cmp     eax, 2
0x180051e18  jnz     short loc_180051DD6
0x180051e1a  mov     rcx, cs:g_hPublisher
0x180051e21  lea     r9d, [rax+2Bh]
0x180051e25  xor     r8d, r8d
0x180051e28  mov     dword ptr [rsp+50h+pdwType], 2A2h
0x180051e30  mov     rdx, r14
0x180051e33  call    fnEfsLogTrace1
0x180051e38  call    cs:__imp_GetProcessHeap
0x180051e3e  mov     edx, 8; dwFlags
0x180051e43  mov     rcx, rax; hHeap
0x180051e46  lea     r8d, [rdx+30h]; dwBytes
0x180051e4a  call    cs:__imp_HeapAlloc
0x180051e50  mov     r15, rax
0x180051e53  mov     r9d, 2Dh ; '-'
0x180051e59  test    rax, rax
0x180051e5c  jnz     short loc_180051ED6
0x180051e5e  mov     edi, 8007000Eh
0x180051e63  mov     dword ptr [rsp+50h+pdwType], 2C2h
0x180051e6b  mov     r8d, 8007000Eh
0x180051e71  jmp     short loc_180051DFA
0x180051e73  test    rsi, rsi
0x180051e76  jz      short loc_180051E38
0x180051e78  mov     rdi, [rbp+String2]
0x180051e7c  mov     rbx, rsi
0x180051e7f  cmp     [rbx], cx
0x180051e82  jz      short loc_180051E38
0x180051e84  mov     rdx, rdi; String2
0x180051e87  mov     rcx, rbx; String1
0x180051e8a  call    cs:__imp__wcsicmp
0x180051e90  xor     ecx, ecx
0x180051e92  test    eax, eax
0x180051e94  jz      short loc_180051EAD
0x180051e96  or      rax, 0FFFFFFFFFFFFFFFFh
0x180051e9a  inc     rax
0x180051e9d  cmp     [rbx+rax*2], cx
0x180051ea1  jnz     short loc_180051E9A
0x180051ea3  lea     rbx, [rbx+rax*2]
0x180051ea7  add     rbx, 2
0x180051eab  jmp     short loc_180051E7F
0x180051ead  mov     rcx, cs:g_hPublisher
0x180051eb4  mov     r8d, 1
0x180051eba  mov     rdx, r14
0x180051ebd  mov     dword ptr [rsp+50h+pdwType], 2B6h
0x180051ec5  mov     edi, r8d
0x180051ec8  lea     r9d, [r8+2Ch]
0x180051ecc  call    fnEfsLogTrace1
0x180051ed1  jmp     loc_18005227C
0x180051ed6  xorps   xmm0, xmm0
0x180051ed9  lea     r8, sourceString
0x180051ee0  movups  xmmword ptr [r15], xmm0
0x180051ee4  xor     eax, eax
0x180051ee6  mov     ebx, 2C7h
0x180051eeb  movups  xmmword ptr [r15+10h], xmm0
0x180051ef0  lea     rdx, EFS_TRACE_START_EVENT
0x180051ef7  mov     dword ptr [rsp+50h+pdwType], ebx
0x180051efb  movups  xmmword ptr [r15+20h], xmm0
0x180051f00  mov     [r15+30h], rax
0x180051f04  mov     [r15+8], r15
0x180051f08  mov     [r15], r15
0x180051f0b  call    fnEfsLogTrace1Strings
0x180051f10  lea     rcx, [r15+10h]; unsigned __int16 **
0x180051f14  mov     rdx, r12; unsigned __int16 *
0x180051f17  lea     r9, EfsStringDupDefaultFree; void (*)(void *)
0x180051f1e  lea     r8, EfsStringDupDefaultAllocate; void *(*)(unsigned __int64)
0x180051f25  call    ?EfsStringDup@@YAJPEAPEAGPEBGP6APEAX_K@ZP6AXPEAX@Z@Z; EfsStringDup(ushort * *,ushort const *,void * (*)(unsigned __int64),void (*)(void *))
0x180051f2a  mov     rcx, cs:g_hPublisher
0x180051f31  lea     r9, sourceString
0x180051f38  mov     dword ptr [rsp+50h+pcbData], ebx
0x180051f3c  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180051f43  mov     dword ptr [rsp+50h+pvData], 2Dh ; '-'
0x180051f4b  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180051f52  mov     dword ptr [rsp+50h+pdwType], eax
0x180051f56  mov     edi, eax
0x180051f58  call    fnEfsLogTrace1String1Dword
0x180051f5d  xor     ecx, ecx
0x180051f5f  test    eax, eax
0x180051f61  js      loc_18005226B
0x180051f67  mov     rbx, [rbp+hkey]
0x180051f6b  lea     rax, [rbp+cbData]
0x180051f6f  mov     [rsp+50h+pcbData], rax; pcbData
0x180051f74  lea     r8, aDecryptpaths; "DecryptPaths"
0x180051f7b  mov     [rsp+50h+pvData], rcx; pvData
0x180051f80  mov     r9d, 20000020h; dwFlags
0x180051f86  mov     [rsp+50h+pdwType], rcx; pdwType
0x180051f8b  mov     rdx, r12; lpSubKey
0x180051f8e  mov     rcx, rbx; hkey
0x180051f91  call    cs:__imp_RegGetValueW
0x180051f97  mov     ecx, [rbp+cbData]
0x180051f9a  test    eax, eax
0x180051f9c  jnz     loc_180052026
0x180051fa2  test    ecx, ecx
0x180051fa4  jz      loc_180052228
0x180051faa  mov     ebx, ecx
0x180051fac  call    cs:__imp_GetProcessHeap
0x180051fb2  mov     r8d, ebx; dwBytes
0x180051fb5  mov     edx, 8; dwFlags
0x180051fba  mov     rcx, rax; hHeap
0x180051fbd  call    cs:__imp_HeapAlloc
0x180051fc3  xor     r14d, r14d
0x180051fc6  mov     [r15+18h], rax
0x180051fca  test    rax, rax
0x180051fcd  jnz     short loc_180051FF4
0x180051fcf  mov     edi, 8007000Eh
0x180051fd4  mov     dword ptr [rsp+50h+pdwType], 2D4h
0x180051fdc  mov     r8d, 8007000Eh
0x180051fe2  mov     r9d, 2Dh ; '-'
0x180051fe8  lea     rdx, EFS_TRACE_ERROR
0x180051fef  jmp     loc_18005225F
0x180051ff4  mov     rbx, [rbp+hkey]
0x180051ff8  lea     rcx, [rbp+cbData]
0x180051ffc  mov     [rsp+50h+pcbData], rcx; pcbData
0x180052001  lea     r8, aDecryptpaths; "DecryptPaths"
0x180052008  mov     [rsp+50h+pvData], rax; pvData
0x18005200d  mov     rcx, rbx; hkey
0x180052010  mov     r9d, 20000020h; dwFlags
0x180052016  mov     [rsp+50h+pdwType], r14; pdwType
0x18005201b  mov     rdx, r12; lpSubKey
0x18005201e  call    cs:__imp_RegGetValueW
0x180052024  jmp     short loc_18005203A
0x180052026  cmp     eax, 2
0x180052029  jz      loc_180052228
0x18005202f  test    ecx, ecx
0x180052031  jz      loc_180052228
0x180052037  xor     r14d, r14d
0x18005203a  test    eax, eax
0x18005203c  jz      short loc_18005205A
0x18005203e  jg      short loc_180052044
0x180052040  mov     edi, eax
0x180052042  jmp     short loc_18005204D
0x180052044  movzx   edi, ax
0x180052047  or      edi, 80070000h
0x18005204d  mov     dword ptr [rsp+50h+pdwType], 2ECh
0x180052055  mov     r8d, edi
0x180052058  jmp     short loc_180051FE2
0x18005205a  mov     eax, [rbp+arg_18]
0x18005205d  lea     r8, aInitialized; "Initialized"
0x180052064  mov     [r15+34h], eax
0x180052068  mov     r9d, 20000002h; dwFlags
0x18005206e  mov     rax, [rbp+arg_20]
0x180052072  mov     rdx, r12; lpSubKey
0x180052075  mov     rcx, rbx; hkey
0x180052078  mov     [rax], r15
0x18005207b  lea     rax, [rbp+cbData]
0x18005207f  mov     [rsp+50h+pcbData], rax; pcbData
0x180052084  mov     [rsp+50h+pvData], r14; pvData
0x180052089  mov     [rsp+50h+pdwType], r14; pdwType
0x18005208e  call    cs:__imp_RegGetValueW
0x180052094  mov     ecx, [rbp+cbData]
0x180052097  test    eax, eax
0x180052099  jnz     short loc_1800520A3
0x18005209b  test    ecx, ecx
0x18005209d  jnz     loc_180052277
0x1800520a3  cmp     eax, 2
0x1800520a6  jz      short loc_1800520B0
0x1800520a8  test    ecx, ecx
0x1800520aa  jnz     loc_18005221D
0x1800520b0  mov     r15d, 2Dh ; '-'
0x1800520b6  lea     r13, sourceString
0x1800520bd  mov     r14d, 30Ch
0x1800520c3  lea     rdx, EFS_TRACE_START_EVENT
0x1800520ca  mov     r9d, r15d
0x1800520cd  mov     dword ptr [rsp+50h+pdwType], r14d
  ... truncated ...
```
