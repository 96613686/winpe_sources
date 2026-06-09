# CsrShutdownProcesses

- ea: `0x180007060`
- end: `0x18000724c`
- name: `CsrShutdownProcesses`
- size: `492`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180006a80`
- `0x180007060`
- `0x180007260`
- `0x1800072c0`
- `0x1800083b0`
- `0x18000ab80`

## import_xrefs

- `ntdll!NtOpenKey` at `0x1800070f9`
- `ntdll!NtOpenKey` at `0x1800070f9`
- `ntdll!RtlInitUnicodeString` at `0x1800070be`
- `ntdll!RtlInitUnicodeString` at `0x1800071cd`
- `ntdll!RtlInitUnicodeString` at `0x1800070be`
- `ntdll!RtlInitUnicodeString` at `0x1800071cd`
- `ntdll!NtClose` at `0x180007210`
- `ntdll!NtClose` at `0x180007210`
- `ntdll!NtQueryValueKey` at `0x1800071fc`
- `ntdll!NtQueryValueKey` at `0x1800071fc`
- `ntdll!NtSetInformationProcess` at `0x180007183`
- `ntdll!NtSetInformationProcess` at `0x180007183`

## string_xrefs

- `0x180007090`: `\Registry\Machine\Software\Policies\Microsoft\Windows\System`

## pseudocode

```c
__int64 __fastcall CsrShutdownProcesses(__int64 a1, int a2)
{
  int v3; // r14d
  int v4; // ebx
  unsigned int v5; // esi
  int ProcessInformation; // [rsp+30h] [rbp-29h] BYREF
  ULONG ResultLength; // [rsp+38h] [rbp-21h] BYREF
  void *KeyHandle; // [rsp+40h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-11h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-1h] BYREF
  __int128 KeyValueInformation; // [rsp+88h] [rbp+2Fh] BYREF

  ProcessInformation = a2;
  ResultLength = 0;
  KeyHandle = 0;
  v3 = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  KeyValueInformation = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\Software\\Policies\\Microsoft\\Windows\\System");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"SerializeAppShutdown");
    if ( NtQueryValueKey(
           KeyHandle,
           &DestinationString,
           KeyValuePartialInformationAlign64,
           &KeyValueInformation,
           0x10u,
           &ResultLength) >= 0
      && ((_DWORD)KeyValueInformation == 4 || DWORD1(KeyValueInformation) == 4)
      && DWORD2(KeyValueInformation) == 1 )
    {
      v3 = 1;
    }
    NtClose(KeyHandle);
  }
  CsrResetShutdownFlags(a1);
  CsrEventWrite(&CsrEvt_ShutdownProcesses_Start);
  CsrpSetToShutdownPriority();
  v4 = -2;
  if ( (unsigned int)((MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24) != -1 )
    v4 = (MEMORY[0x7FFE0320] * (unsigned __int64)MEMORY[0x7FFE0004]) >> 24;
  do
    v5 = ShutdownProcesses(&ProcessInformation, v4, v3, a1);
  while ( v5 != -2147483622 && v5 != -1073741536 );
  ProcessInformation = 13;
  NtSetInformationProcess((HANDLE)0xFFFFFFFFFFFFFFFFLL, ProcessBasePriority, &ProcessInformation, 4u);
  CsrEventWrite(&CsrEvt_ShutdownProcesses_Stop);
  return v5;
}

