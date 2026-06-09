# CreateClusterNotifyPort

- ea: `0x18005e840`
- end: `0x18005ea06`
- name: `CreateClusterNotifyPort`
- size: `454`
- prototype: `HCHANGE __stdcall(HCHANGE hChange, HCLUSTER hCluster, DWORD dwFilter, DWORD_PTR dwNotifyKey)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180040790`

## callees

- `0x180014638`
- `0x18005987c`
- `0x18005b548`
- `0x18005c114`
- `0x18005c424`
- `0x18005cbb4`
- `0x18005e840`
- `0x18006f910`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e94e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e957`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e98a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e993`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e94e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e957`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e98a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005e993`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005e8eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005e8fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005e8eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005e8fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e919`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e919`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005e891`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005e891`

## string_xrefs

- `0x18005e931`: `Failed to create notify session - %d`
- `0x18005e92a`: `CreateClusterNotifyPort`
- `0x18005e999`: `CreateClusterNotifyPort`

## pseudocode

```c
HCHANGE __stdcall CreateClusterNotifyPort(HCHANGE hChange, HCLUSTER hCluster, DWORD dwFilter, DWORD_PTR dwNotifyKey)
{
  DWORD v8; // ecx
  struct _RTL_CRITICAL_SECTION *v10; // rbp
  char *v11; // rbx
  struct _RTL_CRITICAL_SECTION *v12; // r14
  _QWORD *NotifySession; // rax
  DWORD LastError; // esi
  int v15; // [rsp+30h] [rbp-38h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-30h] BYREF
  int v17; // [rsp+78h] [rbp+10h] BYREF

  hMem = 0;
  if ( hCluster != (HCLUSTER)-1LL
    && !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(
                           hChange,
                           hCluster)
    || hChange != (HCHANGE)-1LL
    && !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCHANGE *>(
                           hChange,
                           hChange) )
  {
    v8 = 6;
LABEL_6:
    SetLastError(v8);
    return 0;
  }
  v17 = 0;
  v15 = 1;
  if ( (unsigned int)InitializeClusterNotifyPort(
                       hChange,
                       hCluster,
                       (const enum CLUSTER_NOTIFICATIONS_VERSION *)&v15,
                       &hMem,
                       &v17) )
    return 0;
  if ( v17 )
    return (HCHANGE)hMem;
  v10 = (struct _RTL_CRITICAL_SECTION *)((char *)hCluster + 232);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)hCluster + 232));
  v11 = (char *)hMem;
  v12 = (struct _RTL_CRITICAL_SECTION *)((char *)hMem + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)hMem + 16));
  NotifySession = CreateNotifySession(v11, (__int64)hCluster, 1);
  if ( !NotifySession )
  {
    LastError = GetLastError();
    TraceMsg(2u, 7u, (__int64)L"CreateClusterNotifyPort", 739, L"Failed to create notify session - %d", LastError);
    LeaveCriticalSection(v12);
    LeaveCriticalSection(v10);
LABEL_13:
    if ( hChange == (HCHANGE)-1LL )
      DestroyNotifyCommon(v11, 1);
    v8 = LastError;
    goto LABEL_6;
  }
  LastError = AddEventToSession(NotifySession, 0, dwFilter, dwNotifyKey);
  LeaveCriticalSection(v12);
  LeaveCriticalSection(v10);
  if ( LastError )
  {
    TraceMsg(2u, 7u, (__int64)L"CreateClusterNotifyPort", 763, L"AddEventToSession failed - %d", LastError);
    goto LABEL_13;
  }
  TraceMsg(4u, 7u, (__int64)L"CreateClusterNotifyPort", 772, L"Returning Notify handle 0x%p", v11);
  return (HCHANGE)v11;
}

```

## disassembly

