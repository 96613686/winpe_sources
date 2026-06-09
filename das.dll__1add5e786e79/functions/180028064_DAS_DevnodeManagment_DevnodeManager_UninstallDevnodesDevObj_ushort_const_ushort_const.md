# DAS::DevnodeManagment::DevnodeManager::UninstallDevnodesDevObj(ushort const *,ushort const *)

- ea: `0x180028064`
- end: `0x180028487`
- name: `?UninstallDevnodesDevObj@DevnodeManager@DevnodeManagment@DAS@@AEAAJPEBG0@Z`
- size: `1059`
- prototype: `int(DAS::DevnodeManagment::DevnodeManager *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003a2b4`

## callees

- `0x180007500`
- `0x1800186ac`
- `0x180028064`
- `0x180028490`
- `0x18002879c`
- `0x18003b258`
- `0x18003bc80`
- `0x18003c79c`
- `0x18004ee6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800281a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800281cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028267`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028290`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028410`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800281a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800281cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028267`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028290`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028410`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180028218`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800282c2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180028218`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800282c2`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18002819a`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18002825d`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18002819a`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x18002825d`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800280af`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800280af`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800280f4`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800280f4`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x18002813f`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x180028402`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x18002813f`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x180028402`

## string_xrefs

- `0x180028442`: `onecore\base\devices\association\service\lib\devnodemanagement.cpp`

## pseudocode

