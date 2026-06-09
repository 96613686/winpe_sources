# WriteInterfaceExtraInfo

- ea: `0x180037e0c`
- end: `0x1800383a4`
- name: `WriteInterfaceExtraInfo`
- size: `1432`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting`

## callers

- `0x180015ad4`
- `0x18003a874`

## callees

- `0x180033e90`
- `0x180037e0c`
- `0x1800383ac`
- `0x18004583c`
- `0x180045ad4`
- `0x180045d40`
- `0x180046e2a`
- `0x180046e70`
- `0x180048010`

## import_xrefs

- `ntdll!RtlIpv4AddressToStringW` at `0x180038182`
- `ntdll!RtlIpv4AddressToStringW` at `0x180038182`
- `ntdll!RtlIpv6AddressToStringW` at `0x18003816f`
- `ntdll!RtlIpv6AddressToStringW` at `0x18003816f`
- `KERNEL32!RegDeleteValueW` at `0x180038068`
- `KERNEL32!RegDeleteValueW` at `0x1800382ba`
- `KERNEL32!RegDeleteValueW` at `0x180038068`
- `KERNEL32!RegDeleteValueW` at `0x1800382ba`
- `ADVAPI32!RegSetValueExW` at `0x180037f2e`
- `ADVAPI32!RegSetValueExW` at `0x180037f8a`
- `ADVAPI32!RegSetValueExW` at `0x180037fd4`
- `ADVAPI32!RegSetValueExW` at `0x180038038`
- `ADVAPI32!RegSetValueExW` at `0x18003811c`
- `ADVAPI32!RegSetValueExW` at `0x18003820d`
- `ADVAPI32!RegSetValueExW` at `0x180037f2e`
- `ADVAPI32!RegSetValueExW` at `0x180037f8a`
- `ADVAPI32!RegSetValueExW` at `0x180037fd4`
- `ADVAPI32!RegSetValueExW` at `0x180038038`
- `ADVAPI32!RegSetValueExW` at `0x18003811c`
- `ADVAPI32!RegSetValueExW` at `0x18003820d`

## string_xrefs

- `0x180037f7b`: `VsidOrVlanTag`
- `0x180037fa7`: `VsidOrVlanTag`
- `0x18003810a`: `InitiateConfigPayload`
- `0x180038137`: `InitiateConfigPayload`
- `0x180037ea0`: `WriteInterfaceExtraInfo`
- `0x1800380b2`: `WriteInterfaceExtraInfo`
- `0x1800381a3`: `WriteInterfaceExtraInfo`
- `0x180038238`: `WriteInterfaceExtraInfo`
- `0x1800382ef`: `WriteInterfaceExtraInfo`
- `0x180037f55`: `%s: Couldn't write value %s: %d`
- `0x18003805c`: `%s: Couldn't write value %s: %d`
- `0x1800382e8`: `%s: Couldn't delete the value %s: %d`
- `0x1800380be`: `%s: WriteQoSPoliciesToRegsitry failed with error %d`
- `0x180038243`: `%s: Failed to write registry value %s failed: %d`

## pseudocode

