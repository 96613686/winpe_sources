# CreateIPAddress

- ea: `0x180037278`
- end: `0x18003781b`
- name: `CreateIPAddress`
- size: `1443`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x18003359c`

## callees

- `0x180002f50`
- `0x1800123b0`
- `0x180014638`
- `0x180014698`
- `0x180025478`
- `0x180037278`
- `0x180037994`
- `0x18003855c`
- `0x180052d30`
- `0x18006c010`
- `0x18006c5e0`
- `0x18006ca50`
- `0x1800a2d80`

## import_xrefs

- `ntdll!RtlIpv4StringToAddressExW` at `0x18003734f`
- `ntdll!RtlIpv4StringToAddressExW` at `0x18003734f`
- `ntdll!RtlIpv6StringToAddressExW` at `0x180037388`
- `ntdll!RtlIpv6StringToAddressExW` at `0x180037388`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037560`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800375ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003768f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037560`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800375ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003768f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800372d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800372ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800373b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037450`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800377a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800377d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800377ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800372d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800372ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800373b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037450`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800377a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800377d9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800377ef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037772`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800377ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180037772`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800377ba`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180037681`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180037681`
- `WS2_32!__imp_htonl` at `0x180037406`
- `WS2_32!__imp_htonl` at `0x180037406`

## string_xrefs

- `0x180037535`: `clusapi!CreateIPAddress`
- `0x1800375bd`: `clusapi!CreateIPAddress`
- `0x180037786`: `clusapi!CreateIPAddress`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
struct _HRESOURCE *__fastcall CreateIPAddress(struct _HCLUSTER *a1, __int64 a2, __int64 a3, wchar_t *a4, int a5)
{
  __int64 v8; // rcx
  LONG v10; // ecx
  unsigned int v11; // edi
  __int16 v12; // ax
  u_long v13; // eax
  int v14; // r15d
  DWORD v15; // eax
  const wchar_t *v16; // r14
  unsigned int v17; // r13d
  unsigned int v18; // r12d
  struct _HRESOURCE *ClusterResource; // rsi
  unsigned int LastError; // ebx
  int v21; // eax
  unsigned int v22; // r14d
  _DWORD *v23; // rax
  void *v24; // rdi
  __int64 v25; // rdx
  __int64 v26; // r10
  unsigned int v27; // r9d
  __int64 i; // r8
  unsigned int v29; // edx
  unsigned __int8 (*v30)(struct _HNETWORK *, wchar_t *, unsigned int, void *); // r8
  unsigned int j; // ebx
  void *v32; // rcx
  unsigned int v33[2]; // [rsp+20h] [rbp-378h]
  DWORD dwErrCode; // [rsp+50h] [rbp-348h] BYREF
  __int64 v35; // [rsp+58h] [rbp-340h] BYREF
  __int64 v36; // [rsp+60h] [rbp-338h] BYREF
  BOOL v37; // [rsp+68h] [rbp-330h]
  __int64 v38; // [rsp+70h] [rbp-328h]
  wchar_t *v39; // [rsp+78h] [rbp-320h]
  __int64 v40; // [rsp+80h] [rbp-318h]
  wchar_t *v41; // [rsp+88h] [rbp-310h]
  HCLUSTER hCluster; // [rsp+90h] [rbp-308h]
  __int128 v43; // [rsp+98h] [rbp-300h] BYREF
  _QWORD Address[4]; // [rsp+B8h] [rbp-2E0h] BYREF
  _DWORD v45[8]; // [rsp+D8h] [rbp-2C0h] BYREF
  HLOCAL hMem; // [rsp+F8h] [rbp-2A0h]
  __int64 PropertyListEntry; // [rsp+100h] [rbp-298h]
  __int64 v48; // [rsp+108h] [rbp-290h]
  _BYTE v49[64]; // [rsp+110h] [rbp-288h] BYREF
  wchar_t v50[256]; // [rsp+150h] [rbp-248h] BYREF

