# ndisGetOrCreateFilterInstanceKey(_UNICODE_STRING const *,_NDIS_FILTER_BLOCK *,_NDIS_MINIPORT_BLOCK *,uchar,uchar *,_UNICODE_STRING *)

- ea: `0x140073960`
- end: `0x1400742ca`
- name: `?ndisGetOrCreateFilterInstanceKey@@YAHPEBU_UNICODE_STRING@@PEAU_NDIS_FILTER_BLOCK@@PEAU_NDIS_MINIPORT_BLOCK@@EPEAEPEAU1@@Z`
- size: `2410`
- prototype: `__int64 __usercall@<rax>(const struct _UNICODE_STRING *@<rcx>, struct _NDIS_FILTER_BLOCK *@<rdx>, struct _NDIS_MINIPORT_BLOCK *@<r8>, unsigned __int8@<r9b>, unsigned __int8 *, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140048d20`
- `0x140084d60`

## callees

- `0x14002b980`
- `0x1400472e0`
- `0x140060a10`
- `0x140070560`
- `0x140073960`
- `0x1400e6160`
- `0x1400e62c0`
- `0x1400e65c0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140073b38`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140074014`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140073b38`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140074014`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140073b4b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140073b62`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140073b79`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140073b8d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007402a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140074040`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140074053`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140074066`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007407a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140073b4b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140073b62`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140073b79`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140073b8d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007402a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140074040`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140074053`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140074066`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14007407a`
- `ntoskrnl!RtlStringFromGUID` at `0x140073ac2`
- `ntoskrnl!RtlStringFromGUID` at `0x140073c1b`
- `ntoskrnl!RtlStringFromGUID` at `0x140073ac2`
- `ntoskrnl!RtlStringFromGUID` at `0x140073c1b`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140073c68`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140073cfd`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140074151`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140073c68`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140073cfd`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140074151`
- `ntoskrnl!ZwOpenKey` at `0x140073bc8`
- `ntoskrnl!ZwOpenKey` at `0x140073bc8`
- `ntoskrnl!ZwClose` at `0x140074124`
- `ntoskrnl!ZwClose` at `0x140074124`
- `ntoskrnl!ZwEnumerateKey` at `0x140073d93`
- `ntoskrnl!ZwEnumerateKey` at `0x140073d93`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140073e6d`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140073e6d`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1400740d4`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1400740d4`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140073ceb`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140073ceb`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140073ed7`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140073ed7`
- `ntoskrnl!RtlCreateRegistryKey` at `0x140074097`
- `ntoskrnl!RtlCreateRegistryKey` at `0x140074097`
- `ntoskrnl!ExFreePoolWithTag` at `0x140073ef2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400740ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x140074180`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400741b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400741df`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007420d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007423c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140073ef2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400740ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x140074180`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400741b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400741df`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007420d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007423c`
- `ntoskrnl!ExAllocatePool2` at `0x140073b11`
- `ntoskrnl!ExAllocatePool2` at `0x140073c4e`
- `ntoskrnl!ExAllocatePool2` at `0x140073c9c`
- `ntoskrnl!ExAllocatePool2` at `0x140073d21`
- `ntoskrnl!ExAllocatePool2` at `0x140073f64`
- `ntoskrnl!ExAllocatePool2` at `0x140073fe4`
- `ntoskrnl!ExAllocatePool2` at `0x140073b11`
- `ntoskrnl!ExAllocatePool2` at `0x140073c4e`
- `ntoskrnl!ExAllocatePool2` at `0x140073c9c`
- `ntoskrnl!ExAllocatePool2` at `0x140073d21`
- `ntoskrnl!ExAllocatePool2` at `0x140073f64`
- `ntoskrnl!ExAllocatePool2` at `0x140073fe4`

## string_xrefs

