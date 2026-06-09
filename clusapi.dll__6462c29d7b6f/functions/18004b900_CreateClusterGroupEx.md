# CreateClusterGroupEx

- ea: `0x18004b900`
- end: `0x18004bb1b`
- name: `CreateClusterGroupEx`
- size: `539`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18003359c`
- `0x180041f00`
- `0x18004b8f0`
- `0x180087540`

## callees

- `0x18001236c`
- `0x180014638`
- `0x180025478`
- `0x180047ab4`
- `0x18004aab0`
- `0x18004aca4`
- `0x18004b238`
- `0x18004b900`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004bac9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004bac9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ba9a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004ba9a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004bb06`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004bb06`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b9c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b9e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b9f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004baf4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bafd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b9c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b9e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004b9f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004baf4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004bafd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004b96f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004b9b6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004b96f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18004b9b6`
- `api-ms-win-security-base-l1-1-0!AreAnyAccessesGranted` at `0x18004b956`
- `api-ms-win-security-base-l1-1-0!AreAnyAccessesGranted` at `0x18004b956`

## string_xrefs

- `0x18004ba62`: `ApiCreateGroup`
- `0x18004ba44`: `ApiCreateGroupEx`

## pseudocode

```c
_DWORD *__fastcall CreateClusterGroupEx(__int64 a1, const wchar_t *a2, DWORD *a3)
{
  DWORD v6; // ecx
  _DWORD *v7; // rbx
  __int64 v8; // rax
  unsigned __int64 v9; // rsi
  wchar_t *v10; // rax
  int v11; // esi
  __int64 v12; // rax
  struct _RTL_CRITICAL_SECTION *v13; // rsi
  __int64 *v14; // rdi
  __int64 v15; // rcx
  __int64 v16; // rcx
  DWORD v17; // edi
  unsigned int v19; // [rsp+20h] [rbp-38h] BYREF
  _QWORD v20[3]; // [rsp+28h] [rbp-30h] BYREF
  DWORD *v21; // [rsp+40h] [rbp-18h]
  DWORD *p_dwErrCode; // [rsp+48h] [rbp-10h]
  DWORD dwErrCode; // [rsp+A8h] [rbp+50h] BYREF

  if ( !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(
                           a1,
                           a1) )
  {
    v6 = 6;
    goto LABEL_28;
  }
  dwErrCode = 0;
  v19 = 0;
  if ( !a2 )
  {
    v6 = 123;
    goto LABEL_28;
  }
  if ( !AreAnyAccessesGranted(*(_DWORD *)(a1 + 320), 0x10000003u) )
  {
    v6 = 5;
    goto LABEL_28;
  }
  v7 = LocalAlloc(0, 0x48u);
  if ( !v7 )
  {
LABEL_8:
    v6 = 8;
    goto LABEL_28;
  }
  dwErrCode = MylstrlenW(a2, 0x7FFFFFFFu, &v19);
  if ( dwErrCode )
  {
LABEL_27:
    LocalFree(v7);
    v6 = dwErrCode;
    goto LABEL_28;
  }
  v8 = v19 + 1;
  *v7 = 1128747600;
  v9 = (unsigned int)v8;
  v10 = (wchar_t *)LocalAlloc(0, 2 * v8);
  *((_QWORD *)v7 + 6) = v10;
  if ( !v10 )
  {
    LocalFree(v7);
    goto LABEL_8;
  }
  v11 = StringCchCopyW(v10, v9, a2);
  if ( v11 < 0 )
  {
    LocalFree(*((HLOCAL *)v7 + 6));
    LocalFree(v7);
    if ( (v11 & 0x1FFF0000) != 0x70000 || (v6 = (unsigned __int16)v11, !(_WORD)v11) )
      v6 = v11;
    goto LABEL_28;
  }
  *((_QWORD *)v7 + 5) = a1;
  *((_QWORD *)v7 + 4) = v7 + 6;
  *((_QWORD *)v7 + 3) = v7 + 6;
  v20[1] = a1 + 40;
  v20[2] = a2;
  if ( a3 )
  {
    v21 = a3;
    v20[0] = "ApiCreateGroupEx";
    p_dwErrCode = &dwErrCode;
    v12 = ReconnectOnNull<CreateGroupExFunctor>(v20, &dwErrCode, a1);
  }
  else
  {
    v21 = &dwErrCode;
    v20[0] = "ApiCreateGroup";
    v12 = ReconnectOnNull<CreateGroupFunctor>(v20, &dwErrCode, a1);
  }
  *((_QWORD *)v7 + 7) = v12;
  v7[16] = 0x10000000;
  if ( !v12 || dwErrCode )
  {
    LocalFree(*((HLOCAL *)v7 + 6));
    goto LABEL_27;
  }
  v13 = (struct _RTL_CRITICAL_SECTION *)(a1 + 232);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 232));
  v14 = (__int64 *)(a1 + 88);
  v15 = *v14;
  if ( *(__int64 **)(*v14 + 8) != v14 )
    __fastfail(3u);
  *((_QWORD *)v7 + 1) = v15;
  *((_QWORD *)v7 + 2) = v14;
  *(_QWORD *)(v15 + 8) = v7 + 2;
  *v14 = (__int64)(v7 + 2);
  LeaveCriticalSection(v13);
  v17 = HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Insert<_HGROUP *>(
          v16,
          v7);
  if ( !v17 )
    return v7;
  CloseClusterGroupCommon(v7, 0);
  v6 = v17;
LABEL_28:
  SetLastError(v6);
  return 0;
}

```

