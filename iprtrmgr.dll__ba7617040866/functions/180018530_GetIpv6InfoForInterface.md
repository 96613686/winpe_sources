# GetIpv6InfoForInterface

- ea: `0x180018530`
- end: `0x180018abc`
- name: `GetIpv6InfoForInterface`
- size: `1420`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000f868`
- `0x18001be68`

## callees

- `0x180001f90`
- `0x18000ac60`
- `0x180011790`
- `0x180018530`
- `0x1800583cc`
- `0x180058570`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800186ec`
- `KERNEL32!LocalFree` at `0x1800188c7`
- `KERNEL32!LocalFree` at `0x1800186ec`
- `KERNEL32!LocalFree` at `0x1800188c7`
- `KERNEL32!LocalAlloc` at `0x1800186b9`
- `KERNEL32!LocalAlloc` at `0x1800186b9`
- `KERNEL32!GetLastError` at `0x18001870e`
- `KERNEL32!GetLastError` at `0x18001870e`
- `KERNEL32!HeapAlloc` at `0x18001886e`
- `KERNEL32!HeapAlloc` at `0x18001886e`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x180018669`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x180018669`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180018678`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x1800188d0`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x180018678`
- `IPHLPAPI!SetCurrentThreadCompartmentId` at `0x1800188d0`
- `IPHLPAPI!GetAdaptersAddresses` at `0x1800186a5`
- `IPHLPAPI!GetAdaptersAddresses` at `0x1800186dc`
- `IPHLPAPI!GetAdaptersAddresses` at `0x1800186a5`
- `IPHLPAPI!GetAdaptersAddresses` at `0x1800186dc`

## string_xrefs

- `0x1800185be`: `GetIpv6InfoForInterface: NsiGetRoutingDomainIdForCompartment failed and returned %d`
- `0x1800189cd`: `GetIpv6InfoForInterface: SetCurrentThreadCompartmentId failed and returned %d`

## pseudocode

```c
__int64 __fastcall GetIpv6InfoForInterface(unsigned int a1, NET_IF_COMPARTMENT_ID a2, unsigned int *a3, _QWORD *a4)
{
  ULONG RoutingDomainIdForCompartment; // eax
  ULONG AdaptersAddresses; // ebx
  NET_IF_COMPARTMENT_ID v9; // r14d
  __int64 i; // r15
  char v11; // al
  __int64 v12; // rdi
  const wchar_t *v13; // rdx
  __int64 *v14; // rdx
  __int64 v15; // rcx
  unsigned int v16; // r14d
  LPVOID v17; // rax
  __int64 v18; // r8
  unsigned int v19; // r9d
  __int64 v20; // rdx
  __int64 v21; // rcx
  ULONG SizePointer; // [rsp+30h] [rbp-8A8h] BYREF
  NET_IF_COMPARTMENT_ID CurrentThreadCompartmentId; // [rsp+34h] [rbp-8A4h]
  unsigned int *v25; // [rsp+38h] [rbp-8A0h]
  _OWORD v26[2]; // [rsp+40h] [rbp-898h] BYREF
  _WORD v27[24]; // [rsp+60h] [rbp-878h] BYREF
  _WORD v28[1024]; // [rsp+90h] [rbp-848h] BYREF

  v25 = a3;
  *a3 = 0;
  SizePointer = 0;
  *a4 = 0;
  memset(v26, 0, sizeof(v26));
  if ( a2 != 1
    && gIsRtrMgrEtwEnabled
    && (RoutingDomainIdForCompartment = NsiGetRoutingDomainIdForCompartment(a2, v26),
        (AdaptersAddresses = RoutingDomainIdForCompartment) != 0) )
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v28[0] = 0;
      FormatRRASErrorString(
        v28,
        L"GetIpv6InfoForInterface: NsiGetRoutingDomainIdForCompartment failed and returned %d",
        RoutingDomainIdForCompartment);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, v28);
    }
  }
  else
  {
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v28[0] = 0;
      v27[0] = 0;
      FormatRRASErrorString(v28, L"GetIpv6InfoForInterface: Interface Index %d", a1);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)v28,
          (unsigned int)v26,
          0,
          (__int64)v27);
    }
    CurrentThreadCompartmentId = GetCurrentThreadCompartmentId();
    v9 = CurrentThreadCompartmentId;
    AdaptersAddresses = SetCurrentThreadCompartmentId(a2);
    if ( AdaptersAddresses )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
        return AdaptersAddresses;
      v28[0] = 0;
      v27[0] = 0;
      FormatRRASErrorString(
        v28,
        L"GetIpv6InfoForInterface: SetCurrentThreadCompartmentId failed and returned %d",
        AdaptersAddresses);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
        return AdaptersAddresses;
      McTemplateU0zjzz_EventWriteTransfer(
        (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (unsigned int)RasRtrmgrParamTraceInfo,
        (unsigned int)v28,
        (unsigned int)v26,
        0,
        (__int64)v27);
    }
    else
    {
      for ( i = -1; ; i = 0 )
      {
        AdaptersAddresses = GetAdaptersAddresses(0x17u, 0x2Eu, 0, 0, &SizePointer);
        if ( AdaptersAddresses != 111 )
          break;
        i = (__int64)LocalAlloc(0x40u, SizePointer);
        if ( !i )
        {
          AdaptersAddresses = GetLastError();
          v11 = Microsoft_Windows_RRASEnableBits;
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
            goto LABEL_23;
          v13 = L"Unable to allocate memory for the GetAdaptersAddresses buffer: %d";
          goto LABEL_21;
        }
        AdaptersAddresses = GetAdaptersAddresses(
                              AdaptersAddresses - 88,
                              0x2Eu,
                              0,
                              (PIP_ADAPTER_ADDRESSES)i,
                              &SizePointer);
        if ( AdaptersAddresses != 111 )
        {
          v11 = Microsoft_Windows_RRASEnableBits;
          v12 = i;
          goto LABEL_24;
        }
        LocalFree((HLOCAL)i);
        SizePointer = 0;
      }
      v11 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
        goto LABEL_23;
      v13 = L"GetAdaptersAddresses for getting interface index returns %d for querying the buffer size";
LABEL_21:
      v28[0] = 0;
      v27[0] = 0;
      FormatRRASErrorString(v28, v13, AdaptersAddresses);
      v11 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)v28,
          (unsigned int)v26,
          0,
          (__int64)v27);
        v11 = Microsoft_Windows_RRASEnableBits;
      }