```

## disassembly

```asm
0x180007060  mov     [rsp-8+arg_10], rbx
0x180007065  mov     [rsp-8+arg_18], rsi
0x18000706a  push    rbp
0x18000706b  push    rdi
0x18000706c  push    r14
0x18000706e  lea     rbp, [rsp-47h]
0x180007073  sub     rsp, 0A0h
0x18000707a  mov     rax, cs:__security_cookie
0x180007081  xor     rax, rsp
0x180007084  mov     [rbp+57h+var_18], rax
0x180007088  xorps   xmm0, xmm0
0x18000708b  mov     [rbp+57h+ProcessInformation], edx
0x18000708e  xor     ebx, ebx
0x180007090  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\Software\\Policies"...
0x180007097  mov     rdi, rcx
0x18000709a  mov     [rbp+57h+var_78], ebx
0x18000709d  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800070a1  xor     eax, eax
0x1800070a3  mov     [rbp+57h+KeyHandle], rbx
0x1800070a7  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800070ab  mov     r14d, ebx
0x1800070ae  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800070b2  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800070b6  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800070ba  movups  [rbp+57h+KeyValueInformation], xmm0
0x1800070be  call    cs:__imp_RtlInitUnicodeString
0x1800070c5  nop     dword ptr [rax+rax+00h]
0x1800070ca  lea     rax, [rbp+57h+DestinationString]
0x1800070ce  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800070d5  xorps   xmm0, xmm0
0x1800070d8  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800070dc  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800070e0  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x1800070e4  mov     edx, 20019h; DesiredAccess
0x1800070e9  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800070f0  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800070f4  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800070f9  call    cs:__imp_NtOpenKey
0x180007100  nop     dword ptr [rax+rax+00h]
0x180007105  test    eax, eax
0x180007107  jns     loc_1800071C2
0x18000710d  mov     rcx, rdi
0x180007110  call    CsrResetShutdownFlags
0x180007115  lea     rcx, CsrEvt_ShutdownProcesses_Start; EventDescriptor
0x18000711c  call    CsrEventWrite
0x180007121  call    CsrpSetToShutdownPriority
0x180007126  mov     eax, 7FFE0320h
0x18000712b  mov     ebx, 0FFFFFFFEh
0x180007130  mov     rax, [rax]
0x180007133  mov     ecx, ds:7FFE0004h
0x18000713a  imul    rcx, rax
0x18000713e  shr     rcx, 18h
0x180007142  cmp     ecx, 0FFFFFFFFh
0x180007145  cmovnz  ebx, ecx
0x180007148  mov     r9, rdi
0x18000714b  lea     rcx, [rbp+57h+ProcessInformation]
0x18000714f  mov     r8d, r14d
0x180007152  mov     edx, ebx
0x180007154  call    ShutdownProcesses
0x180007159  mov     esi, eax
0x18000715b  cmp     eax, 8000001Ah
0x180007160  jnz     loc_180007221
0x180007166  mov     r9d, 4; ProcessInformationLength
0x18000716c  mov     [rbp+57h+ProcessInformation], 0Dh
0x180007173  lea     r8, [rbp+57h+ProcessInformation]; ProcessInformation
0x180007177  mov     edx, 5; ProcessInformationClass
0x18000717c  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180007183  call    cs:__imp_NtSetInformationProcess
0x18000718a  nop     dword ptr [rax+rax+00h]
0x18000718f  lea     rcx, CsrEvt_ShutdownProcesses_Stop; EventDescriptor
0x180007196  call    CsrEventWrite
0x18000719b  mov     eax, esi
0x18000719d  mov     rcx, [rbp+57h+var_18]
0x1800071a1  xor     rcx, rsp; StackCookie
0x1800071a4  call    __security_check_cookie
0x1800071a9  lea     r11, [rsp+0B0h+var_10]
0x1800071b1  mov     rbx, [r11+30h]
0x1800071b5  mov     rsi, [r11+38h]
0x1800071b9  mov     rsp, r11
0x1800071bc  pop     r14
0x1800071be  pop     rdi
0x1800071bf  pop     rbp
0x1800071c0  retn
0x1800071c2  lea     rdx, aSerializeappsh; "SerializeAppShutdown"
0x1800071c9  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800071cd  call    cs:__imp_RtlInitUnicodeString
0x1800071d4  nop     dword ptr [rax+rax+00h]
0x1800071d9  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800071dd  lea     rax, [rbp+57h+var_78]
0x1800071e1  mov     [rsp+0B0h+ResultLength], rax; ResultLength
0x1800071e6  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x1800071ea  mov     r8d, 4; KeyValueInformationClass
0x1800071f0  mov     [rsp+0B0h+Length], 10h; Length
0x1800071f8  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x1800071fc  call    cs:__imp_NtQueryValueKey
0x180007203  nop     dword ptr [rax+rax+00h]
0x180007208  test    eax, eax
0x18000720a  jns     short loc_180007232
0x18000720c  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x180007210  call    cs:__imp_NtClose
0x180007217  nop     dword ptr [rax+rax+00h]
0x18000721c  jmp     loc_18000710D
0x180007221  cmp     esi, 0C0000120h
0x180007227  jnz     loc_180007148
0x18000722d  jmp     loc_180007166
0x180007232  cmp     dword ptr [rbp+57h+KeyValueInformation], 4
0x180007236  jz      short loc_18000723E
0x180007238  cmp     dword ptr [rbp+57h+KeyValueInformation+4], 4
0x18000723c  jnz     short loc_18000720C
0x18000723e  mov     eax, 1
0x180007243  cmp     dword ptr [rbp+57h+KeyValueInformation+8], eax
0x180007246  cmovz   r14d, eax
0x18000724a  jmp     short loc_18000720C
```