```c
__int64 __fastcall DAS::DevnodeManagment::DevnodeManager::UninstallDevnodesDevObj(
        DAS::DevnodeManagment::DevnodeManager *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 DeviceInfoList; // rax
  void *v6; // rbx
  const char *v7; // r9
  __int64 v8; // rdx
  unsigned int v9; // r14d
  DWORD LastError; // eax
  char v11; // al
  int v12; // edx
  int v13; // r8d
  int v14; // r9d
  DWORD v15; // eax
  int v16; // edx
  DAS::DevnodeManagment::DevnodeManager *v17; // rcx
  int v18; // r8d
  const char *v19; // rax
  unsigned int v20; // eax
  int v21; // edx
  int v22; // r8d
  const char *v23; // rcx
  int v24; // r9d
  const char *v25; // rax
  unsigned int LastErrorMsg; // ebx
  const char *bIgnoreCase; // [rsp+20h] [rbp-E0h]
  int v29; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v30; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v31; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v32; // [rsp+60h] [rbp-A0h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  WCHAR String2[768]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6B8h] [rbp+5B8h]

  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v30 = DeviceInfoList;
  v6 = (void *)DeviceInfoList;
  if ( DeviceInfoList == -1 )
  {
    v7 = "failed to get device info list";
    v8 = 793;
LABEL_43:
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     (void *)v8,
                     (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\devnodemanagement.cpp",
                     v7,
                     bIgnoreCase);
    goto LABEL_44;
  }
  if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, 0, 0, 4, 0, 0) )
  {
    v7 = "failed to get class devs";
    v8 = 794;
    goto LABEL_43;
  }
  v31 = 0;
  v9 = 0;
  LODWORD(v31) = 48;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  memset_0(String2, 0, sizeof(String2));
  if ( (unsigned int)DevObjEnumDeviceInfo(v6, 0, &v31) )
  {
    do
    {
      if ( a3 )
      {
        if ( !(unsigned int)DevObjGetDeviceProperty(v6, &v31, &DEVPKEY_Aep_PerUserSid, &v29, String2, 1536, 0, 0) )
        {
          LastError = GetLastError();
          if ( LastError == 1168
            || LastError == -536870389
            || *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          {
            goto LABEL_38;
          }
          v11 = GetLastError();
          v14 = 27;
          goto LABEL_11;
        }
        if ( v29 != 18 || CompareStringOrdinal(a3, -1, String2, -1, 1) != 2 )
          goto LABEL_38;
      }
      if ( !(unsigned int)DevObjGetDeviceProperty(v6, &v31, &DEVPKEY_Aep_AepId, &v29, String2, 1536, 0, 0) )
      {
        v15 = GetLastError();
        if ( v15 == 1168 || v15 == -536870389 || *(int **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
          goto LABEL_38;
        v11 = GetLastError();
        v14 = 28;
LABEL_11:
        WPP_RECORDER_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v12,
          v13,
          v14,
          &WPP_416e81a390623384018c9851ffc16906_Traceguids,
          v11);
        goto LABEL_38;
      }
      if ( v29 == 18 && CompareStringOrdinal(a2, -1, String2, -1, 1) == 2 )
      {
        if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          v19 = (const char *)a3;
          if ( !a3 )
            v19 = L"SYSTEM -";
          WPP_RECORDER_SF_SS(
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            v16,
            v18,
            29,
            &WPP_416e81a390623384018c9851ffc16906_Traceguids,
            (__int64)a2,
            (__int64)v19);
        }
        v20 = DAS::DevnodeManagment::DevnodeManager::UninstallDevnodeDevObj(v17, v6, (struct _DO_DEVINFO_DATA *)&v31);
        if ( v20 )
        {
          if ( v20 == -536870389 )
          {
            if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              v24 = 30;
LABEL_35:
              v25 = (const char *)a3;
              if ( !a3 )
                v25 = L"SYSTEM -";
              WPP_RECORDER_SF_SS(
                *((_QWORD *)WPP_GLOBAL_Control + 5),
                v21,
                v22,
                v24,
                &WPP_416e81a390623384018c9851ffc16906_Traceguids,
                (__int64)a2,
                (__int64)v25);
            }
          }
          else if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            v23 = (const char *)a3;
            if ( !a3 )
              v23 = L"SYSTEM -";
            WPP_RECORDER_SF_SSD(
              *((_QWORD *)WPP_GLOBAL_Control + 5),
              (int)L"SYSTEM -",
              v22,
              32,
              &WPP_416e81a390623384018c9851ffc16906_Traceguids,
              (__int64)a2,
              (__int64)v23,
              v20);
          }
        }
        else if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          v24 = 31;
          goto LABEL_35;
        }
      }
LABEL_38:
      v29 = 0;
      v31 = 0;
      LODWORD(v31) = 48;
      ++v9;
      v32 = 0;
      v33 = 0;
      memset_0(String2, 0, sizeof(String2));
    }
    while ( (unsigned int)DevObjEnumDeviceInfo(v6, v9, &v31) );
  }
  if ( GetLastError() != 259 )
  {
    v7 = "failed to enumerate device info";
    v8 = 811;
    goto LABEL_43;
  }
  LastErrorMsg = 0;
LABEL_44:
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int DevObjDestroyDeviceInfoList(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int DevObjDestroyDeviceInfoList(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v30);
  return LastErrorMsg;
}

```

## disassembly

