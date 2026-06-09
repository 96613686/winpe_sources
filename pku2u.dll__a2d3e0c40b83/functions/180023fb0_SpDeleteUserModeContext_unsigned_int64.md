# SpDeleteUserModeContext(unsigned __int64)

- ea: `0x180023fb0`
- end: `0x180024083`
- name: `?SpDeleteUserModeContext@@YAJ_K@Z`
- size: `211`
- prototype: `__int64 __fastcall(unsigned __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180023cb8`
- `0x180023ce0`
- `0x180023fb0`
- `0x18002f174`
- `0x18002fbe4`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18002401b`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002401b`
- `ntdll!RtlReleaseResource` at `0x180024039`
- `ntdll!RtlReleaseResource` at `0x180024039`

## pseudocode

```c
__int64 __fastcall SpDeleteUserModeContext(unsigned __int64 a1)
{
  int v2; // edi
  struct _WST_USERMODE_CONTEXT *v3; // rbx
  struct _WST_USERMODE_CONTEXT *v5; // [rsp+38h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_b11bc16789ec339e90a240f14eab96a8_Traceguids);
  v5 = 0;
  v2 = WSTReferenceUserModeContextByLsaHandle(a1, 1u, &v5);
  if ( v2 >= 0 )
  {
    RtlAcquireResourceExclusive(&Pku2uGlobalUserModeContextResource, 1u);
    v3 = v5;
    if ( *((char *)v5 + 80) < 0 )
      v2 = 590627;
    RtlReleaseResource(&Pku2uGlobalUserModeContextResource);
    WSTDereferenceUserModeContext(v3);
  }
  else
  {
    v2 = 0;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_b11bc16789ec339e90a240f14eab96a8_Traceguids, (unsigned int)v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180023fb0  mov     [rsp+arg_0], rbx
0x180023fb5  mov     [rsp+arg_10], rsi
0x180023fba  push    rdi
0x180023fbb  sub     rsp, 20h
0x180023fbf  mov     rbx, rcx
0x180023fc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180023fc9  lea     rsi, WPP_GLOBAL_Control
0x180023fd0  cmp     rcx, rsi
0x180023fd3  jz      short loc_180023FF0
0x180023fd5  test    byte ptr [rcx+1Ch], 8
0x180023fd9  jz      short loc_180023FF0
0x180023fdb  mov     rcx, [rcx+10h]
0x180023fdf  lea     r8, WPP_b11bc16789ec339e90a240f14eab96a8_Traceguids
0x180023fe6  mov     edx, 13h
0x180023feb  call    WPP_SF_
0x180023ff0  lea     r8, [rsp+28h+arg_8]; struct _WST_USERMODE_CONTEXT **
0x180023ff5  mov     [rsp+28h+arg_8], 0
0x180023ffe  mov     dl, 1; unsigned __int8
0x180024000  mov     rcx, rbx; unsigned __int64
0x180024003  call    ?WSTReferenceUserModeContextByLsaHandle@@YAJ_KEPEAPEAU_WST_USERMODE_CONTEXT@@@Z; WSTReferenceUserModeContextByLsaHandle(unsigned __int64,uchar,_WST_USERMODE_CONTEXT * *)
0x180024008  mov     edi, eax
0x18002400a  test    eax, eax
0x18002400c  jns     short loc_180024012
0x18002400e  xor     edi, edi
0x180024010  jmp     short loc_180024047
0x180024012  mov     dl, 1; Wait
0x180024014  lea     rcx, ?Pku2uGlobalUserModeContextResource@@3U_RTL_RESOURCE@@A; Resource
0x18002401b  call    cs:__imp_RtlAcquireResourceExclusive
0x180024021  mov     rbx, [rsp+28h+arg_8]
0x180024026  lea     rcx, ?Pku2uGlobalUserModeContextResource@@3U_RTL_RESOURCE@@A; Resource
0x18002402d  mov     eax, 90323h
0x180024032  test    byte ptr [rbx+50h], 80h
0x180024036  cmovnz  edi, eax
0x180024039  call    cs:__imp_RtlReleaseResource
0x18002403f  mov     rcx, rbx; struct _WST_USERMODE_CONTEXT *
0x180024042  call    ?WSTDereferenceUserModeContext@@YAXPEAU_WST_USERMODE_CONTEXT@@@Z; WSTDereferenceUserModeContext(_WST_USERMODE_CONTEXT *)
0x180024047  mov     rcx, cs:WPP_GLOBAL_Control
0x18002404e  cmp     rcx, rsi
0x180024051  jz      short loc_180024071
0x180024053  test    byte ptr [rcx+1Ch], 8
0x180024057  jz      short loc_180024071
0x180024059  mov     rcx, [rcx+10h]
0x18002405d  lea     r8, WPP_b11bc16789ec339e90a240f14eab96a8_Traceguids
0x180024064  mov     edx, 14h
0x180024069  mov     r9d, edi
0x18002406c  call    WPP_SF_d
0x180024071  mov     rbx, [rsp+28h+arg_0]
0x180024076  mov     eax, edi
0x180024078  mov     rsi, [rsp+28h+arg_10]
0x18002407d  add     rsp, 20h
0x180024081  pop     rdi
0x180024082  retn
```
