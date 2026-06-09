# ndisGetOrCreateFilterInstanceKey(_UNICODE_STRING const *,_NDIS_FILTER_BLOCK *,_NDIS_MINIPORT_BLOCK *,uchar,uchar *,_UNICODE_STRING *)

- ea: `0x140079040`
- end: `0x1400799aa`
- name: `?ndisGetOrCreateFilterInstanceKey@@YAHPEBU_UNICODE_STRING@@PEAU_NDIS_FILTER_BLOCK@@PEAU_NDIS_MINIPORT_BLOCK@@EPEAEPEAU1@@Z`
- size: `2410`
- prototype: `__int64 __usercall@<rax>(const struct _UNICODE_STRING *@<rcx>, struct _NDIS_FILTER_BLOCK *@<rdx>, struct _NDIS_MINIPORT_BLOCK *@<r8>, unsigned __int8@<r9b>, unsigned __int8 *, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14004d6a0`
- `0x140089fe0`

## callees

- `0x14001fa30`
- `0x14004bc60`
- `0x140065890`
- `0x1400761c0`
- `0x140079040`
- `0x1400eb380`
- `0x1400eb4c0`
- `0x1400eb7c0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140079218`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400796f4`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140079218`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400796f4`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007922b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140079242`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140079259`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007926d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007970a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140079720`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140079733`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140079746`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007975a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007922b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140079242`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140079259`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007926d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007970a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140079720`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140079733`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140079746`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007975a`
- `ntoskrnl!RtlStringFromGUID` at `0x1400791a2`
- `ntoskrnl!RtlStringFromGUID` at `0x1400792fb`
- `ntoskrnl!RtlStringFromGUID` at `0x1400791a2`
- `ntoskrnl!RtlStringFromGUID` at `0x1400792fb`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140079348`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400793dd`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140079831`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140079348`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400793dd`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140079831`
- `ntoskrnl!ZwOpenKey` at `0x1400792a8`
- `ntoskrnl!ZwOpenKey` at `0x1400792a8`
- `ntoskrnl!ZwClose` at `0x140079804`
- `ntoskrnl!ZwClose` at `0x140079804`
- `ntoskrnl!ZwEnumerateKey` at `0x140079473`
- `ntoskrnl!ZwEnumerateKey` at `0x140079473`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14007954d`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14007954d`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1400797b4`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1400797b4`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x1400793cb`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x1400793cb`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400795b7`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400795b7`
- `ntoskrnl!RtlCreateRegistryKey` at `0x140079777`
- `ntoskrnl!RtlCreateRegistryKey` at `0x140079777`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400795d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400797ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x140079860`
- `ntoskrnl!ExFreePoolWithTag` at `0x140079890`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400798bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400798ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007991c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400795d2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400797ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x140079860`
- `ntoskrnl!ExFreePoolWithTag` at `0x140079890`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400798bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400798ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007991c`
- `ntoskrnl!ExAllocatePool2` at `0x1400791f1`
- `ntoskrnl!ExAllocatePool2` at `0x14007932e`
- `ntoskrnl!ExAllocatePool2` at `0x14007937c`
- `ntoskrnl!ExAllocatePool2` at `0x140079401`
- `ntoskrnl!ExAllocatePool2` at `0x140079644`
- `ntoskrnl!ExAllocatePool2` at `0x1400796c4`
- `ntoskrnl!ExAllocatePool2` at `0x1400791f1`
- `ntoskrnl!ExAllocatePool2` at `0x14007932e`
- `ntoskrnl!ExAllocatePool2` at `0x14007937c`
- `ntoskrnl!ExAllocatePool2` at `0x140079401`
- `ntoskrnl!ExAllocatePool2` at `0x140079644`
- `ntoskrnl!ExAllocatePool2` at `0x1400796c4`

## string_xrefs

- `0x140079077`: `\Registry\Machine\System\CurrentControlSet\Services\`
- `0x140079512`: `LowerComponent`
- `0x140079790`: `LowerComponent`

## pseudocode

```c
__int64 __fastcall ndisGetOrCreateFilterInstanceKey(
        const struct _UNICODE_STRING *a1,
        struct _NDIS_FILTER_BLOCK *a2,
        struct _NDIS_MINIPORT_BLOCK *a3,
        char a4,
        unsigned __int8 *a5,
        struct _UNICODE_STRING *Destination)
{
  char v7; // r8
  int v8; // edx
  char v9; // si
  char v10; // r14
  char v11; // r12
  unsigned __int16 *v12; // r15
  unsigned int v13; // ebx
  _NDIS_FILTER_BLOCK *LowerFilter; // rbx
  _NDIS_FILTER_DRIVER_BLOCK *FilterDriver; // rdx
  wchar_t *Pool2; // rax
  NTSTATUS v17; // ebx
  ULONG v18; // ebx
  NTSTATUS v19; // eax
  _NDIS_FILTER_DRIVER_BLOCK *v20; // rcx
  int v21; // eax
  int v22; // edx
  int RegistryValues; // ebx
  unsigned __int16 v24; // ax
  wchar_t *v25; // rax
  NTSTATUS RegistryKey; // eax
  wchar_t *Buffer; // rcx
  int v32; // [rsp+64h] [rbp-9Ch]
  UNICODE_STRING String1; // [rsp+68h] [rbp-98h] BYREF
  UNICODE_STRING v34; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  ULONG ResultLength; // [rsp+98h] [rbp-68h] BYREF
  int v37; // [rsp+9Ch] [rbp-64h]
  ULONG v38; // [rsp+A0h] [rbp-60h]
  void *KeyHandle; // [rsp+A8h] [rbp-58h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+B0h] [rbp-50h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+C0h] [rbp-40h] BYREF
  UNICODE_STRING String2; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int8 *v43; // [rsp+E0h] [rbp-20h]
  UNICODE_STRING SourceString; // [rsp+E8h] [rbp-18h] BYREF
  UNICODE_STRING v45; // [rsp+F8h] [rbp-8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v47[22]; // [rsp+140h] [rbp+40h] BYREF

