# WriteInterfaceExtraInfo

- ea: `0x180043498`
- end: `0x180043a97`
- name: `WriteInterfaceExtraInfo`
- size: `1535`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800236e0`
- `0x180025180`
- `0x180046014`

## callees

- `0x1800302d0`
- `0x180043498`
- `0x180043aa0`
- `0x180050b2c`
- `0x180050cd4`
- `0x180050dbc`
- `0x18005112a`
- `0x180051160`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800435c8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004365d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800436aa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004370e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180043803`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800438f4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800435c8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004365d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800436aa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004370e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180043803`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800438f4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180043737`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800439a5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180043737`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800439a5`
- `ntdll!RtlIpv4AddressToStringW` at `0x180043869`
- `ntdll!RtlIpv4AddressToStringW` at `0x180043869`
- `ntdll!RtlIpv6AddressToStringW` at `0x180043856`
- `ntdll!RtlIpv6AddressToStringW` at `0x180043856`

## string_xrefs

- `0x18004364e`: `VsidOrVlanTag`
- `0x18004367a`: `VsidOrVlanTag`
- `0x1800437f1`: `InitiateConfigPayload`
- `0x18004381e`: `InitiateConfigPayload`
- `0x18004355f`: `WriteInterfaceExtraInfo`
- `0x1800435fa`: `WriteInterfaceExtraInfo`
- `0x1800437b6`: `WriteInterfaceExtraInfo`
- `0x18004388a`: `WriteInterfaceExtraInfo`
- `0x18004391f`: `WriteInterfaceExtraInfo`
- `0x1800439e6`: `WriteInterfaceExtraInfo`
- `0x1800435ec`: `%s: Couldn't write value %s: %d`
- `0x180043767`: `%s: Couldn't delete the value %s: %d`
- `0x1800439f2`: `%s: Couldn't delete the value %s: %d`
- `0x1800437c2`: `%s: WriteQoSPoliciesToRegsitry failed with error %d`
- `0x18004392a`: `%s: Failed to write registry value %s failed: %d`

## pseudocode

