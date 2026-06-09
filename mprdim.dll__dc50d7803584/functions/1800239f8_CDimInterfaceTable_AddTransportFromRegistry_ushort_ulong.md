# CDimInterfaceTable::AddTransportFromRegistry(ushort *,ulong)

- ea: `0x1800239f8`
- end: `0x180023e4c`
- name: `?AddTransportFromRegistry@CDimInterfaceTable@@QEAAKPEAGK@Z`
- size: `1108`
- prototype: `__int64 __fastcall(CDimInterfaceTable *this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002de10`

## callees

- `0x1800014d0`
- `0x180002130`
- `0x180005358`
- `0x180005550`
- `0x180005670`
- `0x180006ce0`
- `0x18000b604`
- `0x18000c0c4`
- `0x18000def0`
- `0x18001b4b0`
- `0x18002230c`
- `0x180022fa8`
- `0x1800239f8`
- `0x18002b23c`
- `0x18002b4ac`
- `0x18002d514`
- `0x180033e60`
- `0x1800357c8`
- `0x180045d40`
- `0x180046e06`
- `0x180046e2a`
- `0x180046e70`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180023e28`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180023e28`
- `rtutils!RouterLogEventStringW` at `0x180023c9d`
- `rtutils!RouterLogEventStringW` at `0x180023d51`
- `rtutils!RouterLogEventStringW` at `0x180023c9d`
- `rtutils!RouterLogEventStringW` at `0x180023d51`
- `ADVAPI32!RegCloseKey` at `0x180023b20`
- `ADVAPI32!RegCloseKey` at `0x180023dae`
- `ADVAPI32!RegCloseKey` at `0x180023dd2`
- `ADVAPI32!RegCloseKey` at `0x180023b20`
- `ADVAPI32!RegCloseKey` at `0x180023dae`
- `ADVAPI32!RegCloseKey` at `0x180023dd2`

## string_xrefs

