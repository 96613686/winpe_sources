# ResolvePhysicalInterface(_GUID const &,_GUID *)

- ea: `0x18008e210`
- end: `0x18008e779`
- name: `?ResolvePhysicalInterface@@YAJAEBU_GUID@@PEAU1@@Z`
- size: `1385`
- prototype: `__int64 __fastcall(const struct _GUID *, struct _GUID *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x1800ca9d0`

## callees

- `0x18000ee14`
- `0x18000fab0`
- `0x180010340`
- `0x180013470`
- `0x180015b10`
- `0x180045a14`
- `0x18004b2ac`
- `0x18004c16c`
- `0x180051238`
- `0x18005b904`
- `0x18008e210`
- `0x18008e7a8`
- `0x1800a88a0`
- `0x1800a8dac`
- `0x1800a9738`
- `0x1800a9744`
- `0x1800c9d20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008e37b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18008e37b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008e41a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008e41a`
- `IPHLPAPI!InternalGetIPPhysicalInterfaceForDestination` at `0x18008e3d8`
- `IPHLPAPI!InternalGetIPPhysicalInterfaceForDestination` at `0x18008e3d8`
- `IPHLPAPI!CloseGetIPPhysicalInterfaceForDestination` at `0x18008e428`
- `IPHLPAPI!CloseGetIPPhysicalInterfaceForDestination` at `0x18008e5cd`
- `IPHLPAPI!CloseGetIPPhysicalInterfaceForDestination` at `0x18008e66f`
- `IPHLPAPI!CloseGetIPPhysicalInterfaceForDestination` at `0x18008e428`
- `IPHLPAPI!CloseGetIPPhysicalInterfaceForDestination` at `0x18008e5cd`
- `IPHLPAPI!CloseGetIPPhysicalInterfaceForDestination` at `0x18008e66f`

## string_xrefs

- `0x18008e5fe`: `Unable to create DoneEvent for ResolvePhysicalInterfaceWorkItem`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall ResolvePhysicalInterface(struct _GUID *a1, struct _GUID *a2)
{
  signed int InternetAddrList; // ebx
  PVOID *v4; // rcx
  __int64 v5; // rdx
  unsigned int v6; // r13d
  char *v7; // r15
  HANDLE EventW; // rax
  unsigned int IPPhysicalInterfaceForDestination; // eax
  unsigned int v10; // edx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  GUID *v13; // r13
  bool v14; // cc
  int v16; // [rsp+40h] [rbp-1C8h] BYREF
  GUID *InterfaceGuid; // [rsp+48h] [rbp-1C0h]
  struct _GUID *v18; // [rsp+50h] [rbp-1B8h]
  int v19; // [rsp+58h] [rbp-1B0h]
  char *v20; // [rsp+60h] [rbp-1A8h]
  struct _GUID *v21; // [rsp+68h] [rbp-1A0h]
  struct _GUID *v22; // [rsp+70h] [rbp-198h]
  char *v23; // [rsp+78h] [rbp-190h]
  _BYTE pExceptionObject[24]; // [rsp+88h] [rbp-180h] BYREF
  int v25; // [rsp+A0h] [rbp-168h] BYREF
  union _NET_LUID_LH v26; // [rsp+B0h] [rbp-158h] BYREF
  signed int v27; // [rsp+C0h] [rbp-148h]
  __int64 v28; // [rsp+C8h] [rbp-140h] BYREF
  __int64 v29; // [rsp+D0h] [rbp-138h] BYREF
  _BYTE v30[256]; // [rsp+E0h] [rbp-128h] BYREF

  v18 = a2;
  InterfaceGuid = a1;
  v21 = a1;
  v22 = a2;
  memset_0(v30, 0, sizeof(v30));
  v29 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 206, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids, a1);
  InternetAddrList = GetInternetAddrList();
  if ( InternetAddrList )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 207;
LABEL_8:
      WPP_SF_d(v4[2], v5, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids, (unsigned int)InternetAddrList);
      v4 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_9;
    }
    goto LABEL_9;
  }
  InternetAddrList = GetPreferredAddress(2, &g_InternetAddrList, v30);
  if ( InternetAddrList )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 208;
      goto LABEL_8;
    }