```c
__int64 __fastcall WriteInterfaceExtraInfo(HKEY hKey, int a2, int a3, const struct in_addr *a4)
{
  unsigned int v7; // ebx
  void (*v9)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  LSTATUS v10; // eax
  const WCHAR *v11; // r9
  const wchar_t *v12; // rdx
  GUID *v13; // r9
  unsigned int v14; // eax
  LSTATUS v15; // eax
  const WCHAR *v16; // r9
  USHORT s_w1; // cx
  __int64 v18; // rax
  const struct _GUID *v19; // r9
  LSTATUS v20; // eax
  BYTE *lpData; // [rsp+20h] [rbp-E0h]
  BYTE *lpDataa; // [rsp+20h] [rbp-E0h]
  unsigned int v24; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v26; // [rsp+50h] [rbp-B0h]
  __int128 v27; // [rsp+60h] [rbp-A0h]
  __int64 v28; // [rsp+70h] [rbp-90h]
  int v29; // [rsp+78h] [rbp-88h]
  int v30; // [rsp+7Ch] [rbp-84h]
  GUID v31; // [rsp+80h] [rbp-80h] BYREF
  int v32; // [rsp+90h] [rbp-70h] BYREF
  __int128 v33; // [rsp+94h] [rbp-6Ch]
  __int128 v34; // [rsp+A4h] [rbp-5Ch]
  int v35; // [rsp+B4h] [rbp-4Ch]
  WCHAR S[56]; // [rsp+C0h] [rbp-40h] BYREF
  BYTE Data[80]; // [rsp+130h] [rbp+30h] BYREF
  int v38; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v39[2044]; // [rsp+184h] [rbp+84h] BYREF

  v7 = 0;
  v24 = 0;
  memset_0(Data, 0, sizeof(Data));
  memset_0(S, 0, 0x64u);
  v38 = 0;
  memset_0(v39, 0, sizeof(v39));
  v32 = 0;
  v25 = 0;
  v33 = 0;
  v35 = 0;
  v34 = 0;
  v28 = 0;
  v26 = 0;
  v29 = -1;
  v27 = 0;
  v30 = 0;
  if ( *((_QWORD *)&xmmword_180078C50 + 1) )
  {
    EtwFuncEntryExitTracer::Initialize((EtwFuncEntryExitTracer *)&v25, L"WriteInterfaceExtraInfo", &v24, v9);
    v7 = v24;
  }
  if ( a4 && hKey )
  {
    if ( a3 )
    {
      MprConvertGuidToString(&a4[7], 40, Data);
      v10 = RegSetValueExW(hKey, L"RoutingDomainId", 0, 1u, Data, 0x50u);
      v24 = v10;
      v7 = v10;
      if ( v10 )
      {
        if ( (_QWORD)xmmword_180078C60 )
        {
          v11 = L"RoutingDomainId";
LABEL_9:
          v12 = L"%s: Couldn't write value %s: %d";
          goto LABEL_10;
        }
        goto LABEL_64;
      }
      if ( a2 == 3 )
      {
        v10 = RegSetValueExW(hKey, L"VsidOrVlanTag", 0, 4u, &a4[11].S_un.S_un_b.s_b1, 4u);
        v24 = v10;
        v7 = v10;
        if ( !v10 )
        {
          v10 = RegSetValueExW(hKey, L"MultiTenantIfLuid", 0, 3u, &a4[12].S_un.S_un_b.s_b1, 8u);
          v24 = v10;
          v7 = v10;
          if ( !v10 || !(_QWORD)xmmword_180078C60 )
            goto LABEL_64;
          v11 = L"MultiTenantIfLuid";
          goto LABEL_9;
        }
        if ( (_QWORD)xmmword_180078C60 )
        {
          v11 = L"VsidOrVlanTag";
          goto LABEL_9;
        }
LABEL_64:
        EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v25);
        return v7;
      }
      if ( a2 != 2 )
        goto LABEL_64;
      if ( a4[14].S_un.S_un_w.s_w1 )
      {
        v10 = RegSetValueExW(hKey, L"RadiusAttributeClass", 0, 1u, &a4[14].S_un.S_un_b.s_b1, 0x202u);
        v24 = v10;
        v7 = v10;
        if ( v10 )
        {
          if ( (_QWORD)xmmword_180078C60 )
          {
            v11 = L"RadiusAttributeClass";
            goto LABEL_9;
          }
          goto LABEL_64;
        }
      }
      else
      {
        v10 = RegDeleteValueW(hKey, L"RadiusAttributeClass");
        v24 = v10;
        v7 = v10;
        if ( v10 == 2 )
        {
          v24 = 0;
        }
        else if ( v10 )
        {
          if ( (_QWORD)xmmword_180078C60 )
          {
            v11 = L"RadiusAttributeClass";
            v12 = L"%s: Couldn't delete the value %s: %d";
LABEL_10:
            LOWORD(v38) = 0;
            LOWORD(v32) = 0;
            v31 = GUID_NULL;
            LODWORD(lpData) = v10;
            FormatRRASErrorString(&v38, v12, L"WriteInterfaceExtraInfo", v11, lpData);
            v13 = &v31;
            if ( a4 != (const struct in_addr *)-28LL )
              v13 = (GUID *)&a4[7];
LABEL_63:
            ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *, GUID *, _QWORD, int *))gCfgStoreParamTemplateFunc)(
              gCfgStoreEtwContext,
              xmmword_180078C60,
              &v38,
              v13,
              0,
              &v32);
            v7 = v24;
            goto LABEL_64;
          }
          goto LABEL_64;
        }
      }
    }
    else if ( a2 != 2 )
    {
      goto LABEL_64;
    }
    v14 = WriteQoSPoliciesToRegsitry(hKey);
    v24 = v14;
    v7 = v14;
    if ( v14 )
    {
      if ( !(_QWORD)xmmword_180078C60 )
        goto LABEL_64;
      LOWORD(v38) = 0;
      LOWORD(v32) = 0;
      v31 = GUID_NULL;
      FormatRRASErrorString(
        &v38,
        L"%s: WriteQoSPoliciesToRegsitry failed with error %d",
        L"WriteInterfaceExtraInfo",
        v14);
LABEL_61:
      v13 = &v31;
      if ( a4 != (const struct in_addr *)-28LL )
        v13 = (GUID *)&a4[7];
      goto LABEL_63;
    }
    v15 = RegSetValueExW(hKey, L"InitiateConfigPayload", 0, 4u, &a4[143].S_un.S_un_b.s_b1, 4u);
    v24 = v15;
    if ( v15 )
    {
      if ( (_QWORD)xmmword_180078C60 )
      {
        v16 = L"InitiateConfigPayload";
LABEL_50:
        LODWORD(lpDataa) = v15;
        LOWORD(v38) = 0;
        LOWORD(v32) = 0;
        v31 = GUID_NULL;
        FormatRRASErrorString(
          &v38,
          L"%s: Failed to write registry value %s failed: %d",
          L"WriteInterfaceExtraInfo",
          v16,
          lpDataa);
        goto LABEL_51;
      }
LABEL_54:
      v7 = 87;
      goto LABEL_55;
    }
    s_w1 = a4[144].S_un.S_un_w.s_w1;
    if ( !s_w1 )
    {
      v20 = RegDeleteValueW(hKey, L"SourceIpAddress");
      v24 = v20;
      v7 = v20;
      if ( v20 != 2 )
      {
        if ( !v20 || !(_QWORD)xmmword_180078C60 )
          goto LABEL_64;
        LOWORD(v38) = 0;
        LOWORD(v32) = 0;
        LODWORD(lpDataa) = v20;
        v31 = GUID_NULL;
        FormatRRASErrorString(
          &v38,
          L"%s: Couldn't delete the value %s: %d",
          L"WriteInterfaceExtraInfo",
          L"SourceIpAddress",
          lpDataa);
        goto LABEL_61;
      }
      v7 = 0;
LABEL_55:
      v24 = v7;
      goto LABEL_64;
    }
    S[0] = 0;
    if ( s_w1 == 2 )
    {
      RtlIpv4AddressToStringW(a4 + 145, S);
    }
    else
    {
      if ( s_w1 != 23 )
      {
LABEL_43:
        if ( (_QWORD)xmmword_180078C60 )
        {
          LOWORD(v38) = 0;
          LOWORD(v32) = 0;
          v31 = GUID_NULL;
          FormatRRASErrorString(&v38, L"%s: Failed to Convert the address to string format", L"WriteInterfaceExtraInfo");
LABEL_51:
          v19 = &v31;
          if ( a4 != (const struct in_addr *)-28LL )
            v19 = (const struct _GUID *)&a4[7];
          gCfgStoreParamTemplateFunc(
            gCfgStoreEtwContext,
            (const struct _EVENT_DESCRIPTOR *)xmmword_180078C60,
            (const unsigned __int16 *)&v38,
            v19,
            0,
            (const unsigned __int16 *)&v32);
          goto LABEL_54;
        }
        goto LABEL_54;
      }
      RtlIpv6AddressToStringW((const struct in6_addr *)&a4[145], S);
    }
    if ( S[0] )
    {
      v18 = -1;
      do
        ++v18;
      while ( S[v18] );
      v15 = RegSetValueExW(hKey, L"SourceIpAddress", 0, 1u, (const BYTE *)S, 2 * v18 + 2);
      v24 = v15;
      v7 = v15;
      if ( !v15 )
        goto LABEL_64;
      if ( !(_QWORD)xmmword_180078C60 )
        goto LABEL_54;
      v16 = L"SourceIpAddress";
      goto LABEL_50;
    }
    goto LABEL_43;
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v25);
  return 87;
}

```

