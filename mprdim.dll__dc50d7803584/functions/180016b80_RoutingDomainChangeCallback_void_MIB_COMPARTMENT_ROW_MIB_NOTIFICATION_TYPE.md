# RoutingDomainChangeCallback(void *,_MIB_COMPARTMENT_ROW *,_MIB_NOTIFICATION_TYPE)

- ea: `0x180016b80`
- end: `0x180016eb2`
- name: `?RoutingDomainChangeCallback@@YAXPEAXPEAU_MIB_COMPARTMENT_ROW@@W4_MIB_NOTIFICATION_TYPE@@@Z`
- size: `818`
- prototype: `void(void *, struct _MIB_COMPARTMENT_ROW *, enum _MIB_NOTIFICATION_TYPE)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180003f58`
- `0x18000d854`
- `0x18000df70`
- `0x180014244`
- `0x180014fcc`
- `0x180016b80`
- `0x180033e90`
- `0x180035d10`
- `0x180045d40`
- `0x180045d7c`
- `0x180045da4`
- `0x180046e2a`
- `0x180046e70`

## string_xrefs

- `0x180016d81`: `RoutingDomainChangeCallback: GetRoutingDomainConfiguration for %ws, compartment %d failed with error %d. Ignoring the error`
- `0x180016bd6`: `Delete`
- `0x180016ca5`: `RoutingDomainChangeCallback: Got routing domain %s notification for %ws, compartment Id = %d`
- `0x180016d3d`: `RoutingDomainChangeCallback: Ignoring notification for %ws, compartment %d, as this routing domain is not enabled for RRAS`
- `0x180016dba`: `RoutingDomainChangeCallback: DimStartRoutingDomain for %ws, compartment Id %d, failed with error %d`
- `0x180016deb`: `RoutingDomainChangeCallback: DimStopRoutingDomain for %ws, compartment Id %d failed with error: %d`
- `0x180016e9c`: `RoutingDomainChangeCallback: Ignoring the notification for routing domain %d, compartment Id %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RoutingDomainChangeCallback(void *a1, struct _GUID *a2, enum _MIB_NOTIFICATION_TYPE a3)
{
  __int64 v3; // rdi
  int v5; // esi
  int RoutingDomainConfiguration; // eax
  __int64 *v7; // rdx
  int started; // eax
  const wchar_t *v9; // rdx
  __int64 v10; // [rsp+20h] [rbp-E0h]
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v12[8]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v13[4]; // [rsp+40h] [rbp-C0h]
  GUID ActivityId; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v15; // [rsp+70h] [rbp-90h]
  int v16; // [rsp+80h] [rbp-80h] BYREF
  __int128 v17; // [rsp+84h] [rbp-7Ch]
  __int128 v18; // [rsp+94h] [rbp-6Ch]
  int v19; // [rsp+A4h] [rbp-5Ch]
  _BYTE v20[80]; // [rsp+B0h] [rbp-50h] BYREF
  int v21; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v22[2044]; // [rsp+104h] [rbp+4h] BYREF

  v3 = a3;
  v11 = 0;
  v13[0] = L"Parameter";
  v13[1] = L"Add";
  v13[2] = L"Delete";
  v13[3] = L"Initial";
  memset_0(v20, 0, sizeof(v20));
  ActivityId = 0;
  v15 = 0;
  v21 = 0;
  memset_0(v22, 0, sizeof(v22));
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  if ( !a2 || (_DWORD)v3 == 3 || !(_DWORD)v3 )
    return;
  scoped_read_lock::scoped_read_lock((scoped_read_lock *)v12, (struct IDimSRWLock *)&gblRoutingDomainOpsLock);
  v5 = SetActivityId(a2);
  MprConvertGuidToString(a2, 40, v20);
  if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
  {
    LOWORD(v21) = 0;
    LOWORD(v16) = 0;
    FormatRRASErrorString(
      &v21,
      L"RoutingDomainChangeCallback: Got routing domain %s notification for %ws, compartment Id = %d",
      v13[v3],
      v20,
      a2[1].Data1);
    if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasDimParamTraceError,
        (unsigned int)&v21,
        (_DWORD)a2,
        0,
        (__int64)&v16);
  }
  HIDWORD(v11) = 4;
  RoutingDomainConfiguration = GetRoutingDomainConfiguration(a2, (__int64)&v11);
  if ( !RoutingDomainConfiguration )
  {
    if ( (_DWORD)v3 == 1 )
    {
      if ( (v11 & 1) == 0 )
      {
        started = DimStartRoutingDomain(a2);
        if ( !started || (Microsoft_Windows_RRASEnableBits & 4) == 0 )
          goto LABEL_28;
        v9 = L"RoutingDomainChangeCallback: DimStartRoutingDomain for %ws, compartment Id %d, failed with error %d";
LABEL_24:
        LODWORD(v10) = started;
        LOWORD(v16) = 0;
        LOWORD(v21) = 0;
        FormatRRASErrorString(&v21, v9, v20, a2[1].Data1, v10);
        goto LABEL_25;
      }
    }
    else if ( (_DWORD)v3 == 2 && (v11 & 1) != 0 )
    {
      started = DimStopRoutingDomain(a2, 1);
      if ( !started || (Microsoft_Windows_RRASEnableBits & 4) == 0 )
        goto LABEL_28;
      v9 = L"RoutingDomainChangeCallback: DimStopRoutingDomain for %ws, compartment Id %d failed with error: %d";
      goto LABEL_24;
    }
    if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
      goto LABEL_28;
    LOWORD(v21) = 0;
    LOWORD(v16) = 0;
    FormatRRASErrorString(
      &v21,
      L"RoutingDomainChangeCallback: Ignoring the notification for routing domain %d, compartment Id %d",
      v20,
      a2[1].Data1);
    goto LABEL_25;
  }
  if ( RoutingDomainConfiguration == 1168 )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
    {
      LOWORD(v21) = 0;
      LOWORD(v16) = 0;
      FormatRRASErrorString(
        &v21,
        L"RoutingDomainChangeCallback: Ignoring notification for %ws, compartment %d, as this routing domain is not enabled for RRAS",
        v20,
        a2[1].Data1);
      if ( (Microsoft_Windows_RRASEnableBits & 8) != 0 )
      {
        v7 = RasDimParamTraceInfo;
LABEL_27:
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (_DWORD)v7,
          (unsigned int)&v21,
          (_DWORD)a2,
          0,
          (__int64)&v16);
        goto LABEL_28;
      }
    }
    goto LABEL_28;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 4) == 0 )
    goto LABEL_28;
  LOWORD(v21) = 0;
  LOWORD(v16) = 0;
  LODWORD(v10) = RoutingDomainConfiguration;
  FormatRRASErrorString(
    &v21,
    L"RoutingDomainChangeCallback: GetRoutingDomainConfiguration for %ws, compartment %d failed with error %d. Ignoring the error",
    v20,
    a2[1].Data1,
    v10);
LABEL_25:
  if ( (Microsoft_Windows_RRASEnableBits & 4) != 0 )
  {
    v7 = RasDimParamTraceError;
    goto LABEL_27;
  }
LABEL_28:
  if ( v5 )
    ReSetActivityId(&ActivityId);
  scoped_lock::~scoped_lock((scoped_lock *)v12);
}

```

