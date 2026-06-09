# DAS::DevnodeManagment::DevnodeManager::UninstallDevnodesSetupDi(ushort const *,ushort const *)

- ea: `0x18004f218`
- end: `0x18004f668`
- name: `?UninstallDevnodesSetupDi@DevnodeManager@DevnodeManagment@DAS@@AEAAJPEBG0@Z`
- size: `1104`
- prototype: `int(DAS::DevnodeManagment::DevnodeManager *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003a2b4`

## callees

- `0x180007500`
- `0x18002879c`
- `0x18003bc80`
- `0x18003c79c`
- `0x18004e8cc`
- `0x18004ec78`
- `0x18004f034`
- `0x18004f218`
- `0x18004f844`
- `0x18004fa2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f318`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f341`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f3e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f411`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f604`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f318`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f341`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f3e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f411`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f604`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004f396`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004f446`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004f396`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18004f446`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiGetDevicePropertyW` at `0x18004f30e`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiGetDevicePropertyW` at `0x18004f3de`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiGetDevicePropertyW` at `0x18004f30e`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiGetDevicePropertyW` at `0x18004f3de`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiEnumDeviceInfo` at `0x18004f2b7`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiEnumDeviceInfo` at `0x18004f5f6`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiEnumDeviceInfo` at `0x18004f2b7`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiEnumDeviceInfo` at `0x18004f5f6`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiGetClassDevsW` at `0x18004f257`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiGetClassDevsW` at `0x18004f257`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiGetDeviceInstanceIdW` at `0x18004f48e`
- `ext-ms-win-setupapi-classinstallers-l1-1-0!SetupDiGetDeviceInstanceIdW` at `0x18004f48e`

## string_xrefs

- `0x18004f4a9`: `onecore\base\devices\association\service\lib\devnodemanagement.cpp`
- `0x18004f628`: `onecore\base\devices\association\service\lib\devnodemanagement.cpp`

## pseudocode

