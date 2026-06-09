# FwCopyDefaultsToLocalStorePerUserRights(void *,HKEY__ *)

- ea: `0x1800999a4`
- end: `0x180099dcf`
- name: `?FwCopyDefaultsToLocalStorePerUserRights@@YAJPEAXPEAUHKEY__@@@Z`
- size: `1067`
- prototype: `__int64 __fastcall(void *, HKEY)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x1800a2578`

## callees

- `0x18000a710`
- `0x180036b64`
- `0x1800729c0`
- `0x1800999a4`
- `0x180099dd8`

## import_xrefs

- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180099b70`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x180099b70`
- `FWPolicyIOMgr!FwGetGlobalConfigFromLocalTempStore` at `0x180099ade`
- `FWPolicyIOMgr!FwGetGlobalConfigFromLocalTempStore` at `0x180099ade`
- `FWPolicyIOMgr!FwSetConfig` at `0x180099bd5`
- `FWPolicyIOMgr!FwSetConfig` at `0x180099bd5`
- `FWPolicyIOMgr!FwSetGlobalConfig` at `0x180099b10`
- `FWPolicyIOMgr!FwSetGlobalConfig` at `0x180099b10`
- `FWPolicyIOMgr!FwDestroyLocalTempStore` at `0x180099d99`
- `FWPolicyIOMgr!FwDestroyLocalTempStore` at `0x180099d99`
- `FWPolicyIOMgr!FwCreateLocalTempStore` at `0x1800999fd`
- `FWPolicyIOMgr!FwCreateLocalTempStore` at `0x1800999fd`
- `FWPolicyIOMgr!FwClosePolicyStore` at `0x180099d7a`
- `FWPolicyIOMgr!FwClosePolicyStore` at `0x180099d7a`
- `FWPolicyIOMgr!FwGetConfig` at `0x180099ba7`
- `FWPolicyIOMgr!FwGetConfig` at `0x180099ba7`
- `FWPolicyIOMgr!FwOpenPolicyStore` at `0x180099a5f`
- `FWPolicyIOMgr!FwOpenPolicyStore` at `0x180099a5f`

## string_xrefs

- `0x1800999dc`: `SYSTEM\CurrentControlSet\Services\SharedAccess\Defaults\FirewallPolicy`

## pseudocode

