# NdisReadConfiguration

- ea: `0x14004dd60`
- end: `0x14004e36e`
- name: `NdisReadConfiguration`
- size: `1550`
- prototype: `void __stdcall(PNDIS_STATUS Status, PNDIS_CONFIGURATION_PARAMETER *ParameterValue, NDIS_HANDLE ConfigurationHandle, PNDIS_STRING Keyword, NDIS_PARAMETER_TYPE ParameterType)`
- caller_count: `23`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14004bd50`
- `0x14004bdb0`
- `0x14004be80`
- `0x14004bfd0`
- `0x14004c580`
- `0x14004cdf0`
- `0x14004ce90`
- `0x14004d200`
- `0x14004d400`
- `0x14007d1e0`
- `0x14008b4d0`
- `0x1400a1424`
- `0x1400b0c50`
- `0x1400c3bb0`
- `0x1400e1688`
- `0x1401434f0`
- `0x14014c4e0`
- `0x14014c5e0`
- `0x14016cef0`
- `0x14016d8f0`
- `0x140171c70`
- `0x1401941b4`
- `0x140194424`

## callees

- `0x14002ab60`
- `0x14004dd60`
- `0x1400521b0`
- `0x140059c80`
- `0x140065540`
- `0x14006cf50`
- `0x1400eb380`
- `0x1400eb4c0`
- `0x14014b878`
- `0x14014bc68`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x14004de14`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004dec9`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004deea`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004df29`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004df51`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004df72`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004df93`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004e0c1`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004e168`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004de14`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004dec9`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004deea`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004df29`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004df51`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004df72`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004df93`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004e0c1`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004e168`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x1400f06ff`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x1400f06ff`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14004e041`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14004e041`
- `ntoskrnl!RtlUnicodeStringToInteger` at `0x14004e082`
- `ntoskrnl!RtlUnicodeStringToInteger` at `0x14004e354`
- `ntoskrnl!RtlUnicodeStringToInteger` at `0x14004e082`
- `ntoskrnl!RtlUnicodeStringToInteger` at `0x14004e354`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004de65`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f087d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004de65`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400f087d`
- `ntoskrnl!ExAllocatePool2` at `0x14004dfde`
- `ntoskrnl!ExAllocatePool2` at `0x14004e1a5`
- `ntoskrnl!ExAllocatePool2` at `0x14004dfde`
- `ntoskrnl!ExAllocatePool2` at `0x14004e1a5`

## pseudocode

