# KsCacheMedium

- ea: `0x1800340d0`
- end: `0x180034590`
- name: `KsCacheMedium`
- size: `1216`
- prototype: `NTSTATUS __stdcall(PUNICODE_STRING SymbolicLink, PKSPIN_MEDIUM Medium, ULONG PinDirection)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003dd90`
- `0x180058254`

## callees

- `0x18000c058`
- `0x180010bf8`
- `0x180019b80`
- `0x180019fc0`
- `0x1800340d0`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x180034313`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180034313`
- `ntoskrnl!ZwCreateKey` at `0x180034280`
- `ntoskrnl!ZwCreateKey` at `0x1800343e9`
- `ntoskrnl!ZwCreateKey` at `0x180034280`
- `ntoskrnl!ZwCreateKey` at `0x1800343e9`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1800341c4`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1800341c4`
- `ntoskrnl!RtlStringFromGUID` at `0x1800342e9`
- `ntoskrnl!RtlStringFromGUID` at `0x1800342e9`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x180034344`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x180034384`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x180034344`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x180034384`
- `ntoskrnl!ZwClose` at `0x1800342bf`
- `ntoskrnl!ZwClose` at `0x180034545`
- `ntoskrnl!ZwClose` at `0x1800342bf`
- `ntoskrnl!ZwClose` at `0x180034545`
- `ntoskrnl!ZwSetValueKey` at `0x180034482`
- `ntoskrnl!ZwSetValueKey` at `0x180034482`
- `ntoskrnl!RtlCompareMemory` at `0x180034410`
- `ntoskrnl!RtlCompareMemory` at `0x180034410`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18003422f`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1800342d6`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18003432a`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18003436f`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18003422f`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1800342d6`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18003432a`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18003436f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x180034303`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x180034358`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x180034398`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x180034303`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x180034358`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x180034398`
- `ntoskrnl!ExFreePoolWithTag` at `0x180034297`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800342a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003455b`
- `ntoskrnl!ExFreePoolWithTag` at `0x180034297`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800342a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003455b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180034184`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800341de`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x180034184`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800341de`

## string_xrefs