```c
__int64 __fastcall FwCopyDefaultsToLocalStorePerUserRights(void *a1, HKEY a2)
{
  int GlobalConfigFromLocalTempStore; // ebx
  __int64 v5; // rcx
  __int64 v6; // rdx
  unsigned int v7; // esi
  unsigned int v8; // esi
  unsigned int ProfileTypeFromProfileIndex; // r15d
  unsigned int i; // r14d
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v13; // [rsp+38h] [rbp-C8h] BYREF
  _DWORD v14[4]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v15[1024]; // [rsp+50h] [rbp-B0h] BYREF

  v14[0] = 0;
  v13 = 0;
  v12 = 0;
  GlobalConfigFromLocalTempStore = FwCreateLocalTempStore(
                                     L"SYSTEM\\CurrentControlSet\\Services\\SharedAccess\\Defaults\\FirewallPolicy",
                                     a2,
                                     &v13);
  if ( GlobalConfigFromLocalTempStore < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_53;
    v6 = 43;
    goto LABEL_5;
  }
  GlobalConfigFromLocalTempStore = FwOpenPolicyStore(2, 2, 0, &v12);
  if ( GlobalConfigFromLocalTempStore < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_53;
    v6 = 44;
LABEL_5:
    WPP_SF_d(
      *(_QWORD *)(v5 + 16),
      v6,
      WPP_681457f4cdf23248f51377d70d9ff610_Traceguids,
      (unsigned int)GlobalConfigFromLocalTempStore);
    goto LABEL_53;
  }
  if ( (int)FwRpcAPIsSecModeAccessCheckForClient(1, 2, a1) >= 0 )
  {
    v7 = 3;
    while ( 1 )
    {
      if ( v7 != 11 && v7 != 18 )
      {
        v14[0] = 4;
        GlobalConfigFromLocalTempStore = FwGetGlobalConfigFromLocalTempStore(a2, v7, v15, v14);
        if ( GlobalConfigFromLocalTempStore < 0 )
        {
          if ( GlobalConfigFromLocalTempStore != -2147024894 && GlobalConfigFromLocalTempStore != -2147024846 )
          {
            v5 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              v6 = 46;
              goto LABEL_5;
            }
            goto LABEL_53;
          }
        }
        else
        {
          GlobalConfigFromLocalTempStore = FwSetGlobalConfig(512, 2, 0, v7, v15, 4);
          if ( GlobalConfigFromLocalTempStore < 0 )
          {
            v5 = WPP_GLOBAL_Control;
            if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            {
              v6 = 45;
              goto LABEL_5;
            }
            goto LABEL_53;
          }
        }
      }
      if ( ++v7 >= 0x13 )
      {
        v8 = 0;
        while ( 2 )
        {
          ProfileTypeFromProfileIndex = FwGetProfileTypeFromProfileIndex(v8);
          for ( i = 1; i < 0x13; ++i )
          {
            v14[0] = 1024;
            GlobalConfigFromLocalTempStore = FwGetConfig(v13, i, ProfileTypeFromProfileIndex, v15, v14);
            if ( GlobalConfigFromLocalTempStore < 0 )
            {
              if ( GlobalConfigFromLocalTempStore != -2147024894 && GlobalConfigFromLocalTempStore != -2147024846 )
              {
                v5 = WPP_GLOBAL_Control;
                if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
                {
                  v6 = 48;
                  goto LABEL_5;
                }
                goto LABEL_53;
              }
            }
            else
            {
              GlobalConfigFromLocalTempStore = FwSetConfig(v12, i, ProfileTypeFromProfileIndex, v15, v14[0]);
              if ( GlobalConfigFromLocalTempStore < 0 )
              {
                v5 = WPP_GLOBAL_Control;
                if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
                {
                  v6 = 47;
                  goto LABEL_5;
                }
                goto LABEL_53;
              }
            }
          }
          if ( ++v8 < 3 )
            continue;
          break;
        }
        GlobalConfigFromLocalTempStore = FwCopyPolicyObjs(v13, v12, 1);
        if ( GlobalConfigFromLocalTempStore >= 0 )
        {
          GlobalConfigFromLocalTempStore = FwCopyPolicyObjs(v13, v12, 0);
          if ( GlobalConfigFromLocalTempStore >= 0 )
            break;
          v5 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v6 = 50;
            goto LABEL_5;
          }
        }
        else
        {
          v5 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          {
            v6 = 49;
            goto LABEL_5;
          }
        }
        goto LABEL_53;
      }
    }
  }
  if ( (int)FwRpcAPIsSecModeAccessCheckForClient(2, 2, a1) < 0
    || (GlobalConfigFromLocalTempStore = FwCopyPolicyObjs(v13, v12, 0), GlobalConfigFromLocalTempStore >= 0) )
  {
    GlobalConfigFromLocalTempStore = 0;
    goto LABEL_53;
  }
  v5 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v6 = 51;
    goto LABEL_5;
  }
LABEL_53:
  if ( v12 )
  {
    FwClosePolicyStore(v12);
    v12 = 0;
  }
  if ( v13 )
    FwDestroyLocalTempStore();
  return (unsigned int)GlobalConfigFromLocalTempStore;
}

```

## disassembly

