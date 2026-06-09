# ndisSetAllFilterDefaultParameters(_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,uchar)

- ea: `0x1400961c8`
- end: `0x14009649c`
- name: `?ndisSetAllFilterDefaultParameters@@YAHPEBU_UNICODE_STRING@@00E@Z`
- size: `724`
- prototype: `__int64 __fastcall(const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, unsigned __int8)`
- caller_count: `3`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400641e0`
- `0x140084d60`
- `0x140085b90`

## callees

- `0x14002b980`
- `0x1400472e0`
- `0x1400961c8`
- `0x1400964a4`
- `0x1400e65c0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400962cc`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400962cc`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400962df`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400962f2`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400962df`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400962f2`
- `ntoskrnl!ZwOpenKey` at `0x14009632d`
- `ntoskrnl!ZwOpenKey` at `0x14009632d`
- `ntoskrnl!ZwClose` at `0x1400963fc`
- `ntoskrnl!ZwClose` at `0x1400963fc`
- `ntoskrnl!ZwEnumerateKey` at `0x1400963a2`
- `ntoskrnl!ZwEnumerateKey` at `0x1400963a2`
- `ntoskrnl!RtlInitUnicodeString` at `0x140096272`
- `ntoskrnl!RtlInitUnicodeString` at `0x140096272`
- `ntoskrnl!ExFreePoolWithTag` at `0x140096413`
- `ntoskrnl!ExFreePoolWithTag` at `0x140096429`
- `ntoskrnl!ExFreePoolWithTag` at `0x140096413`
- `ntoskrnl!ExFreePoolWithTag` at `0x140096429`
- `ntoskrnl!ExAllocatePool2` at `0x1400962a3`
- `ntoskrnl!ExAllocatePool2` at `0x140096356`
- `ntoskrnl!ExAllocatePool2` at `0x1400962a3`
- `ntoskrnl!ExAllocatePool2` at `0x140096356`

## string_xrefs

- `0x140096267`: `\Registry\Machine\System\CurrentControlSet\Services\`

## pseudocode

```c
__int64 __fastcall ndisSetAllFilterDefaultParameters(
        const struct _UNICODE_STRING *a1,
        const struct _UNICODE_STRING *a2,
        const struct _UNICODE_STRING *a3,
        char a4)
{
  ULONG v4; // esi
  unsigned __int16 *Pool2; // rdi
  const struct _UNICODE_STRING *v8; // r12
  int v10; // edx
  unsigned int v11; // ebx
  NTSTATUS v12; // eax
  char v14; // [rsp+30h] [rbp-59h]
  struct _UNICODE_STRING Destination; // [rsp+50h] [rbp-39h] BYREF
  struct _UNICODE_STRING v16; // [rsp+60h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-9h] BYREF
  ULONG ResultLength; // [rsp+F0h] [rbp+67h] BYREF
  void *KeyHandle; // [rsp+100h] [rbp+77h] BYREF

  v4 = 0;
  KeyHandle = 0;
  Pool2 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  *(_QWORD *)&Destination.Length = 0;
  Destination.Buffer = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  v8 = a2;
  DestinationString.Buffer = 0;
  ResultLength = 0;
  *(_QWORD *)&v16.Length = 0;
  v16.Buffer = 0;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v14 = (char)a2;
    LOBYTE(a2) = 4;
    WPP_RECORDER_SF_qqq(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      (int)a2,
      1,
      94,
      (struct _GUID *)&WPP_9524bb9419753e2807bcae08715ee655_Traceguids,
      (char)a1,
      v14,
      (char)a3);
  }
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\");
  Destination.MaximumLength = DestinationString.Length + a3->Length + 2 + a1->Length;
  Destination.Buffer = (wchar_t *)ExAllocatePool2(64, Destination.MaximumLength, 538985550);
  if ( !Destination.Buffer )
    goto LABEL_4;
  v11 = 0;
  RtlCopyUnicodeString(&Destination, &DestinationString);
  RtlAppendUnicodeStringToString(&Destination, a1);
  RtlAppendUnicodeStringToString(&Destination, a3);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &Destination;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( ZwOpenKey(&KeyHandle, 0x80000000, &ObjectAttributes) )
  {
    KeyHandle = 0;
    goto LABEL_15;
  }
  Pool2 = (unsigned __int16 *)ExAllocatePool2(66, 536, 538985550);
  if ( Pool2 )
  {
    while ( 1 )
    {
      memset(Pool2, 0, 0x218u);
      ResultLength = 0;
      v12 = ZwEnumerateKey(KeyHandle, v4, KeyBasicInformation, Pool2, 0x216u, &ResultLength);
      if ( v12 == -2147483622 )
        break;
      if ( v12 )
      {
        v11 = -1073741823;
        break;
      }
      v16.Length = Pool2[6];
      v16.MaximumLength = v16.Length + 2;
      v16.Buffer = Pool2 + 8;
      v11 = ndisSetFilterDefaultParameter(v8, KeyHandle, &v16, a4);
      if ( v11 )
        break;
      ++v4;
    }
  }
  else
  {
LABEL_4:
    v11 = -1073741670;
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
LABEL_15:
  if ( Destination.Buffer )
    ExFreePoolWithTag(Destination.Buffer, 0);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0);
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qqqL(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v10,
      1,
      95,
      (struct _GUID *)&WPP_9524bb9419753e2807bcae08715ee655_Traceguids,
      (char)a1,
      (char)v8,
      (char)a3,
      v11);
  return v11;
}

