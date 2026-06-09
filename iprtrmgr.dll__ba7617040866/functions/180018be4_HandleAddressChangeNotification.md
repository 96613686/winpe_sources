# HandleAddressChangeNotification

- ea: `0x180018be4`
- end: `0x1800190c8`
- name: `HandleAddressChangeNotification`
- size: `1252`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180052050`

## callees

- `0x180001f90`
- `0x18000ac60`
- `0x180011790`
- `0x180015550`
- `0x180018be4`
- `0x18001a110`
- `0x18001a82c`
- `0x18001bc94`
- `0x18001be68`
- `0x18004ffd8`
- `0x180057bac`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180018d30`
- `ntdll!RtlAcquireResourceExclusive` at `0x180018d30`
- `ntdll!RtlReleaseResource` at `0x180019098`
- `ntdll!RtlReleaseResource` at `0x180019098`

## string_xrefs

- `0x180018c94`: `HandleAddressChangeNotification: NsiGetRoutingDomainIdForCompartment failed with error %d`
- `0x180018e0a`: `AddressChange: Error %d trying to update binding for %ws`
- `0x18001904f`: `AddressChange: Error %d trying to update binding for %ws`

## pseudocode

```c
void __fastcall HandleAddressChangeNotification(unsigned int a1, int a2, unsigned int a3)
{
  int *v4; // rsi
  unsigned int RoutingDomainIdForCompartment; // eax
  __int64 InternalInterfaceForRoutingDomain; // rax
  __int64 v9; // rbx
  unsigned int updated; // eax
  __int64 v11; // rdx
  __int64 *v12; // rdx
  unsigned int v13; // eax
  unsigned int v14; // eax
  __int64 *i; // rsi
  __int64 v16; // rbx
  unsigned int v17; // eax
  __int64 *v18; // rdx
  __int128 *v19; // r9
  const wchar_t *v20; // rdx
  unsigned int v21; // eax
  __int64 v22; // rdx
  unsigned int v23; // eax
  struct _GUID v24; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v25; // [rsp+40h] [rbp-C0h] BYREF
  int v26; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v27; // [rsp+54h] [rbp-ACh]
  __int128 v28; // [rsp+64h] [rbp-9Ch]
  int v29; // [rsp+74h] [rbp-8Ch]
  int v30; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v31[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  v30 = 0;
  v4 = &g_bUninitServerv4;
  if ( !a3 )
    v4 = &g_bUninitServerv6;
  v24 = 0;
  memset_0(v31, 0, sizeof(v31));
  v26 = 0;
  v29 = 0;
  v27 = 0;
  v28 = 0;
  v25 = 0;
  RoutingDomainIdForCompartment = NsiGetRoutingDomainIdForCompartment(a1, &v24);
  if ( !RoutingDomainIdForCompartment )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v30) = 0;
      LOWORD(v26) = 0;
      FormatRRASErrorString(&v30, L"HandleAddressChangeNotification for bv4=%d", a3);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)&v30,
          (unsigned int)&v24,
          0,
          (__int64)&v26);
    }
    RtlAcquireResourceExclusive(&Resource, 1u);
    InternalInterfaceForRoutingDomain = GetInternalInterfaceForRoutingDomain(&v24, a3 != 0 ? 33 : 87);
    v9 = InternalInterfaceForRoutingDomain;
    if ( !InternalInterfaceForRoutingDomain )
      goto LABEL_30;
    updated = UpdateBindingInformation(InternalInterfaceForRoutingDomain);
    if ( updated )
    {
      if ( updated == 1227 )
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
          goto LABEL_30;
        LOWORD(v30) = 0;
        LOWORD(v26) = 0;
        FormatRRASErrorString(&v30, L"AddressChange: No address change for %ws", *(_QWORD *)(v9 + 72));
        if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
          goto LABEL_30;
        v12 = RasRtrmgrParamTraceInfo;
        goto LABEL_24;
      }
      if ( updated == 232 )
      {
        v13 = LanEtcInterfaceUpToDown(v9);
        *v4 = 1;
        if ( !v13 || (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
          goto LABEL_30;
        LOWORD(v30) = 0;
        LOWORD(v26) = 0;
        FormatRRASErrorString(&v30, L"AddressChange: Error %d bringing down interface %ws", v13, *(_QWORD *)(v9 + 72));
      }
      else
      {
        if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
          goto LABEL_30;
        LOWORD(v30) = 0;
        LOWORD(v26) = 0;
        FormatRRASErrorString(
          &v30,
          L"AddressChange: Error %d trying to update binding for %ws",
          updated,
          *(_QWORD *)(v9 + 72));
      }
    }
    else
    {
      if ( !*v4 )
      {
        UnbindInterfaceInAllProtocols(v9, v11, updated);
        BindInterfaceInAllProtocols(v9);
        goto LABEL_30;
      }
      *v4 = 0;
      v14 = LanEtcInterfaceDownToUp(v9);
      if ( !v14 || (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
        goto LABEL_30;
      LOWORD(v30) = 0;
      LOWORD(v26) = 0;
      FormatRRASErrorString(&v30, L"AddressChange: Error %d bringing up server if", v14);
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
    {
      v12 = RasRtrMgrParamTraceError;
LABEL_24:
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (_DWORD)v12,
        (unsigned int)&v30,
        (unsigned int)&v24,
        0,
        (__int64)&v26);
    }
LABEL_30:
    for ( i = &ICBList; ; i = (__int64 *)*i )
    {
      v16 = *i;
      if ( (__int64 *)*i == &ICBList )
      {
        RtlReleaseResource(&Resource);
        return;
      }
      if ( *(_DWORD *)(v16 + 144) == 3
        && *(_DWORD *)(v16 + 16) == a2
        && a1 == *(_DWORD *)(v16 + 704)
        && *(_DWORD *)(v16 + 516) == a3 )
      {
        if ( !*(_DWORD *)(v16 + 168) )
        {
          if ( *(_DWORD *)(v16 + 172) != 1 )
            continue;
          v17 = LanEtcInterfaceDownToUp(*i);
          if ( !v17 )
          {
            if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
              continue;
            v20 = L"AddressChange: Succesfully brought up %ws";
            goto LABEL_48;
          }
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
            continue;
          LOWORD(v30) = 0;
          LOWORD(v26) = 0;
          FormatRRASErrorString(
            &v30,
            L"AddressChange: Tried to bring up %ws on receiving DHCP notification. However LanInterfaceDownToUp() returned error %d",
            *(_QWORD *)(v16 + 72),
            v17);
          goto LABEL_41;
        }
        v21 = UpdateBindingInformation(*i);
        if ( v21 )
        {
          if ( v21 == 1227 )
          {
            if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
              continue;
            v20 = L"AddressChange: No address change for %ws";
LABEL_48:
            LOWORD(v30) = 0;
            LOWORD(v26) = 0;
            FormatRRASErrorString(&v30, v20, *(_QWORD *)(v16 + 72));
            if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
              continue;
            v18 = RasRtrmgrParamTraceInfo;
LABEL_43:
            v19 = &v25;
            if ( v16 != -688 )
              LODWORD(v19) = v16 + 688;
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (_DWORD)v18,
              (unsigned int)&v30,
              (_DWORD)v19,
              *(_QWORD *)(v16 + 72),
              (__int64)&v26);
            continue;
          }
          if ( v21 == 232 )
          {
            v23 = LanEtcInterfaceUpToDown(v16);
            if ( !v23 || (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
              continue;
            LOWORD(v30) = 0;
            LOWORD(v26) = 0;
            FormatRRASErrorString(
              &v30,
              L"AddressChange: Error %d bringing down interface %ws",
              v23,
              *(_QWORD *)(v16 + 72));
          }
          else
          {
            if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
              continue;
            LOWORD(v30) = 0;
            LOWORD(v26) = 0;
            FormatRRASErrorString(
              &v30,
              L"AddressChange: Error %d trying to update binding for %ws",
              v21,
              *(_QWORD *)(v16 + 72));
          }
LABEL_41:
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) == 0 )
            continue;
          v18 = RasRtrMgrParamTraceError;
          goto LABEL_43;
        }
        UnbindInterfaceInAllProtocols(v16, v22, 0);
        BindInterfaceInAllProtocols(v16);
        if ( *(_DWORD *)(v16 + 516) )
          UpdateAdvertisement(v16);
      }
    }
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
  {
    LOWORD(v30) = 0;
    FormatRRASErrorString(
      &v30,
      L"HandleAddressChangeNotification: NsiGetRoutingDomainIdForCompartment failed with error %d",
      RoutingDomainIdForCompartment);
    if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrMgrTraceError, &v30);
  }
}

```