## disassembly

```asm
0x180016b80  mov     [rsp-8+arg_0], rbx
0x180016b85  push    rbp
0x180016b86  push    rsi
0x180016b87  push    rdi
0x180016b88  lea     rbp, [rsp-810h]
0x180016b90  sub     rsp, 910h
0x180016b97  mov     rax, cs:__security_cookie
0x180016b9e  xor     rax, rsp
0x180016ba1  mov     [rbp+820h+var_20], rax
0x180016ba8  movsxd  rdi, r8d
0x180016bab  mov     rbx, rdx
0x180016bae  mov     dword ptr [rsp+920h+var_8F0+4], 0
0x180016bb6  mov     dword ptr [rsp+920h+var_8F0], 0
0x180016bbe  lea     rax, aParameter; "Parameter"
0x180016bc5  mov     [rsp+920h+var_8E0], rax
0x180016bca  lea     rax, aAdd; "Add"
0x180016bd1  mov     [rsp+920h+var_8D8], rax
0x180016bd6  lea     rax, aDelete; "Delete"
0x180016bdd  mov     [rsp+920h+var_8D0], rax
0x180016be2  lea     rax, aInitial; "Initial"
0x180016be9  mov     [rsp+920h+var_8C8], rax
0x180016bee  xor     edx, edx; Val
0x180016bf0  lea     r8d, [rdx+50h]; Size
0x180016bf4  lea     rcx, [rbp+820h+var_870]; void *
0x180016bf8  call    memset_0
0x180016bfd  xorps   xmm0, xmm0
0x180016c00  movups  xmmword ptr [rsp+920h+ActivityId.Data1], xmm0
0x180016c05  xorps   xmm1, xmm1
0x180016c08  movups  [rsp+920h+var_8B0], xmm1
0x180016c0d  xor     eax, eax
0x180016c0f  mov     [rbp+820h+var_820], eax
0x180016c12  xor     edx, edx; Val
0x180016c14  mov     r8d, 7FCh; Size
0x180016c1a  lea     rcx, [rbp+820h+var_81C]; void *
0x180016c1e  call    memset_0
0x180016c23  xor     eax, eax
0x180016c25  mov     [rbp+820h+var_8A0], eax
0x180016c28  xorps   xmm0, xmm0
0x180016c2b  movups  [rbp+820h+var_89C], xmm0
0x180016c2f  movups  [rbp+820h+var_88C], xmm0
0x180016c33  mov     [rbp+820h+var_87C], eax
0x180016c36  test    rbx, rbx
0x180016c39  jz      loc_180016E5F
0x180016c3f  cmp     edi, 3
0x180016c42  jz      loc_180016E5F
0x180016c48  test    edi, edi
0x180016c4a  jz      loc_180016E5F
0x180016c50  lea     rdx, ?gblRoutingDomainOpsLock@@3Vcritical_section@@A; struct IDimSRWLock *
0x180016c57  lea     rcx, [rsp+920h+var_8E8]; this
0x180016c5c  call    ??0scoped_read_lock@@QEAA@PEAUIDimSRWLock@@@Z; scoped_read_lock::scoped_read_lock(IDimSRWLock *)
0x180016c61  nop
0x180016c62  lea     rdx, [rsp+920h+ActivityId]
0x180016c67  mov     rcx, rbx; ActivityId
0x180016c6a  call    SetActivityId
0x180016c6f  mov     esi, eax
0x180016c71  lea     r8, [rbp+820h+var_870]
0x180016c75  mov     edx, 28h ; '('
0x180016c7a  mov     rcx, rbx
0x180016c7d  call    MprConvertGuidToString
0x180016c82  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180016c89  jz      short loc_180016CEA
0x180016c8b  xor     ecx, ecx
0x180016c8d  mov     word ptr [rbp+820h+var_820], cx
0x180016c91  mov     word ptr [rbp+820h+var_8A0], cx
0x180016c95  mov     eax, [rbx+10h]
0x180016c98  mov     dword ptr [rsp+920h+var_900], eax
0x180016c9c  lea     r9, [rbp+820h+var_870]
0x180016ca0  mov     r8, [rsp+rdi*8+920h+var_8E0]
0x180016ca5  lea     rdx, aRoutingdomainc_1; "RoutingDomainChangeCallback: Got routin"...
0x180016cac  lea     rcx, [rbp+820h+var_820]
0x180016cb0  call    FormatRRASErrorString
0x180016cb5  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180016cbc  jz      short loc_180016CEA
0x180016cbe  lea     rax, [rbp+820h+var_8A0]
0x180016cc2  mov     [rsp+920h+var_8F8], rax
0x180016cc7  mov     [rsp+920h+var_900], 0
0x180016cd0  mov     r9, rbx
0x180016cd3  lea     r8, [rbp+820h+var_820]
0x180016cd7  lea     rdx, RasDimParamTraceError
0x180016cde  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180016ce5  call    McTemplateU0zjzz_EventWriteTransfer
0x180016cea  mov     dword ptr [rsp+920h+var_8F0+4], 4
0x180016cf2  lea     rax, [rsp+920h+var_8F0]
0x180016cf7  mov     [rsp+920h+var_900], rax; __int64
0x180016cfc  lea     r9, [rsp+920h+var_8F0+4]
0x180016d01  xor     r8d, r8d
0x180016d04  mov     edx, 200h
0x180016d09  mov     rcx, rbx; struct _GUID *
0x180016d0c  call    GetRoutingDomainConfiguration
0x180016d11  mov     ecx, eax
0x180016d13  test    eax, eax
0x180016d15  jz      short loc_180016D8A
0x180016d17  cmp     eax, 490h
0x180016d1c  jnz     short loc_180016D66
0x180016d1e  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x180016d25  jz      loc_180016E46
0x180016d2b  xor     eax, eax
0x180016d2d  mov     word ptr [rbp+820h+var_820], ax
0x180016d31  mov     word ptr [rbp+820h+var_8A0], ax
0x180016d35  mov     r9d, [rbx+10h]
0x180016d39  lea     r8, [rbp+820h+var_870]
0x180016d3d  lea     rdx, aRoutingdomainc_0; "RoutingDomainChangeCallback: Ignoring n"...
0x180016d44  lea     rcx, [rbp+820h+var_820]
0x180016d48  call    FormatRRASErrorString
0x180016d4d  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 8
0x180016d54  jz      loc_180016E46
0x180016d5a  lea     rdx, RasDimParamTraceInfo
0x180016d61  jmp     loc_180016E21
0x180016d66  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180016d6d  jz      loc_180016E46
0x180016d73  xor     eax, eax
0x180016d75  mov     word ptr [rbp+820h+var_820], ax
0x180016d79  mov     word ptr [rbp+820h+var_8A0], ax
0x180016d7d  mov     dword ptr [rsp+920h+var_900], ecx
0x180016d81  lea     rdx, aRoutingdomainc_2; "RoutingDomainChangeCallback: GetRouting"...
0x180016d88  jmp     short loc_180016E00
0x180016d8a  mov     edx, 1; int
0x180016d8f  cmp     edi, edx
0x180016d91  jnz     short loc_180016DC3
0x180016d93  test    byte ptr [rsp+920h+var_8F0], dl
0x180016d97  jnz     loc_180016E81
0x180016d9d  mov     rcx, rbx; struct _GUID *
0x180016da0  call    ?DimStartRoutingDomain@@YAKPEAU_GUID@@@Z; DimStartRoutingDomain(_GUID *)
0x180016da5  test    eax, eax
0x180016da7  jz      loc_180016E46
0x180016dad  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180016db4  jz      loc_180016E46
0x180016dba  lea     rdx, aRoutingdomainc; "RoutingDomainChangeCallback: DimStartRo"...
0x180016dc1  jmp     short loc_180016DF2
0x180016dc3  cmp     edi, 2
0x180016dc6  jnz     loc_180016E81
0x180016dcc  test    byte ptr [rsp+920h+var_8F0], dl
0x180016dd0  jz      loc_180016E81
0x180016dd6  mov     rcx, rbx; struct _GUID *
0x180016dd9  call    ?DimStopRoutingDomain@@YAKPEAU_GUID@@H@Z; DimStopRoutingDomain(_GUID *,int)
0x180016dde  test    eax, eax
0x180016de0  jz      short loc_180016E46
0x180016de2  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180016de9  jz      short loc_180016E46
0x180016deb  lea     rdx, aRoutingdomainc_4; "RoutingDomainChangeCallback: DimStopRou"...
0x180016df2  xor     ecx, ecx
0x180016df4  mov     dword ptr [rsp+920h+var_900], eax
0x180016df8  mov     word ptr [rbp+820h+var_8A0], cx
0x180016dfc  mov     word ptr [rbp+820h+var_820], cx
0x180016e00  mov     r9d, [rbx+10h]
0x180016e04  lea     r8, [rbp+820h+var_870]
0x180016e08  lea     rcx, [rbp+820h+var_820]
0x180016e0c  call    FormatRRASErrorString
0x180016e11  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180016e18  jz      short loc_180016E46
0x180016e1a  lea     rdx, RasDimParamTraceError
0x180016e21  lea     rax, [rbp+820h+var_8A0]
0x180016e25  mov     [rsp+920h+var_8F8], rax
0x180016e2a  mov     [rsp+920h+var_900], 0
0x180016e33  mov     r9, rbx
0x180016e36  lea     r8, [rbp+820h+var_820]
0x180016e3a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180016e41  call    McTemplateU0zjzz_EventWriteTransfer
0x180016e46  test    esi, esi
0x180016e48  jz      short loc_180016E55
0x180016e4a  lea     rcx, [rsp+920h+ActivityId]; ActivityId
0x180016e4f  call    ReSetActivityId
0x180016e54  nop
0x180016e55  lea     rcx, [rsp+920h+var_8E8]; this
0x180016e5a  call    ??1scoped_lock@@QEAA@XZ; scoped_lock::~scoped_lock(void)
0x180016e5f  mov     rcx, [rbp+820h+var_20]
0x180016e66  xor     rcx, rsp; StackCookie
0x180016e69  call    __security_check_cookie
0x180016e6e  mov     rbx, [rsp+920h+arg_0]
0x180016e76  add     rsp, 910h
0x180016e7d  pop     rdi
0x180016e7e  pop     rsi
0x180016e7f  pop     rbp
0x180016e80  retn
0x180016e81  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 4
0x180016e88  jz      short loc_180016E46
0x180016e8a  xor     eax, eax
0x180016e8c  mov     word ptr [rbp+820h+var_820], ax
0x180016e90  mov     word ptr [rbp+820h+var_8A0], ax
0x180016e94  mov     r9d, [rbx+10h]
0x180016e98  lea     r8, [rbp+820h+var_870]
0x180016e9c  lea     rdx, aRoutingdomainc_3; "RoutingDomainChangeCallback: Ignoring t"...
0x180016ea3  lea     rcx, [rbp+820h+var_820]
0x180016ea7  call    FormatRRASErrorString
0x180016eac  jmp     loc_180016E11
```