```c
__int64 __fastcall WriteInterfaceExtraInfo(HKEY hKey, int a2, __int64 a3, const struct in_addr *a4)
{
  void (*v7)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int); // r9
  LSTATUS v8; // eax
  unsigned int v9; // ebx
  const WCHAR *v10; // r9
  const wchar_t *v11; // rdx
  unsigned int v12; // eax
  LSTATUS v13; // eax
  const WCHAR *v14; // r9
  USHORT s_w1; // cx
  __int64 v16; // rax
  const struct _GUID *v17; // r9
  const struct _GUID *v18; // r9
  BYTE *lpData; // [rsp+20h] [rbp-E0h]
  unsigned int v21; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v22; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v23; // [rsp+50h] [rbp-B0h]
  __int128 v24; // [rsp+60h] [rbp-A0h]
  __int64 v25; // [rsp+70h] [rbp-90h]
  int v26; // [rsp+78h] [rbp-88h]
  int v27; // [rsp+7Ch] [rbp-84h]
  GUID v28; // [rsp+80h] [rbp-80h] BYREF
  int v29; // [rsp+90h] [rbp-70h] BYREF
  __int128 v30; // [rsp+94h] [rbp-6Ch]
  __int128 v31; // [rsp+A4h] [rbp-5Ch]
  int v32; // [rsp+B4h] [rbp-4Ch]
  WCHAR S[56]; // [rsp+C0h] [rbp-40h] BYREF
  BYTE Data[80]; // [rsp+130h] [rbp+30h] BYREF
  int v35; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v36[2044]; // [rsp+184h] [rbp+84h] BYREF

  v21 = 0;
  memset_0(Data, 0, sizeof(Data));
  memset_0(S, 0, 0x64u);
  v35 = 0;
  memset_0(v36, 0, sizeof(v36));
  v29 = 0;
  v22 = 0;
  v32 = 0;
  v30 = 0;
  v25 = 0;
  v31 = 0;
  v26 = -1;
  v23 = 0;
  v27 = 0;
  v24 = 0;
  if ( *((_QWORD *)&xmmword_180071090 + 1) )
    EtwFuncEntryExitTracer::Initialize((EtwFuncEntryExitTracer *)&v22, L"WriteInterfaceExtraInfo", &v21, v7);
  if ( a4 && hKey )
  {
    MprConvertGuidToString(&a4[7], 40, Data);
    v8 = RegSetValueExW(hKey, L"RoutingDomainId", 0, 1u, Data, 0x50u);
    v21 = v8;
    v9 = v8;
    if ( v8 )
    {
      if ( (_QWORD)xmmword_1800710A0 )
      {
        v10 = L"RoutingDomainId";
LABEL_8:
        v11 = L"%s: Couldn't write value %s: %d";
LABEL_57:
        LODWORD(lpData) = v8;
        LOWORD(v35) = 0;
        v28 = GUID_NULL;
        LOWORD(v29) = 0;
        FormatRRASErrorString(&v35, v11, L"WriteInterfaceExtraInfo", v10, lpData);
        goto LABEL_58;
      }
      goto LABEL_61;
    }
    if ( a2 == 3 )
    {
      v8 = RegSetValueExW(hKey, L"VsidOrVlanTag", 0, 4u, &a4[11].S_un.S_un_b.s_b1, 4u);
      v21 = v8;
      v9 = v8;
      if ( v8 )
      {
        if ( (_QWORD)xmmword_1800710A0 )
        {
          v10 = L"VsidOrVlanTag";
          goto LABEL_8;
        }
      }
      else
      {
        v8 = RegSetValueExW(hKey, L"MultiTenantIfLuid", 0, 3u, &a4[12].S_un.S_un_b.s_b1, 8u);
        v21 = v8;
        v9 = v8;
        if ( v8 && (_QWORD)xmmword_1800710A0 )
        {
          v10 = L"MultiTenantIfLuid";
          goto LABEL_8;
        }
      }
LABEL_61:
      EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v22);
      return v9;
    }
    if ( a2 != 2 )
      goto LABEL_61;
    if ( a4[14].S_un.S_un_w.s_w1 )
    {
      v8 = RegSetValueExW(hKey, L"RadiusAttributeClass", 0, 1u, &a4[14].S_un.S_un_b.s_b1, 0x202u);
      v21 = v8;
      v9 = v8;
      if ( v8 )
      {
        if ( (_QWORD)xmmword_1800710A0 )
        {
          v10 = L"RadiusAttributeClass";
          v11 = L"%s: Couldn't write value %s: %d";
          goto LABEL_57;
        }
        goto LABEL_61;
      }
    }
    else
    {
      v8 = RegDeleteValueW(hKey, L"RadiusAttributeClass");
      v21 = v8;
      v9 = v8;
      if ( v8 == 2 )
      {
        v21 = 0;
      }
      else if ( v8 )
      {
        if ( !(_QWORD)xmmword_1800710A0 )
          goto LABEL_61;
        v10 = L"RadiusAttributeClass";
        goto LABEL_56;
      }
    }
    v12 = WriteQoSPoliciesToRegsitry(hKey);
    v21 = v12;
    v9 = v12;
    if ( v12 )
    {
      if ( (_QWORD)xmmword_1800710A0 )
      {
        LOWORD(v35) = 0;
        LOWORD(v29) = 0;
        v28 = GUID_NULL;
        FormatRRASErrorString(
          &v35,
          L"%s: WriteQoSPoliciesToRegsitry failed with error %d",
          L"WriteInterfaceExtraInfo",
          v12);
LABEL_58:
        v18 = &v28;
        if ( a4 != (const struct in_addr *)-28LL )
          v18 = (const struct _GUID *)&a4[7];
        gCfgStoreParamTemplateFunc(
          gCfgStoreEtwContext,
          (const struct _EVENT_DESCRIPTOR *)xmmword_1800710A0,
          (const unsigned __int16 *)&v35,
          v18,
          0,
          (const unsigned __int16 *)&v29);
        v9 = v21;
        goto LABEL_61;
      }
      goto LABEL_61;
    }
    v13 = RegSetValueExW(hKey, L"InitiateConfigPayload", 0, 4u, &a4[143].S_un.S_un_b.s_b1, 4u);
    v21 = v13;
    if ( v13 )
    {
      if ( (_QWORD)xmmword_1800710A0 )
      {
        v14 = L"InitiateConfigPayload";
LABEL_45:
        LODWORD(lpData) = v13;
        LOWORD(v35) = 0;
        LOWORD(v29) = 0;
        v28 = GUID_NULL;
        FormatRRASErrorString(
          &v35,
          L"%s: Failed to write registry value %s failed: %d",
          L"WriteInterfaceExtraInfo",
          v14,
          lpData);
        goto LABEL_46;
      }
LABEL_49:
      v9 = 87;
LABEL_50:
      v21 = v9;
      goto LABEL_61;
    }
    s_w1 = a4[144].S_un.S_un_w.s_w1;
    if ( s_w1 )
    {
      S[0] = 0;
      if ( s_w1 == 2 )
      {
        RtlIpv4AddressToStringW(a4 + 145, S);
      }
      else
      {
        if ( s_w1 != 23 )
        {
LABEL_38:
          if ( (_QWORD)xmmword_1800710A0 )
          {
            LOWORD(v35) = 0;
            LOWORD(v29) = 0;
            v28 = GUID_NULL;
            FormatRRASErrorString(
              &v35,
              L"%s: Failed to Convert the address to string format",
              L"WriteInterfaceExtraInfo");
LABEL_46:
            v17 = &v28;
            if ( a4 != (const struct in_addr *)-28LL )
              v17 = (const struct _GUID *)&a4[7];
            gCfgStoreParamTemplateFunc(
              gCfgStoreEtwContext,
              (const struct _EVENT_DESCRIPTOR *)xmmword_1800710A0,
              (const unsigned __int16 *)&v35,
              v17,
              0,
              (const unsigned __int16 *)&v29);
            goto LABEL_49;
          }
          goto LABEL_49;
        }
        RtlIpv6AddressToStringW((const struct in6_addr *)&a4[145], S);
      }
      if ( S[0] )
      {
        v16 = -1;
        do
          ++v16;
        while ( S[v16] );
        v13 = RegSetValueExW(hKey, L"SourceIpAddress", 0, 1u, (const BYTE *)S, 2 * v16 + 2);
        v21 = v13;
        v9 = v13;
        if ( !v13 )
          goto LABEL_61;
        if ( !(_QWORD)xmmword_1800710A0 )
          goto LABEL_49;
        v14 = L"SourceIpAddress";
        goto LABEL_45;
      }
      goto LABEL_38;
    }
    v8 = RegDeleteValueW(hKey, L"SourceIpAddress");
    v21 = v8;
    v9 = v8;
    if ( v8 == 2 )
    {
      v9 = 0;
      goto LABEL_50;
    }
    if ( !v8 || !(_QWORD)xmmword_1800710A0 )
      goto LABEL_61;
    v10 = L"SourceIpAddress";
LABEL_56:
    v11 = L"%s: Couldn't delete the value %s: %d";
    goto LABEL_57;
  }
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v22);
  return 87;
}

```

