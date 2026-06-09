# LsapFindConnectedUserByInternetSid(void *,void * *)

- ea: `0x180060888`
- end: `0x180060c83`
- name: `?LsapFindConnectedUserByInternetSid@@YAJPEAXPEAPEAX@Z`
- size: `1019`
- prototype: `__int64 __fastcall(PSID Sid, void **)`
- caller_count: `3`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800043bc`
- `0x180060740`
- `0x180124194`

## callees

- `0x18000c300`
- `0x18000dd90`
- `0x18000f808`
- `0x180011278`
- `0x18005fa30`
- `0x18005fecc`
- `0x180060888`
- `0x180060c8c`
- `0x180060cb0`
- `0x180060f20`
- `0x180061cb8`
- `0x180078a74`
- `0x1800bbbfc`

## import_xrefs

- `ntdll!RtlCopySid` at `0x180060b84`
- `ntdll!RtlCopySid` at `0x180060b84`
- `ntdll!RtlLengthSid` at `0x180060a04`
- `ntdll!RtlLengthSid` at `0x180060b5a`
- `ntdll!RtlLengthSid` at `0x180060a04`
- `ntdll!RtlLengthSid` at `0x180060b5a`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIFreeSidAndAttributesList` at `0x180060968`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIFreeSidAndAttributesList` at `0x180060968`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrCloseHandle` at `0x180060bba`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrCloseHandle` at `0x180060bba`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIGetUserLogonInformation2` at `0x180060a70`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamIGetUserLogonInformation2` at `0x180060a70`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrRidToSid` at `0x180060b3b`
- `ext-ms-win-samsrv-accountstore-l1-1-0!SamrRidToSid` at `0x180060b3b`

## string_xrefs

- `0x1800608b1`: `LsapFindConnectedUserByInternetSid`
- `0x1800609b1`: `LsapFindConnectedUserByInternetSid`
- `0x180060bfc`: `LsapSamExtRidToSid`
- `0x180060c1b`: `LsapIsUserSidIssuedByMsaIdProv`

## pseudocode