## disassembly

```asm
0x18004b900  push    rbp
0x18004b902  push    rbx
0x18004b903  push    rsi
0x18004b904  push    rdi
0x18004b905  push    r14
0x18004b907  push    r15
0x18004b909  mov     rbp, rsp
0x18004b90c  sub     rsp, 58h
0x18004b910  mov     r14, rdx
0x18004b913  mov     r15, r8
0x18004b916  mov     rdx, rcx
0x18004b919  mov     rdi, rcx
0x18004b91c  call    ??$Contains@PEAU_HCLUSTER@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCLUSTER@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(_HCLUSTER *)
0x18004b921  test    al, al
0x18004b923  jnz     short loc_18004B92F
0x18004b925  mov     ecx, 6
0x18004b92a  jmp     loc_18004BB06
0x18004b92f  mov     [rbp+dwErrCode], 0
0x18004b936  mov     [rbp+var_38], 0
0x18004b93d  test    r14, r14
0x18004b940  jnz     short loc_18004B94B
0x18004b942  lea     ecx, [r14+7Bh]
0x18004b946  jmp     loc_18004BB06
0x18004b94b  mov     ecx, [rdi+140h]; GrantedAccess
0x18004b951  mov     edx, 10000003h; DesiredAccess
0x18004b956  call    cs:__imp_AreAnyAccessesGranted
0x18004b95c  test    eax, eax
0x18004b95e  jnz     short loc_18004B968
0x18004b960  lea     ecx, [rax+5]
0x18004b963  jmp     loc_18004BB06
0x18004b968  mov     edx, 48h ; 'H'; uBytes
0x18004b96d  xor     ecx, ecx; uFlags
0x18004b96f  call    cs:__imp_LocalAlloc
0x18004b975  mov     rbx, rax
0x18004b978  test    rax, rax
0x18004b97b  jnz     short loc_18004B987
0x18004b97d  mov     ecx, 8
0x18004b982  jmp     loc_18004BB06
0x18004b987  lea     r8, [rbp+var_38]; unsigned int *
0x18004b98b  mov     edx, 7FFFFFFFh; unsigned int
0x18004b990  mov     rcx, r14; wchar_t *
0x18004b993  call    ?MylstrlenW@@YAKPEB_WKPEAK@Z; MylstrlenW(wchar_t const *,ulong,ulong *)
0x18004b998  mov     [rbp+dwErrCode], eax
0x18004b99b  test    eax, eax
0x18004b99d  jnz     loc_18004BAFA
0x18004b9a3  mov     eax, [rbp+var_38]
0x18004b9a6  xor     ecx, ecx; uFlags
0x18004b9a8  inc     eax
0x18004b9aa  mov     dword ptr [rbx], 43475250h
0x18004b9b0  mov     esi, eax
0x18004b9b2  lea     rdx, [rax+rax]; uBytes
0x18004b9b6  call    cs:__imp_LocalAlloc
0x18004b9bc  mov     [rbx+30h], rax
0x18004b9c0  test    rax, rax
0x18004b9c3  jnz     short loc_18004B9D0
0x18004b9c5  mov     rcx, rbx; hMem
0x18004b9c8  call    cs:__imp_LocalFree
0x18004b9ce  jmp     short loc_18004B97D
0x18004b9d0  mov     r8, r14; wchar_t *
0x18004b9d3  mov     rdx, rsi; unsigned __int64
0x18004b9d6  mov     rcx, rax; wchar_t *
0x18004b9d9  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18004b9de  mov     esi, eax
0x18004b9e0  test    eax, eax
0x18004b9e2  jns     short loc_18004BA19
0x18004b9e4  mov     rcx, [rbx+30h]; hMem
0x18004b9e8  call    cs:__imp_LocalFree
0x18004b9ee  mov     rcx, rbx; hMem
0x18004b9f1  call    cs:__imp_LocalFree
0x18004b9f7  mov     ecx, esi
0x18004b9f9  and     ecx, 1FFF0000h
0x18004b9ff  cmp     ecx, 70000h
0x18004ba05  jnz     short loc_18004BA12
0x18004ba07  movzx   ecx, si
0x18004ba0a  test    ecx, ecx
0x18004ba0c  jnz     loc_18004BB06
0x18004ba12  mov     ecx, esi
0x18004ba14  jmp     loc_18004BB06
0x18004ba19  mov     [rbx+28h], rdi
0x18004ba1d  lea     rax, [rbx+18h]
0x18004ba21  mov     [rax+8], rax
0x18004ba25  mov     r8, rdi
0x18004ba28  mov     [rax], rax
0x18004ba2b  lea     rax, [rdi+28h]
0x18004ba2f  mov     [rbp+var_28], rax
0x18004ba33  lea     rax, [rbp+dwErrCode]
0x18004ba37  mov     [rbp+var_20], r14
0x18004ba3b  lea     rdx, [rbp+dwErrCode]
0x18004ba3f  test    r15, r15
0x18004ba42  jz      short loc_18004BA62
0x18004ba44  lea     rcx, aApicreategroup; "ApiCreateGroupEx"
0x18004ba4b  mov     [rbp+var_18], r15
0x18004ba4f  mov     [rbp+var_30], rcx
0x18004ba53  lea     rcx, [rbp+var_30]
0x18004ba57  mov     [rbp+var_10], rax
0x18004ba5b  call    ??$ReconnectOnNull@VCreateGroupExFunctor@@@@YAPEAXAEBVCreateGroupExFunctor@@PEAKPEAU_CLUSTER@@@Z; ReconnectOnNull<CreateGroupExFunctor>(CreateGroupExFunctor const &,ulong *,_CLUSTER *)
0x18004ba60  jmp     short loc_18004BA7A
0x18004ba62  lea     rcx, aApicreategroup_1; "ApiCreateGroup"
0x18004ba69  mov     [rbp+var_18], rax
0x18004ba6d  mov     [rbp+var_30], rcx
0x18004ba71  lea     rcx, [rbp+var_30]
0x18004ba75  call    ??$ReconnectOnNull@VCreateGroupFunctor@@@@YAPEAXAEBVCreateGroupFunctor@@PEAKPEAU_CLUSTER@@@Z; ReconnectOnNull<CreateGroupFunctor>(CreateGroupFunctor const &,ulong *,_CLUSTER *)
0x18004ba7a  mov     [rbx+38h], rax
0x18004ba7e  mov     dword ptr [rbx+40h], 10000000h
0x18004ba85  test    rax, rax
0x18004ba88  jz      short loc_18004BAF0
0x18004ba8a  cmp     [rbp+dwErrCode], 0
0x18004ba8e  jnz     short loc_18004BAF0
0x18004ba90  lea     rsi, [rdi+0E8h]
0x18004ba97  mov     rcx, rsi; lpCriticalSection
0x18004ba9a  call    cs:__imp_EnterCriticalSection
0x18004baa0  add     rdi, 58h ; 'X'
0x18004baa4  mov     rcx, [rdi]
0x18004baa7  cmp     [rcx+8], rdi
0x18004baab  jz      short loc_18004BAB4
0x18004baad  mov     ecx, 3
0x18004bab2  int     29h; Win8: RtlFailFast(ecx)
0x18004bab4  lea     rax, [rbx+8]
0x18004bab8  mov     [rax], rcx
0x18004babb  mov     [rax+8], rdi
0x18004babf  mov     [rcx+8], rax
0x18004bac3  mov     rcx, rsi; lpCriticalSection
0x18004bac6  mov     [rdi], rax
0x18004bac9  call    cs:__imp_LeaveCriticalSection
0x18004bacf  mov     rdx, rbx
0x18004bad2  call    ??$Insert@PEAU_HGROUP@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAAKPEAU_HGROUP@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Insert<_HGROUP *>(_HGROUP *)
0x18004bad7  mov     edi, eax
0x18004bad9  test    eax, eax
0x18004badb  jz      short loc_18004BAEB
0x18004badd  xor     edx, edx; int
0x18004badf  mov     rcx, rbx; hMem
0x18004bae2  call    ?CloseClusterGroupCommon@@YAHPEAU_HGROUP@@H@Z; CloseClusterGroupCommon(_HGROUP *,int)
0x18004bae7  mov     ecx, edi
0x18004bae9  jmp     short loc_18004BB06
0x18004baeb  mov     rax, rbx
0x18004baee  jmp     short loc_18004BB0E
0x18004baf0  mov     rcx, [rbx+30h]; hMem
0x18004baf4  call    cs:__imp_LocalFree
0x18004bafa  mov     rcx, rbx; hMem
0x18004bafd  call    cs:__imp_LocalFree
0x18004bb03  mov     ecx, [rbp+dwErrCode]; dwErrCode
0x18004bb06  call    cs:__imp_SetLastError
0x18004bb0c  xor     eax, eax
0x18004bb0e  add     rsp, 58h
0x18004bb12  pop     r15
0x18004bb14  pop     r14
0x18004bb16  pop     rdi
0x18004bb17  pop     rsi
0x18004bb18  pop     rbx
0x18004bb19  pop     rbp
0x18004bb1a  retn
```