LABEL_23:
      v12 = 0;
LABEL_24:
      if ( AdaptersAddresses )
      {
        if ( (v11 & 0x40) != 0 )
        {
          v28[0] = 0;
          v27[0] = 0;
          FormatRRASErrorString(
            v28,
            L"GetIpInfoForInterface: Error %d getting IP Address table from stack",
            AdaptersAddresses);
          if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
          {
            v14 = RasRtrMgrParamTraceError;
LABEL_28:
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (_DWORD)v14,
              (unsigned int)v28,
              (unsigned int)v26,
              0,
              (__int64)v27);
          }
        }
      }
      else
      {
        while ( v12 )
        {
          if ( *(_DWORD *)(v12 + 108) == a1 )
          {
            if ( *(_DWORD *)(v12 + 104) == 2 )
            {
              AdaptersAddresses = 232;
            }
            else
            {
              v15 = *(_QWORD *)(v12 + 24);
              v16 = 0;
              if ( !v15 )
                goto LABEL_48;
              do
              {
                v15 = *(_QWORD *)(v15 + 8);
                ++v16;
              }
              while ( v15 );
              if ( v16 )
              {
                AdaptersAddresses = 0;
                v17 = HeapAlloc(IPRouterHeap, 8u, 28LL * v16);
                *a4 = v17;
                if ( v17 )
                {
                  v18 = *(_QWORD *)(v12 + 24);
                  v19 = 0;
                  v20 = 0;
                  do
                  {
                    ++v19;
                    v21 = 28 * v20++;
                    *(_OWORD *)(v21 + *a4 + 4) = *(_OWORD *)(*(_QWORD *)(v18 + 16) + 8LL);
                    *(_DWORD *)(v21 + *a4) = 128;
                    *(_DWORD *)(v21 + *a4 + 24) = 1;
                    v18 = *(_QWORD *)(v18 + 8);
                  }
                  while ( v19 < v16 );
                  *v25 = v16;
                }
                else if ( (Microsoft_Windows_RRASEnableBits & 0x40) != 0 )
                {
                  v27[0] = 0;
                  McTemplateU0zjzz_EventWriteTransfer(
                    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    (unsigned int)RasRtrMgrParamTraceError,
                    (unsigned int)L"GetIpv6InfoForInterface: Error allocating memory",
                    (unsigned int)v26,
                    0,
                    (__int64)v27);
                }
              }
              else
              {
LABEL_48:
                if ( v11 < 0 )
                {
                  v27[0] = 0;
                  McTemplateU0zjzz_EventWriteTransfer(
                    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    (unsigned int)RasRtrmgrParamTraceInfo,
                    (unsigned int)L"GetIpv6InfoForInterface: Number of unicast addresses is zero",
                    (unsigned int)v26,
                    0,
                    (__int64)v27);
                }
                AdaptersAddresses = 232;
              }
              v9 = CurrentThreadCompartmentId;
            }
            goto LABEL_41;
          }
          v12 = *(_QWORD *)(v12 + 8);
        }
        AdaptersAddresses = 232;
        if ( v11 < 0 )
        {
          v28[0] = 0;
          v27[0] = 0;
          FormatRRASErrorString(v28, L"The interface index %d is NOT in the adapter list", a1);
          if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
          {
            v14 = RasRtrmgrParamTraceInfo;
            goto LABEL_28;
          }
        }
      }
