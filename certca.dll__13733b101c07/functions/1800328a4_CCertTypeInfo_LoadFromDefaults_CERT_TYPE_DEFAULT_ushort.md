# CCertTypeInfo::_LoadFromDefaults(_CERT_TYPE_DEFAULT *,ushort *)

- ea: `0x1800328a4`
- end: `0x180032d64`
- name: `?_LoadFromDefaults@CCertTypeInfo@@IEAAJPEAU_CERT_TYPE_DEFAULT@@PEAG@Z`
- size: `1216`
- prototype: `__int64 __fastcall(CCertTypeInfo *this, const unsigned __int16 **, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002fa68`
- `0x180030224`

## callees

- `0x180008400`
- `0x18000ce90`
- `0x1800113e0`
- `0x180012450`
- `0x18001e404`
- `0x180028040`
- `0x18002a290`
- `0x18002a668`
- `0x1800328a4`
- `0x18003306c`
- `0x180038262`
- `0x1800382c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18003298c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18003298c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180032b72`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180032b72`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032d0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032d1f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032d2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032d3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032d0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032d1f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032d2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180032d3b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180032c9a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180032c9a`

## string_xrefs

- `0x180032a23`: `pKICriticalExtensions`
- `0x180032b45`: `msPKI-Cert-Template-OID`
- `0x180032a46`: `msPKI-Supersede-Templates`

## pseudocode