- `0x180023ae0`: `CDimInterfaceTable::AddTransportFromRegistry: Error %d occured while enumerating Routing Domains from config store.`
- `0x180023cbf`: `Unable to load the interface %s from the registry. The following error occured %d`
- `0x180023d70`: `Unable to load the interface %s from the registry. The following error occured %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDimInterfaceTable::AddTransportFromRegistry(CDimInterfaceTable *this, unsigned __int16 *a2, int a3)
{
  CDimInterfaceTable *v4; // r15
  _QWORD *v5; // rax
  DWORD dwErrorCode; // esi
  DWORD v7; // eax
  unsigned int v9; // ebx
  char *v10; // rdi
  unsigned int i; // r14d
  __int64 v12; // rax
  _QWORD *v13; // rdi
  _QWORD *v14; // rbx
  struct _GUID *v15; // rdx
  CDimInterfaceTable *v16; // rcx
  unsigned int j; // r14d
  unsigned __int16 *v18; // r8
  unsigned __int16 *v19; // r8
  __int64 v20; // rcx
  _QWORD *k; // rax
  unsigned int v22; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v23; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  __int128 Buf1; // [rsp+58h] [rbp-A8h] BYREF
  GUID *pExceptionObject; // [rsp+68h] [rbp-98h] BYREF
  std::tr1::_Ref_count_base *v27; // [rsp+70h] [rbp-90h]
  _BYTE v28[8]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD *v29; // [rsp+88h] [rbp-78h]
  __int64 v30; // [rsp+90h] [rbp-70h]
  unsigned __int16 v31[264]; // [rsp+A0h] [rbp-60h] BYREF
  int v32; // [rsp+2B0h] [rbp+1B0h] BYREF
  _BYTE v33[2044]; // [rsp+2B4h] [rbp+1B4h] BYREF

  v4 = g_pCDimInterfaceTable;
  hKey = 0;
  v22 = 0;
  v30 = 0;
  v5 = operator new(0x30u);
  if ( !v5 )
  {
    *(_QWORD *)&Buf1 = 0;
    exception::exception((exception *)&pExceptionObject, (const char *const *)&Buf1);
    pExceptionObject = (GUID *)&std::bad_alloc::`vftable';
    throw (std::bad_alloc *)&pExceptionObject;
  }
  dwErrorCode = 0;
  v29 = v5;
  *v5 = v5;
  v5[1] = v29;
  v5[2] = v29;
  *((_WORD *)v5 + 20) = 257;
  v32 = 0;
  memset_0(v33, 0, sizeof(v33));
  std::_Tree<std::_Tset_traits<_GUID,CDimInterfaceTable::_ROUTINGDOMAIN_COMP,std::allocator<_GUID>,0>>::insert(
    v28,
    &pExceptionObject);
  if ( *((_BYTE *)v4 + 116) )
  {
    LODWORD(v23) = 0;
    *(_QWORD *)&Buf1 = 0;
    v7 = EnumerateRoutingDomains(1u, (unsigned int *)&v23, (struct _MPRI_ROUTING_DOMAIN_INFO_EX **)&Buf1);
    dwErrorCode = v7;
    if ( v7 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      {
        LOWORD(v32) = 0;
        FormatRRASErrorString(
          &v32,
          L"CDimInterfaceTable::AddTransportFromRegistry: Error %d occured while enumerating Routing Domains from config store.",
          v7);
        if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceError, &v32);
      }
      goto LABEL_7;
    }
    v9 = 0;
    v10 = (char *)Buf1;
    for ( i = (unsigned int)v23; v9 < i; ++v9 )
    {
      v12 = std::_Tree_val<std::_Tset_traits<_GUID,CDimInterfaceTable::_ROUTINGDOMAIN_COMP,std::allocator<_GUID>,0>>::_Buynode<_GUID &>(
              (__int64)v28,
              &v10[540 * v9 + 520]);
      std::_Tree<std::_Tset_traits<_GUID,CDimInterfaceTable::_ROUTINGDOMAIN_COMP,std::allocator<_GUID>,0>>::_Linsert(
        (__int64)v28,
        (__int64)&pExceptionObject,
        v12);
    }
    MprCommonFree(v10);
  }
  v13 = v29;
  v14 = (_QWORD *)*v29;
  while ( v14 != v13 )
  {
    Buf1 = *(_OWORD *)(v14 + 3);
    v15 = !memcmp_0(&Buf1, &GUID_NULL, 0x10u) ? 0LL : (struct _GUID *)&Buf1;
    dwErrorCode = CDimInterfaceTable::RegOpenInterfacesKey(v4, v15, &hKey, &v22);
    if ( dwErrorCode )
      break;
    for ( j = 0; j < v22; ++j )
    {
      v23 = 0;
      dwErrorCode = CDimInterfaceTable::RegOpenInterfaceKey(v16, hKey, j, &v23, v31);
      if ( !dwErrorCode )
      {
        CDimInterfaceTable::AcquireShared(v4);
        CDimInterfaceTable::GetInterfaceByName(v4, &pExceptionObject, v31, 0);
        if ( pExceptionObject )
        {
          dwErrorCode = CDimInterface::AddTransportFromRegistry(pExceptionObject, a3, v23);
        }
        else
        {
          v18 = v31;
          *(_QWORD *)&Buf1 = v31;
          if ( dword_180070F40 )
          {
            RouterLogEventStringW(
              hLogHandle,
              dwErrorCode + 1,
              0x4E89u,
              dwErrorCode + 1,
              (LPWSTR *)&Buf1,
              0x389u,
              dwErrorCode + 1);
            v18 = (unsigned __int16 *)Buf1;
          }
          if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
          {
            LOWORD(v32) = 0;
            FormatRRASErrorString(
              &v32,
              L"Unable to load the interface %s from the registry. The following error occured %d",
              v18,
              905);
            if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceAdminError, &v32);
          }
        }
        CDimInterfaceTable::ReleaseShared(v4);
        if ( dwErrorCode )
        {
          v19 = v31;
          *(_QWORD *)&Buf1 = v31;
          if ( dword_180070F40 )
          {
            RouterLogEventStringW(hLogHandle, 1u, 0x4E89u, 1u, (LPWSTR *)&Buf1, dwErrorCode, 1u);
            v19 = (unsigned __int16 *)Buf1;
          }
          if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
          {
            LOWORD(v32) = 0;
            FormatRRASErrorString(
              &v32,
              L"Unable to load the interface %s from the registry. The following error occured %d",
              v19,
              dwErrorCode);
            if ( (Microsoft_Windows_RRASEnableBits & 1) != 0 )
              McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDimTraceAdminError, &v32);
          }
          dwErrorCode = 0;
        }
        RegCloseKey(v23);
        v16 = v27;
        if ( v27 )
          std::tr1::_Ref_count_base::_Decref(v27);
      }
    }
    RegCloseKey(hKey);
    hKey = 0;
    if ( !*((_BYTE *)v14 + 41) )
    {
      v20 = v14[2];
      if ( *(_BYTE *)(v20 + 41) )
      {
        for ( k = (_QWORD *)v14[1]; !*((_BYTE *)k + 41) && v14 == (_QWORD *)k[2]; k = (_QWORD *)k[1] )
          v14 = k;
      }
      else
      {
        k = std::_Tree_val<std::_Tset_traits<std::tr1::shared_ptr<CDimInterface>,CDimInterfaceTable::_SHARED_PTR_COMP,std::allocator<std::tr1::shared_ptr<CDimInterface>>,0>>::_Min((_QWORD *)v20);
      }
      v14 = k;
    }
  }
