# DeleteRtmRoutes

- ea: `0x18004b218`
- end: `0x18004b481`
- name: `DeleteRtmRoutes`
- size: `617`
- prototype: `__int64 __fastcall(RTM_ENTITY_HANDLE RtmRegHandle, ULONG CriteriaInterface)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002bf1c`
- `0x1800401a0`
- `0x18004ab80`

## callees

- `0x18000ac60`
- `0x18004b218`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18004b3a0`
- `KERNEL32!HeapFree` at `0x18004b429`
- `KERNEL32!HeapFree` at `0x18004b3a0`
- `KERNEL32!HeapFree` at `0x18004b429`
- `KERNEL32!HeapAlloc` at `0x18004b2a4`
- `KERNEL32!HeapAlloc` at `0x18004b2a4`
- `rtm!RtmDeleteRouteToDest` at `0x18004b3e7`
- `rtm!RtmDeleteRouteToDest` at `0x18004b3e7`
- `rtm!RtmReleaseRoutes` at `0x18004b3fc`
- `rtm!RtmReleaseRoutes` at `0x18004b3fc`
- `rtm!RtmGetEnumRoutes` at `0x18004b3c7`
- `rtm!RtmGetEnumRoutes` at `0x18004b3c7`
- `rtm!RtmCreateRouteEnum` at `0x18004b340`
- `rtm!RtmCreateRouteEnum` at `0x18004b340`
- `rtm!RtmDeleteEnumHandle` at `0x18004b417`
- `rtm!RtmDeleteEnumHandle` at `0x18004b417`

## string_xrefs

- `0x18004b43c`: `DeleteRtmRoutes: Integer Overflow`
- `0x18004b2c3`: `DeleteRtmRoutes: Error allocating %d bytes`
- `0x18004b357`: `DeleteRtmRoutes: Error %d creating handle for %d\n`

## pseudocode

```c
__int64 __fastcall DeleteRtmRoutes(RTM_ENTITY_HANDLE RtmRegHandle, ULONG CriteriaInterface, int a3)
{
  unsigned __int64 v6; // rax
  UINT v7; // ebx
  void *v8; // rdi
  DWORD v10; // eax
  DWORD v11; // ebx
  __int64 v12; // rbx
  DWORD i; // r15d
  unsigned int NumRoutes; // [rsp+50h] [rbp-B0h] BYREF
  DWORD ChangeFlags; // [rsp+54h] [rbp-ACh] BYREF
  HANDLE EnumHandle; // [rsp+58h] [rbp-A8h] BYREF
  int v17; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v18[2044]; // [rsp+74h] [rbp-8Ch] BYREF

  EnumHandle = 0;
  NumRoutes = 0;
  ChangeFlags = 0;
  v17 = 0;
  memset_0(v18, 0, sizeof(v18));
  v6 = 8LL * g_rtmProfile.MaxHandlesInEnum;
  if ( v6 > 0xFFFFFFFF )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"DeleteRtmRoutes: Integer Overflow");
    return 534;
  }
  else
  {
    v7 = 8 * g_rtmProfile.MaxHandlesInEnum;
    v8 = HeapAlloc(IPRouterHeap, 0, (unsigned int)v6);
    if ( v8 )
    {
      ChangeFlags = a3 == 0 ? 0x10 : 0;
      v10 = RtmCreateRouteEnum(RtmRegHandle, 0, 0, 0x10000u, 0, ChangeFlags, 0, CriteriaInterface, &EnumHandle);
      v11 = v10;
      if ( v10 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
        {
          LOWORD(v17) = 0;
          FormatRRASErrorString(&v17, L"DeleteRtmRoutes: Error %d creating handle for %d\n", v10, RtmRegHandle);
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v17);
        }
        HeapFree(IPRouterHeap, 0, v8);
        return v11;
      }
      else
      {
        do
        {
          NumRoutes = g_rtmProfile.MaxHandlesInEnum;
          v12 = 0;
          for ( i = RtmGetEnumRoutes(RtmRegHandle, EnumHandle, &NumRoutes, (PRTM_ROUTE_HANDLE)v8);
                (unsigned int)v12 < NumRoutes;
                v12 = (unsigned int)(v12 + 1) )
          {
            if ( RtmDeleteRouteToDest(RtmRegHandle, *((RTM_ROUTE_HANDLE *)v8 + v12), &ChangeFlags) )
              RtmReleaseRoutes(RtmRegHandle, 1u, (PRTM_ROUTE_HANDLE)v8 + v12);
          }
        }
        while ( !i );
        RtmDeleteEnumHandle(RtmRegHandle, EnumHandle);
        HeapFree(IPRouterHeap, 0, v8);
        return 0;
      }
    }
    else
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      {
        LOWORD(v17) = 0;
        FormatRRASErrorString(&v17, L"DeleteRtmRoutes: Error allocating %d bytes", v7);
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v17);
      }
      return 8;
    }
  }
}

