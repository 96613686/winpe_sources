# Dot11InitRegistry

- ea: `0x1400be6fc`
- end: `0x1400be8a1`
- name: `Dot11InitRegistry`
- size: `421`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400be4d4`

## callees

- `0x140020dc0`
- `0x1400bccec`
- `0x1400be6fc`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400be759`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400be7dc`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400be759`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400be7dc`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x1400be738`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x1400be738`
- `ntoskrnl!ZwCreateKey` at `0x1400be7bb`
- `ntoskrnl!ZwCreateKey` at `0x1400be83e`
- `ntoskrnl!ZwCreateKey` at `0x1400be7bb`
- `ntoskrnl!ZwCreateKey` at `0x1400be83e`

## pseudocode

```c
__int64 __fastcall Dot11InitRegistry(__int64 a1)
{
  NTSTATUS v1; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF

  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  v1 = IoOpenDriverRegistryKey(a1, 1, 131103);
  if ( v1 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"Parameters");
    ObjectAttributes.RootDirectory = *(HANDLE *)&WPP_MAIN_CB.AlignmentRequirement;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v1 = ZwCreateKey(&WPP_MAIN_CB.Queue.Wcb.CurrentIrp, 0x2001Fu, &ObjectAttributes, 0, 0, 0, 0);
    if ( v1 >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"Adapters");
      ObjectAttributes.RootDirectory = WPP_MAIN_CB.Queue.Wcb.CurrentIrp;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.Length = 48;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v1 = ZwCreateKey((PHANDLE)&WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc, 0x2001Fu, &ObjectAttributes, 0, 0, 0, 0);
      if ( v1 >= 0 )
        return 0;
    }
  }
  Dot11DeInitRegistry();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_a01680d69d263cc9eb0985aaa3057085_Traceguids, (unsigned int)v1);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1400be6fc  mov     [rsp-8+arg_0], rbx
0x1400be701  push    rbp
0x1400be702  mov     rbp, rsp
0x1400be705  sub     rsp, 80h
0x1400be70c  xorps   xmm0, xmm0
0x1400be70f  lea     rax, WPP_MAIN_CB.AlignmentRequirement
0x1400be716  xor     r9d, r9d
0x1400be719  mov     [rsp+80h+Class], rax
0x1400be71e  mov     r8d, 2001Fh
0x1400be724  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1400be728  lea     edx, [r9+1]
0x1400be72c  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1400be730  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400be734  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400be738  call    cs:__imp_IoOpenDriverRegistryKey
0x1400be73f  nop     dword ptr [rax+rax+00h]
0x1400be744  mov     ebx, eax
0x1400be746  test    eax, eax
0x1400be748  js      loc_1400BE854
0x1400be74e  lea     rdx, aParameters; "Parameters"
0x1400be755  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400be759  call    cs:__imp_RtlInitUnicodeString
0x1400be760  nop     dword ptr [rax+rax+00h]
0x1400be765  mov     rax, qword ptr cs:WPP_MAIN_CB.AlignmentRequirement
0x1400be76c  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400be770  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x1400be774  lea     rcx, WPP_MAIN_CB.Queue+38h; KeyHandle
0x1400be77b  lea     rax, [rbp+DestinationString]
0x1400be77f  mov     [rsp+80h+Disposition], 0; Disposition
0x1400be788  xorps   xmm0, xmm0
0x1400be78b  mov     [rsp+80h+CreateOptions], 0; CreateOptions
0x1400be793  xor     r9d, r9d; TitleIndex
0x1400be796  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400be79a  mov     edx, 2001Fh; DesiredAccess
0x1400be79f  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400be7a6  mov     [rbp+ObjectAttributes.Attributes], 240h
0x1400be7ad  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400be7b2  mov     [rsp+80h+Class], 0; Class
0x1400be7bb  call    cs:__imp_ZwCreateKey
0x1400be7c2  nop     dword ptr [rax+rax+00h]
0x1400be7c7  mov     ebx, eax
0x1400be7c9  test    eax, eax
0x1400be7cb  js      loc_1400BE854
0x1400be7d1  lea     rdx, aAdapters; "Adapters"
0x1400be7d8  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400be7dc  call    cs:__imp_RtlInitUnicodeString
0x1400be7e3  nop     dword ptr [rax+rax+00h]
0x1400be7e8  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x1400be7ef  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400be7f3  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x1400be7f7  lea     rcx, WPP_MAIN_CB.Queue+40h; KeyHandle
0x1400be7fe  lea     rax, [rbp+DestinationString]
0x1400be802  mov     [rsp+80h+Disposition], 0; Disposition
0x1400be80b  xorps   xmm0, xmm0
0x1400be80e  mov     [rsp+80h+CreateOptions], 0; CreateOptions
0x1400be816  xor     r9d, r9d; TitleIndex
0x1400be819  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1400be81d  mov     edx, 2001Fh; DesiredAccess
0x1400be822  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400be829  mov     [rbp+ObjectAttributes.Attributes], 240h
0x1400be830  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400be835  mov     [rsp+80h+Class], 0; Class
0x1400be83e  call    cs:__imp_ZwCreateKey
0x1400be845  nop     dword ptr [rax+rax+00h]
0x1400be84a  mov     ebx, eax
0x1400be84c  test    eax, eax
0x1400be84e  js      short loc_1400BE854
0x1400be850  xor     eax, eax
0x1400be852  jmp     short loc_1400BE88F
0x1400be854  call    Dot11DeInitRegistry
0x1400be859  mov     rcx, cs:WPP_GLOBAL_Control
0x1400be860  lea     rax, WPP_GLOBAL_Control
0x1400be867  cmp     rcx, rax
0x1400be86a  jz      short loc_1400BE88D
0x1400be86c  test    dword ptr [rcx+2Ch], 200h
0x1400be873  jz      short loc_1400BE88D
0x1400be875  mov     rcx, [rcx+18h]
0x1400be879  lea     r8, WPP_a01680d69d263cc9eb0985aaa3057085_Traceguids
0x1400be880  mov     edx, 0Ah
0x1400be885  mov     r9d, ebx
0x1400be888  call    WPP_SF_d
0x1400be88d  mov     eax, ebx
0x1400be88f  mov     rbx, [rsp+80h+arg_0]
0x1400be897  add     rsp, 80h
0x1400be89e  pop     rbp
0x1400be89f  retn
```