```c
__int64 __fastcall LsapFindConnectedUserByInternetSid(PSID Sid, struct _RTL_BALANCED_NODE **a2)
{
  void *v4; // rdx
  struct _RTL_BALANCED_NODE *v5; // rcx
  __int64 v6; // r8
  int v7; // r14d
  NTSTATUS v8; // ebx
  PSID v9; // rcx
  LsaHandleCache *v10; // rcx
  int v11; // edx
  int inited; // eax
  __int16 v14; // ax
  void *v15; // rbx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  int v19; // ebx
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r9
  unsigned int v23; // ebx
  __int64 v24; // rsi
  ULONG v25; // ebx
  struct _RTL_BALANCED_NODE *NoZero; // rax
  __int64 v27; // rdx
  const char *v28; // rcx
  __int128 v29; // [rsp+50h] [rbp-20h] BYREF
  __int128 v30; // [rsp+60h] [rbp-10h] BYREF
  struct _USER_INTERNAL6_INFORMATION *v31; // [rsp+A8h] [rbp+38h] BYREF
  __int64 v32; // [rsp+B0h] [rbp+40h] BYREF
  PSID Sida; // [rsp+B8h] [rbp+48h] BYREF

  v32 = 0;
  v31 = 0;
  Sida = 0;
  v29 = 0;
  v30 = 0;
  CONNECTED_TRACE_ENTER("LsapFindConnectedUserByInternetSid");
  if ( a2 )
    *a2 = 0;
  if ( !(unsigned int)LsapCheckConnectedUserEnabled() )
  {
    v7 = 0;
    v8 = -1073741637;
    goto LABEL_8;
  }
  if ( !(unsigned int)LsapIsUserSidIssuedByMsaIdProv(Sid) )
  {
    v7 = 0;
    v8 = -1073741704;
    v5 = (struct _RTL_BALANCED_NODE *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        (unsigned int)WPP_beece53709d13be865c3a44b1735e315_Traceguids,
        (unsigned int)"LsapIsUserSidIssuedByMsaIdProv",
        120);
    goto LABEL_8;
  }
  v7 = 1;
  inited = LsapLazyInitSamConnection();
  v8 = inited;
  if ( inited < 0 )
  {
    v27 = (unsigned int)inited;
    v28 = "LsapLazyInitSamConnection";
    goto LABEL_56;
  }
  v14 = RtlLengthSid(Sid);
  v15 = g_hIdProvExtSamAccountDomain;
  LOWORD(v29) = v14;
  WORD1(v29) = v14;
  *((_QWORD *)&v29 + 1) = Sid;
  if ( !(unsigned __int8)IsSamIDecodeClaimsBlobPresent(v17, v16, v18) )
  {
    v19 = -1073741637;
    goto LABEL_61;
  }
  v19 = SamIGetUserLogonInformation2(v15, 0x8000, &v29, 1048580, 1310720, 0, &v31, &v30, &v32);
  if ( v19 < 0 )
  {
LABEL_61:
    CONNECTED_TRACE_ERROR("SamIGetUserLogonInformation2", (unsigned int)v19);
    v8 = -1073741724;
    goto LABEL_8;
  }
  if ( (*((_DWORD *)v31 + 82) & 0x140000) != 0x140000 || (*((_DWORD *)v31 + 71) & 0x100004) != 0x100004 )
    goto LABEL_38;
  v20 = *((_QWORD *)v31 + 56) - *(_QWORD *)&GUID_NULL.Data1;
  if ( !v20 )
    v20 = *((_QWORD *)v31 + 57) - *(_QWORD *)GUID_NULL.Data4;
  if ( !v20 )
  {
LABEL_38:
    v8 = -1073741724;
    v5 = (struct _RTL_BALANCED_NODE *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_8;
    v21 = 14;
    v22 = 3221225572LL;
    goto LABEL_41;
  }
  if ( (*((_BYTE *)v31 + 280) & 1) != 0 )
  {
    v8 = -1073741710;
    v5 = (struct _RTL_BALANCED_NODE *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (LsaHandleCache *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_8;
    v21 = 15;
    v22 = 3221225586LL;
LABEL_41:
    WPP_SF_d(v5->ParentValue, v21, WPP_da3d202165313132ccfab67d2692d0fe_Traceguids, v22);
    goto LABEL_8;
  }
  v23 = *((_DWORD *)v31 + 68);
  v24 = v32;
  if ( !(unsigned __int8)IsSamIDecodeClaimsBlobPresent(v31, v4, v6) )
  {
    v8 = -1073741637;
    goto LABEL_55;
  }
  v8 = SamrRidToSid(v24, v23, &Sida);
  if ( v8 < 0 )
  {
LABEL_55:
    v27 = (unsigned int)v8;
    v28 = "LsapSamExtRidToSid";
LABEL_56:
    CONNECTED_TRACE_ERROR(v28, v27);
    goto LABEL_8;
  }
  if ( !a2 )
    goto LABEL_48;
  v25 = RtlLengthSid(Sida);
  NoZero = (struct _RTL_BALANCED_NODE *)LsapAllocateNoZero(v25);
  *a2 = NoZero;
  if ( NoZero )
  {
    v8 = RtlCopySid(v25, NoZero, Sida);
LABEL_48:
    if ( v8 >= 0 )
      goto LABEL_12;
LABEL_8:
    if ( !a2 )
      goto LABEL_12;
    goto LABEL_9;
  }
  v8 = -1073741801;
LABEL_9:
  v5 = *a2;
  if ( *a2 )
    LsapSubProv_FreeRoutine(v5, v4);
  *a2 = 0;
LABEL_12:
  if ( v32 && (unsigned __int8)IsSamIDecodeClaimsBlobPresent(v5, v4, v6) )
    SamrCloseHandle(&v32);
  if ( v31 )
    LsapSamExtFreeUserInternal6Information(v31);
  v9 = Sida;
  if ( Sida )
    LsapSamExtFreeVoid(Sida);
  if ( (unsigned __int8)IsSamIDecodeClaimsBlobPresent(v9, v4, v6) )
    SamIFreeSidAndAttributesList(&v30);
  if ( v7 && v8 < 0 )
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 12;
      goto LABEL_27;
    }
  }
  else
  {
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LsaHandleCache *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v11 = 13;
LABEL_27:
      WPP_SF_sd(
        *((_QWORD *)v10 + 2),
        v11,
        (unsigned int)WPP_beece53709d13be865c3a44b1735e315_Traceguids,
        (unsigned int)"LsapFindConnectedUserByInternetSid",
        v8);
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180060888  mov     [rsp-28h+arg_0], rbx
0x18006088d  push    rbp
0x18006088e  push    rsi
0x18006088f  push    rdi
0x180060890  push    r13
0x180060892  push    r14
0x180060894  mov     rbp, rsp
0x180060897  sub     rsp, 70h
0x18006089b  xorps   xmm0, xmm0
0x18006089e  mov     [rbp+arg_10], 0
0x1800608a6  mov     rsi, rcx
0x1800608a9  mov     [rbp+arg_8], 0
0x1800608b1  lea     rcx, aLsapfindconnec_1; "LsapFindConnectedUserByInternetSid"
0x1800608b8  mov     [rbp+Sid], 0
0x1800608c0  movups  [rbp+var_20], xmm0
0x1800608c4  mov     rdi, rdx
0x1800608c7  movups  [rbp+var_10], xmm0
0x1800608cb  call    CONNECTED_TRACE_ENTER
0x1800608d0  test    rdi, rdi
0x1800608d3  jz      short loc_1800608DC
0x1800608d5  mov     qword ptr [rdi], 0
0x1800608dc  call    ?LsapCheckConnectedUserEnabled@@YAHXZ; LsapCheckConnectedUserEnabled(void)
0x1800608e1  lea     r13, WPP_GLOBAL_Control
0x1800608e8  test    eax, eax
0x1800608ea  jz      loc_1800609DF
0x1800608f0  mov     rcx, rsi; Sid
0x1800608f3  call    ?LsapIsUserSidIssuedByMsaIdProv@@YAHPEAX@Z; LsapIsUserSidIssuedByMsaIdProv(void *)
0x1800608f8  test    eax, eax
0x1800608fa  jnz     loc_1800609EC
0x180060900  xor     r14d, r14d
0x180060903  mov     ebx, 0C0000078h
0x180060908  mov     rcx, cs:WPP_GLOBAL_Control
0x18006090f  cmp     rcx, r13
0x180060912  jz      short loc_18006091E
0x180060914  test    byte ptr [rcx+1Ch], 2
0x180060918  jnz     loc_180060C17
0x18006091e  test    rdi, rdi
0x180060921  jz      short loc_180060936
0x180060923  mov     rcx, [rdi]; struct _RTL_BALANCED_NODE *
0x180060926  test    rcx, rcx
0x180060929  jnz     loc_180060C79
0x18006092f  mov     qword ptr [rdi], 0
0x180060936  cmp     [rbp+arg_10], 0
0x18006093b  jnz     loc_180060BA9
0x180060941  mov     rcx, [rbp+arg_8]; struct _USER_INTERNAL6_INFORMATION *
0x180060945  test    rcx, rcx
0x180060948  jnz     loc_180060B9F
0x18006094e  mov     rcx, [rbp+Sid]; void *
0x180060952  test    rcx, rcx
0x180060955  jnz     loc_180060C0D
0x18006095b  call    IsSamIDecodeClaimsBlobPresent
0x180060960  test    al, al
0x180060962  jz      short loc_180060974
0x180060964  lea     rcx, [rbp+var_10]
0x180060968  call    cs:__imp_SamIFreeSidAndAttributesList
0x18006096f  nop     dword ptr [rax+rax+00h]
0x180060974  test    r14d, r14d
0x180060977  jnz     short loc_180060992
0x180060979  mov     rcx, cs:WPP_GLOBAL_Control
0x180060980  cmp     rcx, r13
0x180060983  jz      short loc_1800609C8
0x180060985  test    byte ptr [rcx+1Ch], 4
0x180060989  jz      short loc_1800609C8
0x18006098b  mov     edx, 0Dh
0x180060990  jmp     short loc_1800609AD
0x180060992  test    ebx, ebx
0x180060994  jns     short loc_180060979
0x180060996  mov     rcx, cs:WPP_GLOBAL_Control
0x18006099d  cmp     rcx, r13
0x1800609a0  jz      short loc_1800609C8
0x1800609a2  test    byte ptr [rcx+1Ch], 1
0x1800609a6  jz      short loc_1800609C8
0x1800609a8  mov     edx, 0Ch
0x1800609ad  mov     rcx, [rcx+10h]
0x1800609b1  lea     r9, aLsapfindconnec_1; "LsapFindConnectedUserByInternetSid"
0x1800609b8  lea     r8, WPP_beece53709d13be865c3a44b1735e315_Traceguids
0x1800609bf  mov     [rsp+70h+var_50], ebx
0x1800609c3  call    WPP_SF_sd
0x1800609c8  mov     eax, ebx
0x1800609ca  mov     rbx, [rsp+70h+arg_0]
0x1800609d2  add     rsp, 70h
0x1800609d6  pop     r14
0x1800609d8  pop     r13
0x1800609da  pop     rdi
0x1800609db  pop     rsi
0x1800609dc  pop     rbp
0x1800609dd  retn
0x1800609df  xor     r14d, r14d
0x1800609e2  mov     ebx, 0C00000BBh
0x1800609e7  jmp     loc_18006091E
0x1800609ec  mov     r14d, 1
0x1800609f2  call    ?LsapLazyInitSamConnection@@YAJXZ; LsapLazyInitSamConnection(void)
0x1800609f7  mov     ebx, eax
0x1800609f9  test    eax, eax
0x1800609fb  js      loc_180060C40
0x180060a01  mov     rcx, rsi; Sid
0x180060a04  call    cs:__imp_RtlLengthSid
0x180060a0b  nop     dword ptr [rax+rax+00h]
0x180060a10  mov     rbx, cs:?g_hIdProvExtSamAccountDomain@@3PEAXEA; void * g_hIdProvExtSamAccountDomain
0x180060a17  mov     word ptr [rbp+var_20], ax
0x180060a1b  mov     word ptr [rbp+var_20+2], ax
0x180060a1f  mov     qword ptr [rbp+var_20+8], rsi
0x180060a23  call    IsSamIDecodeClaimsBlobPresent
0x180060a28  test    al, al
0x180060a2a  jz      loc_180060C5C
0x180060a30  lea     rax, [rbp+arg_10]
0x180060a34  mov     esi, 100004h
0x180060a39  mov     [rsp+70h+var_30], rax
0x180060a3e  lea     r8, [rbp+var_20]
0x180060a42  lea     rax, [rbp+var_10]
0x180060a46  mov     r9d, esi
0x180060a49  mov     [rsp+70h+var_38], rax
0x180060a4e  mov     edx, 8000h
0x180060a53  lea     rax, [rbp+arg_8]
0x180060a57  mov     rcx, rbx
0x180060a5a  mov     [rsp+70h+var_40], rax
0x180060a5f  mov     [rsp+70h+var_48], 0
0x180060a68  mov     [rsp+70h+var_50], 140000h
0x180060a70  call    cs:__imp_SamIGetUserLogonInformation2
0x180060a77  nop     dword ptr [rax+rax+00h]
0x180060a7c  mov     ebx, eax
0x180060a7e  test    eax, eax
0x180060a80  js      loc_180060C61
0x180060a86  mov     rcx, [rbp+arg_8]
0x180060a8a  mov     eax, [rcx+148h]
0x180060a90  and     eax, 140000h
0x180060a95  cmp     eax, 140000h
0x180060a9a  jnz     short loc_180060ACB
0x180060a9c  mov     eax, [rcx+11Ch]
0x180060aa2  and     eax, esi
0x180060aa4  cmp     eax, esi
0x180060aa6  jnz     short loc_180060ACB
0x180060aa8  mov     rax, [rcx+1C0h]
0x180060aaf  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180060ab6  jnz     short loc_180060AC6
0x180060ab8  mov     rax, [rcx+1C8h]
0x180060abf  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180060ac6  test    rax, rax
0x180060ac9  jnz     short loc_180060B0A
0x180060acb  mov     ebx, 0C0000064h
0x180060ad0  mov     rcx, cs:WPP_GLOBAL_Control
0x180060ad7  cmp     rcx, r13
0x180060ada  jz      loc_18006091E
0x180060ae0  test    [rcx+1Ch], r14b
0x180060ae4  jz      loc_18006091E
0x180060aea  mov     edx, 0Eh
0x180060aef  mov     r9d, 0C0000064h
0x180060af5  mov     rcx, [rcx+10h]
0x180060af9  lea     r8, WPP_da3d202165313132ccfab67d2692d0fe_Traceguids
0x180060b00  call    WPP_SF_d
0x180060b05  jmp     loc_18006091E
0x180060b0a  mov     rax, [rbp+arg_8]
0x180060b0e  test    [rax+118h], r14b
0x180060b15  jnz     loc_180060BCB
0x180060b1b  mov     ebx, [rax+110h]
0x180060b21  mov     rsi, [rbp+arg_10]
0x180060b25  call    IsSamIDecodeClaimsBlobPresent
0x180060b2a  test    al, al
0x180060b2c  jz      loc_180060C55
0x180060b32  lea     r8, [rbp+Sid]
0x180060b36  mov     edx, ebx
0x180060b38  mov     rcx, rsi
0x180060b3b  call    cs:__imp_SamrRidToSid
0x180060b42  nop     dword ptr [rax+rax+00h]
0x180060b47  mov     ebx, eax
0x180060b49  test    eax, eax
0x180060b4b  js      loc_180060BFA
0x180060b51  test    rdi, rdi
0x180060b54  jz      short loc_180060B92
0x180060b56  mov     rcx, [rbp+Sid]; Sid
0x180060b5a  call    cs:__imp_RtlLengthSid
0x180060b61  nop     dword ptr [rax+rax+00h]
0x180060b66  mov     ecx, eax
0x180060b68  mov     ebx, eax
0x180060b6a  call    LsapAllocateNoZero
0x180060b6f  mov     [rdi], rax
0x180060b72  test    rax, rax
0x180060b75  jz      loc_180060C4B
0x180060b7b  mov     r8, [rbp+Sid]; SourceSid
0x180060b7f  mov     rdx, rax; DestinationSid
0x180060b82  mov     ecx, ebx; DestinationSidLength
0x180060b84  call    cs:__imp_RtlCopySid
0x180060b8b  nop     dword ptr [rax+rax+00h]
0x180060b90  mov     ebx, eax
0x180060b92  test    ebx, ebx
0x180060b94  jns     loc_180060936
0x180060b9a  jmp     loc_18006091E
0x180060b9f  call    ?LsapSamExtFreeUserInternal6Information@@YAXPEAU_USER_INTERNAL6_INFORMATION@@@Z; LsapSamExtFreeUserInternal6Information(_USER_INTERNAL6_INFORMATION *)
0x180060ba4  jmp     loc_18006094E
0x180060ba9  call    IsSamIDecodeClaimsBlobPresent
0x180060bae  test    al, al
0x180060bb0  jz      loc_180060941
0x180060bb6  lea     rcx, [rbp+arg_10]
0x180060bba  call    cs:__imp_SamrCloseHandle
0x180060bc1  nop     dword ptr [rax+rax+00h]
0x180060bc6  jmp     loc_180060941
0x180060bcb  mov     ebx, 0C0000072h
0x180060bd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180060bd7  cmp     rcx, r13
0x180060bda  jz      loc_18006091E
0x180060be0  test    [rcx+1Ch], r14b
0x180060be4  jz      loc_18006091E
0x180060bea  mov     edx, 0Fh
0x180060bef  mov     r9d, 0C0000072h
0x180060bf5  jmp     loc_180060AF5
0x180060bfa  mov     edx, ebx
0x180060bfc  lea     rcx, aLsapsamextridt; "LsapSamExtRidToSid"
0x180060c03  call    CONNECTED_TRACE_ERROR
0x180060c08  jmp     loc_18006091E
0x180060c0d  call    ?LsapSamExtFreeVoid@@YAXPEAX@Z; LsapSamExtFreeVoid(void *)
0x180060c12  jmp     loc_18006095B
0x180060c17  mov     rcx, [rcx+10h]
0x180060c1b  lea     r9, aLsapisusersidi; "LsapIsUserSidIssuedByMsaIdProv"
0x180060c22  mov     edx, 0Fh
0x180060c27  mov     [rsp+70h+var_50], 0C0000078h
0x180060c2f  lea     r8, WPP_beece53709d13be865c3a44b1735e315_Traceguids
0x180060c36  call    WPP_SF_sd
0x180060c3b  jmp     loc_18006091E
0x180060c40  mov     edx, eax
0x180060c42  lea     rcx, aLsaplazyinitsa_0; "LsapLazyInitSamConnection"
0x180060c49  jmp     short loc_180060C03
0x180060c4b  mov     ebx, 0C0000017h
0x180060c50  jmp     loc_180060923
0x180060c55  mov     ebx, 0C00000BBh
0x180060c5a  jmp     short loc_180060BFA
0x180060c5c  mov     ebx, 0C00000BBh
0x180060c61  mov     edx, ebx
0x180060c63  lea     rcx, aSamigetuserlog_1; "SamIGetUserLogonInformation2"
0x180060c6a  call    CONNECTED_TRACE_ERROR
0x180060c6f  mov     ebx, 0C0000064h
0x180060c74  jmp     loc_18006091E
0x180060c79  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x180060c7e  jmp     loc_18006092F
```
