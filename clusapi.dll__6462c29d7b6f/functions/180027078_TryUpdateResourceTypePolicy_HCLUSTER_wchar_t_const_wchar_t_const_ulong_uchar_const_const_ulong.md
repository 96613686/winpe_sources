# TryUpdateResourceTypePolicy(_HCLUSTER *,wchar_t const *,wchar_t const *,ulong,uchar const * const,ulong)

- ea: `0x180027078`
- end: `0x180027203`
- name: `?TryUpdateResourceTypePolicy@@YAKPEAU_HCLUSTER@@PEB_W1KQEBEK@Z`
- size: `395`
- prototype: `unsigned int __usercall@<eax>(HCLUSTER hCluster@<rcx>, const wchar_t *@<rdx>, LPCWSTR lpszValueName@<r8>, unsigned int@<r9d>, const unsigned __int8 *const, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002723c`
- `0x1800273ac`

## callees

- `0x180014638`
- `0x180027078`
- `0x180063cb0`
- `0x180063f44`
- `0x180064d10`
- `0x180064f20`
- `0x18006f910`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800270d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800270d0`

## string_xrefs

- `0x1800270e1`: `Failed to open registry key of the resource type %s. Error %d`
- `0x1800270f3`: `TryUpdateResourceTypePolicy`
- `0x180027168`: `TryUpdateResourceTypePolicy`
- `0x1800271d7`: `TryUpdateResourceTypePolicy`
- `0x1800271c5`: `Resource type %s property %s is already set.`
- `0x180027148`: `Failed to read value %s of the resource type %s. Error %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TryUpdateResourceTypePolicy(
        HCLUSTER hCluster,
        const wchar_t *a2,
        LPCWSTR lpszValueName,
        int a4,
        const unsigned __int8 *a5,
        unsigned int a6)
{
  HKEY v11; // rbx
  DWORD LastError; // edi
  LONG Value; // eax
  const wchar_t *v14; // rax
  __int64 v15; // r9

  if ( !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(
                           hCluster,
                           hCluster) )
    return 6;
  v11 = OpenClusterRelative(hCluster, L"ResourceTypes", a2, 3u);
  if ( (((unsigned __int64)v11 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    TraceMsg(
      2,
      0,
      L"TryUpdateResourceTypePolicy",
      7484,
      L"Failed to open registry key of the resource type %s. Error %d",
      a2,
      LastError);
    if ( (unsigned __int64)v11 - 1 > 0xFFFFFFFFFFFFFFFDuLL )
      return LastError;
    goto LABEL_5;
  }
  Value = ClusterRegQueryValue(v11, lpszValueName, 0, 0, 0);
  LastError = Value;
  if ( Value )
  {
    if ( Value == 2 )
    {
      LastError = ClusterRegSetValueEx((int)v11, (int)lpszValueName, a4, (int)a5, a6, 0);
      if ( !LastError )
        goto LABEL_5;
      v14 = L"Failed to set value %s of the resource type %s. Error %d";
      v15 = 7523;
    }
    else
    {
      v14 = L"Failed to read value %s of the resource type %s. Error %d";
      v15 = 7512;
    }
    TraceMsg(2, 0, L"TryUpdateResourceTypePolicy", v15, v14, lpszValueName, a2, LastError, v11);
LABEL_5:
    ClusterRegCloseKeyCommon(v11, 1);
    return LastError;
  }
  TraceMsg(
    4,
    0,
    L"TryUpdateResourceTypePolicy",
    7497,
    L"Resource type %s property %s is already set.",
    a2,
    lpszValueName);
  ClusterRegCloseKeyCommon(v11, 1);
  return 0;
}

```

## disassembly

```asm
0x180027078  push    rbx
0x18002707a  push    rbp
0x18002707b  push    rsi
0x18002707c  push    rdi
0x18002707d  push    r14
0x18002707f  sub     rsp, 50h
0x180027083  mov     r14d, r9d
0x180027086  mov     rsi, r8
0x180027089  mov     rbp, rdx
0x18002708c  mov     rbx, rcx
0x18002708f  mov     rdx, rcx
0x180027092  call    ??$Contains@PEAU_HCLUSTER@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCLUSTER@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(_HCLUSTER *)
0x180027097  test    al, al
0x180027099  jnz     short loc_1800270A5
0x18002709b  mov     eax, 6
0x1800270a0  jmp     loc_1800271F8
0x1800270a5  mov     r9d, 3; samDesired
0x1800270ab  mov     r8, rbp; wchar_t *
0x1800270ae  lea     rdx, aResourcetypes; "ResourceTypes"
0x1800270b5  mov     rcx, rbx; hCluster
0x1800270b8  call    ?OpenClusterRelative@@YAPEAUHKEY__@@PEAU_HCLUSTER@@PEB_W1K@Z; OpenClusterRelative(_HCLUSTER *,wchar_t const *,wchar_t const *,ulong)
0x1800270bd  mov     rbx, rax
0x1800270c0  mov     [rsp+78h+var_38], rax
0x1800270c5  inc     rax
0x1800270c8  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800270ce  jnz     short loc_180027123
0x1800270d0  call    cs:__imp_GetLastError
0x1800270d6  mov     edi, eax
0x1800270d8  mov     dword ptr [rsp+78h+var_48], eax
0x1800270dc  mov     [rsp+78h+var_50], rbp
0x1800270e1  lea     rax, aFailedToOpenRe_0; "Failed to open registry key of the reso"...
0x1800270e8  mov     [rsp+78h+lpcbData], rax
0x1800270ed  mov     r9d, 1D3Ch
0x1800270f3  lea     r8, aTryupdateresou; "TryUpdateResourceTypePolicy"
0x1800270fa  xor     edx, edx
0x1800270fc  lea     ecx, [rdx+2]
0x1800270ff  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180027104  nop
0x180027105  lea     rcx, [rbx-1]
0x180027109  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002710d  ja      short loc_18002711C
0x18002710f  mov     edx, 1; int
0x180027114  mov     rcx, rbx; HKEY
0x180027117  call    ?ClusterRegCloseKeyCommon@@YAJPEAUHKEY__@@H@Z; ClusterRegCloseKeyCommon(HKEY__ *,int)
0x18002711c  mov     eax, edi
0x18002711e  jmp     loc_1800271F8
0x180027123  mov     [rsp+78h+lpcbData], 0; lpcbData
0x18002712c  xor     r9d, r9d; lpData
0x18002712f  xor     r8d, r8d; lpdwValueType
0x180027132  mov     rdx, rsi; lpszValueName
0x180027135  mov     rcx, rbx; hKey
0x180027138  call    ClusterRegQueryValue
0x18002713d  mov     edi, eax
0x18002713f  test    eax, eax
0x180027141  jz      short loc_1800271BB
0x180027143  cmp     eax, 2
0x180027146  jz      short loc_18002717C
0x180027148  lea     rax, aFailedToReadVa; "Failed to read value %s of the resource"...
0x18002714f  mov     r9d, 1D58h
0x180027155  mov     [rsp+78h+var_40], edi
0x180027159  mov     [rsp+78h+var_48], rbp
0x18002715e  mov     [rsp+78h+var_50], rsi
0x180027163  mov     [rsp+78h+lpcbData], rax
0x180027168  lea     r8, aTryupdateresou; "TryUpdateResourceTypePolicy"
0x18002716f  xor     edx, edx
0x180027171  lea     ecx, [rdx+2]
0x180027174  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x180027179  nop
0x18002717a  jmp     short loc_18002710F
0x18002717c  mov     [rsp+78h+var_50], 0; wchar_t *
0x180027185  mov     eax, [rsp+78h+arg_28]
0x18002718c  mov     dword ptr [rsp+78h+lpcbData], eax; int
0x180027190  mov     r9, [rsp+78h+arg_20]; int
0x180027198  mov     r8d, r14d; int
0x18002719b  mov     rdx, rsi; int
0x18002719e  mov     rcx, rbx; int
0x1800271a1  call    ClusterRegSetValueEx
0x1800271a6  mov     edi, eax
0x1800271a8  test    eax, eax
0x1800271aa  jz      short loc_18002717A
0x1800271ac  lea     rax, aFailedToSetVal; "Failed to set value %s of the resource "...
0x1800271b3  mov     r9d, 1D63h
0x1800271b9  jmp     short loc_180027155
0x1800271bb  mov     [rsp+78h+var_48], rsi
0x1800271c0  mov     [rsp+78h+var_50], rbp
0x1800271c5  lea     rax, aResourceTypeSP; "Resource type %s property %s is already"...
0x1800271cc  mov     [rsp+78h+lpcbData], rax
0x1800271d1  mov     r9d, 1D49h
0x1800271d7  lea     r8, aTryupdateresou; "TryUpdateResourceTypePolicy"
0x1800271de  xor     edx, edx
0x1800271e0  lea     ecx, [rdx+4]
0x1800271e3  call    ?TraceMsg@@YAXEW4_TraceType@Trace@@PEA_WK1ZZ; TraceMsg(uchar,Trace::_TraceType,wchar_t *,ulong,wchar_t *,...)
0x1800271e8  nop
0x1800271e9  mov     edx, 1; int
0x1800271ee  mov     rcx, rbx; HKEY
0x1800271f1  call    ?ClusterRegCloseKeyCommon@@YAJPEAUHKEY__@@H@Z; ClusterRegCloseKeyCommon(HKEY__ *,int)
0x1800271f6  xor     eax, eax
0x1800271f8  add     rsp, 50h
0x1800271fc  pop     r14
0x1800271fe  pop     rdi
0x1800271ff  pop     rsi
0x180027200  pop     rbp
0x180027201  pop     rbx
0x180027202  retn
```