```c
__int64 __fastcall CCertTypeInfo::_LoadFromDefaults(
        CCertTypeInfo *this,
        const unsigned __int16 **a2,
        unsigned __int16 *a3)
{
  PSID v6; // r14
  HLOCAL v7; // r15
  unsigned int v8; // ebx
  unsigned int v9; // ecx
  int v10; // edx
  unsigned __int16 *v11; // rax
  int SDFromTemplate; // eax
  UINT v13; // edx
  unsigned __int16 **v14; // r8
  unsigned int v15; // ecx
  int v16; // eax
  unsigned __int16 *v17; // rcx
  unsigned __int16 **v18; // r8
  _WORD *v19; // rax
  int v20; // ecx
  int v21; // ecx
  BOOL v22; // eax
  __int64 v23; // rcx
  int SidFromDomain; // eax
  const unsigned __int16 *v25; // rcx
  const unsigned __int16 *v26; // rdx
  HLOCAL v28; // [rsp+20h] [rbp-E0h] BYREF
  PSID Sid; // [rsp+28h] [rbp-D8h] BYREF
  HLOCAL hMem; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v32; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v33; // [rsp+48h] [rbp-B8h]
  _BYTE v34[144]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[256]; // [rsp+E0h] [rbp-20h] BYREF

  memset_0(v34, 0, sizeof(v34));
  v6 = 0;
  StringSid = 0;
  v7 = 0;
  Sid = 0;
  hMem = 0;
  v28 = 0;
  if ( !a2 )
  {
    v8 = -2147467261;
    v9 = 83362600;
    v10 = -2147467261;
LABEL_57:
    CSPrintErrorLineFile(v9, v10);
    goto LABEL_58;
  }
  v11 = CertAllocString(*a2);
  *((_QWORD *)this + 1) = v11;
  if ( !v11 )
  {
    v10 = -2147024882;
    v9 = 83886888;
    v8 = -2147024882;
    goto LABEL_57;
  }
  v32 = (unsigned __int16 *)*a2;
  v33 = 0;
  SDFromTemplate = CCertTypeInfo::SetProperty(this, L"cn", &v32);
  v8 = SDFromTemplate;
  if ( SDFromTemplate )
  {
    v9 = 84280104;
LABEL_56:
    v10 = SDFromTemplate;
    goto LABEL_57;
  }
  v13 = *((_DWORD *)a2 + 2);
  v14 = 0;
  if ( v13 )
  {
    if ( !LoadStringW(g_hInstance, v13, Buffer, 255) )
    {
      SDFromTemplate = myHLastError();
      v8 = SDFromTemplate;
      v9 = 85132072;
      goto LABEL_56;
    }
    v33 = 0;
    v32 = Buffer;
    v14 = &v32;
  }
  SDFromTemplate = CCertTypeInfo::SetProperty(this, L"displayName", v14);
  v8 = SDFromTemplate;
  if ( SDFromTemplate )
  {
    v9 = 85590824;
    goto LABEL_56;
  }
  SDFromTemplate = CCertTypeInfo::_SetWszzProperty(this, L"pKIDefaultCSPs", a2[3]);
  v8 = SDFromTemplate;
  if ( SDFromTemplate )
  {
    v9 = 85787432;
    goto LABEL_56;
  }
  SDFromTemplate = CCertTypeInfo::_SetWszzProperty(this, L"pKIExtendedKeyUsage", a2[4]);
  v8 = SDFromTemplate;
  if ( SDFromTemplate )
  {
    v9 = 85984040;
    goto LABEL_56;
  }
  SDFromTemplate = CCertTypeInfo::_SetWszzProperty(this, L"pKICriticalExtensions", a2[7]);
  v8 = SDFromTemplate;
  if ( SDFromTemplate )
  {
    v9 = 86311720;
    goto LABEL_56;
  }
  SDFromTemplate = CCertTypeInfo::_SetWszzProperty(this, L"msPKI-Supersede-Templates", a2[14]);
  v8 = SDFromTemplate;
  if ( SDFromTemplate )
  {
    v9 = 86639400;
    goto LABEL_56;
  }
  SDFromTemplate = CCertTypeInfo::_SetWszzProperty(this, L"msPKI-RA-Policies", a2[15]);
  v8 = SDFromTemplate;
  if ( SDFromTemplate )
  {
    v9 = 86836008;
    goto LABEL_56;
  }
  SDFromTemplate = CCertTypeInfo::_SetWszzProperty(this, L"msPKI-RA-Application-Policies", a2[17]);
  v8 = SDFromTemplate;
  if ( SDFromTemplate )
  {
    v9 = 87163688;
    goto LABEL_56;
  }
  SDFromTemplate = CCertTypeInfo::_SetWszzProperty(this, L"msPKI-Certificate-Policy", a2[16]);
  v8 = SDFromTemplate;
  if ( SDFromTemplate )
  {
    v9 = 87491368;
    goto LABEL_56;
  }
  SDFromTemplate = CCertTypeInfo::_SetWszzProperty(this, L"msPKI-Certificate-Application-Policy", a2[18]);
  v8 = SDFromTemplate;
  if ( SDFromTemplate )
  {
    v9 = 87819048;
    goto LABEL_56;
  }
  if ( (*((_DWORD *)a2 + 11) & 0x10000) != 0 )
  {
    v16 = CAOIDBuildOID(v15, a2[13], (unsigned __int16 **)&v28, 0);
    v17 = v32;
    v18 = &v32;
    v7 = v28;
    if ( !v16 )
      v17 = (unsigned __int16 *)v28;
    v32 = v17;
    if ( v16 )
      v18 = 0;
  }
  else
  {
    v18 = &v32;
    v32 = (unsigned __int16 *)a2[13];
  }
  v33 = 0;
  SDFromTemplate = CCertTypeInfo::SetProperty(this, L"msPKI-Cert-Template-OID", v18);
  v8 = SDFromTemplate;
  if ( SDFromTemplate )
  {
    v9 = 89522984;
    goto LABEL_56;
  }
  v19 = LocalAlloc(0, 2u);
  *((_QWORD *)this + 5) = v19;
  if ( !v19 )
  {
    v10 = -2147024882;
    v9 = 89981736;
    v8 = -2147024882;
    goto LABEL_57;
  }
  *v19 = *((_WORD *)a2 + 20);
  *((_DWORD *)this + 8) = 2;
  *((_DWORD *)this + 12) = 0;
  v20 = *((_DWORD *)a2 + 11);
  *((_DWORD *)this + 14) = v20;
  v21 = v20 & 0x880;
  *((_DWORD *)this + 36) = *((_DWORD *)a2 + 18);
  *((_DWORD *)this + 15) = *((_DWORD *)a2 + 12);
  *((_DWORD *)this + 16) = *((_DWORD *)a2 + 19);
  *((_DWORD *)this + 17) = *((_DWORD *)a2 + 20);
  *((_DWORD *)this + 18) = *((_DWORD *)a2 + 21);
  *((_DWORD *)this + 19) = *((_DWORD *)a2 + 22);
  *((_DWORD *)this + 20) = *((_DWORD *)a2 + 23);
  *((_DWORD *)this + 21) = *((_DWORD *)a2 + 24);
  *((_DWORD *)this + 22) = *((_DWORD *)a2 + 25);
  *((_DWORD *)this + 6) = *((_DWORD *)a2 + 13);
  *((_DWORD *)this + 4) = v21 != 0;
  v22 = *((_DWORD *)this + 6) != -1 && v21;
  *((_DWORD *)this + 5) = v22;
  v23 = -10000000LL * *((int *)a2 + 16);
  v33 = 0;
  *((_QWORD *)this + 13) = v23;
  *((_QWORD *)this + 14) = -10000000LL * *((int *)a2 + 17);
  v32 = (unsigned __int16 *)*a2;
  SDFromTemplate = CCertTypeInfo::SetProperty(this, L"distinguishedName", &v32);
  v8 = SDFromTemplate;
  if ( SDFromTemplate )
  {
    v9 = 92406568;
    goto LABEL_56;
  }
  SidFromDomain = myGetSidFromDomain(a3, &Sid);
  v8 = SidFromDomain;
  if ( !SidFromDomain )
  {
    v6 = Sid;
    if ( ConvertSidToStringSidW(Sid, &StringSid) )
    {
      v25 = a2[2];
      v28 = StringSid;
      SDFromTemplate = myFormatMessageFromString(v25, (const unsigned __int16 **)&v28, 1u, (unsigned __int16 **)&hMem);
      v8 = SDFromTemplate;
      if ( SDFromTemplate )
      {
        v9 = 93520680;
      }
      else
      {
        SDFromTemplate = myGetSDFromTemplate((const unsigned __int16 *)hMem, v26, (void **)this + 17);
        v8 = SDFromTemplate;
        if ( !SDFromTemplate )
          goto LABEL_58;
        v9 = 93717288;
      }
    }
    else
    {
      SDFromTemplate = myHLastError();
      v8 = SDFromTemplate;
      v9 = 93193000;
    }
    goto LABEL_56;
  }
  if ( SidFromDomain > 0 )
    v8 = (unsigned __int16)SidFromDomain | 0x80070000;
  CSPrintErrorLineFile(0x5890328u, v8);
  v6 = Sid;
LABEL_58:
  if ( hMem )
    LocalFree(hMem);
  if ( StringSid )
    LocalFree(StringSid);
  if ( v6 )
    LocalFree(v6);
  if ( v7 )
    LocalFree(v7);
  return v8;
}

```

