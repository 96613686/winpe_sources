# CreateClusterNotifyPortV2

- ea: `0x18005ea10`
- end: `0x18005ec89`
- name: `CreateClusterNotifyPortV2`
- size: `633`
- prototype: `__int64 __usercall@<rax>(struct _HCHANGE *@<rcx>, struct _HCLUSTER *@<rdx>, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180002f50`
- `0x180014638`
- `0x18001cc2c`
- `0x180029578`
- `0x18005987c`
- `0x18005b1b4`
- `0x18005c114`
- `0x18005c424`
- `0x18005cbb4`
- `0x18005ea10`
- `0x18006f910`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005eb2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005eb38`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005ebca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005ebd3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005ec20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005ec29`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005eb2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005eb38`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005ebca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005ebd3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005ec20`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005ec29`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005eace`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005eadf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005eace`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005eadf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005eafb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005eafb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005ea7c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005ea7c`

## string_xrefs

- `0x18005eb18`: `Failed to create notify session - %d`
- `0x18005eb0f`: `CreateClusterNotifyPortV2`
- `0x18005ebf0`: `CreateClusterNotifyPortV2`
- `0x18005ec46`: `CreateClusterNotifyPortV2`

## pseudocode

```c
char *__fastcall CreateClusterNotifyPortV2(struct _HCHANGE *a1, struct _HCLUSTER *a2, __int64 a3, unsigned int a4)
{
  unsigned int v4; // r12d
  DWORD v7; // ecx
  struct _RTL_CRITICAL_SECTION *v9; // r14
  char *v10; // rbx
  struct _RTL_CRITICAL_SECTION *v11; // r15
  struct _CNOTIFY_SESSION *NotifySession; // r13
  DWORD LastError; // edi
  unsigned int i; // edi
  __int128 v15; // xmm6
  DWORD v16; // r12d
  __int64 v17; // [rsp+30h] [rbp-59h]
  int v18; // [rsp+48h] [rbp-41h] BYREF
  int v19; // [rsp+4Ch] [rbp-3Dh] BYREF
  unsigned int v20; // [rsp+50h] [rbp-39h]
  HLOCAL hMem[2]; // [rsp+58h] [rbp-31h] BYREF
  __int64 v22; // [rsp+68h] [rbp-21h]
  _BYTE v23[32]; // [rsp+70h] [rbp-19h] BYREF

  v20 = a4;
  v22 = a3;
  v4 = a4;
  hMem[0] = 0;
  if ( a2 != (struct _HCLUSTER *)-1LL
    && !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(
                           a1,
                           a2)
    || a1 != (struct _HCHANGE *)-1LL
    && !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCHANGE *>(
                           a1,
                           a1) )
  {
    v7 = 6;
LABEL_6:
    SetLastError(v7);
    return 0;
  }
  v18 = 0;
  v19 = 2;
  if ( (unsigned int)InitializeClusterNotifyPort(a1, a2, (const enum CLUSTER_NOTIFICATIONS_VERSION *)&v19, hMem, &v18) )
    return 0;
  if ( !v18 )
  {
    v9 = (struct _RTL_CRITICAL_SECTION *)((char *)a2 + 232);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)a2 + 232));
    v10 = (char *)hMem[0];
    v11 = (struct _RTL_CRITICAL_SECTION *)((char *)hMem[0] + 16);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)hMem[0] + 16));
    NotifySession = (struct _CNOTIFY_SESSION *)CreateNotifySession(v10, (__int64)a2, 2);
    if ( NotifySession )
    {
      for ( i = 0; ; ++i )
      {
        if ( i >= v4 )
        {
          LeaveCriticalSection(v11);
          LeaveCriticalSection(v9);
          TraceMsg(4u, 7u, (__int64)L"CreateClusterNotifyPortV2", 3669, L"Returning Notify handle 0x%p", v10);
          return v10;
        }
        v15 = *(_OWORD *)(v22 + 16LL * i);
        std::wstring::wstring(v23, &base);
        *(_OWORD *)hMem = v15;
        v16 = AddEventToSession(NotifySession, (__int64)v23, 2, (__int64)hMem);
        std::wstring::_Tidy_deallocate(v23);
        if ( v16 )
          break;
        v4 = v20;
      }
      LeaveCriticalSection(v11);
      LeaveCriticalSection(v9);
      LODWORD(v17) = v16;
      TraceMsg(2u, 7u, (__int64)L"CreateClusterNotifyPortV2", 3656, L"AddEventToSession failed - %d", v17);
      if ( a1 == (struct _HCHANGE *)-1LL )
        DestroyNotifyCommon(v10, 1);
      v7 = v16;
    }
    else
    {
      LastError = GetLastError();
      TraceMsg(2u, 7u, (__int64)L"CreateClusterNotifyPortV2", 3629, L"Failed to create notify session - %d", LastError);
      LeaveCriticalSection(v11);
      LeaveCriticalSection(v9);
      if ( a1 == (struct _HCHANGE *)-1LL )
        DestroyNotifyCommon(v10, 1);
      v7 = LastError;
    }
    goto LABEL_6;
  }
  return (char *)hMem[0];
}

```