## disassembly

```asm
0x180018be4  mov     [rsp-8+arg_8], rbx
0x180018be9  push    rbp
0x180018bea  push    rsi
0x180018beb  push    rdi
0x180018bec  push    r12
0x180018bee  push    r13
0x180018bf0  push    r14
0x180018bf2  push    r15
0x180018bf4  lea     rbp, [rsp-790h]
0x180018bfc  sub     rsp, 890h
0x180018c03  mov     rax, cs:__security_cookie
0x180018c0a  xor     rax, rsp
0x180018c0d  mov     [rbp+7C0h+var_40], rax
0x180018c14  xor     ebx, ebx
0x180018c16  lea     rax, g_bUninitServerv6
0x180018c1d  test    r8d, r8d
0x180018c20  mov     [rbp+7C0h+var_840], ebx
0x180018c23  mov     r15d, r8d
0x180018c26  lea     rsi, g_bUninitServerv4
0x180018c2d  cmovz   rsi, rax
0x180018c31  mov     r13d, edx
0x180018c34  mov     r12d, ecx
0x180018c37  xorps   xmm0, xmm0
0x180018c3a  xor     edx, edx; Val
0x180018c3c  lea     rcx, [rbp+7C0h+var_83C]; void *
0x180018c40  mov     r8d, 7FCh; Size
0x180018c46  movups  xmmword ptr [rsp+8C0h+var_890.Data1], xmm0
0x180018c4b  call    memset_0
0x180018c50  xorps   xmm0, xmm0
0x180018c53  mov     [rsp+8C0h+var_870], ebx
0x180018c57  xor     eax, eax
0x180018c59  lea     rdx, [rsp+8C0h+var_890]
0x180018c5e  mov     ecx, r12d
0x180018c61  mov     [rsp+8C0h+var_84C], eax
0x180018c65  movups  [rsp+8C0h+var_86C], xmm0
0x180018c6a  movups  [rsp+8C0h+var_85C], xmm0
0x180018c6f  movups  [rsp+8C0h+var_880], xmm0
0x180018c74  call    NsiGetRoutingDomainIdForCompartment
0x180018c79  test    eax, eax
0x180018c7b  jz      short loc_180018CCD
0x180018c7d  mov     dil, 40h ; '@'
0x180018c80  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180018c87  jz      loc_18001909E
0x180018c8d  mov     r8d, eax
0x180018c90  mov     word ptr [rbp+7C0h+var_840], bx
0x180018c94  lea     rdx, aHandleaddressc; "HandleAddressChangeNotification: NsiGet"...
0x180018c9b  lea     rcx, [rbp+7C0h+var_840]
0x180018c9f  call    FormatRRASErrorString
0x180018ca4  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180018cab  jz      loc_18001909E
0x180018cb1  lea     r8, [rbp+7C0h+var_840]
0x180018cb5  lea     rdx, RasRtrMgrTraceError
0x180018cbc  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180018cc3  call    McTemplateU0z_EventWriteTransfer
0x180018cc8  jmp     loc_18001909E
0x180018ccd  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180018cd3  lea     r14, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180018cda  jge     short loc_180018D27
0x180018cdc  mov     r8d, r15d
0x180018cdf  mov     word ptr [rbp+7C0h+var_840], bx
0x180018ce3  lea     rdx, aHandleaddressc_0; "HandleAddressChangeNotification for bv4"...
0x180018cea  mov     word ptr [rsp+8C0h+var_870], bx
0x180018cef  lea     rcx, [rbp+7C0h+var_840]
0x180018cf3  call    FormatRRASErrorString
0x180018cf8  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, bl
0x180018cfe  jge     short loc_180018D27
0x180018d00  lea     rax, [rsp+8C0h+var_870]
0x180018d05  mov     rcx, r14
0x180018d08  mov     [rsp+8C0h+var_898], rax
0x180018d0d  lea     r9, [rsp+8C0h+var_890]
0x180018d12  lea     r8, [rbp+7C0h+var_840]
0x180018d16  mov     [rsp+8C0h+var_8A0], rbx
0x180018d1b  lea     rdx, RasRtrmgrParamTraceInfo
0x180018d22  call    McTemplateU0zjzz_EventWriteTransfer
0x180018d27  mov     dl, 1; Wait
0x180018d29  lea     rcx, Resource; Resource
0x180018d30  call    cs:__imp_RtlAcquireResourceExclusive
0x180018d36  mov     eax, r15d
0x180018d39  lea     rcx, [rsp+8C0h+var_890]; struct _GUID *
0x180018d3e  neg     eax
0x180018d40  sbb     edx, edx
0x180018d42  and     edx, 0FFFFFFCAh
0x180018d45  add     edx, 57h ; 'W'; unsigned int
0x180018d48  call    GetInternalInterfaceForRoutingDomain
0x180018d4d  mov     rbx, rax
0x180018d50  mov     dil, 40h ; '@'
0x180018d53  test    rax, rax
0x180018d56  jz      loc_180018EAA
0x180018d5c  mov     rcx, rax
0x180018d5f  call    UpdateBindingInformation
0x180018d64  mov     r8d, eax
0x180018d67  test    eax, eax
0x180018d69  jz      loc_180018E5D
0x180018d6f  cmp     eax, 4CBh
0x180018d74  jnz     short loc_180018DB8
0x180018d76  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180018d7d  jge     loc_180018EAA
0x180018d83  xor     eax, eax
0x180018d85  lea     rdx, aAddresschangeN; "AddressChange: No address change for %w"...
0x180018d8c  mov     word ptr [rbp+7C0h+var_840], ax
0x180018d90  lea     rcx, [rbp+7C0h+var_840]
0x180018d94  mov     word ptr [rsp+8C0h+var_870], ax
0x180018d99  mov     r8, [rbx+48h]
0x180018d9d  call    FormatRRASErrorString
0x180018da2  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180018da9  jge     loc_180018EAA
0x180018daf  lea     rdx, RasRtrmgrParamTraceInfo
0x180018db6  jmp     short loc_180018E37
0x180018db8  cmp     r8d, 0E8h
0x180018dbf  jnz     short loc_180018DFB
0x180018dc1  mov     rcx, rbx
0x180018dc4  call    LanEtcInterfaceUpToDown
0x180018dc9  mov     dword ptr [rsi], 1
0x180018dcf  test    eax, eax
0x180018dd1  jz      loc_180018EAA
0x180018dd7  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180018dde  jz      loc_180018EAA
0x180018de4  xor     ecx, ecx
0x180018de6  lea     rdx, aAddresschangeE_1; "AddressChange: Error %d bringing down i"...
0x180018ded  mov     word ptr [rbp+7C0h+var_840], cx
0x180018df1  mov     r8d, eax
0x180018df4  mov     word ptr [rsp+8C0h+var_870], cx
0x180018df9  jmp     short loc_180018E1A
0x180018dfb  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180018e02  jz      loc_180018EAA
0x180018e08  xor     eax, eax
0x180018e0a  lea     rdx, aAddresschangeE; "AddressChange: Error %d trying to updat"...
0x180018e11  mov     word ptr [rbp+7C0h+var_840], ax
0x180018e15  mov     word ptr [rsp+8C0h+var_870], ax
0x180018e1a  mov     r9, [rbx+48h]
0x180018e1e  lea     rcx, [rbp+7C0h+var_840]
0x180018e22  call    FormatRRASErrorString
0x180018e27  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180018e2e  jz      short loc_180018EAA
0x180018e30  lea     rdx, RasRtrMgrParamTraceError
0x180018e37  lea     rax, [rsp+8C0h+var_870]
0x180018e3c  mov     rcx, r14
0x180018e3f  mov     [rsp+8C0h+var_898], rax
0x180018e44  lea     r8, [rbp+7C0h+var_840]
0x180018e48  lea     r9, [rsp+8C0h+var_890]
0x180018e4d  mov     [rsp+8C0h+var_8A0], 0
0x180018e56  call    McTemplateU0zjzz_EventWriteTransfer
0x180018e5b  jmp     short loc_180018EAA
0x180018e5d  cmp     dword ptr [rsi], 0
0x180018e60  mov     rcx, rbx
0x180018e63  jz      short loc_180018E9D
0x180018e65  mov     dword ptr [rsi], 0
0x180018e6b  call    LanEtcInterfaceDownToUp
0x180018e70  test    eax, eax
0x180018e72  jz      short loc_180018EAA
0x180018e74  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180018e7b  jz      short loc_180018EAA
0x180018e7d  xor     ecx, ecx
0x180018e7f  lea     rdx, aAddresschangeE_0; "AddressChange: Error %d bringing up ser"...
0x180018e86  mov     word ptr [rbp+7C0h+var_840], cx
0x180018e8a  mov     r8d, eax
0x180018e8d  mov     word ptr [rsp+8C0h+var_870], cx
0x180018e92  lea     rcx, [rbp+7C0h+var_840]
0x180018e96  call    FormatRRASErrorString
0x180018e9b  jmp     short loc_180018E27
0x180018e9d  call    UnbindInterfaceInAllProtocols
0x180018ea2  mov     rcx, rbx
0x180018ea5  call    BindInterfaceInAllProtocols
0x180018eaa  lea     rax, ICBList
0x180018eb1  mov     rsi, rax
0x180018eb4  mov     rbx, [rsi]
0x180018eb7  cmp     rbx, rax
0x180018eba  jz      loc_180019091
0x180018ec0  cmp     dword ptr [rbx+90h], 3
0x180018ec7  jnz     loc_180019089
0x180018ecd  cmp     [rbx+10h], r13d
0x180018ed1  jnz     loc_180019089
0x180018ed7  cmp     r12d, [rbx+2C0h]
0x180018ede  jnz     loc_180019089
0x180018ee4  cmp     [rbx+204h], r15d
0x180018eeb  jnz     loc_180019089
0x180018ef1  cmp     dword ptr [rbx+0A8h], 0
0x180018ef8  jnz     loc_180018FD3
0x180018efe  cmp     dword ptr [rbx+0ACh], 1
0x180018f05  jnz     loc_180019089
0x180018f0b  mov     rcx, rbx
0x180018f0e  call    LanEtcInterfaceDownToUp
0x180018f13  test    eax, eax
0x180018f15  jz      short loc_180018F91
0x180018f17  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180018f1e  jz      loc_180019082
0x180018f24  xor     ecx, ecx
0x180018f26  lea     rdx, aAddresschangeT; "AddressChange: Tried to bring up %ws on"...
0x180018f2d  mov     word ptr [rbp+7C0h+var_840], cx
0x180018f31  mov     r9d, eax
0x180018f34  mov     word ptr [rsp+8C0h+var_870], cx
0x180018f39  lea     rcx, [rbp+7C0h+var_840]
0x180018f3d  mov     r8, [rbx+48h]
0x180018f41  call    FormatRRASErrorString
0x180018f46  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x180018f4d  jz      loc_180019082
0x180018f53  lea     rdx, RasRtrMgrParamTraceError
0x180018f5a  lea     rax, [rbx+2B0h]
0x180018f61  mov     rcx, r14
0x180018f64  test    rax, rax
0x180018f67  lea     r9, [rsp+8C0h+var_880]
0x180018f6c  lea     r8, [rbp+7C0h+var_840]
0x180018f70  cmovnz  r9, rax
0x180018f74  lea     rax, [rsp+8C0h+var_870]
0x180018f79  mov     [rsp+8C0h+var_898], rax
0x180018f7e  mov     rax, [rbx+48h]
0x180018f82  mov     [rsp+8C0h+var_8A0], rax
0x180018f87  call    McTemplateU0zjzz_EventWriteTransfer
0x180018f8c  jmp     loc_180019082
0x180018f91  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180018f98  jge     loc_180019082
0x180018f9e  lea     rdx, aAddresschangeS; "AddressChange: Succesfully brought up %"...
0x180018fa5  xor     eax, eax
0x180018fa7  lea     rcx, [rbp+7C0h+var_840]
0x180018fab  mov     word ptr [rbp+7C0h+var_840], ax
0x180018faf  mov     word ptr [rsp+8C0h+var_870], ax
0x180018fb4  mov     r8, [rbx+48h]
0x180018fb8  call    FormatRRASErrorString
0x180018fbd  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180018fc4  jge     loc_180019082
0x180018fca  lea     rdx, RasRtrmgrParamTraceInfo
0x180018fd1  jmp     short loc_180018F5A
0x180018fd3  mov     rcx, rbx
0x180018fd6  call    UpdateBindingInformation
0x180018fdb  mov     r8d, eax
0x180018fde  test    eax, eax
0x180018fe0  jz      short loc_180019061
0x180018fe2  cmp     eax, 4CBh
0x180018fe7  jnz     short loc_180018FFF
0x180018fe9  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180018ff0  jge     loc_180019082
0x180018ff6  lea     rdx, aAddresschangeN; "AddressChange: No address change for %w"...
0x180018ffd  jmp     short loc_180018FA5
0x180018fff  cmp     r8d, 0E8h
0x180019006  jnz     short loc_180019044
0x180019008  mov     rcx, rbx
0x18001900b  call    LanEtcInterfaceUpToDown
0x180019010  test    eax, eax
0x180019012  jz      short loc_180019082
0x180019014  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x18001901b  jz      short loc_180019082
0x18001901d  xor     ecx, ecx
0x18001901f  lea     rdx, aAddresschangeE_1; "AddressChange: Error %d bringing down i"...
0x180019026  mov     word ptr [rbp+7C0h+var_840], cx
0x18001902a  mov     r8d, eax
0x18001902d  mov     word ptr [rsp+8C0h+var_870], cx
0x180019032  mov     r9, [rbx+48h]
0x180019036  lea     rcx, [rbp+7C0h+var_840]
0x18001903a  call    FormatRRASErrorString
0x18001903f  jmp     loc_180018F46
0x180019044  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, dil
0x18001904b  jz      short loc_180019082
0x18001904d  xor     eax, eax
0x18001904f  lea     rdx, aAddresschangeE; "AddressChange: Error %d trying to updat"...
0x180019056  mov     word ptr [rbp+7C0h+var_840], ax
0x18001905a  mov     word ptr [rsp+8C0h+var_870], ax
0x18001905f  jmp     short loc_180019032
0x180019061  mov     rcx, rbx
0x180019064  call    UnbindInterfaceInAllProtocols
0x180019069  mov     rcx, rbx
0x18001906c  call    BindInterfaceInAllProtocols
0x180019071  cmp     dword ptr [rbx+204h], 0
0x180019078  jz      short loc_180019082
0x18001907a  mov     rcx, rbx
0x18001907d  call    UpdateAdvertisement
0x180019082  lea     rax, ICBList
0x180019089  mov     rsi, [rsi]
0x18001908c  jmp     loc_180018EB4
0x180019091  lea     rcx, Resource; Resource
0x180019098  call    cs:__imp_RtlReleaseResource
0x18001909e  mov     rcx, [rbp+7C0h+var_40]
0x1800190a5  xor     rcx, rsp; StackCookie
0x1800190a8  call    __security_check_cookie
0x1800190ad  mov     rbx, [rsp+8C0h+arg_8]
0x1800190b5  add     rsp, 890h
0x1800190bc  pop     r15
0x1800190be  pop     r14
0x1800190c0  pop     r13
0x1800190c2  pop     r12
0x1800190c4  pop     rdi
0x1800190c5  pop     rsi
0x1800190c6  pop     rbp
0x1800190c7  retn
```