## disassembly

```asm
0x180043498  mov     [rsp-8+arg_8], rbx
0x18004349d  push    rbp
0x18004349e  push    rsi
0x18004349f  push    rdi
0x1800434a0  push    r12
0x1800434a2  push    r13
0x1800434a4  push    r14
0x1800434a6  push    r15
0x1800434a8  lea     rbp, [rsp-890h]
0x1800434b0  sub     rsp, 990h
0x1800434b7  mov     rax, cs:__security_cookie
0x1800434be  xor     rax, rsp
0x1800434c1  mov     [rbp+8C0h+var_40], rax
0x1800434c8  xor     r13d, r13d
0x1800434cb  mov     r14d, r8d
0x1800434ce  mov     r12d, edx
0x1800434d1  mov     rsi, rcx
0x1800434d4  mov     ebx, r13d
0x1800434d7  lea     rcx, [rbp+8C0h+Data]; void *
0x1800434db  xor     edx, edx; Val
0x1800434dd  mov     [rsp+9C0h+var_980], ebx
0x1800434e1  lea     r8d, [r13+50h]; Size
0x1800434e5  mov     rdi, r9
0x1800434e8  call    memset_0
0x1800434ed  xor     edx, edx; Val
0x1800434ef  lea     r8d, [r13+64h]; Size
0x1800434f3  lea     rcx, [rbp+8C0h+S]; void *
0x1800434f7  call    memset_0
0x1800434fc  xor     edx, edx; Val
0x1800434fe  mov     [rbp+8C0h+var_840], r13d
0x180043505  mov     r8d, 7FCh; Size
0x18004350b  lea     rcx, [rbp+8C0h+var_83C]; void *
0x180043512  call    memset_0
0x180043517  xorps   xmm0, xmm0
0x18004351a  mov     [rbp+8C0h+var_930], r13d
0x18004351e  xor     eax, eax
0x180043520  mov     [rsp+9C0h+var_978], r13
0x180043525  cmp     qword ptr cs:xmmword_180078C50+8, r13
0x18004352c  xorps   xmm1, xmm1
0x18004352f  movups  [rbp+8C0h+var_92C], xmm0
0x180043533  mov     [rbp+8C0h+var_90C], eax
0x180043536  movups  [rbp+8C0h+var_91C], xmm0
0x18004353a  mov     [rsp+9C0h+var_950], r13
0x18004353f  movdqu  [rsp+9C0h+var_970], xmm0
0x180043545  mov     [rsp+9C0h+var_948], 0FFFFFFFFh
0x18004354d  movdqu  [rsp+9C0h+var_960], xmm1
0x180043553  mov     [rsp+9C0h+var_944], r13d
0x180043558  jz      short loc_180043574
0x18004355a  lea     r8, [rsp+9C0h+var_980]; unsigned int *
0x18004355f  lea     rdx, aWriteinterface; "WriteInterfaceExtraInfo"
0x180043566  lea     rcx, [rsp+9C0h+var_978]; this
0x18004356b  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180043570  mov     ebx, [rsp+9C0h+var_980]
0x180043574  test    rdi, rdi
0x180043577  jz      loc_180043A5E
0x18004357d  test    rsi, rsi
0x180043580  jz      loc_180043A5E
0x180043586  test    r14d, r14d
0x180043589  jz      loc_180043773
0x18004358f  lea     r15, [rdi+1Ch]
0x180043593  mov     edx, 28h ; '('
0x180043598  mov     rcx, r15
0x18004359b  lea     r8, [rbp+8C0h+Data]
0x18004359f  call    MprConvertGuidToString
0x1800435a4  lea     rax, [rbp+8C0h+Data]
0x1800435a8  mov     [rsp+9C0h+cbData], 50h ; 'P'; cbData
0x1800435b0  mov     r9d, 1; dwType
0x1800435b6  mov     [rsp+9C0h+lpData], rax; lpData
0x1800435bb  xor     r8d, r8d; Reserved
0x1800435be  lea     rdx, aRoutingdomaini; "RoutingDomainId"
0x1800435c5  mov     rcx, rsi; hKey
0x1800435c8  call    cs:__imp_RegSetValueExW
0x1800435ce  mov     [rsp+9C0h+var_980], eax
0x1800435d2  mov     ebx, eax
0x1800435d4  test    eax, eax
0x1800435d6  jz      short loc_180043633
0x1800435d8  cmp     qword ptr cs:xmmword_180078C60, r13
0x1800435df  jz      loc_180043A50
0x1800435e5  lea     r9, aRoutingdomaini; "RoutingDomainId"
0x1800435ec  lea     rdx, aSCouldnTWriteV_0; "%s: Couldn't write value %s: %d"
0x1800435f3  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800435fa  lea     r8, aWriteinterface; "WriteInterfaceExtraInfo"
0x180043601  mov     word ptr [rbp+8C0h+var_840], r13w
0x180043609  lea     rcx, [rbp+8C0h+var_840]
0x180043610  mov     word ptr [rbp+8C0h+var_930], r13w
0x180043615  movdqu  [rbp+8C0h+var_940], xmm0
0x18004361a  mov     dword ptr [rsp+9C0h+lpData], eax
0x18004361e  call    FormatRRASErrorString
0x180043623  test    r15, r15
0x180043626  lea     r9, [rbp+8C0h+var_940]
0x18004362a  cmovnz  r9, r15
0x18004362e  jmp     loc_180043A1D
0x180043633  cmp     r12d, 3
0x180043637  jnz     loc_1800436D7
0x18004363d  lea     r9d, [r12+1]; dwType
0x180043642  xor     r8d, r8d; Reserved
0x180043645  lea     rax, [rdi+2Ch]
0x180043649  mov     [rsp+9C0h+cbData], r9d; cbData
0x18004364e  lea     rdx, aVsidorvlantag; "VsidOrVlanTag"
0x180043655  mov     [rsp+9C0h+lpData], rax; lpData
0x18004365a  mov     rcx, rsi; hKey
0x18004365d  call    cs:__imp_RegSetValueExW
0x180043663  mov     [rsp+9C0h+var_980], eax
0x180043667  mov     ebx, eax
0x180043669  test    eax, eax
0x18004366b  jz      short loc_180043686
0x18004366d  cmp     qword ptr cs:xmmword_180078C60, r13
0x180043674  jz      loc_180043A50
0x18004367a  lea     r9, aVsidorvlantag; "VsidOrVlanTag"
0x180043681  jmp     loc_1800435EC
0x180043686  lea     rax, [rdi+30h]
0x18004368a  mov     [rsp+9C0h+cbData], 8; cbData
0x180043692  mov     r9d, 3; dwType
0x180043698  mov     [rsp+9C0h+lpData], rax; lpData
0x18004369d  xor     r8d, r8d; Reserved
0x1800436a0  lea     rdx, aMultitenantifl; "MultiTenantIfLuid"
0x1800436a7  mov     rcx, rsi; hKey
0x1800436aa  call    cs:__imp_RegSetValueExW
0x1800436b0  mov     [rsp+9C0h+var_980], eax
0x1800436b4  mov     ebx, eax
0x1800436b6  test    eax, eax
0x1800436b8  jz      loc_180043A50
0x1800436be  cmp     qword ptr cs:xmmword_180078C60, r13
0x1800436c5  jz      loc_180043A50
0x1800436cb  lea     r9, aMultitenantifl; "MultiTenantIfLuid"
0x1800436d2  jmp     loc_1800435EC
0x1800436d7  mov     r14d, 2
0x1800436dd  cmp     r12d, r14d
0x1800436e0  jnz     loc_180043A50
0x1800436e6  lea     rax, [rdi+38h]
0x1800436ea  mov     rcx, rsi; hKey
0x1800436ed  lea     rdx, aRadiusattribut; "RadiusAttributeClass"
0x1800436f4  cmp     [rax], r13w
0x1800436f8  jz      short loc_180043737
0x1800436fa  mov     [rsp+9C0h+cbData], 202h; cbData
0x180043702  lea     r9d, [r14-1]; dwType
0x180043706  xor     r8d, r8d; Reserved
0x180043709  mov     [rsp+9C0h+lpData], rax; lpData
0x18004370e  call    cs:__imp_RegSetValueExW
0x180043714  mov     [rsp+9C0h+var_980], eax
0x180043718  mov     ebx, eax
0x18004371a  test    eax, eax
0x18004371c  jz      short loc_180043782
0x18004371e  cmp     qword ptr cs:xmmword_180078C60, r13
0x180043725  jz      loc_180043A50
0x18004372b  lea     r9, aRadiusattribut; "RadiusAttributeClass"
0x180043732  jmp     loc_1800435EC
0x180043737  call    cs:__imp_RegDeleteValueW
0x18004373d  mov     [rsp+9C0h+var_980], eax
0x180043741  mov     ebx, eax
0x180043743  cmp     eax, r14d
0x180043746  jnz     short loc_18004374F
0x180043748  mov     [rsp+9C0h+var_980], r13d
0x18004374d  jmp     short loc_180043782
0x18004374f  test    eax, eax
0x180043751  jz      short loc_180043782
0x180043753  cmp     qword ptr cs:xmmword_180078C60, r13
0x18004375a  jz      loc_180043A50
0x180043760  lea     r9, aRadiusattribut; "RadiusAttributeClass"
0x180043767  lea     rdx, aSCouldnTDelete; "%s: Couldn't delete the value %s: %d"
0x18004376e  jmp     loc_1800435F3
0x180043773  mov     r14d, 2
0x180043779  cmp     r12d, r14d
0x18004377c  jnz     loc_180043A50
0x180043782  mov     rdx, rdi
0x180043785  mov     rcx, rsi; hKey
0x180043788  call    WriteQoSPoliciesToRegsitry
0x18004378d  mov     [rsp+9C0h+var_980], eax
0x180043791  mov     ebx, eax
0x180043793  test    eax, eax
0x180043795  jz      short loc_1800437DF
0x180043797  cmp     qword ptr cs:xmmword_180078C60, r13
0x18004379e  jz      loc_180043A50
0x1800437a4  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800437ab  mov     r9d, eax
0x1800437ae  mov     word ptr [rbp+8C0h+var_840], r13w
0x1800437b6  lea     r8, aWriteinterface; "WriteInterfaceExtraInfo"
0x1800437bd  mov     word ptr [rbp+8C0h+var_930], r13w
0x1800437c2  lea     rdx, aSWriteqospolic_0; "%s: WriteQoSPoliciesToRegsitry failed w"...
0x1800437c9  lea     rcx, [rbp+8C0h+var_840]
0x1800437d0  movdqu  [rbp+8C0h+var_940], xmm0
0x1800437d5  call    FormatRRASErrorString
0x1800437da  jmp     loc_180043A0E
0x1800437df  mov     r9d, 4; dwType
0x1800437e5  lea     rax, [rdi+23Ch]
0x1800437ec  mov     [rsp+9C0h+cbData], r9d; cbData
0x1800437f1  lea     rdx, aInitiateconfig; "InitiateConfigPayload"
0x1800437f8  xor     r8d, r8d; Reserved
0x1800437fb  mov     [rsp+9C0h+lpData], rax; lpData
0x180043800  mov     rcx, rsi; hKey
0x180043803  call    cs:__imp_RegSetValueExW
0x180043809  mov     [rsp+9C0h+var_980], eax
0x18004380d  test    eax, eax
0x18004380f  jz      short loc_18004382A
0x180043811  cmp     qword ptr cs:xmmword_180078C60, r13
0x180043818  jz      loc_18004398D
0x18004381e  lea     r9, aInitiateconfig; "InitiateConfigPayload"
0x180043825  jmp     loc_180043918
0x18004382a  movzx   ecx, word ptr [rdi+240h]
0x180043831  test    cx, cx
0x180043834  jz      loc_18004399B
0x18004383a  mov     [rbp+8C0h+S], r13w
0x18004383f  cmp     cx, r14w
0x180043843  jz      short loc_18004385E
0x180043845  cmp     cx, 17h
0x180043849  jnz     short loc_180043876
0x18004384b  lea     rcx, [rdi+244h]; Addr
0x180043852  lea     rdx, [rbp+8C0h+S]; S
0x180043856  call    cs:__imp_RtlIpv6AddressToStringW
0x18004385c  jmp     short loc_18004386F
0x18004385e  lea     rcx, [rdi+244h]; Addr
0x180043865  lea     rdx, [rbp+8C0h+S]; S
0x180043869  call    cs:__imp_RtlIpv4AddressToStringW
0x18004386f  cmp     r13w, [rbp+8C0h+S]
0x180043874  jnz     short loc_1800438BB
0x180043876  cmp     qword ptr cs:xmmword_180078C60, r13
0x18004387d  jz      loc_18004398D
0x180043883  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004388a  lea     r8, aWriteinterface; "WriteInterfaceExtraInfo"
0x180043891  mov     word ptr [rbp+8C0h+var_840], r13w
0x180043899  lea     rdx, aSFailedToConve; "%s: Failed to Convert the address to st"...
0x1800438a0  mov     word ptr [rbp+8C0h+var_930], r13w
0x1800438a5  lea     rcx, [rbp+8C0h+var_840]
0x1800438ac  movdqu  [rbp+8C0h+var_940], xmm0
0x1800438b1  call    FormatRRASErrorString
0x1800438b6  jmp     loc_18004394F
0x1800438bb  lea     rcx, [rbp+8C0h+S]
0x1800438bf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800438c3  inc     rax
0x1800438c6  cmp     [rcx+rax*2], r13w
0x1800438cb  jnz     short loc_1800438C3
0x1800438cd  lea     eax, ds:2[rax*2]
0x1800438d4  mov     r9d, 1; dwType
0x1800438da  mov     [rsp+9C0h+cbData], eax; cbData
0x1800438de  lea     rdx, aSourceipaddres; "SourceIpAddress"
0x1800438e5  lea     rax, [rbp+8C0h+S]
0x1800438e9  xor     r8d, r8d; Reserved
0x1800438ec  mov     rcx, rsi; hKey
0x1800438ef  mov     [rsp+9C0h+lpData], rax; lpData
0x1800438f4  call    cs:__imp_RegSetValueExW
0x1800438fa  mov     [rsp+9C0h+var_980], eax
0x1800438fe  mov     ebx, eax
0x180043900  test    eax, eax
0x180043902  jz      loc_180043A50
0x180043908  cmp     qword ptr cs:xmmword_180078C60, r13
0x18004390f  jz      short loc_18004398D
0x180043911  lea     r9, aSourceipaddres; "SourceIpAddress"
0x180043918  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18004391f  lea     r8, aWriteinterface; "WriteInterfaceExtraInfo"
0x180043926  mov     dword ptr [rsp+9C0h+lpData], eax
0x18004392a  lea     rdx, aSFailedToWrite; "%s: Failed to write registry value %s f"...
0x180043931  mov     word ptr [rbp+8C0h+var_840], r13w
0x180043939  lea     rcx, [rbp+8C0h+var_840]
0x180043940  mov     word ptr [rbp+8C0h+var_930], r13w
0x180043945  movdqu  [rbp+8C0h+var_940], xmm0
0x18004394a  call    FormatRRASErrorString
0x18004394f  mov     rdx, qword ptr cs:xmmword_180078C60
0x180043956  lea     rcx, [rdi+1Ch]
0x18004395a  test    rcx, rcx
0x18004395d  lea     rax, [rbp+8C0h+var_930]
0x180043961  mov     qword ptr [rsp+9C0h+cbData], rax
0x180043966  lea     r9, [rbp+8C0h+var_940]
0x18004396a  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180043971  lea     r8, [rbp+8C0h+var_840]
0x180043978  cmovnz  r9, rcx
0x18004397c  mov     [rsp+9C0h+lpData], r13
0x180043981  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180043988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004398d  mov     ebx, 57h ; 'W'
0x180043992  mov     [rsp+9C0h+var_980], ebx
0x180043996  jmp     loc_180043A50
0x18004399b  lea     rdx, aSourceipaddres; "SourceIpAddress"
0x1800439a2  mov     rcx, rsi; hKey
0x1800439a5  call    cs:__imp_RegDeleteValueW
0x1800439ab  mov     [rsp+9C0h+var_980], eax
0x1800439af  mov     ebx, eax
0x1800439b1  cmp     eax, r14d
0x1800439b4  jnz     short loc_1800439BB
0x1800439b6  mov     ebx, r13d
0x1800439b9  jmp     short loc_180043992
0x1800439bb  test    eax, eax
0x1800439bd  jz      loc_180043A50
0x1800439c3  cmp     qword ptr cs:xmmword_180078C60, r13
0x1800439ca  jz      loc_180043A50
0x1800439d0  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800439d7  lea     r9, aSourceipaddres; "SourceIpAddress"
0x1800439de  mov     word ptr [rbp+8C0h+var_840], r13w
0x1800439e6  lea     r8, aWriteinterface; "WriteInterfaceExtraInfo"
0x1800439ed  mov     word ptr [rbp+8C0h+var_930], r13w
0x1800439f2  lea     rdx, aSCouldnTDelete; "%s: Couldn't delete the value %s: %d"
0x1800439f9  mov     dword ptr [rsp+9C0h+lpData], eax
0x1800439fd  lea     rcx, [rbp+8C0h+var_840]
0x180043a04  movdqu  [rbp+8C0h+var_940], xmm0
0x180043a09  call    FormatRRASErrorString
0x180043a0e  lea     rcx, [rdi+1Ch]
0x180043a12  test    rcx, rcx
0x180043a15  lea     r9, [rbp+8C0h+var_940]
0x180043a19  cmovnz  r9, rcx
0x180043a1d  mov     rdx, qword ptr cs:xmmword_180078C60
0x180043a24  lea     rax, [rbp+8C0h+var_930]
  ... truncated ...
```