```c
void __stdcall NdisReadConfiguration(
        PNDIS_STATUS Status,
        PNDIS_CONFIGURATION_PARAMETER *ParameterValue,
        NDIS_HANDLE ConfigurationHandle,
        PNDIS_STRING Keyword,
        NDIS_PARAMETER_TYPE ParameterType)
{
  _QWORD *v6; // r15
  PNDIS_STATUS v7; // r14
  wchar_t *Buffer; // r12
  unsigned int i; // ebx
  __int64 v10; // rdx
  __int64 v11; // rax
  int RegistryValues; // ebx
  __int64 v13; // r13
  unsigned int j; // ebx
  __int64 v15; // rdi
  __int64 v16; // r14
  wchar_t *v17; // rax
  PNDIS_CONFIGURATION_PARAMETER *v18; // rdi
  _DWORD *v19; // rcx
  size_t v20; // rbx
  const void *v21; // r14
  __int64 Pool2; // rax
  _QWORD *v23; // rdi
  struct _NDIS_CONFIGURATION_PARAMETER *v24; // rax
  __int64 v25; // rax
  unsigned int v26; // r8d
  __int64 k; // r13
  int v28; // eax
  bool v29; // zf
  __int64 v30; // rdx
  int v31; // eax
  int v32; // eax
  _BYTE *v33; // rcx
  PVOID v34; // rdi
  PNDIS_CONFIGURATION_PARAMETER *v35; // [rsp+28h] [rbp-79h]
  PNDIS_CONFIGURATION_PARAMETER *v36; // [rsp+30h] [rbp-71h]
  int v37; // [rsp+38h] [rbp-69h] BYREF
  PNDIS_STATUS v38; // [rsp+40h] [rbp-61h]
  _DWORD v39[2]; // [rsp+48h] [rbp-59h]
  char v40; // [rsp+50h] [rbp-51h]
  unsigned int v41[2]; // [rsp+58h] [rbp-49h] BYREF
  void *v42; // [rsp+60h] [rbp-41h]
  struct _UNICODE_STRING String; // [rsp+68h] [rbp-39h] BYREF
  PVOID P; // [rsp+78h] [rbp-29h] BYREF
  _OWORD v45[2]; // [rsp+80h] [rbp-21h] BYREF
  __int64 v46; // [rsp+A0h] [rbp-1h]

  v42 = ConfigurationHandle;
  v36 = ParameterValue;
  v38 = Status;
  v46 = 0;
  v37 = 0;
  v6 = ConfigurationHandle;
  P = 0;
  v7 = Status;
  v41[0] = 0;
  String = 0;
  v39[0] = 67305985;
  memset(v45, 0, sizeof(v45));
  v39[1] = 33620481;
  v40 = 3;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(ParameterValue) = 4;
    WPP_RECORDER_SF_Z(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      (int)ParameterValue,
      8,
      30,
      (struct _GUID *)&WPP_78fc2fada0c137ca2e9d99d042b3d7f2_Traceguids,
      (__int64)Keyword);
  }
  Buffer = Keyword->Buffer;
  for ( i = 0; i < 3; ++i )
  {
    if ( RtlEqualUnicodeString(Keyword, (PCUNICODE_STRING)&qword_1400F6DF8[2 * i], 1u) )
    {
      v11 = 24LL * i + 1038464;
      RegistryValues = 0;
      *v36 = (PNDIS_CONFIGURATION_PARAMETER)(0x140000000LL + v11);
      goto LABEL_8;
    }
  }
  v13 = *(_QWORD *)(v6[2] + 8LL);
  if ( !v13 )
    goto LABEL_23;
  if ( RtlEqualUnicodeString(Keyword, &String2, 1u) )
  {
    v20 = *(unsigned __int16 *)(v13 + 3808);
    v21 = *(const void **)(v13 + 3816);
    Pool2 = ExAllocatePool2(64, (unsigned int)(v20 + 32), 1852851278);
    v23 = (_QWORD *)Pool2;
    if ( Pool2 )
    {
      v24 = (struct _NDIS_CONFIGURATION_PARAMETER *)(Pool2 + 8);
      *v36 = v24;
      v24->ParameterType = NdisParameterString;
      (*v36)->ParameterData.StringData.Buffer = (wchar_t *)(v23 + 4);
      memmove((*v36)->ParameterData.StringData.Buffer, v21, v20);
      (*v36)->ParameterData.StringData.Length = v20;
      (*v36)->ParameterData.StringData.MaximumLength = v20;
      if ( !*((_BYTE *)v21 + (unsigned int)(v20 - 1)) && !*((_BYTE *)v21 + (unsigned int)(v20 - 2)) )
        (*v36)->ParameterData.StringData.Length -= 2;
      RegistryValues = 0;
      v7 = v38;
      *v23 = v6[3];
      v6[3] = v23;
    }
    else
    {
      RegistryValues = -1073741670;
LABEL_46:
      v7 = v38;
    }
LABEL_8:
    if ( Buffer && Buffer != Keyword->Buffer )
      ExFreePoolWithTag(Buffer, 0);
    goto LABEL_11;
  }
  if ( RtlEqualUnicodeString(Keyword, &stru_1400F6E58, 1u) && (*(_DWORD *)(v6[2] + 16LL) & 1) == 0 )
  {
    if ( (unsigned int)ParameterType <= NdisParameterHexInteger )
    {
      RegistryValues = ndisSaveParameters((wchar_t *)L"BusType", 4u, (void *)(v13 + 3720), 4u, v6, v36);
      goto LABEL_8;
    }
    if ( ParameterType == NdisParameterString )
    {
      *(_DWORD *)&String.Length = 2621440;
      String.Buffer = (wchar_t *)v45;
      RegistryValues = RtlIntegerToUnicodeString(*(_DWORD *)(v13 + 3720), 0xAu, &String);
      if ( !RegistryValues )
        RegistryValues = ndisSaveParameters((wchar_t *)L"BusType", 1u, String.Buffer, String.Length, v6, v36);
      goto LABEL_8;
    }
  }
  for ( j = 0; j < 9; ++j )
  {
    v15 = 2LL * j;
    v16 = j;
    if ( RtlEqualUnicodeString(Keyword, (PCUNICODE_STRING)&qword_1400F8440[v15], 1u) )
    {
      v25 = *(_QWORD *)(v13 + 944);
      RegistryValues = -1073741823;
      if ( !v25 )
        goto LABEL_46;
      v26 = *(_DWORD *)(v25 + 16);
      v10 = v25 + 12;
      *(_QWORD *)v41 = v25 + 12;
      for ( k = 0; (unsigned int)k < v26; k = (unsigned int)(k + 1) )
      {
        v28 = *((unsigned __int8 *)v39 + v16);
        v29 = *(_BYTE *)(v10 + 20 * k + 8) == (unsigned __int8)v28;
        v30 = v10 + 20 * k;
        if ( v29 )
        {
          if ( v28 == 1 )
            goto LABEL_72;
          if ( v28 == 2 )
          {
            v31 = *(unsigned __int16 *)(v30 + 12);
LABEL_73:
            v37 = v31;
          }
          else if ( (unsigned int)(v28 - 3) <= 1 )
          {
LABEL_72:
            v31 = *(_DWORD *)(v30 + 12);
            goto LABEL_73;
          }
          v32 = ndisSaveParameters((&off_1400F8448)[v15], 4u, &v37, 4u, v42, v36);
          v10 = *(_QWORD *)v41;
          RegistryValues = v32;
          break;
        }
        v10 = *(_QWORD *)v41;
      }
      v7 = v38;
      if ( (unsigned int)k >= *(_DWORD *)(v10 + 4) )
        RegistryValues = -1073741823;
      goto LABEL_8;
    }
  }
  if ( !RtlEqualUnicodeString(Keyword, &stru_1400F6E38, 1u) )
    goto LABEL_20;
  if ( ParameterType )
  {
LABEL_85:
    RegistryValues = -1073741823;
    goto LABEL_46;
  }
  if ( ndisNDKGlobalDisabled() )
  {
    RegistryValues = 0;
    *v36 = (PNDIS_CONFIGURATION_PARAMETER)qword_1400F9C68;
    goto LABEL_46;
  }
LABEL_20:
  if ( RtlEqualUnicodeString(Keyword, &stru_1400F6E48, 1u) )
  {
    if ( ParameterType == NdisParameterInteger )
    {
      RegistryValues = 0;
      dword_140122A68 = ndisReadNDKGlobalFlags();
      *v36 = (PNDIS_CONFIGURATION_PARAMETER)&qword_140122A60;
      goto LABEL_46;
    }
    goto LABEL_85;
  }
  v7 = v38;
  v6 = v42;
  if ( RtlEqualUnicodeString(Keyword, &::Keyword, 1u) )
  {
    *(_DWORD *)(v13 + 568) |= 0x80u;
    *(_DWORD *)(v13 + 1872) |= 0x10000u;
  }
LABEL_23:
  if ( !ndisAllowFlowControl && RtlEqualUnicodeString(Keyword, &FlowControlStr, 1u) )
  {
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 3;
      WPP_RECORDER_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v10,
        8,
        31,
        (struct _GUID *)&WPP_78fc2fada0c137ca2e9d99d042b3d7f2_Traceguids);
    }
    RegistryValues = 0;
    *v36 = (PNDIS_CONFIGURATION_PARAMETER)qword_1400F9C68;
    goto LABEL_8;
  }
  if ( (*(_DWORD *)(v6[2] + 16LL) & 2) != 0 && !v6[4] )
  {
    RegistryValues = ndisOpenProtocolSubkey((__int64)v6);
    if ( RegistryValues < 0 )
    {
      v18 = v36;
LABEL_27:
      if ( v13 )
      {
LABEL_28:
        if ( RegistryValues < 0 )
          goto LABEL_8;
      }
      else if ( RegistryValues < 0 )
      {
        if ( !RtlEqualUnicodeString(Keyword, &stru_1400F6E68, 1u) )
          goto LABEL_8;
        v33 = (_BYTE *)v6[1];
        if ( !v33 || *v33 != 2 || v33[24] < 6u || (unsigned int)ndisReadUpperBindings(v33, &P, v41) )
          goto LABEL_8;
        v35 = v18;
        v34 = P;
        RegistryValues = ndisSaveParameters((wchar_t *)L"UpperBindings", 7u, P, v41[0], v6, v35);
        if ( v34 )
          ExFreePoolWithTag(v34, 0);
        v18 = v36;
        goto LABEL_28;
      }
      v19 = *v18;
      if ( (*v18)->ParameterType == NdisParameterString )
      {
        if ( ParameterType )
        {
          if ( ParameterType == NdisParameterHexInteger )
          {
            RtlUnicodeStringToInteger((PCUNICODE_STRING)(v19 + 2), 0x10u, v19 + 2);
            (*v18)->ParameterType = NdisParameterHexInteger;
          }
        }
        else
        {
          RtlUnicodeStringToInteger((PCUNICODE_STRING)(v19 + 2), 0xAu, v19 + 2);
          (*v18)->ParameterType = NdisParameterInteger;
        }
      }
      goto LABEL_8;
    }
  }
  v17 = (wchar_t *)ExAllocatePool2(66, Keyword->Length + 2LL, 538985550);
  Buffer = v17;
  if ( v17 )
  {
    memmove(v17, Keyword->Buffer, Keyword->Length);
    v18 = v36;
    *(wchar_t *)((char *)Buffer + Keyword->Length) = 0;
    *(_QWORD *)(v6[2] + 40LL) = Buffer;
    *(_QWORD *)(v6[2] + 48LL) = v36;
    RegistryValues = RtlQueryRegistryValuesEx(0x40000000, v6[4], v6[2] + 24LL, v6, 0);
    goto LABEL_27;
  }
  RegistryValues = -1073741670;
LABEL_11:
  *v7 = (RegistryValues >> 31) & 0xC0000001;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v10) = 4;
    WPP_RECORDER_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v10,
      8,
      32,
      (struct _GUID *)&WPP_78fc2fada0c137ca2e9d99d042b3d7f2_Traceguids);
  }
}

```