  v41 = a4;
  v38 = a3;
  v40 = a2;
  hCluster = a1;
  if ( !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HGROUP *>(
                           a1,
                           a2)
    || !(unsigned __int8)HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(
                           v8,
                           a1) )
  {
    SetLastError(6u);
    return 0;
  }
  v43 = 0;
  hMem = 0;
  v48 = 0;
  v35 = 0;
  LODWORD(v36) = 0;
  memset(Address, 0, 28);
  v10 = RtlIpv4StringToAddressExW(a4, 0, (struct in_addr *)Address + 1, (PUSHORT)Address + 1);
  if ( v10 < 0 )
  {
    v10 = RtlIpv6StringToAddressExW(a4, (struct in6_addr *)&Address[1], (PULONG)&Address[3], (PUSHORT)Address + 1);
    v11 = 2;
    if ( v10 < 0 )
    {
      v12 = Address[0];
    }
    else
    {
      v12 = 23;
      LOWORD(Address[0]) = 23;
    }
  }
  else
  {
    v11 = 2;
    v12 = 2;
    LOWORD(Address[0]) = 2;
  }
  if ( v10 )
  {
    SetLastError(v10);
    return 0;
  }
  if ( v12 == 2 )
  {
    v13 = 0;
    memset(v45, 0, 28);
    LOWORD(v45[0]) = 2;
    v14 = a5;
    if ( a5 )
      v13 = -1 << (32 - a5);
    v45[1] = htonl(v13);
    v37 = (~v45[1] & HIDWORD(Address[0])) == 0;
    dwErrCode = 32;
    v15 = ClRtlIpAddressToString(v45, v49, &dwErrCode);
    if ( v15 )
    {
      SetLastError(v15);
      return 0;
    }
    v16 = L"IP Address";
    v39 = L"Address";
    v17 = 3;
    PropertyListEntry = CreatePropertyListEntry((wchar_t *)L"SubnetMask", (__int64)&v35 + 4);
    v18 = 4;
    v48 = CreatePropertyListEntry((wchar_t *)L"EnableDhcp", (__int64)&v36);
  }
  else
  {
    if ( v12 != 23 )
    {
      SetLastError(0x57u);
      return 0;
    }
    v16 = L"IPv6 Address";
    v39 = L"Address";
    v17 = 2;
    v18 = 4;
    PropertyListEntry = CreatePropertyListEntry((wchar_t *)L"PrefixLength", (__int64)&v35 + 4);
    v14 = a5;
  }
  ClusterResource = (struct _HRESOURCE *)CreateClusterResourceEx(a2, v38, v16, 0, L"clusapi!CreateIPAddress");
  if ( ClusterResource )
    goto LABEL_30;
  LastError = GetLastError();
  if ( LastError == 5010 )
  {
    while ( v11 < 0x64 )
    {
      v33[0] = v11;
      v21 = StringCchPrintfW(v50, 0x100u, L"%ws (%d)", v38, *(_QWORD *)v33);
      if ( v21 >= 0 )
      {
        ClusterResource = (struct _HRESOURCE *)CreateClusterResourceEx(v40, v50, v16, 0, L"clusapi!CreateIPAddress");
        if ( ClusterResource )
          goto LABEL_30;
        LastError = GetLastError();
        if ( LastError != 5010 )
          break;
      }
      else if ( (v21 & 0x1FFF0000) != 0x70000 || (LastError = (unsigned __int16)v21, !(_WORD)v21) )
      {
        LastError = v21;
      }
      ++v11;
    }
  }
  if ( !LastError )
  {
LABEL_30:
    dwErrCode = 0;
    LastError = MylstrlenW(v41, 0x7FFFFFFFu, &dwErrCode);
    if ( !LastError )
    {
      hMem = (HLOCAL)CreatePropertyListEntry(v39, (__int64)&v35);
      v22 = HIDWORD(v35) + v35 + v36 + 4;
      v23 = LocalAlloc(0x40u, v22);
      v24 = v23;
      if ( v23 )
      {
        *v23 = v17;
        v25 = 0;
        do
        {
          v26 = (__int64)*(&hMem + v25);
          v27 = *((_DWORD *)&v35 + v25);
          for ( i = 0; (unsigned int)i < v27; ++v18 )
          {
            *((_BYTE *)v23 + v18) = *(_BYTE *)(i + v26);
            i = (unsigned int)(i + 1);
          }
          v25 = (unsigned int)(v25 + 1);
        }
        while ( (unsigned int)v25 < v17 );
        LastError = ClusterpResourceControl(ClusterResource, 0, 0x1400086u, v23, v22, 0, 0, 0, 0, 0);
        if ( LastError )
        {
          *(_QWORD *)&v43 = Address;
          DWORD2(v43) = v14;
          EnumerateNetworkObjects(hCluster, v29, v30, &v43);
          LastError = ClusterpResourceControl(ClusterResource, 0, 0x1400086u, v24, v22, 0, 0, 0, 0, 0);
        }
        LocalFree(v24);
      }
      else
      {
        LastError = GetLastError();
      }
      if ( !LastError )
        goto LABEL_44;
    }
  }
  if ( ClusterResource )
  {
    DeleteClusterResourceEx(ClusterResource, L"clusapi!CreateIPAddress");
    CloseClusterResource(ClusterResource);
    ClusterResource = 0;
  }
  SetLastError(LastError);
LABEL_44:
  for ( j = 0; j < v17; ++j )
  {
    v32 = *(&hMem + j);
    if ( v32 )
    {
      LocalFree(v32);
      *(&hMem + j) = 0;
    }
  }
  return ClusterResource;
}

