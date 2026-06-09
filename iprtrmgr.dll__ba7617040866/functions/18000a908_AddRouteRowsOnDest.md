# AddRouteRowsOnDest

- ea: `0x18000a908`
- end: `0x18000aa93`
- name: `AddRouteRowsOnDest`
- size: `395`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008e30`
- `0x180009150`

## callees

- `0x18000a654`
- `0x18000a908`
- `0x18000ac60`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000aa52`
- `KERNEL32!HeapFree` at `0x18000aa52`
- `KERNEL32!HeapAlloc` at `0x18000a958`
- `KERNEL32!HeapAlloc` at `0x18000a958`
- `rtm!RtmReleaseRoutes` at `0x18000aa1f`
- `rtm!RtmReleaseRoutes` at `0x18000aa1f`
- `rtm!RtmGetEnumRoutes` at `0x18000a9e1`
- `rtm!RtmGetEnumRoutes` at `0x18000a9e1`
- `rtm!RtmCreateRouteEnum` at `0x18000a9ab`
- `rtm!RtmCreateRouteEnum` at `0x18000a9ab`
- `rtm!RtmDeleteEnumHandle` at `0x18000aa35`
- `rtm!RtmDeleteEnumHandle` at `0x18000aa35`

## pseudocode

```c
__int64 __fastcall AddRouteRowsOnDest(RTM_DEST_HANDLE *a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned __int64 v6; // rax
  HANDLE *v8; // rdi
  DWORD v10; // ebx
  DWORD EnumRoutes; // eax
  UINT v12; // edx
  __int64 v13; // rbx
  DWORD i; // esi
  unsigned int NumRoutes; // [rsp+50h] [rbp-48h] BYREF
  HANDLE EnumHandle; // [rsp+58h] [rbp-40h] BYREF

  v6 = 8LL * g_rtmProfile.MaxHandlesInEnum;
  NumRoutes = 0;
  EnumHandle = 0;
  if ( v6 > 0xFFFFFFFF )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasRtrmgrTraceInfo,
        L"Leaving: AddRouteRowsOnDest: Integer Overflow");
    return 534;
  }
  else
  {
    v8 = (HANDLE *)HeapAlloc(IPRouterHeap, 0, (unsigned int)v6);
    if ( v8 )
    {
      v10 = RtmCreateRouteEnum(g_hLocalRoute, *a1, *(_DWORD *)(a2 + 12), 0, 0, 0, 0, 0, &EnumHandle);
      if ( !v10 )
      {
        do
        {
          NumRoutes = g_rtmProfile.MaxHandlesInEnum;
          EnumRoutes = RtmGetEnumRoutes(g_hLocalRoute, EnumHandle, &NumRoutes, v8);
          v12 = NumRoutes;
          v13 = 0;
          for ( i = EnumRoutes; (unsigned int)v13 < NumRoutes; v13 = (unsigned int)(v13 + 1) )
          {
            AddRouteRows(v8[v13], a5);
            v12 = NumRoutes;
          }
          RtmReleaseRoutes(g_hLocalRoute, v12, v8);
        }
        while ( !i );
        RtmDeleteEnumHandle(g_hLocalRoute, EnumHandle);
        v10 = 0;
        if ( i != 259 )
          v10 = i;
      }
      HeapFree(IPRouterHeap, 0, v8);
      return v10;
    }
    else
    {
      return 8;
    }
  }
}

```

## disassembly

