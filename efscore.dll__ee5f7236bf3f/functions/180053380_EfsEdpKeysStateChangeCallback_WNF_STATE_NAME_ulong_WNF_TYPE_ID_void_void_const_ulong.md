# EfsEdpKeysStateChangeCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)

- ea: `0x180053380`
- end: `0x180053769`
- name: `?EfsEdpKeysStateChangeCallback@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z`
- size: `1001`
- prototype: `__int64 __fastcall(struct _WNF_STATE_NAME, unsigned int, struct _WNF_TYPE_ID *, void *, const void *, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000505d`
- `0x180053380`
- `0x180053970`
- `0x180054210`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800535de`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800535de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800534da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800535cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180053708`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800534da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800535cd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180053708`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800534e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180053716`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800534e8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180053716`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800535bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053641`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053663`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053682`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800535bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053641`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053663`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053682`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800534cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800536f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800534cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800536f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800534b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800536e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800534b8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800536e6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800535b5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180053609`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800535b5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180053609`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005361a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18005361a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x1800536d3`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x1800536d3`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x180053465`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x180053465`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180053511`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180053511`

## pseudocode

```c
__int64 __fastcall EfsEdpKeysStateChangeCallback(
        struct _WNF_STATE_NAME a1,
        __int64 a2,
        struct _WNF_TYPE_ID *a3,
        void *a4,
        _DWORD *a5,
        unsigned int a6)
{
  PSID *v6; // rbx
  int v7; // ecx
  unsigned int v8; // edi
  int v9; // r8d
  _DWORD *v10; // r14
  unsigned int i; // esi
  HANDLE ProcessHeap; // rax
  int v13; // ecx
  DWORD v14; // ebx
  HANDLE v15; // rax
  signed int LastError; // eax
  signed int v17; // eax
  signed int v18; // eax
  HANDLE v19; // rax
  char ReturnLength; // [rsp+20h] [rbp-50h]
  DWORD TokenInformationLength; // [rsp+40h] [rbp-30h] BYREF
  unsigned int v23; // [rsp+44h] [rbp-2Ch] BYREF
  DWORD v24; // [rsp+48h] [rbp-28h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-20h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp-18h] BYREF
  __int64 v27; // [rsp+60h] [rbp-10h] BYREF
  struct _WNF_STATE_NAME Buf2; // [rsp+A0h] [rbp+30h] BYREF

  Buf2 = a1;
  v27 = 0;
  v23 = 0;
  hObject = 0;
  v6 = 0;
  TokenInformationLength = 0;
  v24 = 0;
  hMem = 0;
  fnEfsLogTrace1Strings(a1.Data[0], (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 45, 43);
  if ( memcmp_0(&WNF_EDP_DPL_KEYS_STATE, &Buf2, 8u) )
  {
    ReturnLength = 46;
LABEL_3:
    v8 = -2147024809;
    v9 = -2147024809;
    goto LABEL_41;
  }
  if ( a6 != 16 )
  {
    ReturnLength = 50;
    goto LABEL_3;
  }
  v10 = a5;
  if ( !a5 )
  {
    v8 = -2147024809;
    fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024809, 45, 53);
    goto LABEL_42;
  }
  fnEfsLogTrace1Strings(v7, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 45, 59);
  v8 = UMgrEnumerateSessionUsers(&v23, &v27);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              v8,
              45,
              59) >= 0 )
  {
    for ( i = 0; i < v23; ++i )
    {
      if ( hMem )
      {
        LocalFree(hMem);
        hMem = 0;
      }
      if ( hObject )
      {
        CloseHandle(hObject);
        hObject = 0;
      }
      if ( v6 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v6);
        v6 = 0;
      }
      if ( *(_DWORD *)(v27 + 16LL * i + 8) == v10[3] )
      {
        v8 = UMgrQueryUserToken(*(_QWORD *)(v27 + 16LL * i), &hObject);
        if ( v8 == -2147023584 )
        {
          v8 = 0;
          fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_STATUS, 0, 45, 88);
        }
        else
        {
          fnEfsLogTrace1Strings(v13, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 45, 92);
          if ( (int)fnEfsLogTrace1String1Dword(
                      g_hPublisher,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                      (unsigned int)&sourceString,
                      v8,
                      45,
                      92) < 0 )
            break;
          if ( !GetTokenInformation(hObject, TokenUser, 0, 0, &TokenInformationLength) && GetLastError() != 122 )
          {
            LastError = GetLastError();
            v8 = LastError;
            if ( LastError > 0 )
              v8 = (unsigned __int16)LastError | 0x80070000;
            ReturnLength = 106;
            goto LABEL_33;
          }
          v14 = TokenInformationLength;
          v15 = GetProcessHeap();
          v6 = (PSID *)HeapAlloc(v15, 8u, v14);
          if ( !v6 )
          {
            v8 = -2147024882;
            ReturnLength = 111;
            v9 = -2147024882;
LABEL_41:
            fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v9, 45, ReturnLength);
            break;
          }
          if ( !GetTokenInformation(hObject, TokenUser, v6, TokenInformationLength, &v24) )
          {
            v18 = GetLastError();
            v8 = v18;
            if ( v18 > 0 )
              v8 = (unsigned __int16)v18 | 0x80070000;
            ReturnLength = 119;
            goto LABEL_33;
          }
          if ( !ConvertSidToStringSidW(*v6, (LPWSTR *)&hMem) )
          {
            v17 = GetLastError();
            v8 = v17;
            if ( v17 > 0 )
              v8 = (unsigned __int16)v17 | 0x80070000;
            ReturnLength = 0x80;
LABEL_33:
            v9 = v8;
            goto LABEL_41;
          }
          if ( v10[2] )
            EfsPauseEdpUserDecryptionOnLock((wchar_t *)hMem);
          else
            EfsInitializeEdpUserDecryptionContextOnUnlock((const unsigned __int16 *)hMem);
        }
      }
    }
  }
