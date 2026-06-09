# NetworkCompliance::VerifyCaller(void)

- ea: `0x1800c6380`
- end: `0x1800c6570`
- name: `?VerifyCaller@NetworkCompliance@@YAJXZ`
- size: `496`
- prototype: `__int64 __fastcall(NetworkCompliance *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18009672c`

## callees

- `0x18000933c`
- `0x1800095a0`
- `0x18000cea4`
- `0x18007ca54`
- `0x1800a1ea4`
- `0x1800ac4ac`
- `0x1800c5d38`
- `0x1800c5fd8`
- `0x1800c6380`
- `0x1800dd968`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800c63b2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800c63b2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800c63bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800c63bf`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800c640b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800c64a0`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800c64e4`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800c64f9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800c652d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800c640b`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800c64a0`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800c64e4`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800c64f9`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800c652d`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800c63d5`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800c63d5`

## string_xrefs

- `0x1800c655d`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x1800c6483`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\NetworkCompliance.cpp`
- `0x1800c64c7`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\NetworkCompliance.cpp`
- `0x1800c6510`: `C:\__w\1\s\src\DeliveryOptimization\Util\win10\NetworkCompliance.cpp`
- `0x1800c643e`: `NetworkCompliance::VerifyCaller`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall NetworkCompliance::VerifyCaller(NetworkCompliance *this)
{
  struct CGlobalObjects *v1; // rbx
  RTL_SRWLOCK *v2; // rdi
  const char *v3; // r9
  __int64 result; // rax
  HRESULT v5; // eax
  int *v6; // rax
  int WinHttpPreferredConnection; // eax
  int v8; // eax
  int v9; // eax
  unsigned int v10; // ebx
  int v11; // eax
  unsigned int v12; // ebx
  int v13; // [rsp+20h] [rbp-48h]
  int v14; // [rsp+20h] [rbp-48h]
  int v15[2]; // [rsp+38h] [rbp-30h] BYREF
  __int64 v16; // [rsp+48h] [rbp-20h]
  unsigned __int64 v17; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  try
  {
    v1 = CGlobalObjects::Instance();
    CDeviceProfile::UpdateDeviceOptions(v1, 0);
    v2 = (RTL_SRWLOCK *)((char *)v1 + 8);
    AcquireSRWLockShared((PSRWLOCK)v1 + 1);
    LOWORD(v1) = *((_WORD *)v1 + 1);
    ReleaseSRWLockShared(v2);
    if ( ((unsigned __int16)v1 & 0x200) == 0 )
      return 1;
    v5 = CoImpersonateClient();
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1262,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        (const char *)(unsigned int)v5,
        v13);
    GetAppIdFromToken(v15);
    if ( !v16 )
    {
      std::string::~string(v15);
      CoRevertToSelf();
      return 1;
    }
    v6 = v15;
    if ( v17 > 0xF )
      v6 = *(int **)v15;
    LogMessage(4u, "NetworkCompliance::VerifyCaller", 0x6Fu, "Caller AppId: %s", (const char *)v6);
    WinHttpPreferredConnection = NetworkCompliance::_GetWinHttpPreferredConnection();
    if ( WinHttpPreferredConnection )
    {
      v8 = WinHttpPreferredConnection - 2;
      if ( v8 )
      {
        if ( v8 == 1 )
        {
          v9 = NetworkCompliance::_VerifyAppCapability((__int64)L"cellularData");
          v10 = v9;
          if ( v9 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x7F,
              (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\NetworkCompliance.cpp",
              (const char *)(unsigned int)v9,
              v14);
            std::string::~string(v15);
            CoRevertToSelf();
            return v10;
          }
        }
      }
      else
      {
        v11 = NetworkCompliance::_VerifyAppCapability((__int64)L"wifiData");
        v12 = v11;
        if ( v11 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x7B,
            (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\NetworkCompliance.cpp",
            (const char *)(unsigned int)v11,
            v14);
          std::string::~string(v15);
          CoRevertToSelf();
          return v12;
        }
      }
      std::string::~string(v15);
      CoRevertToSelf();
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x74,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\NetworkCompliance.cpp",
        (const char *)0x80D03805LL,
        v14);
      std::string::~string(v15);
      CoRevertToSelf();
      result = 2161129477LL;
    }
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x84,
                           (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\Util\\win10\\NetworkCompliance.cpp",
                           v3);
  }
  return result;
}

```

## disassembly