  v7 = (char)a2;
  SourceString.Buffer = (wchar_t *)L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\";
  v8 = (int)a1;
  *(_QWORD *)&GuidString.Length = 0;
  v9 = 0;
  GuidString.Buffer = 0;
  v10 = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  v11 = 0;
  v45.Buffer = (wchar_t *)L"\\";
  v12 = 0;
  *(_QWORD *)&String1.Length = 0;
  String1.Buffer = 0;
  *(_QWORD *)&UnicodeString.Length = 0;
  UnicodeString.Buffer = 0;
  KeyHandle = 0;
  ResultLength = 0;
  *(_QWORD *)&v34.Length = 0;
  v34.Buffer = 0;
  *(_QWORD *)&String2.Length = 0;
  String2.Buffer = 0;
  v43 = a5;
  *(_QWORD *)&SourceString.Length = 6946920;
  *(_QWORD *)&v45.Length = 262146;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v8) = 4;
    WPP_RECORDER_SF_qqq(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v8,
      1,
      99,
      (struct _GUID *)&WPP_9524bb9419753e2807bcae08715ee655_Traceguids,
      (char)a1,
      (char)a3,
      v7);
    v8 = (int)a1;
    v7 = (char)a2;
  }
  if ( !a3->BaseMiniport )
  {
    v13 = -1073741811;
    goto LABEL_57;
  }
  *a5 = 0;
  *Destination = 0;
  if ( RtlStringFromGUID(&a3->BaseMiniport->InterfaceGuid, &GuidString) )
    goto LABEL_54;
  DestinationString.Length = 0;
  v9 = 1;
  DestinationString.MaximumLength = GuidString.Length
                                  + SourceString.Length
                                  + ndisParameterStr.Length
                                  + ndisFilterAdapterStr.Length
                                  + a1->Length
                                  + 2;
  DestinationString.Buffer = (wchar_t *)ExAllocatePool2(64, DestinationString.MaximumLength, 538985550);
  if ( !DestinationString.Buffer )
  {
    v13 = -1073741670;
    goto LABEL_55;
  }
  RtlCopyUnicodeString(&DestinationString, &SourceString);
  RtlAppendUnicodeStringToString(&DestinationString, a1);
  RtlAppendUnicodeStringToString(&DestinationString, &ndisParameterStr);
  RtlAppendUnicodeStringToString(&DestinationString, &ndisFilterAdapterStr);
  RtlAppendUnicodeStringToString(&DestinationString, &GuidString);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x40000000u, &ObjectAttributes) )
  {
    KeyHandle = 0;
    v13 = -1073741823;
LABEL_60:
    RtlFreeUnicodeString(&GuidString);
    v8 = (int)a1;
    v7 = (char)a2;
    goto LABEL_61;
  }
  LowerFilter = a2->LowerFilter;
  if ( LowerFilter )
  {
    while ( 1 )
    {
      FilterDriver = LowerFilter->FilterDriver;
      if ( (FilterDriver->Bind._p->_t.FilterBindFlags & 2) == 0 )
        break;
      LowerFilter = LowerFilter->LowerFilter;
      if ( !LowerFilter )
        goto LABEL_13;
    }
    String1.Length = FilterDriver->DefaultFilterCharacteristics.UniqueName.Length;
    String1.MaximumLength = String1.Length + 2;
    Pool2 = (wchar_t *)ExAllocatePool2(64, (unsigned __int16)(String1.Length + 2), 538985550);
    String1.Buffer = Pool2;
    if ( !Pool2 )
    {
      v13 = -1073741670;
      goto LABEL_55;
    }
    v10 = 1;
    memmove(Pool2, LowerFilter->FilterDriver->DefaultFilterCharacteristics.UniqueName.Buffer, String1.Length);
  }
  else
  {
LABEL_13:
    if ( RtlStringFromGUID(&a3->InterfaceGuid, &UnicodeString) )
      goto LABEL_54;
    String1.Length = UnicodeString.Length;
    String1.MaximumLength = UnicodeString.MaximumLength;
    String1.Buffer = (wchar_t *)ExAllocatePool2(64, UnicodeString.MaximumLength, 538985550);
    if ( !String1.Buffer )
    {
      RtlFreeUnicodeString(&UnicodeString);
      goto LABEL_54;
    }
    v10 = 1;
    v17 = RtlUpcaseUnicodeString(&String1, &UnicodeString, 0);
    RtlFreeUnicodeString(&UnicodeString);
    if ( v17 )
      goto LABEL_54;
  }
  v12 = (unsigned __int16 *)ExAllocatePool2(66, 536, 538985550);
  if ( !v12 )
  {
    v13 = -1073741670;
    goto LABEL_55;
  }
  v37 = 0;
  v18 = 0;
  v32 = 0;
  while ( 1 )
  {
    v38 = v18;
    if ( v18 > 0x270F )
      break;
    memset(v12, 0, 0x218u);
    ResultLength = 0;
    v19 = ZwEnumerateKey(KeyHandle, v18, KeyBasicInformation, v12, 0x216u, &ResultLength);
    if ( v19 == -2147483622 )
      break;
    if ( v19 )
      goto LABEL_54;
    v34.Length = v12[6];
    v34.Buffer = v12 + 8;
    v34.MaximumLength = v34.Length + 2;
    memset(v47, 0, 0xA8u);
    LODWORD(v47[1]) = 1;
    v47[2] = v12 + 8;
    v20 = a2->FilterDriver;
    if ( v20->DefaultFilterCharacteristics.MajorNdisVersion > 6u
      || v20->DefaultFilterCharacteristics.MajorNdisVersion == 6
      && v20->DefaultFilterCharacteristics.MinorNdisVersion >= 0x28u )
    {
      v21 = 256;
      v37 = 0x1000000;
      v32 = 256;
    }
    else
    {
      v21 = v32;
    }
    v47[7] = 0;
    LODWORD(v47[8]) = v21 | 0x24;
    v47[16] = 0;
    v47[9] = L"LowerComponent";
    v47[10] = &String2;
    LODWORD(v47[11]) = v37;
    RegistryValues = RtlQueryRegistryValuesEx(0x40000000, KeyHandle, v47, 0, 0);
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_dd(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v22,
        1,
        100,
        (struct _GUID *)&WPP_9524bb9419753e2807bcae08715ee655_Traceguids,
        RegistryValues,
        v32);
    if ( RegistryValues )
    {
      v13 = -1073741823;
      goto LABEL_55;
    }
    if ( !RtlCompareUnicodeString(&String1, &String2, 1u) )
    {
      *v43 = 1;
      goto LABEL_47;
    }
    if ( String2.Buffer )
    {
      ExFreePoolWithTag(String2.Buffer, 0);
      String2.Buffer = 0;
    }
    v18 = v38 + 1;
  }
  if ( !*v43 )
  {
    if ( !a4 )
      goto LABEL_54;
    if ( v18 > 0x270F )
    {
      v13 = -1073741670;
      goto LABEL_55;
    }
    *(_DWORD *)&v34.Length = 655368;
    v34.Buffer = (wchar_t *)ExAllocatePool2(64, 10, 538985550);
    if ( !v34.Buffer )
    {
      v13 = -1073741670;
      goto LABEL_55;
    }
    v11 = 1;
    if ( (unsigned int)RtlStringCchPrintfW(v34.Buffer, (unsigned __int64)v34.MaximumLength >> 1, L"%04d", v18) )
      goto LABEL_54;
  }