```asm
0x1800999a4  mov     [rsp-8+arg_10], rbx
0x1800999a9  push    rbp
0x1800999aa  push    rsi
0x1800999ab  push    r12
0x1800999ad  push    r14
0x1800999af  push    r15
0x1800999b1  lea     rbp, [rsp-360h]
0x1800999b9  sub     rsp, 460h
0x1800999c0  mov     rax, cs:__security_cookie
0x1800999c7  xor     rax, rsp
0x1800999ca  mov     [rbp+380h+var_30], rax
0x1800999d1  mov     r12, rcx
0x1800999d4  mov     [rsp+480h+var_440], 0
0x1800999dc  lea     rcx, aSystemCurrentc_6; "SYSTEM\\CurrentControlSet\\Services\\Sh"...
0x1800999e3  mov     [rsp+480h+var_448], 0
0x1800999ec  lea     r8, [rsp+480h+var_448]
0x1800999f1  mov     [rsp+480h+var_450], 0
0x1800999fa  mov     r14, rdx
0x1800999fd  call    cs:__imp_FwCreateLocalTempStore
0x180099a04  nop     dword ptr [rax+rax+00h]
0x180099a09  mov     ebx, eax
0x180099a0b  test    eax, eax
0x180099a0d  jns     short loc_180099A4D
0x180099a0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180099a16  lea     rax, WPP_GLOBAL_Control
0x180099a1d  cmp     rcx, rax
0x180099a20  jz      loc_180099D70
0x180099a26  test    byte ptr [rcx+1Ch], 1
0x180099a2a  jz      loc_180099D70
0x180099a30  mov     edx, 2Bh ; '+'
0x180099a35  mov     rcx, [rcx+10h]
0x180099a39  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x180099a40  mov     r9d, ebx
0x180099a43  call    WPP_SF_d
0x180099a48  jmp     loc_180099D70
0x180099a4d  xor     r8d, r8d
0x180099a50  lea     r9, [rsp+480h+var_450]
0x180099a55  lea     r15d, [r8+2]
0x180099a59  mov     edx, r15d
0x180099a5c  mov     ecx, r15d
0x180099a5f  call    cs:__imp_FwOpenPolicyStore
0x180099a66  nop     dword ptr [rax+rax+00h]
0x180099a6b  mov     ebx, eax
0x180099a6d  test    eax, eax
0x180099a6f  jns     short loc_180099A98
0x180099a71  mov     rcx, cs:WPP_GLOBAL_Control
0x180099a78  lea     rax, WPP_GLOBAL_Control
0x180099a7f  cmp     rcx, rax
0x180099a82  jz      loc_180099D70
0x180099a88  test    byte ptr [rcx+1Ch], 1
0x180099a8c  jz      loc_180099D70
0x180099a92  lea     edx, [r15+2Ah]
0x180099a96  jmp     short loc_180099A35
0x180099a98  mov     r8, r12
0x180099a9b  mov     edx, r15d
0x180099a9e  mov     ecx, 1
0x180099aa3  call    FwRpcAPIsSecModeAccessCheckForClient
0x180099aa8  test    eax, eax
0x180099aaa  js      loc_180099D1B
0x180099ab0  mov     esi, 3
0x180099ab5  cmp     esi, 0Bh
0x180099ab8  jz      loc_180099B61
0x180099abe  cmp     esi, 12h
0x180099ac1  jz      loc_180099B61
0x180099ac7  lea     r9, [rsp+480h+var_440]
0x180099acc  mov     [rsp+480h+var_440], 4
0x180099ad4  lea     r8, [rsp+480h+var_430]
0x180099ad9  mov     edx, esi
0x180099adb  mov     rcx, r14
0x180099ade  call    cs:__imp_FwGetGlobalConfigFromLocalTempStore
0x180099ae5  nop     dword ptr [rax+rax+00h]
0x180099aea  mov     ebx, eax
0x180099aec  test    eax, eax
0x180099aee  js      short loc_180099B4D
0x180099af0  lea     rax, [rsp+480h+var_430]
0x180099af5  mov     [rsp+480h+var_458], 4
0x180099afd  mov     ecx, 200h
0x180099b02  mov     [rsp+480h+var_460], rax
0x180099b07  mov     r9d, esi
0x180099b0a  xor     r8d, r8d
0x180099b0d  mov     edx, r15d
0x180099b10  call    cs:__imp_FwSetGlobalConfig
0x180099b17  nop     dword ptr [rax+rax+00h]
0x180099b1c  mov     ebx, eax
0x180099b1e  test    eax, eax
0x180099b20  jns     short loc_180099B61
0x180099b22  mov     rcx, cs:WPP_GLOBAL_Control
0x180099b29  lea     rax, WPP_GLOBAL_Control
0x180099b30  cmp     rcx, rax
0x180099b33  jz      loc_180099D70
0x180099b39  test    byte ptr [rcx+1Ch], 1
0x180099b3d  jz      loc_180099D70
0x180099b43  mov     edx, 2Dh ; '-'
0x180099b48  jmp     loc_180099A35
0x180099b4d  cmp     ebx, 80070002h
0x180099b53  jz      short loc_180099B61
0x180099b55  cmp     ebx, 80070032h
0x180099b5b  jnz     loc_180099C12
0x180099b61  inc     esi
0x180099b63  cmp     esi, 13h
0x180099b66  jb      loc_180099AB5
0x180099b6c  xor     esi, esi
0x180099b6e  mov     ecx, esi
0x180099b70  call    cs:__imp_FwGetProfileTypeFromProfileIndex
0x180099b77  nop     dword ptr [rax+rax+00h]
0x180099b7c  mov     r15d, eax
0x180099b7f  mov     r14d, 1
0x180099b85  mov     rcx, [rsp+480h+var_448]
0x180099b8a  lea     rax, [rsp+480h+var_440]
0x180099b8f  lea     r9, [rsp+480h+var_430]
0x180099b94  mov     [rsp+480h+var_460], rax
0x180099b99  mov     r8d, r15d
0x180099b9c  mov     [rsp+480h+var_440], 400h
0x180099ba4  mov     edx, r14d
0x180099ba7  call    cs:__imp_FwGetConfig
0x180099bae  nop     dword ptr [rax+rax+00h]
0x180099bb3  mov     ebx, eax
0x180099bb5  test    eax, eax
0x180099bb7  js      loc_180099C3D
0x180099bbd  mov     eax, [rsp+480h+var_440]
0x180099bc1  lea     r9, [rsp+480h+var_430]
0x180099bc6  mov     rcx, [rsp+480h+var_450]
0x180099bcb  mov     r8d, r15d
0x180099bce  mov     edx, r14d
0x180099bd1  mov     dword ptr [rsp+480h+var_460], eax
0x180099bd5  call    cs:__imp_FwSetConfig
0x180099bdc  nop     dword ptr [rax+rax+00h]
0x180099be1  mov     ebx, eax
0x180099be3  test    eax, eax
0x180099be5  jns     short loc_180099C4D
0x180099be7  mov     rcx, cs:WPP_GLOBAL_Control
0x180099bee  lea     rax, WPP_GLOBAL_Control
0x180099bf5  cmp     rcx, rax
0x180099bf8  jz      loc_180099D70
0x180099bfe  test    byte ptr [rcx+1Ch], 1
0x180099c02  jz      loc_180099D70
0x180099c08  mov     edx, 2Fh ; '/'
0x180099c0d  jmp     loc_180099A35
0x180099c12  mov     rcx, cs:WPP_GLOBAL_Control
0x180099c19  lea     rax, WPP_GLOBAL_Control
0x180099c20  cmp     rcx, rax
0x180099c23  jz      loc_180099D70
0x180099c29  test    byte ptr [rcx+1Ch], 1
0x180099c2d  jz      loc_180099D70
0x180099c33  mov     edx, 2Eh ; '.'
0x180099c38  jmp     loc_180099A35
0x180099c3d  cmp     ebx, 80070002h
0x180099c43  jz      short loc_180099C4D
0x180099c45  cmp     ebx, 80070032h
0x180099c4b  jnz     short loc_180099CAC
0x180099c4d  inc     r14d
0x180099c50  cmp     r14d, 13h
0x180099c54  jb      loc_180099B85
0x180099c5a  inc     esi
0x180099c5c  cmp     esi, 3
0x180099c5f  jb      loc_180099B6E
0x180099c65  mov     rdx, [rsp+480h+var_450]
0x180099c6a  xor     r9d, r9d
0x180099c6d  mov     rcx, [rsp+480h+var_448]
0x180099c72  lea     r8d, [r9+1]
0x180099c76  call    ?FwCopyPolicyObjs@@YAJPEAX0HKW4_tag_FW_IPSEC_PHASE@@@Z; FwCopyPolicyObjs(void *,void *,int,ulong,_tag_FW_IPSEC_PHASE)
0x180099c7b  mov     ebx, eax
0x180099c7d  test    eax, eax
0x180099c7f  jns     short loc_180099CD7
0x180099c81  mov     rcx, cs:WPP_GLOBAL_Control
0x180099c88  lea     rax, WPP_GLOBAL_Control
0x180099c8f  cmp     rcx, rax
0x180099c92  jz      loc_180099D70
0x180099c98  test    byte ptr [rcx+1Ch], 1
0x180099c9c  jz      loc_180099D70
0x180099ca2  mov     edx, 31h ; '1'
0x180099ca7  jmp     loc_180099A35
0x180099cac  mov     rcx, cs:WPP_GLOBAL_Control
0x180099cb3  lea     rax, WPP_GLOBAL_Control
0x180099cba  cmp     rcx, rax
0x180099cbd  jz      loc_180099D70
0x180099cc3  test    byte ptr [rcx+1Ch], 1
0x180099cc7  jz      loc_180099D70
0x180099ccd  mov     edx, 30h ; '0'
0x180099cd2  jmp     loc_180099A35
0x180099cd7  mov     rdx, [rsp+480h+var_450]
0x180099cdc  xor     r9d, r9d
0x180099cdf  mov     rcx, [rsp+480h+var_448]
0x180099ce4  xor     r8d, r8d
0x180099ce7  call    ?FwCopyPolicyObjs@@YAJPEAX0HKW4_tag_FW_IPSEC_PHASE@@@Z; FwCopyPolicyObjs(void *,void *,int,ulong,_tag_FW_IPSEC_PHASE)
0x180099cec  mov     ebx, eax
0x180099cee  test    eax, eax
0x180099cf0  jns     short loc_180099D15
0x180099cf2  mov     rcx, cs:WPP_GLOBAL_Control
0x180099cf9  lea     rax, WPP_GLOBAL_Control
0x180099d00  cmp     rcx, rax
0x180099d03  jz      short loc_180099D70
0x180099d05  test    byte ptr [rcx+1Ch], 1
0x180099d09  jz      short loc_180099D70
0x180099d0b  mov     edx, 32h ; '2'
0x180099d10  jmp     loc_180099A35
0x180099d15  mov     r15d, 2
0x180099d1b  mov     r8, r12
0x180099d1e  mov     edx, r15d
0x180099d21  mov     ecx, r15d
0x180099d24  call    FwRpcAPIsSecModeAccessCheckForClient
0x180099d29  test    eax, eax
0x180099d2b  js      short loc_180099D6E
0x180099d2d  mov     rdx, [rsp+480h+var_450]
0x180099d32  mov     r9d, 1
0x180099d38  mov     rcx, [rsp+480h+var_448]
0x180099d3d  xor     r8d, r8d
0x180099d40  call    ?FwCopyPolicyObjs@@YAJPEAX0HKW4_tag_FW_IPSEC_PHASE@@@Z; FwCopyPolicyObjs(void *,void *,int,ulong,_tag_FW_IPSEC_PHASE)
0x180099d45  mov     ebx, eax
0x180099d47  test    eax, eax
0x180099d49  jns     short loc_180099D6E
0x180099d4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180099d52  lea     rax, WPP_GLOBAL_Control
0x180099d59  cmp     rcx, rax
0x180099d5c  jz      short loc_180099D70
0x180099d5e  test    byte ptr [rcx+1Ch], 1
0x180099d62  jz      short loc_180099D70
0x180099d64  mov     edx, 33h ; '3'
0x180099d69  jmp     loc_180099A35
0x180099d6e  xor     ebx, ebx
0x180099d70  mov     rcx, [rsp+480h+var_450]
0x180099d75  test    rcx, rcx
0x180099d78  jz      short loc_180099D8F
0x180099d7a  call    cs:__imp_FwClosePolicyStore
0x180099d81  nop     dword ptr [rax+rax+00h]
0x180099d86  mov     [rsp+480h+var_450], 0
0x180099d8f  mov     rcx, [rsp+480h+var_448]
0x180099d94  test    rcx, rcx
0x180099d97  jz      short loc_180099DA5
0x180099d99  call    cs:__imp_FwDestroyLocalTempStore
0x180099da0  nop     dword ptr [rax+rax+00h]
0x180099da5  mov     eax, ebx
0x180099da7  mov     rcx, [rbp+380h+var_30]
0x180099dae  xor     rcx, rsp; StackCookie
0x180099db1  call    __security_check_cookie
0x180099db6  mov     rbx, [rsp+480h+arg_10]
0x180099dbe  add     rsp, 460h
0x180099dc5  pop     r15
0x180099dc7  pop     r14
0x180099dc9  pop     r12
0x180099dcb  pop     rsi
0x180099dcc  pop     rbp
0x180099dcd  retn
```