```asm
0x1800c6380  mov     [rsp+arg_0], rbx
0x1800c6385  push    rdi
0x1800c6386  sub     rsp, 60h
0x1800c638a  mov     rax, cs:__security_cookie
0x1800c6391  xor     rax, rsp
0x1800c6394  mov     [rsp+68h+var_10], rax
0x1800c6399  call    ?Instance@CGlobalObjects@@SAAEAV1@XZ; CGlobalObjects::Instance(void)
0x1800c639e  mov     rbx, rax
0x1800c63a1  xor     edx, edx; bool
0x1800c63a3  mov     rcx, rax; this
0x1800c63a6  call    ?UpdateDeviceOptions@CDeviceProfile@@QEAAX_N@Z; CDeviceProfile::UpdateDeviceOptions(bool)
0x1800c63ab  lea     rdi, [rbx+8]
0x1800c63af  mov     rcx, rdi; SRWLock
0x1800c63b2  call    cs:__imp_AcquireSRWLockShared
0x1800c63b8  movzx   ebx, word ptr [rbx+2]
0x1800c63bc  mov     rcx, rdi; SRWLock
0x1800c63bf  call    cs:__imp_ReleaseSRWLockShared
0x1800c63c5  bt      ebx, 9
0x1800c63c9  jb      short loc_1800C63D5
0x1800c63cb  mov     eax, 1
0x1800c63d0  jmp     loc_1800C6542
0x1800c63d5  call    cs:__imp_CoImpersonateClient
0x1800c63db  mov     rcx, [rsp+68h]; this
0x1800c63e0  test    eax, eax
0x1800c63e2  js      loc_1800C655A
0x1800c63e8  mov     [rsp+68h+var_38], 1
0x1800c63ed  lea     rcx, [rsp+68h+var_30]
0x1800c63f2  call    ?GetAppIdFromToken@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEAX@Z; GetAppIdFromToken(void *)
0x1800c63f7  nop
0x1800c63f8  cmp     [rsp+68h+var_20], 0
0x1800c63fe  jnz     short loc_1800C641B
0x1800c6400  lea     rcx, [rsp+68h+var_30]; void *
0x1800c6405  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800c640a  nop
0x1800c640b  call    cs:__imp_CoRevertToSelf
0x1800c6411  mov     eax, 1
0x1800c6416  jmp     loc_1800C6542
0x1800c641b  lea     rax, [rsp+68h+var_30]
0x1800c6420  cmp     [rsp+68h+var_18], 0Fh
0x1800c6426  cmova   rax, qword ptr [rsp+68h+var_30]
0x1800c642c  mov     qword ptr [rsp+68h+var_48], rax; int
0x1800c6431  lea     r9, aCallerAppidS; "Caller AppId: %s"
0x1800c6438  mov     r8d, 6Fh ; 'o'; unsigned int
0x1800c643e  lea     rdx, aNetworkcomplia; "NetworkCompliance::VerifyCaller"
0x1800c6445  lea     ecx, [r8-6Bh]; unsigned __int8
0x1800c6449  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800c644e  call    NetworkCompliance___GetWinHttpPreferredConnection
0x1800c6453  test    eax, eax
0x1800c6455  jz      loc_1800C6503
0x1800c645b  sub     eax, 2
0x1800c645e  jz      short loc_1800C64AD
0x1800c6460  cmp     eax, 1
0x1800c6463  jnz     loc_1800C64EE
0x1800c6469  lea     rcx, aCellulardata; "cellularData"
0x1800c6470  call    NetworkCompliance___VerifyAppCapability
0x1800c6475  mov     ebx, eax
0x1800c6477  test    eax, eax
0x1800c6479  jns     short loc_1800C64EE
0x1800c647b  mov     rcx, [rsp+68h]; this
0x1800c6480  mov     r9d, eax; char *
0x1800c6483  lea     r8, aCW1SSrcDeliver_46; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800c648a  mov     edx, 7Fh; void *
0x1800c648f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c6494  nop
0x1800c6495  lea     rcx, [rsp+68h+var_30]; void *
0x1800c649a  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800c649f  nop
0x1800c64a0  call    cs:__imp_CoRevertToSelf
0x1800c64a6  mov     eax, ebx
0x1800c64a8  jmp     loc_1800C6542
0x1800c64ad  lea     rcx, aWifidata; "wifiData"
0x1800c64b4  call    NetworkCompliance___VerifyAppCapability
0x1800c64b9  mov     ebx, eax
0x1800c64bb  test    eax, eax
0x1800c64bd  jns     short loc_1800C64EE
0x1800c64bf  mov     rcx, [rsp+68h]; this
0x1800c64c4  mov     r9d, eax; char *
0x1800c64c7  lea     r8, aCW1SSrcDeliver_46; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800c64ce  mov     edx, 7Bh ; '{'; void *
0x1800c64d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c64d8  nop
0x1800c64d9  lea     rcx, [rsp+68h+var_30]; void *
0x1800c64de  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800c64e3  nop
0x1800c64e4  call    cs:__imp_CoRevertToSelf
0x1800c64ea  mov     eax, ebx
0x1800c64ec  jmp     short loc_1800C6542
0x1800c64ee  lea     rcx, [rsp+68h+var_30]; void *
0x1800c64f3  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800c64f8  nop
0x1800c64f9  call    cs:__imp_CoRevertToSelf
0x1800c64ff  xor     eax, eax
0x1800c6501  jmp     short loc_1800C6542
0x1800c6503  mov     rcx, [rsp+68h]; this
0x1800c6508  mov     ebx, 80D03805h
0x1800c650d  mov     r9d, ebx; char *
0x1800c6510  lea     r8, aCW1SSrcDeliver_46; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x1800c6517  mov     edx, 74h ; 't'; void *
0x1800c651c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c6521  nop
0x1800c6522  lea     rcx, [rsp+68h+var_30]; void *
0x1800c6527  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800c652c  nop
0x1800c652d  call    cs:__imp_CoRevertToSelf
0x1800c6533  mov     eax, ebx
0x1800c6535  jmp     short loc_1800C6542
0x1800c6537  mov     eax, 8007000Eh
0x1800c653c  jmp     short loc_1800C6542
0x1800c653e  mov     eax, [rsp+68h+var_34]
0x1800c6542  mov     rcx, [rsp+68h+var_10]
0x1800c6547  xor     rcx, rsp; StackCookie
0x1800c654a  call    __security_check_cookie
0x1800c654f  mov     rbx, [rsp+68h+arg_0]
0x1800c6554  add     rsp, 60h
0x1800c6558  pop     rdi
0x1800c6559  retn
0x1800c655a  mov     r9d, eax; char *
0x1800c655d  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x1800c6564  mov     edx, 1262h; void *
0x1800c6569  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