```asm
0x180028064  mov     [rsp-8+arg_0], rbx
0x180028069  mov     [rsp-8+arg_18], rsi
0x18002806e  push    rbp
0x18002806f  push    rdi
0x180028070  push    r12
0x180028072  push    r13
0x180028074  push    r14
0x180028076  lea     rbp, [rsp-590h]
0x18002807e  sub     rsp, 690h
0x180028085  mov     rax, cs:__security_cookie
0x18002808c  xor     rax, rsp
0x18002808f  mov     [rbp+5B0h+var_30], rax
0x180028096  mov     rdi, r8
0x180028099  mov     qword ptr [rsp+6B0h+bIgnoreCase], 0
0x1800280a2  mov     rsi, rdx
0x1800280a5  xor     r8d, r8d
0x1800280a8  xor     edx, edx
0x1800280aa  xor     r9d, r9d
0x1800280ad  xor     ecx, ecx
0x1800280af  call    cs:__imp_DevObjCreateDeviceInfoList
0x1800280b5  mov     [rsp+6B0h+var_668], rax
0x1800280ba  mov     rbx, rax
0x1800280bd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800280c1  jnz     short loc_1800280D4
0x1800280c3  lea     r9, aFailedToGetDev_0; "failed to get device info list"
0x1800280ca  mov     edx, 319h
0x1800280cf  jmp     loc_18002843B
0x1800280d4  mov     qword ptr [rsp+6B0h+var_688], 0
0x1800280dd  mov     r9d, 4
0x1800280e3  xor     r8d, r8d
0x1800280e6  mov     qword ptr [rsp+6B0h+bIgnoreCase], 0; char *
0x1800280ef  xor     edx, edx
0x1800280f1  mov     rcx, rbx
0x1800280f4  call    cs:__imp_DevObjGetClassDevs
0x1800280fa  test    eax, eax
0x1800280fc  jz      loc_18002842F
0x180028102  xorps   xmm0, xmm0
0x180028105  lea     rcx, [rbp+5B0h+String2]; void *
0x180028109  movups  [rsp+6B0h+var_660], xmm0
0x18002810e  xor     r14d, r14d
0x180028111  mov     dword ptr [rsp+6B0h+var_660], 30h ; '0'
0x180028119  xor     edx, edx; Val
0x18002811b  mov     [rsp+6B0h+var_670], r14d
0x180028120  mov     r8d, 600h; Size
0x180028126  movups  [rsp+6B0h+var_650], xmm0
0x18002812b  movups  [rsp+6B0h+var_640], xmm0
0x180028130  call    memset_0
0x180028135  lea     r8, [rsp+6B0h+var_660]
0x18002813a  xor     edx, edx
0x18002813c  mov     rcx, rbx
0x18002813f  call    cs:__imp_DevObjEnumDeviceInfo
0x180028145  test    eax, eax
0x180028147  jz      loc_180028410
0x18002814d  lea     r12, WPP_RECORDER_INITIALIZED
0x180028154  lea     r13, WPP_416e81a390623384018c9851ffc16906_Traceguids
0x18002815b  test    rdi, rdi
0x18002815e  jz      loc_180028227
0x180028164  mov     dword ptr [rsp+6B0h+var_678], 0
0x18002816c  lea     rax, [rbp+5B0h+String2]
0x180028170  mov     [rsp+6B0h+var_680], 0
0x180028179  lea     r9, [rsp+6B0h+var_670]
0x18002817e  mov     dword ptr [rsp+6B0h+var_688], 600h
0x180028186  lea     r8, DEVPKEY_Aep_PerUserSid
0x18002818d  lea     rdx, [rsp+6B0h+var_660]
0x180028192  mov     qword ptr [rsp+6B0h+bIgnoreCase], rax
0x180028197  mov     rcx, rbx
0x18002819a  call    cs:__imp_DevObjGetDeviceProperty
0x1800281a0  test    eax, eax
0x1800281a2  jnz     short loc_1800281F7
0x1800281a4  call    cs:__imp_GetLastError
0x1800281aa  cmp     eax, 490h
0x1800281af  jz      loc_1800283C1
0x1800281b5  cmp     eax, 0E000020Bh
0x1800281ba  jz      loc_1800283C1
0x1800281c0  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1800281c7  jz      loc_1800283C1
0x1800281cd  call    cs:__imp_GetLastError
0x1800281d3  mov     r9d, 1Bh; int
0x1800281d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800281e0  mov     dword ptr [rsp+6B0h+var_688], eax; char
0x1800281e4  mov     qword ptr [rsp+6B0h+bIgnoreCase], r13; MessageGuid
0x1800281e9  mov     rcx, [rcx+28h]; int
0x1800281ed  call    WPP_RECORDER_SF_D
0x1800281f2  jmp     loc_1800283C1
0x1800281f7  cmp     [rsp+6B0h+var_670], 12h
0x1800281fc  jnz     loc_1800283C1
0x180028202  or      r9d, 0FFFFFFFFh; cchCount2
0x180028206  mov     [rsp+6B0h+bIgnoreCase], 1; bIgnoreCase
0x18002820e  or      edx, r9d; cchCount1
0x180028211  lea     r8, [rbp+5B0h+String2]; lpString2
0x180028215  mov     rcx, rdi; lpString1
0x180028218  call    cs:__imp_CompareStringOrdinal
0x18002821e  cmp     eax, 2
0x180028221  jnz     loc_1800283C1
0x180028227  mov     dword ptr [rsp+6B0h+var_678], 0
0x18002822f  lea     rax, [rbp+5B0h+String2]
0x180028233  mov     [rsp+6B0h+var_680], 0
0x18002823c  lea     r9, [rsp+6B0h+var_670]
0x180028241  mov     dword ptr [rsp+6B0h+var_688], 600h
0x180028249  lea     r8, DEVPKEY_Aep_AepId
0x180028250  lea     rdx, [rsp+6B0h+var_660]
0x180028255  mov     qword ptr [rsp+6B0h+bIgnoreCase], rax
0x18002825a  mov     rcx, rbx
0x18002825d  call    cs:__imp_DevObjGetDeviceProperty
0x180028263  test    eax, eax
0x180028265  jnz     short loc_1800282A1
0x180028267  call    cs:__imp_GetLastError
0x18002826d  cmp     eax, 490h
0x180028272  jz      loc_1800283C1
0x180028278  cmp     eax, 0E000020Bh
0x18002827d  jz      loc_1800283C1
0x180028283  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18002828a  jz      loc_1800283C1
0x180028290  call    cs:__imp_GetLastError
0x180028296  mov     r9d, 1Ch
0x18002829c  jmp     loc_1800281D9
0x1800282a1  cmp     [rsp+6B0h+var_670], 12h
0x1800282a6  jnz     loc_1800283C1
0x1800282ac  or      r9d, 0FFFFFFFFh; cchCount2
0x1800282b0  mov     [rsp+6B0h+bIgnoreCase], 1; bIgnoreCase
0x1800282b8  or      edx, r9d; cchCount1
0x1800282bb  lea     r8, [rbp+5B0h+String2]; lpString2
0x1800282bf  mov     rcx, rsi; lpString1
0x1800282c2  call    cs:__imp_CompareStringOrdinal
0x1800282c8  cmp     eax, 2
0x1800282cb  jnz     loc_1800283C1
0x1800282d1  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1800282d8  jz      short loc_180028310
0x1800282da  test    rdi, rdi
0x1800282dd  lea     rcx, aSystem_1; "SYSTEM -"
0x1800282e4  mov     rax, rdi
0x1800282e7  mov     r9d, 1Dh; int
0x1800282ed  cmovz   rax, rcx
0x1800282f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800282f8  mov     [rsp+6B0h+var_680], rax; __int64
0x1800282fd  mov     qword ptr [rsp+6B0h+var_688], rsi; __int64
0x180028302  mov     qword ptr [rsp+6B0h+bIgnoreCase], r13; MessageGuid
0x180028307  mov     rcx, [rcx+28h]; int
0x18002830b  call    WPP_RECORDER_SF_SS
0x180028310  lea     r8, [rsp+6B0h+var_660]; struct _DO_DEVINFO_DATA *
0x180028315  mov     rdx, rbx; void *
0x180028318  call    ?UninstallDevnodeDevObj@DevnodeManager@DevnodeManagment@DAS@@AEAAKPEAXPEAU_DO_DEVINFO_DATA@@@Z; DAS::DevnodeManagment::DevnodeManager::UninstallDevnodeDevObj(void *,_DO_DEVINFO_DATA *)
0x18002831d  test    eax, eax
0x18002831f  jz      short loc_180028382
0x180028321  cmp     eax, 0E000020Bh
0x180028326  jz      short loc_180028371
0x180028328  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18002832f  jz      loc_1800283C1
0x180028335  mov     dword ptr [rsp+6B0h+var_678], eax; char
0x180028339  lea     rdx, aSystem_1; "SYSTEM -"
0x180028340  test    rdi, rdi
0x180028343  mov     rcx, rdi
0x180028346  mov     r9d, 20h ; ' '; int
0x18002834c  cmovz   rcx, rdx
0x180028350  mov     [rsp+6B0h+var_680], rcx; __int64
0x180028355  mov     rcx, cs:WPP_GLOBAL_Control
0x18002835c  mov     qword ptr [rsp+6B0h+var_688], rsi; __int64
0x180028361  mov     qword ptr [rsp+6B0h+bIgnoreCase], r13; MessageGuid
0x180028366  mov     rcx, [rcx+28h]; int
0x18002836a  call    WPP_RECORDER_SF_SSD
0x18002836f  jmp     short loc_1800283C1
0x180028371  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180028378  jz      short loc_1800283C1
0x18002837a  mov     r9d, 1Eh
0x180028380  jmp     short loc_180028391
0x180028382  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180028389  jz      short loc_1800283C1
0x18002838b  mov     r9d, 1Fh; int
0x180028391  test    rdi, rdi
0x180028394  lea     rcx, aSystem_1; "SYSTEM -"
0x18002839b  mov     rax, rdi
0x18002839e  cmovz   rax, rcx
0x1800283a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800283a9  mov     [rsp+6B0h+var_680], rax; __int64
0x1800283ae  mov     qword ptr [rsp+6B0h+var_688], rsi; __int64
0x1800283b3  mov     qword ptr [rsp+6B0h+bIgnoreCase], r13; MessageGuid
0x1800283b8  mov     rcx, [rcx+28h]; int
0x1800283bc  call    WPP_RECORDER_SF_SS
0x1800283c1  xorps   xmm0, xmm0
0x1800283c4  mov     [rsp+6B0h+var_670], 0
0x1800283cc  movups  [rsp+6B0h+var_660], xmm0
0x1800283d1  xor     edx, edx; Val
0x1800283d3  mov     dword ptr [rsp+6B0h+var_660], 30h ; '0'
0x1800283db  mov     r8d, 600h; Size
0x1800283e1  lea     rcx, [rbp+5B0h+String2]; void *
0x1800283e5  inc     r14d
0x1800283e8  movups  [rsp+6B0h+var_650], xmm0
0x1800283ed  movups  [rsp+6B0h+var_640], xmm0
0x1800283f2  call    memset_0
0x1800283f7  lea     r8, [rsp+6B0h+var_660]
0x1800283fc  mov     edx, r14d
0x1800283ff  mov     rcx, rbx
0x180028402  call    cs:__imp_DevObjEnumDeviceInfo
0x180028408  test    eax, eax
0x18002840a  jnz     loc_18002815B
0x180028410  call    cs:__imp_GetLastError
0x180028416  cmp     eax, 103h
0x18002841b  jnz     short loc_180028421
0x18002841d  xor     ebx, ebx
0x18002841f  jmp     short loc_180028450
0x180028421  lea     r9, aFailedToEnumer_0; "failed to enumerate device info"
0x180028428  mov     edx, 32Bh
0x18002842d  jmp     short loc_18002843B
0x18002842f  lea     r9, aFailedToGetCla; "failed to get class devs"
0x180028436  mov     edx, 31Ah; void *
0x18002843b  mov     rcx, [rbp+5B8h]; this
0x180028442  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\association\\se"...
0x180028449  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18002844e  mov     ebx, eax
0x180028450  lea     rcx, [rsp+6B0h+var_668]
0x180028455  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?DevObjDestroyDeviceInfoList@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&DevObjDestroyDeviceInfoList(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&DevObjDestroyDeviceInfoList(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18002845a  mov     eax, ebx
0x18002845c  mov     rcx, [rbp+5B0h+var_30]
0x180028463  xor     rcx, rsp; StackCookie
0x180028466  call    __security_check_cookie
0x18002846b  lea     r11, [rsp+6B0h+var_20]
0x180028473  mov     rbx, [r11+30h]
0x180028477  mov     rsi, [r11+48h]
0x18002847b  mov     rsp, r11
0x18002847e  pop     r14
0x180028480  pop     r13
0x180028482  pop     r12
0x180028484  pop     rdi
0x180028485  pop     rbp
0x180028486  retn
```