LABEL_7:
  if ( hKey )
    RegCloseKey(hKey);
  std::_Tree<std::_Tmap_traits<void *,void *,std::less<void *>,std::allocator<std::pair<void * const,void *>>,0>>::~_Tree<std::_Tmap_traits<void *,void *,std::less<void *>,std::allocator<std::pair<void * const,void *>>,0>>(v28);
  return dwErrorCode;
}

```

## disassembly

```asm
0x1800239f8  push    rbp
0x1800239fa  push    rbx
0x1800239fb  push    rsi
0x1800239fc  push    rdi
0x1800239fd  push    r12
0x1800239ff  push    r13
0x180023a01  push    r14
0x180023a03  push    r15
0x180023a05  lea     rbp, [rsp-9C8h]
0x180023a0d  sub     rsp, 0AC8h
0x180023a14  mov     rax, cs:__security_cookie
0x180023a1b  xor     rax, rsp
0x180023a1e  mov     [rbp+0A00h+var_50], rax
0x180023a25  mov     r12d, r8d
0x180023a28  mov     r15, cs:?g_pCDimInterfaceTable@@3PEAVCDimInterfaceTable@@EA; CDimInterfaceTable * g_pCDimInterfaceTable
0x180023a2f  xor     r13d, r13d
0x180023a32  mov     [rsp+0B00h+hKey], r13
0x180023a37  mov     [rsp+0B00h+var_AC0], r13d
0x180023a3c  mov     [rbp+0A00h+var_A70], r13
0x180023a40  lea     ecx, [r13+30h]; Size
0x180023a44  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023a49  test    rax, rax
0x180023a4c  jz      loc_180023E19
0x180023a52  mov     esi, r13d
0x180023a55  mov     [rbp+0A00h+var_A78], rax
0x180023a59  mov     [rax], rax
0x180023a5c  mov     rcx, [rbp+0A00h+var_A78]
0x180023a60  mov     [rax+8], rcx
0x180023a64  mov     rcx, [rbp+0A00h+var_A78]
0x180023a68  mov     [rax+10h], rcx
0x180023a6c  mov     word ptr [rax+28h], 101h
0x180023a72  mov     [rbp+0A00h+var_850], r13d
0x180023a79  xor     edx, edx; Val
0x180023a7b  mov     r8d, 7FCh; Size
0x180023a81  lea     rcx, [rbp+0A00h+var_84C]; void *
0x180023a88  call    memset_0
0x180023a8d  lea     rdx, [rsp+0B00h+pExceptionObject]
0x180023a92  lea     rcx, [rbp+0A00h+var_A80]
0x180023a96  call    ?insert@?$_Tree@V?$_Tset_traits@U_GUID@@U_ROUTINGDOMAIN_COMP@CDimInterfaceTable@@V?$allocator@U_GUID@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@V?$_Tset_traits@U_GUID@@U_ROUTINGDOMAIN_COMP@CDimInterfaceTable@@V?$allocator@U_GUID@@@std@@$0A@@std@@@std@@@std@@_N@2@AEBU_GUID@@_N@Z; std::_Tree<std::_Tset_traits<_GUID,CDimInterfaceTable::_ROUTINGDOMAIN_COMP,std::allocator<_GUID>,0>>::insert(_GUID const &,bool)
0x180023a9b  cmp     [r15+74h], r13b
0x180023a9f  jz      loc_180023BA3
0x180023aa5  mov     dword ptr [rsp+0B00h+var_AB8], r13d
0x180023aaa  mov     qword ptr [rsp+0B00h+Buf1], r13
0x180023aaf  lea     r8, [rsp+0B00h+Buf1]; struct _MPRI_ROUTING_DOMAIN_INFO_EX **
0x180023ab4  lea     rdx, [rsp+0B00h+var_AB8]; unsigned int *
0x180023ab9  lea     ecx, [r13+1]; unsigned int
0x180023abd  call    EnumerateRoutingDomains
0x180023ac2  mov     esi, eax
0x180023ac4  test    eax, eax
0x180023ac6  jz      loc_180023B55
0x180023acc  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180023ad3  jz      short loc_180023B16
0x180023ad5  mov     word ptr [rbp+0A00h+var_850], r13w
0x180023add  mov     r8d, eax
0x180023ae0  lea     rdx, aCdiminterfacet_13; "CDimInterfaceTable::AddTransportFromReg"...
0x180023ae7  lea     rcx, [rbp+0A00h+var_850]
0x180023aee  call    FormatRRASErrorString
0x180023af3  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180023afa  jz      short loc_180023B16
0x180023afc  lea     r8, [rbp+0A00h+var_850]
0x180023b03  lea     rdx, RasDimTraceError
0x180023b0a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180023b11  call    McTemplateU0z_EventWriteTransfer
0x180023b16  mov     rcx, [rsp+0B00h+hKey]; hKey
0x180023b1b  test    rcx, rcx
0x180023b1e  jz      short loc_180023B27
0x180023b20  call    cs:__imp_RegCloseKey
0x180023b26  nop
0x180023b27  lea     rcx, [rbp+0A00h+var_A80]
0x180023b2b  call    ??1?$_Tree@V?$_Tmap_traits@PEAXPEAXU?$less@PEAX@std@@V?$allocator@U?$pair@QEAXPEAX@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<void *,void *,std::less<void *>,std::allocator<std::pair<void * const,void *>>,0>>::~_Tree<std::_Tmap_traits<void *,void *,std::less<void *>,std::allocator<std::pair<void * const,void *>>,0>>(void)
0x180023b30  mov     eax, esi
0x180023b32  mov     rcx, [rbp+0A00h+var_50]
0x180023b39  xor     rcx, rsp; StackCookie
0x180023b3c  call    __security_check_cookie
0x180023b41  add     rsp, 0AC8h
0x180023b48  pop     r15
0x180023b4a  pop     r14
0x180023b4c  pop     r13
0x180023b4e  pop     r12
0x180023b50  pop     rdi
0x180023b51  pop     rsi
0x180023b52  pop     rbx
0x180023b53  pop     rbp
0x180023b54  retn
0x180023b55  mov     ebx, r13d
0x180023b58  mov     rdi, qword ptr [rsp+0B00h+Buf1]
0x180023b5d  mov     r14d, dword ptr [rsp+0B00h+var_AB8]
0x180023b62  test    r14d, r14d
0x180023b65  jz      short loc_180023B9B
0x180023b67  mov     eax, ebx
0x180023b69  imul    rdx, rax, 21Ch
0x180023b70  add     rdx, 208h
0x180023b77  add     rdx, rdi
0x180023b7a  lea     rcx, [rbp+0A00h+var_A80]
0x180023b7e  call    ??$_Buynode@AEAU_GUID@@@?$_Tree_val@V?$_Tset_traits@U_GUID@@U_ROUTINGDOMAIN_COMP@CDimInterfaceTable@@V?$allocator@U_GUID@@@std@@$0A@@std@@@std@@QEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@U_GUID@@U_ROUTINGDOMAIN_COMP@CDimInterfaceTable@@V?$allocator@U_GUID@@@std@@$0A@@std@@@1@AEAU_GUID@@@Z; std::_Tree_val<std::_Tset_traits<_GUID,CDimInterfaceTable::_ROUTINGDOMAIN_COMP,std::allocator<_GUID>,0>>::_Buynode<_GUID &>(_GUID &)
0x180023b83  mov     r8, rax
0x180023b86  lea     rdx, [rsp+0B00h+pExceptionObject]
0x180023b8b  lea     rcx, [rbp+0A00h+var_A80]
0x180023b8f  call    ?_Linsert@?$_Tree@V?$_Tset_traits@U_GUID@@U_ROUTINGDOMAIN_COMP@CDimInterfaceTable@@V?$allocator@U_GUID@@@std@@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@V?$_Tset_traits@U_GUID@@U_ROUTINGDOMAIN_COMP@CDimInterfaceTable@@V?$allocator@U_GUID@@@std@@$0A@@std@@@std@@@std@@_N@2@PEAU_Node@?$_Tree_nod@V?$_Tset_traits@U_GUID@@U_ROUTINGDOMAIN_COMP@CDimInterfaceTable@@V?$allocator@U_GUID@@@std@@$0A@@std@@@2@_N@Z; std::_Tree<std::_Tset_traits<_GUID,CDimInterfaceTable::_ROUTINGDOMAIN_COMP,std::allocator<_GUID>,0>>::_Linsert(std::_Tree_nod<std::_Tset_traits<_GUID,CDimInterfaceTable::_ROUTINGDOMAIN_COMP,std::allocator<_GUID>,0>>::_Node *,bool)
0x180023b94  inc     ebx
0x180023b96  cmp     ebx, r14d
0x180023b99  jb      short loc_180023B67
0x180023b9b  mov     rcx, rdi; lpMem
0x180023b9e  call    MprCommonFree
0x180023ba3  mov     rdi, [rbp+0A00h+var_A78]
0x180023ba7  mov     rbx, [rdi]
0x180023baa  cmp     rbx, rdi
0x180023bad  jz      loc_180023B16
0x180023bb3  movups  xmm0, xmmword ptr [rbx+18h]
0x180023bb7  movdqu  [rsp+0B00h+Buf1], xmm0
0x180023bbd  mov     r8d, 10h; Size
0x180023bc3  lea     rdx, GUID_NULL; Buf2
0x180023bca  lea     rcx, [rsp+0B00h+Buf1]; Buf1
0x180023bcf  call    memcmp_0
0x180023bd4  lea     r9, [rsp+0B00h+var_AC0]; unsigned int *
0x180023bd9  lea     r8, [rsp+0B00h+hKey]; HKEY *
0x180023bde  mov     rcx, r15; this
0x180023be1  test    eax, eax
0x180023be3  jnz     short loc_180023BE9
0x180023be5  xor     edx, edx
0x180023be7  jmp     short loc_180023BEE
0x180023be9  lea     rdx, [rsp+0B00h+Buf1]; struct _GUID *
0x180023bee  call    ?RegOpenInterfacesKey@CDimInterfaceTable@@AEAAKPEAU_GUID@@AEAPEAUHKEY__@@AEAK@Z; CDimInterfaceTable::RegOpenInterfacesKey(_GUID *,HKEY__ * &,ulong &)
0x180023bf3  test    eax, eax
0x180023bf5  mov     esi, eax
0x180023bf7  jnz     loc_180023B16
0x180023bfd  mov     r14d, r13d
0x180023c00  cmp     r14d, [rsp+0B00h+var_AC0]
0x180023c05  jnb     loc_180023DCD
0x180023c0b  mov     [rsp+0B00h+var_AB8], r13
0x180023c10  lea     rax, [rbp+0A00h+var_A60]
0x180023c14  mov     [rsp+0B00h+plpszSubStringArray], rax; unsigned __int16 *
0x180023c19  lea     r9, [rsp+0B00h+var_AB8]; HKEY *
0x180023c1e  mov     r8d, r14d; unsigned int
0x180023c21  mov     rdx, [rsp+0B00h+hKey]; HKEY
0x180023c26  call    ?RegOpenInterfaceKey@CDimInterfaceTable@@AEAAKPEAUHKEY__@@KAEAPEAU2@PEAG@Z; CDimInterfaceTable::RegOpenInterfaceKey(HKEY__ *,ulong,HKEY__ * &,ushort *)
0x180023c2b  mov     esi, eax
0x180023c2d  test    eax, eax
0x180023c2f  jnz     loc_180023DC5
0x180023c35  mov     rcx, r15; this
0x180023c38  call    ?AcquireShared@CDimInterfaceTable@@UEAAXXZ; CDimInterfaceTable::AcquireShared(void)
0x180023c3d  xor     r9d, r9d
0x180023c40  lea     r8, [rbp+0A00h+var_A60]
0x180023c44  lea     rdx, [rsp+0B00h+pExceptionObject]
0x180023c49  mov     rcx, r15
0x180023c4c  call    ?GetInterfaceByName@CDimInterfaceTable@@QEAA?AV?$shared_ptr@VCDimInterface@@@tr1@std@@PEAG_N@Z; CDimInterfaceTable::GetInterfaceByName(ushort *,bool)
0x180023c51  nop
0x180023c52  mov     rcx, [rsp+0B00h+pExceptionObject]; this
0x180023c57  test    rcx, rcx
0x180023c5a  jnz     loc_180023CF7
0x180023c60  lea     r8, [rbp+0A00h+var_A60]
0x180023c64  mov     qword ptr [rsp+0B00h+Buf1], r8
0x180023c69  cmp     cs:dword_180070F40, r13d
0x180023c70  jbe     short loc_180023CA8
0x180023c72  lea     ecx, [rsi+1]
0x180023c75  mov     [rsp+0B00h+dwErrorIndex], ecx; dwErrorIndex
0x180023c79  mov     [rsp+0B00h+dwErrorCode], 389h; dwErrorCode
0x180023c81  lea     rax, [rsp+0B00h+Buf1]
0x180023c86  mov     [rsp+0B00h+plpszSubStringArray], rax; plpszSubStringArray
0x180023c8b  mov     r9d, ecx; dwSubStringCount
0x180023c8e  mov     r8d, 4E89h; dwMessageId
0x180023c94  mov     edx, ecx; dwEventType
0x180023c96  mov     rcx, cs:hLogHandle; hLogHandle
0x180023c9d  call    cs:__imp_RouterLogEventStringW
0x180023ca3  mov     r8, qword ptr [rsp+0B00h+Buf1]
0x180023ca8  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 1
0x180023caf  jz      short loc_180023D06
0x180023cb1  mov     word ptr [rbp+0A00h+var_850], r13w
0x180023cb9  mov     r9d, 389h
0x180023cbf  lea     rdx, aUnableToLoadTh_0; "Unable to load the interface %s from th"...
0x180023cc6  lea     rcx, [rbp+0A00h+var_850]
0x180023ccd  call    FormatRRASErrorString
0x180023cd2  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 1
0x180023cd9  jz      short loc_180023D06
0x180023cdb  lea     r8, [rbp+0A00h+var_850]
0x180023ce2  lea     rdx, RasDimTraceAdminError
0x180023ce9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180023cf0  call    McTemplateU0z_EventWriteTransfer
0x180023cf5  jmp     short loc_180023D06
0x180023cf7  mov     r8, [rsp+0B00h+var_AB8]; HKEY
0x180023cfc  mov     edx, r12d; unsigned int
0x180023cff  call    ?AddTransportFromRegistry@CDimInterface@@QEAAKKPEAUHKEY__@@@Z; CDimInterface::AddTransportFromRegistry(ulong,HKEY__ *)
0x180023d04  mov     esi, eax
0x180023d06  mov     rcx, r15; this
0x180023d09  call    ?ReleaseShared@CDimInterfaceTable@@UEAAXXZ; CDimInterfaceTable::ReleaseShared(void)
0x180023d0e  test    esi, esi
0x180023d10  jz      loc_180023DA9
0x180023d16  lea     r8, [rbp+0A00h+var_A60]
0x180023d1a  mov     qword ptr [rsp+0B00h+Buf1], r8
0x180023d1f  cmp     cs:dword_180070F40, r13d
0x180023d26  jbe     short loc_180023D5C
0x180023d28  mov     ecx, 1
0x180023d2d  mov     [rsp+0B00h+dwErrorIndex], ecx; dwErrorIndex
0x180023d31  mov     [rsp+0B00h+dwErrorCode], esi; dwErrorCode
0x180023d35  lea     rax, [rsp+0B00h+Buf1]
0x180023d3a  mov     [rsp+0B00h+plpszSubStringArray], rax; plpszSubStringArray
0x180023d3f  mov     r9d, ecx; dwSubStringCount
0x180023d42  mov     r8d, 4E89h; dwMessageId
0x180023d48  mov     edx, ecx; dwEventType
0x180023d4a  mov     rcx, cs:hLogHandle; hLogHandle
0x180023d51  call    cs:__imp_RouterLogEventStringW
0x180023d57  mov     r8, qword ptr [rsp+0B00h+Buf1]
0x180023d5c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 1
0x180023d63  jz      short loc_180023DA6
0x180023d65  mov     word ptr [rbp+0A00h+var_850], r13w
0x180023d6d  mov     r9d, esi
0x180023d70  lea     rdx, aUnableToLoadTh_0; "Unable to load the interface %s from th"...
0x180023d77  lea     rcx, [rbp+0A00h+var_850]
0x180023d7e  call    FormatRRASErrorString
0x180023d83  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 1
0x180023d8a  jz      short loc_180023DA6
0x180023d8c  lea     r8, [rbp+0A00h+var_850]
0x180023d93  lea     rdx, RasDimTraceAdminError
0x180023d9a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180023da1  call    McTemplateU0z_EventWriteTransfer
0x180023da6  mov     esi, r13d
0x180023da9  mov     rcx, [rsp+0B00h+var_AB8]; hKey
0x180023dae  call    cs:__imp_RegCloseKey
0x180023db4  nop
0x180023db5  mov     rcx, [rsp+0B00h+var_A90]; this
0x180023dba  test    rcx, rcx
0x180023dbd  jz      short loc_180023DC5
0x180023dbf  call    ?_Decref@_Ref_count_base@tr1@std@@QEAAXXZ; std::tr1::_Ref_count_base::_Decref(void)
0x180023dc4  nop
0x180023dc5  inc     r14d
0x180023dc8  jmp     loc_180023C00
0x180023dcd  mov     rcx, [rsp+0B00h+hKey]; hKey
0x180023dd2  call    cs:__imp_RegCloseKey
0x180023dd8  mov     [rsp+0B00h+hKey], r13
0x180023ddd  cmp     [rbx+29h], r13b
0x180023de1  jnz     loc_180023BAA
0x180023de7  mov     rcx, [rbx+10h]
0x180023deb  cmp     [rcx+29h], r13b
0x180023def  jnz     short loc_180023DF8
0x180023df1  call    ?_Min@?$_Tree_val@V?$_Tset_traits@V?$shared_ptr@VCDimInterface@@@tr1@std@@U_SHARED_PTR_COMP@CDimInterfaceTable@@V?$allocator@V?$shared_ptr@VCDimInterface@@@tr1@std@@@3@$0A@@std@@@std@@SAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$shared_ptr@VCDimInterface@@@tr1@std@@U_SHARED_PTR_COMP@CDimInterfaceTable@@V?$allocator@V?$shared_ptr@VCDimInterface@@@tr1@std@@@3@$0A@@std@@@2@PEAU342@@Z; std::_Tree_val<std::_Tset_traits<std::tr1::shared_ptr<CDimInterface>,CDimInterfaceTable::_SHARED_PTR_COMP,std::allocator<std::tr1::shared_ptr<CDimInterface>>,0>>::_Min(std::_Tree_nod<std::_Tset_traits<std::tr1::shared_ptr<CDimInterface>,CDimInterfaceTable::_SHARED_PTR_COMP,std::allocator<std::tr1::shared_ptr<CDimInterface>>,0>>::_Node *)
0x180023df6  jmp     short loc_180023E11
0x180023df8  mov     rax, [rbx+8]
0x180023dfc  jmp     short loc_180023E0B
0x180023dfe  cmp     rbx, [rax+10h]
0x180023e02  jnz     short loc_180023E11
0x180023e04  mov     rbx, rax
0x180023e07  mov     rax, [rax+8]
0x180023e0b  cmp     [rax+29h], r13b
0x180023e0f  jz      short loc_180023DFE
0x180023e11  mov     rbx, rax
0x180023e14  jmp     loc_180023BAA
0x180023e19  mov     qword ptr [rsp+0B00h+Buf1], r13
0x180023e1e  lea     rdx, [rsp+0B00h+Buf1]
0x180023e23  lea     rcx, [rsp+0B00h+pExceptionObject]
0x180023e28  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x180023e2e  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180023e35  mov     [rsp+0B00h+pExceptionObject], rax
0x180023e3a  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180023e41  lea     rcx, [rsp+0B00h+pExceptionObject]; pExceptionObject
0x180023e46  call    _CxxThrowException_0
```