```

## disassembly

```asm
0x180037278  push    rbx
0x18003727a  push    rsi
0x18003727b  push    rdi
0x18003727c  push    r12
0x18003727e  push    r13
0x180037280  push    r14
0x180037282  push    r15
0x180037284  sub     rsp, 360h
0x18003728b  mov     rax, cs:__security_cookie
0x180037292  xor     rax, rsp
0x180037295  mov     [rsp+398h+var_48], rax
0x18003729d  mov     rdi, r9
0x1800372a0  mov     [rsp+398h+var_310], r9
0x1800372a8  mov     [rsp+398h+var_328], r8
0x1800372ad  mov     rsi, rdx
0x1800372b0  mov     [rsp+398h+var_318], rdx
0x1800372b8  mov     rbx, rcx
0x1800372bb  mov     [rsp+398h+hCluster], rcx
0x1800372c3  call    ??$Contains@PEAU_HGROUP@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HGROUP@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HGROUP *>(_HGROUP *)
0x1800372c8  test    al, al
0x1800372ca  jnz     short loc_1800372DE
0x1800372cc  mov     ecx, 6; dwErrCode
0x1800372d1  call    cs:__imp_SetLastError
0x1800372d7  xor     eax, eax
0x1800372d9  jmp     loc_1800377F7
0x1800372de  mov     rdx, rbx
0x1800372e1  call    ??$Contains@PEAU_HCLUSTER@@@?$HandleValidator@PEAU_HCHANGE@@PEAU_HGROUPSETENUM@@PEAU_HGROUPSET@@PEAU_HRESENUMEX@@PEAU_HGROUPENUMEX@@PEAU_HCLUSENUMEX@@PEAU_HNODEENUMEX@@PEAU_HRESTYPEENUM@@PEAU_HNETINTERFACEENUM@@PEAU_HNODEENUM@@PEAU_HNETWORKENUM@@PEAU_HRESENUM@@PEAU_HGROUPENUM@@PEAU_HCLUSENUM@@PEAU_HNETINTERFACE@@PEAU_HNETWORK@@PEAU_HREGBATCHPORT@@PEAU_HREGBATCHNOTIFICATION@@PEAU_HRESOURCE@@PEAU_HGROUP@@PEAU_HNODE@@PEAU_HCLUSTER@@PEAUHKEY__@@PEAU_HKEYVALUESTORE@@@@QEAA_NPEAU_HCLUSTER@@@Z; HandleValidator<_HCHANGE *,_HGROUPSETENUM *,_HGROUPSET *,_HRESENUMEX *,_HGROUPENUMEX *,_HCLUSENUMEX *,_HNODEENUMEX *,_HRESTYPEENUM *,_HNETINTERFACEENUM *,_HNODEENUM *,_HNETWORKENUM *,_HRESENUM *,_HGROUPENUM *,_HCLUSENUM *,_HNETINTERFACE *,_HNETWORK *,_HREGBATCHPORT *,_HREGBATCHNOTIFICATION *,_HRESOURCE *,_HGROUP *,_HNODE *,_HCLUSTER *,HKEY__ *,_HKEYVALUESTORE *>::Contains<_HCLUSTER *>(_HCLUSTER *)
0x1800372e6  test    al, al
0x1800372e8  jnz     short loc_1800372FC
0x1800372ea  mov     ecx, 6; dwErrCode
0x1800372ef  call    cs:__imp_SetLastError
0x1800372f5  xor     eax, eax
0x1800372f7  jmp     loc_1800377F7
0x1800372fc  xorps   xmm0, xmm0
0x1800372ff  movups  [rsp+398h+var_300], xmm0
0x180037307  mov     [rsp+398h+hMem], 0
0x180037313  mov     [rsp+398h+var_290], 0
0x18003731f  xor     eax, eax
0x180037321  mov     [rsp+398h+var_340], rax
0x180037326  mov     dword ptr [rsp+398h+var_338], eax
0x18003732a  movups  xmmword ptr [rsp+398h+Address.S_un], xmm0
0x180037332  movups  xmmword ptr [rsp+398h+Address.S_un+0Ch], xmm0
0x18003733a  lea     r9, [rsp+398h+Address.S_un+2]; Port
0x180037342  lea     r8, [rsp+398h+Address.S_un+4]; Address
0x18003734a  xor     edx, edx; Strict
0x18003734c  mov     rcx, rdi; AddressString
0x18003734f  call    cs:__imp_RtlIpv4StringToAddressExW
0x180037355  mov     ecx, eax
0x180037357  test    eax, eax
0x180037359  js      short loc_18003736D
0x18003735b  mov     edi, 2
0x180037360  movzx   eax, di
0x180037363  mov     word ptr [rsp+398h+Address.S_un], ax
0x18003736b  jmp     short loc_1800373B0
0x18003736d  lea     r9, [rsp+398h+Address.S_un+2]; Port
0x180037375  lea     r8, [rsp+398h+ScopeId]; ScopeId
0x18003737d  lea     rdx, [rsp+398h+Address.S_un+8]; Address
0x180037385  mov     rcx, rdi; AddressString
0x180037388  call    cs:__imp_RtlIpv6StringToAddressExW
0x18003738e  mov     ecx, eax; dwErrCode
0x180037390  mov     edi, 2
0x180037395  test    eax, eax
0x180037397  js      short loc_1800373A8
0x180037399  lea     edx, [rdi+15h]
0x18003739c  mov     eax, edx
0x18003739e  mov     word ptr [rsp+398h+Address.S_un], dx
0x1800373a6  jmp     short loc_1800373B5
0x1800373a8  movzx   eax, word ptr [rsp+398h+Address.S_un]
0x1800373b0  mov     edx, 17h
0x1800373b5  test    ecx, ecx
0x1800373b7  jz      short loc_1800373C6
0x1800373b9  call    cs:__imp_SetLastError
0x1800373bf  xor     eax, eax
0x1800373c1  jmp     loc_1800377F7
0x1800373c6  cmp     ax, di
0x1800373c9  jnz     loc_1800374DA
0x1800373cf  xorps   xmm0, xmm0
0x1800373d2  xor     eax, eax
0x1800373d4  movups  xmmword ptr [rsp+398h+var_2C0], xmm0
0x1800373dc  movups  xmmword ptr [rsp+398h+var_2C0+0Ch], xmm0
0x1800373e4  mov     word ptr [rsp+398h+var_2C0], di
0x1800373ec  mov     r15d, [rsp+398h+arg_20]
0x1800373f4  test    r15d, r15d
0x1800373f7  jz      short loc_180037404
0x1800373f9  lea     ecx, [rax+20h]
0x1800373fc  sub     ecx, r15d
0x1800373ff  or      eax, 0FFFFFFFFh
0x180037402  shl     eax, cl
0x180037404  mov     ecx, eax; hostlong
0x180037406  call    cs:__imp_htonl
0x18003740c  mov     dword ptr [rsp+398h+var_2C0+4], eax
0x180037413  not     eax
0x180037415  test    dword ptr [rsp+398h+Address.S_un+4], eax
0x18003741c  mov     eax, 0
0x180037421  setz    al
0x180037424  mov     [rsp+398h+var_330], eax
0x180037428  mov     [rsp+398h+dwErrCode], 20h ; ' '
0x180037430  lea     r8, [rsp+398h+dwErrCode]
0x180037435  lea     rdx, [rsp+398h+var_288]
0x18003743d  lea     rcx, [rsp+398h+var_2C0]
0x180037445  call    ClRtlIpAddressToString
0x18003744a  test    eax, eax
0x18003744c  jz      short loc_18003745D
0x18003744e  mov     ecx, eax; dwErrCode
0x180037450  call    cs:__imp_SetLastError
0x180037456  xor     eax, eax
0x180037458  jmp     loc_1800377F7
0x18003745d  lea     r14, aIpAddress; "IP Address"
0x180037464  lea     rax, aAddress; "Address"
0x18003746b  mov     [rsp+398h+var_320], rax
0x180037470  mov     r13d, 3
0x180037476  mov     r8d, [rsp+398h+dwErrCode]
0x18003747b  add     r8d, r8d
0x18003747e  lea     rax, [rsp+398h+var_340+4]
0x180037483  mov     qword ptr [rsp+398h+var_378], rax; __int64
0x180037488  lea     r9, [rsp+398h+var_288]
0x180037490  mov     edx, 10003h
0x180037495  lea     rcx, aSubnetmask; "SubnetMask"
0x18003749c  call    CreatePropertyListEntry
0x1800374a1  mov     [rsp+398h+var_298], rax
0x1800374a9  lea     rax, [rsp+398h+var_338]
0x1800374ae  mov     qword ptr [rsp+398h+var_378], rax; __int64
0x1800374b3  lea     r9, [rsp+398h+var_330]
0x1800374b8  lea     r12d, [r13+1]
0x1800374bc  mov     r8d, r12d
0x1800374bf  mov     edx, 10002h
0x1800374c4  lea     rcx, aEnabledhcp; "EnableDhcp"
0x1800374cb  call    CreatePropertyListEntry
0x1800374d0  mov     [rsp+398h+var_290], rax
0x1800374d8  jmp     short loc_180037535
0x1800374da  cmp     ax, dx
0x1800374dd  jnz     loc_1800377D4
0x1800374e3  lea     r14, aIpv6Address; "IPv6 Address"
0x1800374ea  lea     rbx, aAddress; "Address"
0x1800374f1  mov     [rsp+398h+var_320], rbx
0x1800374f6  mov     r13d, edi
0x1800374f9  lea     rax, [rsp+398h+var_340+4]
0x1800374fe  mov     qword ptr [rsp+398h+var_378], rax; __int64
0x180037503  lea     r9, [rsp+398h+arg_20]
0x18003750b  mov     r12d, 4
0x180037511  mov     r8d, r12d
0x180037514  mov     edx, 10002h
0x180037519  lea     rcx, aPrefixlength; "PrefixLength"
0x180037520  call    CreatePropertyListEntry
0x180037525  mov     [rsp+398h+var_298], rax
0x18003752d  mov     r15d, [rsp+398h+arg_20]
0x180037535  lea     rax, aClusapiCreatei; "clusapi!CreateIPAddress"
0x18003753c  mov     qword ptr [rsp+398h+var_378], rax
0x180037541  xor     r9d, r9d
0x180037544  mov     r8, r14
0x180037547  mov     rdx, [rsp+398h+var_328]
0x18003754c  mov     rcx, rsi
0x18003754f  call    CreateClusterResourceEx
0x180037554  mov     rsi, rax
0x180037557  test    rax, rax
0x18003755a  jnz     loc_18003760A
0x180037560  call    cs:__imp_GetLastError
0x180037566  mov     ebx, eax
0x180037568  cmp     eax, 1392h
0x18003756d  jnz     loc_180037602
0x180037573  cmp     edi, 64h ; 'd'
0x180037576  jnb     loc_180037602
0x18003757c  mov     [rsp+398h+var_378], edi
0x180037580  mov     r9, [rsp+398h+var_328]
0x180037585  lea     r8, aWsD_0; "%ws (%d)"
0x18003758c  mov     edx, 100h; unsigned __int64
0x180037591  lea     rcx, [rsp+398h+var_248]; wchar_t *
0x180037599  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18003759e  test    eax, eax
0x1800375a0  jns     short loc_1800375BD
0x1800375a2  mov     ecx, eax
0x1800375a4  and     ecx, 1FFF0000h
0x1800375aa  cmp     ecx, 70000h
0x1800375b0  jnz     short loc_1800375B9
0x1800375b2  movzx   ebx, ax
0x1800375b5  test    ebx, ebx
0x1800375b7  jnz     short loc_1800375FB
0x1800375b9  mov     ebx, eax
0x1800375bb  jmp     short loc_1800375FB
0x1800375bd  lea     rax, aClusapiCreatei; "clusapi!CreateIPAddress"
0x1800375c4  mov     qword ptr [rsp+398h+var_378], rax
0x1800375c9  xor     r9d, r9d
0x1800375cc  mov     r8, r14
0x1800375cf  lea     rdx, [rsp+398h+var_248]
0x1800375d7  mov     rcx, [rsp+398h+var_318]
0x1800375df  call    CreateClusterResourceEx
0x1800375e4  mov     rsi, rax
0x1800375e7  test    rax, rax
0x1800375ea  jnz     short loc_18003760A
0x1800375ec  call    cs:__imp_GetLastError
0x1800375f2  mov     ebx, eax
0x1800375f4  cmp     eax, 1392h
0x1800375f9  jnz     short loc_180037602
0x1800375fb  inc     edi
0x1800375fd  jmp     loc_180037573
0x180037602  test    ebx, ebx
0x180037604  jnz     loc_18003777E
0x18003760a  mov     [rsp+398h+dwErrCode], 0
0x180037612  lea     r8, [rsp+398h+dwErrCode]; unsigned int *
0x180037617  mov     edx, 7FFFFFFFh; unsigned int
0x18003761c  mov     rdi, [rsp+398h+var_310]
0x180037624  mov     rcx, rdi; wchar_t *
0x180037627  call    ?MylstrlenW@@YAKPEB_WKPEAK@Z; MylstrlenW(wchar_t const *,ulong,ulong *)
0x18003762c  mov     ebx, eax
0x18003762e  test    eax, eax
0x180037630  jnz     loc_18003777E
0x180037636  mov     r8d, [rsp+398h+dwErrCode]
0x18003763b  lea     r8d, ds:2[r8*2]
0x180037643  lea     rax, [rsp+398h+var_340]
0x180037648  mov     qword ptr [rsp+398h+var_378], rax; __int64
0x18003764d  mov     r9, rdi
0x180037650  mov     edx, 10003h
0x180037655  mov     rcx, [rsp+398h+var_320]; wchar_t *
0x18003765a  call    CreatePropertyListEntry
0x18003765f  mov     [rsp+398h+hMem], rax
0x180037667  mov     edx, dword ptr [rsp+398h+var_340]
0x18003766b  add     edx, dword ptr [rsp+398h+var_340+4]
0x18003766f  mov     r14d, dword ptr [rsp+398h+var_338]
0x180037674  add     r14d, 4
0x180037678  add     r14d, edx
0x18003767b  mov     edx, r14d; uBytes
0x18003767e  lea     ecx, [rbx+40h]; uFlags
0x180037681  call    cs:__imp_LocalAlloc
0x180037687  mov     rdi, rax
0x18003768a  test    rax, rax
0x18003768d  jnz     short loc_18003769F
0x18003768f  call    cs:__imp_GetLastError
0x180037695  mov     ebx, eax
0x180037697  xor     r12d, r12d
0x18003769a  jmp     loc_180037778
0x18003769f  mov     [rax], r13d
0x1800376a2  xor     edx, edx
0x1800376a4  mov     r10, [rsp+rdx*8+398h+hMem]
0x1800376ac  mov     r9d, dword ptr [rsp+rdx*4+398h+var_340]
0x1800376b1  xor     r8d, r8d
0x1800376b4  test    r9d, r9d
0x1800376b7  jz      short loc_1800376CE
0x1800376b9  mov     ecx, r12d
0x1800376bc  mov     al, [r8+r10]
0x1800376c0  mov     [rcx+rdi], al
0x1800376c3  inc     r8d
0x1800376c6  inc     r12d
0x1800376c9  cmp     r8d, r9d
0x1800376cc  jb      short loc_1800376B9
0x1800376ce  inc     edx
0x1800376d0  cmp     edx, r13d
0x1800376d3  jb      short loc_1800376A4
0x1800376d5  xor     r12d, r12d
0x1800376d8  mov     [rsp+398h+var_350], r12; wchar_t *
0x1800376dd  mov     [rsp+398h+var_358], r12b; bool
0x1800376e2  mov     [rsp+398h+var_360], r12; unsigned int *
0x1800376e7  mov     [rsp+398h+var_368], r12d; unsigned int
0x1800376ec  mov     [rsp+398h+var_370], r12; void *
0x1800376f1  mov     [rsp+398h+var_378], r14d; unsigned int
0x1800376f6  mov     r9, rdi; void *
0x1800376f9  xor     edx, edx; struct _HNODE *
0x1800376fb  mov     r8d, 1400086h; unsigned int
0x180037701  mov     rcx, rsi; struct _HRESOURCE *
0x180037704  call    ?ClusterpResourceControl@@YAKPEAU_HRESOURCE@@PEAU_HNODE@@KPEAXK2KPEAK_NPEB_W@Z; ClusterpResourceControl(_HRESOURCE *,_HNODE *,ulong,void *,ulong,void *,ulong,ulong *,bool,wchar_t const *)
0x180037709  mov     ebx, eax
0x18003770b  test    eax, eax
0x18003770d  jz      short loc_18003776F
0x18003770f  lea     rax, [rsp+398h+Address]
0x180037717  mov     qword ptr [rsp+398h+var_300], rax
0x18003771f  mov     dword ptr [rsp+398h+var_300+8], r15d
0x180037727  lea     r9, [rsp+398h+var_300]; void *
0x18003772f  mov     rcx, [rsp+398h+hCluster]; hCluster
0x180037737  call    ?EnumerateNetworkObjects@@YAKPEAU_HCLUSTER@@KP6AEPEAU_HNETWORK@@PEA_WKPEAX@Z3@Z; EnumerateNetworkObjects(_HCLUSTER *,ulong,uchar (*)(_HNETWORK *,wchar_t *,ulong,void *),void *)
0x18003773c  mov     [rsp+398h+var_350], r12; wchar_t *
0x180037741  mov     [rsp+398h+var_358], r12b; bool
0x180037746  mov     [rsp+398h+var_360], r12; unsigned int *
0x18003774b  mov     [rsp+398h+var_368], r12d; unsigned int
0x180037750  mov     [rsp+398h+var_370], r12; void *
0x180037755  mov     [rsp+398h+var_378], r14d; unsigned int
0x18003775a  mov     r9, rdi; void *
0x18003775d  xor     edx, edx; struct _HNODE *
0x18003775f  mov     r8d, 1400086h; unsigned int
0x180037765  mov     rcx, rsi; struct _HRESOURCE *
0x180037768  call    ?ClusterpResourceControl@@YAKPEAU_HRESOURCE@@PEAU_HNODE@@KPEAXK2KPEAK_NPEB_W@Z; ClusterpResourceControl(_HRESOURCE *,_HNODE *,ulong,void *,ulong,void *,ulong,ulong *,bool,wchar_t const *)
0x18003776d  mov     ebx, eax
0x18003776f  mov     rcx, rdi; hMem
0x180037772  call    cs:__imp_LocalFree
0x180037778  test    ebx, ebx
0x18003777a  jz      short loc_1800377A8
0x18003777c  jmp     short loc_180037781
0x18003777e  xor     r12d, r12d
0x180037781  test    rsi, rsi
0x180037784  jz      short loc_1800377A0
0x180037786  lea     rdx, aClusapiCreatei; "clusapi!CreateIPAddress"
0x18003778d  mov     rcx, rsi
0x180037790  call    DeleteClusterResourceEx
0x180037795  mov     rcx, rsi; hResource
0x180037798  call    CloseClusterResource
0x18003779d  mov     rsi, r12
0x1800377a0  mov     ecx, ebx; dwErrCode
0x1800377a2  call    cs:__imp_SetLastError
0x1800377a8  mov     ebx, r12d
0x1800377ab  mov     edi, ebx
0x1800377ad  mov     rcx, [rsp+rdi*8+398h+hMem]; hMem
0x1800377b5  test    rcx, rcx
  ... truncated ...
```