```c
__int64 __fastcall DAS::DevnodeManagment::DevnodeManager::UninstallDevnodesSetupDi(
        DAS::DevnodeManagment::DevnodeManager *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  HDEVINFO v5; // rbx
  const char *v6; // r9
  __int64 v7; // rdx
  DWORD v8; // r14d
  DWORD LastError; // eax
  char v10; // al
  int v11; // edx
  int v12; // r8d
  int v13; // r9d
  DWORD v14; // eax
  int v15; // r8d
  DAS::DevnodeManagment::DevnodeManager *v16; // rcx
  BOOL DeviceInstanceIdW; // eax
  __int64 v18; // rcx
  const char *v19; // rax
  unsigned int v20; // eax
  int v21; // edx
  int v22; // r8d
  int v23; // r9d
  const char *v24; // rcx
  int v25; // r9d
  const char *v26; // rax
  unsigned int LastErrorMsg; // ebx
  const char *PropertyBuffer; // [rsp+20h] [rbp-E0h]
  const char *PropertyBufferSize; // [rsp+28h] [rbp-D8h]
  DEVPROPTYPE PropertyType; // [rsp+50h] [rbp-B0h] BYREF
  HDEVINFO ClassDevsW; // [rsp+58h] [rbp-A8h] BYREF
  _SP_DEVINFO_DATA DeviceInfoData; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR DeviceInstanceId[200]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR v35[768]; // [rsp+210h] [rbp+110h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+848h] [rbp+748h]

  ClassDevsW = SetupDiGetClassDevsW(0, 0, 0, 4u);
  v5 = ClassDevsW;
  if ( ClassDevsW == (HDEVINFO)-1LL )
  {
    v6 = "failed to get class devs";
    v7 = 950;
LABEL_43:
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     (void *)v7,
                     (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodemanagement.cpp",
                     v6,
                     PropertyBuffer);
    goto LABEL_44;
  }
  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  v8 = 0;
  DeviceInfoData.cbSize = 32;
  PropertyType = 0;
  memset_0(v35, 0, sizeof(v35));
  if ( SetupDiEnumDeviceInfo(ClassDevsW, 0, &DeviceInfoData) )
  {
    do
    {
      if ( a3 )
      {
        if ( !SetupDiGetDevicePropertyW(
                v5,
                &DeviceInfoData,
                &DEVPKEY_Aep_PerUserSid,
                &PropertyType,
                (PBYTE)v35,
                0x600u,
                0,
                0) )
        {
          LastError = GetLastError();
          if ( LastError == 1168
            || LastError == -536870389
            || *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          {
            goto LABEL_39;
          }
          v10 = GetLastError();
          v13 = 38;
          goto LABEL_10;
        }
        if ( PropertyType != 18 || CompareStringOrdinal(a3, -1, v35, -1, 1) != 2 )
          goto LABEL_39;
      }
      if ( !SetupDiGetDevicePropertyW(v5, &DeviceInfoData, &DEVPKEY_Aep_AepId, &PropertyType, (PBYTE)v35, 0x600u, 0, 0) )
      {
        v14 = GetLastError();
        if ( v14 == 1168 || v14 == -536870389 || *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          goto LABEL_39;
        v10 = GetLastError();
        v13 = 39;
LABEL_10:
        WPP_RECORDER_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v11,
          v12,
          v13,
          &WPP_416e81a390623384018c9851ffc16906_Traceguids,
          v10);
        goto LABEL_39;
      }
      if ( PropertyType == 18 && CompareStringOrdinal(a2, -1, v35, -1, 1) == 2 )
      {
        memset_0(DeviceInstanceId, 0, sizeof(DeviceInstanceId));
        v16 = (DAS::DevnodeManagment::DevnodeManager *)WPP_GLOBAL_Control;
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          DeviceInstanceIdW = SetupDiGetDeviceInstanceIdW(v5, &DeviceInfoData, DeviceInstanceId, 0x190u, 0);
          wil::details::in1diag3::Log_GetLastErrorIfFalseMsg(
            retaddr,
            (void *)0x401,
            (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodemanagement.cpp",
            (const char *)DeviceInstanceIdW,
            (bool)"failed to get device instance ID",
            PropertyBufferSize);
          v16 = (DAS::DevnodeManagment::DevnodeManager *)WPP_GLOBAL_Control;
        }
        if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          v18 = *((_QWORD *)v16 + 5);
          v19 = (const char *)a3;
          if ( !a3 )
            v19 = L"SYSTEM -";
          WPP_RECORDER_SF_SSS(
            v18,
            (unsigned int)L"SYSTEM -",
            v15,
            40,
            (__int64)PropertyBuffer,
            (__int64)DeviceInstanceId,
            (__int64)a2,
            (__int64)v19);
        }
        v20 = DAS::DevnodeManagment::DevnodeManager::UninstallDevnodeSetupDi(v16, v5, &DeviceInfoData);
        if ( v20 )
        {
          if ( v20 == -536870389 )
          {
            if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              v25 = 41;
LABEL_36:
              v26 = (const char *)a3;
              if ( !a3 )
                v26 = L"SYSTEM -";
              WPP_RECORDER_SF_SSS(
                *((_QWORD *)WPP_GLOBAL_Control + 5),
                v21,
                v22,
                v25,
                (__int64)PropertyBuffer,
                (__int64)DeviceInstanceId,
                (__int64)a2,
                (__int64)v26);
            }
          }
          else if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            v24 = (const char *)a3;
            if ( !a3 )
              v24 = L"SYSTEM -";
            WPP_RECORDER_SF_SSSD(
              *((_QWORD *)WPP_GLOBAL_Control + 5),
              (unsigned int)L"SYSTEM -",
              v22,
              v23,
              (_DWORD)PropertyBuffer,
              (__int64)DeviceInstanceId,
              (__int64)a2,
              (__int64)v24,
              v20);
          }
        }
        else if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          v25 = 42;
          goto LABEL_36;
        }
      }
LABEL_39:
      PropertyType = 0;
      memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
      DeviceInfoData.cbSize = 32;
      ++v8;
      memset_0(v35, 0, sizeof(v35));
    }
    while ( SetupDiEnumDeviceInfo(v5, v8, &DeviceInfoData) );
  }
  if ( GetLastError() != 259 )
  {
    v6 = "failed to enumerate device info";
    v7 = 967;
    goto LABEL_43;
  }
  LastErrorMsg = 0;
LABEL_44:
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int SetupDiDestroyDeviceInfoList(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int SetupDiDestroyDeviceInfoList(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ClassDevsW);
  return LastErrorMsg;
}

```

