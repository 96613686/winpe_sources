# CDtcConfig::SetDefaultDtcClusterResource(ushort const *,ushort const *)

- ea: `0x180049cb0`
- end: `0x180049e5f`
- name: `?SetDefaultDtcClusterResource@CDtcConfig@@UEAAJPEBG0@Z`
- size: `431`
- prototype: `__int64 __fastcall(CDtcConfig *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x18000f8d0`
- `0x180049cb0`
- `0x180081dd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049e04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049e04`
- `MTXCLU!MtxCluGetDTCVirtualServerNameW` at `0x180049d98`
- `MTXCLU!MtxCluGetDTCVirtualServerNameW` at `0x180049d98`
- `MTXCLU!MtxCluGetResourceIdStringFromName` at `0x180049d6a`
- `MTXCLU!MtxCluGetResourceIdStringFromName` at `0x180049d6a`
- `MTXCLU!MtxCluSetDefaultClusterResource` at `0x180049dc3`
- `MTXCLU!MtxCluSetDefaultClusterResource` at `0x180049dc3`

## string_xrefs

- `0x180049cec`: `com\complus\dtc\dtc\msdtcprx\src\dtcconfig.cpp`
- `0x180049ce2`: `CDtcConfig::SetDefaultDtcClusterResource`

## pseudocode

```c
__int64 __fastcall CDtcConfig::SetDefaultDtcClusterResource(
        CDtcConfig *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int ResourceIdStringFromName; // ebx
  const wchar_t *v6; // rax
  __int64 v7; // r9
  const wchar_t *v8; // rax
  __int64 v9; // r9
  __int64 v11; // [rsp+28h] [rbp-270h]
  bool v12; // [rsp+40h] [rbp-258h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-250h] BYREF
  _BYTE v14[528]; // [rsp+50h] [rbp-248h] BYREF

  pv = 0;
  if ( a3 )
  {
    v12 = 0;
    MtxCluIsClusterPresentNonAdmin(0, &v12);
    if ( v12 )
    {
      ResourceIdStringFromName = MtxCluGetResourceIdStringFromName(a2, a3, &pv);
      if ( ResourceIdStringFromName >= 0 )
      {
        ResourceIdStringFromName = MtxCluGetDTCVirtualServerNameW(a2, pv, v14, 261);
        if ( ResourceIdStringFromName < 0 )
        {
          v6 = L"MtxCluGetDTCVirtualServerNameW failed";
          v7 = 632;
          goto LABEL_3;
        }
        ResourceIdStringFromName = MtxCluSetDefaultClusterResource(a2, pv, v14);
        if ( ResourceIdStringFromName >= 0 )
          goto LABEL_13;
        v8 = L"Failed to set default cluster resource to %s";
        v9 = 645;
      }
      else
      {
        v8 = L"MtxCluGetResourceIdStringFromName Failed for '%s'";
        v9 = 625;
      }
      LODWORD(v11) = ResourceIdStringFromName;
      TraceStringInline(
        15,
        1,
        L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
        v9,
        L"CDtcConfig::SetDefaultDtcClusterResource",
        v11,
        v8,
        a3);
      goto LABEL_13;
    }
    ResourceIdStringFromName = -2147019860;
    v6 = L"Not a cluster node.";
    v7 = 615;
  }
  else
  {
    ResourceIdStringFromName = -2147024809;
    v6 = L"Invalid arguments";
    v7 = 608;
  }
LABEL_3:
  LODWORD(v11) = ResourceIdStringFromName;
  TraceStringInline(
    15,
    1,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
    v7,
    L"CDtcConfig::SetDefaultDtcClusterResource",
    v11,
    v6);
LABEL_13:
  CoTaskMemFree(pv);
  LODWORD(v11) = ResourceIdStringFromName;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
    651,
    L"CDtcConfig::SetDefaultDtcClusterResource",
    v11,
    L"Out");
  return (unsigned int)ResourceIdStringFromName;
}

```

## disassembly