```asm
0x18005e840  mov     [rsp+arg_0], rbx
0x18005e845  mov     [rsp+arg_10], rbp
0x18005e84a  push    rsi
0x18005e84b  push    rdi
0x18005e84c  push    r12
0x18005e84e  push    r14
0x18005e850  push    r15
0x18005e852  sub     rsp, 40h
0x18005e856  mov     [rsp+68h+hMem], 0
0x18005e85f  mov     r15, r9
0x18005e862  mov     r12d, r8d
0x18005e865  mov     rsi, rdx
0x18005e868  mov     rdi, rcx
0x18005e86b  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18005e86f  jz      short loc_18005E87A
0x18005e871  call    ??$Contains@PEAU_HCLUSTER@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCLUSTER@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(_HCLUSTER *)
0x18005e876  test    al, al
0x18005e878  jz      short loc_18005E88C
0x18005e87a  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18005e87e  jz      short loc_18005E89E
0x18005e880  mov     rdx, rdi
0x18005e883  call    ??$Contains@PEAU_HCHANGE@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCHANGE@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCHANGE *>(_HCHANGE *)
0x18005e888  test    al, al
0x18005e88a  jnz     short loc_18005E89E
0x18005e88c  mov     ecx, 6; dwErrCode
0x18005e891  call    cs:__imp_SetLastError
0x18005e897  xor     eax, eax
0x18005e899  jmp     loc_18005E9ED
0x18005e89e  lea     rax, [rsp+68h+arg_8]
0x18005e8a3  mov     [rsp+68h+arg_8], 0
0x18005e8ab  lea     r9, [rsp+68h+hMem]; struct _CNOTIFY **
0x18005e8b0  mov     [rsp+68h+var_48], rax; int *
0x18005e8b5  lea     r8, [rsp+68h+var_38]; enum CLUSTER_NOTIFICATIONS_VERSION *
0x18005e8ba  mov     [rsp+68h+var_38], 1
0x18005e8c2  mov     rdx, rsi; struct _HCLUSTER *
0x18005e8c5  mov     rcx, rdi; struct _HCHANGE *
0x18005e8c8  call    ?InitializeClusterNotifyPort@@YAKPEAU_HCHANGE@@PEAU_HCLUSTER@@AEBW4CLUSTER_NOTIFICATIONS_VERSION@@AEAPEAU_CNOTIFY@@AEAH@Z; InitializeClusterNotifyPort(_HCHANGE *,_HCLUSTER *,CLUSTER_NOTIFICATIONS_VERSION const &,_CNOTIFY * &,int &)
0x18005e8cd  test    eax, eax
0x18005e8cf  jnz     short loc_18005E897
0x18005e8d1  cmp     [rsp+68h+arg_8], eax
0x18005e8d5  jz      short loc_18005E8E1
0x18005e8d7  mov     rax, [rsp+68h+hMem]
0x18005e8dc  jmp     loc_18005E9ED
0x18005e8e1  lea     rbp, [rsi+0E8h]
0x18005e8e8  mov     rcx, rbp; lpCriticalSection
0x18005e8eb  call    cs:__imp_EnterCriticalSection
0x18005e8f1  mov     rbx, [rsp+68h+hMem]
0x18005e8f6  lea     r14, [rbx+10h]
0x18005e8fa  mov     rcx, r14; lpCriticalSection
0x18005e8fd  call    cs:__imp_EnterCriticalSection
0x18005e903  mov     r8d, 1
0x18005e909  mov     rdx, rsi
0x18005e90c  mov     rcx, rbx
0x18005e90f  call    ?CreateNotifySession@@YAPEAU_CNOTIFY_SESSION@@PEAU_CNOTIFY@@PEAU_CLUSTER@@W4CLUSTER_NOTIFICATIONS_VERSION@@@Z; CreateNotifySession(_CNOTIFY *,_CLUSTER *,CLUSTER_NOTIFICATIONS_VERSION)
0x18005e914  test    rax, rax
0x18005e917  jnz     short loc_18005E975
0x18005e919  call    cs:__imp_GetLastError
0x18005e91f  mov     dword ptr [rsp+68h+var_40], eax
0x18005e923  mov     edx, 7
0x18005e928  mov     esi, eax
0x18005e92a  lea     r8, aCreateclustern_3; "CreateClusterNotifyPort"
0x18005e931  lea     rax, aFailedToCreate_3; "Failed to create notify session - %d"
0x18005e938  mov     r9d, 2E3h
0x18005e93e  mov     [rsp+68h+var_48], rax
0x18005e943  lea     ecx, [rdx-5]
0x18005e946  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005e94b  mov     rcx, r14; lpCriticalSection
0x18005e94e  call    cs:__imp_LeaveCriticalSection
0x18005e954  mov     rcx, rbp; lpCriticalSection
0x18005e957  call    cs:__imp_LeaveCriticalSection
0x18005e95d  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18005e961  jnz     short loc_18005E96E
0x18005e963  lea     edx, [rdi+2]; int
0x18005e966  mov     rcx, rbx; hMem
0x18005e969  call    ?DestroyNotifyCommon@@YAXPEAU_CNOTIFY@@H@Z; DestroyNotifyCommon(_CNOTIFY *,int)
0x18005e96e  mov     ecx, esi
0x18005e970  jmp     loc_18005E891
0x18005e975  mov     r9, r15
0x18005e978  mov     r8d, r12d
0x18005e97b  xor     edx, edx
0x18005e97d  mov     rcx, rax
0x18005e980  call    ?AddEventToSession@@YAKPEAU_CNOTIFY_SESSION@@PEAXK_KW4CLUSTER_NOTIFICATIONS_VERSION@@@Z; AddEventToSession(_CNOTIFY_SESSION *,void *,ulong,unsigned __int64,CLUSTER_NOTIFICATIONS_VERSION)
0x18005e985  mov     rcx, r14; lpCriticalSection
0x18005e988  mov     esi, eax
0x18005e98a  call    cs:__imp_LeaveCriticalSection
0x18005e990  mov     rcx, rbp; lpCriticalSection
0x18005e993  call    cs:__imp_LeaveCriticalSection
0x18005e999  lea     r8, aCreateclustern_3; "CreateClusterNotifyPort"
0x18005e9a0  mov     edx, 7
0x18005e9a5  test    esi, esi
0x18005e9a7  jz      short loc_18005E9C9
0x18005e9a9  lea     rax, aAddeventtosess_0; "AddEventToSession failed - %d"
0x18005e9b0  mov     dword ptr [rsp+68h+var_40], esi
0x18005e9b4  mov     r9d, 2FBh
0x18005e9ba  mov     [rsp+68h+var_48], rax
0x18005e9bf  lea     ecx, [rdx-5]
0x18005e9c2  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005e9c7  jmp     short loc_18005E95D
0x18005e9c9  lea     rax, aReturningNotif; "Returning Notify handle 0x%p"
0x18005e9d0  mov     [rsp+68h+var_40], rbx
0x18005e9d5  mov     r9d, 304h
0x18005e9db  mov     [rsp+68h+var_48], rax
0x18005e9e0  mov     ecx, 4
0x18005e9e5  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005e9ea  mov     rax, rbx
0x18005e9ed  lea     r11, [rsp+68h+var_28]
0x18005e9f2  mov     rbx, [r11+30h]
0x18005e9f6  mov     rbp, [r11+40h]
0x18005e9fa  mov     rsp, r11
0x18005e9fd  pop     r15
0x18005e9ff  pop     r14
0x18005ea01  pop     r12
0x18005ea03  pop     rdi
0x18005ea04  pop     rsi
0x18005ea05  retn
```