LABEL_47:
  v24 = GuidString.Length
      + v45.Length
      + ndisParameterStr.Length
      + ndisFilterAdapterStr.Length
      + a1->Length
      + v34.Length
      + 2;
  Destination->MaximumLength = v24;
  v25 = (wchar_t *)ExAllocatePool2(64, v24, 538985550);
  v8 = (int)a1;
  Destination->Buffer = v25;
  if ( !v25 )
  {
    v13 = -1073741670;
    goto LABEL_56;
  }
  v13 = 0;
  RtlCopyUnicodeString(Destination, a1);
  RtlAppendUnicodeStringToString(Destination, &ndisParameterStr);
  RtlAppendUnicodeStringToString(Destination, &ndisFilterAdapterStr);
  RtlAppendUnicodeStringToString(Destination, &GuidString);
  RtlAppendUnicodeStringToString(Destination, &v45);
  RtlAppendUnicodeStringToString(Destination, &v34);
  if ( *v43 )
    goto LABEL_55;
  RegistryKey = RtlCreateRegistryKey(1u, Destination->Buffer);
  Buffer = Destination->Buffer;
  if ( !RegistryKey )
  {
    if ( !RtlWriteRegistryValue(1u, Buffer, L"LowerComponent", 1u, String1.Buffer, String1.Length + 2) )
      goto LABEL_55;
    Buffer = Destination->Buffer;
  }
  ExFreePoolWithTag(Buffer, 0);
  *Destination = 0;
