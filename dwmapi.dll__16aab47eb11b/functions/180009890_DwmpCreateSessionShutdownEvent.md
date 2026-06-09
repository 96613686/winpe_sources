# DwmpCreateSessionShutdownEvent

- ea: `0x180009890`
- end: `0x180009a06`
- name: `DwmpCreateSessionShutdownEvent`
- size: `374`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x180003370`
- `0x180003b30`
- `0x180009890`
- `0x18000d0a0`

## import_xrefs

- `ntdll!NtCreateEvent` at `0x180009979`
- `ntdll!NtCreateEvent` at `0x180009979`
- `ntdll!RtlInitUnicodeString` at `0x180009900`
- `ntdll!RtlInitUnicodeString` at `0x180009900`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009908`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009908`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800099fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800099fe`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180009920`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180009920`

## pseudocode

```c
__int64 __fastcall DwmpCreateSessionShutdownEvent(unsigned int a1, void **a2)
{
  int v3; // eax
  int v4; // ebx
  NTSTATUS v5; // eax
  signed int LastError; // eax
  unsigned int v8; // edx
  int v9; // ecx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+30h] [rbp-79h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-71h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-41h] BYREF
  WCHAR SourceString[56]; // [rsp+80h] [rbp-29h] BYREF

  SecurityDescriptor = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v3 = StringCchPrintfW(SourceString, 0x35u, L"\\Sessions\\%d\\Windows\\DwmCatastrophicShutdown", a1);
  v4 = v3;
  if ( v3 < 0 )
  {
    v8 = 42;
    v9 = v3;
  }
  else
  {
    RtlInitUnicodeString(&DestinationString, SourceString);
    SetLastError(0);
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(L"D:(A;;0x00100002;;;SY)", 1u, &SecurityDescriptor, 0) )
    {
      if ( SecurityDescriptor )
      {
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.RootDirectory = 0;
        ObjectAttributes.Attributes = 0;
        ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
        ObjectAttributes.SecurityQualityOfService = 0;
        v5 = NtCreateEvent(a2, 0x100002u, &ObjectAttributes, NotificationEvent, 0);
        if ( v5 >= 0 )
          goto LABEL_5;
        v8 = 69;
        v4 = v5 | 0x10000000;
      }
      else
      {
        v4 = -2147024882;
        v8 = 57;
      }
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      v8 = 55;
      if ( v4 >= 0 )
        v4 = -2003304445;
    }
    v9 = v4;
  }
  DoStackCaptureDirect(v9, v8);
LABEL_5:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180009890  mov     [rsp-8+arg_10], rbx
0x180009895  mov     [rsp-8+arg_18], rdi
0x18000989a  push    rbp
0x18000989b  lea     rbp, [rsp-57h]
0x1800098a0  sub     rsp, 100h
0x1800098a7  mov     rax, cs:__security_cookie
0x1800098ae  xor     rax, rsp
0x1800098b1  mov     [rbp+57h+var_10], rax
0x1800098b5  xorps   xmm1, xmm1
0x1800098b8  mov     [rbp+57h+SecurityDescriptor], 0
0x1800098c0  mov     rdi, rdx
0x1800098c3  lea     r8, aSessionsDWindo; "\\Sessions\\%d\\Windows\\DwmCatastrophi"...
0x1800098ca  xorps   xmm0, xmm0
0x1800098cd  mov     r9d, ecx
0x1800098d0  mov     edx, 35h ; '5'; unsigned __int64
0x1800098d5  lea     rcx, [rbp+57h+SourceString]; unsigned __int16 *
0x1800098d9  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800098dd  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x1800098e1  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x1800098e5  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x1800098e9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800098ee  mov     ebx, eax
0x1800098f0  test    eax, eax
0x1800098f2  js      loc_1800099D7
0x1800098f8  lea     rdx, [rbp+57h+SourceString]; SourceString
0x1800098fc  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180009900  call    cs:__imp_RtlInitUnicodeString
0x180009906  xor     ecx, ecx; dwErrCode
0x180009908  call    cs:__imp_SetLastError
0x18000990e  xor     r9d, r9d; SecurityDescriptorSize
0x180009911  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180009915  lea     rcx, StringSecurityDescriptor; "D:(A;;0x00100002;;;SY)"
0x18000991c  lea     edx, [r9+1]; StringSDRevision
0x180009920  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180009926  test    eax, eax
0x180009928  jz      loc_1800099AF
0x18000992e  mov     rax, [rbp+57h+SecurityDescriptor]
0x180009932  test    rax, rax
0x180009935  jz      loc_1800099E5
0x18000993b  lea     rcx, [rbp+57h+DestinationString]
0x18000993f  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180009946  mov     [rbp+57h+ObjectAttributes.ObjectName], rcx
0x18000994a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000994e  mov     rcx, rdi; EventHandle
0x180009951  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180009959  xor     r9d, r9d; EventType
0x18000995c  mov     [rbp+57h+ObjectAttributes.Attributes], 0
0x180009963  mov     edx, 100002h; DesiredAccess
0x180009968  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rax
0x18000996c  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], 0
0x180009974  mov     [rsp+100h+InitialState], 0; InitialState
0x180009979  call    cs:__imp_NtCreateEvent
0x18000997f  test    eax, eax
0x180009981  js      short loc_1800099F1
0x180009983  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x180009987  test    rcx, rcx
0x18000998a  jnz     short loc_1800099FE
0x18000998c  mov     eax, ebx
0x18000998e  mov     rcx, [rbp+57h+var_10]
0x180009992  xor     rcx, rsp; StackCookie
0x180009995  call    __security_check_cookie
0x18000999a  lea     r11, [rsp+100h+var_s0]
0x1800099a2  mov     rbx, [r11+20h]
0x1800099a6  mov     rdi, [r11+28h]
0x1800099aa  mov     rsp, r11
0x1800099ad  pop     rbp
0x1800099ae  retn
0x1800099af  call    cs:__imp_GetLastError
0x1800099b5  mov     ebx, eax
0x1800099b7  test    eax, eax
0x1800099b9  jle     short loc_1800099C4
0x1800099bb  movzx   ebx, ax
0x1800099be  or      ebx, 80070000h
0x1800099c4  test    ebx, ebx
0x1800099c6  mov     eax, 88980003h
0x1800099cb  mov     edx, 37h ; '7'
0x1800099d0  cmovns  ebx, eax
0x1800099d3  mov     ecx, ebx
0x1800099d5  jmp     short loc_1800099DE
0x1800099d7  mov     edx, 2Ah ; '*'; unsigned int
0x1800099dc  mov     ecx, eax; int
0x1800099de  call    ?DoStackCaptureDirect@@YAXJI@Z; DoStackCaptureDirect(long,uint)
0x1800099e3  jmp     short loc_180009983
0x1800099e5  mov     ebx, 8007000Eh
0x1800099ea  mov     edx, 39h ; '9'
0x1800099ef  jmp     short loc_1800099D3
0x1800099f1  mov     ebx, eax
0x1800099f3  mov     edx, 45h ; 'E'
0x1800099f8  bts     ebx, 1Ch
0x1800099fc  jmp     short loc_1800099D3
0x1800099fe  call    cs:__imp_LocalFree
0x180009a04  jmp     short loc_18000998C
```
