# CCertificateStoreCspWSTEPNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)

- ea: `0x180021d10`
- end: `0x180022014`
- name: `?CreateNodeInstance@CCertificateStoreCspWSTEPNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z`
- size: `772`
- prototype: `__int64 __usercall@<rax>(struct CConfigServiceProvider2Impl *@<rcx>, struct IConfigManager2URI *@<rdx>, const struct CSP_NODE_DATA *@<r8>, int@<r9d>, struct ICSPNode **, unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180008de0`
- `0x18001a114`
- `0x18001a4fc`
- `0x180021c18`
- `0x180021d10`
- `0x18002201c`
- `0x180036b00`
- `0x180107010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180021e6e`
- `OLEAUT32!__imp_SysFreeString` at `0x180021eef`
- `OLEAUT32!__imp_SysFreeString` at `0x180021e6e`
- `OLEAUT32!__imp_SysFreeString` at `0x180021eef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021e8e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021f0f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021e8e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021f0f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021e4a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180021e4a`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x180021eca`
- `DMCmnUtils!OmaDmRegistryGetString` at `0x180021eca`

## string_xrefs

- `0x180021eb9`: `DiscoveryServiceFullURL`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CCertificateStoreCspWSTEPNode::CreateNodeInstance(
        struct CConfigServiceProvider2Impl *a1,
        struct IConfigManager2URI *a2,
        const struct CSP_NODE_DATA *a3,
        int a4,
        struct ICSPNode **a5,
        unsigned int *a6)
{
  int v10; // edi
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  const unsigned __int16 *EnrollmentId2; // rax
  int v17; // esi
  const WCHAR *v18; // rax
  LSTATUS v19; // eax
  signed int v20; // ebx
  HKEY v21; // rcx
  int String; // eax
  HKEY v24; // rcx
  unsigned int v25; // eax
  unsigned int v26; // eax
  struct ICSPNode *v27; // rbx
  struct CConfigServiceProvider2Impl *v28; // rsi
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  struct ICSPNode *v30; // [rsp+38h] [rbp-C8h] BYREF
  int v31; // [rsp+40h] [rbp-C0h] BYREF
  BSTR bstrString; // [rsp+48h] [rbp-B8h] BYREF
  struct CConfigServiceProvider2Impl *v33; // [rsp+50h] [rbp-B0h]
  unsigned __int16 v34[264]; // [rsp+60h] [rbp-A0h] BYREF

  v33 = a1;
  v31 = 0;
  v30 = 0;
  if ( !a1 || !a2 || !a3 || !a5 || !a6 )
  {
    ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v30);
    return 2147942487LL;
  }
  *a5 = 0;
  *a6 = 0;
  v10 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, int *))(*(_QWORD *)a2 + 136LL))(a2, &v31);
  if ( v10 < 0 )
  {
LABEL_42:
    ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v30);
    return (unsigned int)v10;
  }
  if ( *((_DWORD *)a3 + 3) == 23 )
    *a6 = 2;
  v11 = *((_DWORD *)a3 + 3);
  if ( v11 > 0x12 )
  {
    v25 = v11 - 19;
    if ( !v25 )
      goto LABEL_35;
    v26 = v25 - 1;
    if ( !v26 )
      goto LABEL_35;
    v15 = v26 - 3;
    if ( !v15 )
      goto LABEL_35;
LABEL_33:
    if ( v15 - 1 >= 2 )
    {
      v10 = -2147418113;
      goto LABEL_42;
    }
    goto LABEL_35;
  }
  if ( v11 == 18 )
    goto LABEL_35;
  v12 = v11 - 12;
  if ( !v12 )
    goto LABEL_35;
  v13 = v12 - 1;
  if ( !v13 )
    goto LABEL_35;
  v14 = v13 - 1;
  if ( !v14 )
    goto LABEL_35;
  v15 = v14 - 1;
  if ( v15 )
    goto LABEL_33;
  hKey = 0;
  EnrollmentId2 = GetEnrollmentId2(a1);
  ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, EnrollmentId2);
  v17 = 1;
  v18 = (const WCHAR *)DMGetKnownRegPath(1);
  v19 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v18, 0, 0x2001Fu, &hKey);
  v20 = v19;
  if ( v19 > 0 )
    v20 = (unsigned __int16)v19 | 0x80070000;
  if ( v20 >= 0 )
  {
    String = OmaDmRegistryGetString(hKey, bstrString, L"DiscoveryServiceFullURL", v34, 0x101u);
    v10 = String;
    if ( String == -2147024894 || String == -2147023267 )
    {
      v17 = 0;
      v10 = 0;
    }
    SysFreeString(bstrString);
    v24 = hKey;
    hKey = 0;
    if ( v24 )
      RegCloseKey(v24);
    if ( v10 < 0 )
      goto LABEL_42;
    if ( !v17 )
    {
      if ( !a4 )
      {
        v10 = -2046820350;
        goto LABEL_42;
      }
LABEL_37:
      v10 = ATL::CComObject<CCertificateStoreCspWSTEPNode>::CreateInstance(&v30);
      if ( v10 >= 0 )
      {
        v27 = v30;
        if ( v30 )
        {
          v28 = v33;
          v10 = (*(__int64 (__fastcall **)(struct ICSPNode *, struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *))(*(_QWORD *)v30 + 136LL))(
                  v30,
                  v33,
                  a2,
                  a3);
          if ( v10 >= 0 )
          {
            (*(void (__fastcall **)(struct ICSPNode *))(*(_QWORD *)v27 + 8LL))(v27);
            *((_QWORD *)v27 + 16) = v28;
            v30 = 0;
            *a5 = v27;
          }
        }
        else
        {
          v10 = -2147024882;
        }
      }
      goto LABEL_42;
    }
LABEL_35:
    if ( a4 )
    {
      v10 = -2046820335;
      goto LABEL_42;
    }
    goto LABEL_37;
  }
  SysFreeString(bstrString);
  v21 = hKey;
  hKey = 0;
  if ( v21 )
    RegCloseKey(v21);
  ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(&v30);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180021d10  mov     [rsp-8+arg_18], rbx
0x180021d15  push    rbp
0x180021d16  push    rsi
0x180021d17  push    rdi
0x180021d18  push    r12
0x180021d1a  push    r13
0x180021d1c  push    r14
0x180021d1e  push    r15
0x180021d20  lea     rbp, [rsp-180h]
0x180021d28  sub     rsp, 280h
0x180021d2f  mov     rax, cs:__security_cookie
0x180021d36  xor     rax, rsp
0x180021d39  mov     [rbp+1B0h+var_40], rax
0x180021d40  mov     r13d, r9d
0x180021d43  mov     r14, r8
0x180021d46  mov     r15, rdx
0x180021d49  mov     rsi, rcx
0x180021d4c  mov     [rsp+2B0h+var_260], rcx
0x180021d51  mov     r12, [rbp+1B0h+arg_20]
0x180021d58  mov     rbx, [rbp+1B0h+arg_28]
0x180021d5f  xor     eax, eax
0x180021d61  mov     [rsp+2B0h+var_270], eax
0x180021d65  mov     [rsp+2B0h+var_278], rax
0x180021d6a  test    rcx, rcx
0x180021d6d  jz      loc_180021FDA
0x180021d73  test    rdx, rdx
0x180021d76  jz      loc_180021FDA
0x180021d7c  test    r8, r8
0x180021d7f  jz      loc_180021FDA
0x180021d85  test    r12, r12
0x180021d88  jz      loc_180021FDA
0x180021d8e  test    rbx, rbx
0x180021d91  jz      loc_180021FDA
0x180021d97  mov     [r12], rax
0x180021d9b  mov     [rbx], eax
0x180021d9d  mov     rax, [rdx]
0x180021da0  lea     rdx, [rsp+2B0h+var_270]
0x180021da5  mov     rcx, r15
0x180021da8  mov     rax, [rax+88h]
0x180021daf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021db4  mov     edi, eax
0x180021db6  test    eax, eax
0x180021db8  js      loc_180021FCC
0x180021dbe  cmp     dword ptr [r14+0Ch], 17h
0x180021dc3  jnz     short loc_180021DCB
0x180021dc5  mov     dword ptr [rbx], 2
0x180021dcb  mov     eax, [r14+0Ch]
0x180021dcf  cmp     eax, 12h
0x180021dd2  ja      loc_180021F36
0x180021dd8  jz      loc_180021F56
0x180021dde  sub     eax, 0Ch
0x180021de1  jz      loc_180021F56
0x180021de7  sub     eax, 1
0x180021dea  jz      loc_180021F56
0x180021df0  sub     eax, 1
0x180021df3  jz      loc_180021F56
0x180021df9  sub     eax, 1
0x180021dfc  jnz     loc_180021F45
0x180021e02  mov     [rsp+2B0h+hKey], 0
0x180021e0b  mov     rcx, rsi; struct CConfigServiceProvider2Impl *
0x180021e0e  call    ?GetEnrollmentId2@@YAPEAGPEAVCConfigServiceProvider2Impl@@@Z; GetEnrollmentId2(CConfigServiceProvider2Impl *)
0x180021e13  mov     rdx, rax; unsigned __int16 *
0x180021e16  lea     rcx, [rsp+2B0h+bstrString]; this
0x180021e1b  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x180021e20  nop
0x180021e21  mov     esi, 1
0x180021e26  mov     ecx, esi
0x180021e28  call    ?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z; DMGetKnownRegPath(REFKNOWNREGID)
0x180021e2d  lea     rcx, [rsp+2B0h+hKey]
0x180021e32  mov     [rsp+2B0h+phkResult], rcx; phkResult
0x180021e37  mov     r9d, 2001Fh; samDesired
0x180021e3d  xor     r8d, r8d; ulOptions
0x180021e40  mov     rdx, rax; lpSubKey
0x180021e43  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180021e4a  call    cs:__imp_RegOpenKeyExW
0x180021e51  nop     dword ptr [rax+rax+00h]
0x180021e56  mov     ebx, eax
0x180021e58  test    eax, eax
0x180021e5a  jle     short loc_180021E65
0x180021e5c  movzx   ebx, ax
0x180021e5f  or      ebx, 80070000h
0x180021e65  test    ebx, ebx
0x180021e67  jns     short loc_180021EAC
0x180021e69  mov     rcx, [rsp+2B0h+bstrString]; bstrString
0x180021e6e  call    cs:__imp_SysFreeString
0x180021e75  nop     dword ptr [rax+rax+00h]
0x180021e7a  nop
0x180021e7b  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180021e80  mov     [rsp+2B0h+hKey], 0
0x180021e89  test    rcx, rcx
0x180021e8c  jz      short loc_180021E9B
0x180021e8e  call    cs:__imp_RegCloseKey
0x180021e95  nop     dword ptr [rax+rax+00h]
0x180021e9a  nop
0x180021e9b  lea     rcx, [rsp+2B0h+var_278]
0x180021ea0  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x180021ea5  mov     eax, ebx
0x180021ea7  jmp     loc_180021FE9
0x180021eac  mov     dword ptr [rsp+2B0h+phkResult], 101h
0x180021eb4  lea     r9, [rsp+2B0h+var_250]
0x180021eb9  lea     r8, aDiscoveryservi; "DiscoveryServiceFullURL"
0x180021ec0  mov     rdx, [rsp+2B0h+bstrString]
0x180021ec5  mov     rcx, [rsp+2B0h+hKey]
0x180021eca  call    cs:__imp_?OmaDmRegistryGetString@@YAJPEAUHKEY__@@PEBG1PEAGI@Z; OmaDmRegistryGetString(HKEY__ *,ushort const *,ushort const *,ushort *,uint)
0x180021ed1  nop     dword ptr [rax+rax+00h]
0x180021ed6  mov     edi, eax
0x180021ed8  cmp     eax, 80070002h
0x180021edd  jz      short loc_180021EE6
0x180021edf  cmp     eax, 8007065Dh
0x180021ee4  jnz     short loc_180021EEA
0x180021ee6  xor     esi, esi
0x180021ee8  xor     edi, edi
0x180021eea  mov     rcx, [rsp+2B0h+bstrString]; bstrString
0x180021eef  call    cs:__imp_SysFreeString
0x180021ef6  nop     dword ptr [rax+rax+00h]
0x180021efb  nop
0x180021efc  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180021f01  mov     [rsp+2B0h+hKey], 0
0x180021f0a  test    rcx, rcx
0x180021f0d  jz      short loc_180021F1B
0x180021f0f  call    cs:__imp_RegCloseKey
0x180021f16  nop     dword ptr [rax+rax+00h]
0x180021f1b  test    edi, edi
0x180021f1d  js      loc_180021FCC
0x180021f23  test    esi, esi
0x180021f25  jnz     short loc_180021F56
0x180021f27  test    r13d, r13d
0x180021f2a  jnz     short loc_180021F62
0x180021f2c  mov     edi, 86000002h
0x180021f31  jmp     loc_180021FCC
0x180021f36  sub     eax, 13h
0x180021f39  jz      short loc_180021F56
0x180021f3b  sub     eax, 1
0x180021f3e  jz      short loc_180021F56
0x180021f40  sub     eax, 3
0x180021f43  jz      short loc_180021F56
0x180021f45  sub     eax, 1
0x180021f48  jz      short loc_180021F56
0x180021f4a  cmp     eax, 1
0x180021f4d  jz      short loc_180021F56
0x180021f4f  mov     edi, 8000FFFFh
0x180021f54  jmp     short loc_180021FCC
0x180021f56  test    r13d, r13d
0x180021f59  jz      short loc_180021F62
0x180021f5b  mov     edi, 86000011h
0x180021f60  jmp     short loc_180021FCC
0x180021f62  lea     rcx, [rsp+2B0h+var_278]
0x180021f67  call    ?CreateInstance@?$CComObject@VCCertificateStoreCspWSTEPNode@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CCertificateStoreCspWSTEPNode>::CreateInstance(ATL::CComObject<CCertificateStoreCspWSTEPNode> * *)
0x180021f6c  mov     edi, eax
0x180021f6e  test    eax, eax
0x180021f70  js      short loc_180021FCC
0x180021f72  mov     rbx, [rsp+2B0h+var_278]
0x180021f77  test    rbx, rbx
0x180021f7a  jnz     short loc_180021F83
0x180021f7c  mov     edi, 8007000Eh
0x180021f81  jmp     short loc_180021FCC
0x180021f83  mov     rax, [rbx]
0x180021f86  mov     r9, r14
0x180021f89  mov     r8, r15
0x180021f8c  mov     rsi, [rsp+2B0h+var_260]
0x180021f91  mov     rdx, rsi
0x180021f94  mov     rcx, rbx
0x180021f97  mov     rax, [rax+88h]
0x180021f9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fa3  mov     edi, eax
0x180021fa5  test    eax, eax
0x180021fa7  js      short loc_180021FCC
0x180021fa9  mov     rax, [rbx]
0x180021fac  mov     rcx, rbx
0x180021faf  mov     rax, [rax+8]
0x180021fb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fb8  mov     [rbx+80h], rsi
0x180021fbf  mov     [rsp+2B0h+var_278], 0
0x180021fc8  mov     [r12], rbx
0x180021fcc  lea     rcx, [rsp+2B0h+var_278]
0x180021fd1  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x180021fd6  mov     eax, edi
0x180021fd8  jmp     short loc_180021FE9
0x180021fda  lea     rcx, [rsp+2B0h+var_278]
0x180021fdf  call    ??1?$CComPtrBase@V?$CComObject@VCRemoteFindNode@@@ATL@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ATL::CComObject<CRemoteFindNode>>::~CComPtrBase<ATL::CComObject<CRemoteFindNode>>(void)
0x180021fe4  mov     eax, 80070057h
0x180021fe9  mov     rcx, [rbp+1B0h+var_40]
0x180021ff0  xor     rcx, rsp; StackCookie
0x180021ff3  call    __security_check_cookie
0x180021ff8  mov     rbx, [rsp+2B0h+arg_18]
0x180022000  add     rsp, 280h
0x180022007  pop     r15
0x180022009  pop     r14
0x18002200b  pop     r13
0x18002200d  pop     r12
0x18002200f  pop     rdi
0x180022010  pop     rsi
0x180022011  pop     rbp
0x180022012  retn
```