## disassembly

```asm
0x18005ea10  mov     rax, rsp
0x18005ea13  mov     [rax+20h], rbx
0x18005ea17  push    rbp
0x18005ea18  push    rsi
0x18005ea19  push    rdi
0x18005ea1a  push    r12
0x18005ea1c  push    r13
0x18005ea1e  push    r14
0x18005ea20  push    r15
0x18005ea22  lea     rbp, [rax-57h]
0x18005ea26  sub     rsp, 0A0h
0x18005ea2d  movaps  xmmword ptr [rax-48h], xmm6
0x18005ea31  mov     rax, cs:__security_cookie
0x18005ea38  xor     rax, rsp
0x18005ea3b  mov     [rbp+4Fh+var_48], rax
0x18005ea3f  xor     ebx, ebx
0x18005ea41  mov     [rbp+4Fh+var_88], r9d
0x18005ea45  mov     [rbp+4Fh+var_70], r8
0x18005ea49  mov     r12d, r9d
0x18005ea4c  mov     [rbp+4Fh+hMem], rbx
0x18005ea50  mov     rdi, rdx
0x18005ea53  mov     rsi, rcx
0x18005ea56  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18005ea5a  jz      short loc_18005EA65
0x18005ea5c  call    ??$Contains@PEAU_HCLUSTER@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCLUSTER@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(_HCLUSTER *)
0x18005ea61  test    al, al
0x18005ea63  jz      short loc_18005EA77
0x18005ea65  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18005ea69  jz      short loc_18005EA89
0x18005ea6b  mov     rdx, rsi
0x18005ea6e  call    ??$Contains@PEAU_HCHANGE@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCHANGE@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCHANGE *>(_HCHANGE *)
0x18005ea73  test    al, al
0x18005ea75  jnz     short loc_18005EA89
0x18005ea77  mov     ecx, 6; dwErrCode
0x18005ea7c  call    cs:__imp_SetLastError
0x18005ea82  xor     eax, eax
0x18005ea84  jmp     loc_18005EC5D
0x18005ea89  lea     rax, [rbp+4Fh+var_90]
0x18005ea8d  mov     [rbp+4Fh+var_90], ebx
0x18005ea90  mov     r13d, 2
0x18005ea96  mov     [rsp+0D0h+var_B0], rax; int *
0x18005ea9b  lea     r9, [rbp+4Fh+hMem]; struct _CNOTIFY **
0x18005ea9f  mov     [rbp+4Fh+var_8C], r13d
0x18005eaa3  lea     r8, [rbp+4Fh+var_8C]; enum CLUSTER_NOTIFICATIONS_VERSION *
0x18005eaa7  mov     rdx, rdi; struct _HCLUSTER *
0x18005eaaa  mov     rcx, rsi; struct _HCHANGE *
0x18005eaad  call    ?InitializeClusterNotifyPort@@YAKPEAU_HCHANGE@@PEAU_HCLUSTER@@AEBW4CLUSTER_NOTIFICATIONS_VERSION@@AEAPEAU_CNOTIFY@@AEAH@Z; InitializeClusterNotifyPort(_HCHANGE *,_HCLUSTER *,CLUSTER_NOTIFICATIONS_VERSION const &,_CNOTIFY * &,int &)
0x18005eab2  test    eax, eax
0x18005eab4  jnz     short loc_18005EA82
0x18005eab6  cmp     [rbp+4Fh+var_90], ebx
0x18005eab9  jz      short loc_18005EAC4
0x18005eabb  mov     rax, [rbp+4Fh+hMem]
0x18005eabf  jmp     loc_18005EC5D
0x18005eac4  lea     r14, [rdi+0E8h]
0x18005eacb  mov     rcx, r14; lpCriticalSection
0x18005eace  call    cs:__imp_EnterCriticalSection
0x18005ead4  mov     rbx, [rbp+4Fh+hMem]
0x18005ead8  lea     r15, [rbx+10h]
0x18005eadc  mov     rcx, r15; lpCriticalSection
0x18005eadf  call    cs:__imp_EnterCriticalSection
0x18005eae5  mov     r8d, r13d
0x18005eae8  mov     rdx, rdi
0x18005eaeb  mov     rcx, rbx
0x18005eaee  call    ?CreateNotifySession@@YAPEAU_CNOTIFY_SESSION@@PEAU_CNOTIFY@@PEAU_CLUSTER@@W4CLUSTER_NOTIFICATIONS_VERSION@@@Z; CreateNotifySession(_CNOTIFY *,_CLUSTER *,CLUSTER_NOTIFICATIONS_VERSION)
0x18005eaf3  mov     r13, rax
0x18005eaf6  test    rax, rax
0x18005eaf9  jnz     short loc_18005EB56
0x18005eafb  call    cs:__imp_GetLastError
0x18005eb01  mov     dword ptr [rsp+0D0h+var_A8], eax
0x18005eb05  lea     edx, [r13+7]
0x18005eb09  mov     r9d, 0E2Dh
0x18005eb0f  lea     r8, aCreateclustern_5; "CreateClusterNotifyPortV2"
0x18005eb16  mov     edi, eax
0x18005eb18  lea     rax, aFailedToCreate_3; "Failed to create notify session - %d"
0x18005eb1f  lea     ecx, [rdx-5]
0x18005eb22  mov     [rsp+0D0h+var_B0], rax
0x18005eb27  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005eb2c  mov     rcx, r15; lpCriticalSection
0x18005eb2f  call    cs:__imp_LeaveCriticalSection
0x18005eb35  mov     rcx, r14; lpCriticalSection
0x18005eb38  call    cs:__imp_LeaveCriticalSection
0x18005eb3e  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18005eb42  jnz     short loc_18005EB4F
0x18005eb44  lea     edx, [rsi+2]; int
0x18005eb47  mov     rcx, rbx; hMem
0x18005eb4a  call    ?DestroyNotifyCommon@@YAXPEAU_CNOTIFY@@H@Z; DestroyNotifyCommon(_CNOTIFY *,int)
0x18005eb4f  mov     ecx, edi
0x18005eb51  jmp     loc_18005EA7C
0x18005eb56  xor     edi, edi
0x18005eb58  cmp     edi, r12d
0x18005eb5b  jnb     loc_18005EC1D
0x18005eb61  mov     rcx, [rbp+4Fh+var_70]
0x18005eb65  lea     rdx, base
0x18005eb6c  mov     eax, edi
0x18005eb6e  add     rax, rax
0x18005eb71  movups  xmm6, xmmword ptr [rcx+rax*8]
0x18005eb75  lea     rcx, [rbp+4Fh+var_68]
0x18005eb79  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18005eb7e  mov     r9, [rbp+4Fh+arg_20]
0x18005eb82  lea     rax, [rbp+4Fh+hMem]
0x18005eb86  mov     [rsp+0D0h+var_A0], rax
0x18005eb8b  xor     r8d, r8d
0x18005eb8e  lea     rax, [rbp+4Fh+var_68]
0x18005eb92  mov     dword ptr [rsp+0D0h+var_A8], 2
0x18005eb9a  xor     edx, edx
0x18005eb9c  mov     [rsp+0D0h+var_B0], rax
0x18005eba1  mov     rcx, r13
0x18005eba4  movdqu  xmmword ptr [rbp+4Fh+hMem], xmm6
0x18005eba9  call    ?AddEventToSession@@YAKPEAU_CNOTIFY_SESSION@@PEAXK_KAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4CLUSTER_NOTIFICATIONS_VERSION@@U_NOTIFY_FILTER_AND_TYPE@@@Z; AddEventToSession(_CNOTIFY_SESSION *,void *,ulong,unsigned __int64,std::wstring const &,CLUSTER_NOTIFICATIONS_VERSION,_NOTIFY_FILTER_AND_TYPE)
0x18005ebae  lea     rcx, [rbp+4Fh+var_68]
0x18005ebb2  mov     r12d, eax
0x18005ebb5  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005ebba  test    r12d, r12d
0x18005ebbd  jnz     short loc_18005EBC7
0x18005ebbf  mov     r12d, [rbp+4Fh+var_88]
0x18005ebc3  inc     edi
0x18005ebc5  jmp     short loc_18005EB58
0x18005ebc7  mov     rcx, r15; lpCriticalSection
0x18005ebca  call    cs:__imp_LeaveCriticalSection
0x18005ebd0  mov     rcx, r14; lpCriticalSection
0x18005ebd3  call    cs:__imp_LeaveCriticalSection
0x18005ebd9  mov     edx, 7
0x18005ebde  mov     dword ptr [rsp+0D0h+var_A8], r12d
0x18005ebe3  lea     rax, aAddeventtosess_0; "AddEventToSession failed - %d"
0x18005ebea  mov     r9d, 0E48h
0x18005ebf0  lea     r8, aCreateclustern_5; "CreateClusterNotifyPortV2"
0x18005ebf7  mov     [rsp+0D0h+var_B0], rax
0x18005ebfc  lea     ecx, [rdx-5]
0x18005ebff  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005ec04  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18005ec08  jnz     short loc_18005EC15
0x18005ec0a  lea     edx, [rsi+2]; int
0x18005ec0d  mov     rcx, rbx; hMem
0x18005ec10  call    ?DestroyNotifyCommon@@YAXPEAU_CNOTIFY@@H@Z; DestroyNotifyCommon(_CNOTIFY *,int)
0x18005ec15  mov     ecx, r12d
0x18005ec18  jmp     loc_18005EA7C
0x18005ec1d  mov     rcx, r15; lpCriticalSection
0x18005ec20  call    cs:__imp_LeaveCriticalSection
0x18005ec26  mov     rcx, r14; lpCriticalSection
0x18005ec29  call    cs:__imp_LeaveCriticalSection
0x18005ec2f  mov     edx, 7
0x18005ec34  mov     [rsp+0D0h+var_A8], rbx
0x18005ec39  lea     rax, aReturningNotif; "Returning Notify handle 0x%p"
0x18005ec40  mov     r9d, 0E55h
0x18005ec46  lea     r8, aCreateclustern_5; "CreateClusterNotifyPortV2"
0x18005ec4d  mov     [rsp+0D0h+var_B0], rax
0x18005ec52  lea     ecx, [rdx-3]
0x18005ec55  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x18005ec5a  mov     rax, rbx
0x18005ec5d  mov     rcx, [rbp+4Fh+var_48]
0x18005ec61  xor     rcx, rsp; StackCookie
0x18005ec64  call    __security_check_cookie
0x18005ec69  lea     r11, [rsp+0D0h+var_30]
0x18005ec71  mov     rbx, [r11+58h]
0x18005ec75  movaps  xmm6, xmmword ptr [r11-10h]
0x18005ec7a  mov     rsp, r11
0x18005ec7d  pop     r15
0x18005ec7f  pop     r14
0x18005ec81  pop     r13
0x18005ec83  pop     r12
0x18005ec85  pop     rdi
0x18005ec86  pop     rsi
0x18005ec87  pop     rbp
0x18005ec88  retn
```
