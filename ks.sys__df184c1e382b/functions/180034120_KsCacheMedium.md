# KsCacheMedium

- ea: `0x180034120`
- end: `0x1800345e0`
- name: `KsCacheMedium`
- size: `1216`
- prototype: `NTSTATUS __stdcall(PUNICODE_STRING SymbolicLink, PKSPIN_MEDIUM Medium, ULONG PinDirection)`
- caller_count: `2`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003dd80`
- `0x1800583f4`

## callees

- `0x18000c058`
- `0x180010c68`
- `0x180019bd0`
- `0x18001a000`
- `0x180034120`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x180034363`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180034363`
- `ntoskrnl!ZwCreateKey` at `0x1800342d0`
- `ntoskrnl!ZwCreateKey` at `0x180034439`
- `ntoskrnl!ZwCreateKey` at `0x1800342d0`
- `ntoskrnl!ZwCreateKey` at `0x180034439`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180034214`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180034214`
- `ntoskrnl!RtlStringFromGUID` at `0x180034339`
- `ntoskrnl!RtlStringFromGUID` at `0x180034339`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x180034394`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x1800343d4`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x180034394`
- `ntoskrnl!RtlIntegerToUnicodeString` at `0x1800343d4`
- `ntoskrnl!ZwClose` at `0x18003430f`
- `ntoskrnl!ZwClose` at `0x180034595`
- `ntoskrnl!ZwClose` at `0x18003430f`
- `ntoskrnl!ZwClose` at `0x180034595`
- `ntoskrnl!ZwSetValueKey` at `0x1800344d2`
- `ntoskrnl!ZwSetValueKey` at `0x1800344d2`
- `ntoskrnl!RtlCompareMemory` at `0x180034460`
- `ntoskrnl!RtlCompareMemory` at `0x180034460`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18003427f`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180034326`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18003437a`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1800343bf`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18003427f`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x180034326`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18003437a`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x1800343bf`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x180034353`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1800343a8`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1800343e8`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x180034353`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1800343a8`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1800343e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800342e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800342f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800345ab`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800342e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800342f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800345ab`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800341d4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18003422e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800341d4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18003422e`

## string_xrefs