LABEL_9:
    if ( InternetAddrList > 0 )
      InternetAddrList = (unsigned __int16)InternetAddrList | 0x80070000;
    goto LABEL_75;
  }
  v16 = 0;
  v19 = 0;
  v6 = 0;
  v28 = 0;
  v20 = 0;
  while ( 1 )
  {
    v7 = (char *)operator new(0x20u);
    v23 = v7;
    *(_OWORD *)v7 = 0;
    *((_QWORD *)v7 + 2) = 0;
    *((_DWORD *)v7 + 6) = 258;
    EventW = CreateEventW(0, 1, 0, 0);
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      v7 + 16,
      EventW);
    if ( !*((_QWORD *)v7 + 2) )
    {
      std::exception::exception(
        (std::exception *)pExceptionObject,
        "Unable to create DoneEvent for ResolvePhysicalInterfaceWorkItem");
      throw (std::exception *)pExceptionObject;
    }
    v20 = v7;
    IPPhysicalInterfaceForDestination = InternalGetIPPhysicalInterfaceForDestination(
                                          &v30[128 * (unsigned __int64)v6],
                                          0,
                                          &v29,
                                          v7,
                                          v7,
                                          GetIPPhysicalInterfaceCallback,
                                          &v28);
    if ( IPPhysicalInterfaceForDestination == 997 )
      break;
    if ( !IPPhysicalInterfaceForDestination )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v12 = 213;
LABEL_25:
        WPP_SF_(v11[2], v12, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids);
      }
LABEL_26:
      *v18 = *(struct _GUID *)v7;
      InternetAddrList = 0;
LABEL_27:
      v13 = InterfaceGuid;
      v4 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_59;
    }
    if ( IPPhysicalInterfaceForDestination == 1231 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 214, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids, 1231);
      InternetAddrList = -2147023665;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          215,
          &WPP_bec8c779ead031fcc66297531c43b631_Traceguids,
          IPPhysicalInterfaceForDestination);
      InterfaceIdentifier::GetMapping((int)&v25, InterfaceGuid);
      InternetAddrList = v27;
      v14 = v27 <= 0;
      if ( !v27 )
      {
        InternetAddrList = GetNdisPhysicalInterface(&v26, v18);
        if ( !InternetAddrList )
        {
          v4 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            WPP_SF__guid_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              216,
              &WPP_bec8c779ead031fcc66297531c43b631_Traceguids,
              v18);
            v4 = (PVOID *)WPP_GLOBAL_Control;
          }
          v16 = 1;
          goto LABEL_32;
        }
        v14 = InternetAddrList < 0;
      }
      if ( !v14 )
        InternetAddrList = (unsigned __int16)InternetAddrList | 0x80070000;
    }
    ++v6;
    if ( v28 )
    {
      CloseGetIPPhysicalInterfaceForDestination(&v28);
      v28 = 0;
    }
    ResolvePhysicalInterfaceWorkItem::`scalar deleting destructor'((ResolvePhysicalInterfaceWorkItem *)v7, v10);
    v7 = 0;
    v20 = 0;
    if ( v6 >= 2 )
      goto LABEL_27;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 210, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids, 10000);
  WaitForSingleObject(*((HANDLE *)v7 + 2), 0x2710u);
  CloseGetIPPhysicalInterfaceForDestination(&v28);
  v28 = 0;
  if ( !*((_DWORD *)v7 + 6) )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v12 = 211;
      goto LABEL_25;
    }
    goto LABEL_26;
  }
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 212, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  InternetAddrList = -2147024638;
LABEL_32:
  v13 = InterfaceGuid;
LABEL_59:
  if ( v28 )
  {
    CloseGetIPPhysicalInterfaceForDestination(&v28);
    v28 = 0;
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v7 )
  {
    ResolvePhysicalInterfaceWorkItem::`scalar deleting destructor'((ResolvePhysicalInterfaceWorkItem *)v7, v10);
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( InternetAddrList >= 0 )
  {
    if ( v16 )
      goto LABEL_75;
    v16 = 0;
    if ( (int)IsInterfaceConnectedOrPhysical(v13, 0, &v16) < 0 || !v16 )
    {
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF__guid__guid_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          218,
          (unsigned int)&WPP_bec8c779ead031fcc66297531c43b631_Traceguids,
          (_DWORD)v18,
          (__int64)v13);
        v4 = (PVOID *)WPP_GLOBAL_Control;
      }
      InternetAddrList = -2147024894;
      goto LABEL_75;
    }
    goto LABEL_67;
  }
  if ( v4 == &WPP_GLOBAL_Control )
    return (unsigned int)InternetAddrList;
  if ( (*((_BYTE *)v4 + 28) & 1) != 0 )
  {
    WPP_SF__guid_(v4[2], 217, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids, v13);
LABEL_67:
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_75:
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
    WPP_SF_d(v4[2], 219, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids, (unsigned int)InternetAddrList);
  return (unsigned int)InternetAddrList;
}

