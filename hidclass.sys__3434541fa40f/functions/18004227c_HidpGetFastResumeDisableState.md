# HidpGetFastResumeDisableState

- ea: `0x18004227c`
- end: `0x180042433`
- name: `HidpGetFastResumeDisableState`
- size: `439`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1800385f0`

## callees

- `0x18001d7b4`
- `0x18001e538`
- `0x18004227c`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x180042351`
- `ntoskrnl!ZwQueryValueKey` at `0x180042351`
- `ntoskrnl!ZwOpenKey` at `0x1800422ca`
- `ntoskrnl!ZwOpenKey` at `0x1800422ca`
- `ntoskrnl!ZwClose` at `0x18004238c`
- `ntoskrnl!ZwClose` at `0x18004238c`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004237c`
- `ntoskrnl!ExFreePoolWithTag` at `0x18004237c`
- `ntoskrnl!ExAllocatePool2` at `0x18004231c`
- `ntoskrnl!ExAllocatePool2` at `0x18004231c`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800422f9`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800422f9`

## pseudocode

```c
NTSTATUS __fastcall HidpGetFastResumeDisableState(__int64 a1)
{
  __int64 v1; // rsi
  int v3; // edx
  NTSTATUS v4; // ebx
  __int64 v5; // r8
  unsigned int *Pool2; // rbx
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp+7h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp+17h] BYREF
  ULONG Length; // [rsp+B0h] [rbp+67h] BYREF
  void *KeyHandle; // [rsp+B8h] [rbp+6Fh] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  v1 = a1 + 8;
  KeyHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)(a1 + 8);
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = ZwOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      LOBYTE(v3) = 0;
    }
    else
    {
      v3 = 1;
    }
    LOBYTE(v5) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        v3,
        v5,
        g_RecorderLog,
        2,
        3,
        10,
        (__int64)WPP_0064a2c5ae813aea6fb92d3ddadcbb3b_Traceguids,
        v4);
    return TraceLoggingZwOpenKeyFailed((unsigned int)v4, v1, v5);
  }
  else
  {
    Length = 0;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"FastResumeDisable");
    Length = DestinationString.MaximumLength + 28;
    Pool2 = (unsigned int *)ExAllocatePool2(256, Length, 1130654024);
    if ( Pool2 )
    {
      if ( ZwQueryValueKey(KeyHandle, &DestinationString, KeyValueFullInformation, Pool2, Length, &Length) >= 0
        && Pool2[3] == 4 )
      {
        *(_BYTE *)(a1 + 297) = *(unsigned int *)((char *)Pool2 + Pool2[2]) != 0;
      }
      ExFreePoolWithTag(Pool2, 0);
    }
    return ZwClose(KeyHandle);
  }
}

