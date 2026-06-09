# SspGetProcessName

- ea: `0x18004ce98`
- end: `0x18004d048`
- name: `SspGetProcessName`
- size: `432`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180050890`

## callees

- `0x18000cba0`
- `0x18002ee7c`
- `0x18002fb50`
- `0x180030844`
- `0x18004ce98`
- `0x18006bd80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18004cfe0`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18004cfe0`
- `ntdll!NtQueryInformationProcess` at `0x18004cf9d`
- `ntdll!NtQueryInformationProcess` at `0x18004cf9d`
- `ntdll!NtOpenProcess` at `0x18004cf36`
- `ntdll!NtOpenProcess` at `0x18004cf36`
- `ntdll!NtClose` at `0x18004d01c`
- `ntdll!NtClose` at `0x18004d01c`
- `ntdll!RtlInitUnicodeString` at `0x18004cffd`
- `ntdll!RtlInitUnicodeString` at `0x18004cffd`

## pseudocode

```c
__int64 __fastcall SspGetProcessName(unsigned int a1, __int64 a2)
{
  unsigned __int64 v3; // rbx
  NTSTATUS v4; // ebx
  wchar_t *v5; // rax
  const WCHAR *p_ProcessInformation; // rax
  void *ProcessHandle; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-C8h] BYREF
  _CLIENT_ID ClientId; // [rsp+48h] [rbp-B8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t ProcessInformation; // [rsp+90h] [rbp-70h] BYREF
  USHORT v13; // [rsp+92h] [rbp-6Eh]
  int v14; // [rsp+94h] [rbp-6Ch]
  void *Src; // [rsp+98h] [rbp-68h]

  v3 = a1;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ProcessHandle = 0;
  memset_0(&ProcessInformation, 0, 0x212u);
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  ClientId.UniqueProcess = (HANDLE)v3;
  ClientId.UniqueThread = 0;
  DestinationString = 0;
  v4 = NtOpenProcess(&ProcessHandle, 0x400u, &ObjectAttributes, &ClientId);
  if ( v4 >= 0 )
  {
    v4 = NtQueryInformationProcess(ProcessHandle, ProcessImageFileName, &ProcessInformation, 0x210u, 0);
    if ( v4 >= 0 )
    {
      DestinationString.Length = ProcessInformation;
      DestinationString.MaximumLength = v13;
      *(_DWORD *)(&DestinationString.MaximumLength + 1) = v14;
      DestinationString.Buffer = (PWSTR)Src;
      memmove_0(&ProcessInformation, Src, v13);
      v5 = wcsrchr(&ProcessInformation, 0x5Cu);
      if ( v5 )
        p_ProcessInformation = v5 + 1;
      else
        p_ProcessInformation = &ProcessInformation;
      RtlInitUnicodeString(&DestinationString, p_ProcessInformation);
      v4 = NtLmDuplicateUnicodeString(a2, &DestinationString);
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_ced0880886a53ec11230ac267b1eff8e_Traceguids, (unsigned int)v4);
  }
  if ( ProcessHandle )
    NtClose(ProcessHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18004ce98  mov     [rsp-8+arg_10], rbx
0x18004ce9d  mov     [rsp-8+arg_18], rdi
0x18004cea2  push    rbp
0x18004cea3  lea     rbp, [rsp-1C0h]
0x18004ceab  sub     rsp, 2C0h
0x18004ceb2  mov     rax, cs:__security_cookie
0x18004ceb9  xor     rax, rsp
0x18004cebc  mov     [rbp+1C0h+var_10], rax
0x18004cec3  mov     rdi, rdx
0x18004cec6  mov     ebx, ecx
0x18004cec8  xor     edx, edx; Val
0x18004ceca  mov     qword ptr [rsp+2C0h+ObjectAttributes.Length], 30h ; '0'
0x18004ced3  lea     rcx, [rbp+1C0h+ProcessInformation]; void *
0x18004ced7  mov     qword ptr [rsp+2C0h+ObjectAttributes.Attributes], 0
0x18004cee0  mov     r8d, 212h; Size
0x18004cee6  mov     [rsp+2C0h+ProcessHandle], 0
0x18004ceef  call    memset_0
0x18004cef4  xorps   xmm0, xmm0
0x18004cef7  mov     [rsp+2C0h+ObjectAttributes.RootDirectory], 0
0x18004cf00  lea     r9, [rsp+2C0h+ClientId]; ClientId
0x18004cf05  mov     [rsp+2C0h+ObjectAttributes.ObjectName], 0
0x18004cf0e  lea     r8, [rsp+2C0h+ObjectAttributes]; ObjectAttributes
0x18004cf13  mov     [rsp+2C0h+ClientId.UniqueProcess], rbx
0x18004cf18  mov     edx, 400h; DesiredAccess
0x18004cf1d  mov     [rsp+2C0h+ClientId.UniqueThread], 0
0x18004cf26  lea     rcx, [rsp+2C0h+ProcessHandle]; ProcessHandle
0x18004cf2b  movups  xmmword ptr [rsp+2C0h+DestinationString.Length], xmm0
0x18004cf30  movdqu  xmmword ptr [rsp+2C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004cf36  call    cs:__imp_NtOpenProcess
0x18004cf3c  mov     ebx, eax
0x18004cf3e  test    eax, eax
0x18004cf40  jns     short loc_18004CF80
0x18004cf42  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cf49  lea     rax, WPP_GLOBAL_Control
0x18004cf50  cmp     rcx, rax
0x18004cf53  jz      loc_18004D012
0x18004cf59  test    byte ptr [rcx+1Ch], 1
0x18004cf5d  jz      loc_18004D012
0x18004cf63  mov     rcx, [rcx+10h]
0x18004cf67  lea     r8, WPP_ced0880886a53ec11230ac267b1eff8e_Traceguids
0x18004cf6e  mov     edx, 15h
0x18004cf73  mov     r9d, ebx
0x18004cf76  call    WPP_SF_d
0x18004cf7b  jmp     loc_18004D012
0x18004cf80  mov     rcx, [rsp+2C0h+ProcessHandle]; ProcessHandle
0x18004cf85  lea     r8, [rbp+1C0h+ProcessInformation]; ProcessInformation
0x18004cf89  mov     r9d, 210h; ProcessInformationLength
0x18004cf8f  mov     [rsp+2C0h+ReturnLength], 0; ReturnLength
0x18004cf98  mov     edx, 1Bh; ProcessInformationClass
0x18004cf9d  call    cs:__imp_NtQueryInformationProcess
0x18004cfa3  mov     ebx, eax
0x18004cfa5  test    eax, eax
0x18004cfa7  js      short loc_18004D012
0x18004cfa9  movzx   ecx, [rbp+1C0h+var_22E]
0x18004cfad  movzx   eax, [rbp+1C0h+ProcessInformation]
0x18004cfb1  mov     r8d, ecx; Size
0x18004cfb4  mov     rdx, [rbp+1C0h+Src]; Src
0x18004cfb8  mov     [rsp+2C0h+DestinationString.Length], ax
0x18004cfbd  mov     eax, [rbp+1C0h+var_22C]
0x18004cfc0  mov     [rsp+2C0h+DestinationString.MaximumLength], cx
0x18004cfc5  lea     rcx, [rbp+1C0h+ProcessInformation]; void *
0x18004cfc9  mov     dword ptr [rsp+2C0h+DestinationString+4], eax
0x18004cfcd  mov     [rsp+2C0h+DestinationString.Buffer], rdx
0x18004cfd2  call    memmove_0
0x18004cfd7  mov     edx, 5Ch ; '\'; Ch
0x18004cfdc  lea     rcx, [rbp+1C0h+ProcessInformation]; Str
0x18004cfe0  call    cs:__imp_wcsrchr
0x18004cfe6  test    rax, rax
0x18004cfe9  jz      short loc_18004CFF1
0x18004cfeb  add     rax, 2
0x18004cfef  jmp     short loc_18004CFF5
0x18004cff1  lea     rax, [rbp+1C0h+ProcessInformation]
0x18004cff5  mov     rdx, rax; SourceString
0x18004cff8  lea     rcx, [rsp+2C0h+DestinationString]; DestinationString
0x18004cffd  call    cs:__imp_RtlInitUnicodeString
0x18004d003  lea     rdx, [rsp+2C0h+DestinationString]
0x18004d008  mov     rcx, rdi
0x18004d00b  call    NtLmDuplicateUnicodeString
0x18004d010  mov     ebx, eax
0x18004d012  mov     rcx, [rsp+2C0h+ProcessHandle]; Handle
0x18004d017  test    rcx, rcx
0x18004d01a  jz      short loc_18004D022
0x18004d01c  call    cs:__imp_NtClose
0x18004d022  mov     eax, ebx
0x18004d024  mov     rcx, [rbp+1C0h+var_10]
0x18004d02b  xor     rcx, rsp; StackCookie
0x18004d02e  call    __security_check_cookie
0x18004d033  lea     r11, [rsp+2C0h+var_s0]
0x18004d03b  mov     rbx, [r11+20h]
0x18004d03f  mov     rdi, [r11+28h]
0x18004d043  mov     rsp, r11
0x18004d046  pop     rbp
0x18004d047  retn
```