## disassembly

```asm
0x1800328a4  push    rbp
0x1800328a6  push    rbx
0x1800328a7  push    rsi
0x1800328a8  push    rdi
0x1800328a9  push    r12
0x1800328ab  push    r14
0x1800328ad  push    r15
0x1800328af  lea     rbp, [rsp-1F0h]
0x1800328b7  sub     rsp, 2F0h
0x1800328be  mov     rax, cs:__security_cookie
0x1800328c5  xor     rax, rsp
0x1800328c8  mov     [rbp+220h+var_40], rax
0x1800328cf  mov     r12, r8
0x1800328d2  mov     rsi, rdx
0x1800328d5  mov     rdi, rcx
0x1800328d8  xor     edx, edx; Val
0x1800328da  mov     r8d, 90h; Size
0x1800328e0  lea     rcx, [rsp+320h+var_2D0]; void *
0x1800328e5  call    memset_0
0x1800328ea  xor     r14d, r14d
0x1800328ed  mov     [rsp+320h+StringSid], 0
0x1800328f6  xor     r15d, r15d
0x1800328f9  mov     [rsp+320h+Sid], r14
0x1800328fe  mov     [rsp+320h+hMem], r14
0x180032903  mov     [rsp+320h+var_300], r15
0x180032908  test    rsi, rsi
0x18003290b  jnz     short loc_18003291E
0x18003290d  mov     ebx, 80004003h
0x180032912  mov     ecx, 4F80328h
0x180032917  mov     edx, ebx
0x180032919  jmp     loc_180032D00
0x18003291e  mov     rcx, [rsi]; Src
0x180032921  call    ?CertAllocString@@YAPEAGPEBG@Z; CertAllocString(ushort const *)
0x180032926  mov     [rdi+8], rax
0x18003292a  test    rax, rax
0x18003292d  jnz     short loc_180032940
0x18003292f  mov     edx, 8007000Eh
0x180032934  mov     ecx, 5000328h
0x180032939  mov     ebx, edx
0x18003293b  jmp     loc_180032D00
0x180032940  mov     rax, [rsi]
0x180032943  lea     r8, [rsp+320h+var_2E0]; unsigned __int16 **
0x180032948  lea     rdx, aCn_1; "cn"
0x18003294f  mov     [rsp+320h+var_2E0], rax
0x180032954  mov     rcx, rdi; this
0x180032957  mov     [rsp+320h+var_2D8], r14
0x18003295c  call    ?SetProperty@CCertTypeInfo@@QEAAJPEBGPEAPEAG@Z; CCertTypeInfo::SetProperty(ushort const *,ushort * *)
0x180032961  mov     ebx, eax
0x180032963  test    eax, eax
0x180032965  jz      short loc_180032971
0x180032967  mov     ecx, 5060328h
0x18003296c  jmp     loc_180032CFE
0x180032971  mov     edx, [rsi+8]; uID
0x180032974  xor     r8d, r8d
0x180032977  test    edx, edx
0x180032979  jz      short loc_1800329BA
0x18003297b  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180032982  lea     r8, [rbp+220h+Buffer]; lpBuffer
0x180032986  mov     r9d, 0FFh; cchBufferMax
0x18003298c  call    cs:__imp_LoadStringW
0x180032992  test    eax, eax
0x180032994  jnz     short loc_1800329A7
0x180032996  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18003299b  mov     ebx, eax
0x18003299d  mov     ecx, 5130328h
0x1800329a2  jmp     loc_180032CFE
0x1800329a7  lea     rax, [rbp+220h+Buffer]
0x1800329ab  mov     [rsp+320h+var_2D8], r14
0x1800329b0  mov     [rsp+320h+var_2E0], rax
0x1800329b5  lea     r8, [rsp+320h+var_2E0]; unsigned __int16 **
0x1800329ba  lea     rdx, aDisplayname_0; "displayName"
0x1800329c1  mov     rcx, rdi; this
0x1800329c4  call    ?SetProperty@CCertTypeInfo@@QEAAJPEBGPEAPEAG@Z; CCertTypeInfo::SetProperty(ushort const *,ushort * *)
0x1800329c9  mov     ebx, eax
0x1800329cb  test    eax, eax
0x1800329cd  jz      short loc_1800329D9
0x1800329cf  mov     ecx, 51A0328h
0x1800329d4  jmp     loc_180032CFE
0x1800329d9  mov     r8, [rsi+18h]; unsigned __int16 *
0x1800329dd  lea     rdx, aPkidefaultcsps; "pKIDefaultCSPs"
0x1800329e4  mov     rcx, rdi; this
0x1800329e7  call    ?_SetWszzProperty@CCertTypeInfo@@IEAAJPEBG0@Z; CCertTypeInfo::_SetWszzProperty(ushort const *,ushort const *)
0x1800329ec  mov     ebx, eax
0x1800329ee  test    eax, eax
0x1800329f0  jz      short loc_1800329FC
0x1800329f2  mov     ecx, 51D0328h
0x1800329f7  jmp     loc_180032CFE
0x1800329fc  mov     r8, [rsi+20h]; unsigned __int16 *
0x180032a00  lea     rdx, aPkiextendedkey; "pKIExtendedKeyUsage"
0x180032a07  mov     rcx, rdi; this
0x180032a0a  call    ?_SetWszzProperty@CCertTypeInfo@@IEAAJPEBG0@Z; CCertTypeInfo::_SetWszzProperty(ushort const *,ushort const *)
0x180032a0f  mov     ebx, eax
0x180032a11  test    eax, eax
0x180032a13  jz      short loc_180032A1F
0x180032a15  mov     ecx, 5200328h
0x180032a1a  jmp     loc_180032CFE
0x180032a1f  mov     r8, [rsi+38h]; unsigned __int16 *
0x180032a23  lea     rdx, aPkicriticalext; "pKICriticalExtensions"
0x180032a2a  mov     rcx, rdi; this
0x180032a2d  call    ?_SetWszzProperty@CCertTypeInfo@@IEAAJPEBG0@Z; CCertTypeInfo::_SetWszzProperty(ushort const *,ushort const *)
0x180032a32  mov     ebx, eax
0x180032a34  test    eax, eax
0x180032a36  jz      short loc_180032A42
0x180032a38  mov     ecx, 5250328h
0x180032a3d  jmp     loc_180032CFE
0x180032a42  mov     r8, [rsi+70h]; unsigned __int16 *
0x180032a46  lea     rdx, aMspkiSupersede; "msPKI-Supersede-Templates"
0x180032a4d  mov     rcx, rdi; this
0x180032a50  call    ?_SetWszzProperty@CCertTypeInfo@@IEAAJPEBG0@Z; CCertTypeInfo::_SetWszzProperty(ushort const *,ushort const *)
0x180032a55  mov     ebx, eax
0x180032a57  test    eax, eax
0x180032a59  jz      short loc_180032A65
0x180032a5b  mov     ecx, 52A0328h
0x180032a60  jmp     loc_180032CFE
0x180032a65  mov     r8, [rsi+78h]; unsigned __int16 *
0x180032a69  lea     rdx, aMspkiRaPolicie; "msPKI-RA-Policies"
0x180032a70  mov     rcx, rdi; this
0x180032a73  call    ?_SetWszzProperty@CCertTypeInfo@@IEAAJPEBG0@Z; CCertTypeInfo::_SetWszzProperty(ushort const *,ushort const *)
0x180032a78  mov     ebx, eax
0x180032a7a  test    eax, eax
0x180032a7c  jz      short loc_180032A88
0x180032a7e  mov     ecx, 52D0328h
0x180032a83  jmp     loc_180032CFE
0x180032a88  mov     r8, [rsi+88h]; unsigned __int16 *
0x180032a8f  lea     rdx, aMspkiRaApplica; "msPKI-RA-Application-Policies"
0x180032a96  mov     rcx, rdi; this
0x180032a99  call    ?_SetWszzProperty@CCertTypeInfo@@IEAAJPEBG0@Z; CCertTypeInfo::_SetWszzProperty(ushort const *,ushort const *)
0x180032a9e  mov     ebx, eax
0x180032aa0  test    eax, eax
0x180032aa2  jz      short loc_180032AAE
0x180032aa4  mov     ecx, 5320328h
0x180032aa9  jmp     loc_180032CFE
0x180032aae  mov     r8, [rsi+80h]; unsigned __int16 *
0x180032ab5  lea     rdx, aMspkiCertifica; "msPKI-Certificate-Policy"
0x180032abc  mov     rcx, rdi; this
0x180032abf  call    ?_SetWszzProperty@CCertTypeInfo@@IEAAJPEBG0@Z; CCertTypeInfo::_SetWszzProperty(ushort const *,ushort const *)
0x180032ac4  mov     ebx, eax
0x180032ac6  test    eax, eax
0x180032ac8  jz      short loc_180032AD4
0x180032aca  mov     ecx, 5370328h
0x180032acf  jmp     loc_180032CFE
0x180032ad4  mov     r8, [rsi+90h]; unsigned __int16 *
0x180032adb  lea     rdx, aMspkiCertifica_0; "msPKI-Certificate-Application-Policy"
0x180032ae2  mov     rcx, rdi; this
0x180032ae5  call    ?_SetWszzProperty@CCertTypeInfo@@IEAAJPEBG0@Z; CCertTypeInfo::_SetWszzProperty(ushort const *,ushort const *)
0x180032aea  mov     ebx, eax
0x180032aec  test    eax, eax
0x180032aee  jz      short loc_180032AFA
0x180032af0  mov     ecx, 53C0328h
0x180032af5  jmp     loc_180032CFE
0x180032afa  test    dword ptr [rsi+2Ch], 10000h
0x180032b01  mov     rax, [rsi+68h]
0x180032b05  jz      short loc_180032B3B
0x180032b07  xor     r9d, r9d; struct ldap *
0x180032b0a  lea     r8, [rsp+320h+var_300]; unsigned __int16 **
0x180032b0f  mov     rdx, rax; unsigned __int16 *
0x180032b12  call    ?CAOIDBuildOID@@YAJKPEBGPEAPEAGPEAUldap@@@Z; CAOIDBuildOID(ulong,ushort const *,ushort * *,ldap *)
0x180032b17  mov     rcx, [rsp+320h+var_2E0]
0x180032b1c  lea     r8, [rsp+320h+var_2E0]
0x180032b21  mov     r15, [rsp+320h+var_300]
0x180032b26  test    eax, eax
0x180032b28  cmovz   rcx, r15
0x180032b2c  mov     [rsp+320h+var_2E0], rcx
0x180032b31  xor     ecx, ecx
0x180032b33  test    eax, eax
0x180032b35  cmovnz  r8, rcx
0x180032b39  jmp     short loc_180032B45
0x180032b3b  lea     r8, [rsp+320h+var_2E0]; unsigned __int16 **
0x180032b40  mov     [rsp+320h+var_2E0], rax
0x180032b45  lea     rdx, aMspkiCertTempl; "msPKI-Cert-Template-OID"
0x180032b4c  mov     [rsp+320h+var_2D8], r14
0x180032b51  mov     rcx, rdi; this
0x180032b54  call    ?SetProperty@CCertTypeInfo@@QEAAJPEBGPEAPEAG@Z; CCertTypeInfo::SetProperty(ushort const *,ushort * *)
0x180032b59  mov     ebx, eax
0x180032b5b  test    eax, eax
0x180032b5d  jz      short loc_180032B69
0x180032b5f  mov     ecx, 5560328h
0x180032b64  jmp     loc_180032CFE
0x180032b69  mov     ebx, 2
0x180032b6e  xor     ecx, ecx; uFlags
0x180032b70  mov     edx, ebx; uBytes
0x180032b72  call    cs:__imp_LocalAlloc
0x180032b78  mov     [rdi+28h], rax
0x180032b7c  mov     rcx, rax
0x180032b7f  test    rax, rax
0x180032b82  jnz     short loc_180032B95
0x180032b84  mov     edx, 8007000Eh
0x180032b89  mov     ecx, 55D0328h
0x180032b8e  mov     ebx, edx
0x180032b90  jmp     loc_180032D00
0x180032b95  movzx   eax, word ptr [rsi+28h]
0x180032b99  mov     [rcx], ax
0x180032b9c  mov     [rdi+20h], ebx
0x180032b9f  mov     [rdi+30h], r14d
0x180032ba3  mov     ecx, [rsi+2Ch]
0x180032ba6  mov     [rdi+38h], ecx
0x180032ba9  and     ecx, 880h
0x180032baf  mov     eax, [rsi+48h]
0x180032bb2  mov     [rdi+90h], eax
0x180032bb8  mov     eax, [rsi+30h]
0x180032bbb  mov     [rdi+3Ch], eax
0x180032bbe  mov     eax, [rsi+4Ch]
0x180032bc1  mov     [rdi+40h], eax
0x180032bc4  mov     eax, [rsi+50h]
0x180032bc7  mov     [rdi+44h], eax
0x180032bca  mov     eax, [rsi+54h]
0x180032bcd  mov     [rdi+48h], eax
0x180032bd0  mov     eax, [rsi+58h]
0x180032bd3  mov     [rdi+4Ch], eax
0x180032bd6  mov     eax, [rsi+5Ch]
0x180032bd9  mov     [rdi+50h], eax
0x180032bdc  mov     eax, [rsi+60h]
0x180032bdf  mov     [rdi+54h], eax
0x180032be2  mov     eax, [rsi+64h]
0x180032be5  mov     [rdi+58h], eax
0x180032be8  mov     eax, [rsi+34h]
0x180032beb  mov     [rdi+18h], eax
0x180032bee  mov     eax, r14d
0x180032bf1  setnz   al
0x180032bf4  mov     [rdi+10h], eax
0x180032bf7  cmp     dword ptr [rdi+18h], 0FFFFFFFFh
0x180032bfb  jz      short loc_180032C08
0x180032bfd  test    ecx, ecx
0x180032bff  jz      short loc_180032C08
0x180032c01  mov     eax, 1
0x180032c06  jmp     short loc_180032C0A
0x180032c08  xor     eax, eax
0x180032c0a  mov     [rdi+14h], eax
0x180032c0d  lea     r8, [rsp+320h+var_2E0]; unsigned __int16 **
0x180032c12  movsxd  rax, dword ptr [rsi+40h]
0x180032c16  lea     rdx, aDistinguishedn; "distinguishedName"
0x180032c1d  imul    rcx, rax, 0FFFFFFFFFF676980h
0x180032c24  mov     [rsp+320h+var_2D8], r14
0x180032c29  mov     [rdi+68h], rcx
0x180032c2d  movsxd  rax, dword ptr [rsi+44h]
0x180032c31  imul    rcx, rax, 0FFFFFFFFFF676980h
0x180032c38  mov     [rdi+70h], rcx
0x180032c3c  mov     rcx, rdi; this
0x180032c3f  mov     rax, [rsi]
0x180032c42  mov     [rsp+320h+var_2E0], rax
0x180032c47  call    ?SetProperty@CCertTypeInfo@@QEAAJPEBGPEAPEAG@Z; CCertTypeInfo::SetProperty(ushort const *,ushort * *)
0x180032c4c  mov     ebx, eax
0x180032c4e  test    eax, eax
0x180032c50  jz      short loc_180032C5C
0x180032c52  mov     ecx, 5820328h
0x180032c57  jmp     loc_180032CFE
0x180032c5c  lea     rdx, [rsp+320h+Sid]; void **
0x180032c61  mov     rcx, r12; unsigned __int16 *
0x180032c64  call    ?myGetSidFromDomain@@YAKPEAGPEAPEAX@Z; myGetSidFromDomain(ushort *,void * *)
0x180032c69  mov     ebx, eax
0x180032c6b  test    eax, eax
0x180032c6d  jz      short loc_180032C8D
0x180032c6f  jle     short loc_180032C7A
0x180032c71  movzx   ebx, ax
0x180032c74  or      ebx, 80070000h
0x180032c7a  mov     edx, ebx; int
0x180032c7c  mov     ecx, 5890328h; unsigned int
0x180032c81  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180032c86  mov     r14, [rsp+320h+Sid]
0x180032c8b  jmp     short loc_180032D05
0x180032c8d  mov     r14, [rsp+320h+Sid]
0x180032c92  lea     rdx, [rsp+320h+StringSid]; StringSid
0x180032c97  mov     rcx, r14; Sid
0x180032c9a  call    cs:__imp_ConvertSidToStringSidW
0x180032ca0  test    eax, eax
0x180032ca2  jnz     short loc_180032CB2
0x180032ca4  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x180032ca9  mov     ebx, eax
0x180032cab  mov     ecx, 58E0328h
0x180032cb0  jmp     short loc_180032CFE
0x180032cb2  mov     rax, [rsp+320h+StringSid]
0x180032cb7  lea     r9, [rsp+320h+hMem]; unsigned __int16 **
0x180032cbc  mov     rcx, [rsi+10h]; unsigned __int16 *
0x180032cc0  lea     rdx, [rsp+320h+var_300]; unsigned __int16 **
0x180032cc5  mov     r8d, 1; unsigned int
0x180032ccb  mov     [rsp+320h+var_300], rax
0x180032cd0  call    ?myFormatMessageFromString@@YAJPEBGPEAPEBGKPEAPEAG@Z; myFormatMessageFromString(ushort const *,ushort const * *,ulong,ushort * *)
0x180032cd5  mov     ebx, eax
0x180032cd7  test    eax, eax
0x180032cd9  jz      short loc_180032CE2
0x180032cdb  mov     ecx, 5930328h
0x180032ce0  jmp     short loc_180032CFE
0x180032ce2  mov     rcx, [rsp+320h+hMem]; unsigned __int16 *
0x180032ce7  lea     r8, [rdi+88h]; void **
0x180032cee  call    ?myGetSDFromTemplate@@YAJPEBG0PEAPEAX@Z; myGetSDFromTemplate(ushort const *,ushort const *,void * *)
0x180032cf3  mov     ebx, eax
0x180032cf5  test    eax, eax
0x180032cf7  jz      short loc_180032D05
0x180032cf9  mov     ecx, 5960328h; unsigned int
0x180032cfe  mov     edx, eax; int
0x180032d00  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x180032d05  mov     rcx, [rsp+320h+hMem]; hMem
0x180032d0a  test    rcx, rcx
0x180032d0d  jz      short loc_180032D15
0x180032d0f  call    cs:__imp_LocalFree
0x180032d15  mov     rcx, [rsp+320h+StringSid]; hMem
0x180032d1a  test    rcx, rcx
0x180032d1d  jz      short loc_180032D25
0x180032d1f  call    cs:__imp_LocalFree
0x180032d25  test    r14, r14
  ... truncated ...
```
