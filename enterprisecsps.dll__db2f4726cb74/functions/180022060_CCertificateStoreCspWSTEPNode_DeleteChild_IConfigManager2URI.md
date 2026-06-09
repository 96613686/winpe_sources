# CCertificateStoreCspWSTEPNode::DeleteChild(IConfigManager2URI *)

- ea: `0x180022060`
- end: `0x1800222b2`
- name: `?DeleteChild@CCertificateStoreCspWSTEPNode@@UEAAJPEAUIConfigManager2URI@@@Z`
- size: `594`
- prototype: `__int64 __fastcall(CCertificateStoreCspWSTEPNode *__hidden this, struct IConfigManager2URI *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18001a114`
- `0x18002201c`
- `0x180022060`
- `0x180036b00`
- `0x180107010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180022122`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180022175`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800221b2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002222e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180022122`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180022175`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800221b2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002222e`
- `OLEAUT32!__imp_SysFreeString` at `0x180022295`
- `OLEAUT32!__imp_SysFreeString` at `0x180022295`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022285`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022285`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800220cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800220cb`
- `DMCmnUtils!OmaDmRegistryDeleteValue` at `0x180022141`
- `DMCmnUtils!OmaDmRegistryDeleteValue` at `0x180022194`
- `DMCmnUtils!OmaDmRegistryDeleteValue` at `0x18002224d`
- `DMCmnUtils!OmaDmRegistryDeleteValue` at `0x180022141`
- `DMCmnUtils!OmaDmRegistryDeleteValue` at `0x180022194`
- `DMCmnUtils!OmaDmRegistryDeleteValue` at `0x18002224d`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x180022201`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x180022201`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800221d5`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800221d5`

## string_xrefs

- `0x180022189`: `DiscoveryServiceFullURL`

## pseudocode

```c
__int64 __fastcall CCertificateStoreCspWSTEPNode::DeleteChild(
        CCertificateStoreCspWSTEPNode *this,
        struct IConfigManager2URI *a2)
{
  struct CConfigServiceProvider2Impl *v3; // rcx
  const unsigned __int16 *EnrollmentId2; // rax
  const WCHAR *v6; // rax
  LSTATUS v7; // eax
  signed int v8; // edi
  HKEY v9; // rcx
  __int64 v11; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v12; // [rsp+60h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+30h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp+38h] BYREF

  v11 = 0;
  v3 = (struct CConfigServiceProvider2Impl *)*((_QWORD *)this + 16);
  v12 = 0;
  EnrollmentId2 = GetEnrollmentId2(v3);
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, EnrollmentId2);
  hKey = 0;
  v6 = (const WCHAR *)DMGetKnownRegPath(1);
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v6, 0, 0x2001Fu, &hKey);
  v8 = v7;
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
  if ( v8 >= 0 )
  {
    if ( *((_DWORD *)this + 11) != 14 )
      goto LABEL_19;
    v8 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, _QWORD, __int64 *))(*(_QWORD *)a2 + 88LL))(a2, 0, &v11);
    if ( v8 < 0 )
      goto LABEL_20;
    if ( !(unsigned int)_o__wcsicmp(v11, L"RenewPeriod") )
    {
      v8 = OmaDmRegistryDeleteValue(hKey, bstrString, L"RenewalPeriod");
      if ( v8 >= 0 )
        *(_DWORD *)(*((_QWORD *)this + 2) + 140LL) = 1;
      goto LABEL_20;
    }
    if ( !(unsigned int)_o__wcsicmp(v11, L"ServerURL") )
    {
      v8 = OmaDmRegistryDeleteValue(hKey, bstrString, L"DiscoveryServiceFullURL");
      goto LABEL_20;
    }
    if ( !(unsigned int)_o__wcsicmp(v11, L"ROBOSupport") )
    {
      if ( (int)OmaDmRegistryGetDWORD(hKey, bstrString, L"Federated", &v12) < 0 || v12 != -1 )
      {
        v8 = OmaDmRegistrySetDWORD(hKey, bstrString, L"RenewROBOSupport", 0);
        if ( v8 >= 0 )
          *(_DWORD *)(*((_QWORD *)this + 2) + 144LL) = 1;
        goto LABEL_20;
      }
LABEL_19:
      v8 = -2046820335;
      goto LABEL_20;
    }
    if ( (unsigned int)_o__wcsicmp(v11, L"RetryInterval") )
      goto LABEL_19;
    v8 = OmaDmRegistryDeleteValue(hKey, bstrString, L"RetryInterval");
    if ( v8 >= 0 )
      *(_DWORD *)(*((_QWORD *)this + 2) + 136LL) = 1;
  }