```asm
0x180049cb0  mov     [rsp+arg_0], rbx
0x180049cb5  push    rsi
0x180049cb6  push    rdi
0x180049cb7  push    r12
0x180049cb9  push    r14
0x180049cbb  push    r15
0x180049cbd  sub     rsp, 270h
0x180049cc4  mov     rax, cs:__security_cookie
0x180049ccb  xor     rax, rsp
0x180049cce  mov     [rsp+298h+var_38], rax
0x180049cd6  mov     [rsp+298h+pv], 0
0x180049cdf  mov     rdi, r8
0x180049ce2  lea     r12, aCdtcconfigSetd; "CDtcConfig::SetDefaultDtcClusterResourc"...
0x180049ce9  mov     rsi, rdx
0x180049cec  lea     r14, aComComplusDtcD_19; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x180049cf3  mov     r15d, 0Fh
0x180049cf9  test    r8, r8
0x180049cfc  jnz     short loc_180049D33
0x180049cfe  mov     ebx, 80070057h
0x180049d03  lea     rax, aInvalidArgumen_9; "Invalid arguments"
0x180049d0a  mov     r9d, 260h
0x180049d10  mov     [rsp+298h+var_268], rax
0x180049d15  mov     r8, r14
0x180049d18  mov     dword ptr [rsp+298h+var_270], ebx
0x180049d1c  mov     edx, 1
0x180049d21  mov     ecx, r15d
0x180049d24  mov     [rsp+298h+var_278], r12
0x180049d29  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180049d2e  jmp     loc_180049DFF
0x180049d33  lea     rdx, [rsp+298h+var_258]; bool *
0x180049d38  mov     [rsp+298h+var_258], 0
0x180049d3d  xor     ecx, ecx; unsigned __int16 *
0x180049d3f  call    ?MtxCluIsClusterPresentNonAdmin@@YAJPEBGAEA_N@Z; MtxCluIsClusterPresentNonAdmin(ushort const *,bool &)
0x180049d44  cmp     [rsp+298h+var_258], 0
0x180049d49  jnz     short loc_180049D5F
0x180049d4b  mov     ebx, 800713ACh
0x180049d50  lea     rax, aNotAClusterNod; "Not a cluster node."
0x180049d57  mov     r9d, 267h
0x180049d5d  jmp     short loc_180049D10
0x180049d5f  lea     r8, [rsp+298h+pv]
0x180049d64  mov     rdx, rdi
0x180049d67  mov     rcx, rsi
0x180049d6a  call    cs:__imp_MtxCluGetResourceIdStringFromName
0x180049d70  mov     ebx, eax
0x180049d72  test    eax, eax
0x180049d74  jns     short loc_180049D85
0x180049d76  lea     rax, aMtxclugetresou_0; "MtxCluGetResourceIdStringFromName Faile"...
0x180049d7d  mov     r9d, 271h
0x180049d83  jmp     short loc_180049DDC
0x180049d85  mov     rdx, [rsp+298h+pv]
0x180049d8a  lea     r8, [rsp+298h+var_248]
0x180049d8f  mov     r9d, 105h
0x180049d95  mov     rcx, rsi
0x180049d98  call    cs:__imp_MtxCluGetDTCVirtualServerNameW
0x180049d9e  mov     ebx, eax
0x180049da0  test    eax, eax
0x180049da2  jns     short loc_180049DB6
0x180049da4  lea     rax, aMtxclugetdtcvi; "MtxCluGetDTCVirtualServerNameW failed"
0x180049dab  mov     r9d, 278h
0x180049db1  jmp     loc_180049D10
0x180049db6  mov     rdx, [rsp+298h+pv]
0x180049dbb  lea     r8, [rsp+298h+var_248]
0x180049dc0  mov     rcx, rsi
0x180049dc3  call    cs:__imp_MtxCluSetDefaultClusterResource
0x180049dc9  mov     ebx, eax
0x180049dcb  test    eax, eax
0x180049dcd  jns     short loc_180049DFF
0x180049dcf  lea     rax, aFailedToSetDef; "Failed to set default cluster resource "...
0x180049dd6  mov     r9d, 285h
0x180049ddc  mov     [rsp+298h+var_260], rdi
0x180049de1  mov     r8, r14
0x180049de4  mov     [rsp+298h+var_268], rax
0x180049de9  mov     edx, 1
0x180049dee  mov     dword ptr [rsp+298h+var_270], ebx
0x180049df2  mov     ecx, r15d
0x180049df5  mov     [rsp+298h+var_278], r12
0x180049dfa  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180049dff  mov     rcx, [rsp+298h+pv]; pv
0x180049e04  call    cs:__imp_CoTaskMemFree
0x180049e0a  lea     rax, aOut; "Out"
0x180049e11  mov     r9d, 28Bh
0x180049e17  mov     [rsp+298h+var_268], rax
0x180049e1c  mov     r8, r14
0x180049e1f  mov     dword ptr [rsp+298h+var_270], ebx
0x180049e23  mov     edx, 6
0x180049e28  mov     ecx, r15d
0x180049e2b  mov     [rsp+298h+var_278], r12
0x180049e30  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180049e35  mov     eax, ebx
0x180049e37  mov     rcx, [rsp+298h+var_38]
0x180049e3f  xor     rcx, rsp; StackCookie
0x180049e42  call    __security_check_cookie
0x180049e47  mov     rbx, [rsp+298h+arg_0]
0x180049e4f  add     rsp, 270h
0x180049e56  pop     r15
0x180049e58  pop     r14
0x180049e5a  pop     r12
0x180049e5c  pop     rdi
0x180049e5d  pop     rsi
0x180049e5e  retn
```
