# CCertificateStoreCspWSTEPNode::SetValue(tagVARIANT)

- ea: `0x180022b70`
- end: `0x180022e0a`
- name: `?SetValue@CCertificateStoreCspWSTEPNode@@UEAAJUtagVARIANT@@@Z`
- size: `666`
- prototype: `__int64 __fastcall(CCertificateStoreCspWSTEPNode *__hidden this, struct tagVARIANT *__struct_ptr)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18001a114`
- `0x18002201c`
- `0x180022b70`
- `0x180036b00`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180022dea`
- `OLEAUT32!__imp_SysFreeString` at `0x180022dea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022c12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022dd9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022c12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180022dd9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022bda`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180022bda`
- `DMCmnUtils!OmaDmRegistrySetString` at `0x180022dba`
- `DMCmnUtils!OmaDmRegistrySetString` at `0x180022dba`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x180022c79`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x180022cf1`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x180022d3a`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x180022d83`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x180022c79`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x180022cf1`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x180022d3a`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x180022d83`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x180022cbb`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x180022cbb`

## string_xrefs

- `0x180022dac`: `DiscoveryServiceFullURL`

## pseudocode

```c
__int64 __fastcall CCertificateStoreCspWSTEPNode::SetValue(
        struct CConfigServiceProvider2Impl **this,
        struct tagVARIANT *a2)
{
  const unsigned __int16 *EnrollmentId2; // rax
  const WCHAR *v5; // rax
  LSTATUS v6; // eax
  signed int v7; // esi
  unsigned __int16 *v8; // rbx
  HKEY v9; // rcx
  unsigned int Lo; // r9d
  int v11; // edi
  LONG v12; // r9d
  LONG lVal; // r9d
  HKEY v14; // rcx
  unsigned int v16; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+40h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp+48h] BYREF

  v16 = 0;
  EnrollmentId2 = GetEnrollmentId2(this[16]);
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, EnrollmentId2);
  hKey = 0;
  v5 = (const WCHAR *)DMGetKnownRegPath(1);
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x2001Fu, &hKey);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  v8 = bstrString;
  if ( v7 < 0 )
  {
    v9 = hKey;
    hKey = 0;
    if ( v9 )
      RegCloseKey(v9);
    goto LABEL_35;
  }
  switch ( *((_DWORD *)this + 11) )
  {
    case 0xF:
      if ( a2->vt == 8 )
      {
        v11 = OmaDmRegistrySetString(hKey, bstrString, L"DiscoveryServiceFullURL", a2->bstrVal);
        goto LABEL_32;
      }
      break;
    case 0x10:
      if ( a2->vt == 3 )
      {
        lVal = a2->lVal;
        if ( (unsigned int)(lVal - 1) <= 0x3E7 )
        {
          v11 = OmaDmRegistrySetDWORD(hKey, bstrString, L"RenewalPeriod", lVal);
          if ( v11 >= 0 )
            *((_DWORD *)this[2] + 35) = 1;
          goto LABEL_32;
        }
      }
      break;
    case 0x11:
      if ( a2->vt == 3 )
      {
        v12 = a2->lVal;
        if ( (unsigned int)(v12 - 1) <= 0x3E7 )
        {
          v11 = OmaDmRegistrySetDWORD(hKey, bstrString, L"RetryInterval", v12);
          if ( v11 >= 0 )
            *((_DWORD *)this[2] + 34) = 1;
          goto LABEL_32;
        }
      }
      break;
    case 0x12:
      if ( a2->vt == 11
        && ((int)OmaDmRegistryGetDWORD(hKey, bstrString, L"Federated", &v16) < 0 || a2->iVal == -1 || v16 != -1) )
      {
        v11 = OmaDmRegistrySetDWORD(hKey, v8, L"RenewROBOSupport", a2->iVal);
        if ( v11 >= 0 )
          *((_DWORD *)this[2] + 36) = 1;
        goto LABEL_32;
      }
      break;
    default:
      if ( *((_DWORD *)this + 11) == 25 && a2->vt == 3 )
      {
        Lo = a2->cyVal.Lo;
        if ( Lo <= 0x3E8 )
        {
          v11 = OmaDmRegistrySetDWORD(hKey, bstrString, L"RetryAfterExpiryInterval", Lo);
          if ( v11 >= 0 )
            *((_DWORD *)this[2] + 34) = 1;
          goto LABEL_32;
        }
      }
      break;
  }
  v11 = -2046820335;
LABEL_32:
  v14 = hKey;
  hKey = 0;
  if ( v14 )
    RegCloseKey(v14);
  v7 = v11;
LABEL_35:
  SysFreeString(v8);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180022b70  mov     [rsp-28h+arg_8], rbx
0x180022b75  push    rbp
0x180022b76  push    rsi
0x180022b77  push    rdi
0x180022b78  push    r12
0x180022b7a  push    r14
0x180022b7c  mov     rbp, rsp
0x180022b7f  sub     rsp, 30h
0x180022b83  mov     r14, rcx
0x180022b86  mov     [rbp+arg_0], 0
0x180022b8d  mov     rcx, [rcx+80h]; struct CConfigServiceProvider2Impl *
0x180022b94  mov     rdi, rdx
0x180022b97  call    ?GetEnrollmentId2@@YAPEAGPEAVCConfigServiceProvider2Impl@@@Z; GetEnrollmentId2(CConfigServiceProvider2Impl *)
0x180022b9c  mov     rdx, rax; unsigned __int16 *
0x180022b9f  lea     rcx, [rbp+bstrString]; this
0x180022ba3  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180022ba8  mov     r12d, 1
0x180022bae  mov     [rbp+hKey], 0
0x180022bb6  mov     ecx, r12d
0x180022bb9  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x180022bbe  lea     rcx, [rbp+hKey]
0x180022bc2  mov     r9d, 2001Fh; samDesired
0x180022bc8  mov     [rsp+30h+phkResult], rcx; phkResult
0x180022bcd  xor     r8d, r8d; ulOptions
0x180022bd0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180022bd7  mov     rdx, rax; lpSubKey
0x180022bda  call    cs:__imp_RegOpenKeyExW
0x180022be1  nop     dword ptr [rax+rax+00h]
0x180022be6  mov     esi, eax
0x180022be8  test    eax, eax
0x180022bea  jle     short loc_180022BF5
0x180022bec  movzx   esi, ax
0x180022bef  or      esi, 80070000h
0x180022bf5  mov     rbx, [rbp+bstrString]
0x180022bf9  test    esi, esi
0x180022bfb  jns     short loc_180022C23
0x180022bfd  mov     rcx, [rbp+hKey]; hKey
0x180022c01  mov     [rbp+hKey], 0
0x180022c09  test    rcx, rcx
0x180022c0c  jz      loc_180022DE7
0x180022c12  call    cs:__imp_RegCloseKey
0x180022c19  nop     dword ptr [rax+rax+00h]
0x180022c1e  jmp     loc_180022DE7
0x180022c23  mov     ecx, [r14+2Ch]
0x180022c27  sub     ecx, 0Fh
0x180022c2a  jz      loc_180022DA2
0x180022c30  sub     ecx, r12d
0x180022c33  jz      loc_180022D59
0x180022c39  sub     ecx, r12d
0x180022c3c  jz      loc_180022D17
0x180022c42  sub     ecx, r12d
0x180022c45  jz      short loc_180022C9F
0x180022c47  cmp     ecx, 7
0x180022c4a  jnz     loc_180022D5F
0x180022c50  cmp     word ptr [rdi], 3
0x180022c54  jnz     loc_180022D5F
0x180022c5a  mov     r9d, [rdi+8]
0x180022c5e  cmp     r9d, 3E8h
0x180022c65  ja      loc_180022D5F
0x180022c6b  mov     rcx, [rbp+hKey]
0x180022c6f  lea     r8, aRetryafterexpi; "RetryAfterExpiryInterval"
0x180022c76  mov     rdx, rbx
0x180022c79  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180022c80  nop     dword ptr [rax+rax+00h]
0x180022c85  mov     edi, eax
0x180022c87  test    eax, eax
0x180022c89  js      loc_180022DC8
0x180022c8f  mov     rcx, [r14+10h]
0x180022c93  mov     [rcx+88h], r12d
0x180022c9a  jmp     loc_180022DC8
0x180022c9f  cmp     word ptr [rdi], 0Bh
0x180022ca3  jnz     loc_180022D5F
0x180022ca9  mov     rcx, [rbp+hKey]
0x180022cad  lea     r9, [rbp+arg_0]
0x180022cb1  lea     r8, aFederated; "Federated"
0x180022cb8  mov     rdx, rbx
0x180022cbb  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180022cc2  nop     dword ptr [rax+rax+00h]
0x180022cc7  test    eax, eax
0x180022cc9  js      short loc_180022CDE
0x180022ccb  or      eax, 0FFFFFFFFh
0x180022cce  cmp     ax, [rdi+8]
0x180022cd2  jz      short loc_180022CDE
0x180022cd4  cmp     [rbp+arg_0], 0FFFFFFFFh
0x180022cd8  jz      loc_180022D5F
0x180022cde  movsx   r9d, word ptr [rdi+8]
0x180022ce3  lea     r8, aRenewrobosuppo; "RenewROBOSupport"
0x180022cea  mov     rcx, [rbp+hKey]
0x180022cee  mov     rdx, rbx
0x180022cf1  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180022cf8  nop     dword ptr [rax+rax+00h]
0x180022cfd  mov     edi, eax
0x180022cff  test    eax, eax
0x180022d01  js      loc_180022DC8
0x180022d07  mov     rax, [r14+10h]
0x180022d0b  mov     [rax+90h], r12d
0x180022d12  jmp     loc_180022DC8
0x180022d17  cmp     word ptr [rdi], 3
0x180022d1b  jnz     short loc_180022D5F
0x180022d1d  mov     r9d, [rdi+8]
0x180022d21  lea     eax, [r9-1]
0x180022d25  cmp     eax, 3E7h
0x180022d2a  ja      short loc_180022D5F
0x180022d2c  mov     rcx, [rbp+hKey]
0x180022d30  lea     r8, aRetryinterval; "RetryInterval"
0x180022d37  mov     rdx, rbx
0x180022d3a  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180022d41  nop     dword ptr [rax+rax+00h]
0x180022d46  mov     edi, eax
0x180022d48  test    eax, eax
0x180022d4a  js      short loc_180022DC8
0x180022d4c  mov     rax, [r14+10h]
0x180022d50  mov     [rax+88h], r12d
0x180022d57  jmp     short loc_180022DC8
0x180022d59  cmp     word ptr [rdi], 3
0x180022d5d  jz      short loc_180022D66
0x180022d5f  mov     edi, 86000011h
0x180022d64  jmp     short loc_180022DC8
0x180022d66  mov     r9d, [rdi+8]
0x180022d6a  lea     eax, [r9-1]
0x180022d6e  cmp     eax, 3E7h
0x180022d73  ja      short loc_180022D5F
0x180022d75  mov     rcx, [rbp+hKey]
0x180022d79  lea     r8, aRenewalperiod; "RenewalPeriod"
0x180022d80  mov     rdx, rbx
0x180022d83  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180022d8a  nop     dword ptr [rax+rax+00h]
0x180022d8f  mov     edi, eax
0x180022d91  test    eax, eax
0x180022d93  js      short loc_180022DC8
0x180022d95  mov     rax, [r14+10h]
0x180022d99  mov     [rax+8Ch], r12d
0x180022da0  jmp     short loc_180022DC8
0x180022da2  cmp     word ptr [rdi], 8
0x180022da6  jnz     short loc_180022D5F
0x180022da8  mov     r9, [rdi+8]
0x180022dac  lea     r8, aDiscoveryservi; "DiscoveryServiceFullURL"
0x180022db3  mov     rcx, [rbp+hKey]
0x180022db7  mov     rdx, rbx
0x180022dba  call    cs:__imp_?OmaDmRegistrySetString@@YAJPEAUHKEY__@@PEBG11@Z; OmaDmRegistrySetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180022dc1  nop     dword ptr [rax+rax+00h]
0x180022dc6  mov     edi, eax
0x180022dc8  mov     rcx, [rbp+hKey]; hKey
0x180022dcc  mov     [rbp+hKey], 0
0x180022dd4  test    rcx, rcx
0x180022dd7  jz      short loc_180022DE5
0x180022dd9  call    cs:__imp_RegCloseKey
0x180022de0  nop     dword ptr [rax+rax+00h]
0x180022de5  mov     esi, edi
0x180022de7  mov     rcx, rbx; bstrString
0x180022dea  call    cs:__imp_SysFreeString
0x180022df1  nop     dword ptr [rax+rax+00h]
0x180022df6  mov     rbx, [rsp+30h+arg_8]
0x180022dfb  mov     eax, esi
0x180022dfd  add     rsp, 30h
0x180022e01  pop     r14
0x180022e03  pop     r12
0x180022e05  pop     rdi
0x180022e06  pop     rsi
0x180022e07  pop     rbp
0x180022e08  retn
```