LABEL_42:
  if ( v27 )
  {
    UMgrFreeSessionUsers();
    v27 = 0;
  }
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( v6 )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v6);
  }
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    v8,
    45,
    160);
  return 0;
}

```

## disassembly

```asm
0x180053380  mov     rax, rsp
0x180053383  mov     [rax+10h], rbx
0x180053387  mov     [rax+18h], rsi
0x18005338b  mov     [rax+8], rcx
0x18005338f  push    rbp
0x180053390  push    rdi
0x180053391  push    r12
0x180053393  push    r14
0x180053395  push    r15
0x180053397  mov     rbp, rsp
0x18005339a  sub     rsp, 70h
0x18005339e  xor     r15d, r15d
0x1800533a1  mov     dword ptr [rax-78h], 52Bh
0x1800533a8  lea     r8, sourceString
0x1800533af  mov     [rbp+var_10], r15
0x1800533b3  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800533ba  mov     [rbp+var_2C], r15d
0x1800533be  mov     [rbp+hObject], r15
0x1800533c2  mov     ebx, r15d
0x1800533c5  lea     r12d, [r15+2Dh]
0x1800533c9  mov     [rbp+TokenInformationLength], r15d
0x1800533cd  mov     r9d, r12d
0x1800533d0  mov     [rbp+var_28], r15d
0x1800533d4  mov     [rbp+hMem], r15
0x1800533d8  call    fnEfsLogTrace1Strings
0x1800533dd  lea     r8d, [r15+8]; Size
0x1800533e1  lea     rdx, [rbp+Buf2]; Buf2
0x1800533e5  lea     rcx, WNF_EDP_DPL_KEYS_STATE; Buf1
0x1800533ec  call    memcmp_0
0x1800533f1  test    eax, eax
0x1800533f3  jz      short loc_18005340D
0x1800533f5  mov     dword ptr [rsp+70h+ReturnLength], 52Eh
0x1800533fd  mov     edi, 80070057h
0x180053402  mov     r8d, 80070057h
0x180053408  jmp     loc_1800536B4
0x18005340d  cmp     [rbp+arg_28], 10h
0x180053411  jz      short loc_18005341D
0x180053413  mov     dword ptr [rsp+70h+ReturnLength], 532h
0x18005341b  jmp     short loc_1800533FD
0x18005341d  mov     r14, [rbp+arg_20]
0x180053421  mov     r9d, r12d
0x180053424  test    r14, r14
0x180053427  jnz     short loc_180053441
0x180053429  mov     edi, 80070057h
0x18005342e  mov     dword ptr [rsp+70h+ReturnLength], 535h
0x180053436  mov     r8d, 80070057h
0x18005343c  jmp     loc_1800536B7
0x180053441  mov     esi, 53Bh
0x180053446  lea     r8, sourceString
0x18005344d  lea     rdx, EFS_TRACE_START_EVENT
0x180053454  mov     dword ptr [rsp+70h+ReturnLength], esi
0x180053458  call    fnEfsLogTrace1Strings
0x18005345d  lea     rdx, [rbp+var_10]
0x180053461  lea     rcx, [rbp+var_2C]
0x180053465  call    cs:__imp_UMgrEnumerateSessionUsers
0x18005346b  mov     rcx, cs:g_hPublisher
0x180053472  lea     r9, sourceString
0x180053479  mov     [rsp+70h+var_40], esi
0x18005347d  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180053484  mov     [rsp+70h+var_48], r12d
0x180053489  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x180053490  mov     edi, eax
0x180053492  mov     dword ptr [rsp+70h+ReturnLength], eax
0x180053496  call    fnEfsLogTrace1String1Dword
0x18005349b  test    eax, eax
0x18005349d  js      loc_1800536CA
0x1800534a3  mov     esi, r15d
0x1800534a6  cmp     esi, [rbp+var_2C]
0x1800534a9  jnb     loc_1800536CA
0x1800534af  mov     rcx, [rbp+hMem]; hMem
0x1800534b3  test    rcx, rcx
0x1800534b6  jz      short loc_1800534C2
0x1800534b8  call    cs:__imp_LocalFree
0x1800534be  mov     [rbp+hMem], r15
0x1800534c2  mov     rcx, [rbp+hObject]; hObject
0x1800534c6  test    rcx, rcx
0x1800534c9  jz      short loc_1800534D5
0x1800534cb  call    cs:__imp_CloseHandle
0x1800534d1  mov     [rbp+hObject], r15
0x1800534d5  test    rbx, rbx
0x1800534d8  jz      short loc_1800534F1
0x1800534da  call    cs:__imp_GetProcessHeap
0x1800534e0  mov     r8, rbx; lpMem
0x1800534e3  xor     edx, edx; dwFlags
0x1800534e5  mov     rcx, rax; hHeap
0x1800534e8  call    cs:__imp_HeapFree
0x1800534ee  mov     rbx, r15
0x1800534f1  mov     r8, [rbp+var_10]
0x1800534f5  mov     eax, [r14+0Ch]
0x1800534f9  mov     ecx, esi
0x1800534fb  add     rcx, rcx
0x1800534fe  cmp     [r8+rcx*8+8], eax
0x180053503  jnz     loc_18005363A
0x180053509  mov     rcx, [r8+rcx*8]
0x18005350d  lea     rdx, [rbp+hObject]
0x180053511  call    cs:__imp_UMgrQueryUserToken
0x180053517  mov     edi, eax
0x180053519  mov     r9d, r12d
0x18005351c  cmp     eax, 80070520h
0x180053521  jnz     short loc_180053549
0x180053523  mov     rcx, cs:g_hPublisher
0x18005352a  lea     rdx, EFS_TRACE_STATUS
0x180053531  xor     r8d, r8d
0x180053534  mov     dword ptr [rsp+70h+ReturnLength], 558h
0x18005353c  mov     edi, r15d
0x18005353f  call    fnEfsLogTrace1
0x180053544  jmp     loc_18005363A
0x180053549  lea     r8, sourceString
0x180053550  mov     dword ptr [rsp+70h+ReturnLength], 55Ch
0x180053558  lea     rdx, EFS_TRACE_START_EVENT
0x18005355f  call    fnEfsLogTrace1Strings
0x180053564  mov     rcx, cs:g_hPublisher
0x18005356b  lea     r9, sourceString
0x180053572  mov     [rsp+70h+var_40], 55Ch
0x18005357a  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x180053581  mov     [rsp+70h+var_48], r12d
0x180053586  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x18005358d  mov     dword ptr [rsp+70h+ReturnLength], edi
0x180053591  call    fnEfsLogTrace1String1Dword
0x180053596  test    eax, eax
0x180053598  js      loc_1800536CA
0x18005359e  mov     rcx, [rbp+hObject]; TokenHandle
0x1800535a2  lea     rax, [rbp+TokenInformationLength]
0x1800535a6  xor     r9d, r9d; TokenInformationLength
0x1800535a9  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x1800535ae  xor     r8d, r8d; TokenInformation
0x1800535b1  lea     edx, [r9+1]; TokenInformationClass
0x1800535b5  call    cs:__imp_GetTokenInformation
0x1800535bb  test    eax, eax
0x1800535bd  jnz     short loc_1800535CA
0x1800535bf  call    cs:__imp_GetLastError
0x1800535c5  cmp     eax, 7Ah ; 'z'
0x1800535c8  jnz     short loc_180053641
0x1800535ca  mov     ebx, [rbp+TokenInformationLength]
0x1800535cd  call    cs:__imp_GetProcessHeap
0x1800535d3  mov     r8d, ebx; dwBytes
0x1800535d6  mov     edx, 8; dwFlags
0x1800535db  mov     rcx, rax; hHeap
0x1800535de  call    cs:__imp_HeapAlloc
0x1800535e4  mov     rbx, rax
0x1800535e7  test    rax, rax
0x1800535ea  jz      loc_1800536A1
0x1800535f0  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800535f4  lea     rax, [rbp+var_28]
0x1800535f8  mov     rcx, [rbp+hObject]; TokenHandle
0x1800535fc  mov     r8, rbx; TokenInformation
0x1800535ff  mov     edx, 1; TokenInformationClass
0x180053604  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180053609  call    cs:__imp_GetTokenInformation
0x18005360f  test    eax, eax
0x180053611  jz      short loc_180053682
0x180053613  mov     rcx, [rbx]; Sid
0x180053616  lea     rdx, [rbp+hMem]; StringSid
0x18005361a  call    cs:__imp_ConvertSidToStringSidW
0x180053620  test    eax, eax
0x180053622  jz      short loc_180053663
0x180053624  mov     rcx, [rbp+hMem]; String1
0x180053628  cmp     [r14+8], r15d
0x18005362c  jnz     short loc_180053635
0x18005362e  call    ?EfsInitializeEdpUserDecryptionContextOnUnlock@@YAXPEBG@Z; EfsInitializeEdpUserDecryptionContextOnUnlock(ushort const *)
0x180053633  jmp     short loc_18005363A
0x180053635  call    ?EfsPauseEdpUserDecryptionOnLock@@YAXPEBG@Z; EfsPauseEdpUserDecryptionOnLock(ushort const *)
0x18005363a  inc     esi
0x18005363c  jmp     loc_1800534A6
0x180053641  call    cs:__imp_GetLastError
0x180053647  mov     edi, eax
0x180053649  test    eax, eax
0x18005364b  jle     short loc_180053656
0x18005364d  movzx   edi, ax
0x180053650  or      edi, 80070000h
0x180053656  mov     dword ptr [rsp+70h+ReturnLength], 56Ah
0x18005365e  mov     r8d, edi
0x180053661  jmp     short loc_1800536B4
0x180053663  call    cs:__imp_GetLastError
0x180053669  mov     edi, eax
0x18005366b  test    eax, eax
0x18005366d  jle     short loc_180053678
0x18005366f  movzx   edi, ax
0x180053672  or      edi, 80070000h
0x180053678  mov     dword ptr [rsp+70h+ReturnLength], 580h
0x180053680  jmp     short loc_18005365E
0x180053682  call    cs:__imp_GetLastError
0x180053688  mov     edi, eax
0x18005368a  test    eax, eax
0x18005368c  jle     short loc_180053697
0x18005368e  movzx   edi, ax
0x180053691  or      edi, 80070000h
0x180053697  mov     dword ptr [rsp+70h+ReturnLength], 577h
0x18005369f  jmp     short loc_18005365E
0x1800536a1  mov     edi, 8007000Eh
0x1800536a6  mov     dword ptr [rsp+70h+ReturnLength], 56Fh
0x1800536ae  mov     r8d, 8007000Eh
0x1800536b4  mov     r9d, r12d
0x1800536b7  mov     rcx, cs:g_hPublisher
0x1800536be  lea     rdx, EFS_TRACE_ERROR
0x1800536c5  call    fnEfsLogTrace1
0x1800536ca  mov     rcx, [rbp+var_10]
0x1800536ce  test    rcx, rcx
0x1800536d1  jz      short loc_1800536DD
0x1800536d3  call    cs:__imp_UMgrFreeSessionUsers
0x1800536d9  mov     [rbp+var_10], r15
0x1800536dd  mov     rcx, [rbp+hMem]; hMem
0x1800536e1  test    rcx, rcx
0x1800536e4  jz      short loc_1800536F0
0x1800536e6  call    cs:__imp_LocalFree
0x1800536ec  mov     [rbp+hMem], r15
0x1800536f0  mov     rcx, [rbp+hObject]; hObject
0x1800536f4  test    rcx, rcx
0x1800536f7  jz      short loc_180053703
0x1800536f9  call    cs:__imp_CloseHandle
0x1800536ff  mov     [rbp+hObject], r15
0x180053703  test    rbx, rbx
0x180053706  jz      short loc_18005371C
0x180053708  call    cs:__imp_GetProcessHeap
0x18005370e  mov     r8, rbx; lpMem
0x180053711  xor     edx, edx; dwFlags
0x180053713  mov     rcx, rax; hHeap
0x180053716  call    cs:__imp_HeapFree
0x18005371c  mov     rcx, cs:g_hPublisher
0x180053723  lea     r9, sourceString
0x18005372a  mov     [rsp+70h+var_40], 5A0h
0x180053732  lea     r8, EFS_TRACE_LEAVE_HR_EVENT_ERROR
0x180053739  mov     [rsp+70h+var_48], r12d
0x18005373e  lea     rdx, EFS_TRACE_LEAVE_HR_EVENT
0x180053745  mov     dword ptr [rsp+70h+ReturnLength], edi
0x180053749  call    fnEfsLogTrace1String1Dword
0x18005374e  lea     r11, [rsp+70h+var_s0]
0x180053753  xor     eax, eax
0x180053755  mov     rbx, [r11+38h]
0x180053759  mov     rsi, [r11+40h]
0x18005375d  mov     rsp, r11
0x180053760  pop     r15
0x180053762  pop     r14
0x180053764  pop     r12
0x180053766  pop     rdi
0x180053767  pop     rbp
0x180053768  retn
```