- `0x180034218`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\MediumCache`

## pseudocode

```c
NTSTATUS __stdcall KsCacheMedium(PUNICODE_STRING SymbolicLink, PKSPIN_MEDIUM Medium, ULONG PinDirection)
{
  NTSTATUS result; // eax
  __int64 v6; // rbx
  wchar_t *PoolWithTag; // rax
  wchar_t *v8; // rdi
  wchar_t *v9; // rax
  wchar_t *v10; // r14
  int v11; // ebx
  bool v12; // zf
  wchar_t *Buffer; // rax
  wchar_t *v14; // rcx
  _WORD *v15; // rdx
  __int16 v16; // ax
  NTSTATUS v17; // eax
  int v18; // edx
  int v19; // r8d
  int Class; // [rsp+20h] [rbp-99h]
  UNICODE_STRING Destination; // [rsp+40h] [rbp-79h] BYREF
  ULONG Disposition; // [rsp+50h] [rbp-69h] BYREF
  void *KeyHandle; // [rsp+58h] [rbp-61h] BYREF
  UNICODE_STRING DestinationString; // [rsp+60h] [rbp-59h] BYREF
  ULONG Data; // [rsp+70h] [rbp-49h] BYREF
  UNICODE_STRING String; // [rsp+78h] [rbp-41h] BYREF
  UNICODE_STRING GuidString; // [rsp+88h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-21h] BYREF
  char v29; // [rsp+C8h] [rbp+Fh] BYREF

  Data = PinDirection;
  result = 0;
  KeyHandle = 0;
  Disposition = 0;
  memset(&ObjectAttributes, 0, 44);
  GuidString = 0;
  Destination = 0;
  String = 0;
  DestinationString = 0;
  if ( !Medium
    || Medium->Alignment == *(_QWORD *)&KSMEDIUMSETID_Standard.Data1
    && *(&Medium->Alignment + 1) == *(_QWORD *)KSMEDIUMSETID_Standard.Data4
    || Medium->Alignment == *(_QWORD *)&GUID_NULL.Data1 && *(&Medium->Alignment + 1) == *(_QWORD *)GUID_NULL.Data4 )
  {
    return result;
  }
  v6 = 512;
  PoolWithTag = (wchar_t *)ExAllocatePoolWithTag((POOL_TYPE)1025, 0x200u, 0x636D534Bu);
  v8 = PoolWithTag;
  if ( !PoolWithTag )
    return -1073741670;
  if ( !ExPoolZeroingNativelySupported )
    memset(PoolWithTag, 0, 0x200u);
  *(_DWORD *)&DestinationString.Length = 0x2000000;
  DestinationString.Buffer = v8;
  RtlCopyUnicodeString(&DestinationString, SymbolicLink);
  v9 = (wchar_t *)ExAllocatePoolWithTag(PagedPool, 0x200u, 0x636D534Bu);
  v10 = v9;
  if ( !v9 )
  {
    ExFreePoolWithTag(v8, 0);
    return -1073741670;
  }
  *(_DWORD *)&Destination.Length = 0x2000000;
  Destination.Buffer = v9;
  do
  {
    *(_BYTE *)v9 = 0;
    v9 = (wchar_t *)((char *)v9 + 1);
    --v6;
  }
  while ( v6 );
  *(_DWORD *)&String.Length = 0x200000;
  String.Buffer = (wchar_t *)&v29;
  *(_DWORD *)&GuidString.Length = 0;
  GuidString.Buffer = 0;
  RtlAppendUnicodeToString(&Destination, L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control\\MediumCache");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &Destination;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v11 = ZwCreateKey(&KeyHandle, 0xF003Fu, &ObjectAttributes, 0, 0, 0, &Disposition);
  if ( v11 >= 0 )
  {
    ZwClose(KeyHandle);
    RtlAppendUnicodeToString(&Destination, L"\\");
    v11 = RtlStringFromGUID(&Medium->Set, &GuidString);
    if ( v11 >= 0 )
    {
      RtlAppendUnicodeStringToString(&Destination, &GuidString);
      RtlFreeUnicodeString(&GuidString);
      RtlAppendUnicodeToString(&Destination, L"-");
      RtlIntegerToUnicodeString(Medium->Id, 0x10u, &String);
      RtlAppendUnicodeStringToString(&Destination, &String);
      RtlAppendUnicodeToString(&Destination, L"-");
      RtlIntegerToUnicodeString(Medium->Flags, 0x10u, &String);
      RtlAppendUnicodeStringToString(&Destination, &String);
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &Destination;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v11 = ZwCreateKey(&KeyHandle, 0xF003Fu, &ObjectAttributes, 0, 0, 0, &Disposition);
      if ( v11 >= 0 )
      {
        v12 = (unsigned int)RtlCompareMemory(DestinationString.Buffer, L"\\DosDevices", 0x16u) == 22;
        Buffer = DestinationString.Buffer;
        if ( v12 )
        {
          v14 = DestinationString.Buffer + 11;
          *(_QWORD *)DestinationString.Buffer = 0x2E005C005CLL;
          v15 = Buffer + 3;
          do
          {
            v16 = *v14++;
            *v15++ = v16;
          }
          while ( v16 );
        }
        else if ( DestinationString.Buffer[1] == 63 && DestinationString.Buffer[2] == 63 )
        {
          DestinationString.Buffer[1] = 92;
        }
        v17 = ZwSetValueKey(KeyHandle, &DestinationString, 0, 4u, &Data, 4u);
        v11 = v17;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
          {
            LOBYTE(v18) = 5;
            WPP_RECORDER_SF_d(
              WPP_GLOBAL_Control->DeviceExtension,
              v18,
              v19,
              17,
              (__int64)WPP_0de5e70475493ec6bd40349f10325ac4_Traceguids,
              v17);
          }
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
              WPP_RECORDER_SF_Sd(
                WPP_GLOBAL_Control->DeviceExtension,
                v18,
                v19,
                18,
                Class,
                (__int64)Destination.Buffer,
                Destination.Length);
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
                WPP_RECORDER_SF_Sd(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v18,
                  v19,
                  19,
                  Class,
                  (__int64)DestinationString.Buffer,
                  DestinationString.Length);
            }
          }
        }
        ZwClose(KeyHandle);
      }
    }
  }
  ExFreePoolWithTag(v8, 0);
  ExFreePoolWithTag(v10, 0);
  return v11;
}

