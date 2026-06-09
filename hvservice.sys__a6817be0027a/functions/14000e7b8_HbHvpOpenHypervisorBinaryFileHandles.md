# HbHvpOpenHypervisorBinaryFileHandles

- ea: `0x14000e7b8`
- end: `0x14000e99d`
- name: `HbHvpOpenHypervisorBinaryFileHandles`
- size: `485`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000e6fc`

## callees

- `0x140002a16`
- `0x140002ae0`
- `0x14000e75c`
- `0x14000e7b8`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000e807`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000e909`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000e807`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000e909`
- `ntoskrnl!ZwOpenFile` at `0x14000e85d`
- `ntoskrnl!ZwOpenFile` at `0x14000e95f`
- `ntoskrnl!ZwOpenFile` at `0x14000e85d`
- `ntoskrnl!ZwOpenFile` at `0x14000e95f`

## string_xrefs

- `0x14000e7e0`: `\SystemRoot\System32\hvloader.dll`
- `0x14000e8fe`: `\SystemRoot\System32\hvax64.exe`
- `0x14000e8f3`: `\SystemRoot\System32\hvix64.exe`

## pseudocode

```c
__int64 __fastcall HbHvpOpenHypervisorBinaryFileHandles(__int64 a1)
{
  NTSTATUS v2; // ebx
  int v8; // eax
  const WCHAR *v9; // rdx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-39h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp+7h] BYREF
  char Str1[16]; // [rsp+80h] [rbp+17h] BYREF
  char Str2[16]; // [rsp+90h] [rbp+27h] BYREF
  char v16[16]; // [rsp+A0h] [rbp+37h] BYREF

  DestinationString = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  RtlInitUnicodeString(&DestinationString, L"\\SystemRoot\\System32\\hvloader.dll");
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = ZwOpenFile((PHANDLE)(a1 + 200), 0x80000000, &ObjectAttributes, &IoStatusBlock, 5u, 0x20u);
  if ( v2 < 0 )
    goto LABEL_6;
  _RAX = 0;
  __asm { cpuid }
  *(_DWORD *)&Str1[4] = _RBX;
  *(_DWORD *)&Str1[12] = _RCX;
  *(_DWORD *)&Str1[8] = _RDX;
  strcpy(Str2, "AuthenticAMD");
  strcpy(v16, "HygonGenuine");
  *(_DWORD *)Str1 = _RAX;
  if ( !strncmp_0(&Str1[4], Str2, 0xCu)
    || (v8 = strncmp_0(&Str1[4], v16, 0xCu), v9 = L"\\SystemRoot\\System32\\hvix64.exe", !v8) )
  {
    v9 = L"\\SystemRoot\\System32\\hvax64.exe";
  }
  RtlInitUnicodeString(&DestinationString, v9);
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v2 = ZwOpenFile((PHANDLE)(a1 + 192), 0x80000000, &ObjectAttributes, &IoStatusBlock, 5u, 0x20u);
  if ( v2 < 0 )
LABEL_6:
    HbHvpCloseHypervisorBinaryFileHandles(a1);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14000e7b8  mov     [rsp-8+arg_8], rbx
0x14000e7bd  mov     [rsp-8+arg_10], rdi
0x14000e7c2  push    rbp
0x14000e7c3  lea     rbp, [rsp-57h]
0x14000e7c8  sub     rsp, 0C0h
0x14000e7cf  mov     rax, cs:__security_cookie
0x14000e7d6  xor     rax, rsp
0x14000e7d9  mov     [rbp+57h+var_10], rax
0x14000e7dd  xorps   xmm0, xmm0
0x14000e7e0  lea     rdx, aSystemrootSyst; "\\SystemRoot\\System32\\hvloader.dll"
0x14000e7e7  mov     rdi, rcx
0x14000e7ea  xorps   xmm1, xmm1
0x14000e7ed  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14000e7f1  xor     eax, eax
0x14000e7f3  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000e7f7  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14000e7fb  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14000e7ff  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x14000e803  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14000e807  call    cs:__imp_RtlInitUnicodeString
0x14000e80e  nop     dword ptr [rax+rax+00h]
0x14000e813  lea     rax, [rbp+57h+DestinationString]
0x14000e817  mov     [rsp+0C0h+OpenOptions], 20h ; ' '; OpenOptions
0x14000e81f  xorps   xmm0, xmm0
0x14000e822  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14000e826  lea     rcx, [rdi+0C8h]; FileHandle
0x14000e82d  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000e834  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14000e838  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14000e840  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000e844  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14000e84b  mov     edx, 80000000h; DesiredAccess
0x14000e850  mov     [rsp+0C0h+ShareAccess], 5; ShareAccess
0x14000e858  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000e85d  call    cs:__imp_ZwOpenFile
0x14000e864  nop     dword ptr [rax+rax+00h]
0x14000e869  mov     ebx, eax
0x14000e86b  test    eax, eax
0x14000e86d  js      loc_14000E971
0x14000e873  mov     eax, dword ptr cs:aAuthenticamd+8; "cAMD"
0x14000e879  xor     ecx, ecx
0x14000e87b  movsd   xmm1, qword ptr cs:aAuthenticamd; "AuthenticAMD"
0x14000e883  xorps   xmm0, xmm0
0x14000e886  mov     dword ptr [rbp+57h+var_28], eax
0x14000e889  mov     al, byte ptr cs:aAuthenticamd+0Ch; ""
0x14000e88f  movups  xmmword ptr [rbp+57h+Str1], xmm0
0x14000e893  mov     [rbp+57h+var_28+4], al
0x14000e896  mov     eax, dword ptr cs:aHygongenuine+8; "uine"
0x14000e89c  movsd   xmm0, qword ptr cs:aHygongenuine; "HygonGenuine"
0x14000e8a4  mov     dword ptr [rbp+57h+var_20+8], eax
0x14000e8a7  mov     al, byte ptr cs:aHygongenuine+0Ch; ""
0x14000e8ad  mov     [rbp+57h+var_20+0Ch], al
0x14000e8b0  xor     eax, eax
0x14000e8b2  cpuid
0x14000e8b4  mov     dword ptr [rbp+57h+Str1+4], ebx
0x14000e8b7  mov     ebx, 0Ch
0x14000e8bc  mov     dword ptr [rbp+57h+Str1+0Ch], ecx
0x14000e8bf  mov     r8d, ebx; MaxCount
0x14000e8c2  mov     dword ptr [rbp+57h+Str1+8], edx
0x14000e8c5  lea     rcx, [rbp+57h+Str1+4]; Str1
0x14000e8c9  lea     rdx, [rbp+57h+Str2]; Str2
0x14000e8cd  movsd   qword ptr [rbp+57h+Str2], xmm1
0x14000e8d2  movsd   qword ptr [rbp+57h+var_20], xmm0
0x14000e8d7  mov     dword ptr [rbp+57h+Str1], eax
0x14000e8da  call    strncmp_0
0x14000e8df  test    eax, eax
0x14000e8e1  jz      short loc_14000E8FE
0x14000e8e3  mov     r8d, ebx; MaxCount
0x14000e8e6  lea     rdx, [rbp+57h+var_20]; Str2
0x14000e8ea  lea     rcx, [rbp+57h+Str1+4]; Str1
0x14000e8ee  call    strncmp_0
0x14000e8f3  lea     rdx, aSystemrootSyst_0; "\\SystemRoot\\System32\\hvix64.exe"
0x14000e8fa  test    eax, eax
0x14000e8fc  jnz     short loc_14000E905
0x14000e8fe  lea     rdx, aSystemrootSyst_1; "\\SystemRoot\\System32\\hvax64.exe"
0x14000e905  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000e909  call    cs:__imp_RtlInitUnicodeString
0x14000e910  nop     dword ptr [rax+rax+00h]
0x14000e915  lea     rax, [rbp+57h+DestinationString]
0x14000e919  mov     [rsp+0C0h+OpenOptions], 20h ; ' '; OpenOptions
0x14000e921  xorps   xmm0, xmm0
0x14000e924  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14000e928  lea     rcx, [rdi+0C0h]; FileHandle
0x14000e92f  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000e936  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14000e93a  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14000e942  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000e946  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14000e94d  mov     edx, 80000000h; DesiredAccess
0x14000e952  mov     [rsp+0C0h+ShareAccess], 5; ShareAccess
0x14000e95a  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000e95f  call    cs:__imp_ZwOpenFile
0x14000e966  nop     dword ptr [rax+rax+00h]
0x14000e96b  mov     ebx, eax
0x14000e96d  test    eax, eax
0x14000e96f  jns     short loc_14000E979
0x14000e971  mov     rcx, rdi
0x14000e974  call    HbHvpCloseHypervisorBinaryFileHandles
0x14000e979  mov     eax, ebx
0x14000e97b  mov     rcx, [rbp+57h+var_10]
0x14000e97f  xor     rcx, rsp; StackCookie
0x14000e982  call    __security_check_cookie
0x14000e987  lea     r11, [rsp+0C0h+var_s0]
0x14000e98f  mov     rbx, [r11+18h]
0x14000e993  mov     rdi, [r11+20h]
0x14000e997  mov     rsp, r11
0x14000e99a  pop     rbp
0x14000e99b  retn
```