```

## disassembly

```asm
0x18004b218  mov     [rsp-8+arg_10], rbx
0x18004b21d  push    rbp
0x18004b21e  push    rsi
0x18004b21f  push    rdi
0x18004b220  push    r14
0x18004b222  push    r15
0x18004b224  lea     rbp, [rsp-780h]
0x18004b22c  sub     rsp, 880h
0x18004b233  mov     rax, cs:__security_cookie
0x18004b23a  xor     rax, rsp
0x18004b23d  mov     [rbp+7A0h+var_30], rax
0x18004b244  mov     r14d, r8d
0x18004b247  mov     [rsp+8A0h+EnumHandle], 0
0x18004b250  mov     r15d, edx
0x18004b253  mov     [rsp+8A0h+NumRoutes], 0
0x18004b25b  mov     rsi, rcx
0x18004b25e  mov     [rsp+8A0h+ChangeFlags], 0
0x18004b266  xor     eax, eax
0x18004b268  lea     rcx, [rsp+8A0h+var_82C]; void *
0x18004b26d  xor     edx, edx; Val
0x18004b26f  mov     [rsp+8A0h+var_830], eax
0x18004b273  mov     r8d, 7FCh; Size
0x18004b279  call    memset_0
0x18004b27e  mov     eax, cs:g_rtmProfile.MaxHandlesInEnum
0x18004b284  mov     ecx, 0FFFFFFFFh
0x18004b289  shl     rax, 3
0x18004b28d  cmp     rax, rcx
0x18004b290  ja      loc_18004B433
0x18004b296  mov     rcx, cs:IPRouterHeap; hHeap
0x18004b29d  xor     edx, edx; dwFlags
0x18004b29f  mov     r8d, eax; dwBytes
0x18004b2a2  mov     ebx, eax
0x18004b2a4  call    cs:__imp_HeapAlloc
0x18004b2aa  mov     rdi, rax
0x18004b2ad  test    rax, rax
0x18004b2b0  jnz     short loc_18004B2FF
0x18004b2b2  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18004b2b9  jz      short loc_18004B2F5
0x18004b2bb  mov     r8d, ebx
0x18004b2be  mov     word ptr [rsp+8A0h+var_830], ax
0x18004b2c3  lea     rdx, aDeletertmroute_2; "DeleteRtmRoutes: Error allocating %d by"...
0x18004b2ca  lea     rcx, [rsp+8A0h+var_830]
0x18004b2cf  call    FormatRRASErrorString
0x18004b2d4  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18004b2db  jz      short loc_18004B2F5
0x18004b2dd  lea     r8, [rsp+8A0h+var_830]
0x18004b2e2  lea     rdx, RasRtrMgrTraceError
0x18004b2e9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004b2f0  call    McTemplateU0z_EventWriteTransfer
0x18004b2f5  mov     eax, 8
0x18004b2fa  jmp     loc_18004B45B
0x18004b2ff  lea     rcx, [rsp+8A0h+EnumHandle]
0x18004b304  neg     r14d
0x18004b307  mov     [rsp+8A0h+RtmEnumHandle], rcx; RtmEnumHandle
0x18004b30c  mov     r9d, 10000h; EnumFlags
0x18004b312  sbb     eax, eax
0x18004b314  mov     [rsp+8A0h+CriteriaInterface], r15d; CriteriaInterface
0x18004b319  not     eax
0x18004b31b  mov     [rsp+8A0h+CriteriaRoute], 0; CriteriaRoute
0x18004b324  and     eax, 10h
0x18004b327  xor     r8d, r8d; TargetViews
0x18004b32a  mov     [rsp+8A0h+MatchingFlags], eax; MatchingFlags
0x18004b32e  xor     edx, edx; DestHandle
0x18004b330  mov     rcx, rsi; RtmRegHandle
0x18004b333  mov     [rsp+8A0h+StartDest], 0; StartDest
0x18004b33c  mov     [rsp+8A0h+ChangeFlags], eax
0x18004b340  call    cs:__imp_RtmCreateRouteEnum
0x18004b346  mov     ebx, eax
0x18004b348  test    eax, eax
0x18004b34a  jz      short loc_18004B3AD
0x18004b34c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18004b353  jz      short loc_18004B394
0x18004b355  xor     ecx, ecx
0x18004b357  lea     rdx, aDeletertmroute_0; "DeleteRtmRoutes: Error %d creating hand"...
0x18004b35e  mov     word ptr [rsp+8A0h+var_830], cx
0x18004b363  mov     r9, rsi
0x18004b366  lea     rcx, [rsp+8A0h+var_830]
0x18004b36b  mov     r8d, eax
0x18004b36e  call    FormatRRASErrorString
0x18004b373  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x18004b37a  jz      short loc_18004B394
0x18004b37c  lea     r8, [rsp+8A0h+var_830]
0x18004b381  lea     rdx, RasRtrMgrTraceError
0x18004b388  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004b38f  call    McTemplateU0z_EventWriteTransfer
0x18004b394  mov     rcx, cs:IPRouterHeap; hHeap
0x18004b39b  mov     r8, rdi; lpMem
0x18004b39e  xor     edx, edx; dwFlags
0x18004b3a0  call    cs:__imp_HeapFree
0x18004b3a6  mov     eax, ebx
0x18004b3a8  jmp     loc_18004B45B
0x18004b3ad  mov     eax, cs:g_rtmProfile.MaxHandlesInEnum
0x18004b3b3  lea     r8, [rsp+8A0h+NumRoutes]; NumRoutes
0x18004b3b8  mov     rdx, [rsp+8A0h+EnumHandle]; EnumHandle
0x18004b3bd  mov     r9, rdi; RouteHandles
0x18004b3c0  mov     rcx, rsi; RtmRegHandle
0x18004b3c3  mov     [rsp+8A0h+NumRoutes], eax
0x18004b3c7  call    cs:__imp_RtmGetEnumRoutes
0x18004b3cd  xor     ebx, ebx
0x18004b3cf  mov     r15d, eax
0x18004b3d2  cmp     [rsp+8A0h+NumRoutes], ebx
0x18004b3d6  jbe     short loc_18004B40A
0x18004b3d8  lea     r14, [rdi+rbx*8]
0x18004b3dc  mov     rcx, rsi; RtmRegHandle
0x18004b3df  mov     rdx, [r14]; RouteHandle
0x18004b3e2  lea     r8, [rsp+8A0h+ChangeFlags]; ChangeFlags
0x18004b3e7  call    cs:__imp_RtmDeleteRouteToDest
0x18004b3ed  test    eax, eax
0x18004b3ef  jz      short loc_18004B402
0x18004b3f1  mov     r8, r14; RouteHandles
0x18004b3f4  mov     edx, 1; NumRoutes
0x18004b3f9  mov     rcx, rsi; RtmRegHandle
0x18004b3fc  call    cs:__imp_RtmReleaseRoutes
0x18004b402  inc     ebx
0x18004b404  cmp     ebx, [rsp+8A0h+NumRoutes]
0x18004b408  jb      short loc_18004B3D8
0x18004b40a  test    r15d, r15d
0x18004b40d  jz      short loc_18004B3AD
0x18004b40f  mov     rdx, [rsp+8A0h+EnumHandle]; EnumHandle
0x18004b414  mov     rcx, rsi; RtmRegHandle
0x18004b417  call    cs:__imp_RtmDeleteEnumHandle
0x18004b41d  mov     rcx, cs:IPRouterHeap; hHeap
0x18004b424  mov     r8, rdi; lpMem
0x18004b427  xor     edx, edx; dwFlags
0x18004b429  call    cs:__imp_HeapFree
0x18004b42f  xor     eax, eax
0x18004b431  jmp     short loc_18004B45B
0x18004b433  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18004b43a  jz      short loc_18004B456
0x18004b43c  lea     r8, aDeletertmroute_3; "DeleteRtmRoutes: Integer Overflow"
0x18004b443  lea     rdx, RasRtrmgrTraceInfo
0x18004b44a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18004b451  call    McTemplateU0z_EventWriteTransfer
0x18004b456  mov     eax, 216h
0x18004b45b  mov     rcx, [rbp+7A0h+var_30]
0x18004b462  xor     rcx, rsp; StackCookie
0x18004b465  call    __security_check_cookie
0x18004b46a  mov     rbx, [rsp+8A0h+arg_10]
0x18004b472  add     rsp, 880h
0x18004b479  pop     r15
0x18004b47b  pop     r14
0x18004b47d  pop     rdi
0x18004b47e  pop     rsi
0x18004b47f  pop     rbp
0x18004b480  retn
```
