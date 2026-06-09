# NdisReadConfiguration

- ea: `0x1400493e0`
- end: `0x1400499ee`
- name: `NdisReadConfiguration`
- size: `1550`
- prototype: `void __stdcall(PNDIS_STATUS Status, PNDIS_CONFIGURATION_PARAMETER *ParameterValue, NDIS_HANDLE ConfigurationHandle, PNDIS_STRING Keyword, NDIS_PARAMETER_TYPE ParameterType)`
- caller_count: `23`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400473d0`
- `0x140047430`
- `0x140047500`
- `0x140047650`
- `0x140047c00`
- `0x140048470`
- `0x140048510`
- `0x140048880`
- `0x140048a80`
- `0x140077a80`
- `0x140086250`
- `0x14009c1a4`
- `0x1400ab810`
- `0x1400be780`
- `0x1400dc4d8`
- `0x14013c550`
- `0x140145540`
- `0x140145640`
- `0x140165f60`
- `0x140166a50`
- `0x14016ad80`
- `0x14018e1a4`
- `0x14018e414`

## callees

- `0x140029620`
- `0x1400493e0`
- `0x14004d300`
- `0x140054b80`
- `0x1400606c0`
- `0x140067370`
- `0x1400e6160`
- `0x1400e62c0`
- `0x1401448d8`
- `0x140144cc8`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x140049494`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140049549`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004956a`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400495a9`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400495d1`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400495f2`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140049613`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140049741`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400497e8`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140049494`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140049549`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14004956a`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400495a9`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400495d1`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400495f2`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140049613`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140049741`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400497e8`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x1400eb7f7`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x1400eb7f7`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400496c1`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400496c1`
- `ntoskrnl!RtlUnicodeStringToInteger` at `0x140049702`
- `ntoskrnl!RtlUnicodeStringToInteger` at `0x1400499d4`
- `ntoskrnl!RtlUnicodeStringToInteger` at `0x140049702`
- `ntoskrnl!RtlUnicodeStringToInteger` at `0x1400499d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400494e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400eb975`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400494e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400eb975`
- `ntoskrnl!ExAllocatePool2` at `0x14004965e`
- `ntoskrnl!ExAllocatePool2` at `0x140049825`
- `ntoskrnl!ExAllocatePool2` at `0x14004965e`
- `ntoskrnl!ExAllocatePool2` at `0x140049825`

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
    if ( RtlEqualUnicodeString(Keyword, (PCUNICODE_STRING)&qword_1400F1DF8[2 * i], 1u) )
    {
      v11 = 24LL * i + 1017920;
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
  if ( RtlEqualUnicodeString(Keyword, &stru_1400F1E58, 1u) && (*(_DWORD *)(v6[2] + 16LL) & 1) == 0 )
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
    if ( RtlEqualUnicodeString(Keyword, (PCUNICODE_STRING)&qword_1400F3420[v15], 1u) )
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
          v32 = ndisSaveParameters((&off_1400F3428)[v15], 4u, &v37, 4u, v42, v36);
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
  if ( !RtlEqualUnicodeString(Keyword, &stru_1400F1E38, 1u) )
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
    *v36 = (PNDIS_CONFIGURATION_PARAMETER)qword_1400F4C58;
    goto LABEL_46;
  }