LABEL_20:
  v9 = hKey;
  hKey = 0;
  if ( v9 )
    RegCloseKey(v9);
  SysFreeString(bstrString);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180022060  mov     [rsp-18h+arg_8], rsi
0x180022065  push    rbp
0x180022066  push    rdi
0x180022067  push    r14
0x180022069  mov     rbp, rsp
0x18002206c  sub     rsp, 40h
0x180022070  mov     rsi, rcx
0x180022073  mov     [rbp+var_10], 0
0x18002207b  mov     rcx, [rcx+80h]; struct CConfigServiceProvider2Impl *
0x180022082  mov     r14, rdx
0x180022085  mov     [rbp+arg_0], 0
0x18002208c  call    ?GetEnrollmentId2@@YAPEAGPEAVCConfigServiceProvider2Impl@@@Z; GetEnrollmentId2(CConfigServiceProvider2Impl *)
0x180022091  mov     rdx, rax; unsigned __int16 *
0x180022094  lea     rcx, [rbp+bstrString]; this
0x180022098  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x18002209d  mov     ecx, 1
0x1800220a2  mov     [rbp+hKey], 0
0x1800220aa  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x1800220af  lea     rcx, [rbp+hKey]
0x1800220b3  mov     r9d, 2001Fh; samDesired
0x1800220b9  mov     [rsp+40h+phkResult], rcx; phkResult
0x1800220be  xor     r8d, r8d; ulOptions
0x1800220c1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800220c8  mov     rdx, rax; lpSubKey
0x1800220cb  call    cs:__imp_RegOpenKeyExW
0x1800220d2  nop     dword ptr [rax+rax+00h]
0x1800220d7  mov     edi, eax
0x1800220d9  test    eax, eax
0x1800220db  jle     short loc_1800220E6
0x1800220dd  movzx   edi, ax
0x1800220e0  or      edi, 80070000h
0x1800220e6  test    edi, edi
0x1800220e8  js      loc_180022274
0x1800220ee  cmp     dword ptr [rsi+2Ch], 0Eh
0x1800220f2  jnz     loc_18002226F
0x1800220f8  mov     rax, [r14]
0x1800220fb  lea     r8, [rbp+var_10]
0x1800220ff  xor     edx, edx
0x180022101  mov     rcx, r14
0x180022104  mov     rax, [rax+58h]
0x180022108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002210d  mov     edi, eax
0x18002210f  test    eax, eax
0x180022111  js      loc_180022274
0x180022117  mov     rcx, [rbp+var_10]
0x18002211b  lea     rdx, aRenewperiod; "RenewPeriod"
0x180022122  call    cs:__imp__o__wcsicmp
0x180022129  nop     dword ptr [rax+rax+00h]
0x18002212e  test    eax, eax
0x180022130  jnz     short loc_18002216A
0x180022132  mov     rdx, [rbp+bstrString]
0x180022136  lea     r8, aRenewalperiod; "RenewalPeriod"
0x18002213d  mov     rcx, [rbp+hKey]
0x180022141  call    cs:__imp_?OmaDmRegistryDeleteValue@@YAJPEAUHKEY__@@PEBG1@Z; OmaDmRegistryDeleteValue(HKEY__ *,ushort const *,ushort const *)
0x180022148  nop     dword ptr [rax+rax+00h]
0x18002214d  mov     edi, eax
0x18002214f  test    eax, eax
0x180022151  js      loc_180022274
0x180022157  mov     rax, [rsi+10h]
0x18002215b  mov     dword ptr [rax+8Ch], 1
0x180022165  jmp     loc_180022274
0x18002216a  mov     rcx, [rbp+var_10]
0x18002216e  lea     rdx, aServerurl; "ServerURL"
0x180022175  call    cs:__imp__o__wcsicmp
0x18002217c  nop     dword ptr [rax+rax+00h]
0x180022181  test    eax, eax
0x180022183  jnz     short loc_1800221A7
0x180022185  mov     rdx, [rbp+bstrString]
0x180022189  lea     r8, aDiscoveryservi; "DiscoveryServiceFullURL"
0x180022190  mov     rcx, [rbp+hKey]
0x180022194  call    cs:__imp_?OmaDmRegistryDeleteValue@@YAJPEAUHKEY__@@PEBG1@Z; OmaDmRegistryDeleteValue(HKEY__ *,ushort const *,ushort const *)
0x18002219b  nop     dword ptr [rax+rax+00h]
0x1800221a0  mov     edi, eax
0x1800221a2  jmp     loc_180022274
0x1800221a7  mov     rcx, [rbp+var_10]
0x1800221ab  lea     rdx, aRobosupport; "ROBOSupport"
0x1800221b2  call    cs:__imp__o__wcsicmp
0x1800221b9  nop     dword ptr [rax+rax+00h]
0x1800221be  test    eax, eax
0x1800221c0  jnz     short loc_180022223
0x1800221c2  mov     rdx, [rbp+bstrString]
0x1800221c6  lea     r9, [rbp+arg_0]
0x1800221ca  mov     rcx, [rbp+hKey]
0x1800221ce  lea     r8, aFederated; "Federated"
0x1800221d5  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800221dc  nop     dword ptr [rax+rax+00h]
0x1800221e1  test    eax, eax
0x1800221e3  js      short loc_1800221EF
0x1800221e5  cmp     [rbp+arg_0], 0FFFFFFFFh
0x1800221e9  jz      loc_18002226F
0x1800221ef  mov     rdx, [rbp+bstrString]
0x1800221f3  lea     r8, aRenewrobosuppo; "RenewROBOSupport"
0x1800221fa  mov     rcx, [rbp+hKey]
0x1800221fe  xor     r9d, r9d
0x180022201  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180022208  nop     dword ptr [rax+rax+00h]
0x18002220d  mov     edi, eax
0x18002220f  test    eax, eax
0x180022211  js      short loc_180022274
0x180022213  mov     rax, [rsi+10h]
0x180022217  mov     dword ptr [rax+90h], 1
0x180022221  jmp     short loc_180022274
0x180022223  mov     rcx, [rbp+var_10]
0x180022227  lea     rdx, aRetryinterval; "RetryInterval"
0x18002222e  call    cs:__imp__o__wcsicmp
0x180022235  nop     dword ptr [rax+rax+00h]
0x18002223a  test    eax, eax
0x18002223c  jnz     short loc_18002226F
0x18002223e  mov     rdx, [rbp+bstrString]
0x180022242  lea     r8, aRetryinterval; "RetryInterval"
0x180022249  mov     rcx, [rbp+hKey]
0x18002224d  call    cs:__imp_?OmaDmRegistryDeleteValue@@YAJPEAUHKEY__@@PEBG1@Z; OmaDmRegistryDeleteValue(HKEY__ *,ushort const *,ushort const *)
0x180022254  nop     dword ptr [rax+rax+00h]
0x180022259  mov     edi, eax
0x18002225b  test    eax, eax
0x18002225d  js      short loc_180022274
0x18002225f  mov     rax, [rsi+10h]
0x180022263  mov     dword ptr [rax+88h], 1
0x18002226d  jmp     short loc_180022274
0x18002226f  mov     edi, 86000011h
0x180022274  mov     rcx, [rbp+hKey]; hKey
0x180022278  mov     [rbp+hKey], 0
0x180022280  test    rcx, rcx
0x180022283  jz      short loc_180022291
0x180022285  call    cs:__imp_RegCloseKey
0x18002228c  nop     dword ptr [rax+rax+00h]
0x180022291  mov     rcx, [rbp+bstrString]; bstrString
0x180022295  call    cs:__imp_SysFreeString
0x18002229c  nop     dword ptr [rax+rax+00h]
0x1800222a1  mov     rsi, [rsp+40h+arg_8]
0x1800222a6  mov     eax, edi
0x1800222a8  add     rsp, 40h
0x1800222ac  pop     r14
0x1800222ae  pop     rdi
0x1800222af  pop     rbp
0x1800222b0  retn
```
