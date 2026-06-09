# ChangeDefaultRouteMetrics

- ea: `0x18003f7c8`
- end: `0x18003fb19`
- name: `ChangeDefaultRouteMetrics`
- size: `849`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x180010b80`
- `0x180010cd8`

## callees

- `0x18003f7c8`
- `0x180051ef8`
- `0x180057aa4`
- `0x180057c48`
- `0x180058536`
- `0x180058570`
- `0x180058600`

## import_xrefs

- `msvcrt!_resetstkoflw` at `0x18003faef`
- `msvcrt!_resetstkoflw` at `0x18003faef`
- `rtm!RtmReleaseRoutes` at `0x18003faa9`
- `rtm!RtmReleaseRoutes` at `0x18003faa9`
- `rtm!RtmGetEnumRoutes` at `0x18003fac6`
- `rtm!RtmGetEnumRoutes` at `0x18003fac6`
- `rtm!RtmCreateRouteEnum` at `0x18003f94d`
- `rtm!RtmCreateRouteEnum` at `0x18003f94d`
- `rtm!RtmDeleteEnumHandle` at `0x18003fadf`
- `rtm!RtmDeleteEnumHandle` at `0x18003fadf`
- `rtm!RtmGetExactMatchDestination` at `0x18003f90e`
- `rtm!RtmGetExactMatchDestination` at `0x18003f90e`
- `rtm!RtmReleaseDestInfo` at `0x18003f965`
- `rtm!RtmReleaseDestInfo` at `0x18003f965`
- `rtm!RtmReleaseRouteInfo` at `0x18003f9d7`
- `rtm!RtmReleaseRouteInfo` at `0x18003f9d7`
- `rtm!RtmGetRouteInfo` at `0x18003f993`
- `rtm!RtmGetRouteInfo` at `0x18003f993`
- `rtm!RtmUpdateAndUnlockRoute` at `0x18003fa62`
- `rtm!RtmUpdateAndUnlockRoute` at `0x18003fa62`
- `rtm!RtmLockRoute` at `0x18003fa01`
- `rtm!RtmLockRoute` at `0x18003fa83`
- `rtm!RtmLockRoute` at `0x18003fa01`
- `rtm!RtmLockRoute` at `0x18003fa83`

## pseudocode

```c
int __fastcall ChangeDefaultRouteMetrics(int a1, int a2, struct _GUID *a3)
{
  unsigned int DestHandle_high; // edi
  void *RtmRegistrationHandle; // rbx
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rcx
  void *v11; // rsp
  void *v12; // rsp
  unsigned __int64 v13; // r9
  unsigned __int64 v14; // rcx
  unsigned __int64 v15; // rcx
  void *v16; // rsp
  void *v17; // rsp
  DWORD RouteEnum; // eax
  void *v19; // rcx
  unsigned int v20; // r14d
  void *v21; // rdi
  unsigned int i; // ecx
  struct _RTM_ROUTE_INFO RouteInfo; // [rsp+50h] [rbp+0h] BYREF
  _BYTE v25[96]; // [rsp+90h] [rbp+40h] BYREF
  struct _RTM_DEST_INFO DestHandle; // [rsp+F0h] [rbp+A0h] BYREF
  struct _RTM_NET_ADDRESS DestAddress; // [rsp+150h] [rbp+100h] BYREF

  *(_QWORD *)&RouteInfo.PrefInfo.Preference = a3;
  memset(&DestAddress, 0, sizeof(DestAddress));
  memset_0(&DestHandle, 0, sizeof(DestHandle));
  RouteInfo.Neighbour = 0;
  LODWORD(RouteInfo.DestHandle) = 0;
  DestHandle_high = a2 != 0 ? 33 : 87;
  HIDWORD(RouteInfo.DestHandle) = DestHandle_high;
  RtmRegistrationHandle = (void *)GetRtmRegistrationHandle(a3, DestHandle_high, 2u);
  memset_0(v25, 0, sizeof(v25));
  memset(&DestAddress, 0, sizeof(DestAddress));
  v8 = 8LL * g_rtmProfile.MaxHandlesInEnum;
  if ( v8 > 0xFFFFFFFF )
    return v8;
  v9 = (unsigned int)v8 + 15LL;
  if ( v9 <= (unsigned int)v8 )
    v9 = 0xFFFFFFFFFFFFFF0LL;
  v10 = v9 & 0xFFFFFFFFFFFFFFF0uLL;
  v11 = alloca(v10);
  v12 = alloca(v10);
  RouteInfo.EntitySpecificInfo = &RouteInfo;
  LODWORD(v8) = RTMSIZEOFROUTEINFO(g_rtmProfile.MaxNextHopsInRoute, &RouteInfo);
  if ( (_DWORD)v8 )
    return v8;
  v14 = LODWORD(RouteInfo.DestHandle) + 15LL;
  if ( v14 <= LODWORD(RouteInfo.DestHandle) )
    v14 = v13;
  v15 = v14 & 0xFFFFFFFFFFFFFFF0uLL;
  v16 = alloca(v15);
  v17 = alloca(v15);
  *(_QWORD *)&RouteInfo.NextHopsList.NumNextHops = &RouteInfo;
  LODWORD(v8) = RtmGetExactMatchDestination(RtmRegistrationHandle, &DestAddress, 0, 0, &DestHandle);
  if ( (_DWORD)v8 )
    return v8;
  RouteInfo.Neighbour = 0;
  RouteEnum = RtmCreateRouteEnum(RtmRegistrationHandle, DestHandle.DestHandle, 0, 0, 0, 0, 0, 0, &RouteInfo.Neighbour);
  v19 = RtmRegistrationHandle;
  if ( RouteEnum )
    goto LABEL_9;
LABEL_28:
  LODWORD(RouteInfo.DestHandle) = g_rtmProfile.MaxHandlesInEnum;
  RtmGetEnumRoutes(v19, RouteInfo.Neighbour, (PUINT)&RouteInfo, &RouteInfo.DestHandle);
  if ( LODWORD(RouteInfo.DestHandle) )
  {
    v20 = 0;
    while ( 1 )
    {
      *(_QWORD *)&RouteInfo.State = 0;
      LODWORD(RouteInfo.RouteOwner) = 0;
      if ( !RtmGetRouteInfo(RtmRegistrationHandle, *(&RouteInfo.DestHandle + v20), &RouteInfo, 0) )
        break;
LABEL_26:
      if ( ++v20 >= LODWORD(RouteInfo.DestHandle) )
      {
        RtmReleaseRoutes(RtmRegistrationHandle, (UINT)RouteInfo.DestHandle, &RouteInfo.DestHandle);
        v19 = RtmRegistrationHandle;
        goto LABEL_28;
      }
    }
    GetAllRtmRegistrationHandles(*(_QWORD *)&RouteInfo.PrefInfo.Preference, DestHandle_high, v25);
    v21 = 0;
    for ( i = 0; i < 5; ++i )
    {
      if ( RouteInfo.RouteOwner == *(RTM_ENTITY_HANDLE *)&v25[16 * i + 8] )
      {
        v21 = *(void **)&v25[16 * i + 8];
        break;
      }
    }
    RtmReleaseRouteInfo(RtmRegistrationHandle, &RouteInfo);
    if ( v21 && !RtmLockRoute(v21, *(&RouteInfo.DestHandle + v20), 1, 1, (PRTM_ROUTE_INFO *)&RouteInfo.State) )
    {
      if ( a1 )
      {
        ++*(_DWORD *)(*(_QWORD *)&RouteInfo.State + 28LL);
      }
      else
      {
        if ( *(_DWORD *)(*(_QWORD *)&RouteInfo.State + 28LL) <= 1u )
        {
LABEL_24:
          RtmLockRoute(v21, *(&RouteInfo.DestHandle + v20), 1, 0, 0);
          goto LABEL_25;
        }
        --*(_DWORD *)(*(_QWORD *)&RouteInfo.State + 28LL);
      }
      LODWORD(RouteInfo.RouteOwner) = 0;
      if ( RtmUpdateAndUnlockRoute(
             v21,
             *(&RouteInfo.DestHandle + v20),
             0xFFFFFFFF,
             0,
             0,
             0,
             (PRTM_ROUTE_CHANGE_FLAGS)&RouteInfo.RouteOwner) )
      {
        goto LABEL_24;
      }
    }
LABEL_25:
    DestHandle_high = HIDWORD(RouteInfo.DestHandle);
    goto LABEL_26;
  }
  RtmDeleteEnumHandle(RtmRegistrationHandle, RouteInfo.Neighbour);
  v19 = RtmRegistrationHandle;
LABEL_9:
  LODWORD(v8) = RtmReleaseDestInfo(v19, &DestHandle);
  return v8;
}