```

## disassembly

```asm
0x1800340d0  mov     [rsp-8+arg_18], rbx
0x1800340d5  push    rbp
0x1800340d6  push    rsi
0x1800340d7  push    rdi
0x1800340d8  push    r14
0x1800340da  push    r15
0x1800340dc  lea     rbp, [rsp-37h]
0x1800340e1  sub     rsp, 0F0h
0x1800340e8  mov     rax, cs:__security_cookie
0x1800340ef  xor     rax, rsp
0x1800340f2  mov     [rbp+57h+var_28], rax
0x1800340f6  xorps   xmm0, xmm0
0x1800340f9  mov     [rbp+57h+Data], r8d
0x1800340fd  xor     r15d, r15d
0x180034100  xorps   xmm1, xmm1
0x180034103  xor     eax, eax
0x180034105  mov     [rbp+57h+KeyHandle], r15
0x180034109  mov     [rbp+57h+var_C0], r15d
0x18003410d  mov     rsi, rdx
0x180034110  mov     r14, rcx
0x180034113  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180034117  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18003411b  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18003411f  movups  xmmword ptr [rbp+57h+GuidString.Length], xmm0
0x180034123  movups  xmmword ptr [rbp+57h+Destination.Length], xmm1
0x180034127  movups  xmmword ptr [rbp+57h+String.Length], xmm0
0x18003412b  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x18003412f  test    rdx, rdx
0x180034132  jz      loc_18003456C
0x180034138  mov     rcx, [rdx]
0x18003413b  cmp     rcx, qword ptr cs:KSMEDIUMSETID_Standard.Data1
0x180034142  jnz     short loc_180034155
0x180034144  mov     rcx, [rdx+8]
0x180034148  cmp     rcx, qword ptr cs:KSMEDIUMSETID_Standard.Data4
0x18003414f  jz      loc_18003456C
0x180034155  mov     rcx, [rdx]
0x180034158  cmp     rcx, qword ptr cs:GUID_NULL.Data1
0x18003415f  jnz     short loc_180034172
0x180034161  mov     rcx, [rdx+8]
0x180034165  cmp     rcx, qword ptr cs:GUID_NULL.Data4
0x18003416c  jz      loc_18003456C
0x180034172  mov     ebx, 200h
0x180034177  mov     r8d, 636D534Bh; Tag
0x18003417d  mov     edx, ebx; NumberOfBytes
0x18003417f  mov     ecx, 401h; PoolType
0x180034184  call    cs:__imp_ExAllocatePoolWithTag
0x18003418b  nop     dword ptr [rax+rax+00h]
0x180034190  mov     rdi, rax
0x180034193  test    rax, rax
0x180034196  jz      loc_180034567
0x18003419c  cmp     cs:ExPoolZeroingNativelySupported, r15b
0x1800341a3  jnz     short loc_1800341B2
0x1800341a5  mov     r8d, ebx; Size
0x1800341a8  xor     edx, edx; Val
0x1800341aa  mov     rcx, rax; void *
0x1800341ad  call    memset
0x1800341b2  mov     rdx, r14; SourceString
0x1800341b5  mov     dword ptr [rbp+57h+DestinationString.Length], 2000000h
0x1800341bc  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800341c0  mov     [rbp+57h+DestinationString.Buffer], rdi
0x1800341c4  call    cs:__imp_RtlCopyUnicodeString
0x1800341cb  nop     dword ptr [rax+rax+00h]
0x1800341d0  mov     r8d, 636D534Bh; Tag
0x1800341d6  mov     rdx, rbx; NumberOfBytes
0x1800341d9  mov     ecx, 1; PoolType
0x1800341de  call    cs:__imp_ExAllocatePoolWithTag
0x1800341e5  nop     dword ptr [rax+rax+00h]
0x1800341ea  mov     r14, rax
0x1800341ed  test    rax, rax
0x1800341f0  jz      loc_180034556
0x1800341f6  mov     dword ptr [rbp+57h+Destination.Length], 2000000h
0x1800341fd  mov     [rbp+57h+Destination.Buffer], rax
0x180034201  mov     [rax], r15b
0x180034204  inc     rax
0x180034207  sub     rbx, 1
0x18003420b  jnz     short loc_180034201
0x18003420d  lea     rax, [rbp+57h+var_48]
0x180034211  mov     dword ptr [rbp+57h+String.Length], 200000h
0x180034218  lea     rdx, Source; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x18003421f  mov     [rbp+57h+String.Buffer], rax
0x180034223  lea     rcx, [rbp+57h+Destination]; Destination
0x180034227  mov     dword ptr [rbp+57h+GuidString.Length], r15d
0x18003422b  mov     [rbp+57h+GuidString.Buffer], r15
0x18003422f  call    cs:__imp_RtlAppendUnicodeToString
0x180034236  nop     dword ptr [rax+rax+00h]
0x18003423b  lea     rax, [rbp+57h+Destination]
0x18003423f  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180034246  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18003424a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18003424e  lea     rax, [rbp+57h+var_C0]
0x180034252  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x180034256  mov     [rsp+110h+Disposition], rax; Disposition
0x18003425b  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18003425f  xorps   xmm0, xmm0
0x180034262  mov     [rsp+110h+CreateOptions], r15d; CreateOptions
0x180034267  xor     r9d, r9d; TitleIndex
0x18003426a  mov     [rsp+110h+Class], r15; Class
0x18003426f  mov     edx, 0F003Fh; DesiredAccess
0x180034274  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x18003427b  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180034280  call    cs:__imp_ZwCreateKey
0x180034287  nop     dword ptr [rax+rax+00h]
0x18003428c  mov     ebx, eax
0x18003428e  test    eax, eax
0x180034290  jns     short loc_1800342BB
0x180034292  xor     edx, edx; Tag
0x180034294  mov     rcx, rdi; P
0x180034297  call    cs:__imp_ExFreePoolWithTag
0x18003429e  nop     dword ptr [rax+rax+00h]
0x1800342a3  xor     edx, edx; Tag
0x1800342a5  mov     rcx, r14; P
0x1800342a8  call    cs:__imp_ExFreePoolWithTag
0x1800342af  nop     dword ptr [rax+rax+00h]
0x1800342b4  mov     eax, ebx
0x1800342b6  jmp     loc_18003456C
0x1800342bb  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1800342bf  call    cs:__imp_ZwClose
0x1800342c6  nop     dword ptr [rax+rax+00h]
0x1800342cb  lea     rdx, asc_18001DB50; "\\"
0x1800342d2  lea     rcx, [rbp+57h+Destination]; Destination
0x1800342d6  call    cs:__imp_RtlAppendUnicodeToString
0x1800342dd  nop     dword ptr [rax+rax+00h]
0x1800342e2  lea     rdx, [rbp+57h+GuidString]; GuidString
0x1800342e6  mov     rcx, rsi; Guid
0x1800342e9  call    cs:__imp_RtlStringFromGUID
0x1800342f0  nop     dword ptr [rax+rax+00h]
0x1800342f5  mov     ebx, eax
0x1800342f7  test    eax, eax
0x1800342f9  js      short loc_180034292
0x1800342fb  lea     rdx, [rbp+57h+GuidString]; Source
0x1800342ff  lea     rcx, [rbp+57h+Destination]; Destination
0x180034303  call    cs:__imp_RtlAppendUnicodeStringToString
0x18003430a  nop     dword ptr [rax+rax+00h]
0x18003430f  lea     rcx, [rbp+57h+GuidString]; UnicodeString
0x180034313  call    cs:__imp_RtlFreeUnicodeString
0x18003431a  nop     dword ptr [rax+rax+00h]
0x18003431f  lea     rdx, asc_18001DB54; "-"
0x180034326  lea     rcx, [rbp+57h+Destination]; Destination
0x18003432a  call    cs:__imp_RtlAppendUnicodeToString
0x180034331  nop     dword ptr [rax+rax+00h]
0x180034336  mov     ecx, [rsi+10h]; Value
0x180034339  lea     r8, [rbp+57h+String]; String
0x18003433d  mov     ebx, 10h
0x180034342  mov     edx, ebx; Base
0x180034344  call    cs:__imp_RtlIntegerToUnicodeString
0x18003434b  nop     dword ptr [rax+rax+00h]
0x180034350  lea     rdx, [rbp+57h+String]; Source
0x180034354  lea     rcx, [rbp+57h+Destination]; Destination
0x180034358  call    cs:__imp_RtlAppendUnicodeStringToString
0x18003435f  nop     dword ptr [rax+rax+00h]
0x180034364  lea     rdx, asc_18001DB54; "-"
0x18003436b  lea     rcx, [rbp+57h+Destination]; Destination
0x18003436f  call    cs:__imp_RtlAppendUnicodeToString
0x180034376  nop     dword ptr [rax+rax+00h]
0x18003437b  mov     ecx, [rsi+14h]; Value
0x18003437e  lea     r8, [rbp+57h+String]; String
0x180034382  mov     edx, ebx; Base
0x180034384  call    cs:__imp_RtlIntegerToUnicodeString
0x18003438b  nop     dword ptr [rax+rax+00h]
0x180034390  lea     rdx, [rbp+57h+String]; Source
0x180034394  lea     rcx, [rbp+57h+Destination]; Destination
0x180034398  call    cs:__imp_RtlAppendUnicodeStringToString
0x18003439f  nop     dword ptr [rax+rax+00h]
0x1800343a4  lea     rax, [rbp+57h+Destination]
0x1800343a8  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800343af  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800343b3  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800343b7  lea     rax, [rbp+57h+var_C0]
0x1800343bb  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x1800343bf  mov     [rsp+110h+Disposition], rax; Disposition
0x1800343c4  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800343c8  xorps   xmm0, xmm0
0x1800343cb  mov     [rsp+110h+CreateOptions], r15d; CreateOptions
0x1800343d0  xor     r9d, r9d; TitleIndex
0x1800343d3  mov     [rsp+110h+Class], r15; Class
0x1800343d8  mov     edx, 0F003Fh; DesiredAccess
0x1800343dd  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1800343e4  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800343e9  call    cs:__imp_ZwCreateKey
0x1800343f0  nop     dword ptr [rax+rax+00h]
0x1800343f5  mov     ebx, eax
0x1800343f7  test    eax, eax
0x1800343f9  js      loc_180034292
0x1800343ff  mov     rcx, [rbp+57h+DestinationString.Buffer]; Source1
0x180034403  lea     rdx, aDosdevices; "\\DosDevices"
0x18003440a  mov     r8d, 16h; Length
0x180034410  call    cs:__imp_RtlCompareMemory
0x180034417  nop     dword ptr [rax+rax+00h]
0x18003441c  cmp     eax, 16h
0x18003441f  mov     rax, [rbp+57h+DestinationString.Buffer]
0x180034423  jnz     short loc_18003444F
0x180034425  mov     r8, 2E005C005Ch
0x18003442f  lea     rcx, [rax+16h]
0x180034433  mov     [rax], r8
0x180034436  lea     rdx, [rax+6]
0x18003443a  movzx   eax, word ptr [rcx]
0x18003443d  lea     rcx, [rcx+2]
0x180034441  mov     [rdx], ax
0x180034444  lea     rdx, [rdx+2]
0x180034448  test    ax, ax
0x18003444b  jnz     short loc_18003443A
0x18003444d  jmp     short loc_180034463
0x18003444f  cmp     word ptr [rax+2], 3Fh ; '?'
0x180034454  jnz     short loc_180034463
0x180034456  cmp     word ptr [rax+4], 3Fh ; '?'
0x18003445b  jnz     short loc_180034463
0x18003445d  mov     word ptr [rax+2], 5Ch ; '\'
0x180034463  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180034467  lea     rax, [rbp+57h+Data]
0x18003446b  mov     r9d, 4; Type
0x180034471  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x180034475  mov     [rsp+110h+CreateOptions], r9d; DataSize
0x18003447a  xor     r8d, r8d; TitleIndex
0x18003447d  mov     [rsp+110h+Class], rax; Data
0x180034482  call    cs:__imp_ZwSetValueKey
0x180034489  nop     dword ptr [rax+rax+00h]
0x18003448e  mov     ebx, eax
0x180034490  lea     rsi, WPP_RECORDER_INITIALIZED
0x180034497  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x18003449e  jz      loc_180034541
0x1800344a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800344ab  cmp     [rcx+48h], r15w
0x1800344b0  jz      short loc_1800344D3
0x1800344b2  mov     rcx, [rcx+40h]
0x1800344b6  mov     r9d, 11h
0x1800344bc  mov     [rsp+110h+CreateOptions], eax
0x1800344c0  mov     dl, 5
0x1800344c2  lea     rax, WPP_0de5e70475493ec6bd40349f10325ac4_Traceguids
0x1800344c9  mov     [rsp+110h+Class], rax
0x1800344ce  call    WPP_RECORDER_SF_d
0x1800344d3  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1800344da  jz      short loc_180034541
0x1800344dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800344e3  cmp     [rcx+48h], r15w
0x1800344e8  jz      short loc_18003450A
0x1800344ea  movzx   eax, [rbp+57h+Destination.Length]
0x1800344ee  mov     r9d, 12h
0x1800344f4  mov     rcx, [rcx+40h]
0x1800344f8  mov     dword ptr [rsp+110h+Disposition], eax
0x1800344fc  mov     rax, [rbp+57h+Destination.Buffer]
0x180034500  mov     qword ptr [rsp+110h+CreateOptions], rax
0x180034505  call    WPP_RECORDER_SF_Sd
0x18003450a  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x180034511  jz      short loc_180034541
0x180034513  mov     rcx, cs:WPP_GLOBAL_Control
0x18003451a  cmp     [rcx+48h], r15w
0x18003451f  jz      short loc_180034541
0x180034521  movzx   eax, [rbp+57h+DestinationString.Length]
0x180034525  mov     r9d, 13h
0x18003452b  mov     rcx, [rcx+40h]
0x18003452f  mov     dword ptr [rsp+110h+Disposition], eax
0x180034533  mov     rax, [rbp+57h+DestinationString.Buffer]
0x180034537  mov     qword ptr [rsp+110h+CreateOptions], rax
0x18003453c  call    WPP_RECORDER_SF_Sd
0x180034541  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180034545  call    cs:__imp_ZwClose
0x18003454c  nop     dword ptr [rax+rax+00h]
0x180034551  jmp     loc_180034292
0x180034556  xor     edx, edx; Tag
0x180034558  mov     rcx, rdi; P
0x18003455b  call    cs:__imp_ExFreePoolWithTag
0x180034562  nop     dword ptr [rax+rax+00h]
0x180034567  mov     eax, 0C000009Ah
0x18003456c  mov     rcx, [rbp+57h+var_28]
0x180034570  xor     rcx, rsp; StackCookie
0x180034573  call    __security_check_cookie
0x180034578  mov     rbx, [rsp+110h+arg_18]
0x180034580  add     rsp, 0F0h
0x180034587  pop     r15
0x180034589  pop     r14
0x18003458b  pop     rdi
0x18003458c  pop     rsi
0x18003458d  pop     rbp
0x18003458e  retn
```
