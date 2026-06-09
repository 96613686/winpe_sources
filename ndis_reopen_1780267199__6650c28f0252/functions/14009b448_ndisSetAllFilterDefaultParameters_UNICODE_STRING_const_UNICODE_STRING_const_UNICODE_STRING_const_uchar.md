# ndisSetAllFilterDefaultParameters(_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,uchar)

- ea: `0x14009b448`
- end: `0x14009b71c`
- name: `?ndisSetAllFilterDefaultParameters@@YAHPEBU_UNICODE_STRING@@00E@Z`
- size: `724`
- prototype: `__int64 __fastcall(const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, const struct _UNICODE_STRING *, unsigned __int8)`
- caller_count: `3`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140069920`
- `0x140089fe0`
- `0x14008ae10`

## callees

- `0x14001fa30`
- `0x14004bc60`
- `0x14009b448`
- `0x14009b724`
- `0x1400eb7c0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14009b54c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14009b54c`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14009b55f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14009b572`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14009b55f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14009b572`
- `ntoskrnl!ZwOpenKey` at `0x14009b5ad`
- `ntoskrnl!ZwOpenKey` at `0x14009b5ad`
- `ntoskrnl!ZwClose` at `0x14009b67c`
- `ntoskrnl!ZwClose` at `0x14009b67c`
- `ntoskrnl!ZwEnumerateKey` at `0x14009b622`
- `ntoskrnl!ZwEnumerateKey` at `0x14009b622`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009b4f2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14009b4f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009b693`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009b6a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009b693`
- `ntoskrnl!ExFreePoolWithTag` at `0x14009b6a9`
- `ntoskrnl!ExAllocatePool2` at `0x14009b523`
- `ntoskrnl!ExAllocatePool2` at `0x14009b5d6`
- `ntoskrnl!ExAllocatePool2` at `0x14009b523`
- `ntoskrnl!ExAllocatePool2` at `0x14009b5d6`

## string_xrefs

- `0x14009b4e7`: `\Registry\Machine\System\CurrentControlSet\Services\`

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
0x14009b448  mov     [rsp-8+arg_8], rbx
0x14009b44d  push    rbp
0x14009b44e  push    rsi
0x14009b44f  push    rdi
0x14009b450  push    r12
0x14009b452  push    r13
0x14009b454  push    r14
0x14009b456  push    r15
0x14009b458  lea     rbp, [rsp-27h]
0x14009b45d  sub     rsp, 0B0h
0x14009b464  xor     esi, esi
0x14009b466  xorps   xmm0, xmm0
0x14009b469  mov     [rbp+57h+KeyHandle], rsi
0x14009b46d  mov     edi, esi
0x14009b46f  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14009b473  mov     qword ptr [rbp+57h+Destination.Length], rsi
0x14009b477  mov     r13b, r9b
0x14009b47a  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14009b47e  mov     [rbp+57h+Destination.Buffer], rsi
0x14009b482  mov     r14, r8
0x14009b485  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14009b489  mov     qword ptr [rbp+57h+DestinationString.Length], rsi
0x14009b48d  mov     r12, rdx
0x14009b490  mov     [rbp+57h+DestinationString.Buffer], rsi
0x14009b494  mov     r15, rcx
0x14009b497  mov     [rbp+57h+arg_0], esi
0x14009b49a  mov     qword ptr [rbp+57h+var_80.Length], rsi
0x14009b49e  mov     [rbp+57h+var_80.Buffer], rsi
0x14009b4a2  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14009b4a9  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14009b4b0  lea     rax, WPP_9524bb9419753e2807bcae08715ee655_Traceguids
0x14009b4b7  jz      short loc_14009B4E7
0x14009b4b9  mov     rcx, cs:WPP_GLOBAL_Control
0x14009b4c0  lea     r9d, [rsi+5Eh]; int
0x14009b4c4  mov     qword ptr [rsp+0E0h+var_A8], r8; char
0x14009b4c9  lea     r8d, [rsi+1]; int
0x14009b4cd  mov     qword ptr [rsp+0E0h+var_B0], rdx; char
0x14009b4d2  mov     dl, 4; int
0x14009b4d4  mov     [rsp+0E0h+ResultLength], r15; char
0x14009b4d9  mov     rcx, [rcx+40h]; int
0x14009b4dd  mov     qword ptr [rsp+0E0h+Length], rax; struct _GUID *
0x14009b4e2  call    WPP_RECORDER_SF_qqq
0x14009b4e7  lea     rdx, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x14009b4ee  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14009b4f2  call    cs:__imp_RtlInitUnicodeString
0x14009b4f9  nop     dword ptr [rax+rax+00h]
0x14009b4fe  movzx   ecx, word ptr [r15]
0x14009b502  mov     r8d, 2020444Eh
0x14009b508  movzx   eax, word ptr [r14]
0x14009b50c  add     ax, 2
0x14009b510  add     cx, ax
0x14009b513  add     cx, [rbp+57h+DestinationString.Length]
0x14009b517  movzx   edx, cx
0x14009b51a  mov     ecx, 40h ; '@'
0x14009b51f  mov     [rbp+57h+Destination.MaximumLength], dx
0x14009b523  call    cs:__imp_ExAllocatePool2
0x14009b52a  nop     dword ptr [rax+rax+00h]
0x14009b52f  mov     [rbp+57h+Destination.Buffer], rax
0x14009b533  test    rax, rax
0x14009b536  jnz     short loc_14009B542
0x14009b538  mov     ebx, 0C000009Ah
0x14009b53d  jmp     loc_14009B673
0x14009b542  lea     rdx, [rbp+57h+DestinationString]; SourceString
0x14009b546  mov     ebx, esi
0x14009b548  lea     rcx, [rbp+57h+Destination]; DestinationString
0x14009b54c  call    cs:__imp_RtlCopyUnicodeString
0x14009b553  nop     dword ptr [rax+rax+00h]
0x14009b558  mov     rdx, r15; Source
0x14009b55b  lea     rcx, [rbp+57h+Destination]; Destination
0x14009b55f  call    cs:__imp_RtlAppendUnicodeStringToString
0x14009b566  nop     dword ptr [rax+rax+00h]
0x14009b56b  mov     rdx, r14; Source
0x14009b56e  lea     rcx, [rbp+57h+Destination]; Destination
0x14009b572  call    cs:__imp_RtlAppendUnicodeStringToString
0x14009b579  nop     dword ptr [rax+rax+00h]
0x14009b57e  lea     rax, [rbp+57h+Destination]
0x14009b582  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14009b589  xorps   xmm0, xmm0
0x14009b58c  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14009b590  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14009b594  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x14009b598  mov     edx, 80000000h; DesiredAccess
0x14009b59d  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14009b5a4  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14009b5a8  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14009b5ad  call    cs:__imp_ZwOpenKey
0x14009b5b4  nop     dword ptr [rax+rax+00h]
0x14009b5b9  test    eax, eax
0x14009b5bb  jz      short loc_14009B5C6
0x14009b5bd  mov     [rbp+57h+KeyHandle], rsi
0x14009b5c1  jmp     loc_14009B688
0x14009b5c6  mov     edx, 218h
0x14009b5cb  mov     ecx, 42h ; 'B'
0x14009b5d0  mov     r8d, 2020444Eh
0x14009b5d6  call    cs:__imp_ExAllocatePool2
0x14009b5dd  nop     dword ptr [rax+rax+00h]
0x14009b5e2  mov     rdi, rax
0x14009b5e5  test    rax, rax
0x14009b5e8  jz      loc_14009B538
0x14009b5ee  xor     edx, edx; Val
0x14009b5f0  mov     r8d, 218h; Size
0x14009b5f6  mov     rcx, rdi; void *
0x14009b5f9  call    memset
0x14009b5fe  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x14009b602  lea     rax, [rbp+57h+arg_0]
0x14009b606  mov     [rsp+0E0h+ResultLength], rax; ResultLength
0x14009b60b  mov     r9, rdi; KeyInformation
0x14009b60e  xor     r8d, r8d; KeyInformationClass
0x14009b611  mov     [rsp+0E0h+Length], 216h; Length
0x14009b619  mov     edx, esi; Index
0x14009b61b  mov     [rbp+57h+arg_0], 0
0x14009b622  call    cs:__imp_ZwEnumerateKey
0x14009b629  nop     dword ptr [rax+rax+00h]
0x14009b62e  cmp     eax, 8000001Ah
0x14009b633  jz      short loc_14009B673
0x14009b635  test    eax, eax
0x14009b637  jnz     short loc_14009B66E
0x14009b639  movzx   eax, word ptr [rdi+0Ch]
0x14009b63d  lea     r8, [rbp+57h+var_80]; struct _UNICODE_STRING *
0x14009b641  mov     rdx, [rbp+57h+KeyHandle]; void *
0x14009b645  mov     r9b, r13b; unsigned __int8
0x14009b648  mov     [rbp+57h+var_80.Length], ax
0x14009b64c  mov     rcx, r12; struct _UNICODE_STRING *
0x14009b64f  add     ax, 2
0x14009b653  mov     [rbp+57h+var_80.MaximumLength], ax
0x14009b657  lea     rax, [rdi+10h]
0x14009b65b  mov     [rbp+57h+var_80.Buffer], rax
0x14009b65f  call    ?ndisSetFilterDefaultParameter@@YAHPEBU_UNICODE_STRING@@PEAX0E@Z; ndisSetFilterDefaultParameter(_UNICODE_STRING const *,void *,_UNICODE_STRING const *,uchar)
0x14009b664  mov     ebx, eax
0x14009b666  test    eax, eax
0x14009b668  jnz     short loc_14009B673
0x14009b66a  inc     esi
0x14009b66c  jmp     short loc_14009B5EE
0x14009b66e  mov     ebx, 0C0000001h
0x14009b673  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x14009b677  test    rcx, rcx
0x14009b67a  jz      short loc_14009B688
0x14009b67c  call    cs:__imp_ZwClose
0x14009b683  nop     dword ptr [rax+rax+00h]
0x14009b688  mov     rcx, [rbp+57h+Destination.Buffer]; P
0x14009b68c  test    rcx, rcx
0x14009b68f  jz      short loc_14009B69F
0x14009b691  xor     edx, edx; Tag
0x14009b693  call    cs:__imp_ExFreePoolWithTag
0x14009b69a  nop     dword ptr [rax+rax+00h]
0x14009b69f  test    rdi, rdi
0x14009b6a2  jz      short loc_14009B6B5
0x14009b6a4  xor     edx, edx; Tag
0x14009b6a6  mov     rcx, rdi; P
0x14009b6a9  call    cs:__imp_ExFreePoolWithTag
0x14009b6b0  nop     dword ptr [rax+rax+00h]
0x14009b6b5  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14009b6bc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14009b6c3  jz      short loc_14009B6FE
0x14009b6c5  mov     rcx, cs:WPP_GLOBAL_Control
0x14009b6cc  lea     rax, WPP_9524bb9419753e2807bcae08715ee655_Traceguids
0x14009b6d3  mov     dword ptr [rsp+0E0h+var_A0], ebx; char
0x14009b6d7  mov     r9d, 5Fh ; '_'; int
0x14009b6dd  mov     qword ptr [rsp+0E0h+var_A8], r14; char
0x14009b6e2  mov     qword ptr [rsp+0E0h+var_B0], r12; char
0x14009b6e7  mov     rcx, [rcx+40h]; int
0x14009b6eb  lea     r8d, [r9-5Eh]; int
0x14009b6ef  mov     [rsp+0E0h+ResultLength], r15; char
0x14009b6f4  mov     qword ptr [rsp+0E0h+Length], rax; struct _GUID *
0x14009b6f9  call    WPP_RECORDER_SF_qqqL
0x14009b6fe  mov     eax, ebx
0x14009b700  mov     rbx, [rsp+0E0h+arg_8]
0x14009b708  add     rsp, 0B0h
0x14009b70f  pop     r15
0x14009b711  pop     r14
0x14009b713  pop     r13
0x14009b715  pop     r12
0x14009b717  pop     rdi
0x14009b718  pop     rsi
0x14009b719  pop     rbp
0x14009b71a  retn
```