## disassembly

```asm
0x180037e0c  mov     [rsp-8+arg_8], rbx
0x180037e11  push    rbp
0x180037e12  push    rsi
0x180037e13  push    rdi
0x180037e14  push    r12
0x180037e16  push    r13
0x180037e18  push    r14
0x180037e1a  push    r15
0x180037e1c  lea     rbp, [rsp-890h]
0x180037e24  sub     rsp, 990h
0x180037e2b  mov     rax, cs:__security_cookie
0x180037e32  xor     rax, rsp
0x180037e35  mov     [rbp+8C0h+var_40], rax
0x180037e3c  xor     r12d, r12d
0x180037e3f  mov     r15d, edx
0x180037e42  mov     rsi, rcx
0x180037e45  mov     [rsp+9C0h+var_980], r12d
0x180037e4a  xor     edx, edx; Val
0x180037e4c  lea     rcx, [rbp+8C0h+Data]; void *
0x180037e50  mov     rdi, r9
0x180037e53  lea     ebx, [r12+50h]
0x180037e58  mov     r8d, ebx; Size
0x180037e5b  call    memset_0
0x180037e60  xor     edx, edx; Val
0x180037e62  lea     r8d, [r12+64h]; Size
0x180037e67  lea     rcx, [rbp+8C0h+S]; void *
0x180037e6b  call    memset_0
0x180037e70  xor     edx, edx; Val
0x180037e72  mov     [rbp+8C0h+var_840], r12d
0x180037e79  mov     r8d, 7FCh; Size
0x180037e7f  lea     rcx, [rbp+8C0h+var_83C]; void *
0x180037e86  call    memset_0
0x180037e8b  xorps   xmm0, xmm0
0x180037e8e  mov     [rbp+8C0h+var_930], r12d
0x180037e92  xor     eax, eax
0x180037e94  mov     [rsp+9C0h+var_978], r12
0x180037e99  cmp     qword ptr cs:xmmword_180071090+8, r12
0x180037ea0  lea     r13, aWriteinterface; "WriteInterfaceExtraInfo"
0x180037ea7  xorps   xmm1, xmm1
0x180037eaa  mov     [rbp+8C0h+var_90C], eax
0x180037ead  movups  [rbp+8C0h+var_92C], xmm0
0x180037eb1  mov     [rsp+9C0h+var_950], r12
0x180037eb6  movups  [rbp+8C0h+var_91C], xmm0
0x180037eba  mov     [rsp+9C0h+var_948], 0FFFFFFFFh
0x180037ec2  movdqu  [rsp+9C0h+var_970], xmm0
0x180037ec8  mov     [rsp+9C0h+var_944], r12d
0x180037ecd  movdqu  [rsp+9C0h+var_960], xmm1
0x180037ed3  jz      short loc_180037EE7
0x180037ed5  lea     r8, [rsp+9C0h+var_980]; unsigned int *
0x180037eda  mov     rdx, r13; unsigned __int16 *
0x180037edd  lea     rcx, [rsp+9C0h+var_978]; this
0x180037ee2  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x180037ee7  test    rdi, rdi
0x180037eea  jz      loc_18003836B
0x180037ef0  test    rsi, rsi
0x180037ef3  jz      loc_18003836B
0x180037ef9  lea     r14, [rdi+1Ch]
0x180037efd  mov     edx, 28h ; '('
0x180037f02  mov     rcx, r14
0x180037f05  lea     r8, [rbp+8C0h+Data]
0x180037f09  call    MprConvertGuidToString
0x180037f0e  lea     rax, [rbp+8C0h+Data]
0x180037f12  mov     [rsp+9C0h+cbData], ebx; cbData
0x180037f16  mov     r9d, 1; dwType
0x180037f1c  mov     [rsp+9C0h+lpData], rax; lpData
0x180037f21  xor     r8d, r8d; Reserved
0x180037f24  lea     rdx, aRoutingdomaini; "RoutingDomainId"
0x180037f2b  mov     rcx, rsi; hKey
0x180037f2e  call    cs:__imp_RegSetValueExW
0x180037f34  mov     [rsp+9C0h+var_980], eax
0x180037f38  mov     ebx, eax
0x180037f3a  test    eax, eax
0x180037f3c  jz      short loc_180037F61
0x180037f3e  cmp     qword ptr cs:xmmword_1800710A0, r12
0x180037f45  jz      loc_18003835D
0x180037f4b  lea     r9, aRoutingdomaini; "RoutingDomainId"
0x180037f52  mov     r8, r13
0x180037f55  lea     rdx, aSCouldnTWriteV_0; "%s: Couldn't write value %s: %d"
0x180037f5c  jmp     loc_1800382F6
0x180037f61  cmp     r15d, 3
0x180037f65  jnz     loc_180038001
0x180037f6b  lea     r9d, [r15+1]; dwType
0x180037f6f  xor     r8d, r8d; Reserved
0x180037f72  lea     rax, [rdi+2Ch]
0x180037f76  mov     [rsp+9C0h+cbData], r9d; cbData
0x180037f7b  lea     rdx, aVsidorvlantag; "VsidOrVlanTag"
0x180037f82  mov     [rsp+9C0h+lpData], rax; lpData
0x180037f87  mov     rcx, rsi; hKey
0x180037f8a  call    cs:__imp_RegSetValueExW
0x180037f90  mov     [rsp+9C0h+var_980], eax
0x180037f94  mov     ebx, eax
0x180037f96  test    eax, eax
0x180037f98  jz      short loc_180037FB0
0x180037f9a  cmp     qword ptr cs:xmmword_1800710A0, r12
0x180037fa1  jz      loc_18003835D
0x180037fa7  lea     r9, aVsidorvlantag; "VsidOrVlanTag"
0x180037fae  jmp     short loc_180037F52
0x180037fb0  lea     rax, [rdi+30h]
0x180037fb4  mov     [rsp+9C0h+cbData], 8; cbData
0x180037fbc  mov     r9d, 3; dwType
0x180037fc2  mov     [rsp+9C0h+lpData], rax; lpData
0x180037fc7  xor     r8d, r8d; Reserved
0x180037fca  lea     rdx, aMultitenantifl; "MultiTenantIfLuid"
0x180037fd1  mov     rcx, rsi; hKey
0x180037fd4  call    cs:__imp_RegSetValueExW
0x180037fda  mov     [rsp+9C0h+var_980], eax
0x180037fde  mov     ebx, eax
0x180037fe0  test    eax, eax
0x180037fe2  jz      loc_18003835D
0x180037fe8  cmp     qword ptr cs:xmmword_1800710A0, r12
0x180037fef  jz      loc_18003835D
0x180037ff5  lea     r9, aMultitenantifl; "MultiTenantIfLuid"
0x180037ffc  jmp     loc_180037F52
0x180038001  mov     r13d, 2
0x180038007  cmp     r15d, r13d
0x18003800a  jnz     loc_18003835D
0x180038010  lea     rax, [rdi+38h]
0x180038014  mov     rcx, rsi; hKey
0x180038017  lea     rdx, aRadiusattribut; "RadiusAttributeClass"
0x18003801e  cmp     [rax], r12w
0x180038022  jz      short loc_180038068
0x180038024  mov     [rsp+9C0h+cbData], 202h; cbData
0x18003802c  lea     r9d, [r13-1]; dwType
0x180038030  xor     r8d, r8d; Reserved
0x180038033  mov     [rsp+9C0h+lpData], rax; lpData
0x180038038  call    cs:__imp_RegSetValueExW
0x18003803e  mov     [rsp+9C0h+var_980], eax
0x180038042  mov     ebx, eax
0x180038044  test    eax, eax
0x180038046  jz      short loc_18003807E
0x180038048  cmp     qword ptr cs:xmmword_1800710A0, r12
0x18003804f  jz      loc_18003835D
0x180038055  lea     r9, aRadiusattribut; "RadiusAttributeClass"
0x18003805c  lea     rdx, aSCouldnTWriteV_0; "%s: Couldn't write value %s: %d"
0x180038063  jmp     loc_1800382EF
0x180038068  call    cs:__imp_RegDeleteValueW
0x18003806e  mov     [rsp+9C0h+var_980], eax
0x180038072  mov     ebx, eax
0x180038074  cmp     eax, r13d
0x180038077  jnz     short loc_1800380DB
0x180038079  mov     [rsp+9C0h+var_980], r12d
0x18003807e  mov     rdx, rdi
0x180038081  mov     rcx, rsi; hKey
0x180038084  call    WriteQoSPoliciesToRegsitry
0x180038089  mov     [rsp+9C0h+var_980], eax
0x18003808d  mov     ebx, eax
0x18003808f  test    eax, eax
0x180038091  jz      short loc_1800380F8
0x180038093  cmp     qword ptr cs:xmmword_1800710A0, r12
0x18003809a  jz      loc_18003835D
0x1800380a0  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800380a7  mov     r9d, eax
0x1800380aa  mov     word ptr [rbp+8C0h+var_840], r12w
0x1800380b2  lea     r8, aWriteinterface; "WriteInterfaceExtraInfo"
0x1800380b9  mov     word ptr [rbp+8C0h+var_930], r12w
0x1800380be  lea     rdx, aSWriteqospolic_0; "%s: WriteQoSPoliciesToRegsitry failed w"...
0x1800380c5  lea     rcx, [rbp+8C0h+var_840]
0x1800380cc  movdqu  [rbp+8C0h+var_940], xmm0
0x1800380d1  call    FormatRRASErrorString
0x1800380d6  jmp     loc_18003831F
0x1800380db  test    eax, eax
0x1800380dd  jz      short loc_18003807E
0x1800380df  cmp     qword ptr cs:xmmword_1800710A0, r12
0x1800380e6  jz      loc_18003835D
0x1800380ec  lea     r9, aRadiusattribut; "RadiusAttributeClass"
0x1800380f3  jmp     loc_1800382E8
0x1800380f8  mov     r9d, 4; dwType
0x1800380fe  lea     rax, [rdi+23Ch]
0x180038105  mov     [rsp+9C0h+cbData], r9d; cbData
0x18003810a  lea     rdx, aInitiateconfig; "InitiateConfigPayload"
0x180038111  xor     r8d, r8d; Reserved
0x180038114  mov     [rsp+9C0h+lpData], rax; lpData
0x180038119  mov     rcx, rsi; hKey
0x18003811c  call    cs:__imp_RegSetValueExW
0x180038122  mov     [rsp+9C0h+var_980], eax
0x180038126  test    eax, eax
0x180038128  jz      short loc_180038143
0x18003812a  cmp     qword ptr cs:xmmword_1800710A0, r12
0x180038131  jz      loc_1800382A2
0x180038137  lea     r9, aInitiateconfig; "InitiateConfigPayload"
0x18003813e  jmp     loc_180038231
0x180038143  movzx   ecx, word ptr [rdi+240h]
0x18003814a  test    cx, cx
0x18003814d  jz      loc_1800382B0
0x180038153  mov     [rbp+8C0h+S], r12w
0x180038158  cmp     cx, r13w
0x18003815c  jz      short loc_180038177
0x18003815e  cmp     cx, 17h
0x180038162  jnz     short loc_18003818F
0x180038164  lea     rcx, [rdi+244h]; Addr
0x18003816b  lea     rdx, [rbp+8C0h+S]; S
0x18003816f  call    cs:__imp_RtlIpv6AddressToStringW
0x180038175  jmp     short loc_180038188
0x180038177  lea     rcx, [rdi+244h]; Addr
0x18003817e  lea     rdx, [rbp+8C0h+S]; S
0x180038182  call    cs:__imp_RtlIpv4AddressToStringW
0x180038188  cmp     r12w, [rbp+8C0h+S]
0x18003818d  jnz     short loc_1800381D4
0x18003818f  cmp     qword ptr cs:xmmword_1800710A0, r12
0x180038196  jz      loc_1800382A2
0x18003819c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800381a3  lea     r8, aWriteinterface; "WriteInterfaceExtraInfo"
0x1800381aa  mov     word ptr [rbp+8C0h+var_840], r12w
0x1800381b2  lea     rdx, aSFailedToConve; "%s: Failed to Convert the address to st"...
0x1800381b9  mov     word ptr [rbp+8C0h+var_930], r12w
0x1800381be  lea     rcx, [rbp+8C0h+var_840]
0x1800381c5  movdqu  [rbp+8C0h+var_940], xmm0
0x1800381ca  call    FormatRRASErrorString
0x1800381cf  jmp     loc_180038268
0x1800381d4  lea     rcx, [rbp+8C0h+S]
0x1800381d8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800381dc  inc     rax
0x1800381df  cmp     [rcx+rax*2], r12w
0x1800381e4  jnz     short loc_1800381DC
0x1800381e6  lea     eax, ds:2[rax*2]
0x1800381ed  mov     r9d, 1; dwType
0x1800381f3  mov     [rsp+9C0h+cbData], eax; cbData
0x1800381f7  lea     rdx, aSourceipaddres; "SourceIpAddress"
0x1800381fe  lea     rax, [rbp+8C0h+S]
0x180038202  xor     r8d, r8d; Reserved
0x180038205  mov     rcx, rsi; hKey
0x180038208  mov     [rsp+9C0h+lpData], rax; lpData
0x18003820d  call    cs:__imp_RegSetValueExW
0x180038213  mov     [rsp+9C0h+var_980], eax
0x180038217  mov     ebx, eax
0x180038219  test    eax, eax
0x18003821b  jz      loc_18003835D
0x180038221  cmp     qword ptr cs:xmmword_1800710A0, r12
0x180038228  jz      short loc_1800382A2
0x18003822a  lea     r9, aSourceipaddres; "SourceIpAddress"
0x180038231  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180038238  lea     r8, aWriteinterface; "WriteInterfaceExtraInfo"
0x18003823f  mov     dword ptr [rsp+9C0h+lpData], eax
0x180038243  lea     rdx, aSFailedToWrite; "%s: Failed to write registry value %s f"...
0x18003824a  mov     word ptr [rbp+8C0h+var_840], r12w
0x180038252  lea     rcx, [rbp+8C0h+var_840]
0x180038259  mov     word ptr [rbp+8C0h+var_930], r12w
0x18003825e  movdqu  [rbp+8C0h+var_940], xmm0
0x180038263  call    FormatRRASErrorString
0x180038268  mov     rdx, qword ptr cs:xmmword_1800710A0
0x18003826f  lea     rax, [rbp+8C0h+var_930]
0x180038273  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x18003827a  lea     r9, [rbp+8C0h+var_940]
0x18003827e  mov     qword ptr [rsp+9C0h+cbData], rax
0x180038283  lea     r8, [rbp+8C0h+var_840]
0x18003828a  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180038291  test    r14, r14
0x180038294  mov     [rsp+9C0h+lpData], r12
0x180038299  cmovnz  r9, r14
0x18003829d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800382a2  mov     ebx, 57h ; 'W'
0x1800382a7  mov     [rsp+9C0h+var_980], ebx
0x1800382ab  jmp     loc_18003835D
0x1800382b0  lea     rdx, aSourceipaddres; "SourceIpAddress"
0x1800382b7  mov     rcx, rsi; hKey
0x1800382ba  call    cs:__imp_RegDeleteValueW
0x1800382c0  mov     [rsp+9C0h+var_980], eax
0x1800382c4  mov     ebx, eax
0x1800382c6  cmp     eax, r13d
0x1800382c9  jnz     short loc_1800382D0
0x1800382cb  mov     ebx, r12d
0x1800382ce  jmp     short loc_1800382A7
0x1800382d0  test    eax, eax
0x1800382d2  jz      loc_18003835D
0x1800382d8  cmp     qword ptr cs:xmmword_1800710A0, r12
0x1800382df  jz      short loc_18003835D
0x1800382e1  lea     r9, aSourceipaddres; "SourceIpAddress"
0x1800382e8  lea     rdx, aSCouldnTDelete; "%s: Couldn't delete the value %s: %d"
0x1800382ef  lea     r8, aWriteinterface; "WriteInterfaceExtraInfo"
0x1800382f6  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800382fd  lea     rcx, [rbp+8C0h+var_840]
0x180038304  mov     dword ptr [rsp+9C0h+lpData], eax
0x180038308  mov     word ptr [rbp+8C0h+var_840], r12w
0x180038310  movdqu  [rbp+8C0h+var_940], xmm0
0x180038315  mov     word ptr [rbp+8C0h+var_930], r12w
0x18003831a  call    FormatRRASErrorString
0x18003831f  mov     rdx, qword ptr cs:xmmword_1800710A0
0x180038326  lea     rax, [rbp+8C0h+var_930]
0x18003832a  mov     rcx, cs:?gCfgStoreEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gCfgStoreEtwContext
0x180038331  lea     r9, [rbp+8C0h+var_940]
0x180038335  mov     qword ptr [rsp+9C0h+cbData], rax
0x18003833a  lea     r8, [rbp+8C0h+var_840]
0x180038341  mov     rax, cs:?gCfgStoreParamTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBGPEBU_GUID@@22@ZEA; ulong (*gCfgStoreParamTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *,_GUID const *,ushort const *,ushort const *)
0x180038348  test    r14, r14
0x18003834b  mov     [rsp+9C0h+lpData], r12
0x180038350  cmovnz  r9, r14
0x180038354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038359  mov     ebx, [rsp+9C0h+var_980]
0x18003835d  lea     rcx, [rsp+9C0h+var_978]; this
0x180038362  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180038367  mov     eax, ebx
0x180038369  jmp     short loc_18003837A
0x18003836b  lea     rcx, [rsp+9C0h+var_978]; this
0x180038370  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x180038375  mov     eax, 57h ; 'W'
0x18003837a  mov     rcx, [rbp+8C0h+var_40]
0x180038381  xor     rcx, rsp; StackCookie
0x180038384  call    __security_check_cookie
0x180038389  mov     rbx, [rsp+9C0h+arg_8]
0x180038391  add     rsp, 990h
  ... truncated ...
```
