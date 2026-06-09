# CscPolicy_AsyncPolicyThreadProc(void *)

- ea: `0x180012120`
- end: `0x180012379`
- name: `?CscPolicy_AsyncPolicyThreadProc@@YAKPEAX@Z`
- size: `601`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x1800084e0`
- `0x180009864`
- `0x18000f5cc`
- `0x180012120`
- `0x1800128e4`
- `0x180012a64`
- `0x180012b48`
- `0x180012da4`
- `0x180012fc4`
- `0x180013088`
- `0x1800130ec`
- `0x1800138b8`
- `0x1800144a8`
- `0x18002a808`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180012301`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180012301`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180012182`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180012182`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180012372`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180012372`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012346`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012346`
- `CSCAPI!OfflineFilesQueryStatus` at `0x18001223e`
- `CSCAPI!OfflineFilesQueryStatus` at `0x18001223e`

## pseudocode

```c
void __fastcall __noreturn CscPolicy_AsyncPolicyThreadProc(_QWORD *Parameter)
{
  __int64 PolicyAuthority; // rsi
  void *v3; // rcx
  UstVarLib *v4; // rcx
  unsigned int Error; // eax
  void *v6; // rdx
  int ServiceActivePolicyAuthority; // edi
  unsigned int v8; // eax
  const unsigned __int16 *v9; // rcx
  unsigned int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rdx
  void *v15; // rcx
  HMODULE v16; // rbp
  unsigned __int64 v17; // r14
  void *v18; // rsi
  int v19; // r15d
  BOOL pbActive; // [rsp+50h] [rbp+8h] BYREF
  int v21; // [rsp+58h] [rbp+10h] BYREF

  PolicyAuthority = (int)CscPolAuth_ReadPolicyAuthority();
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x80) != 0 )
    WPP_SF_q(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 57, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids, Parameter[4]);
  v3 = (void *)Parameter[4];
  if ( v3 && !ImpersonateLoggedOnUser(v3) )
  {
    Error = UstVarLib::ResultFromLastError(v4);
    ServiceActivePolicyAuthority = Error;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 58, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids, Error);
    goto LABEL_35;
  }
  ServiceActivePolicyAuthority = 0;
  if ( *((_DWORD *)Parameter + 6) )
  {
    v8 = CscPolicy_ProcessEnableDisablePolicy((&lpSubKey)[PolicyAuthority]);
    v9 = (const unsigned __int16 *)WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x80) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 59, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids, v8);
    v10 = CscPolicy_ProcessBranchCacheEnableDisablePolicy(v9);
    ServiceActivePolicyAuthority = v10;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x80) != 0 )
      WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 60, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids, v10);
  }
  pbActive = 0;
  OfflineFilesQueryStatus(&pbActive, 0);
  if ( pbActive )
  {
    v21 = 0;
    ServiceActivePolicyAuthority = CscPolicyp_GetServiceActivePolicyAuthority((enum POLICY_AUTHORITY *)&v21);
    if ( ServiceActivePolicyAuthority >= 0 )
    {
      if ( *((_DWORD *)Parameter + 6) )
      {
        v11 = CscPolicy_ProcessCacheQuotaPolicy((&lpSubKey)[v21]);
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x80) != 0 )
        {
          WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 61, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids, v11);
        }
        v12 = CscPolicy_ProcessEncryptionPolicy();
        ServiceActivePolicyAuthority = v12;
        v13 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x80) == 0 )
        {
          goto LABEL_30;
        }
        v14 = 62;
      }
      else
      {
        v12 = CscPolicy_ProcessAdminPinPolicy();
        ServiceActivePolicyAuthority = v12;
        v13 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
          goto LABEL_30;
        v14 = 63;
      }
      WPP_SF_d(*(_QWORD *)(v13 + 16), v14, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids, v12);
    }
  }
  v13 = WPP_GLOBAL_Control;
LABEL_30:
  if ( Parameter[4] )
  {
    RevertToSelf();
    v13 = WPP_GLOBAL_Control;
  }
  if ( (_UNKNOWN *)v13 != &WPP_GLOBAL_Control && (*(_BYTE *)(v13 + 28) & 0x80) != 0 )
    WPP_SF_q(*(_QWORD *)(v13 + 16), 64, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids, Parameter[4]);
LABEL_35:
  v15 = (void *)Parameter[4];
  v16 = (HMODULE)*Parameter;
  v17 = Parameter[1];
  v18 = (void *)Parameter[2];
  v19 = *((_DWORD *)Parameter + 10);
  if ( v15 )
    CloseHandle(v15);
  CscUtil_HeapFree(Parameter, v6);
  if ( v19 )
    CscPolicy_ProcessGroupPolicyCompleted(v17, ServiceActivePolicyAuthority);
  else
    CscPolicy_ProcessWMIPolicyCompleted(v18);
  FreeLibraryAndExitThread(v16, 0);
}