```

## disassembly

```asm
0x18003f7c8  push    rbp
0x18003f7ca  push    rbx
0x18003f7cb  push    rsi
0x18003f7cc  push    rdi
0x18003f7cd  push    r12
0x18003f7cf  push    r13
0x18003f7d1  push    r14
0x18003f7d3  push    r15
0x18003f7d5  sub     rsp, 178h
0x18003f7dc  lea     rbp, [rsp+50h]
0x18003f7e1  mov     rax, cs:__security_cookie
0x18003f7e8  xor     rax, rbp
0x18003f7eb  mov     [rbp+160h+var_48], rax
0x18003f7f2  mov     rsi, r8
0x18003f7f5  mov     qword ptr [rbp+160h+RouteInfo.PrefInfo.Preference], r8
0x18003f7f9  mov     ebx, edx
0x18003f7fb  mov     r13d, ecx
0x18003f7fe  xorps   xmm0, xmm0
0x18003f801  xor     eax, eax
0x18003f803  movups  xmmword ptr [rbp+160h+DestAddress.AddressFamily], xmm0
0x18003f80a  mov     dword ptr [rbp+160h+DestAddress.AddrBits+0Ch], eax
0x18003f810  xor     edx, edx; Val
0x18003f812  lea     r8d, [rax+58h]; Size
0x18003f816  lea     rcx, [rbp+160h+DestHandle]; void *
0x18003f81d  call    memset_0
0x18003f822  xor     r15d, r15d
0x18003f825  mov     [rbp+160h+RouteInfo.Neighbour], r15
0x18003f829  mov     dword ptr [rbp+160h+RouteInfo.DestHandle], r15d
0x18003f82d  neg     ebx
0x18003f82f  sbb     edi, edi
0x18003f831  and     edi, 0FFFFFFCAh
0x18003f834  add     edi, 57h ; 'W'
0x18003f837  mov     dword ptr [rbp+160h+RouteInfo.DestHandle+4], edi
0x18003f83a  lea     r8d, [r15+2]; unsigned int
0x18003f83e  mov     edx, edi; unsigned int
0x18003f840  mov     rcx, rsi; struct _GUID *
0x18003f843  call    GetRtmRegistrationHandle
0x18003f848  mov     rbx, rax
0x18003f84b  xor     edx, edx; Val
0x18003f84d  lea     r8d, [r15+60h]; Size
0x18003f851  lea     rcx, [rbp+160h+var_120]; void *
0x18003f855  call    memset_0
0x18003f85a  xorps   xmm0, xmm0
0x18003f85d  xor     eax, eax
0x18003f85f  movups  xmmword ptr [rbp+160h+DestAddress.AddressFamily], xmm0
0x18003f866  mov     dword ptr [rbp+160h+DestAddress.AddrBits+0Ch], eax
0x18003f86c  mov     eax, cs:g_rtmProfile.MaxHandlesInEnum
0x18003f872  shl     rax, 3
0x18003f876  mov     ecx, 0FFFFFFFFh
0x18003f87b  cmp     rax, rcx
0x18003f87e  ja      loc_18003FAED
0x18003f884  mov     eax, eax
0x18003f886  lea     rcx, [rax+0Fh]
0x18003f88a  mov     r9, 0FFFFFFFFFFFFFF0h
0x18003f894  cmp     rcx, rax
0x18003f897  ja      short loc_18003F89C
0x18003f899  mov     rcx, r9
0x18003f89c  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18003f8a0  mov     rax, rcx
0x18003f8a3  call    _alloca_probe
0x18003f8a8  sub     rsp, rcx
0x18003f8ab  lea     rsi, [rsp+1B0h+RouteInfo]
0x18003f8b0  mov     [rbp+160h+RouteInfo.EntitySpecificInfo], rsi
0x18003f8b4  lea     rdx, [rbp+160h+RouteInfo]
0x18003f8b8  mov     ecx, cs:g_rtmProfile.MaxNextHopsInRoute
0x18003f8be  call    RTMSIZEOFROUTEINFO
0x18003f8c3  test    eax, eax
0x18003f8c5  jnz     loc_18003FAF6
0x18003f8cb  mov     eax, dword ptr [rbp+160h+RouteInfo.DestHandle]
0x18003f8ce  lea     rcx, [rax+0Fh]
0x18003f8d2  cmp     rcx, rax
0x18003f8d5  ja      short loc_18003F8DA
0x18003f8d7  mov     rcx, r9
0x18003f8da  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18003f8de  mov     rax, rcx
0x18003f8e1  call    _alloca_probe
0x18003f8e6  sub     rsp, rcx
0x18003f8e9  lea     r12, [rsp+1B0h+RouteInfo]
0x18003f8ee  mov     qword ptr [rbp+160h+RouteInfo.NextHopsList.NumNextHops], r12
0x18003f8f2  lea     rax, [rbp+160h+DestHandle]
0x18003f8f9  mov     [rsp+1B0h+DestInfo], rax; DestInfo
0x18003f8fe  xor     r9d, r9d; TargetViews
0x18003f901  xor     r8d, r8d; ProtocolId
0x18003f904  lea     rdx, [rbp+160h+DestAddress]; DestAddress
0x18003f90b  mov     rcx, rbx; RtmRegHandle
0x18003f90e  call    cs:__imp_RtmGetExactMatchDestination
0x18003f914  test    eax, eax
0x18003f916  jnz     loc_18003FAF6
0x18003f91c  mov     [rbp+160h+RouteInfo.Neighbour], r15
0x18003f920  lea     rax, [rbp+160h+RouteInfo.Neighbour]
0x18003f924  mov     [rsp+1B0h+RtmEnumHandle], rax; RtmEnumHandle
0x18003f929  mov     [rsp+1B0h+CriteriaInterface], r15d; CriteriaInterface
0x18003f92e  mov     [rsp+1B0h+CriteriaRoute], r15; CriteriaRoute
0x18003f933  mov     [rsp+1B0h+MatchingFlags], r15d; MatchingFlags
0x18003f938  mov     [rsp+1B0h+DestInfo], r15; StartDest
0x18003f93d  xor     r9d, r9d; EnumFlags
0x18003f940  xor     r8d, r8d; TargetViews
0x18003f943  mov     rdx, [rbp+160h+DestHandle.DestHandle]; DestHandle
0x18003f94a  mov     rcx, rbx; RtmRegHandle
0x18003f94d  call    cs:__imp_RtmCreateRouteEnum
0x18003f953  mov     rcx, rbx; RtmRegHandle
0x18003f956  test    eax, eax
0x18003f958  jz      loc_18003FAB2
0x18003f95e  lea     rdx, [rbp+160h+DestHandle]; DestInfo
0x18003f965  call    cs:__imp_RtmReleaseDestInfo
0x18003f96b  jmp     loc_18003FAF6
0x18003f970  mov     r14d, r15d
0x18003f973  test    eax, eax
0x18003f975  jz      loc_18003FAA1
0x18003f97b  mov     qword ptr [rbp+160h+RouteInfo.State], r15
0x18003f97f  mov     dword ptr [rbp+160h+RouteInfo.RouteOwner], r15d
0x18003f983  mov     r15d, r14d
0x18003f986  xor     r9d, r9d; DestAddress
0x18003f989  mov     r8, r12; RouteInfo
0x18003f98c  mov     rdx, [rsi+r15*8]; RouteHandle
0x18003f990  mov     rcx, rbx; RtmRegHandle
0x18003f993  call    cs:__imp_RtmGetRouteInfo
0x18003f999  test    eax, eax
0x18003f99b  jnz     loc_18003FA8C
0x18003f9a1  lea     r8, [rbp+160h+var_120]
0x18003f9a5  mov     edx, edi
0x18003f9a7  mov     rcx, qword ptr [rbp+160h+RouteInfo.PrefInfo.Preference]
0x18003f9ab  call    GetAllRtmRegistrationHandles
0x18003f9b0  xor     edi, edi
0x18003f9b2  xor     ecx, ecx
0x18003f9b4  cmp     ecx, 5
0x18003f9b7  jnb     short loc_18003F9D1
0x18003f9b9  mov     eax, ecx
0x18003f9bb  add     rax, rax
0x18003f9be  mov     rdx, [rbp+rax*8+160h+var_118]
0x18003f9c3  cmp     [r12+8], rdx
0x18003f9c8  jz      short loc_18003F9CE
0x18003f9ca  inc     ecx
0x18003f9cc  jmp     short loc_18003F9B4
0x18003f9ce  mov     rdi, rdx
0x18003f9d1  mov     rdx, r12; RouteInfo
0x18003f9d4  mov     rcx, rbx; RtmRegHandle
0x18003f9d7  call    cs:__imp_RtmReleaseRouteInfo
0x18003f9dd  test    rdi, rdi
0x18003f9e0  jz      loc_18003FA89
0x18003f9e6  lea     rax, [rbp+160h+RouteInfo.State]
0x18003f9ea  mov     [rsp+1B0h+DestInfo], rax; RoutePointer
0x18003f9ef  mov     eax, 1
0x18003f9f4  mov     r9d, eax; LockRoute
0x18003f9f7  mov     r8d, eax; Exclusive
0x18003f9fa  mov     rdx, [rsi+r15*8]; RouteHandle
0x18003f9fe  mov     rcx, rdi; RtmRegHandle
0x18003fa01  call    cs:__imp_RtmLockRoute
0x18003fa07  xor     ecx, ecx
0x18003fa09  test    eax, eax
0x18003fa0b  jnz     short loc_18003FA89
0x18003fa0d  test    r13d, r13d
0x18003fa10  jnz     short loc_18003FA28
0x18003fa12  mov     rax, qword ptr [rbp+160h+RouteInfo.State]
0x18003fa16  cmp     dword ptr [rax+1Ch], 1
0x18003fa1a  ja      short loc_18003FA23
0x18003fa1c  mov     [rsp+1B0h+DestInfo], rcx
0x18003fa21  jmp     short loc_18003FA75
0x18003fa23  test    r13d, r13d
0x18003fa26  jz      short loc_18003FA31
0x18003fa28  mov     rax, qword ptr [rbp+160h+RouteInfo.State]
0x18003fa2c  inc     dword ptr [rax+1Ch]
0x18003fa2f  jmp     short loc_18003FA3D
0x18003fa31  mov     rax, qword ptr [rbp+160h+RouteInfo.State]
0x18003fa35  mov     edx, 0FFFFFFFFh
0x18003fa3a  add     [rax+1Ch], edx
0x18003fa3d  mov     dword ptr [rbp+160h+RouteInfo.RouteOwner], ecx
0x18003fa40  lea     rax, [rbp+160h+RouteInfo.RouteOwner]
0x18003fa44  mov     [rsp+1B0h+CriteriaRoute], rax; ChangeFlags
0x18003fa49  mov     qword ptr [rsp+1B0h+MatchingFlags], rcx; NotifyHandle
0x18003fa4e  mov     dword ptr [rsp+1B0h+DestInfo], ecx; NotifyType
0x18003fa52  xor     r9d, r9d; RouteListHandle
0x18003fa55  mov     r8d, 0FFFFFFFFh; TimeToLive
0x18003fa5b  mov     rdx, [rsi+r15*8]; RouteHandle
0x18003fa5f  mov     rcx, rdi; RtmRegHandle
0x18003fa62  call    cs:__imp_RtmUpdateAndUnlockRoute
0x18003fa68  test    eax, eax
0x18003fa6a  jz      short loc_18003FA89
0x18003fa6c  mov     [rsp+1B0h+DestInfo], 0; RoutePointer
0x18003fa75  xor     r9d, r9d; LockRoute
0x18003fa78  lea     r8d, [r9+1]; Exclusive
0x18003fa7c  mov     rdx, [rsi+r15*8]; RouteHandle
0x18003fa80  mov     rcx, rdi; RtmRegHandle
0x18003fa83  call    cs:__imp_RtmLockRoute
0x18003fa89  mov     edi, dword ptr [rbp+160h+RouteInfo.DestHandle+4]
0x18003fa8c  inc     r14d
0x18003fa8f  mov     eax, dword ptr [rbp+160h+RouteInfo.DestHandle]
0x18003fa92  cmp     r14d, eax
0x18003fa95  mov     r15d, 0
0x18003fa9b  jb      loc_18003F97B
0x18003faa1  mov     r8, rsi; RouteHandles
0x18003faa4  mov     edx, eax; NumRoutes
0x18003faa6  mov     rcx, rbx; RtmRegHandle
0x18003faa9  call    cs:__imp_RtmReleaseRoutes
0x18003faaf  mov     rcx, rbx; RtmRegHandle
0x18003fab2  mov     eax, cs:g_rtmProfile.MaxHandlesInEnum
0x18003fab8  mov     dword ptr [rbp+160h+RouteInfo.DestHandle], eax
0x18003fabb  mov     r9, rsi; RouteHandles
0x18003fabe  lea     r8, [rbp+160h+RouteInfo]; NumRoutes
0x18003fac2  mov     rdx, [rbp+160h+RouteInfo.Neighbour]; EnumHandle
0x18003fac6  call    cs:__imp_RtmGetEnumRoutes
0x18003facc  mov     eax, dword ptr [rbp+160h+RouteInfo.DestHandle]
0x18003facf  cmp     eax, 1
0x18003fad2  jnb     loc_18003F970
0x18003fad8  mov     rdx, [rbp+160h+RouteInfo.Neighbour]; EnumHandle
0x18003fadc  mov     rcx, rbx; RtmRegHandle
0x18003fadf  call    cs:__imp_RtmDeleteEnumHandle
0x18003fae5  mov     rcx, rbx
0x18003fae8  jmp     loc_18003F95E
0x18003faed  jmp     short loc_18003FAF6
0x18003faef  call    cs:__imp__resetstkoflw
0x18003faf5  nop
0x18003faf6  mov     rcx, [rbp+160h+var_48]
0x18003fafd  xor     rcx, rbp; StackCookie
0x18003fb00  call    __security_check_cookie
0x18003fb05  lea     rsp, [rbp+128h]
0x18003fb0c  pop     r15
0x18003fb0e  pop     r14
0x18003fb10  pop     r13
0x18003fb12  pop     r12
0x18003fb14  pop     rdi
0x18003fb15  pop     rsi
0x18003fb16  pop     rbx
0x18003fb17  pop     rbp
0x18003fb18  retn
```
