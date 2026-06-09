# RouterIdentityObjectOpen(ushort *,ulong,void * *)

- ea: `0x180017988`
- end: `0x180017eb1`
- name: `?RouterIdentityObjectOpen@@YAKPEAGKPEAPEAX@Z`
- size: `1321`
- prototype: `unsigned int __fastcall(unsigned __int16 *, unsigned int, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1800182a0`

## callees

- `0x18000def0`
- `0x180017988`
- `0x18001851c`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`

## import_xrefs

- `adsldpc!ADSICloseDSObject` at `0x180017da5`
- `adsldpc!ADSICloseDSObject` at `0x180017da5`
- `adsldpc!ADSICreateDSObject` at `0x180017d98`
- `adsldpc!ADSICreateDSObject` at `0x180017d98`
- `adsldpc!ADSIOpenDSObject` at `0x180017bda`
- `adsldpc!ADSIOpenDSObject` at `0x180017c34`
- `adsldpc!ADSIOpenDSObject` at `0x180017df3`
- `adsldpc!ADSIOpenDSObject` at `0x180017bda`
- `adsldpc!ADSIOpenDSObject` at `0x180017c34`
- `adsldpc!ADSIOpenDSObject` at `0x180017df3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017b4b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180017ab5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180017b7c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180017ab5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180017b7c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017e10`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017e2c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017e10`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017e2c`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180017b22`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x180017b22`
- `netutils!NetApiBufferFree` at `0x180017e3c`
- `netutils!NetApiBufferFree` at `0x180017e3c`
- `logoncli!DsGetDcNameW` at `0x1800179ff`
- `logoncli!DsGetDcNameW` at `0x1800179ff`
- `Secur32!GetComputerObjectNameW` at `0x180017afc`
- `Secur32!GetComputerObjectNameW` at `0x180017b41`
- `Secur32!GetComputerObjectNameW` at `0x180017afc`
- `Secur32!GetComputerObjectNameW` at `0x180017b41`

## string_xrefs

- `0x180017e56`: `RouterIdentityObjectOpen returned %d`

## pseudocode

```c
__int64 __fastcall RouterIdentityObjectOpen(unsigned __int16 *a1, char a2, void **a3)
{
  DWORD DcNameW; // eax
  DWORD LastError; // ebx
  WCHAR *v7; // rax
  WCHAR *v8; // rdi
  SIZE_T v9; // r9
  WCHAR *v10; // rax
  __int64 v11; // rax
  SIZE_T v12; // r14
  wchar_t *v13; // rsi
  int v14; // ecx
  int v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rcx
  ULONG Flags[2]; // [rsp+20h] [rbp-E0h]
  PDOMAIN_CONTROLLER_INFOW *DomainControllerInfo; // [rsp+28h] [rbp-D8h]
  ULONG nSize; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+48h] [rbp-B8h] BYREF
  PDOMAIN_CONTROLLER_INFOW v26; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v27; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+68h] [rbp-98h]
  const wchar_t *v29; // [rsp+70h] [rbp-90h] BYREF
  int v30; // [rsp+78h] [rbp-88h]
  int v31; // [rsp+7Ch] [rbp-84h]
  __int128 *v32; // [rsp+80h] [rbp-80h]
  int v33; // [rsp+88h] [rbp-78h]
  const wchar_t *v34; // [rsp+90h] [rbp-70h]
  int v35; // [rsp+98h] [rbp-68h]
  int v36; // [rsp+9Ch] [rbp-64h]
  int *v37; // [rsp+A0h] [rbp-60h]
  unsigned int v38; // [rsp+A8h] [rbp-58h]
  int v39; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v40[9]; // [rsp+B8h] [rbp-48h]
  wchar_t pszDest[56]; // [rsp+100h] [rbp+0h] BYREF
  wchar_t v42[56]; // [rsp+170h] [rbp+70h] BYREF
  wchar_t v43[56]; // [rsp+1E0h] [rbp+E0h] BYREF
  int v44; // [rsp+250h] [rbp+150h] BYREF
  _BYTE v45[2044]; // [rsp+254h] [rbp+154h] BYREF

  v26 = 0;
  nSize = 0;
  v44 = 0;
  memset_0(v45, 0, sizeof(v45));
  DcNameW = DsGetDcNameW(0, 0, 0, 0, 0x1010u, &v26);
  LastError = DcNameW;
  if ( DcNameW )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
    {
      LOWORD(v44) = 0;
      FormatRRASErrorString(&v44, L"No DS located, DsGetDcName()=%d", DcNameW);
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceError, &v44);
    }
    goto LABEL_39;
  }
  if ( (v26->Flags & 0x10) == 0 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceError, L"No DS located");
    LastError = 1908;
    goto LABEL_39;
  }
  nSize = 200;
  v7 = (WCHAR *)HeapAlloc(hHeap, 8u, 0x190u);
  v8 = v7;
  if ( v7 )
  {
    if ( !GetComputerObjectNameW(NameFullyQualifiedDN, v7, &nSize) )
    {
      v9 = 2LL * ++nSize;
      v10 = (WCHAR *)HeapReAlloc(hHeap, 8u, v8, v9);
      if ( !v10 )
      {
        LastError = 8;
LABEL_38:
        HeapFree(hHeap, 0, v8);
        goto LABEL_39;
      }
      v8 = v10;
      if ( !GetComputerObjectNameW(NameFullyQualifiedDN, v10, &nSize) )
      {
        LastError = GetLastError();
        goto LABEL_38;
      }
    }
    v11 = -1;
    do
      ++v11;
    while ( v8[v11] );
    v12 = (unsigned int)(2 * v11 + 58);
    v13 = (wchar_t *)HeapAlloc(hHeap, 8u, v12);
    if ( !v13 )
    {
      LastError = 8;
      goto LABEL_37;
    }
    StringCbPrintfW(v13, v12, L"%s%s%s%s", L"LDAP://", L"CN=RouterIdentity", L",", v8);
    v14 = ADSIOpenDSObject(v13, 0, 0, 0, a3);
    if ( v14 == -2147016656 )
    {
      v25 = 0;
      v28 = 0;
      v27 = 0;
      StringCbPrintfW(v13, v12, L"%s%s", L"LDAP://", v8);
      v15 = ADSIOpenDSObject(v13, 0, 0, 0, &v25);
      if ( v15 < 0 )
      {
        LastError = (unsigned __int16)v15;
LABEL_36:
        HeapFree(hHeap, 0, v13);
LABEL_37:
        if ( !v8 )
          goto LABEL_39;
        goto LABEL_38;
      }
      v33 = 1;
      LODWORD(v27) = 3;
      *((_QWORD *)&v27 + 1) = L"RRASAdministrationConnectionPoint";
      v29 = L"ObjectClass";
      v32 = &v27;
      v16 = 0;
      v30 = 3;
      v31 = 3;
      if ( (a2 & 1) != 0 )
      {
        LODWORD(DomainControllerInfo) = 602;
        Flags[0] = 6;
        StringCbPrintfW(pszDest, 0x64u, L"%d:%d:%d", 311, *(_QWORD *)Flags, DomainControllerInfo);
        v39 = 3;
        v40[0] = pszDest;
        v16 = 1;
      }
      if ( (a2 & 2) != 0 )
      {
        LODWORD(DomainControllerInfo) = 601;
        Flags[0] = 6;
        StringCbPrintfW(v42, 0x64u, L"%d:%d:%d", 311, *(_QWORD *)Flags, DomainControllerInfo);
        v17 = v16++;
        v18 = 3 * v17;
        LODWORD(v40[v18]) = 3;
        v40[v18] = v42;
      }
      if ( (a2 & 4) != 0 )
      {
        LODWORD(DomainControllerInfo) = 603;
        Flags[0] = 6;
        StringCbPrintfW(v43, 0x64u, L"%d:%d:%d", 311, *(_QWORD *)Flags, DomainControllerInfo);
        v19 = v16++;
        v20 = 3 * v19;
        LODWORD(v40[v20]) = 3;
        v40[v20] = v43;
      }
      v34 = L"MsRRASAttribute";
      v35 = 3;
      v36 = 3;
      v37 = &v39;
      v38 = v16;
      LastError = ADSICreateDSObject(v25, L"CN=RouterIdentity", &v29, 2);
      ADSICloseDSObject(v25);
      if ( (LastError & 0x80000000) != 0 )
      {
        LastError = (unsigned __int16)LastError;
        goto LABEL_36;
      }
      StringCbPrintfW(v13, v12, L"%s%s%s%s", L"LDAP://", L"CN=RouterIdentity", L",", v8);
      v14 = ADSIOpenDSObject(v13, 0, 0, 0, a3);
    }
    LastError = (unsigned __int16)v14;
    if ( v14 >= 0 )
      LastError = 0;
    goto LABEL_36;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasDimTraceError,
      L"Memory exhausted -- unable to continue");
  LastError = 8;