## disassembly

```asm
0x18004f218  mov     [rsp-8+arg_0], rbx
0x18004f21d  push    rbp
0x18004f21e  push    rsi
0x18004f21f  push    rdi
0x18004f220  push    r12
0x18004f222  push    r14
0x18004f224  lea     rbp, [rsp-720h]
0x18004f22c  sub     rsp, 820h
0x18004f233  mov     rax, cs:__security_cookie
0x18004f23a  xor     rax, rsp
0x18004f23d  mov     [rbp+740h+var_30], rax
0x18004f244  mov     rdi, r8
0x18004f247  mov     rsi, rdx
0x18004f24a  xor     r8d, r8d; hwndParent
0x18004f24d  xor     edx, edx; Enumerator
0x18004f24f  mov     r9d, 4; Flags
0x18004f255  xor     ecx, ecx; ClassGuid
0x18004f257  call    cs:__imp_SetupDiGetClassDevsW
0x18004f25d  mov     [rsp+840h+var_7E8], rax
0x18004f262  mov     rbx, rax
0x18004f265  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004f269  jnz     short loc_18004F27C
0x18004f26b  lea     r9, aFailedToGetCla; "failed to get class devs"
0x18004f272  mov     edx, 3B6h
0x18004f277  jmp     loc_18004F621
0x18004f27c  xorps   xmm0, xmm0
0x18004f27f  lea     rcx, [rbp+740h+var_630]; void *
0x18004f286  movups  xmmword ptr [rsp+840h+DeviceInfoData.cbSize], xmm0
0x18004f28b  xor     r14d, r14d
0x18004f28e  mov     [rsp+840h+DeviceInfoData.cbSize], 20h ; ' '
0x18004f296  xor     edx, edx; Val
0x18004f298  mov     [rsp+840h+PropertyType], r14d
0x18004f29d  mov     r8d, 600h; Size
0x18004f2a3  movups  xmmword ptr [rsp+840h+DeviceInfoData.ClassGuid.Data4+4], xmm0
0x18004f2a8  call    memset_0
0x18004f2ad  lea     r8, [rsp+840h+DeviceInfoData]; DeviceInfoData
0x18004f2b2  xor     edx, edx; MemberIndex
0x18004f2b4  mov     rcx, rbx; DeviceInfoSet
0x18004f2b7  call    cs:__imp_SetupDiEnumDeviceInfo
0x18004f2bd  test    eax, eax
0x18004f2bf  jz      loc_18004F604
0x18004f2c5  lea     r12, WPP_RECORDER_INITIALIZED
0x18004f2cc  test    rdi, rdi
0x18004f2cf  jz      loc_18004F3A5
0x18004f2d5  mov     [rsp+840h+Flags], 0; Flags
0x18004f2dd  lea     rax, [rbp+740h+var_630]
0x18004f2e4  mov     [rsp+840h+RequiredSize], 0; RequiredSize
0x18004f2ed  lea     r9, [rsp+840h+PropertyType]; PropertyType
0x18004f2f2  mov     [rsp+840h+PropertyBufferSize], 600h; PropertyBufferSize
0x18004f2fa  lea     r8, DEVPKEY_Aep_PerUserSid; PropertyKey
0x18004f301  lea     rdx, [rsp+840h+DeviceInfoData]; DeviceInfoData
0x18004f306  mov     [rsp+840h+PropertyBuffer], rax; PropertyBuffer
0x18004f30b  mov     rcx, rbx; DeviceInfoSet
0x18004f30e  call    cs:__imp_SetupDiGetDevicePropertyW
0x18004f314  test    eax, eax
0x18004f316  jnz     short loc_18004F372
0x18004f318  call    cs:__imp_GetLastError
0x18004f31e  cmp     eax, 490h
0x18004f323  jz      loc_18004F5B7
0x18004f329  cmp     eax, 0E000020Bh
0x18004f32e  jz      loc_18004F5B7
0x18004f334  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18004f33b  jz      loc_18004F5B7
0x18004f341  call    cs:__imp_GetLastError
0x18004f347  mov     r9d, 26h ; '&'; int
0x18004f34d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f354  mov     [rsp+840h+PropertyBufferSize], eax; char
0x18004f358  lea     rax, WPP_416e81a390623384018c9851ffc16906_Traceguids
0x18004f35f  mov     [rsp+840h+PropertyBuffer], rax; MessageGuid
0x18004f364  mov     rcx, [rcx+28h]; int
0x18004f368  call    WPP_RECORDER_SF_D
0x18004f36d  jmp     loc_18004F5B7
0x18004f372  cmp     [rsp+840h+PropertyType], 12h
0x18004f377  jnz     loc_18004F5B7
0x18004f37d  or      r9d, 0FFFFFFFFh; cchCount2
0x18004f381  mov     dword ptr [rsp+840h+PropertyBuffer], 1; bIgnoreCase
0x18004f389  or      edx, r9d; cchCount1
0x18004f38c  lea     r8, [rbp+740h+var_630]; lpString2
0x18004f393  mov     rcx, rdi; lpString1
0x18004f396  call    cs:__imp_CompareStringOrdinal
0x18004f39c  cmp     eax, 2
0x18004f39f  jnz     loc_18004F5B7
0x18004f3a5  mov     [rsp+840h+Flags], 0; Flags
0x18004f3ad  lea     rax, [rbp+740h+var_630]
0x18004f3b4  mov     [rsp+840h+RequiredSize], 0; RequiredSize
0x18004f3bd  lea     r9, [rsp+840h+PropertyType]; PropertyType
0x18004f3c2  mov     [rsp+840h+PropertyBufferSize], 600h; char *
0x18004f3ca  lea     r8, DEVPKEY_Aep_AepId; PropertyKey
0x18004f3d1  lea     rdx, [rsp+840h+DeviceInfoData]; DeviceInfoData
0x18004f3d6  mov     [rsp+840h+PropertyBuffer], rax; PropertyBuffer
0x18004f3db  mov     rcx, rbx; DeviceInfoSet
0x18004f3de  call    cs:__imp_SetupDiGetDevicePropertyW
0x18004f3e4  test    eax, eax
0x18004f3e6  jnz     short loc_18004F422
0x18004f3e8  call    cs:__imp_GetLastError
0x18004f3ee  cmp     eax, 490h
0x18004f3f3  jz      loc_18004F5B7
0x18004f3f9  cmp     eax, 0E000020Bh
0x18004f3fe  jz      loc_18004F5B7
0x18004f404  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18004f40b  jz      loc_18004F5B7
0x18004f411  call    cs:__imp_GetLastError
0x18004f417  mov     r9d, 27h ; '''
0x18004f41d  jmp     loc_18004F34D
0x18004f422  cmp     [rsp+840h+PropertyType], 12h
0x18004f427  jnz     loc_18004F5B7
0x18004f42d  or      r9d, 0FFFFFFFFh; cchCount2
0x18004f431  mov     dword ptr [rsp+840h+PropertyBuffer], 1; bIgnoreCase
0x18004f439  or      edx, r9d; cchCount1
0x18004f43c  lea     r8, [rbp+740h+var_630]; lpString2
0x18004f443  mov     rcx, rsi; lpString1
0x18004f446  call    cs:__imp_CompareStringOrdinal
0x18004f44c  cmp     eax, 2
0x18004f44f  jnz     loc_18004F5B7
0x18004f455  xor     edx, edx; Val
0x18004f457  lea     rcx, [rbp+740h+DeviceInstanceId]; void *
0x18004f45b  mov     r8d, 190h; Size
0x18004f461  call    memset_0
0x18004f466  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f46d  cmp     byte ptr [rcx+19h], 2
0x18004f471  jb      short loc_18004F4C8
0x18004f473  mov     r9d, 190h; DeviceInstanceIdSize
0x18004f479  mov     [rsp+840h+PropertyBuffer], 0; RequiredSize
0x18004f482  lea     r8, [rbp+740h+DeviceInstanceId]; DeviceInstanceId
0x18004f486  mov     rcx, rbx; DeviceInfoSet
0x18004f489  lea     rdx, [rsp+840h+DeviceInfoData]; DeviceInfoData
0x18004f48e  call    cs:__imp_SetupDiGetDeviceInstanceIdW
0x18004f494  mov     rcx, [rbp+748h]; this
0x18004f49b  lea     rdx, aFailedToGetDev; "failed to get device instance ID"
0x18004f4a2  test    eax, eax
0x18004f4a4  mov     [rsp+840h+PropertyBuffer], rdx; char *
0x18004f4a9  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\association\\se"...
0x18004f4b0  mov     edx, 401h; void *
0x18004f4b5  setnz   al
0x18004f4b8  movzx   r9d, al; char *
0x18004f4bc  call    ?Log_GetLastErrorIfFalseMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Log_GetLastErrorIfFalseMsg(void *,uint,char const *,bool,char const *,...)
0x18004f4c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f4c8  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18004f4cf  jz      short loc_18004F504
0x18004f4d1  mov     rcx, [rcx+28h]
0x18004f4d5  lea     rdx, aSystem_1; "SYSTEM -"
0x18004f4dc  test    rdi, rdi
0x18004f4df  mov     rax, rdi
0x18004f4e2  mov     r9d, 28h ; '('
0x18004f4e8  cmovz   rax, rdx
0x18004f4ec  mov     qword ptr [rsp+840h+Flags], rax
0x18004f4f1  lea     rax, [rbp+740h+DeviceInstanceId]
0x18004f4f5  mov     [rsp+840h+RequiredSize], rsi
0x18004f4fa  mov     qword ptr [rsp+840h+PropertyBufferSize], rax
0x18004f4ff  call    WPP_RECORDER_SF_SSS
0x18004f504  lea     r8, [rsp+840h+DeviceInfoData]; struct _SP_DEVINFO_DATA *
0x18004f509  mov     rdx, rbx; void *
0x18004f50c  call    ?UninstallDevnodeSetupDi@DevnodeManager@DevnodeManagment@DAS@@AEAAKPEAXPEAU_SP_DEVINFO_DATA@@@Z; DAS::DevnodeManagment::DevnodeManager::UninstallDevnodeSetupDi(void *,_SP_DEVINFO_DATA *)
0x18004f511  test    eax, eax
0x18004f513  jz      short loc_18004F574
0x18004f515  cmp     eax, 0E000020Bh
0x18004f51a  jz      short loc_18004F563
0x18004f51c  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18004f523  jz      loc_18004F5B7
0x18004f529  mov     [rsp+840h+var_800], eax
0x18004f52d  lea     rdx, aSystem_1; "SYSTEM -"
0x18004f534  test    rdi, rdi
0x18004f537  lea     rax, [rbp+740h+DeviceInstanceId]
0x18004f53b  mov     rcx, rdi
0x18004f53e  cmovz   rcx, rdx
0x18004f542  mov     qword ptr [rsp+840h+Flags], rcx
0x18004f547  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f54e  mov     [rsp+840h+RequiredSize], rsi
0x18004f553  mov     qword ptr [rsp+840h+PropertyBufferSize], rax
0x18004f558  mov     rcx, [rcx+28h]
0x18004f55c  call    WPP_RECORDER_SF_SSSD
0x18004f561  jmp     short loc_18004F5B7
0x18004f563  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18004f56a  jz      short loc_18004F5B7
0x18004f56c  mov     r9d, 29h ; ')'
0x18004f572  jmp     short loc_18004F583
0x18004f574  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18004f57b  jz      short loc_18004F5B7
0x18004f57d  mov     r9d, 2Ah ; '*'
0x18004f583  test    rdi, rdi
0x18004f586  lea     rcx, aSystem_1; "SYSTEM -"
0x18004f58d  mov     rax, rdi
0x18004f590  cmovz   rax, rcx
0x18004f594  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f59b  mov     qword ptr [rsp+840h+Flags], rax
0x18004f5a0  lea     rax, [rbp+740h+DeviceInstanceId]
0x18004f5a4  mov     [rsp+840h+RequiredSize], rsi
0x18004f5a9  mov     qword ptr [rsp+840h+PropertyBufferSize], rax
0x18004f5ae  mov     rcx, [rcx+28h]
0x18004f5b2  call    WPP_RECORDER_SF_SSS
0x18004f5b7  xorps   xmm0, xmm0
0x18004f5ba  mov     [rsp+840h+PropertyType], 0
0x18004f5c2  movups  xmmword ptr [rsp+840h+DeviceInfoData.cbSize], xmm0
0x18004f5c7  xor     edx, edx; Val
0x18004f5c9  mov     [rsp+840h+DeviceInfoData.cbSize], 20h ; ' '
0x18004f5d1  mov     r8d, 600h; Size
0x18004f5d7  lea     rcx, [rbp+740h+var_630]; void *
0x18004f5de  inc     r14d
0x18004f5e1  movups  xmmword ptr [rsp+840h+DeviceInfoData.ClassGuid.Data4+4], xmm0
0x18004f5e6  call    memset_0
0x18004f5eb  lea     r8, [rsp+840h+DeviceInfoData]; DeviceInfoData
0x18004f5f0  mov     edx, r14d; MemberIndex
0x18004f5f3  mov     rcx, rbx; DeviceInfoSet
0x18004f5f6  call    cs:__imp_SetupDiEnumDeviceInfo
0x18004f5fc  test    eax, eax
0x18004f5fe  jnz     loc_18004F2CC
0x18004f604  call    cs:__imp_GetLastError
0x18004f60a  cmp     eax, 103h
0x18004f60f  jnz     short loc_18004F615
0x18004f611  xor     ebx, ebx
0x18004f613  jmp     short loc_18004F636
0x18004f615  lea     r9, aFailedToEnumer_0; "failed to enumerate device info"
0x18004f61c  mov     edx, 3C7h; void *
0x18004f621  mov     rcx, [rbp+748h]; this
0x18004f628  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\association\\se"...
0x18004f62f  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18004f634  mov     ebx, eax
0x18004f636  lea     rcx, [rsp+840h+var_7E8]
0x18004f63b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?SetupDiDestroyDeviceInfoList@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&SetupDiDestroyDeviceInfoList(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&SetupDiDestroyDeviceInfoList(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004f640  mov     eax, ebx
0x18004f642  mov     rcx, [rbp+740h+var_30]
0x18004f649  xor     rcx, rsp; StackCookie
0x18004f64c  call    __security_check_cookie
0x18004f651  mov     rbx, [rsp+840h+arg_0]
0x18004f659  add     rsp, 820h
0x18004f660  pop     r14
0x18004f662  pop     r12
0x18004f664  pop     rdi
0x18004f665  pop     rsi
0x18004f666  pop     rbp
0x18004f667  retn
```