- `0x180034268`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\MediumCache`

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
              (__int64)WPP_9ded0dcd308a3e4cff16fc62ccb55bdd_Traceguids,
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
0x180034120  mov     [rsp-8+arg_18], rbx
0x180034125  push    rbp
0x180034126  push    rsi
0x180034127  push    rdi
0x180034128  push    r14
0x18003412a  push    r15
0x18003412c  lea     rbp, [rsp-37h]
0x180034131  sub     rsp, 0F0h
0x180034138  mov     rax, cs:__security_cookie
0x18003413f  xor     rax, rsp
0x180034142  mov     [rbp+57h+var_28], rax
0x180034146  xorps   xmm0, xmm0
0x180034149  mov     [rbp+57h+Data], r8d
0x18003414d  xor     r15d, r15d
0x180034150  xorps   xmm1, xmm1
0x180034153  xor     eax, eax
0x180034155  mov     [rbp+57h+KeyHandle], r15
0x180034159  mov     [rbp+57h+var_C0], r15d
0x18003415d  mov     rsi, rdx
0x180034160  mov     r14, rcx
0x180034163  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180034167  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18003416b  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18003416f  movups  xmmword ptr [rbp+57h+GuidString.Length], xmm0
0x180034173  movups  xmmword ptr [rbp+57h+Destination.Length], xmm1
0x180034177  movups  xmmword ptr [rbp+57h+String.Length], xmm0
0x18003417b  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x18003417f  test    rdx, rdx
0x180034182  jz      loc_1800345BC
0x180034188  mov     rcx, [rdx]
0x18003418b  cmp     rcx, qword ptr cs:KSMEDIUMSETID_Standard.Data1
0x180034192  jnz     short loc_1800341A5
0x180034194  mov     rcx, [rdx+8]
0x180034198  cmp     rcx, qword ptr cs:KSMEDIUMSETID_Standard.Data4
0x18003419f  jz      loc_1800345BC
0x1800341a5  mov     rcx, [rdx]
0x1800341a8  cmp     rcx, qword ptr cs:GUID_NULL.Data1
0x1800341af  jnz     short loc_1800341C2
0x1800341b1  mov     rcx, [rdx+8]
0x1800341b5  cmp     rcx, qword ptr cs:GUID_NULL.Data4
0x1800341bc  jz      loc_1800345BC
0x1800341c2  mov     ebx, 200h
0x1800341c7  mov     r8d, 636D534Bh; Tag
0x1800341cd  mov     edx, ebx; NumberOfBytes
0x1800341cf  mov     ecx, 401h; PoolType
0x1800341d4  call    cs:__imp_ExAllocatePoolWithTag
0x1800341db  nop     dword ptr [rax+rax+00h]
0x1800341e0  mov     rdi, rax
0x1800341e3  test    rax, rax
0x1800341e6  jz      loc_1800345B7
0x1800341ec  cmp     cs:ExPoolZeroingNativelySupported, r15b
0x1800341f3  jnz     short loc_180034202
0x1800341f5  mov     r8d, ebx; Size
0x1800341f8  xor     edx, edx; Val
0x1800341fa  mov     rcx, rax; void *
0x1800341fd  call    memset
0x180034202  mov     rdx, r14; SourceString
0x180034205  mov     dword ptr [rbp+57h+DestinationString.Length], 2000000h
0x18003420c  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180034210  mov     [rbp+57h+DestinationString.Buffer], rdi
0x180034214  call    cs:__imp_RtlCopyUnicodeString
0x18003421b  nop     dword ptr [rax+rax+00h]
0x180034220  mov     r8d, 636D534Bh; Tag
0x180034226  mov     rdx, rbx; NumberOfBytes
0x180034229  mov     ecx, 1; PoolType
0x18003422e  call    cs:__imp_ExAllocatePoolWithTag
0x180034235  nop     dword ptr [rax+rax+00h]
0x18003423a  mov     r14, rax
0x18003423d  test    rax, rax
0x180034240  jz      loc_1800345A6
0x180034246  mov     dword ptr [rbp+57h+Destination.Length], 2000000h
0x18003424d  mov     [rbp+57h+Destination.Buffer], rax
0x180034251  mov     [rax], r15b
0x180034254  inc     rax
0x180034257  sub     rbx, 1
0x18003425b  jnz     short loc_180034251
0x18003425d  lea     rax, [rbp+57h+var_48]
0x180034261  mov     dword ptr [rbp+57h+String.Length], 200000h
0x180034268  lea     rdx, Source; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x18003426f  mov     [rbp+57h+String.Buffer], rax
0x180034273  lea     rcx, [rbp+57h+Destination]; Destination
0x180034277  mov     dword ptr [rbp+57h+GuidString.Length], r15d
0x18003427b  mov     [rbp+57h+GuidString.Buffer], r15
0x18003427f  call    cs:__imp_RtlAppendUnicodeToString
0x180034286  nop     dword ptr [rax+rax+00h]
0x18003428b  lea     rax, [rbp+57h+Destination]
0x18003428f  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180034296  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18003429a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18003429e  lea     rax, [rbp+57h+var_C0]
0x1800342a2  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x1800342a6  mov     [rsp+110h+Disposition], rax; Disposition
0x1800342ab  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800342af  xorps   xmm0, xmm0
0x1800342b2  mov     [rsp+110h+CreateOptions], r15d; CreateOptions
0x1800342b7  xor     r9d, r9d; TitleIndex
0x1800342ba  mov     [rsp+110h+Class], r15; Class
0x1800342bf  mov     edx, 0F003Fh; DesiredAccess
0x1800342c4  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1800342cb  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800342d0  call    cs:__imp_ZwCreateKey
0x1800342d7  nop     dword ptr [rax+rax+00h]
0x1800342dc  mov     ebx, eax
0x1800342de  test    eax, eax
0x1800342e0  jns     short loc_18003430B
0x1800342e2  xor     edx, edx; Tag
0x1800342e4  mov     rcx, rdi; P
0x1800342e7  call    cs:__imp_ExFreePoolWithTag
0x1800342ee  nop     dword ptr [rax+rax+00h]
0x1800342f3  xor     edx, edx; Tag
0x1800342f5  mov     rcx, r14; P
0x1800342f8  call    cs:__imp_ExFreePoolWithTag
0x1800342ff  nop     dword ptr [rax+rax+00h]
0x180034304  mov     eax, ebx
0x180034306  jmp     loc_1800345BC
0x18003430b  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18003430f  call    cs:__imp_ZwClose
0x180034316  nop     dword ptr [rax+rax+00h]
0x18003431b  lea     rdx, asc_18001DBA0; "\\"
0x180034322  lea     rcx, [rbp+57h+Destination]; Destination
0x180034326  call    cs:__imp_RtlAppendUnicodeToString
0x18003432d  nop     dword ptr [rax+rax+00h]
0x180034332  lea     rdx, [rbp+57h+GuidString]; GuidString
0x180034336  mov     rcx, rsi; Guid
0x180034339  call    cs:__imp_RtlStringFromGUID
0x180034340  nop     dword ptr [rax+rax+00h]
0x180034345  mov     ebx, eax
0x180034347  test    eax, eax
0x180034349  js      short loc_1800342E2
0x18003434b  lea     rdx, [rbp+57h+GuidString]; Source
0x18003434f  lea     rcx, [rbp+57h+Destination]; Destination
0x180034353  call    cs:__imp_RtlAppendUnicodeStringToString
0x18003435a  nop     dword ptr [rax+rax+00h]
0x18003435f  lea     rcx, [rbp+57h+GuidString]; UnicodeString
0x180034363  call    cs:__imp_RtlFreeUnicodeString
0x18003436a  nop     dword ptr [rax+rax+00h]
0x18003436f  lea     rdx, asc_18001DBA4; "-"
0x180034376  lea     rcx, [rbp+57h+Destination]; Destination
0x18003437a  call    cs:__imp_RtlAppendUnicodeToString
0x180034381  nop     dword ptr [rax+rax+00h]
0x180034386  mov     ecx, [rsi+10h]; Value
0x180034389  lea     r8, [rbp+57h+String]; String
0x18003438d  mov     ebx, 10h
0x180034392  mov     edx, ebx; Base
0x180034394  call    cs:__imp_RtlIntegerToUnicodeString
0x18003439b  nop     dword ptr [rax+rax+00h]
0x1800343a0  lea     rdx, [rbp+57h+String]; Source
0x1800343a4  lea     rcx, [rbp+57h+Destination]; Destination
0x1800343a8  call    cs:__imp_RtlAppendUnicodeStringToString
0x1800343af  nop     dword ptr [rax+rax+00h]
0x1800343b4  lea     rdx, asc_18001DBA4; "-"
0x1800343bb  lea     rcx, [rbp+57h+Destination]; Destination
0x1800343bf  call    cs:__imp_RtlAppendUnicodeToString
0x1800343c6  nop     dword ptr [rax+rax+00h]
0x1800343cb  mov     ecx, [rsi+14h]; Value
0x1800343ce  lea     r8, [rbp+57h+String]; String
0x1800343d2  mov     edx, ebx; Base
0x1800343d4  call    cs:__imp_RtlIntegerToUnicodeString
0x1800343db  nop     dword ptr [rax+rax+00h]
0x1800343e0  lea     rdx, [rbp+57h+String]; Source
0x1800343e4  lea     rcx, [rbp+57h+Destination]; Destination
0x1800343e8  call    cs:__imp_RtlAppendUnicodeStringToString
0x1800343ef  nop     dword ptr [rax+rax+00h]
0x1800343f4  lea     rax, [rbp+57h+Destination]
0x1800343f8  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800343ff  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180034403  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180034407  lea     rax, [rbp+57h+var_C0]
0x18003440b  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x18003440f  mov     [rsp+110h+Disposition], rax; Disposition
0x180034414  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x180034418  xorps   xmm0, xmm0
0x18003441b  mov     [rsp+110h+CreateOptions], r15d; CreateOptions
0x180034420  xor     r9d, r9d; TitleIndex
0x180034423  mov     [rsp+110h+Class], r15; Class
0x180034428  mov     edx, 0F003Fh; DesiredAccess
0x18003442d  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x180034434  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180034439  call    cs:__imp_ZwCreateKey
0x180034440  nop     dword ptr [rax+rax+00h]
0x180034445  mov     ebx, eax
0x180034447  test    eax, eax
0x180034449  js      loc_1800342E2
0x18003444f  mov     rcx, [rbp+57h+DestinationString.Buffer]; Source1
0x180034453  lea     rdx, aDosdevices; "\\DosDevices"
0x18003445a  mov     r8d, 16h; Length
0x180034460  call    cs:__imp_RtlCompareMemory
0x180034467  nop     dword ptr [rax+rax+00h]
0x18003446c  cmp     eax, 16h
0x18003446f  mov     rax, [rbp+57h+DestinationString.Buffer]
0x180034473  jnz     short loc_18003449F
0x180034475  mov     r8, 2E005C005Ch
0x18003447f  lea     rcx, [rax+16h]
0x180034483  mov     [rax], r8
0x180034486  lea     rdx, [rax+6]
0x18003448a  movzx   eax, word ptr [rcx]
0x18003448d  lea     rcx, [rcx+2]
0x180034491  mov     [rdx], ax
0x180034494  lea     rdx, [rdx+2]
0x180034498  test    ax, ax
0x18003449b  jnz     short loc_18003448A
0x18003449d  jmp     short loc_1800344B3
0x18003449f  cmp     word ptr [rax+2], 3Fh ; '?'
0x1800344a4  jnz     short loc_1800344B3
0x1800344a6  cmp     word ptr [rax+4], 3Fh ; '?'
0x1800344ab  jnz     short loc_1800344B3
0x1800344ad  mov     word ptr [rax+2], 5Ch ; '\'
0x1800344b3  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800344b7  lea     rax, [rbp+57h+Data]
0x1800344bb  mov     r9d, 4; Type
0x1800344c1  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x1800344c5  mov     [rsp+110h+CreateOptions], r9d; DataSize
0x1800344ca  xor     r8d, r8d; TitleIndex
0x1800344cd  mov     [rsp+110h+Class], rax; Data
0x1800344d2  call    cs:__imp_ZwSetValueKey
0x1800344d9  nop     dword ptr [rax+rax+00h]
0x1800344de  mov     ebx, eax
0x1800344e0  lea     rsi, WPP_RECORDER_INITIALIZED
0x1800344e7  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1800344ee  jz      loc_180034591
0x1800344f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800344fb  cmp     [rcx+48h], r15w
0x180034500  jz      short loc_180034523
0x180034502  mov     rcx, [rcx+40h]
0x180034506  mov     r9d, 11h
0x18003450c  mov     [rsp+110h+CreateOptions], eax
0x180034510  mov     dl, 5
0x180034512  lea     rax, WPP_9ded0dcd308a3e4cff16fc62ccb55bdd_Traceguids
0x180034519  mov     [rsp+110h+Class], rax
0x18003451e  call    WPP_RECORDER_SF_d
0x180034523  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x18003452a  jz      short loc_180034591
0x18003452c  mov     rcx, cs:WPP_GLOBAL_Control
0x180034533  cmp     [rcx+48h], r15w
0x180034538  jz      short loc_18003455A
0x18003453a  movzx   eax, [rbp+57h+Destination.Length]
0x18003453e  mov     r9d, 12h
0x180034544  mov     rcx, [rcx+40h]
0x180034548  mov     dword ptr [rsp+110h+Disposition], eax
0x18003454c  mov     rax, [rbp+57h+Destination.Buffer]
0x180034550  mov     qword ptr [rsp+110h+CreateOptions], rax
0x180034555  call    WPP_RECORDER_SF_Sd
0x18003455a  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x180034561  jz      short loc_180034591
0x180034563  mov     rcx, cs:WPP_GLOBAL_Control
0x18003456a  cmp     [rcx+48h], r15w
0x18003456f  jz      short loc_180034591
0x180034571  movzx   eax, [rbp+57h+DestinationString.Length]
0x180034575  mov     r9d, 13h
0x18003457b  mov     rcx, [rcx+40h]
0x18003457f  mov     dword ptr [rsp+110h+Disposition], eax
0x180034583  mov     rax, [rbp+57h+DestinationString.Buffer]
0x180034587  mov     qword ptr [rsp+110h+CreateOptions], rax
0x18003458c  call    WPP_RECORDER_SF_Sd
0x180034591  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180034595  call    cs:__imp_ZwClose
0x18003459c  nop     dword ptr [rax+rax+00h]
0x1800345a1  jmp     loc_1800342E2
0x1800345a6  xor     edx, edx; Tag
0x1800345a8  mov     rcx, rdi; P
0x1800345ab  call    cs:__imp_ExFreePoolWithTag
0x1800345b2  nop     dword ptr [rax+rax+00h]
0x1800345b7  mov     eax, 0C000009Ah
0x1800345bc  mov     rcx, [rbp+57h+var_28]
0x1800345c0  xor     rcx, rsp; StackCookie
0x1800345c3  call    __security_check_cookie
0x1800345c8  mov     rbx, [rsp+110h+arg_18]
0x1800345d0  add     rsp, 0F0h
0x1800345d7  pop     r15
0x1800345d9  pop     r14
0x1800345db  pop     rdi
0x1800345dc  pop     rsi
0x1800345dd  pop     rbp
0x1800345de  retn
```