```asm
0x18000a908  push    rbx
0x18000a90a  push    rbp
0x18000a90b  push    rsi
0x18000a90c  push    rdi
0x18000a90d  push    r12
0x18000a90f  push    r14
0x18000a911  push    r15
0x18000a913  sub     rsp, 60h
0x18000a917  mov     eax, cs:g_rtmProfile.MaxHandlesInEnum
0x18000a91d  mov     rbx, rcx
0x18000a920  shl     rax, 3
0x18000a924  mov     ecx, 0FFFFFFFFh
0x18000a929  mov     [rsp+98h+NumRoutes], 0
0x18000a931  mov     r15d, r9d
0x18000a934  mov     [rsp+98h+EnumHandle], 0
0x18000a93d  mov     r12, r8
0x18000a940  mov     r14, rdx
0x18000a943  cmp     rax, rcx
0x18000a946  ja      loc_18000AA5C
0x18000a94c  mov     rcx, cs:IPRouterHeap; hHeap
0x18000a953  xor     edx, edx; dwFlags
0x18000a955  mov     r8d, eax; dwBytes
0x18000a958  call    cs:__imp_HeapAlloc
0x18000a95e  mov     rdi, rax
0x18000a961  test    rax, rax
0x18000a964  jnz     short loc_18000A96E
0x18000a966  lea     eax, [rdi+8]
0x18000a969  jmp     loc_18000AA84
0x18000a96e  mov     r8d, [r14+0Ch]; TargetViews
0x18000a972  lea     rax, [rsp+98h+EnumHandle]
0x18000a977  mov     rdx, [rbx]; DestHandle
0x18000a97a  xor     r9d, r9d; EnumFlags
0x18000a97d  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x18000a984  mov     [rsp+98h+RtmEnumHandle], rax; RtmEnumHandle
0x18000a989  mov     [rsp+98h+CriteriaInterface], 0; CriteriaInterface
0x18000a991  mov     [rsp+98h+CriteriaRoute], 0; CriteriaRoute
0x18000a99a  mov     [rsp+98h+MatchingFlags], 0; MatchingFlags
0x18000a9a2  mov     [rsp+98h+StartDest], 0; StartDest
0x18000a9ab  call    cs:__imp_RtmCreateRouteEnum
0x18000a9b1  mov     ebx, eax
0x18000a9b3  test    eax, eax
0x18000a9b5  jnz     loc_18000AA46
0x18000a9bb  mov     rbp, [rsp+98h+arg_20]
0x18000a9c3  mov     eax, cs:g_rtmProfile.MaxHandlesInEnum
0x18000a9c9  lea     r8, [rsp+98h+NumRoutes]; NumRoutes
0x18000a9ce  mov     rdx, [rsp+98h+EnumHandle]; EnumHandle
0x18000a9d3  mov     r9, rdi; RouteHandles
0x18000a9d6  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x18000a9dd  mov     [rsp+98h+NumRoutes], eax
0x18000a9e1  call    cs:__imp_RtmGetEnumRoutes
0x18000a9e7  mov     edx, [rsp+98h+NumRoutes]
0x18000a9eb  xor     ebx, ebx
0x18000a9ed  mov     esi, eax
0x18000a9ef  test    edx, edx
0x18000a9f1  jz      short loc_18000AA15
0x18000a9f3  mov     edx, [r14+10h]
0x18000a9f7  mov     r9d, r15d
0x18000a9fa  mov     rcx, [rdi+rbx*8]; RouteHandle
0x18000a9fe  mov     r8, r12
0x18000aa01  mov     [rsp+98h+StartDest], rbp; __int64
0x18000aa06  call    AddRouteRows
0x18000aa0b  mov     edx, [rsp+98h+NumRoutes]; NumRoutes
0x18000aa0f  inc     ebx
0x18000aa11  cmp     ebx, edx
0x18000aa13  jb      short loc_18000A9F3
0x18000aa15  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x18000aa1c  mov     r8, rdi; RouteHandles
0x18000aa1f  call    cs:__imp_RtmReleaseRoutes
0x18000aa25  test    esi, esi
0x18000aa27  jz      short loc_18000A9C3
0x18000aa29  mov     rdx, [rsp+98h+EnumHandle]; EnumHandle
0x18000aa2e  mov     rcx, cs:g_hLocalRoute; RtmRegHandle
0x18000aa35  call    cs:__imp_RtmDeleteEnumHandle
0x18000aa3b  xor     ebx, ebx
0x18000aa3d  cmp     esi, 103h
0x18000aa43  cmovnz  ebx, esi
0x18000aa46  mov     rcx, cs:IPRouterHeap; hHeap
0x18000aa4d  mov     r8, rdi; lpMem
0x18000aa50  xor     edx, edx; dwFlags
0x18000aa52  call    cs:__imp_HeapFree
0x18000aa58  mov     eax, ebx
0x18000aa5a  jmp     short loc_18000AA84
0x18000aa5c  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18000aa63  jz      short loc_18000AA7F
0x18000aa65  lea     r8, aLeavingAddrout; "Leaving: AddRouteRowsOnDest: Integer Ov"...
0x18000aa6c  lea     rdx, RasRtrmgrTraceInfo
0x18000aa73  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000aa7a  call    McTemplateU0z_EventWriteTransfer
0x18000aa7f  mov     eax, 216h
0x18000aa84  add     rsp, 60h
0x18000aa88  pop     r15
0x18000aa8a  pop     r14
0x18000aa8c  pop     r12
0x18000aa8e  pop     rdi
0x18000aa8f  pop     rsi
0x18000aa90  pop     rbp
0x18000aa91  pop     rbx
0x18000aa92  retn
```
