# CreateNetworkName

- ea: `0x180037824`
- end: `0x18003798b`
- name: `CreateNetworkName`
- size: `359`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x18003359c`
- `0x180041f00`

## callees

- `0x180014638`
- `0x180014698`
- `0x180037824`
- `0x18003cbdc`
- `0x18006c010`
- `0x18006c5e0`
- `0x18006ca50`
- `0x18006f910`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800378fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800378fc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037968`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037978`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037968`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037978`

## string_xrefs

- `0x18003787c`: `clusapi!CreateNetworkName`
- `0x18003791e`: `CreateNetworkName`
- `0x180037908`: `Failed to create NetName resource %ws. Error %d.`
- `0x18003794d`: `clusapi!CreateNetworkName - modify networkname failed`

## pseudocode

```c
struct _HRESOURCE *__fastcall CreateNetworkName(
        PhaseManager *a1,
        struct _HCLUSTER *a2,
        __int64 a3,
        const WCHAR *a4,
        const wchar_t *a5,
        wchar_t *a6,
        struct CreateClusterADState *a7,
        int a8,
        int a9,
        int a10)
{
  __int64 v14; // rcx
  const wchar_t *v15; // r8
  struct _HRESOURCE *ClusterResource; // rax
  struct _HRESOURCE *v17; // rbx
  DWORD v18; // esi
  int v19; // r9d
  wchar_t *v20; // r11
  DWORD LastError; // eax
  __int64 v23; // [rsp+30h] [rbp-48h]

  if ( (unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HGROUP *>(
                          a1,
                          a3)
    && (unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(
                          v14,
                          a2) )
  {
    v15 = L"Network Name";
    if ( a9 )
      v15 = L"Distributed Network Name";
    ClusterResource = (struct _HRESOURCE *)CreateClusterResourceEx(a3, a4, v15, 0, L"clusapi!CreateNetworkName");
    v17 = ClusterResource;
    if ( ClusterResource )
    {
      v18 = ModifyNetworkName(a1, a2, a4, a5, a6, a7, a8, ClusterResource, a9, a10);
      if ( !v18 )
      {
LABEL_15:
        SetLastError(v18);
        return v17;
      }
      v19 = 6793;
      v20 = L"Failed to modify NetName resource %ws. Error %d.";
    }
    else
    {
      LastError = GetLastError();
      v19 = 6800;
      v20 = L"Failed to create NetName resource %ws. Error %d.";
      v18 = LastError;
    }
    if ( !a4 )
      a4 = &base;
    LODWORD(v23) = v18;
    TraceMsg(2u, 0, (__int64)L"CreateNetworkName", v19, v20, a4, v23);
    if ( v18 )
    {
      if ( v17 )
      {
        DeleteClusterResourceEx(v17, L"clusapi!CreateNetworkName - modify networkname failed");
        CloseClusterResource(v17);
      }
      v17 = 0;
    }
    goto LABEL_15;
  }
  SetLastError(6u);
  return 0;
}

```

## disassembly

```asm
0x180037824  push    rbx
0x180037826  push    rbp
0x180037827  push    rsi
0x180037828  push    rdi
0x180037829  push    r14
0x18003782b  sub     rsp, 50h
0x18003782f  mov     rsi, rdx
0x180037832  mov     rdi, r9
0x180037835  mov     rdx, r8
0x180037838  mov     rbx, r8
0x18003783b  mov     r14, rcx
0x18003783e  call    ??$Contains@PEAU_HGROUP@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HGROUP@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HGROUP *>(_HGROUP *)
0x180037843  test    al, al
0x180037845  jz      loc_180037973
0x18003784b  mov     rdx, rsi
0x18003784e  call    ??$Contains@PEAU_HCLUSTER@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCLUSTER@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(_HCLUSTER *)
0x180037853  test    al, al
0x180037855  jz      loc_180037973
0x18003785b  mov     ebp, [rsp+78h+arg_40]
0x180037862  lea     rax, aDistributedNet; "Distributed Network Name"
0x180037869  test    ebp, ebp
0x18003786b  lea     r8, aNetworkName; "Network Name"
0x180037872  mov     rdx, rdi
0x180037875  mov     rcx, rbx
0x180037878  cmovnz  r8, rax
0x18003787c  lea     rax, aClusapiCreaten_2; "clusapi!CreateNetworkName"
0x180037883  xor     r9d, r9d
0x180037886  mov     [rsp+78h+var_58], rax
0x18003788b  call    CreateClusterResourceEx
0x180037890  mov     rbx, rax
0x180037893  test    rax, rax
0x180037896  jz      short loc_1800378FC
0x180037898  mov     eax, [rsp+78h+arg_48]
0x18003789f  mov     r8, rdi
0x1800378a2  mov     r9, [rsp+78h+arg_20]
0x1800378aa  mov     rdx, rsi
0x1800378ad  mov     [rsp+78h+var_30], eax
0x1800378b1  mov     rcx, r14
0x1800378b4  mov     eax, [rsp+78h+arg_38]
0x1800378bb  mov     [rsp+78h+var_38], ebp
0x1800378bf  mov     [rsp+78h+var_40], rbx
0x1800378c4  mov     dword ptr [rsp+78h+var_48], eax
0x1800378c8  mov     rax, [rsp+78h+arg_30]
0x1800378d0  mov     [rsp+78h+var_50], rax
0x1800378d5  mov     rax, [rsp+78h+arg_28]
0x1800378dd  mov     [rsp+78h+var_58], rax
0x1800378e2  call    ModifyNetworkName
0x1800378e7  mov     esi, eax
0x1800378e9  test    eax, eax
0x1800378eb  jz      short loc_180037966
0x1800378ed  mov     r9d, 1A89h
0x1800378f3  lea     r11, aFailedToModify_0; "Failed to modify NetName resource %ws. "...
0x1800378fa  jmp     short loc_180037911
0x1800378fc  call    cs:__imp_GetLastError
0x180037902  mov     r9d, 1A90h
0x180037908  lea     r11, aFailedToCreate_17; "Failed to create NetName resource %ws. "...
0x18003790f  mov     esi, eax
0x180037911  xor     r10d, r10d
0x180037914  lea     rdx, base
0x18003791b  test    rdi, rdi
0x18003791e  lea     r8, aCreatenetworkn; "CreateNetworkName"
0x180037925  mov     cl, 2
0x180037927  cmovz   rdi, rdx
0x18003792b  mov     dword ptr [rsp+78h+var_48], esi
0x18003792f  mov     edx, r10d
0x180037932  mov     [rsp+78h+var_50], rdi
0x180037937  movzx   ecx, cl
0x18003793a  mov     [rsp+78h+var_58], r11
0x18003793f  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180037944  test    esi, esi
0x180037946  jz      short loc_180037966
0x180037948  test    rbx, rbx
0x18003794b  jz      short loc_180037964
0x18003794d  lea     rdx, aClusapiCreaten_1; "clusapi!CreateNetworkName - modify netw"...
0x180037954  mov     rcx, rbx
0x180037957  call    DeleteClusterResourceEx
0x18003795c  mov     rcx, rbx; hResource
0x18003795f  call    CloseClusterResource
0x180037964  xor     ebx, ebx
0x180037966  mov     ecx, esi; dwErrCode
0x180037968  call    cs:__imp_SetLastError
0x18003796e  mov     rax, rbx
0x180037971  jmp     short loc_180037980
0x180037973  mov     ecx, 6; dwErrCode
0x180037978  call    cs:__imp_SetLastError
0x18003797e  xor     eax, eax
0x180037980  add     rsp, 50h
0x180037984  pop     r14
0x180037986  pop     rdi
0x180037987  pop     rsi
0x180037988  pop     rbp
0x180037989  pop     rbx
0x18003798a  retn
```
