# CDplUser::SaveDuck(CDplDuck *)

- ea: `0x1800bc65c`
- end: `0x1800bcc41`
- name: `?SaveDuck@CDplUser@@AEAAJPEAVCDplDuck@@@Z`
- size: `1509`
- prototype: `__int64 __fastcall(CDplUser *__hidden this, struct CDplDuck *)`
- caller_count: `3`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18009975c`
- `0x1800b0e7c`
- `0x1800bb988`

## callees

- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x1800649d4`
- `0x1800861ec`
- `0x180095d4c`
- `0x1800964ac`
- `0x18009652c`
- `0x1800ac870`
- `0x1800b1bc4`
- `0x1800b1f20`
- `0x1800bc65c`
- `0x1800bd7a8`
- `0x1800bd810`
- `0x1800c8260`
- `0x1800d5af8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bcba9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bcbc0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bcba9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bcbc0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800bca8a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800bca8a`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800bcafb`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800bcafb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bca28`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bca28`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800bcad1`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800bcad1`

## pseudocode

```c
__int64 __fastcall CDplUser::SaveDuck(CDplUser *this, struct CDplDuck *a2)
{
  WCHAR *v4; // rdi
  int v5; // ecx
  int v6; // r13d
  unsigned int DuckPersistencePath; // ebx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // r15
  const WCHAR *v13; // r12
  int v14; // ecx
  CDplUser *v15; // rcx
  int v16; // eax
  LSTATUS v17; // eax
  __int64 *v18; // rdx
  LSTATUS v19; // eax
  LSTATUS v20; // eax
  LSTATUS v21; // eax
  char phkResult; // [rsp+20h] [rbp-49h]
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-19h] BYREF
  LPCVOID lpData; // [rsp+58h] [rbp-11h] BYREF
  LPCWSTR v26; // [rsp+60h] [rbp-9h] BYREF
  unsigned __int64 v27; // [rsp+68h] [rbp-1h] BYREF
  void *v28[10]; // [rsp+70h] [rbp+7h] BYREF
  int v29; // [rsp+D0h] [rbp+67h] BYREF
  DWORD cbData; // [rsp+D8h] [rbp+6Fh] BYREF
  HKEY hKey; // [rsp+E0h] [rbp+77h] BYREF
  HKEY v32; // [rsp+E8h] [rbp+7Fh] BYREF

  v29 = 1;
  v26 = 0;
  lpData = 0;
  cbData = 0;
  v27 = 0;
  hKey = 0;
  v32 = 0;
  v4 = 0;
  v28[0] = 0;
  lpSubKey = 0;
  fnEfsLogTrace1Strings((_DWORD)this, (unsigned int)EFS_TRACE_ENTER_EVENT, (unsigned int)&sourceString, 40, 143);
  v6 = CDplUser::UserSvcLock(this);
  if ( !a2 || !*((_DWORD *)a2 + 30) )
  {
    phkResult = -103;
    goto LABEL_39;
  }
  fnEfsLogTrace1Strings(v5, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 157);
  DuckPersistencePath = EdpCredSvcShouldCheckCaller(&v29);
  if ( (int)fnEfsLogTrace1String1Dword(
              g_hPublisher,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT,
              (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
              (unsigned int)&sourceString,
              DuckPersistencePath,
              40,
              157) >= 0 )
  {
    if ( !v29
      || (fnEfsLogTrace1Strings(v8, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 165),
          DuckPersistencePath = CDplUser::CheckCaller((PSID *)this),
          (int)fnEfsLogTrace1String1Dword(
                 g_hPublisher,
                 (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                 (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                 (unsigned int)&sourceString,
                 DuckPersistencePath,
                 40,
                 165) >= 0) )
    {
      fnEfsLogTrace1Strings(v8, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 172);
      DuckPersistencePath = CDplUser::GetDuckPersistencePath(this, (unsigned __int16 **)&v26);
      if ( (int)fnEfsLogTrace1String1Dword(
                  g_hPublisher,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                  (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                  (unsigned int)&sourceString,
                  DuckPersistencePath,
                  40,
                  172) >= 0 )
      {
        fnEfsLogTrace1Strings(v9, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 178);
        DuckPersistencePath = CDplDuck::Serialize(a2, (unsigned __int8 **)&lpData, &cbData);
        if ( (int)fnEfsLogTrace1String1Dword(
                    g_hPublisher,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                    (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                    (unsigned int)&sourceString,
                    DuckPersistencePath,
                    40,
                    178) >= 0 )
        {
          if ( DuckPersistencePath )
          {
            phkResult = -70;
LABEL_39:
            DuckPersistencePath = 1;
            v18 = EFS_TRACE_STATUS;
            goto LABEL_40;
          }
          fnEfsLogTrace1Strings(v10, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 194);
          v11 = *((_QWORD *)a2 + 14);
          v12 = -1;
          if ( v11 + 1 >= v11 )
            v12 = v11 + 1;
          DuckPersistencePath = v11 + 1 < v11 ? 0x80070216 : 0;
          if ( (int)fnEfsLogTrace1String1Dword(
                      g_hPublisher,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                      (unsigned int)&sourceString,
                      DuckPersistencePath,
                      40,
                      194) >= 0 )
          {
            v13 = (const WCHAR *)(&CDplDuck::SaveValueName)[v12 & 1];
            fnEfsLogTrace1Strings(
              (unsigned int)&CDplDuck::SaveValueName,
              (unsigned int)EFS_TRACE_START_EVENT,
              (unsigned int)&sourceString,
              40,
              208);
            DuckPersistencePath = CDplServiceImpl::RevertToSelf(*((CDplServiceImpl **)this + 6), v28);
            if ( (int)fnEfsLogTrace1String1Dword(
                        g_hPublisher,
                        (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                        (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                        (unsigned int)&sourceString,
                        DuckPersistencePath,
                        40,
                        208) >= 0 )
            {
              fnEfsLogTrace1Strings(v14, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 40, 214);
              DuckPersistencePath = CDplUser::GetDuckPersistenceRoot(v15, (unsigned __int16 **)&lpSubKey, 0);
              v16 = fnEfsLogTrace1String1Dword(
                      g_hPublisher,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                      (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                      (unsigned int)&sourceString,
                      DuckPersistencePath,
                      40,
                      214);
              v4 = (WCHAR *)lpSubKey;
              if ( v16 >= 0 )
              {
                v17 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0xF003Fu, &hKey);
                if ( v17 )
                {
                  if ( v17 > 0 )
                    DuckPersistencePath = (unsigned __int16)v17 | 0x80070000;
                  else
                    DuckPersistencePath = v17;
                  phkResult = -32;
LABEL_20:
                  v18 = EFS_TRACE_ERROR;
LABEL_40:
                  fnEfsLogTrace1(g_hPublisher, (_DWORD)v18, DuckPersistencePath, 40, phkResult);
                  goto LABEL_41;
                }
                v19 = RegCreateKeyExW(hKey, *((LPCWSTR *)this + 13), 0, 0, 0, 0xF003Fu, 0, &v32, 0);
                if ( v19 )
                {
                  if ( v19 > 0 )
                    DuckPersistencePath = (unsigned __int16)v19 | 0x80070000;
                  else
                    DuckPersistencePath = v19;
                  phkResult = -17;
                  goto LABEL_20;
                }
                v20 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, v26, v13, 3u, lpData, cbData);
                if ( v20 )
                {
                  if ( v20 > 0 )
                    DuckPersistencePath = (unsigned __int16)v20 | 0x80070000;
                  else
                    DuckPersistencePath = v20;
                  phkResult = -5;
                  goto LABEL_20;
                }
                v21 = RegFlushKey(hKey);
                if ( v21 )
                {
                  if ( v21 > 0 )
                    DuckPersistencePath = (unsigned __int16)v21 | 0x80070000;
                  else
                    DuckPersistencePath = v21;
                  phkResult = 10;
                  goto LABEL_20;
                }
                *((_QWORD *)a2 + 14) = v12;
                *((_DWORD *)a2 + 30) = 0;
                if ( (int)ULongLongSub(v12, 1u, &v27) >= 0 )
                  CDplService::RegDeleteValueSecurely(v32, (LPCWSTR)(&CDplDuck::SaveValueName)[v27 & 1]);
              }
            }
          }
        }
      }
    }
  }
LABEL_41:
  CDplUser::UserSvcUnlock(this, v6);
  if ( lpData )
    DplibMemFree((void *)lpData);
  if ( v32 )
  {
    RegCloseKey(v32);
    v32 = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  CDplServiceImpl::RestoreImpersonation(*((CDplServiceImpl **)this + 6), v28);
  if ( v26 )
    DplibMemFree((void *)v26);
  if ( v4 )
    DplibMemFree(v4);
  fnEfsLogTrace1String1Dword(
    g_hPublisher,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT,
    (unsigned int)EFS_TRACE_LEAVE_HR_EVENT_ERROR,
    (unsigned int)&sourceString,
    DuckPersistencePath,
    40,
    61);
  return DuckPersistencePath;
}

```

## disassembly

```asm
0x1800bc65c  push    rbp
0x1800bc65e  push    rbx
0x1800bc65f  push    rsi
0x1800bc660  push    rdi
0x1800bc661  push    r12
0x1800bc663  push    r13
0x1800bc665  push    r14
0x1800bc667  push    r15
0x1800bc669  lea     rbp, [rsp-1Fh]
0x1800bc66e  sub     rsp, 88h
0x1800bc675  xor     r12d, r12d
0x1800bc678  mov     [rbp+57h+arg_0], 1
0x1800bc67f  mov     rsi, rdx
0x1800bc682  mov     [rbp+57h+var_60], r12
0x1800bc686  lea     r8, sourceString
0x1800bc68d  mov     [rbp+57h+lpData], r12
0x1800bc691  lea     rdx, EFS_TRACE_ENTER_EVENT
0x1800bc698  mov     [rbp+57h+cbData], r12d
0x1800bc69c  lea     r9d, [r12+28h]
0x1800bc6a1  mov     [rbp+57h+var_58], r12
0x1800bc6a5  mov     r14, rcx
0x1800bc6a8  mov     [rbp+57h+hKey], r12
0x1800bc6ac  mov     [rbp+57h+arg_18], r12
0x1800bc6b0  mov     edi, r12d
0x1800bc6b3  mov     [rbp+57h+var_50], r12
0x1800bc6b7  mov     [rbp+57h+lpSubKey], r12
0x1800bc6bb  mov     dword ptr [rsp+0C0h+phkResult], 48Fh
0x1800bc6c3  call    fnEfsLogTrace1Strings
0x1800bc6c8  mov     rcx, r14; this
0x1800bc6cb  call    ?UserSvcLock@CDplUser@@AEAAHXZ; CDplUser::UserSvcLock(void)
0x1800bc6d0  mov     r13d, eax
0x1800bc6d3  test    rsi, rsi
0x1800bc6d6  jz      loc_1800BCB5E
0x1800bc6dc  cmp     [rsi+78h], r12d
0x1800bc6e0  jz      loc_1800BCB5E
0x1800bc6e6  mov     r15d, 49Dh
0x1800bc6ec  lea     r9d, [r12+28h]
0x1800bc6f1  lea     r8, sourceString
0x1800bc6f8  mov     dword ptr [rsp+0C0h+phkResult], r15d
0x1800bc6fd  lea     rdx, EFS_TRACE_START_EVENT
0x1800bc704  call    fnEfsLogTrace1Strings
0x1800bc709  lea     rcx, [rbp+57h+arg_0]; int *
0x1800bc70d  call    ?EdpCredSvcShouldCheckCaller@@YAJPEAH@Z; EdpCredSvcShouldCheckCaller(int *)
0x1800bc712  mov     rcx, cs:g_hPublisher
0x1800bc719  lea     r9, sourceString
0x1800bc720  mov     dword ptr [rsp+0C0h+lpSecurityAttributes], r15d
0x1800bc725  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800bc72c  mov     [rsp+0C0h+samDesired], 28h ; '('
0x1800bc734  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800bc73b  mov     dword ptr [rsp+0C0h+phkResult], eax
0x1800bc73f  mov     ebx, eax
0x1800bc741  call    fnEfsLogTrace1String1Dword
0x1800bc746  test    eax, eax
0x1800bc748  js      loc_1800BCB87
0x1800bc74e  cmp     [rbp+57h+arg_0], r12d
0x1800bc752  jz      short loc_1800BC7BB
0x1800bc754  mov     r15d, 4A5h
0x1800bc75a  lea     r9d, [r12+28h]
0x1800bc75f  lea     r8, sourceString
0x1800bc766  mov     dword ptr [rsp+0C0h+phkResult], r15d
0x1800bc76b  lea     rdx, EFS_TRACE_START_EVENT
0x1800bc772  call    fnEfsLogTrace1Strings
0x1800bc777  mov     rcx, r14; this
0x1800bc77a  call    ?CheckCaller@CDplUser@@AEAAJXZ; CDplUser::CheckCaller(void)
0x1800bc77f  mov     rcx, cs:g_hPublisher
0x1800bc786  lea     r9, sourceString
0x1800bc78d  mov     dword ptr [rsp+0C0h+lpSecurityAttributes], r15d
0x1800bc792  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800bc799  mov     [rsp+0C0h+samDesired], 28h ; '('
0x1800bc7a1  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800bc7a8  mov     dword ptr [rsp+0C0h+phkResult], eax
0x1800bc7ac  mov     ebx, eax
0x1800bc7ae  call    fnEfsLogTrace1String1Dword
0x1800bc7b3  test    eax, eax
0x1800bc7b5  js      loc_1800BCB87
0x1800bc7bb  mov     r15d, 4ACh
0x1800bc7c1  lea     r8, sourceString
0x1800bc7c8  mov     r9d, 28h ; '('
0x1800bc7ce  mov     dword ptr [rsp+0C0h+phkResult], r15d
0x1800bc7d3  lea     rdx, EFS_TRACE_START_EVENT
0x1800bc7da  call    fnEfsLogTrace1Strings
0x1800bc7df  lea     rdx, [rbp+57h+var_60]; unsigned __int16 **
0x1800bc7e3  mov     rcx, r14; this
0x1800bc7e6  call    ?GetDuckPersistencePath@CDplUser@@AEAAJPEAPEAG@Z; CDplUser::GetDuckPersistencePath(ushort * *)
0x1800bc7eb  mov     rcx, cs:g_hPublisher
0x1800bc7f2  lea     r9, sourceString
0x1800bc7f9  mov     dword ptr [rsp+0C0h+lpSecurityAttributes], r15d
0x1800bc7fe  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800bc805  mov     [rsp+0C0h+samDesired], 28h ; '('
0x1800bc80d  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800bc814  mov     dword ptr [rsp+0C0h+phkResult], eax
0x1800bc818  mov     ebx, eax
0x1800bc81a  call    fnEfsLogTrace1String1Dword
0x1800bc81f  test    eax, eax
0x1800bc821  js      loc_1800BCB87
0x1800bc827  mov     r15d, 4B2h
0x1800bc82d  lea     r8, sourceString
0x1800bc834  mov     r9d, 28h ; '('
0x1800bc83a  mov     dword ptr [rsp+0C0h+phkResult], r15d
0x1800bc83f  lea     rdx, EFS_TRACE_START_EVENT
0x1800bc846  call    fnEfsLogTrace1Strings
0x1800bc84b  lea     r8, [rbp+57h+cbData]; unsigned int *
0x1800bc84f  mov     rcx, rsi; this
0x1800bc852  lea     rdx, [rbp+57h+lpData]; unsigned __int8 **
0x1800bc856  call    ?Serialize@CDplDuck@@AEAAJPEAPEAEPEAK@Z; CDplDuck::Serialize(uchar * *,ulong *)
0x1800bc85b  mov     rcx, cs:g_hPublisher
0x1800bc862  lea     r9, sourceString
0x1800bc869  mov     dword ptr [rsp+0C0h+lpSecurityAttributes], r15d
0x1800bc86e  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800bc875  mov     [rsp+0C0h+samDesired], 28h ; '('
0x1800bc87d  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800bc884  mov     dword ptr [rsp+0C0h+phkResult], eax
0x1800bc888  mov     ebx, eax
0x1800bc88a  call    fnEfsLogTrace1String1Dword
0x1800bc88f  test    eax, eax
0x1800bc891  js      loc_1800BCB87
0x1800bc897  mov     r9d, 28h ; '('
0x1800bc89d  test    ebx, ebx
0x1800bc89f  jz      short loc_1800BC8AE
0x1800bc8a1  mov     dword ptr [rsp+0C0h+phkResult], 4BAh
0x1800bc8a9  jmp     loc_1800BCB6C
0x1800bc8ae  mov     r12d, 4C2h
0x1800bc8b4  lea     r8, sourceString
0x1800bc8bb  lea     rdx, EFS_TRACE_START_EVENT
0x1800bc8c2  mov     dword ptr [rsp+0C0h+phkResult], r12d
0x1800bc8c7  call    fnEfsLogTrace1Strings
0x1800bc8cc  mov     rcx, [rsi+70h]
0x1800bc8d0  lea     r9, sourceString
0x1800bc8d7  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800bc8db  mov     dword ptr [rsp+0C0h+lpSecurityAttributes], r12d
0x1800bc8e0  mov     [rsp+0C0h+samDesired], 28h ; '('
0x1800bc8e8  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800bc8ef  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800bc8f6  lea     rax, [rcx+1]
0x1800bc8fa  cmp     rax, rcx
0x1800bc8fd  mov     rcx, cs:g_hPublisher
0x1800bc904  cmovnb  r15, rax
0x1800bc908  sbb     ebx, ebx
0x1800bc90a  and     ebx, 80070216h
0x1800bc910  mov     dword ptr [rsp+0C0h+phkResult], ebx
0x1800bc914  call    fnEfsLogTrace1String1Dword
0x1800bc919  test    eax, eax
0x1800bc91b  js      loc_1800BCB87
0x1800bc921  mov     rax, r15
0x1800bc924  mov     dword ptr [rsp+0C0h+phkResult], 4D0h
0x1800bc92c  and     eax, 1
0x1800bc92f  lea     rcx, ?SaveValueName@CDplDuck@@0PAPEBGA; ushort const * near * CDplDuck::SaveValueName
0x1800bc936  mov     r9d, 28h ; '('
0x1800bc93c  lea     r8, sourceString
0x1800bc943  lea     rdx, EFS_TRACE_START_EVENT
0x1800bc94a  mov     r12, [rcx+rax*8]
0x1800bc94e  call    fnEfsLogTrace1Strings
0x1800bc953  mov     rcx, [r14+30h]; this
0x1800bc957  lea     rdx, [rbp+57h+var_50]; void **
0x1800bc95b  call    ?RevertToSelf@CDplServiceImpl@@AEAAJPEAPEAX@Z; CDplServiceImpl::RevertToSelf(void * *)
0x1800bc960  mov     rcx, cs:g_hPublisher
0x1800bc967  lea     r9, sourceString
0x1800bc96e  mov     dword ptr [rsp+0C0h+lpSecurityAttributes], 4D0h
0x1800bc976  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800bc97d  mov     [rsp+0C0h+samDesired], 28h ; '('
0x1800bc985  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800bc98c  mov     dword ptr [rsp+0C0h+phkResult], eax
0x1800bc990  mov     ebx, eax
0x1800bc992  call    fnEfsLogTrace1String1Dword
0x1800bc997  test    eax, eax
0x1800bc999  js      loc_1800BCB87
0x1800bc99f  mov     edi, 4D6h
0x1800bc9a4  lea     r8, sourceString
0x1800bc9ab  mov     r9d, 28h ; '('
0x1800bc9b1  mov     dword ptr [rsp+0C0h+phkResult], edi
0x1800bc9b5  lea     rdx, EFS_TRACE_START_EVENT
0x1800bc9bc  call    fnEfsLogTrace1Strings
0x1800bc9c1  xor     r8d, r8d; unsigned int *
0x1800bc9c4  lea     rdx, [rbp+57h+lpSubKey]; unsigned __int16 **
0x1800bc9c8  call    ?GetDuckPersistenceRoot@CDplUser@@AEAAJPEAPEAGPEAK@Z; CDplUser::GetDuckPersistenceRoot(ushort * *,ulong *)
0x1800bc9cd  mov     rcx, cs:g_hPublisher
0x1800bc9d4  lea     r9, sourceString
0x1800bc9db  mov     dword ptr [rsp+0C0h+lpSecurityAttributes], edi
0x1800bc9df  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800bc9e6  mov     [rsp+0C0h+samDesired], 28h ; '('
0x1800bc9ee  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800bc9f5  mov     dword ptr [rsp+0C0h+phkResult], eax
0x1800bc9f9  mov     ebx, eax
0x1800bc9fb  call    fnEfsLogTrace1String1Dword
0x1800bca00  mov     rdi, [rbp+57h+lpSubKey]
0x1800bca04  test    eax, eax
0x1800bca06  js      loc_1800BCB87
0x1800bca0c  lea     rax, [rbp+57h+hKey]
0x1800bca10  mov     r9d, 0F003Fh; samDesired
0x1800bca16  xor     r8d, r8d; ulOptions
0x1800bca19  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1800bca1e  mov     rdx, rdi; lpSubKey
0x1800bca21  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800bca28  call    cs:__imp_RegOpenKeyExW
0x1800bca2e  xor     ecx, ecx
0x1800bca30  test    eax, eax
0x1800bca32  jz      short loc_1800BCA5D
0x1800bca34  jg      short loc_1800BCA3A
0x1800bca36  mov     ebx, eax
0x1800bca38  jmp     short loc_1800BCA43
0x1800bca3a  movzx   ebx, ax
0x1800bca3d  or      ebx, 80070000h
0x1800bca43  mov     dword ptr [rsp+0C0h+phkResult], 4E0h
0x1800bca4b  mov     r9d, 28h ; '('
0x1800bca51  lea     rdx, EFS_TRACE_ERROR
0x1800bca58  jmp     loc_1800BCB78
0x1800bca5d  mov     rdx, [r14+68h]; lpSubKey
0x1800bca61  lea     rax, [rbp+57h+arg_18]
0x1800bca65  mov     [rsp+0C0h+lpdwDisposition], rcx; lpdwDisposition
0x1800bca6a  xor     r9d, r9d; lpClass
0x1800bca6d  mov     [rsp+0C0h+var_88], rax; phkResult
0x1800bca72  xor     r8d, r8d; Reserved
0x1800bca75  mov     [rsp+0C0h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x1800bca7a  mov     [rsp+0C0h+samDesired], 0F003Fh; samDesired
0x1800bca82  mov     dword ptr [rsp+0C0h+phkResult], ecx; dwOptions
0x1800bca86  mov     rcx, [rbp+57h+hKey]; hKey
0x1800bca8a  call    cs:__imp_RegCreateKeyExW
0x1800bca90  test    eax, eax
0x1800bca92  jz      short loc_1800BCAAD
0x1800bca94  jg      short loc_1800BCA9A
0x1800bca96  mov     ebx, eax
0x1800bca98  jmp     short loc_1800BCAA3
0x1800bca9a  movzx   ebx, ax
0x1800bca9d  or      ebx, 80070000h
0x1800bcaa3  mov     dword ptr [rsp+0C0h+phkResult], 4EFh
0x1800bcaab  jmp     short loc_1800BCA4B
0x1800bcaad  mov     eax, [rbp+57h+cbData]
0x1800bcab0  mov     r9d, 3; dwType
0x1800bcab6  mov     rdx, [rbp+57h+var_60]; lpSubKey
0x1800bcaba  mov     r8, r12; lpValueName
0x1800bcabd  mov     [rsp+0C0h+samDesired], eax; cbData
0x1800bcac1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800bcac8  mov     rax, [rbp+57h+lpData]
0x1800bcacc  mov     [rsp+0C0h+phkResult], rax; lpData
0x1800bcad1  call    cs:__imp_RegSetKeyValueW
0x1800bcad7  test    eax, eax
0x1800bcad9  jz      short loc_1800BCAF7
0x1800bcadb  jg      short loc_1800BCAE1
0x1800bcadd  mov     ebx, eax
0x1800bcadf  jmp     short loc_1800BCAEA
0x1800bcae1  movzx   ebx, ax
0x1800bcae4  or      ebx, 80070000h
0x1800bcaea  mov     dword ptr [rsp+0C0h+phkResult], 4FBh
0x1800bcaf2  jmp     loc_1800BCA4B
0x1800bcaf7  mov     rcx, [rbp+57h+hKey]; hKey
0x1800bcafb  call    cs:__imp_RegFlushKey
0x1800bcb01  test    eax, eax
0x1800bcb03  jz      short loc_1800BCB21
0x1800bcb05  jg      short loc_1800BCB0B
0x1800bcb07  mov     ebx, eax
0x1800bcb09  jmp     short loc_1800BCB14
0x1800bcb0b  movzx   ebx, ax
0x1800bcb0e  or      ebx, 80070000h
0x1800bcb14  mov     dword ptr [rsp+0C0h+phkResult], 50Ah
0x1800bcb1c  jmp     loc_1800BCA4B
0x1800bcb21  lea     r8, [rbp+57h+var_58]; unsigned __int64 *
0x1800bcb25  mov     [rsi+70h], r15
0x1800bcb29  mov     edx, 1; unsigned __int64
0x1800bcb2e  mov     dword ptr [rsi+78h], 0
0x1800bcb35  mov     rcx, r15; unsigned __int64
0x1800bcb38  call    ?ULongLongSub@@YAJ_K0PEA_K@Z; ULongLongSub(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800bcb3d  test    eax, eax
0x1800bcb3f  js      short loc_1800BCB87
0x1800bcb41  mov     rdx, [rbp+57h+var_58]
0x1800bcb45  lea     rax, ?SaveValueName@CDplDuck@@0PAPEBGA; ushort const * near * CDplDuck::SaveValueName
0x1800bcb4c  mov     rcx, [rbp+57h+arg_18]; hKey
0x1800bcb50  and     edx, 1
0x1800bcb53  mov     rdx, [rax+rdx*8]; lpValueName
0x1800bcb57  call    ?RegDeleteValueSecurely@CDplService@@SAJPEAUHKEY__@@PEBG@Z; CDplService::RegDeleteValueSecurely(HKEY__ *,ushort const *)
0x1800bcb5c  jmp     short loc_1800BCB87
0x1800bcb5e  mov     dword ptr [rsp+0C0h+phkResult], 499h
0x1800bcb66  mov     r9d, 28h ; '('
0x1800bcb6c  mov     ebx, 1
0x1800bcb71  lea     rdx, EFS_TRACE_STATUS
0x1800bcb78  mov     rcx, cs:g_hPublisher
0x1800bcb7f  mov     r8d, ebx
0x1800bcb82  call    fnEfsLogTrace1
0x1800bcb87  mov     edx, r13d; int
0x1800bcb8a  mov     rcx, r14; this
0x1800bcb8d  call    ?UserSvcUnlock@CDplUser@@AEAAHH@Z; CDplUser::UserSvcUnlock(int)
0x1800bcb92  mov     rcx, [rbp+57h+lpData]; void *
0x1800bcb96  test    rcx, rcx
0x1800bcb99  jz      short loc_1800BCBA0
0x1800bcb9b  call    ?DplibMemFree@@YAJPEAX@Z; DplibMemFree(void *)
0x1800bcba0  mov     rcx, [rbp+57h+arg_18]; hKey
0x1800bcba4  test    rcx, rcx
0x1800bcba7  jz      short loc_1800BCBB7
0x1800bcba9  call    cs:__imp_RegCloseKey
0x1800bcbaf  mov     [rbp+57h+arg_18], 0
0x1800bcbb7  mov     rcx, [rbp+57h+hKey]; hKey
0x1800bcbbb  test    rcx, rcx
0x1800bcbbe  jz      short loc_1800BCBCE
0x1800bcbc0  call    cs:__imp_RegCloseKey
0x1800bcbc6  mov     [rbp+57h+hKey], 0
0x1800bcbce  mov     rcx, [r14+30h]; this
0x1800bcbd2  lea     rdx, [rbp+57h+var_50]; void **
0x1800bcbd6  call    ?RestoreImpersonation@CDplServiceImpl@@AEAAXPEAPEAX@Z; CDplServiceImpl::RestoreImpersonation(void * *)
0x1800bcbdb  mov     rcx, [rbp+57h+var_60]; void *
0x1800bcbdf  test    rcx, rcx
0x1800bcbe2  jz      short loc_1800BCBE9
  ... truncated ...
```