LABEL_39:
  if ( v26 )
    NetApiBufferFree(v26);
  if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
  {
    LOWORD(v44) = 0;
    FormatRRASErrorString(&v44, L"RouterIdentityObjectOpen returned %d", LastError);
    if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceInfo, &v44);
  }
  return LastError;
}

```

## disassembly

```asm
0x180017988  push    rbp
0x18001798a  push    rbx
0x18001798b  push    rsi
0x18001798c  push    rdi
0x18001798d  push    r12
0x18001798f  push    r13
0x180017991  push    r14
0x180017993  push    r15
0x180017995  lea     rbp, [rsp-968h]
0x18001799d  sub     rsp, 0A68h
0x1800179a4  mov     rax, cs:__security_cookie
0x1800179ab  xor     rax, rsp
0x1800179ae  mov     [rbp+9A0h+var_50], rax
0x1800179b5  xor     r13d, r13d
0x1800179b8  lea     rcx, [rbp+9A0h+var_84C]; void *
0x1800179bf  mov     r12, r8
0x1800179c2  mov     [rsp+0AA0h+var_A50], r13
0x1800179c7  mov     r15d, edx
0x1800179ca  mov     [rsp+0AA0h+nSize], r13d
0x1800179cf  xor     edx, edx; Val
0x1800179d1  mov     [rbp+9A0h+var_850], r13d
0x1800179d8  mov     r8d, 7FCh; Size
0x1800179de  call    memset_0
0x1800179e3  lea     rax, [rsp+0AA0h+var_A50]
0x1800179e8  xor     r9d, r9d; SiteName
0x1800179eb  mov     [rsp+0AA0h+DomainControllerInfo], rax; DomainControllerInfo
0x1800179f0  xor     r8d, r8d; DomainGuid
0x1800179f3  xor     edx, edx; DomainName
0x1800179f5  mov     [rsp+0AA0h+Flags], 1010h; Flags
0x1800179fd  xor     ecx, ecx; ComputerName
0x1800179ff  call    cs:__imp_DsGetDcNameW
0x180017a05  lea     esi, [r13+8]
0x180017a09  mov     ebx, eax
0x180017a0b  test    eax, eax
0x180017a0d  jz      short loc_180017A66
0x180017a0f  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180017a16  jz      loc_180017E32
0x180017a1c  mov     r8d, eax
0x180017a1f  mov     word ptr [rbp+9A0h+var_850], r13w
0x180017a27  lea     rdx, aNoDsLocatedDsg; "No DS located, DsGetDcName()=%d"
0x180017a2e  lea     rcx, [rbp+9A0h+var_850]
0x180017a35  call    FormatRRASErrorString
0x180017a3a  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180017a41  jz      loc_180017E32
0x180017a47  lea     r8, [rbp+9A0h+var_850]
0x180017a4e  lea     rdx, RasDimTraceError
0x180017a55  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180017a5c  call    McTemplateU0z_EventWriteTransfer
0x180017a61  jmp     loc_180017E32
0x180017a66  mov     rax, [rsp+0AA0h+var_A50]
0x180017a6b  test    byte ptr [rax+38h], 10h
0x180017a6f  jnz     short loc_180017A9E
0x180017a71  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180017a78  jz      short loc_180017A94
0x180017a7a  lea     r8, aNoDsLocated; "No DS located"
0x180017a81  lea     rdx, RasDimTraceError
0x180017a88  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180017a8f  call    McTemplateU0z_EventWriteTransfer
0x180017a94  mov     ebx, 774h
0x180017a99  jmp     loc_180017E32
0x180017a9e  mov     rcx, cs:hHeap; hHeap
0x180017aa5  mov     r8d, 190h; dwBytes
0x180017aab  mov     edx, esi; dwFlags
0x180017aad  mov     [rsp+0AA0h+nSize], 0C8h
0x180017ab5  call    cs:__imp_HeapAlloc
0x180017abb  mov     rdi, rax
0x180017abe  test    rax, rax
0x180017ac1  jnz     short loc_180017AED
0x180017ac3  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180017aca  jz      short loc_180017AE6
0x180017acc  lea     r8, aMemoryExhauste; "Memory exhausted -- unable to continue"
0x180017ad3  lea     rdx, RasDimTraceError
0x180017ada  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180017ae1  call    McTemplateU0z_EventWriteTransfer
0x180017ae6  mov     ebx, esi
0x180017ae8  jmp     loc_180017E32
0x180017aed  mov     ebx, 1
0x180017af2  lea     r8, [rsp+0AA0h+nSize]; nSize
0x180017af7  mov     ecx, ebx; NameFormat
0x180017af9  mov     rdx, rdi; lpNameBuffer
0x180017afc  call    cs:__imp_GetComputerObjectNameW
0x180017b02  test    al, al
0x180017b04  jnz     short loc_180017B58
0x180017b06  mov     eax, [rsp+0AA0h+nSize]
0x180017b0a  mov     r8, rdi; lpMem
0x180017b0d  mov     rcx, cs:hHeap; hHeap
0x180017b14  add     eax, ebx
0x180017b16  mov     r9d, eax
0x180017b19  mov     edx, esi; dwFlags
0x180017b1b  add     r9, r9; dwBytes
0x180017b1e  mov     [rsp+0AA0h+nSize], eax
0x180017b22  call    cs:__imp_HeapReAlloc
0x180017b28  test    rax, rax
0x180017b2b  jnz     short loc_180017B34
0x180017b2d  mov     ebx, esi
0x180017b2f  jmp     loc_180017E20
0x180017b34  lea     r8, [rsp+0AA0h+nSize]; nSize
0x180017b39  mov     rdx, rax; lpNameBuffer
0x180017b3c  mov     ecx, ebx; NameFormat
0x180017b3e  mov     rdi, rax
0x180017b41  call    cs:__imp_GetComputerObjectNameW
0x180017b47  test    al, al
0x180017b49  jnz     short loc_180017B58
0x180017b4b  call    cs:__imp_GetLastError
0x180017b51  mov     ebx, eax
0x180017b53  jmp     loc_180017E20
0x180017b58  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017b5c  inc     rax
0x180017b5f  cmp     [rdi+rax*2], r13w
0x180017b64  jnz     short loc_180017B5C
0x180017b66  mov     rcx, cs:hHeap; hHeap
0x180017b6d  lea     eax, ds:3Ah[rax*2]
0x180017b74  mov     r8d, eax; dwBytes
0x180017b77  mov     edx, esi; dwFlags
0x180017b79  mov     r14d, eax
0x180017b7c  call    cs:__imp_HeapAlloc
0x180017b82  mov     rsi, rax
0x180017b85  test    rax, rax
0x180017b88  jnz     short loc_180017B94
0x180017b8a  lea     esi, [rax+8]
0x180017b8d  mov     ebx, esi
0x180017b8f  jmp     loc_180017E1B
0x180017b94  lea     rax, asc_180057150; ","
0x180017b9b  mov     [rsp+0AA0h+var_A70], rdi
0x180017ba0  mov     [rsp+0AA0h+DomainControllerInfo], rax
0x180017ba5  lea     r9, aLdap; "LDAP://"
0x180017bac  lea     rax, aCnRouteridenti; "CN=RouterIdentity"
0x180017bb3  mov     rdx, r14; cbDest
0x180017bb6  lea     r8, aSSSS; "%s%s%s%s"
0x180017bbd  mov     qword ptr [rsp+0AA0h+Flags], rax
0x180017bc2  mov     rcx, rsi; pszDest
0x180017bc5  call    StringCbPrintfW
0x180017bca  xor     r9d, r9d
0x180017bcd  mov     qword ptr [rsp+0AA0h+Flags], r12
0x180017bd2  xor     r8d, r8d
0x180017bd5  xor     edx, edx
0x180017bd7  mov     rcx, rsi
0x180017bda  call    cs:__imp_ADSIOpenDSObject
0x180017be0  mov     ecx, eax
0x180017be2  cmp     eax, 80072030h
0x180017be7  jnz     loc_180017DFB
0x180017bed  xorps   xmm0, xmm0
0x180017bf0  mov     [rsp+0AA0h+var_A58], r13
0x180017bf5  xor     eax, eax
0x180017bf7  mov     qword ptr [rsp+0AA0h+Flags], rdi
0x180017bfc  lea     r9, aLdap; "LDAP://"
0x180017c03  mov     [rsp+0AA0h+var_A38], rax
0x180017c08  lea     r8, aSS; "%s%s"
0x180017c0f  mov     rdx, r14; cbDest
0x180017c12  mov     rcx, rsi; pszDest
0x180017c15  movups  [rsp+0AA0h+var_A48], xmm0
0x180017c1a  call    StringCbPrintfW
0x180017c1f  lea     rax, [rsp+0AA0h+var_A58]
0x180017c24  xor     r9d, r9d
0x180017c27  xor     r8d, r8d
0x180017c2a  mov     qword ptr [rsp+0AA0h+Flags], rax
0x180017c2f  xor     edx, edx
0x180017c31  mov     rcx, rsi
0x180017c34  call    cs:__imp_ADSIOpenDSObject
0x180017c3a  test    eax, eax
0x180017c3c  jns     short loc_180017C46
0x180017c3e  movzx   ebx, ax
0x180017c41  jmp     loc_180017E04
0x180017c46  mov     [rbp+9A0h+var_A18], 1
0x180017c4d  mov     edx, 3
0x180017c52  mov     dword ptr [rsp+0AA0h+var_A48], edx
0x180017c56  lea     rax, aRrasadministra; "RRASAdministrationConnectionPoint"
0x180017c5d  mov     qword ptr [rsp+0AA0h+var_A48+8], rax
0x180017c62  lea     rax, aObjectclass; "ObjectClass"
0x180017c69  mov     [rsp+0AA0h+var_A30], rax
0x180017c6e  lea     rax, [rsp+0AA0h+var_A48]
0x180017c73  mov     [rbp+9A0h+var_A20], rax
0x180017c77  mov     ebx, r13d
0x180017c7a  mov     [rsp+0AA0h+var_A28], edx
0x180017c7e  mov     [rsp+0AA0h+var_A24], edx
0x180017c82  test    r15b, 1
0x180017c86  jz      short loc_180017CC6
0x180017c88  mov     dword ptr [rsp+0AA0h+DomainControllerInfo], 25Ah
0x180017c90  lea     r8, aDDD; "%d:%d:%d"
0x180017c97  mov     r9d, 137h
0x180017c9d  mov     [rsp+0AA0h+Flags], 6
0x180017ca5  mov     edx, 64h ; 'd'; cbDest
0x180017caa  lea     rcx, [rbp+9A0h+pszDest]; pszDest
0x180017cae  call    StringCbPrintfW
0x180017cb3  mov     edx, 3
0x180017cb8  lea     rax, [rbp+9A0h+pszDest]
0x180017cbc  mov     [rbp+9A0h+var_9F0], edx
0x180017cbf  mov     [rbp+9A0h+var_9E8], rax
0x180017cc3  lea     ebx, [rdx-2]
0x180017cc6  test    r15b, 2
0x180017cca  jz      short loc_180017D11
0x180017ccc  mov     dword ptr [rsp+0AA0h+DomainControllerInfo], 259h
0x180017cd4  lea     r8, aDDD; "%d:%d:%d"
0x180017cdb  mov     r9d, 137h
0x180017ce1  mov     [rsp+0AA0h+Flags], 6
0x180017ce9  mov     edx, 64h ; 'd'; cbDest
0x180017cee  lea     rcx, [rbp+9A0h+var_930]; pszDest
0x180017cf2  call    StringCbPrintfW
0x180017cf7  mov     eax, ebx
0x180017cf9  mov     edx, 3
0x180017cfe  inc     ebx
0x180017d00  lea     rcx, [rax+rax*2]
0x180017d04  lea     rax, [rbp+9A0h+var_930]
0x180017d08  mov     [rbp+rcx*8+9A0h+var_9F0], edx
0x180017d0c  mov     [rbp+rcx*8+9A0h+var_9E8], rax
0x180017d11  test    r15b, 4
0x180017d15  jz      short loc_180017D62
0x180017d17  mov     dword ptr [rsp+0AA0h+DomainControllerInfo], 25Bh
0x180017d1f  lea     r8, aDDD; "%d:%d:%d"
0x180017d26  mov     r9d, 137h
0x180017d2c  mov     [rsp+0AA0h+Flags], 6
0x180017d34  mov     edx, 64h ; 'd'; cbDest
0x180017d39  lea     rcx, [rbp+9A0h+var_8C0]; pszDest
0x180017d40  call    StringCbPrintfW
0x180017d45  mov     eax, ebx
0x180017d47  mov     edx, 3
0x180017d4c  inc     ebx
0x180017d4e  lea     rcx, [rax+rax*2]
0x180017d52  lea     rax, [rbp+9A0h+var_8C0]
0x180017d59  mov     [rbp+rcx*8+9A0h+var_9F0], edx
0x180017d5d  mov     [rbp+rcx*8+9A0h+var_9E8], rax
0x180017d62  mov     rcx, [rsp+0AA0h+var_A58]
0x180017d67  lea     rax, aMsrrasattribut; "MsRRASAttribute"
0x180017d6e  mov     [rbp+9A0h+var_A10], rax
0x180017d72  lea     r15, aCnRouteridenti; "CN=RouterIdentity"
0x180017d79  lea     rax, [rbp+9A0h+var_9F0]
0x180017d7d  mov     [rbp+9A0h+var_A08], edx
0x180017d80  mov     [rbp+9A0h+var_A04], edx
0x180017d83  lea     r8, [rsp+0AA0h+var_A30]
0x180017d88  mov     r9d, 2
0x180017d8e  mov     [rbp+9A0h+var_A00], rax
0x180017d92  mov     rdx, r15
0x180017d95  mov     [rbp+9A0h+var_9F8], ebx
0x180017d98  call    cs:__imp_ADSICreateDSObject
0x180017d9e  mov     rcx, [rsp+0AA0h+var_A58]
0x180017da3  mov     ebx, eax
0x180017da5  call    cs:__imp_ADSICloseDSObject
0x180017dab  test    ebx, ebx
0x180017dad  jns     short loc_180017DB4
0x180017daf  movzx   ebx, bx
0x180017db2  jmp     short loc_180017E04
0x180017db4  lea     rax, asc_180057150; ","
0x180017dbb  mov     [rsp+0AA0h+var_A70], rdi
0x180017dc0  mov     [rsp+0AA0h+DomainControllerInfo], rax
0x180017dc5  lea     r9, aLdap; "LDAP://"
0x180017dcc  lea     r8, aSSSS; "%s%s%s%s"
0x180017dd3  mov     qword ptr [rsp+0AA0h+Flags], r15
0x180017dd8  mov     rdx, r14; cbDest
0x180017ddb  mov     rcx, rsi; pszDest
0x180017dde  call    StringCbPrintfW
0x180017de3  xor     r9d, r9d
0x180017de6  mov     qword ptr [rsp+0AA0h+Flags], r12
0x180017deb  xor     r8d, r8d
0x180017dee  xor     edx, edx
0x180017df0  mov     rcx, rsi
0x180017df3  call    cs:__imp_ADSIOpenDSObject
0x180017df9  mov     ecx, eax
0x180017dfb  test    ecx, ecx
0x180017dfd  movzx   ebx, cx
0x180017e00  cmovns  ebx, r13d
0x180017e04  mov     rcx, cs:hHeap; hHeap
0x180017e0b  mov     r8, rsi; lpMem
0x180017e0e  xor     edx, edx; dwFlags
0x180017e10  call    cs:__imp_HeapFree
0x180017e16  mov     esi, 8
0x180017e1b  test    rdi, rdi
0x180017e1e  jz      short loc_180017E32
0x180017e20  mov     rcx, cs:hHeap; hHeap
0x180017e27  mov     r8, rdi; lpMem
0x180017e2a  xor     edx, edx; dwFlags
0x180017e2c  call    cs:__imp_HeapFree
0x180017e32  mov     rcx, [rsp+0AA0h+var_A50]; Buffer
0x180017e37  test    rcx, rcx
0x180017e3a  jz      short loc_180017E42
0x180017e3c  call    cs:__imp_NetApiBufferFree
0x180017e42  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x180017e49  jz      short loc_180017E8C
0x180017e4b  mov     r8d, ebx
0x180017e4e  mov     word ptr [rbp+9A0h+var_850], r13w
0x180017e56  lea     rdx, aRouteridentity; "RouterIdentityObjectOpen returned %d"
0x180017e5d  lea     rcx, [rbp+9A0h+var_850]
0x180017e64  call    FormatRRASErrorString
0x180017e69  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, sil
0x180017e70  jz      short loc_180017E8C
0x180017e72  lea     r8, [rbp+9A0h+var_850]
0x180017e79  lea     rdx, RasDimTraceInfo
0x180017e80  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180017e87  call    McTemplateU0z_EventWriteTransfer
0x180017e8c  mov     eax, ebx
0x180017e8e  mov     rcx, [rbp+9A0h+var_50]
0x180017e95  xor     rcx, rsp; StackCookie
0x180017e98  call    __security_check_cookie
0x180017e9d  add     rsp, 0A68h
0x180017ea4  pop     r15
0x180017ea6  pop     r14
0x180017ea8  pop     r13
0x180017eaa  pop     r12
0x180017eac  pop     rdi
0x180017ead  pop     rsi
0x180017eae  pop     rbx
  ... truncated ...
```