LABEL_20:
  if ( RtlEqualUnicodeString(Keyword, &stru_1400F1E48, 1u) )
  {
    if ( ParameterType == NdisParameterInteger )
    {
      RegistryValues = 0;
      dword_14011CA68 = ndisReadNDKGlobalFlags();
      *v36 = (PNDIS_CONFIGURATION_PARAMETER)&qword_14011CA60;
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
    *v36 = (PNDIS_CONFIGURATION_PARAMETER)qword_1400F4C58;
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
        if ( !RtlEqualUnicodeString(Keyword, &stru_1400F1E68, 1u) )
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
0x1400493e0  push    rbp
0x1400493e2  push    rbx
0x1400493e3  push    rsi
0x1400493e4  push    rdi
0x1400493e5  push    r12
0x1400493e7  push    r13
0x1400493e9  push    r14
0x1400493eb  push    r15
0x1400493ed  lea     rbp, [rsp-17h]
0x1400493f2  sub     rsp, 0B8h
0x1400493f9  mov     rax, cs:__security_cookie
0x140049400  xor     rax, rsp
0x140049403  mov     [rbp+4Fh+var_48], rax
0x140049407  xor     edi, edi
0x140049409  mov     [rbp+4Fh+var_90], r8
0x14004940d  xorps   xmm1, xmm1
0x140049410  mov     [rbp+4Fh+var_C0], rdx
0x140049414  xor     eax, eax
0x140049416  mov     [rbp+4Fh+var_B0], rcx
0x14004941a  xorps   xmm0, xmm0
0x14004941d  mov     [rbp+4Fh+var_50], rax
0x140049421  mov     rsi, r9
0x140049424  mov     [rbp+4Fh+var_B8], edi
0x140049427  mov     r15, r8
0x14004942a  mov     [rbp+4Fh+P], rdi
0x14004942e  mov     r14, rcx
0x140049431  mov     [rbp+4Fh+var_98], edi
0x140049434  movups  xmmword ptr [rbp+4Fh+String.Length], xmm0
0x140049438  mov     [rbp+4Fh+var_A8], 4030201h
0x14004943f  movups  [rbp+4Fh+var_70], xmm1
0x140049443  mov     [rbp+4Fh+var_A4], 2010201h
0x14004944a  movups  [rbp+4Fh+var_60], xmm1
0x14004944e  mov     [rbp+4Fh+var_A0], 3
0x140049452  lea     rax, WPP_RECORDER_INITIALIZED
0x140049459  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140049460  lea     rcx, WPP_78fc2fada0c137ca2e9d99d042b3d7f2_Traceguids
0x140049467  jnz     loc_1400498CD
0x14004946d  mov     r12, [rsi+8]
0x140049471  lea     r13, qword_1400F1DF8
0x140049478  mov     ebx, edi
0x14004947a  cmp     ebx, 3
0x14004947d  jnb     loc_14004952B
0x140049483  mov     edx, ebx
0x140049485  mov     r8b, 1; CaseInSensitive
0x140049488  shl     rdx, 4
0x14004948c  mov     rcx, rsi; String1
0x14004948f  add     rdx, r13; String2
0x140049492  mov     edi, ebx
0x140049494  call    cs:__imp_RtlEqualUnicodeString
0x14004949b  nop     dword ptr [rax+rax+00h]
0x1400494a0  test    al, al
0x1400494a2  jnz     short loc_1400494A8
0x1400494a4  inc     ebx
0x1400494a6  jmp     short loc_14004947A
0x1400494a8  mov     rcx, [rbp+4Fh+var_C0]
0x1400494ac  lea     rax, [rdi+rdi*2]
0x1400494b0  lea     rax, ds:0F8840h[rax*8]
0x1400494b8  xor     ebx, ebx
0x1400494ba  lea     r15, cs:140000000h
0x1400494c1  add     rax, r15
0x1400494c4  mov     [rcx], rax
0x1400494c7  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400494ce  lea     r15, WPP_78fc2fada0c137ca2e9d99d042b3d7f2_Traceguids
0x1400494d5  test    r12, r12
0x1400494d8  jz      short loc_1400494F1
0x1400494da  cmp     r12, [rsi+8]
0x1400494de  jz      short loc_1400494F1
0x1400494e0  xor     edx, edx; Tag
0x1400494e2  mov     rcx, r12; P
0x1400494e5  call    cs:__imp_ExFreePoolWithTag
0x1400494ec  nop     dword ptr [rax+rax+00h]
0x1400494f1  sar     ebx, 1Fh
0x1400494f4  and     ebx, 0C0000001h
0x1400494fa  mov     [r14], ebx
0x1400494fd  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140049504  jnz     loc_1400497AB
0x14004950a  mov     rcx, [rbp+4Fh+var_48]
0x14004950e  xor     rcx, rsp; StackCookie
0x140049511  call    __security_check_cookie
0x140049516  add     rsp, 0B8h
0x14004951d  pop     r15
0x14004951f  pop     r14
0x140049521  pop     r13
0x140049523  pop     r12
0x140049525  pop     rdi
0x140049526  pop     rsi
0x140049527  pop     rbx
0x140049528  pop     rbp
0x140049529  retn
0x14004952b  mov     rax, [r15+10h]
0x14004952f  mov     r13, [rax+8]
0x140049533  test    r13, r13
0x140049536  jz      loc_14004962F
0x14004953c  mov     r8b, 1; CaseInSensitive
0x14004953f  lea     rdx, String2; String2
0x140049546  mov     rcx, rsi; String1
0x140049549  call    cs:__imp_RtlEqualUnicodeString
0x140049550  nop     dword ptr [rax+rax+00h]
0x140049555  test    al, al
0x140049557  jnz     loc_140049801
0x14004955d  mov     r8b, 1; CaseInSensitive
0x140049560  lea     rdx, stru_1400F1E58; String2
0x140049567  mov     rcx, rsi; String1
0x14004956a  call    cs:__imp_RtlEqualUnicodeString
0x140049571  nop     dword ptr [rax+rax+00h]
0x140049576  test    al, al
0x140049578  jnz     loc_1400EB7B8
0x14004957e  xor     ebx, ebx
0x140049580  lea     r15, cs:140000000h
0x140049587  nop     word ptr [rax+rax+00000000h]
0x140049590  mov     edi, ebx
0x140049592  lea     rdx, rva qword_1400F3420[r15]
0x140049599  shl     rdi, 4
0x14004959d  mov     r8b, 1; CaseInSensitive
0x1400495a0  add     rdx, rdi; String2
0x1400495a3  mov     r14d, ebx
0x1400495a6  mov     rcx, rsi; String1
0x1400495a9  call    cs:__imp_RtlEqualUnicodeString
0x1400495b0  nop     dword ptr [rax+rax+00h]
0x1400495b5  test    al, al
0x1400495b7  jnz     loc_140049969
0x1400495bd  inc     ebx
0x1400495bf  cmp     ebx, 9
0x1400495c2  jb      short loc_140049590
0x1400495c4  mov     r8b, 1; CaseInSensitive
0x1400495c7  lea     rdx, stru_1400F1E38; String2
0x1400495ce  mov     rcx, rsi; String1
0x1400495d1  call    cs:__imp_RtlEqualUnicodeString
0x1400495d8  nop     dword ptr [rax+rax+00h]
0x1400495dd  test    al, al
0x1400495df  jnz     loc_140049913
0x1400495e5  mov     r8b, 1; CaseInSensitive
0x1400495e8  lea     rdx, stru_1400F1E48; String2
0x1400495ef  mov     rcx, rsi; String1
0x1400495f2  call    cs:__imp_RtlEqualUnicodeString
0x1400495f9  nop     dword ptr [rax+rax+00h]
0x1400495fe  test    al, al
0x140049600  jnz     loc_14004993F
0x140049606  mov     r8b, 1; CaseInSensitive
0x140049609  lea     rdx, Keyword; String2
0x140049610  mov     rcx, rsi; String1
0x140049613  call    cs:__imp_RtlEqualUnicodeString
0x14004961a  nop     dword ptr [rax+rax+00h]
0x14004961f  mov     r14, [rbp+4Fh+var_B0]
0x140049623  mov     r15, [rbp+4Fh+var_90]
0x140049627  test    al, al
0x140049629  jnz     loc_140049847
0x14004962f  cmp     cs:?ndisAllowFlowControl@@3EA, 0; uchar ndisAllowFlowControl
0x140049636  jz      loc_140049734
0x14004963c  mov     rax, [r15+10h]
0x140049640  mov     ecx, [rax+10h]
0x140049643  test    cl, 2
0x140049646  jnz     loc_140049785
0x14004964c  movzx   edx, word ptr [rsi]
0x14004964f  mov     ecx, 42h ; 'B'
0x140049654  add     rdx, 2
0x140049658  mov     r8d, 2020444Eh
0x14004965e  call    cs:__imp_ExAllocatePool2
0x140049665  nop     dword ptr [rax+rax+00h]
0x14004966a  mov     r12, rax
0x14004966d  test    rax, rax
0x140049670  jz      loc_14004971C
0x140049676  movzx   r8d, word ptr [rsi]; Size
0x14004967a  mov     rcx, rax; void *
0x14004967d  mov     rdx, [rsi+8]; Src
0x140049681  call    memmove
0x140049686  movzx   ecx, word ptr [rsi]
0x140049689  xor     eax, eax
0x14004968b  mov     rdi, [rbp+4Fh+var_C0]
0x14004968f  mov     r9, r15
0x140049692  mov     [rsp+0F0h+var_D0], 0
0x14004969b  mov     [rcx+r12], ax
0x1400496a0  mov     ecx, 40000000h
0x1400496a5  mov     rax, [r15+10h]
0x1400496a9  mov     [rax+28h], r12
0x1400496ad  mov     rax, [r15+10h]
0x1400496b1  mov     [rax+30h], rdi
0x1400496b5  mov     r8, [r15+10h]
0x1400496b9  mov     rdx, [r15+20h]
0x1400496bd  add     r8, 18h
0x1400496c1  call    cs:__imp_RtlQueryRegistryValuesEx
0x1400496c8  nop     dword ptr [rax+rax+00h]
0x1400496cd  mov     ebx, eax
0x1400496cf  test    r13, r13
0x1400496d2  jz      loc_1400497D3
0x1400496d8  test    ebx, ebx
0x1400496da  js      loc_1400494C7
0x1400496e0  mov     rcx, [rdi]
0x1400496e3  cmp     dword ptr [rcx], 2
0x1400496e6  jnz     loc_1400494C7
0x1400496ec  cmp     [rbp+4Fh+ParameterType], 0
0x1400496f0  jnz     loc_1400499BE
0x1400496f6  add     rcx, 8; String
0x1400496fa  mov     edx, 0Ah; Base
0x1400496ff  mov     r8, rcx; Value
0x140049702  call    cs:__imp_RtlUnicodeStringToInteger
0x140049709  nop     dword ptr [rax+rax+00h]
0x14004970e  mov     rax, [rdi]
0x140049711  mov     dword ptr [rax], 0
0x140049717  jmp     loc_1400494C7
0x14004971c  mov     ebx, 0C000009Ah
0x140049721  lea     rdi, WPP_RECORDER_INITIALIZED
0x140049728  lea     r15, WPP_78fc2fada0c137ca2e9d99d042b3d7f2_Traceguids
0x14004972f  jmp     loc_1400494F1
0x140049734  mov     r8b, 1; CaseInSensitive
0x140049737  lea     rdx, ?FlowControlStr@@3U_UNICODE_STRING@@A; String2
0x14004973e  mov     rcx, rsi; String1
0x140049741  call    cs:__imp_RtlEqualUnicodeString
0x140049748  nop     dword ptr [rax+rax+00h]
0x14004974d  test    al, al
0x14004974f  jz      loc_14004963C
0x140049755  lea     rdi, WPP_RECORDER_INITIALIZED
0x14004975c  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140049763  lea     r15, WPP_78fc2fada0c137ca2e9d99d042b3d7f2_Traceguids
0x14004976a  jnz     loc_140049996
0x140049770  mov     rcx, [rbp+4Fh+var_C0]
0x140049774  lea     rax, qword_1400F4C58
0x14004977b  xor     ebx, ebx
0x14004977d  mov     [rcx], rax
0x140049780  jmp     loc_1400494D5
0x140049785  cmp     qword ptr [r15+20h], 0
0x14004978a  jnz     loc_14004964C
0x140049790  mov     rcx, r15
0x140049793  call    ndisOpenProtocolSubkey
0x140049798  mov     ebx, eax
0x14004979a  test    eax, eax
0x14004979c  jns     loc_14004964C
0x1400497a2  mov     rdi, [rbp+4Fh+var_C0]
0x1400497a6  jmp     loc_1400496CF
0x1400497ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400497b2  mov     r9d, 20h ; ' '; int
0x1400497b8  mov     r8d, 8; int
0x1400497be  mov     [rsp+0F0h+var_D0], r15; struct _GUID *
0x1400497c3  mov     dl, 4; int
0x1400497c5  mov     rcx, [rcx+40h]; int
0x1400497c9  call    WPP_RECORDER_SF_
0x1400497ce  jmp     loc_14004950A
0x1400497d3  test    ebx, ebx
0x1400497d5  jns     loc_1400496E0
0x1400497db  mov     r8b, 1; CaseInSensitive
0x1400497de  lea     rdx, stru_1400F1E68; String2
0x1400497e5  mov     rcx, rsi; String1
0x1400497e8  call    cs:__imp_RtlEqualUnicodeString
0x1400497ef  nop     dword ptr [rax+rax+00h]
0x1400497f4  test    al, al
0x1400497f6  jz      loc_1400494C7
0x1400497fc  jmp     loc_1400EB90E
0x140049801  movzx   ebx, word ptr [r13+0EE0h]
0x140049809  lea     eax, [rbx+20h]
0x14004980c  cmp     eax, 20h ; ' '
0x14004980f  jb      short loc_140049862
0x140049811  mov     r14, [r13+0EE8h]
0x140049818  mov     ecx, 40h ; '@'
0x14004981d  mov     edx, eax
0x14004981f  mov     r8d, 6E70444Eh
0x140049825  call    cs:__imp_ExAllocatePool2
0x14004982c  nop     dword ptr [rax+rax+00h]
0x140049831  mov     rdi, rax
0x140049834  test    rax, rax
0x140049837  jnz     short loc_14004986C
0x140049839  mov     ebx, 0C000009Ah
0x14004983e  mov     r14, [rbp+4Fh+var_B0]
0x140049842  jmp     loc_1400494C7
0x140049847  or      dword ptr [r13+238h], 80h
0x140049852  or      dword ptr [r13+750h], 10000h
0x14004985d  jmp     loc_14004962F
0x140049862  mov     ebx, 0C000000Dh
0x140049867  jmp     loc_1400494C7
0x14004986c  mov     r13, [rbp+4Fh+var_C0]
0x140049870  lea     rcx, [rdi+20h]
0x140049874  add     rax, 8
0x140049878  mov     r8, rbx; Size
0x14004987b  mov     rdx, r14; Src
0x14004987e  mov     [r13+0], rax
0x140049882  mov     dword ptr [rax], 2
0x140049888  mov     rax, [r13+0]
0x14004988c  mov     [rax+10h], rcx
0x140049890  mov     rcx, [r13+0]
0x140049894  mov     rcx, [rcx+10h]; void *
0x140049898  call    memmove
0x14004989d  mov     rax, [r13+0]
0x1400498a1  mov     [rax+8], bx
0x1400498a5  mov     rax, [r13+0]
0x1400498a9  mov     [rax+0Ah], bx
0x1400498ad  lea     eax, [rbx-1]
0x1400498b0  cmp     byte ptr [rax+r14], 0
0x1400498b5  jz      short loc_1400498FA
0x1400498b7  mov     rax, [r15+18h]
0x1400498bb  xor     ebx, ebx
0x1400498bd  mov     r14, [rbp+4Fh+var_B0]
0x1400498c1  mov     [rdi], rax
0x1400498c4  mov     [r15+18h], rdi
0x1400498c8  jmp     loc_1400494C7
0x1400498cd  mov     [rsp+0F0h+var_C8], rsi; __int64
0x1400498d2  mov     r9d, 1Eh; int
0x1400498d8  mov     [rsp+0F0h+var_D0], rcx; struct _GUID *
0x1400498dd  mov     r8d, 8; int
0x1400498e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400498ea  mov     dl, 4; int
0x1400498ec  mov     rcx, [rcx+40h]; int
  ... truncated ...
```