```

## disassembly

```asm
0x180012120  mov     [rsp+arg_10], rbx
0x180012125  mov     [rsp+arg_18], rbp
0x18001212a  push    rsi
0x18001212b  push    rdi
0x18001212c  push    r13
0x18001212e  push    r14
0x180012130  push    r15
0x180012132  sub     rsp, 20h
0x180012136  mov     rbx, rcx
0x180012139  call    ?CscPolAuth_ReadPolicyAuthority@@YA?AW4POLICY_AUTHORITY@@XZ; CscPolAuth_ReadPolicyAuthority(void)
0x18001213e  movsxd  rsi, eax
0x180012141  mov     rcx, cs:WPP_GLOBAL_Control
0x180012148  lea     rbp, WPP_GLOBAL_Control
0x18001214f  lea     r15, WPP_0c7c2fbccac53d672b897e28c13f3d8d_Traceguids
0x180012156  mov     r14b, 80h
0x180012159  cmp     rcx, rbp
0x18001215c  jz      short loc_180012179
0x18001215e  test    [rcx+1Ch], r14b
0x180012162  jz      short loc_180012179
0x180012164  mov     r9, [rbx+20h]
0x180012168  mov     edx, 39h ; '9'
0x18001216d  mov     rcx, [rcx+10h]
0x180012171  mov     r8, r15
0x180012174  call    WPP_SF_q
0x180012179  mov     rcx, [rbx+20h]; hToken
0x18001217d  test    rcx, rcx
0x180012180  jz      short loc_1800121C6
0x180012182  call    cs:__imp_ImpersonateLoggedOnUser
0x180012188  test    eax, eax
0x18001218a  jnz     short loc_1800121C6
0x18001218c  call    ?ResultFromLastError@UstVarLib@@YAJXZ; UstVarLib::ResultFromLastError(void)
0x180012191  mov     edi, eax
0x180012193  mov     rcx, cs:WPP_GLOBAL_Control
0x18001219a  cmp     rcx, rbp
0x18001219d  jz      loc_18001232E
0x1800121a3  test    byte ptr [rcx+1Ch], 2
0x1800121a7  jz      loc_18001232E
0x1800121ad  mov     rcx, [rcx+10h]
0x1800121b1  mov     edx, 3Ah ; ':'
0x1800121b6  mov     r9d, eax
0x1800121b9  mov     r8, r15
0x1800121bc  call    WPP_SF_d
0x1800121c1  jmp     loc_18001232E
0x1800121c6  xor     edi, edi
0x1800121c8  lea     r13, lpSubKey
0x1800121cf  cmp     [rbx+18h], edi
0x1800121d2  jz      short loc_18001222F
0x1800121d4  mov     rcx, [r13+rsi*8+0]; lpSubKey
0x1800121d9  call    ?CscPolicy_ProcessEnableDisablePolicy@@YAJPEBG@Z; CscPolicy_ProcessEnableDisablePolicy(ushort const *)
0x1800121de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800121e5  cmp     rcx, rbp
0x1800121e8  jz      short loc_180012202
0x1800121ea  test    [rcx+1Ch], r14b
0x1800121ee  jz      short loc_180012202
0x1800121f0  mov     rcx, [rcx+10h]
0x1800121f4  lea     edx, [rdi+3Bh]
0x1800121f7  mov     r9d, eax
0x1800121fa  mov     r8, r15
0x1800121fd  call    WPP_SF_d
0x180012202  call    ?CscPolicy_ProcessBranchCacheEnableDisablePolicy@@YAJPEBG@Z; CscPolicy_ProcessBranchCacheEnableDisablePolicy(ushort const *)
0x180012207  mov     edi, eax
0x180012209  mov     rcx, cs:WPP_GLOBAL_Control
0x180012210  cmp     rcx, rbp
0x180012213  jz      short loc_18001222F
0x180012215  test    [rcx+1Ch], r14b
0x180012219  jz      short loc_18001222F
0x18001221b  mov     rcx, [rcx+10h]
0x18001221f  mov     edx, 3Ch ; '<'
0x180012224  mov     r9d, eax
0x180012227  mov     r8, r15
0x18001222a  call    WPP_SF_d
0x18001222f  xor     edx, edx; pbEnabled
0x180012231  mov     [rsp+48h+pbActive], 0
0x180012239  lea     rcx, [rsp+48h+pbActive]; pbActive
0x18001223e  call    cs:__imp_OfflineFilesQueryStatus
0x180012244  cmp     [rsp+48h+pbActive], 0
0x180012249  jz      loc_1800122F3
0x18001224f  lea     rcx, [rsp+48h+arg_8]; enum POLICY_AUTHORITY *
0x180012254  mov     [rsp+48h+arg_8], 0
0x18001225c  call    ?CscPolicyp_GetServiceActivePolicyAuthority@@YAJPEAW4POLICY_AUTHORITY@@@Z; CscPolicyp_GetServiceActivePolicyAuthority(POLICY_AUTHORITY *)
0x180012261  mov     edi, eax
0x180012263  test    eax, eax
0x180012265  js      loc_1800122F3
0x18001226b  cmp     dword ptr [rbx+18h], 0
0x18001226f  jz      short loc_1800122C6
0x180012271  movsxd  rcx, [rsp+48h+arg_8]
0x180012276  mov     rcx, [r13+rcx*8+0]; lpSubKey
0x18001227b  call    ?CscPolicy_ProcessCacheQuotaPolicy@@YAJPEBG@Z; CscPolicy_ProcessCacheQuotaPolicy(ushort const *)
0x180012280  mov     rcx, cs:WPP_GLOBAL_Control
0x180012287  cmp     rcx, rbp
0x18001228a  jz      short loc_1800122A6
0x18001228c  test    [rcx+1Ch], r14b
0x180012290  jz      short loc_1800122A6
0x180012292  mov     rcx, [rcx+10h]
0x180012296  mov     edx, 3Dh ; '='
0x18001229b  mov     r9d, eax
0x18001229e  mov     r8, r15
0x1800122a1  call    WPP_SF_d
0x1800122a6  call    ?CscPolicy_ProcessEncryptionPolicy@@YAJXZ; CscPolicy_ProcessEncryptionPolicy(void)
0x1800122ab  mov     edi, eax
0x1800122ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800122b4  cmp     rcx, rbp
0x1800122b7  jz      short loc_1800122FA
0x1800122b9  test    [rcx+1Ch], r14b
0x1800122bd  jz      short loc_1800122FA
0x1800122bf  mov     edx, 3Eh ; '>'
0x1800122c4  jmp     short loc_1800122E4
0x1800122c6  call    ?CscPolicy_ProcessAdminPinPolicy@@YAJXZ; CscPolicy_ProcessAdminPinPolicy(void)
0x1800122cb  mov     edi, eax
0x1800122cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800122d4  cmp     rcx, rbp
0x1800122d7  jz      short loc_1800122FA
0x1800122d9  test    byte ptr [rcx+1Ch], 2
0x1800122dd  jz      short loc_1800122FA
0x1800122df  mov     edx, 3Fh ; '?'
0x1800122e4  mov     rcx, [rcx+10h]
0x1800122e8  mov     r9d, eax
0x1800122eb  mov     r8, r15
0x1800122ee  call    WPP_SF_d
0x1800122f3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800122fa  cmp     qword ptr [rbx+20h], 0
0x1800122ff  jz      short loc_18001230E
0x180012301  call    cs:__imp_RevertToSelf
0x180012307  mov     rcx, cs:WPP_GLOBAL_Control
0x18001230e  cmp     rcx, rbp
0x180012311  jz      short loc_18001232E
0x180012313  test    [rcx+1Ch], r14b
0x180012317  jz      short loc_18001232E
0x180012319  mov     r9, [rbx+20h]
0x18001231d  mov     edx, 40h ; '@'
0x180012322  mov     rcx, [rcx+10h]
0x180012326  mov     r8, r15
0x180012329  call    WPP_SF_q
0x18001232e  mov     rcx, [rbx+20h]; hObject
0x180012332  mov     rbp, [rbx]
0x180012335  mov     r14, [rbx+8]
0x180012339  mov     rsi, [rbx+10h]
0x18001233d  mov     r15d, [rbx+28h]
0x180012341  test    rcx, rcx
0x180012344  jz      short loc_18001234C
0x180012346  call    cs:__imp_CloseHandle
0x18001234c  mov     rcx, rbx; lpMem
0x18001234f  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x180012354  test    r15d, r15d
0x180012357  jz      short loc_180012365
0x180012359  mov     edx, edi; int
0x18001235b  mov     rcx, r14; unsigned __int64
0x18001235e  call    ?CscPolicy_ProcessGroupPolicyCompleted@@YAK_KJ@Z; CscPolicy_ProcessGroupPolicyCompleted(unsigned __int64,long)
0x180012363  jmp     short loc_18001236D
0x180012365  mov     rcx, rsi; void *
0x180012368  call    ?CscPolicy_ProcessWMIPolicyCompleted@@YAXPEAX@Z; CscPolicy_ProcessWMIPolicyCompleted(void *)
0x18001236d  xor     edx, edx; dwExitCode
0x18001236f  mov     rcx, rbp; hLibModule
0x180012372  call    cs:__imp_FreeLibraryAndExitThread
```