```

## disassembly

```asm
0x18008e210  mov     [rsp+arg_10], rbx
0x18008e215  mov     [rsp+arg_18], rsi
0x18008e21a  push    r13
0x18008e21c  push    r14
0x18008e21e  push    r15
0x18008e220  sub     rsp, 1F0h
0x18008e227  mov     rax, cs:__security_cookie
0x18008e22e  xor     rax, rsp
0x18008e231  mov     [rsp+208h+var_28], rax
0x18008e239  mov     [rsp+208h+var_1B8], rdx
0x18008e23e  mov     rbx, rcx
0x18008e241  mov     [rsp+208h+InterfaceGuid], rcx
0x18008e246  mov     [rsp+208h+var_1A0], rcx
0x18008e24b  mov     [rsp+208h+var_198], rdx
0x18008e250  xor     edx, edx; Val
0x18008e252  mov     r8d, 100h; Size
0x18008e258  lea     rcx, [rsp+208h+var_128]; void *
0x18008e260  call    memset_0
0x18008e265  mov     [rsp+208h+var_138], 0
0x18008e271  lea     r14, WPP_GLOBAL_Control
0x18008e278  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e27f  lea     rsi, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x18008e286  cmp     rcx, r14
0x18008e289  jz      short loc_18008E2A5
0x18008e28b  test    byte ptr [rcx+1Ch], 8
0x18008e28f  jz      short loc_18008E2A5
0x18008e291  mov     edx, 0CEh
0x18008e296  mov     r9, rbx
0x18008e299  mov     r8, rsi
0x18008e29c  mov     rcx, [rcx+10h]
0x18008e2a0  call    WPP_SF__guid_
0x18008e2a5  call    ?GetInternetAddrList@@YAKXZ; GetInternetAddrList(void)
0x18008e2aa  mov     ebx, eax
0x18008e2ac  test    eax, eax
0x18008e2ae  jz      short loc_18008E2F3
0x18008e2b0  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e2b7  cmp     rcx, r14
0x18008e2ba  jz      short loc_18008E2DD
0x18008e2bc  test    byte ptr [rcx+1Ch], 1
0x18008e2c0  jz      short loc_18008E2DD
0x18008e2c2  mov     edx, 0CFh
0x18008e2c7  mov     r9d, ebx
0x18008e2ca  mov     r8, rsi
0x18008e2cd  mov     rcx, [rcx+10h]
0x18008e2d1  call    WPP_SF_d
0x18008e2d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e2dd  test    ebx, ebx
0x18008e2df  jle     loc_18008E72E
0x18008e2e5  movzx   ebx, bx
0x18008e2e8  or      ebx, 80070000h
0x18008e2ee  jmp     loc_18008E72E
0x18008e2f3  lea     r8, [rsp+208h+var_128]
0x18008e2fb  lea     rdx, ?g_InternetAddrList@@3V?$array@Usockaddr_in6@@$01@std@@A; std::array<sockaddr_in6,2> g_InternetAddrList
0x18008e302  mov     ecx, 2
0x18008e307  call    GetPreferredAddress
0x18008e30c  mov     ebx, eax
0x18008e30e  test    eax, eax
0x18008e310  jz      short loc_18008E32B
0x18008e312  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e319  cmp     rcx, r14
0x18008e31c  jz      short loc_18008E2DD
0x18008e31e  test    byte ptr [rcx+1Ch], 1
0x18008e322  jz      short loc_18008E2DD
0x18008e324  mov     edx, 0D0h
0x18008e329  jmp     short loc_18008E2C7
0x18008e32b  xor     eax, eax
0x18008e32d  mov     [rsp+208h+var_1C8], eax
0x18008e331  mov     [rsp+208h+var_1B0], eax
0x18008e335  xor     r13d, r13d
0x18008e338  mov     [rsp+208h+var_140], rax
0x18008e340  mov     [rsp+208h+var_1A8], rax
0x18008e345  mov     ecx, 20h ; ' '; Size
0x18008e34a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008e34f  mov     r15, rax
0x18008e352  mov     [rsp+208h+var_190], rax
0x18008e357  xorps   xmm0, xmm0
0x18008e35a  movups  xmmword ptr [rax], xmm0
0x18008e35d  lea     rbx, [rax+10h]
0x18008e361  mov     qword ptr [rbx], 0
0x18008e368  mov     dword ptr [rax+18h], 102h
0x18008e36f  xor     r9d, r9d; lpName
0x18008e372  xor     r8d, r8d; bInitialState
0x18008e375  lea     edx, [r9+1]; bManualReset
0x18008e379  xor     ecx, ecx; lpEventAttributes
0x18008e37b  call    cs:__imp_CreateEventW
0x18008e381  mov     rdx, rax
0x18008e384  mov     rcx, rbx
0x18008e387  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18008e38c  cmp     qword ptr [rbx], 0
0x18008e390  jz      loc_18008E5FE
0x18008e396  mov     [rsp+208h+var_1A8], r15
0x18008e39b  mov     eax, r13d
0x18008e39e  shl     rax, 7
0x18008e3a2  lea     rcx, [rsp+208h+var_128]
0x18008e3aa  add     rcx, rax
0x18008e3ad  lea     rax, [rsp+208h+var_140]
0x18008e3b5  mov     [rsp+208h+var_1D8], rax
0x18008e3ba  lea     rax, ?GetIPPhysicalInterfaceCallback@@YAXPEAXPEAU_GUID@@K@Z; GetIPPhysicalInterfaceCallback(void *,_GUID *,ulong)
0x18008e3c1  mov     [rsp+208h+var_1E0], rax
0x18008e3c6  mov     [rsp+208h+var_1E8], r15
0x18008e3cb  mov     r9, r15
0x18008e3ce  lea     r8, [rsp+208h+var_138]
0x18008e3d6  xor     edx, edx
0x18008e3d8  call    cs:__imp_InternalGetIPPhysicalInterfaceForDestination
0x18008e3de  cmp     eax, 3E5h
0x18008e3e3  jnz     loc_18008E4B6
0x18008e3e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e3f0  cmp     rcx, r14
0x18008e3f3  jz      short loc_18008E412
0x18008e3f5  test    byte ptr [rcx+1Ch], 8
0x18008e3f9  jz      short loc_18008E412
0x18008e3fb  mov     edx, 0D2h
0x18008e400  mov     r9d, 2710h
0x18008e406  mov     r8, rsi
0x18008e409  mov     rcx, [rcx+10h]
0x18008e40d  call    WPP_SF_d
0x18008e412  mov     edx, 2710h; dwMilliseconds
0x18008e417  mov     rcx, [rbx]; hHandle
0x18008e41a  call    cs:__imp_WaitForSingleObject
0x18008e420  lea     rcx, [rsp+208h+var_140]
0x18008e428  call    cs:__imp_CloseGetIPPhysicalInterfaceForDestination
0x18008e42e  mov     [rsp+208h+var_140], 0
0x18008e43a  cmp     dword ptr [r15+18h], 0
0x18008e43f  jnz     short loc_18008E47D
0x18008e441  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e448  cmp     rcx, r14
0x18008e44b  jz      short loc_18008E464
0x18008e44d  test    byte ptr [rcx+1Ch], 8
0x18008e451  jz      short loc_18008E464
0x18008e453  mov     edx, 0D3h
0x18008e458  mov     r8, rsi
0x18008e45b  mov     rcx, [rcx+10h]
0x18008e45f  call    WPP_SF_
0x18008e464  movups  xmm0, xmmword ptr [r15]
0x18008e468  mov     rax, [rsp+208h+var_1B8]
0x18008e46d  movdqu  xmmword ptr [rax], xmm0
0x18008e471  xor     ebx, ebx
0x18008e473  mov     r13, [rsp+208h+InterfaceGuid]
0x18008e478  jmp     loc_18008E655
0x18008e47d  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e484  cmp     rcx, r14
0x18008e487  jz      short loc_18008E4A7
0x18008e489  test    byte ptr [rcx+1Ch], 8
0x18008e48d  jz      short loc_18008E4A7
0x18008e48f  mov     edx, 0D4h
0x18008e494  mov     r8, rsi
0x18008e497  mov     rcx, [rcx+10h]
0x18008e49b  call    WPP_SF_
0x18008e4a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e4a7  mov     ebx, 80070102h
0x18008e4ac  mov     r13, [rsp+208h+InterfaceGuid]
0x18008e4b1  jmp     loc_18008E65C
0x18008e4b6  test    eax, eax
0x18008e4b8  jnz     short loc_18008E4D3
0x18008e4ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e4c1  cmp     rcx, r14
0x18008e4c4  jz      short loc_18008E464
0x18008e4c6  test    byte ptr [rcx+1Ch], 8
0x18008e4ca  jz      short loc_18008E464
0x18008e4cc  mov     edx, 0D5h
0x18008e4d1  jmp     short loc_18008E458
0x18008e4d3  mov     r8d, 4CFh
0x18008e4d9  cmp     eax, r8d
0x18008e4dc  jnz     short loc_18008E50E
0x18008e4de  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e4e5  cmp     rcx, r14
0x18008e4e8  jz      short loc_18008E504
0x18008e4ea  test    byte ptr [rcx+1Ch], 8
0x18008e4ee  jz      short loc_18008E504
0x18008e4f0  mov     edx, 0D6h
0x18008e4f5  mov     r9d, r8d
0x18008e4f8  mov     r8, rsi
0x18008e4fb  mov     rcx, [rcx+10h]
0x18008e4ff  call    WPP_SF_d
0x18008e504  mov     ebx, 800704CFh
0x18008e509  jmp     loc_18008E5B2
0x18008e50e  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e515  cmp     rcx, r14
0x18008e518  jz      short loc_18008E534
0x18008e51a  test    byte ptr [rcx+1Ch], 8
0x18008e51e  jz      short loc_18008E534
0x18008e520  mov     edx, 0D7h
0x18008e525  mov     r9d, eax
0x18008e528  mov     r8, rsi
0x18008e52b  mov     rcx, [rcx+10h]
0x18008e52f  call    WPP_SF_d
0x18008e534  mov     rdx, [rsp+208h+InterfaceGuid]; InterfaceGuid
0x18008e539  lea     rcx, [rsp+208h+var_168]; int
0x18008e541  call    ?GetMapping@InterfaceIdentifier@@SA?AV?$tuple@KUIdentity@InterfaceIdentifier@@@std@@AEBU_GUID@@@Z; InterfaceIdentifier::GetMapping(_GUID const &)
0x18008e546  mov     ebx, [rsp+208h+var_148]
0x18008e54d  test    ebx, ebx
0x18008e54f  jnz     short loc_18008E5A7
0x18008e551  mov     rdx, [rsp+208h+var_1B8]; struct _GUID *
0x18008e556  lea     rcx, [rsp+208h+var_158]; union _NET_LUID_LH *
0x18008e55e  call    ?GetNdisPhysicalInterface@@YAKAEBT_NET_LUID_LH@@PEAU_GUID@@@Z; GetNdisPhysicalInterface(_NET_LUID_LH const &,_GUID *)
0x18008e563  mov     ebx, eax
0x18008e565  test    eax, eax
0x18008e567  jnz     short loc_18008E5A5
0x18008e569  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e570  cmp     rcx, r14
0x18008e573  jz      short loc_18008E598
0x18008e575  test    byte ptr [rcx+1Ch], 8
0x18008e579  jz      short loc_18008E598
0x18008e57b  mov     edx, 0D8h
0x18008e580  mov     r9, [rsp+208h+var_1B8]
0x18008e585  mov     r8, rsi
0x18008e588  mov     rcx, [rcx+10h]
0x18008e58c  call    WPP_SF__guid_
0x18008e591  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e598  mov     [rsp+208h+var_1C8], 1
0x18008e5a0  jmp     loc_18008E4AC
0x18008e5a5  test    ebx, ebx
0x18008e5a7  jle     short loc_18008E5B2
0x18008e5a9  movzx   ebx, bx
0x18008e5ac  or      ebx, 80070000h
0x18008e5b2  mov     eax, 1
0x18008e5b7  add     r13d, eax
0x18008e5ba  cmp     [rsp+208h+var_140], 0
0x18008e5c3  jz      short loc_18008E5DF
0x18008e5c5  lea     rcx, [rsp+208h+var_140]
0x18008e5cd  call    cs:__imp_CloseGetIPPhysicalInterfaceForDestination
0x18008e5d3  mov     [rsp+208h+var_140], 0
0x18008e5df  mov     rcx, r15; this
0x18008e5e2  call    ??_GResolvePhysicalInterfaceWorkItem@@QEAAPEAXI@Z; ResolvePhysicalInterfaceWorkItem::`scalar deleting destructor'(uint)
0x18008e5e7  xor     r15d, r15d
0x18008e5ea  mov     [rsp+208h+var_1A8], r15
0x18008e5ef  cmp     r13d, 2
0x18008e5f3  jb      loc_18008E345
0x18008e5f9  jmp     loc_18008E473
0x18008e5fe  lea     rdx, aUnableToCreate; "Unable to create DoneEvent for ResolveP"...
0x18008e605  lea     rcx, [rsp+208h+pExceptionObject]; this
0x18008e60d  call    ??0exception@std@@QEAA@QEBD@Z; std::exception::exception(char const * const)
0x18008e612  lea     rdx, _TI1?AVexception@std@@; pThrowInfo
0x18008e619  lea     rcx, [rsp+208h+pExceptionObject]; pExceptionObject
0x18008e621  call    _CxxThrowException_0
0x18008e627  lea     r14, WPP_GLOBAL_Control
0x18008e62e  lea     rsi, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x18008e635  mov     ebx, [rsp+208h+var_1C8]
0x18008e639  mov     eax, [rsp+208h+var_1B0]
0x18008e63d  mov     [rsp+208h+var_1C8], eax
0x18008e641  mov     r15, [rsp+208h+var_1A8]
0x18008e646  mov     r13, [rsp+208h+var_1A0]
0x18008e64b  mov     rax, [rsp+208h+var_198]
0x18008e650  mov     [rsp+208h+var_1B8], rax
0x18008e655  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e65c  cmp     [rsp+208h+var_140], 0
0x18008e665  jz      short loc_18008E688
0x18008e667  lea     rcx, [rsp+208h+var_140]
0x18008e66f  call    cs:__imp_CloseGetIPPhysicalInterfaceForDestination
0x18008e675  mov     [rsp+208h+var_140], 0
0x18008e681  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e688  test    r15, r15
0x18008e68b  jz      short loc_18008E69C
0x18008e68d  mov     rcx, r15; this
0x18008e690  call    ??_GResolvePhysicalInterfaceWorkItem@@QEAAPEAXI@Z; ResolvePhysicalInterfaceWorkItem::`scalar deleting destructor'(uint)
0x18008e695  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e69c  test    ebx, ebx
0x18008e69e  jns     short loc_18008E6CC
0x18008e6a0  cmp     rcx, r14
0x18008e6a3  jz      loc_18008E74D
0x18008e6a9  test    byte ptr [rcx+1Ch], 1
0x18008e6ad  jz      short loc_18008E72E
0x18008e6af  mov     edx, 0D9h
0x18008e6b4  mov     r9, r13
0x18008e6b7  mov     r8, rsi
0x18008e6ba  mov     rcx, [rcx+10h]
0x18008e6be  call    WPP_SF__guid_
0x18008e6c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e6ca  jmp     short loc_18008E72E
0x18008e6cc  cmp     [rsp+208h+var_1C8], 0
0x18008e6d1  jnz     short loc_18008E72E
0x18008e6d3  mov     [rsp+208h+var_1C8], 0
0x18008e6db  lea     r8, [rsp+208h+var_1C8]; int *
0x18008e6e0  xor     edx, edx; int *
0x18008e6e2  mov     rcx, r13; struct _GUID *
0x18008e6e5  call    ?IsInterfaceConnectedOrPhysical@@YAJPEBU_GUID@@PEAH1@Z; IsInterfaceConnectedOrPhysical(_GUID const *,int *,int *)
0x18008e6ea  test    eax, eax
0x18008e6ec  js      short loc_18008E6F5
0x18008e6ee  cmp     [rsp+208h+var_1C8], 0
0x18008e6f3  jnz     short loc_18008E6C3
0x18008e6f5  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e6fc  cmp     rcx, r14
0x18008e6ff  jz      short loc_18008E729
0x18008e701  test    byte ptr [rcx+1Ch], 4
0x18008e705  jz      short loc_18008E729
0x18008e707  mov     edx, 0DAh
0x18008e70c  mov     [rsp+208h+var_1E8], r13
0x18008e711  mov     r9, [rsp+208h+var_1B8]
0x18008e716  mov     r8, rsi
0x18008e719  mov     rcx, [rcx+10h]
0x18008e71d  call    WPP_SF__guid__guid_
0x18008e722  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e729  mov     ebx, 80070002h
0x18008e72e  cmp     rcx, r14
0x18008e731  jz      short loc_18008E74D
0x18008e733  test    byte ptr [rcx+1Ch], 8
0x18008e737  jz      short loc_18008E74D
0x18008e739  mov     edx, 0DBh
0x18008e73e  mov     r9d, ebx
0x18008e741  mov     r8, rsi
  ... truncated ...
```