```

## disassembly

```asm
0x18004227c  mov     [rsp-8+arg_10], rbx
0x180042281  push    rbp
0x180042282  push    rsi
0x180042283  push    rdi
0x180042284  lea     rbp, [rsp-47h]
0x180042289  sub     rsp, 90h
0x180042290  xor     eax, eax
0x180042292  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18004229a  lea     rsi, [rcx+8]
0x18004229e  mov     [rbp+57h+KeyHandle], rax
0x1800422a2  mov     rdi, rcx
0x1800422a5  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1800422a9  xorps   xmm0, xmm0
0x1800422ac  mov     [rbp+57h+ObjectAttributes.ObjectName], rsi
0x1800422b0  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800422b4  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x1800422bc  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800422c0  mov     edx, 0F003Fh; DesiredAccess
0x1800422c5  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800422ca  call    cs:__imp_ZwOpenKey
0x1800422d1  nop     dword ptr [rax+rax+00h]
0x1800422d6  mov     ebx, eax
0x1800422d8  test    eax, eax
0x1800422da  js      loc_18004239D
0x1800422e0  xorps   xmm0, xmm0
0x1800422e3  mov     [rbp+57h+arg_0], 0
0x1800422ea  lea     rdx, aFastresumedisa; "FastResumeDisable"
0x1800422f1  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800422f5  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800422f9  call    cs:__imp_RtlInitUnicodeString
0x180042300  nop     dword ptr [rax+rax+00h]
0x180042305  movzx   eax, [rbp+57h+DestinationString.MaximumLength]
0x180042309  mov     ecx, 100h
0x18004230e  add     eax, 1Ch
0x180042311  mov     r8d, 43646948h
0x180042317  mov     edx, eax
0x180042319  mov     [rbp+57h+arg_0], eax
0x18004231c  call    cs:__imp_ExAllocatePool2
0x180042323  nop     dword ptr [rax+rax+00h]
0x180042328  mov     rbx, rax
0x18004232b  test    rax, rax
0x18004232e  jz      short loc_180042388
0x180042330  mov     ecx, [rbp+57h+arg_0]
0x180042333  lea     rax, [rbp+57h+arg_0]
0x180042337  mov     [rsp+0A0h+ResultLength], rax; ResultLength
0x18004233c  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x180042340  mov     [rsp+0A0h+Length], ecx; Length
0x180042344  mov     r9, rbx; KeyValueInformation
0x180042347  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x18004234b  mov     r8d, 1; KeyValueInformationClass
0x180042351  call    cs:__imp_ZwQueryValueKey
0x180042358  nop     dword ptr [rax+rax+00h]
0x18004235d  test    eax, eax
0x18004235f  js      short loc_180042377
0x180042361  cmp     dword ptr [rbx+0Ch], 4
0x180042365  jnz     short loc_180042377
0x180042367  mov     eax, [rbx+8]
0x18004236a  cmp     dword ptr [rax+rbx], 0
0x18004236e  setnz   al
0x180042371  mov     [rdi+129h], al
0x180042377  xor     edx, edx; Tag
0x180042379  mov     rcx, rbx; P
0x18004237c  call    cs:__imp_ExFreePoolWithTag
0x180042383  nop     dword ptr [rax+rax+00h]
0x180042388  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18004238c  call    cs:__imp_ZwClose
0x180042393  nop     dword ptr [rax+rax+00h]
0x180042398  jmp     loc_18004241F
0x18004239d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800423a4  lea     rax, WPP_GLOBAL_Control
0x1800423ab  cmp     rcx, rax
0x1800423ae  jz      short loc_1800423C4
0x1800423b0  mov     eax, [rcx+2Ch]
0x1800423b3  test    al, 4
0x1800423b5  jz      short loc_1800423C4
0x1800423b7  cmp     byte ptr [rcx+29h], 2
0x1800423bb  jb      short loc_1800423C4
0x1800423bd  mov     edx, 1
0x1800423c2  jmp     short loc_1800423C6
0x1800423c4  xor     dl, dl
0x1800423c6  lea     rax, WPP_RECORDER_INITIALIZED
0x1800423cd  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800423d4  setnz   r8b
0x1800423d8  test    dl, dl
0x1800423da  jnz     short loc_1800423E1
0x1800423dc  test    r8b, r8b
0x1800423df  jz      short loc_180042415
0x1800423e1  mov     r9, cs:g_RecorderLog
0x1800423e8  lea     rax, WPP_0064a2c5ae813aea6fb92d3ddadcbb3b_Traceguids
0x1800423ef  mov     rcx, [rcx+18h]
0x1800423f3  mov     [rsp+0A0h+var_60], ebx
0x1800423f7  mov     [rsp+0A0h+var_68], rax
0x1800423fc  mov     [rsp+0A0h+var_70], 0Ah
0x180042403  mov     dword ptr [rsp+0A0h+ResultLength], 3
0x18004240b  mov     byte ptr [rsp+0A0h+Length], 2
0x180042410  call    WPP_RECORDER_AND_TRACE_SF_d
0x180042415  mov     rdx, rsi
0x180042418  mov     ecx, ebx
0x18004241a  call    TraceLoggingZwOpenKeyFailed
0x18004241f  mov     rbx, [rsp+0A0h+arg_10]
0x180042427  add     rsp, 90h
0x18004242e  pop     rdi
0x18004242f  pop     rsi
0x180042430  pop     rbp
0x180042431  retn
```