```

## disassembly

```asm
0x1400961c8  mov     [rsp-8+arg_8], rbx
0x1400961cd  push    rbp
0x1400961ce  push    rsi
0x1400961cf  push    rdi
0x1400961d0  push    r12
0x1400961d2  push    r13
0x1400961d4  push    r14
0x1400961d6  push    r15
0x1400961d8  lea     rbp, [rsp-27h]
0x1400961dd  sub     rsp, 0B0h
0x1400961e4  xor     esi, esi
0x1400961e6  xorps   xmm0, xmm0
0x1400961e9  mov     [rbp+57h+KeyHandle], rsi
0x1400961ed  mov     edi, esi
0x1400961ef  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1400961f3  mov     qword ptr [rbp+57h+Destination.Length], rsi
0x1400961f7  mov     r13b, r9b
0x1400961fa  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1400961fe  mov     [rbp+57h+Destination.Buffer], rsi
0x140096202  mov     r14, r8
0x140096205  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140096209  mov     qword ptr [rbp+57h+DestinationString.Length], rsi
0x14009620d  mov     r12, rdx
0x140096210  mov     [rbp+57h+DestinationString.Buffer], rsi
0x140096214  mov     r15, rcx
0x140096217  mov     [rbp+57h+arg_0], esi
0x14009621a  mov     qword ptr [rbp+57h+var_80.Length], rsi
0x14009621e  mov     [rbp+57h+var_80.Buffer], rsi
0x140096222  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140096229  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140096230  lea     rax, WPP_9524bb9419753e2807bcae08715ee655_Traceguids
0x140096237  jz      short loc_140096267
0x140096239  mov     rcx, cs:WPP_GLOBAL_Control
0x140096240  lea     r9d, [rsi+5Eh]; int
0x140096244  mov     qword ptr [rsp+0E0h+var_A8], r8; char
0x140096249  lea     r8d, [rsi+1]; int
0x14009624d  mov     qword ptr [rsp+0E0h+var_B0], rdx; char
0x140096252  mov     dl, 4; int
0x140096254  mov     [rsp+0E0h+ResultLength], r15; char
0x140096259  mov     rcx, [rcx+40h]; int
0x14009625d  mov     qword ptr [rsp+0E0h+Length], rax; struct _GUID *
0x140096262  call    WPP_RECORDER_SF_qqq
0x140096267  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x14009626e  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140096272  call    cs:__imp_RtlInitUnicodeString
0x140096279  nop     dword ptr [rax+rax+00h]
0x14009627e  movzx   ecx, word ptr [r15]
0x140096282  mov     r8d, 2020444Eh
0x140096288  movzx   eax, word ptr [r14]
0x14009628c  add     ax, 2
0x140096290  add     cx, ax
0x140096293  add     cx, [rbp+57h+DestinationString.Length]
0x140096297  movzx   edx, cx
0x14009629a  mov     ecx, 40h ; '@'
0x14009629f  mov     [rbp+57h+Destination.MaximumLength], dx
0x1400962a3  call    cs:__imp_ExAllocatePool2
0x1400962aa  nop     dword ptr [rax+rax+00h]
0x1400962af  mov     [rbp+57h+Destination.Buffer], rax
0x1400962b3  test    rax, rax
0x1400962b6  jnz     short loc_1400962C2
0x1400962b8  mov     ebx, 0C000009Ah
0x1400962bd  jmp     loc_1400963F3
0x1400962c2  lea     rdx, [rbp+57h+DestinationString]; SourceString
0x1400962c6  mov     ebx, esi
0x1400962c8  lea     rcx, [rbp+57h+Destination]; DestinationString
0x1400962cc  call    cs:__imp_RtlCopyUnicodeString
0x1400962d3  nop     dword ptr [rax+rax+00h]
0x1400962d8  mov     rdx, r15; Source
0x1400962db  lea     rcx, [rbp+57h+Destination]; Destination
0x1400962df  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400962e6  nop     dword ptr [rax+rax+00h]
0x1400962eb  mov     rdx, r14; Source
0x1400962ee  lea     rcx, [rbp+57h+Destination]; Destination
0x1400962f2  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400962f9  nop     dword ptr [rax+rax+00h]
0x1400962fe  lea     rax, [rbp+57h+Destination]
0x140096302  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140096309  xorps   xmm0, xmm0
0x14009630c  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140096310  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140096314  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x140096318  mov     edx, 80000000h; DesiredAccess
0x14009631d  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140096324  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140096328  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14009632d  call    cs:__imp_ZwOpenKey
0x140096334  nop     dword ptr [rax+rax+00h]
0x140096339  test    eax, eax
0x14009633b  jz      short loc_140096346
0x14009633d  mov     [rbp+57h+KeyHandle], rsi
0x140096341  jmp     loc_140096408
0x140096346  mov     edx, 218h
0x14009634b  mov     ecx, 42h ; 'B'
0x140096350  mov     r8d, 2020444Eh
0x140096356  call    cs:__imp_ExAllocatePool2
0x14009635d  nop     dword ptr [rax+rax+00h]
0x140096362  mov     rdi, rax
0x140096365  test    rax, rax
0x140096368  jz      loc_1400962B8
0x14009636e  xor     edx, edx; Val
0x140096370  mov     r8d, 218h; Size
0x140096376  mov     rcx, rdi; void *
0x140096379  call    memset
0x14009637e  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140096382  lea     rax, [rbp+57h+arg_0]
0x140096386  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x14009638b  mov     r9, rdi; KeyInformation
0x14009638e  xor     r8d, r8d; KeyInformationClass
0x140096391  mov     [rsp+0E0h+Length], 216h; Length
0x140096399  mov     edx, esi; Index
0x14009639b  mov     [rbp+57h+arg_0], 0
0x1400963a2  call    cs:__imp_ZwEnumerateKey
0x1400963a9  nop     dword ptr [rax+rax+00h]
0x1400963ae  cmp     eax, 8000001Ah
0x1400963b3  jz      short loc_1400963F3
0x1400963b5  test    eax, eax
0x1400963b7  jnz     short loc_1400963EE
0x1400963b9  movzx   eax, word ptr [rdi+0Ch]
0x1400963bd  lea     r8, [rbp+57h+var_80]; struct _UNICODE_STRING *
0x1400963c1  mov     rdx, [rbp+57h+KeyHandle]; void *
0x1400963c5  mov     r9b, r13b; unsigned __int8
0x1400963c8  mov     [rbp+57h+var_80.Length], ax
0x1400963cc  mov     rcx, r12; struct _UNICODE_STRING *
0x1400963cf  add     ax, 2
0x1400963d3  mov     [rbp+57h+var_80.MaximumLength], ax
0x1400963d7  lea     rax, [rdi+10h]
0x1400963db  mov     [rbp+57h+var_80.Buffer], rax
0x1400963df  call    ?ndisSetFilterDefaultParameter@@YAHPEBU_UNICODE_STRING@@PEAX0E@Z; ndisSetFilterDefaultParameter(_UNICODE_STRING const *,void *,_UNICODE_STRING const *,uchar)
0x1400963e4  mov     ebx, eax
0x1400963e6  test    eax, eax
0x1400963e8  jnz     short loc_1400963F3
0x1400963ea  inc     esi
0x1400963ec  jmp     short loc_14009636E
0x1400963ee  mov     ebx, 0C0000001h
0x1400963f3  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1400963f7  test    rcx, rcx
0x1400963fa  jz      short loc_140096408
0x1400963fc  call    cs:__imp_ZwClose
0x140096403  nop     dword ptr [rax+rax+00h]
0x140096408  mov     rcx, [rbp+57h+Destination.Buffer]; P
0x14009640c  test    rcx, rcx
0x14009640f  jz      short loc_14009641F
0x140096411  xor     edx, edx; Tag
0x140096413  call    cs:__imp_ExFreePoolWithTag
0x14009641a  nop     dword ptr [rax+rax+00h]
0x14009641f  test    rdi, rdi
0x140096422  jz      short loc_140096435
0x140096424  xor     edx, edx; Tag
0x140096426  mov     rcx, rdi; P
0x140096429  call    cs:__imp_ExFreePoolWithTag
0x140096430  nop     dword ptr [rax+rax+00h]
0x140096435  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14009643c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140096443  jz      short loc_14009647E
0x140096445  mov     rcx, cs:WPP_GLOBAL_Control
0x14009644c  lea     rax, WPP_9524bb9419753e2807bcae08715ee655_Traceguids
0x140096453  mov     dword ptr [rsp+0E0h+var_A0], ebx; char
0x140096457  mov     r9d, 5Fh ; '_'; int
0x14009645d  mov     qword ptr [rsp+0E0h+var_A8], r14; char
0x140096462  mov     qword ptr [rsp+0E0h+var_B0], r12; char
0x140096467  mov     rcx, [rcx+40h]; int
0x14009646b  lea     r8d, [r9-5Eh]; int
0x14009646f  mov     [rsp+0E0h+ResultLength], r15; char
0x140096474  mov     qword ptr [rsp+0E0h+Length], rax; struct _GUID *
0x140096479  call    WPP_RECORDER_SF_qqqL
0x14009647e  mov     eax, ebx
0x140096480  mov     rbx, [rsp+0E0h+arg_8]
0x140096488  add     rsp, 0B0h
0x14009648f  pop     r15
0x140096491  pop     r14
0x140096493  pop     r13
0x140096495  pop     r12
0x140096497  pop     rdi
0x140096498  pop     rsi
0x140096499  pop     rbp
0x14009649a  retn
```