## disassembly

```asm
0x14004dd60  push    rbp
0x14004dd62  push    rbx
0x14004dd63  push    rsi
0x14004dd64  push    rdi
0x14004dd65  push    r12
0x14004dd67  push    r13
0x14004dd69  push    r14
0x14004dd6b  push    r15
0x14004dd6d  lea     rbp, [rsp-17h]
0x14004dd72  sub     rsp, 0B8h
0x14004dd79  mov     rax, cs:__security_cookie
0x14004dd80  xor     rax, rsp
0x14004dd83  mov     [rbp+4Fh+var_48], rax
0x14004dd87  xor     edi, edi
0x14004dd89  mov     [rbp+4Fh+var_90], r8
0x14004dd8d  xorps   xmm1, xmm1
0x14004dd90  mov     [rbp+4Fh+var_C0], rdx
0x14004dd94  xor     eax, eax
0x14004dd96  mov     [rbp+4Fh+var_B0], rcx
0x14004dd9a  xorps   xmm0, xmm0
0x14004dd9d  mov     [rbp+4Fh+var_50], rax
0x14004dda1  mov     rsi, r9
0x14004dda4  mov     [rbp+4Fh+var_B8], edi
0x14004dda7  mov     r15, r8
0x14004ddaa  mov     [rbp+4Fh+P], rdi
0x14004ddae  mov     r14, rcx
0x14004ddb1  mov     [rbp+4Fh+var_98], edi
0x14004ddb4  movups  xmmword ptr [rbp+4Fh+String.Length], xmm0
0x14004ddb8  mov     [rbp+4Fh+var_A8], 4030201h
0x14004ddbf  movups  [rbp+4Fh+var_70], xmm1
0x14004ddc3  mov     [rbp+4Fh+var_A4], 2010201h
0x14004ddca  movups  [rbp+4Fh+var_60], xmm1
0x14004ddce  mov     [rbp+4Fh+var_A0], 3
0x14004ddd2  lea     rax, WPP_RECORDER_INITIALIZED
0x14004ddd9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004dde0  lea     rcx, WPP_78fc2fada0c137ca2e9d99d042b3d7f2_Traceguids
0x14004dde7  jnz     loc_14004E24D
0x14004dded  mov     r12, [rsi+8]
0x14004ddf1  lea     r13, qword_1400F6DF8
0x14004ddf8  mov     ebx, edi
0x14004ddfa  cmp     ebx, 3
0x14004ddfd  jnb     loc_14004DEAB
0x14004de03  mov     edx, ebx
0x14004de05  mov     r8b, 1; CaseInSensitive
0x14004de08  shl     rdx, 4
0x14004de0c  mov     rcx, rsi; String1
0x14004de0f  add     rdx, r13; String2
0x14004de12  mov     edi, ebx
0x14004de14  call    cs:__imp_RtlEqualUnicodeString
0x14004de1b  nop     dword ptr [rax+rax+00h]
0x14004de20  test    al, al
0x14004de22  jnz     short loc_14004DE28
0x14004de24  inc     ebx
0x14004de26  jmp     short loc_14004DDFA
0x14004de28  mov     rcx, [rbp+4Fh+var_C0]
0x14004de2c  lea     rax, [rdi+rdi*2]
0x14004de30  lea     rax, ds:0FD880h[rax*8]
0x14004de38  xor     ebx, ebx
0x14004de3a  lea     r15, cs:140000000h
0x14004de41  add     rax, r15
0x14004de44  mov     [rcx], rax
0x14004de47  lea     rdi, WPP_RECORDER_INITIALIZED
0x14004de4e  lea     r15, WPP_78fc2fada0c137ca2e9d99d042b3d7f2_Traceguids
0x14004de55  test    r12, r12
0x14004de58  jz      short loc_14004DE71
0x14004de5a  cmp     r12, [rsi+8]
0x14004de5e  jz      short loc_14004DE71
0x14004de60  xor     edx, edx; Tag
0x14004de62  mov     rcx, r12; P
0x14004de65  call    cs:__imp_ExFreePoolWithTag
0x14004de6c  nop     dword ptr [rax+rax+00h]
0x14004de71  sar     ebx, 1Fh
0x14004de74  and     ebx, 0C0000001h
0x14004de7a  mov     [r14], ebx
0x14004de7d  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14004de84  jnz     loc_14004E12B
0x14004de8a  mov     rcx, [rbp+4Fh+var_48]
0x14004de8e  xor     rcx, rsp; StackCookie
0x14004de91  call    __security_check_cookie
0x14004de96  add     rsp, 0B8h
0x14004de9d  pop     r15
0x14004de9f  pop     r14
0x14004dea1  pop     r13
0x14004dea3  pop     r12
0x14004dea5  pop     rdi
0x14004dea6  pop     rsi
0x14004dea7  pop     rbx
0x14004dea8  pop     rbp
0x14004dea9  retn
0x14004deab  mov     rax, [r15+10h]
0x14004deaf  mov     r13, [rax+8]
0x14004deb3  test    r13, r13
0x14004deb6  jz      loc_14004DFAF
0x14004debc  mov     r8b, 1; CaseInSensitive
0x14004debf  lea     rdx, String2; String2
0x14004dec6  mov     rcx, rsi; String1
0x14004dec9  call    cs:__imp_RtlEqualUnicodeString
0x14004ded0  nop     dword ptr [rax+rax+00h]
0x14004ded5  test    al, al
0x14004ded7  jnz     loc_14004E181
0x14004dedd  mov     r8b, 1; CaseInSensitive
0x14004dee0  lea     rdx, stru_1400F6E58; String2
0x14004dee7  mov     rcx, rsi; String1
0x14004deea  call    cs:__imp_RtlEqualUnicodeString
0x14004def1  nop     dword ptr [rax+rax+00h]
0x14004def6  test    al, al
0x14004def8  jnz     loc_1400F06C0
0x14004defe  xor     ebx, ebx
0x14004df00  lea     r15, cs:140000000h
0x14004df07  nop     word ptr [rax+rax+00000000h]
0x14004df10  mov     edi, ebx
0x14004df12  lea     rdx, rva qword_1400F8440[r15]
0x14004df19  shl     rdi, 4
0x14004df1d  mov     r8b, 1; CaseInSensitive
0x14004df20  add     rdx, rdi; String2
0x14004df23  mov     r14d, ebx
0x14004df26  mov     rcx, rsi; String1
0x14004df29  call    cs:__imp_RtlEqualUnicodeString
0x14004df30  nop     dword ptr [rax+rax+00h]
0x14004df35  test    al, al
0x14004df37  jnz     loc_14004E2E9
0x14004df3d  inc     ebx
0x14004df3f  cmp     ebx, 9
0x14004df42  jb      short loc_14004DF10
0x14004df44  mov     r8b, 1; CaseInSensitive
0x14004df47  lea     rdx, stru_1400F6E38; String2
0x14004df4e  mov     rcx, rsi; String1
0x14004df51  call    cs:__imp_RtlEqualUnicodeString
0x14004df58  nop     dword ptr [rax+rax+00h]
0x14004df5d  test    al, al
0x14004df5f  jnz     loc_14004E293
0x14004df65  mov     r8b, 1; CaseInSensitive
0x14004df68  lea     rdx, stru_1400F6E48; String2
0x14004df6f  mov     rcx, rsi; String1
0x14004df72  call    cs:__imp_RtlEqualUnicodeString
0x14004df79  nop     dword ptr [rax+rax+00h]
0x14004df7e  test    al, al
0x14004df80  jnz     loc_14004E2BF
0x14004df86  mov     r8b, 1; CaseInSensitive
0x14004df89  lea     rdx, Keyword; String2
0x14004df90  mov     rcx, rsi; String1
0x14004df93  call    cs:__imp_RtlEqualUnicodeString
0x14004df9a  nop     dword ptr [rax+rax+00h]
0x14004df9f  mov     r14, [rbp+4Fh+var_B0]
0x14004dfa3  mov     r15, [rbp+4Fh+var_90]
0x14004dfa7  test    al, al
0x14004dfa9  jnz     loc_14004E1C7
0x14004dfaf  cmp     cs:?ndisAllowFlowControl@@3EA, 0; uchar ndisAllowFlowControl
0x14004dfb6  jz      loc_14004E0B4
0x14004dfbc  mov     rax, [r15+10h]
0x14004dfc0  mov     ecx, [rax+10h]
0x14004dfc3  test    cl, 2
0x14004dfc6  jnz     loc_14004E105
0x14004dfcc  movzx   edx, word ptr [rsi]
0x14004dfcf  mov     ecx, 42h ; 'B'
0x14004dfd4  add     rdx, 2
0x14004dfd8  mov     r8d, 2020444Eh
0x14004dfde  call    cs:__imp_ExAllocatePool2
0x14004dfe5  nop     dword ptr [rax+rax+00h]
0x14004dfea  mov     r12, rax
0x14004dfed  test    rax, rax
0x14004dff0  jz      loc_14004E09C
0x14004dff6  movzx   r8d, word ptr [rsi]; Size
0x14004dffa  mov     rcx, rax; void *
0x14004dffd  mov     rdx, [rsi+8]; Src
0x14004e001  call    memmove
0x14004e006  movzx   ecx, word ptr [rsi]
0x14004e009  xor     eax, eax
0x14004e00b  mov     rdi, [rbp+4Fh+var_C0]
0x14004e00f  mov     r9, r15
0x14004e012  mov     [rsp+0F0h+var_D0], 0
0x14004e01b  mov     [rcx+r12], ax
0x14004e020  mov     ecx, 40000000h
0x14004e025  mov     rax, [r15+10h]
0x14004e029  mov     [rax+28h], r12
0x14004e02d  mov     rax, [r15+10h]
0x14004e031  mov     [rax+30h], rdi
0x14004e035  mov     r8, [r15+10h]
0x14004e039  mov     rdx, [r15+20h]
0x14004e03d  add     r8, 18h
0x14004e041  call    cs:__imp_RtlQueryRegistryValuesEx
0x14004e048  nop     dword ptr [rax+rax+00h]
0x14004e04d  mov     ebx, eax
0x14004e04f  test    r13, r13
0x14004e052  jz      loc_14004E153
0x14004e058  test    ebx, ebx
0x14004e05a  js      loc_14004DE47
0x14004e060  mov     rcx, [rdi]
0x14004e063  cmp     dword ptr [rcx], 2
0x14004e066  jnz     loc_14004DE47
0x14004e06c  cmp     [rbp+4Fh+ParameterType], 0
0x14004e070  jnz     loc_14004E33E
0x14004e076  add     rcx, 8; String
0x14004e07a  mov     edx, 0Ah; Base
0x14004e07f  mov     r8, rcx; Value
0x14004e082  call    cs:__imp_RtlUnicodeStringToInteger
0x14004e089  nop     dword ptr [rax+rax+00h]
0x14004e08e  mov     rax, [rdi]
0x14004e091  mov     dword ptr [rax], 0
0x14004e097  jmp     loc_14004DE47
0x14004e09c  mov     ebx, 0C000009Ah
0x14004e0a1  lea     rdi, WPP_RECORDER_INITIALIZED
0x14004e0a8  lea     r15, WPP_78fc2fada0c137ca2e9d99d042b3d7f2_Traceguids
0x14004e0af  jmp     loc_14004DE71
0x14004e0b4  mov     r8b, 1; CaseInSensitive
0x14004e0b7  lea     rdx, ?FlowControlStr@@3U_UNICODE_STRING@@A; String2
0x14004e0be  mov     rcx, rsi; String1
0x14004e0c1  call    cs:__imp_RtlEqualUnicodeString
0x14004e0c8  nop     dword ptr [rax+rax+00h]
0x14004e0cd  test    al, al
0x14004e0cf  jz      loc_14004DFBC
0x14004e0d5  lea     rdi, WPP_RECORDER_INITIALIZED
0x14004e0dc  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14004e0e3  lea     r15, WPP_78fc2fada0c137ca2e9d99d042b3d7f2_Traceguids
0x14004e0ea  jnz     loc_14004E316
0x14004e0f0  mov     rcx, [rbp+4Fh+var_C0]
0x14004e0f4  lea     rax, qword_1400F9C68
0x14004e0fb  xor     ebx, ebx
0x14004e0fd  mov     [rcx], rax
0x14004e100  jmp     loc_14004DE55
0x14004e105  cmp     qword ptr [r15+20h], 0
0x14004e10a  jnz     loc_14004DFCC
0x14004e110  mov     rcx, r15
0x14004e113  call    ndisOpenProtocolSubkey
0x14004e118  mov     ebx, eax
0x14004e11a  test    eax, eax
0x14004e11c  jns     loc_14004DFCC
0x14004e122  mov     rdi, [rbp+4Fh+var_C0]
0x14004e126  jmp     loc_14004E04F
0x14004e12b  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e132  mov     r9d, 20h ; ' '; int
0x14004e138  mov     r8d, 8; int
0x14004e13e  mov     [rsp+0F0h+var_D0], r15; struct _GUID *
0x14004e143  mov     dl, 4; int
0x14004e145  mov     rcx, [rcx+40h]; int
0x14004e149  call    WPP_RECORDER_SF_
0x14004e14e  jmp     loc_14004DE8A
0x14004e153  test    ebx, ebx
0x14004e155  jns     loc_14004E060
0x14004e15b  mov     r8b, 1; CaseInSensitive
0x14004e15e  lea     rdx, stru_1400F6E68; String2
0x14004e165  mov     rcx, rsi; String1
0x14004e168  call    cs:__imp_RtlEqualUnicodeString
0x14004e16f  nop     dword ptr [rax+rax+00h]
0x14004e174  test    al, al
0x14004e176  jz      loc_14004DE47
0x14004e17c  jmp     loc_1400F0816
0x14004e181  movzx   ebx, word ptr [r13+0EE0h]
0x14004e189  lea     eax, [rbx+20h]
0x14004e18c  cmp     eax, 20h ; ' '
0x14004e18f  jb      short loc_14004E1E2
0x14004e191  mov     r14, [r13+0EE8h]
0x14004e198  mov     ecx, 40h ; '@'
0x14004e19d  mov     edx, eax
0x14004e19f  mov     r8d, 6E70444Eh
0x14004e1a5  call    cs:__imp_ExAllocatePool2
0x14004e1ac  nop     dword ptr [rax+rax+00h]
0x14004e1b1  mov     rdi, rax
0x14004e1b4  test    rax, rax
0x14004e1b7  jnz     short loc_14004E1EC
0x14004e1b9  mov     ebx, 0C000009Ah
0x14004e1be  mov     r14, [rbp+4Fh+var_B0]
0x14004e1c2  jmp     loc_14004DE47
0x14004e1c7  or      dword ptr [r13+238h], 80h
0x14004e1d2  or      dword ptr [r13+750h], 10000h
0x14004e1dd  jmp     loc_14004DFAF
0x14004e1e2  mov     ebx, 0C000000Dh
0x14004e1e7  jmp     loc_14004DE47
0x14004e1ec  mov     r13, [rbp+4Fh+var_C0]
0x14004e1f0  lea     rcx, [rdi+20h]
0x14004e1f4  add     rax, 8
0x14004e1f8  mov     r8, rbx; Size
0x14004e1fb  mov     rdx, r14; Src
0x14004e1fe  mov     [r13+0], rax
0x14004e202  mov     dword ptr [rax], 2
0x14004e208  mov     rax, [r13+0]
0x14004e20c  mov     [rax+10h], rcx
0x14004e210  mov     rcx, [r13+0]
0x14004e214  mov     rcx, [rcx+10h]; void *
0x14004e218  call    memmove
0x14004e21d  mov     rax, [r13+0]
0x14004e221  mov     [rax+8], bx
0x14004e225  mov     rax, [r13+0]
0x14004e229  mov     [rax+0Ah], bx
0x14004e22d  lea     eax, [rbx-1]
0x14004e230  cmp     byte ptr [rax+r14], 0
0x14004e235  jz      short loc_14004E27A
0x14004e237  mov     rax, [r15+18h]
0x14004e23b  xor     ebx, ebx
0x14004e23d  mov     r14, [rbp+4Fh+var_B0]
0x14004e241  mov     [rdi], rax
0x14004e244  mov     [r15+18h], rdi
0x14004e248  jmp     loc_14004DE47
0x14004e24d  mov     [rsp+0F0h+var_C8], rsi; __int64
0x14004e252  mov     r9d, 1Eh; int
0x14004e258  mov     [rsp+0F0h+var_D0], rcx; struct _GUID *
0x14004e25d  mov     r8d, 8; int
0x14004e263  mov     rcx, cs:WPP_GLOBAL_Control
0x14004e26a  mov     dl, 4; int
0x14004e26c  mov     rcx, [rcx+40h]; int
  ... truncated ...
```