LABEL_54:
  v13 = -1073741823;
LABEL_55:
  v8 = (int)a1;
LABEL_56:
  v7 = (char)a2;
LABEL_57:
  if ( KeyHandle )
  {
    ZwClose(KeyHandle);
    v8 = (int)a1;
    v7 = (char)a2;
  }
  if ( v9 )
    goto LABEL_60;
LABEL_61:
  if ( DestinationString.Buffer )
  {
    ExFreePoolWithTag(DestinationString.Buffer, 0);
    v8 = (int)a1;
    v7 = (char)a2;
  }
  if ( v10 )
  {
    ExFreePoolWithTag(String1.Buffer, 0);
    v8 = (int)a1;
    v7 = (char)a2;
  }
  if ( String2.Buffer )
  {
    ExFreePoolWithTag(String2.Buffer, 0);
    v8 = (int)a1;
    v7 = (char)a2;
  }
  if ( v12 )
  {
    ExFreePoolWithTag(v12, 0);
    v8 = (int)a1;
    v7 = (char)a2;
  }
  if ( v11 )
  {
    ExFreePoolWithTag(v34.Buffer, 0);
    v8 = (int)a1;
    v7 = (char)a2;
  }
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qqqL(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v8,
      1,
      101,
      (struct _GUID *)&WPP_9524bb9419753e2807bcae08715ee655_Traceguids,
      v8,
      (char)a3,
      v7,
      v13);
  return v13;
}