- `0x140073997`: `\Registry\Machine\System\CurrentControlSet\Services\`
- `0x140073e32`: `LowerComponent`
- `0x1400740b0`: `LowerComponent`

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
0x140073960  mov     [rsp-8+arg_18], rbx
0x140073965  push    rbp
0x140073966  push    rsi
0x140073967  push    rdi
0x140073968  push    r12
0x14007396a  push    r13
0x14007396c  push    r14
0x14007396e  push    r15
0x140073970  lea     rbp, [rsp-100h]
0x140073978  sub     rsp, 200h
0x14007397f  mov     rax, cs:__security_cookie
0x140073986  xor     rax, rsp
0x140073989  mov     [rbp+130h+var_40], rax
0x140073990  mov     rbx, [rbp+130h+arg_20]
0x140073997  lea     rax, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x14007399e  mov     r13, [rbp+130h+Destination]
0x1400739a5  xorps   xmm0, xmm0
0x1400739a8  mov     rdi, r8
0x1400739ab  mov     [rsp+230h+var_1D8], rdx
0x1400739b0  mov     r8, rdx
0x1400739b3  mov     [rbp+130h+SourceString.Buffer], rax
0x1400739b7  mov     rdx, rcx
0x1400739ba  mov     [rsp+230h+Source], rcx
0x1400739bf  xor     ecx, ecx
0x1400739c1  mov     [rsp+230h+var_1D0], r9b
0x1400739c6  lea     rax, asc_1400F6810; "\\"
0x1400739cd  mov     qword ptr [rbp+130h+GuidString.Length], rcx
0x1400739d1  xor     sil, sil
0x1400739d4  mov     [rbp+130h+GuidString.Buffer], rcx
0x1400739d8  xor     r14b, r14b
0x1400739db  mov     qword ptr [rbp+130h+DestinationString.Length], rcx
0x1400739df  mov     [rbp+130h+DestinationString.Buffer], rcx
0x1400739e3  xor     r12b, r12b
0x1400739e6  mov     [rbp+130h+var_138.Buffer], rax
0x1400739ea  mov     r15d, ecx
0x1400739ed  mov     qword ptr [rsp+230h+String1.Length], rcx
0x1400739f2  mov     [rsp+230h+String1.Buffer], rcx
0x1400739f7  mov     qword ptr [rbp+130h+UnicodeString.Length], rcx
0x1400739fb  mov     [rbp+130h+UnicodeString.Buffer], rcx
0x1400739ff  mov     [rbp+130h+KeyHandle], rcx
0x140073a03  mov     [rbp+130h+var_198], ecx
0x140073a06  mov     qword ptr [rsp+230h+var_1B8.Length], rcx
0x140073a0b  mov     [rbp+130h+var_1B8.Buffer], rcx
0x140073a0f  mov     qword ptr [rbp+130h+String2.Length], rcx
0x140073a13  mov     [rbp+130h+String2.Buffer], rcx
0x140073a17  mov     [rbp+130h+var_150], rbx
0x140073a1b  mov     qword ptr [rbp+130h+SourceString.Length], 6A0068h
0x140073a23  mov     qword ptr [rbp+130h+var_138.Length], 40002h
0x140073a2b  movups  xmmword ptr [rbp+130h+ObjectAttributes.Length], xmm0
0x140073a2f  movups  xmmword ptr [rbp+130h+ObjectAttributes.ObjectName], xmm0
0x140073a33  movups  xmmword ptr [rbp+130h+ObjectAttributes.SecurityDescriptor], xmm0
0x140073a37  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140073a3e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140073a45  lea     r10, WPP_9524bb9419753e2807bcae08715ee655_Traceguids
0x140073a4c  jz      short loc_140073A98
0x140073a4e  mov     rcx, cs:WPP_GLOBAL_Control
0x140073a55  mov     r9d, 63h ; 'c'; int
0x140073a5b  mov     qword ptr [rsp+230h+var_1F8], r8; char
0x140073a60  mov     r8d, 1; int
0x140073a66  mov     qword ptr [rsp+230h+var_200], rdi; char
0x140073a6b  mov     [rsp+230h+ResultLength], rdx; char
0x140073a70  mov     dl, 4; int
0x140073a72  mov     rcx, [rcx+40h]; int
0x140073a76  mov     qword ptr [rsp+230h+Length], r10; struct _GUID *
0x140073a7b  call    WPP_RECORDER_SF_qqq
0x140073a80  mov     rdx, [rsp+230h+Source]
0x140073a85  lea     rax, WPP_RECORDER_INITIALIZED
0x140073a8c  mov     r8, [rsp+230h+var_1D8]
0x140073a91  lea     r10, WPP_9524bb9419753e2807bcae08715ee655_Traceguids
0x140073a98  cmp     [rdi+10h], r15
0x140073a9c  jnz     short loc_140073AA8
0x140073a9e  mov     ebx, 0C000000Dh
0x140073aa3  jmp     loc_14007411B
0x140073aa8  mov     [rbx], sil
0x140073aab  lea     rdx, [rbp+130h+GuidString]; GuidString
0x140073aaf  xorps   xmm0, xmm0
0x140073ab2  movups  xmmword ptr [r13+0], xmm0
0x140073ab7  mov     rcx, [rdi+10h]
0x140073abb  add     rcx, 0FA8h; Guid
0x140073ac2  call    cs:__imp_RtlStringFromGUID
0x140073ac9  nop     dword ptr [rax+rax+00h]
0x140073ace  test    eax, eax
0x140073ad0  jnz     loc_1400740FE
0x140073ad6  mov     rbx, [rsp+230h+Source]
0x140073adb  mov     ecx, 40h ; '@'
0x140073ae0  mov     [rbp+130h+DestinationString.Length], ax
0x140073ae4  mov     r8d, 2020444Eh
0x140073aea  mov     sil, 1
0x140073aed  movzx   eax, word ptr [rbx]
0x140073af0  add     ax, 2
0x140073af4  add     ax, cs:?ndisFilterAdapterStr@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING ndisFilterAdapterStr ...
0x140073afb  add     ax, cs:?ndisParameterStr@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING ndisParameterStr ...
0x140073b02  add     ax, [rbp+130h+SourceString.Length]
0x140073b06  add     ax, [rbp+130h+GuidString.Length]
0x140073b0a  movzx   edx, ax
0x140073b0d  mov     [rbp+130h+DestinationString.MaximumLength], dx
0x140073b11  call    cs:__imp_ExAllocatePool2
0x140073b18  nop     dword ptr [rax+rax+00h]
0x140073b1d  mov     [rbp+130h+DestinationString.Buffer], rax
0x140073b21  test    rax, rax
0x140073b24  jnz     short loc_140073B30
0x140073b26  mov     ebx, 0C000009Ah
0x140073b2b  jmp     loc_140074103
0x140073b30  lea     rdx, [rbp+130h+SourceString]; SourceString
0x140073b34  lea     rcx, [rbp+130h+DestinationString]; DestinationString
0x140073b38  call    cs:__imp_RtlCopyUnicodeString
0x140073b3f  nop     dword ptr [rax+rax+00h]
0x140073b44  mov     rdx, rbx; Source
0x140073b47  lea     rcx, [rbp+130h+DestinationString]; Destination
0x140073b4b  call    cs:__imp_RtlAppendUnicodeStringToString
0x140073b52  nop     dword ptr [rax+rax+00h]
0x140073b57  lea     rdx, ?ndisParameterStr@@3U_UNICODE_STRING@@A; Source
0x140073b5e  lea     rcx, [rbp+130h+DestinationString]; Destination
0x140073b62  call    cs:__imp_RtlAppendUnicodeStringToString
0x140073b69  nop     dword ptr [rax+rax+00h]
0x140073b6e  lea     rdx, ?ndisFilterAdapterStr@@3U_UNICODE_STRING@@A; Source
0x140073b75  lea     rcx, [rbp+130h+DestinationString]; Destination
0x140073b79  call    cs:__imp_RtlAppendUnicodeStringToString
0x140073b80  nop     dword ptr [rax+rax+00h]
0x140073b85  lea     rdx, [rbp+130h+GuidString]; Source
0x140073b89  lea     rcx, [rbp+130h+DestinationString]; Destination
0x140073b8d  call    cs:__imp_RtlAppendUnicodeStringToString
0x140073b94  nop     dword ptr [rax+rax+00h]
0x140073b99  lea     rax, [rbp+130h+DestinationString]
0x140073b9d  mov     [rbp+130h+ObjectAttributes.Length], 30h ; '0'
0x140073ba4  xorps   xmm0, xmm0
0x140073ba7  mov     [rbp+130h+ObjectAttributes.ObjectName], rax
0x140073bab  lea     r8, [rbp+130h+ObjectAttributes]; ObjectAttributes
0x140073baf  mov     [rbp+130h+ObjectAttributes.RootDirectory], r15
0x140073bb3  mov     edx, 40000000h; DesiredAccess
0x140073bb8  mov     [rbp+130h+ObjectAttributes.Attributes], 240h
0x140073bbf  lea     rcx, [rbp+130h+KeyHandle]; KeyHandle
0x140073bc3  movdqu  xmmword ptr [rbp+130h+ObjectAttributes.SecurityDescriptor], xmm0
0x140073bc8  call    cs:__imp_ZwOpenKey
0x140073bcf  nop     dword ptr [rax+rax+00h]
0x140073bd4  test    eax, eax
0x140073bd6  jz      short loc_140073BE6
0x140073bd8  mov     [rbp+130h+KeyHandle], r15
0x140073bdc  mov     ebx, 0C0000001h
0x140073be1  jmp     loc_14007414D
0x140073be6  mov     rbx, [rsp+230h+var_1D8]
0x140073beb  mov     rbx, [rbx+70h]
0x140073bef  test    rbx, rbx
0x140073bf2  jz      short loc_140073C10
0x140073bf4  mov     rdx, [rbx+10h]
0x140073bf8  mov     rax, [rdx+150h]
0x140073bff  mov     ecx, [rax+28h]
0x140073c02  test    cl, 2
0x140073c05  jz      short loc_140073C79
0x140073c07  mov     rbx, [rbx+70h]
0x140073c0b  test    rbx, rbx
0x140073c0e  jnz     short loc_140073BF4
0x140073c10  lea     rcx, [rdi+0FA8h]; Guid
0x140073c17  lea     rdx, [rbp+130h+UnicodeString]; GuidString
0x140073c1b  call    cs:__imp_RtlStringFromGUID
0x140073c22  nop     dword ptr [rax+rax+00h]
0x140073c27  test    eax, eax
0x140073c29  jnz     loc_1400740FE
0x140073c2f  movzx   eax, [rbp+130h+UnicodeString.Length]
0x140073c33  mov     ecx, 40h ; '@'
0x140073c38  mov     [rsp+230h+String1.Length], ax
0x140073c3d  mov     r8d, 2020444Eh
0x140073c43  movzx   eax, [rbp+130h+UnicodeString.MaximumLength]
0x140073c47  mov     edx, eax
0x140073c49  mov     [rsp+230h+String1.MaximumLength], ax
0x140073c4e  call    cs:__imp_ExAllocatePool2
0x140073c55  nop     dword ptr [rax+rax+00h]
0x140073c5a  mov     [rsp+230h+String1.Buffer], rax
0x140073c5f  test    rax, rax
0x140073c62  jnz     short loc_140073CDB
0x140073c64  lea     rcx, [rbp+130h+UnicodeString]; UnicodeString
0x140073c68  call    cs:__imp_RtlFreeUnicodeString
0x140073c6f  nop     dword ptr [rax+rax+00h]
0x140073c74  jmp     loc_1400740FE
0x140073c79  movzx   eax, word ptr [rdx+80h]
0x140073c80  mov     ecx, 40h ; '@'
0x140073c85  mov     [rsp+230h+String1.Length], ax
0x140073c8a  mov     r8d, 2020444Eh
0x140073c90  add     ax, 2
0x140073c94  movzx   edx, ax
0x140073c97  mov     [rsp+230h+String1.MaximumLength], dx
0x140073c9c  call    cs:__imp_ExAllocatePool2
0x140073ca3  nop     dword ptr [rax+rax+00h]
0x140073ca8  mov     [rsp+230h+String1.Buffer], rax
0x140073cad  test    rax, rax
0x140073cb0  jnz     short loc_140073CBC
0x140073cb2  mov     ebx, 0C000009Ah
0x140073cb7  jmp     loc_140074103
0x140073cbc  mov     rdx, [rbx+10h]
0x140073cc0  mov     rcx, rax; void *
0x140073cc3  movzx   r8d, [rsp+230h+String1.Length]; Size
0x140073cc9  movzx   r14d, sil
0x140073ccd  mov     rdx, [rdx+88h]; Src
0x140073cd4  call    memmove
0x140073cd9  jmp     short loc_140073D11
0x140073cdb  xor     r8d, r8d; AllocateDestinationString
0x140073cde  lea     rdx, [rbp+130h+UnicodeString]; SourceString
0x140073ce2  lea     rcx, [rsp+230h+String1]; DestinationString
0x140073ce7  movzx   r14d, sil
0x140073ceb  call    cs:__imp_RtlUpcaseUnicodeString
0x140073cf2  nop     dword ptr [rax+rax+00h]
0x140073cf7  lea     rcx, [rbp+130h+UnicodeString]; UnicodeString
0x140073cfb  mov     ebx, eax
0x140073cfd  call    cs:__imp_RtlFreeUnicodeString
0x140073d04  nop     dword ptr [rax+rax+00h]
0x140073d09  test    ebx, ebx
0x140073d0b  jnz     loc_1400740FE
0x140073d11  mov     edx, 218h
0x140073d16  mov     ecx, 42h ; 'B'
0x140073d1b  mov     r8d, 2020444Eh
0x140073d21  call    cs:__imp_ExAllocatePool2
0x140073d28  nop     dword ptr [rax+rax+00h]
0x140073d2d  mov     r15, rax
0x140073d30  test    rax, rax
0x140073d33  jnz     short loc_140073D3F
0x140073d35  mov     ebx, 0C000009Ah
0x140073d3a  jmp     loc_140074103
0x140073d3f  mov     [rbp+130h+var_194], 0
0x140073d46  xor     ebx, ebx
0x140073d48  mov     dword ptr [rsp+230h+var_1CC], 0
0x140073d50  mov     [rbp+130h+var_190], ebx
0x140073d53  cmp     ebx, 270Fh
0x140073d59  ja      loc_140073F26
0x140073d5f  xor     edx, edx; Val
0x140073d61  mov     r8d, 218h; Size
0x140073d67  mov     rcx, r15; void *
0x140073d6a  call    memset
0x140073d6f  mov     rcx, [rbp+130h+KeyHandle]; KeyHandle
0x140073d73  lea     rax, [rbp+130h+var_198]
0x140073d77  mov     [rsp+230h+ResultLength], rax; ResultLength
0x140073d7c  mov     r9, r15; KeyInformation
0x140073d7f  xor     r8d, r8d; KeyInformationClass
0x140073d82  mov     [rsp+230h+Length], 216h; Length
0x140073d8a  mov     edx, ebx; Index
0x140073d8c  mov     [rbp+130h+var_198], 0
0x140073d93  call    cs:__imp_ZwEnumerateKey
0x140073d9a  nop     dword ptr [rax+rax+00h]
0x140073d9f  cmp     eax, 8000001Ah
0x140073da4  jz      loc_140073F26
0x140073daa  test    eax, eax
0x140073dac  jnz     loc_1400740FE
0x140073db2  movzx   eax, word ptr [r15+0Ch]
0x140073db7  lea     rbx, [r15+10h]
0x140073dbb  mov     [rsp+230h+var_1B8.Length], ax
0x140073dc0  lea     rcx, [rbp+130h+var_F0]; void *
0x140073dc4  add     ax, 2
0x140073dc8  mov     [rbp+130h+var_1B8.Buffer], rbx
0x140073dcc  xor     edx, edx; Val
0x140073dce  mov     [rsp+230h+var_1B8.MaximumLength], ax
0x140073dd3  mov     r8d, 0A8h; Size
0x140073dd9  call    memset
0x140073dde  mov     rax, [rsp+230h+var_1D8]
0x140073de3  mov     [rbp+130h+var_E8], 1
0x140073dea  mov     [rbp+130h+var_E0], rbx
0x140073dee  mov     rcx, [rax+10h]
0x140073df2  cmp     byte ptr [rcx+64h], 6
0x140073df6  ja      short loc_140073E00
0x140073df8  jnz     short loc_140073E12
0x140073dfa  cmp     byte ptr [rcx+65h], 28h ; '('
0x140073dfe  jb      short loc_140073E12
0x140073e00  mov     eax, 100h
0x140073e05  mov     [rbp+130h+var_194], 1000000h
0x140073e0c  mov     dword ptr [rsp+230h+var_1CC], eax
0x140073e10  jmp     short loc_140073E16
0x140073e12  mov     eax, dword ptr [rsp+230h+var_1CC]
0x140073e16  mov     rdx, [rbp+130h+KeyHandle]
0x140073e1a  lea     r8, [rbp+130h+var_F0]
0x140073e1e  or      eax, 24h
0x140073e21  mov     [rbp+130h+var_B8], 0
0x140073e29  mov     [rbp+130h+var_B0], eax
0x140073e2f  xor     r9d, r9d
0x140073e32  lea     rax, ValueName; "LowerComponent"
0x140073e39  mov     [rbp+130h+var_70], 0
0x140073e44  mov     [rbp+130h+var_A8], rax
0x140073e4b  mov     ecx, 40000000h
0x140073e50  lea     rax, [rbp+130h+String2]
0x140073e54  mov     qword ptr [rsp+230h+Length], 0
0x140073e5d  mov     [rbp+130h+var_A0], rax
0x140073e64  mov     eax, [rbp+130h+var_194]
0x140073e67  mov     [rbp+130h+var_98], eax
0x140073e6d  call    cs:__imp_RtlQueryRegistryValuesEx
0x140073e74  nop     dword ptr [rax+rax+00h]
0x140073e79  mov     ebx, eax
0x140073e7b  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140073e82  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140073e89  jz      short loc_140073EC6
0x140073e8b  mov     rcx, cs:WPP_GLOBAL_Control
0x140073e92  mov     r9d, 64h ; 'd'; int
0x140073e98  mov     eax, dword ptr [rsp+230h+var_1CC]
0x140073e9c  mov     r8d, 1; int
0x140073ea2  mov     dword ptr [rsp+230h+var_200], eax; char
0x140073ea6  lea     rax, WPP_9524bb9419753e2807bcae08715ee655_Traceguids
0x140073ead  mov     dword ptr [rsp+230h+ResultLength], ebx; char
0x140073eb1  mov     rcx, [rcx+40h]; int
0x140073eb5  mov     qword ptr [rsp+230h+Length], rax; struct _GUID *
0x140073eba  call    WPP_RECORDER_SF_dd
0x140073ebf  lea     rax, WPP_RECORDER_INITIALIZED
0x140073ec6  test    ebx, ebx
0x140073ec8  jnz     short loc_140073F1C
0x140073eca  movzx   r8d, sil; CaseInSensitive
  ... truncated ...
```
