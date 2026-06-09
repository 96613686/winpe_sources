# CscRegistryInitializeParams

- ea: `0x14002115c`
- end: `0x1400212e0`
- name: `CscRegistryInitializeParams`
- size: `388`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140090740`

## callees

- `0x1400190ec`
- `0x14001a69c`
- `0x14002115c`
- `0x14002166c`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140021299`
- `ntoskrnl!ZwClose` at `0x140021299`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002118c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002118c`
- `ntoskrnl!ExInitializeResourceLite` at `0x14002126e`
- `ntoskrnl!ExInitializeResourceLite` at `0x14002126e`
- `ntoskrnl!ZwOpenKey` at `0x1400211cb`
- `ntoskrnl!ZwOpenKey` at `0x1400211cb`

## string_xrefs

- `0x14002116b`: `\Registry\Machine\System\CurrentControlSet\Services\CSC\Parameters`

## pseudocode

```c
__int64 CscRegistryInitializeParams()
{
  NTSTATUS v0; // eax
  NTSTATUS Param; // ebx
  int v2; // edi
  int i; // edi
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF
  void *KeyHandle; // [rsp+A0h] [rbp+28h] BYREF

  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\CSC\\Parameters");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v0 = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  Param = v0;
  if ( v0 >= 0 )
    goto LABEL_7;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_ZD(
      WPP_GLOBAL_Control->AttachedDevice,
      12,
      (unsigned int)WPP_d79ea00412a8325f3b090053ac99afd3_Traceguids,
      (unsigned int)&DestinationString,
      v0);
  if ( Param == -1073741772 )
  {
LABEL_7:
    for ( i = 0; i < 19; ++i )
    {
      if ( i != LODWORD(qword_14003A130[9 * i]) )
      {
        Param = -1073741811;
        v2 = 847;
        goto LABEL_17;
      }
      Param = CscRegistrypLoadParam(KeyHandle);
      if ( Param < 0 )
      {
        v2 = 852;
        goto LABEL_17;
      }
    }
    Param = ExInitializeResourceLite(&Resource);
    if ( Param >= 0 )
    {
      v2 = 0;
      byte_14003A0C0[0] = 1;
    }
    else
    {
      v2 = 856;
    }
  }
  else
  {
    v2 = 834;
  }
LABEL_17:
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      13,
      WPP_d79ea00412a8325f3b090053ac99afd3_Traceguids,
      (unsigned int)Param,
      v2);
  return (unsigned int)Param;
}

```

## disassembly

```asm
0x14002115c  push    rbp
0x14002115e  push    rbx
0x14002115f  push    rsi
0x140021160  push    rdi
0x140021161  mov     rbp, rsp
0x140021164  sub     rsp, 78h
0x140021168  xorps   xmm0, xmm0
0x14002116b  lea     rdx, SourceString; "\\Registry\\Machine\\System\\CurrentCon"...
0x140021172  xor     eax, eax
0x140021174  lea     rcx, [rbp+DestinationString]; DestinationString
0x140021178  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14002117c  mov     [rbp+KeyHandle], rax
0x140021180  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140021184  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140021188  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14002118c  call    cs:__imp_RtlInitUnicodeString
0x140021193  nop     dword ptr [rax+rax+00h]
0x140021198  lea     rax, [rbp+DestinationString]
0x14002119c  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400211a3  xorps   xmm0, xmm0
0x1400211a6  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400211aa  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400211ae  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1400211b6  mov     edx, 20019h; DesiredAccess
0x1400211bb  mov     [rbp+ObjectAttributes.Attributes], 240h
0x1400211c2  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x1400211c6  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400211cb  call    cs:__imp_ZwOpenKey
0x1400211d2  nop     dword ptr [rax+rax+00h]
0x1400211d7  lea     rsi, WPP_GLOBAL_Control
0x1400211de  mov     ebx, eax
0x1400211e0  test    eax, eax
0x1400211e2  jns     short loc_140021224
0x1400211e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400211eb  cmp     rcx, rsi
0x1400211ee  jz      short loc_140021215
0x1400211f0  mov     edx, [rcx+2Ch]
0x1400211f3  test    dl, 20h
0x1400211f6  jz      short loc_140021215
0x1400211f8  mov     rcx, [rcx+18h]
0x1400211fc  lea     r9, [rbp+DestinationString]
0x140021200  mov     edx, 0Ch
0x140021205  mov     [rsp+78h+var_58], eax
0x140021209  lea     r8, WPP_d79ea00412a8325f3b090053ac99afd3_Traceguids
0x140021210  call    WPP_SF_ZD
0x140021215  cmp     ebx, 0C0000034h
0x14002121b  jz      short loc_140021224
0x14002121d  mov     edi, 342h
0x140021222  jmp     short loc_140021290
0x140021224  xor     edi, edi
0x140021226  cmp     edi, 13h
0x140021229  jge     short loc_140021267
0x14002122b  movsxd  rax, edi
0x14002122e  lea     rcx, [rax+rax*8]
0x140021232  lea     rax, qword_14003A130
0x140021239  lea     rdx, [rax+rcx*8]
0x14002123d  cmp     edi, [rdx]
0x14002123f  jnz     short loc_14002125B
0x140021241  mov     rcx, [rbp+KeyHandle]
0x140021245  call    CscRegistrypLoadParam
0x14002124a  mov     ebx, eax
0x14002124c  test    eax, eax
0x14002124e  js      short loc_140021254
0x140021250  inc     edi
0x140021252  jmp     short loc_140021226
0x140021254  mov     edi, 354h
0x140021259  jmp     short loc_140021290
0x14002125b  mov     ebx, 0C000000Dh
0x140021260  mov     edi, 34Fh
0x140021265  jmp     short loc_140021290
0x140021267  lea     rcx, Resource; Resource
0x14002126e  call    cs:__imp_ExInitializeResourceLite
0x140021275  nop     dword ptr [rax+rax+00h]
0x14002127a  mov     ebx, eax
0x14002127c  test    eax, eax
0x14002127e  jns     short loc_140021287
0x140021280  mov     edi, 358h
0x140021285  jmp     short loc_140021290
0x140021287  xor     edi, edi
0x140021289  mov     cs:byte_14003A0C0, 1
0x140021290  mov     rcx, [rbp+KeyHandle]; Handle
0x140021294  test    rcx, rcx
0x140021297  jz      short loc_1400212A5
0x140021299  call    cs:__imp_ZwClose
0x1400212a0  nop     dword ptr [rax+rax+00h]
0x1400212a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400212ac  cmp     rcx, rsi
0x1400212af  jz      short loc_1400212D4
0x1400212b1  mov     eax, [rcx+2Ch]
0x1400212b4  test    al, 20h
0x1400212b6  jz      short loc_1400212D4
0x1400212b8  mov     rcx, [rcx+18h]
0x1400212bc  lea     r8, WPP_d79ea00412a8325f3b090053ac99afd3_Traceguids
0x1400212c3  mov     edx, 0Dh
0x1400212c8  mov     [rsp+78h+var_58], edi
0x1400212cc  mov     r9d, ebx
0x1400212cf  call    WPP_SF_Dd
0x1400212d4  mov     eax, ebx
0x1400212d6  add     rsp, 78h
0x1400212da  pop     rdi
0x1400212db  pop     rsi
0x1400212dc  pop     rbx
0x1400212dd  pop     rbp
0x1400212de  retn
```