```

## disassembly

```asm
0x140079040  mov     [rsp-8+arg_18], rbx
0x140079045  push    rbp
0x140079046  push    rsi
0x140079047  push    rdi
0x140079048  push    r12
0x14007904a  push    r13
0x14007904c  push    r14
0x14007904e  push    r15
0x140079050  lea     rbp, [rsp-100h]
0x140079058  sub     rsp, 200h
0x14007905f  mov     rax, cs:__security_cookie
0x140079066  xor     rax, rsp
0x140079069  mov     [rbp+130h+var_40], rax
0x140079070  mov     rbx, [rbp+130h+arg_20]
0x140079077  lea     rax, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x14007907e  mov     r13, [rbp+130h+Destination]
0x140079085  xorps   xmm0, xmm0
0x140079088  mov     rdi, r8
0x14007908b  mov     [rsp+230h+var_1D8], rdx
0x140079090  mov     r8, rdx
0x140079093  mov     [rbp+130h+SourceString.Buffer], rax
0x140079097  mov     rdx, rcx
0x14007909a  mov     [rsp+230h+Source], rcx
0x14007909f  xor     ecx, ecx
0x1400790a1  mov     [rsp+230h+var_1D0], r9b
0x1400790a6  lea     rax, asc_1400FB840; "\\"
0x1400790ad  mov     qword ptr [rbp+130h+GuidString.Length], rcx
0x1400790b1  xor     sil, sil
0x1400790b4  mov     [rbp+130h+GuidString.Buffer], rcx
0x1400790b8  xor     r14b, r14b
0x1400790bb  mov     qword ptr [rbp+130h+DestinationString.Length], rcx
0x1400790bf  mov     [rbp+130h+DestinationString.Buffer], rcx
0x1400790c3  xor     r12b, r12b
0x1400790c6  mov     [rbp+130h+var_138.Buffer], rax
0x1400790ca  mov     r15d, ecx
0x1400790cd  mov     qword ptr [rsp+230h+String1.Length], rcx
0x1400790d2  mov     [rsp+230h+String1.Buffer], rcx
0x1400790d7  mov     qword ptr [rbp+130h+UnicodeString.Length], rcx
0x1400790db  mov     [rbp+130h+UnicodeString.Buffer], rcx
0x1400790df  mov     [rbp+130h+KeyHandle], rcx
0x1400790e3  mov     [rbp+130h+var_198], ecx
0x1400790e6  mov     qword ptr [rsp+230h+var_1B8.Length], rcx
0x1400790eb  mov     [rbp+130h+var_1B8.Buffer], rcx
0x1400790ef  mov     qword ptr [rbp+130h+String2.Length], rcx
0x1400790f3  mov     [rbp+130h+String2.Buffer], rcx
0x1400790f7  mov     [rbp+130h+var_150], rbx
0x1400790fb  mov     qword ptr [rbp+130h+SourceString.Length], 6A0068h
0x140079103  mov     qword ptr [rbp+130h+var_138.Length], 40002h
0x14007910b  movups  xmmword ptr [rbp+130h+ObjectAttributes.Length], xmm0
0x14007910f  movups  xmmword ptr [rbp+130h+ObjectAttributes.ObjectName], xmm0
0x140079113  movups  xmmword ptr [rbp+130h+ObjectAttributes.SecurityDescriptor], xmm0
0x140079117  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007911e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140079125  lea     r10, WPP_9524bb9419753e2807bcae08715ee655_Traceguids
0x14007912c  jz      short loc_140079178
0x14007912e  mov     rcx, cs:WPP_GLOBAL_Control
0x140079135  mov     r9d, 63h ; 'c'; int
0x14007913b  mov     qword ptr [rsp+230h+var_1F8], r8; char
0x140079140  mov     r8d, 1; int
0x140079146  mov     qword ptr [rsp+230h+var_200], rdi; char
0x14007914b  mov     [rsp+230h+ResultLength], rdx; char
0x140079150  mov     dl, 4; int
0x140079152  mov     rcx, [rcx+40h]; int
0x140079156  mov     qword ptr [rsp+230h+Length], r10; struct _GUID *
0x14007915b  call    WPP_RECORDER_SF_qqq
0x140079160  mov     rdx, [rsp+230h+Source]
0x140079165  lea     rax, WPP_RECORDER_INITIALIZED
0x14007916c  mov     r8, [rsp+230h+var_1D8]
0x140079171  lea     r10, WPP_9524bb9419753e2807bcae08715ee655_Traceguids
0x140079178  cmp     [rdi+10h], r15
0x14007917c  jnz     short loc_140079188
0x14007917e  mov     ebx, 0C000000Dh
0x140079183  jmp     loc_1400797FB
0x140079188  mov     [rbx], sil
0x14007918b  lea     rdx, [rbp+130h+GuidString]; GuidString
0x14007918f  xorps   xmm0, xmm0
0x140079192  movups  xmmword ptr [r13+0], xmm0
0x140079197  mov     rcx, [rdi+10h]
0x14007919b  add     rcx, 0FA8h; Guid
0x1400791a2  call    cs:__imp_RtlStringFromGUID
0x1400791a9  nop     dword ptr [rax+rax+00h]
0x1400791ae  test    eax, eax
0x1400791b0  jnz     loc_1400797DE
0x1400791b6  mov     rbx, [rsp+230h+Source]
0x1400791bb  mov     ecx, 40h ; '@'
0x1400791c0  mov     [rbp+130h+DestinationString.Length], ax
0x1400791c4  mov     r8d, 2020444Eh
0x1400791ca  mov     sil, 1
0x1400791cd  movzx   eax, word ptr [rbx]
0x1400791d0  add     ax, 2
0x1400791d4  add     ax, cs:?ndisFilterAdapterStr@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING ndisFilterAdapterStr ...
0x1400791db  add     ax, cs:?ndisParameterStr@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING ndisParameterStr ...
0x1400791e2  add     ax, [rbp+130h+SourceString.Length]
0x1400791e6  add     ax, [rbp+130h+GuidString.Length]
0x1400791ea  movzx   edx, ax
0x1400791ed  mov     [rbp+130h+DestinationString.MaximumLength], dx
0x1400791f1  call    cs:__imp_ExAllocatePool2
0x1400791f8  nop     dword ptr [rax+rax+00h]
0x1400791fd  mov     [rbp+130h+DestinationString.Buffer], rax
0x140079201  test    rax, rax
0x140079204  jnz     short loc_140079210
0x140079206  mov     ebx, 0C000009Ah
0x14007920b  jmp     loc_1400797E3
0x140079210  lea     rdx, [rbp+130h+SourceString]; SourceString
0x140079214  lea     rcx, [rbp+130h+DestinationString]; DestinationString
0x140079218  call    cs:__imp_RtlCopyUnicodeString
0x14007921f  nop     dword ptr [rax+rax+00h]
0x140079224  mov     rdx, rbx; Source
0x140079227  lea     rcx, [rbp+130h+DestinationString]; Destination
0x14007922b  call    cs:__imp_RtlAppendUnicodeStringToString
0x140079232  nop     dword ptr [rax+rax+00h]
0x140079237  lea     rdx, ?ndisParameterStr@@3U_UNICODE_STRING@@A; Source
0x14007923e  lea     rcx, [rbp+130h+DestinationString]; Destination
0x140079242  call    cs:__imp_RtlAppendUnicodeStringToString
0x140079249  nop     dword ptr [rax+rax+00h]
0x14007924e  lea     rdx, ?ndisFilterAdapterStr@@3U_UNICODE_STRING@@A; Source
0x140079255  lea     rcx, [rbp+130h+DestinationString]; Destination
0x140079259  call    cs:__imp_RtlAppendUnicodeStringToString
0x140079260  nop     dword ptr [rax+rax+00h]
0x140079265  lea     rdx, [rbp+130h+GuidString]; Source
0x140079269  lea     rcx, [rbp+130h+DestinationString]; Destination
0x14007926d  call    cs:__imp_RtlAppendUnicodeStringToString
0x140079274  nop     dword ptr [rax+rax+00h]
0x140079279  lea     rax, [rbp+130h+DestinationString]
0x14007927d  mov     [rbp+130h+ObjectAttributes.Length], 30h ; '0'
0x140079284  xorps   xmm0, xmm0
0x140079287  mov     [rbp+130h+ObjectAttributes.ObjectName], rax
0x14007928b  lea     r8, [rbp+130h+ObjectAttributes]; ObjectAttributes
0x14007928f  mov     [rbp+130h+ObjectAttributes.RootDirectory], r15
0x140079293  mov     edx, 40000000h; DesiredAccess
0x140079298  mov     [rbp+130h+ObjectAttributes.Attributes], 240h
0x14007929f  lea     rcx, [rbp+130h+KeyHandle]; KeyHandle
0x1400792a3  movdqu  xmmword ptr [rbp+130h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400792a8  call    cs:__imp_ZwOpenKey
0x1400792af  nop     dword ptr [rax+rax+00h]
0x1400792b4  test    eax, eax
0x1400792b6  jz      short loc_1400792C6
0x1400792b8  mov     [rbp+130h+KeyHandle], r15
0x1400792bc  mov     ebx, 0C0000001h
0x1400792c1  jmp     loc_14007982D
0x1400792c6  mov     rbx, [rsp+230h+var_1D8]
0x1400792cb  mov     rbx, [rbx+70h]
0x1400792cf  test    rbx, rbx
0x1400792d2  jz      short loc_1400792F0
0x1400792d4  mov     rdx, [rbx+10h]
0x1400792d8  mov     rax, [rdx+150h]
0x1400792df  mov     ecx, [rax+28h]
0x1400792e2  test    cl, 2
0x1400792e5  jz      short loc_140079359
0x1400792e7  mov     rbx, [rbx+70h]
0x1400792eb  test    rbx, rbx
0x1400792ee  jnz     short loc_1400792D4
0x1400792f0  lea     rcx, [rdi+0FA8h]; Guid
0x1400792f7  lea     rdx, [rbp+130h+UnicodeString]; GuidString
0x1400792fb  call    cs:__imp_RtlStringFromGUID
0x140079302  nop     dword ptr [rax+rax+00h]
0x140079307  test    eax, eax
0x140079309  jnz     loc_1400797DE
0x14007930f  movzx   eax, [rbp+130h+UnicodeString.Length]
0x140079313  mov     ecx, 40h ; '@'
0x140079318  mov     [rsp+230h+String1.Length], ax
0x14007931d  mov     r8d, 2020444Eh
0x140079323  movzx   eax, [rbp+130h+UnicodeString.MaximumLength]
0x140079327  mov     edx, eax
0x140079329  mov     [rsp+230h+String1.MaximumLength], ax
0x14007932e  call    cs:__imp_ExAllocatePool2
0x140079335  nop     dword ptr [rax+rax+00h]
0x14007933a  mov     [rsp+230h+String1.Buffer], rax
0x14007933f  test    rax, rax
0x140079342  jnz     short loc_1400793BB
0x140079344  lea     rcx, [rbp+130h+UnicodeString]; UnicodeString
0x140079348  call    cs:__imp_RtlFreeUnicodeString
0x14007934f  nop     dword ptr [rax+rax+00h]
0x140079354  jmp     loc_1400797DE
0x140079359  movzx   eax, word ptr [rdx+80h]
0x140079360  mov     ecx, 40h ; '@'
0x140079365  mov     [rsp+230h+String1.Length], ax
0x14007936a  mov     r8d, 2020444Eh
0x140079370  add     ax, 2
0x140079374  movzx   edx, ax
0x140079377  mov     [rsp+230h+String1.MaximumLength], dx
0x14007937c  call    cs:__imp_ExAllocatePool2
0x140079383  nop     dword ptr [rax+rax+00h]
0x140079388  mov     [rsp+230h+String1.Buffer], rax
0x14007938d  test    rax, rax
0x140079390  jnz     short loc_14007939C
0x140079392  mov     ebx, 0C000009Ah
0x140079397  jmp     loc_1400797E3
0x14007939c  mov     rdx, [rbx+10h]
0x1400793a0  mov     rcx, rax; void *
0x1400793a3  movzx   r8d, [rsp+230h+String1.Length]; Size
0x1400793a9  movzx   r14d, sil
0x1400793ad  mov     rdx, [rdx+88h]; Src
0x1400793b4  call    memmove
0x1400793b9  jmp     short loc_1400793F1
0x1400793bb  xor     r8d, r8d; AllocateDestinationString
0x1400793be  lea     rdx, [rbp+130h+UnicodeString]; SourceString
0x1400793c2  lea     rcx, [rsp+230h+String1]; DestinationString
0x1400793c7  movzx   r14d, sil
0x1400793cb  call    cs:__imp_RtlUpcaseUnicodeString
0x1400793d2  nop     dword ptr [rax+rax+00h]
0x1400793d7  lea     rcx, [rbp+130h+UnicodeString]; UnicodeString
0x1400793db  mov     ebx, eax
0x1400793dd  call    cs:__imp_RtlFreeUnicodeString
0x1400793e4  nop     dword ptr [rax+rax+00h]
0x1400793e9  test    ebx, ebx
0x1400793eb  jnz     loc_1400797DE
0x1400793f1  mov     edx, 218h
0x1400793f6  mov     ecx, 42h ; 'B'
0x1400793fb  mov     r8d, 2020444Eh
0x140079401  call    cs:__imp_ExAllocatePool2
0x140079408  nop     dword ptr [rax+rax+00h]
0x14007940d  mov     r15, rax
0x140079410  test    rax, rax
0x140079413  jnz     short loc_14007941F
0x140079415  mov     ebx, 0C000009Ah
0x14007941a  jmp     loc_1400797E3
0x14007941f  mov     [rbp+130h+var_194], 0
0x140079426  xor     ebx, ebx
0x140079428  mov     dword ptr [rsp+230h+var_1CC], 0
0x140079430  mov     [rbp+130h+var_190], ebx
0x140079433  cmp     ebx, 270Fh
0x140079439  ja      loc_140079606
0x14007943f  xor     edx, edx; Val
0x140079441  mov     r8d, 218h; Size
0x140079447  mov     rcx, r15; void *
0x14007944a  call    memset
0x14007944f  mov     rcx, [rbp+130h+KeyHandle]; KeyHandle
0x140079453  lea     rax, [rbp+130h+var_198]
0x140079457  mov     [rsp+230h+ResultLength], rax; ResultLength
0x14007945c  mov     r9, r15; KeyInformation
0x14007945f  xor     r8d, r8d; KeyInformationClass
0x140079462  mov     [rsp+230h+Length], 216h; Length
0x14007946a  mov     edx, ebx; Index
0x14007946c  mov     [rbp+130h+var_198], 0
0x140079473  call    cs:__imp_ZwEnumerateKey
0x14007947a  nop     dword ptr [rax+rax+00h]
0x14007947f  cmp     eax, 8000001Ah
0x140079484  jz      loc_140079606
0x14007948a  test    eax, eax
0x14007948c  jnz     loc_1400797DE
0x140079492  movzx   eax, word ptr [r15+0Ch]
0x140079497  lea     rbx, [r15+10h]
0x14007949b  mov     [rsp+230h+var_1B8.Length], ax
0x1400794a0  lea     rcx, [rbp+130h+var_F0]; void *
0x1400794a4  add     ax, 2
0x1400794a8  mov     [rbp+130h+var_1B8.Buffer], rbx
0x1400794ac  xor     edx, edx; Val
0x1400794ae  mov     [rsp+230h+var_1B8.MaximumLength], ax
0x1400794b3  mov     r8d, 0A8h; Size
0x1400794b9  call    memset
0x1400794be  mov     rax, [rsp+230h+var_1D8]
0x1400794c3  mov     [rbp+130h+var_E8], 1
0x1400794ca  mov     [rbp+130h+var_E0], rbx
0x1400794ce  mov     rcx, [rax+10h]
0x1400794d2  cmp     byte ptr [rcx+64h], 6
0x1400794d6  ja      short loc_1400794E0
0x1400794d8  jnz     short loc_1400794F2
0x1400794da  cmp     byte ptr [rcx+65h], 28h ; '('
0x1400794de  jb      short loc_1400794F2
0x1400794e0  mov     eax, 100h
0x1400794e5  mov     [rbp+130h+var_194], 1000000h
0x1400794ec  mov     dword ptr [rsp+230h+var_1CC], eax
0x1400794f0  jmp     short loc_1400794F6
0x1400794f2  mov     eax, dword ptr [rsp+230h+var_1CC]
0x1400794f6  mov     rdx, [rbp+130h+KeyHandle]
0x1400794fa  lea     r8, [rbp+130h+var_F0]
0x1400794fe  or      eax, 24h
0x140079501  mov     [rbp+130h+var_B8], 0
0x140079509  mov     [rbp+130h+var_B0], eax
0x14007950f  xor     r9d, r9d
0x140079512  lea     rax, ValueName; "LowerComponent"
0x140079519  mov     [rbp+130h+var_70], 0
0x140079524  mov     [rbp+130h+var_A8], rax
0x14007952b  mov     ecx, 40000000h
0x140079530  lea     rax, [rbp+130h+String2]
0x140079534  mov     qword ptr [rsp+230h+Length], 0
0x14007953d  mov     [rbp+130h+var_A0], rax
0x140079544  mov     eax, [rbp+130h+var_194]
0x140079547  mov     [rbp+130h+var_98], eax
0x14007954d  call    cs:__imp_RtlQueryRegistryValuesEx
0x140079554  nop     dword ptr [rax+rax+00h]
0x140079559  mov     ebx, eax
0x14007955b  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140079562  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140079569  jz      short loc_1400795A6
0x14007956b  mov     rcx, cs:WPP_GLOBAL_Control
0x140079572  mov     r9d, 64h ; 'd'; int
0x140079578  mov     eax, dword ptr [rsp+230h+var_1CC]
0x14007957c  mov     r8d, 1; int
0x140079582  mov     dword ptr [rsp+230h+var_200], eax; char
0x140079586  lea     rax, WPP_9524bb9419753e2807bcae08715ee655_Traceguids
0x14007958d  mov     dword ptr [rsp+230h+ResultLength], ebx; char
0x140079591  mov     rcx, [rcx+40h]; int
0x140079595  mov     qword ptr [rsp+230h+Length], rax; struct _GUID *
0x14007959a  call    WPP_RECORDER_SF_dd
0x14007959f  lea     rax, WPP_RECORDER_INITIALIZED
0x1400795a6  test    ebx, ebx
0x1400795a8  jnz     short loc_1400795FC
0x1400795aa  movzx   r8d, sil; CaseInSensitive
  ... truncated ...
```