LABEL_41:
      if ( (unsigned __int64)(i - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        LocalFree((HLOCAL)i);
      SetCurrentThreadCompartmentId(v9);
    }
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v28[0] = 0;
      v27[0] = 0;
      FormatRRASErrorString(v28, L"GetIpv6InfoForInterface: Interface Index %d. Return %d", a1, AdaptersAddresses);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasRtrmgrParamTraceInfo,
          (unsigned int)v28,
          (unsigned int)v26,
          0,
          (__int64)v27);
    }
  }
  return AdaptersAddresses;
}

```

## disassembly

```asm
0x180018530  push    rbx
0x180018532  push    rsi
0x180018533  push    rdi
0x180018534  push    r12
0x180018536  push    r13
0x180018538  push    r14
0x18001853a  push    r15
0x18001853c  sub     rsp, 8A0h
0x180018543  mov     rax, cs:__security_cookie
0x18001854a  xor     rax, rsp
0x18001854d  mov     [rsp+8D8h+var_48], rax
0x180018555  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18001855c  xor     r14d, r14d
0x18001855f  mov     [rsp+8D8h+var_8A0], r8
0x180018564  mov     [r8], r14d
0x180018567  mov     r13, r9
0x18001856a  mov     [rsp+8D8h+var_8A8], r14d
0x18001856f  mov     edi, edx
0x180018571  mov     [r9], r14
0x180018574  mov     r12d, ecx
0x180018577  movdqu  [rsp+8D8h+var_898], xmm0
0x18001857d  xorps   xmm0, xmm0
0x180018580  movups  [rsp+8D8h+var_888], xmm0
0x180018585  cmp     edx, 1
0x180018588  jz      short loc_1800185FF
0x18001858a  cmp     cs:gIsRtrMgrEtwEnabled, r14d
0x180018591  jz      short loc_1800185FF
0x180018593  lea     rdx, [rsp+8D8h+var_898]
0x180018598  mov     ecx, edi
0x18001859a  call    NsiGetRoutingDomainIdForCompartment
0x18001859f  mov     ebx, eax
0x1800185a1  test    eax, eax
0x1800185a3  jz      short loc_1800185FF
0x1800185a5  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x1800185ac  jge     loc_180018A97
0x1800185b2  mov     r8d, eax
0x1800185b5  mov     [rsp+8D8h+var_848], r14w
0x1800185be  lea     rdx, aGetipv6infofor; "GetIpv6InfoForInterface: NsiGetRoutingD"...
0x1800185c5  lea     rcx, [rsp+8D8h+var_848]
0x1800185cd  call    FormatRRASErrorString
0x1800185d2  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x1800185d9  jge     loc_180018A97
0x1800185df  lea     r8, [rsp+8D8h+var_848]
0x1800185e7  lea     rdx, RasRtrmgrTraceInfo
0x1800185ee  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800185f5  call    McTemplateU0z_EventWriteTransfer
0x1800185fa  jmp     loc_180018A97
0x1800185ff  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x180018606  lea     rsi, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001860d  jge     short loc_180018669
0x18001860f  mov     r8d, r12d
0x180018612  mov     [rsp+8D8h+var_848], r14w
0x18001861b  lea     rdx, aGetipv6infofor_1; "GetIpv6InfoForInterface: Interface Inde"...
0x180018622  mov     [rsp+8D8h+var_878], r14w
0x180018628  lea     rcx, [rsp+8D8h+var_848]
0x180018630  call    FormatRRASErrorString
0x180018635  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r14b
0x18001863c  jge     short loc_180018669
0x18001863e  lea     rax, [rsp+8D8h+var_878]
0x180018643  mov     rcx, rsi
0x180018646  mov     [rsp+8D8h+var_8B0], rax
0x18001864b  lea     r9, [rsp+8D8h+var_898]
0x180018650  lea     r8, [rsp+8D8h+var_848]
0x180018658  mov     [rsp+8D8h+SizePointer], r14
0x18001865d  lea     rdx, RasRtrmgrParamTraceInfo
0x180018664  call    McTemplateU0zjzz_EventWriteTransfer
0x180018669  call    cs:__imp_GetCurrentThreadCompartmentId
0x18001866f  mov     ecx, edi; CompartmentId
0x180018671  mov     [rsp+8D8h+var_8A4], eax
0x180018675  mov     r14d, eax
0x180018678  call    cs:__imp_SetCurrentThreadCompartmentId
0x18001867e  mov     ebx, eax
0x180018680  test    eax, eax
0x180018682  jnz     loc_1800189BE
0x180018688  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001868c  lea     edi, [rax+2Eh]
0x18001868f  xor     r9d, r9d; AdapterAddresses
0x180018692  lea     rax, [rsp+8D8h+var_8A8]
0x180018697  xor     r8d, r8d; Reserved
0x18001869a  mov     [rsp+8D8h+SizePointer], rax; SizePointer
0x18001869f  mov     edx, edi; Flags
0x1800186a1  lea     ecx, [r9+17h]; Family
0x1800186a5  call    cs:__imp_GetAdaptersAddresses
0x1800186ab  mov     ebx, eax
0x1800186ad  cmp     eax, 6Fh ; 'o'
0x1800186b0  jnz     short loc_18001872A
0x1800186b2  mov     edx, [rsp+8D8h+var_8A8]; uBytes
0x1800186b6  lea     ecx, [rax-2Fh]; uFlags
0x1800186b9  call    cs:__imp_LocalAlloc
0x1800186bf  mov     r15, rax
0x1800186c2  test    rax, rax
0x1800186c5  jz      short loc_18001870E
0x1800186c7  lea     rax, [rsp+8D8h+var_8A8]
0x1800186cc  mov     r9, r15; AdapterAddresses
0x1800186cf  xor     r8d, r8d; Reserved
0x1800186d2  mov     [rsp+8D8h+SizePointer], rax; SizePointer
0x1800186d7  mov     edx, edi; Flags
0x1800186d9  lea     ecx, [rbx-58h]; Family
0x1800186dc  call    cs:__imp_GetAdaptersAddresses
0x1800186e2  mov     ebx, eax
0x1800186e4  cmp     eax, 6Fh ; 'o'
0x1800186e7  jnz     short loc_1800186FF
0x1800186e9  mov     rcx, r15; hMem
0x1800186ec  call    cs:__imp_LocalFree
0x1800186f2  xor     r15d, r15d
0x1800186f5  mov     [rsp+8D8h+var_8A8], 0
0x1800186fd  jmp     short loc_18001868F
0x1800186ff  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180018706  mov     rdi, r15
0x180018709  jmp     loc_18001879E
0x18001870e  call    cs:__imp_GetLastError
0x180018714  mov     ebx, eax
0x180018716  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18001871d  test    al, al
0x18001871f  jns     short loc_18001879C
0x180018721  lea     rdx, aUnableToAlloca; "Unable to allocate memory for the GetAd"...
0x180018728  jmp     short loc_18001873C
0x18001872a  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180018731  test    al, al
0x180018733  jns     short loc_18001879C
0x180018735  lea     rdx, aGetadaptersadd_0; "GetAdaptersAddresses for getting interf"...
0x18001873c  xor     eax, eax
0x18001873e  lea     rcx, [rsp+8D8h+var_848]
0x180018746  mov     r8d, ebx
0x180018749  mov     [rsp+8D8h+var_848], ax
0x180018751  mov     [rsp+8D8h+var_878], ax
0x180018756  call    FormatRRASErrorString
0x18001875b  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x180018762  test    al, al
0x180018764  jns     short loc_18001879C
0x180018766  lea     rax, [rsp+8D8h+var_878]
0x18001876b  mov     rcx, rsi
0x18001876e  mov     [rsp+8D8h+var_8B0], rax
0x180018773  lea     r9, [rsp+8D8h+var_898]
0x180018778  lea     r8, [rsp+8D8h+var_848]
0x180018780  mov     [rsp+8D8h+SizePointer], 0
0x180018789  lea     rdx, RasRtrmgrParamTraceInfo
0x180018790  call    McTemplateU0zjzz_EventWriteTransfer
0x180018795  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18001879c  xor     edi, edi
0x18001879e  test    ebx, ebx
0x1800187a0  jz      short loc_180018811
0x1800187a2  test    al, 40h
0x1800187a4  jz      loc_1800188BA
0x1800187aa  xor     eax, eax
0x1800187ac  lea     rdx, aGetipinfoforin_3; "GetIpInfoForInterface: Error %d getting"...
0x1800187b3  mov     r8d, ebx
0x1800187b6  mov     [rsp+8D8h+var_848], ax
0x1800187be  lea     rcx, [rsp+8D8h+var_848]
0x1800187c6  mov     [rsp+8D8h+var_878], ax
0x1800187cb  call    FormatRRASErrorString
0x1800187d0  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x1800187d7  jz      loc_1800188BA
0x1800187dd  lea     rdx, RasRtrMgrParamTraceError
0x1800187e4  lea     rax, [rsp+8D8h+var_878]
0x1800187e9  mov     rcx, rsi
0x1800187ec  mov     [rsp+8D8h+var_8B0], rax
0x1800187f1  lea     r8, [rsp+8D8h+var_848]
0x1800187f9  lea     r9, [rsp+8D8h+var_898]
0x1800187fe  mov     [rsp+8D8h+SizePointer], 0
0x180018807  call    McTemplateU0zjzz_EventWriteTransfer
0x18001880c  jmp     loc_1800188BA
0x180018811  test    rdi, rdi
0x180018814  jz      loc_180018972
0x18001881a  cmp     [rdi+6Ch], r12d
0x18001881e  jz      short loc_180018826
0x180018820  mov     rdi, [rdi+8]
0x180018824  jmp     short loc_180018811
0x180018826  cmp     dword ptr [rdi+68h], 2
0x18001882a  jnz     short loc_180018836
0x18001882c  mov     ebx, 0E8h
0x180018831  jmp     loc_1800188BA
0x180018836  mov     rcx, [rdi+18h]
0x18001883a  xor     r14d, r14d
0x18001883d  test    rcx, rcx
0x180018840  jz      loc_18001892F
0x180018846  mov     rcx, [rcx+8]
0x18001884a  inc     r14d
0x18001884d  test    rcx, rcx
0x180018850  jnz     short loc_180018846
0x180018852  test    r14d, r14d
0x180018855  jz      loc_18001892F
0x18001885b  mov     eax, r14d
0x18001885e  lea     edx, [rcx+8]; dwFlags
0x180018861  mov     rcx, cs:IPRouterHeap; hHeap
0x180018868  xor     ebx, ebx
0x18001886a  imul    r8, rax, 1Ch; dwBytes
0x18001886e  call    cs:__imp_HeapAlloc
0x180018874  mov     [r13+0], rax
0x180018878  test    rax, rax
0x18001887b  jnz     short loc_1800188DB
0x18001887d  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 40h
0x180018884  jz      short loc_1800188B5
0x180018886  mov     [rsp+8D8h+var_878], ax
0x18001888b  lea     r9, [rsp+8D8h+var_898]
0x180018890  lea     rax, [rsp+8D8h+var_878]
0x180018895  mov     rcx, rsi
0x180018898  mov     [rsp+8D8h+var_8B0], rax
0x18001889d  lea     r8, aGetipv6infofor_4; "GetIpv6InfoForInterface: Error allocati"...
0x1800188a4  lea     rdx, RasRtrMgrParamTraceError
0x1800188ab  mov     [rsp+8D8h+SizePointer], rbx
0x1800188b0  call    McTemplateU0zjzz_EventWriteTransfer
0x1800188b5  mov     r14d, [rsp+8D8h+var_8A4]
0x1800188ba  lea     rax, [r15-1]
0x1800188be  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800188c2  ja      short loc_1800188CD
0x1800188c4  mov     rcx, r15; hMem
0x1800188c7  call    cs:__imp_LocalFree
0x1800188cd  mov     ecx, r14d; CompartmentId
0x1800188d0  call    cs:__imp_SetCurrentThreadCompartmentId
0x1800188d6  jmp     loc_180018A2D
0x1800188db  mov     r8, [rdi+18h]
0x1800188df  xor     r9d, r9d
0x1800188e2  test    r14d, r14d
0x1800188e5  jz      short loc_180018925
0x1800188e7  xor     edx, edx
0x1800188e9  mov     rax, [r8+10h]
0x1800188ed  inc     r9d
0x1800188f0  imul    rcx, rdx, 1Ch
0x1800188f4  movups  xmm0, xmmword ptr [rax+8]
0x1800188f8  mov     rax, [r13+0]
0x1800188fc  inc     rdx
0x1800188ff  movdqu  xmmword ptr [rcx+rax+4], xmm0
0x180018905  mov     rax, [r13+0]
0x180018909  mov     dword ptr [rcx+rax], 80h
0x180018910  mov     rax, [r13+0]
0x180018914  mov     dword ptr [rcx+rax+18h], 1
0x18001891c  mov     r8, [r8+8]
0x180018920  cmp     r9d, r14d
0x180018923  jb      short loc_1800188E9
0x180018925  mov     rax, [rsp+8D8h+var_8A0]
0x18001892a  mov     [rax], r14d
0x18001892d  jmp     short loc_1800188B5
0x18001892f  test    al, 80h
0x180018931  jz      short loc_180018968
0x180018933  xor     eax, eax
0x180018935  lea     r9, [rsp+8D8h+var_898]
0x18001893a  mov     [rsp+8D8h+var_878], ax
0x18001893f  lea     r8, aGetipv6infofor_0; "GetIpv6InfoForInterface: Number of unic"...
0x180018946  lea     rax, [rsp+8D8h+var_878]
0x18001894b  mov     rcx, rsi
0x18001894e  mov     [rsp+8D8h+var_8B0], rax
0x180018953  lea     rdx, RasRtrmgrParamTraceInfo
0x18001895a  mov     [rsp+8D8h+SizePointer], 0
0x180018963  call    McTemplateU0zjzz_EventWriteTransfer
0x180018968  mov     ebx, 0E8h
0x18001896d  jmp     loc_1800188B5
0x180018972  mov     ebx, 0E8h
0x180018977  test    al, al
0x180018979  jns     loc_1800188BA
0x18001897f  xor     eax, eax
0x180018981  lea     rdx, aTheInterfaceIn; "The interface index %d is NOT in the ad"...
0x180018988  mov     r8d, r12d
0x18001898b  mov     [rsp+8D8h+var_848], ax
0x180018993  lea     rcx, [rsp+8D8h+var_848]
0x18001899b  mov     [rsp+8D8h+var_878], ax
0x1800189a0  call    FormatRRASErrorString
0x1800189a5  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800189ac  jge     loc_1800188BA
0x1800189b2  lea     rdx, RasRtrmgrParamTraceInfo
0x1800189b9  jmp     loc_1800187E4
0x1800189be  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800189c5  jge     loc_180018A97
0x1800189cb  xor     eax, eax
0x1800189cd  lea     rdx, aGetipv6infofor_2; "GetIpv6InfoForInterface: SetCurrentThre"...
0x1800189d4  mov     r8d, ebx
0x1800189d7  mov     [rsp+8D8h+var_848], ax
0x1800189df  lea     rcx, [rsp+8D8h+var_848]
0x1800189e7  mov     [rsp+8D8h+var_878], ax
0x1800189ec  call    FormatRRASErrorString
0x1800189f1  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x1800189f8  jge     loc_180018A97
0x1800189fe  lea     rax, [rsp+8D8h+var_878]
0x180018a03  mov     rcx, rsi
0x180018a06  mov     [rsp+8D8h+var_8B0], rax
0x180018a0b  lea     r9, [rsp+8D8h+var_898]
0x180018a10  lea     r8, [rsp+8D8h+var_848]
0x180018a18  mov     [rsp+8D8h+SizePointer], 0
0x180018a21  lea     rdx, RasRtrmgrParamTraceInfo
0x180018a28  call    McTemplateU0zjzz_EventWriteTransfer
0x180018a2d  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180018a34  jge     short loc_180018A97
0x180018a36  xor     eax, eax
0x180018a38  lea     rdx, aGetipv6infofor_3; "GetIpv6InfoForInterface: Interface Inde"...
0x180018a3f  mov     r9d, ebx
0x180018a42  mov     [rsp+8D8h+var_848], ax
0x180018a4a  mov     r8d, r12d
0x180018a4d  mov     [rsp+8D8h+var_878], ax
0x180018a52  lea     rcx, [rsp+8D8h+var_848]
0x180018a5a  call    FormatRRASErrorString
0x180018a5f  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, 0
0x180018a66  jge     short loc_180018A97
0x180018a68  lea     rax, [rsp+8D8h+var_878]
0x180018a6d  mov     rcx, rsi
0x180018a70  mov     [rsp+8D8h+var_8B0], rax
0x180018a75  lea     r9, [rsp+8D8h+var_898]
0x180018a7a  lea     r8, [rsp+8D8h+var_848]
0x180018a82  mov     [rsp+8D8h+SizePointer], 0
0x180018a8b  lea     rdx, RasRtrmgrParamTraceInfo
0x180018a92  call    McTemplateU0zjzz_EventWriteTransfer
  ... truncated ...
```
