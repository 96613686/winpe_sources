# CreateJobObjectW

- ea: `0x18003de80`
- end: `0x18003df3a`
- name: `CreateJobObjectW`
- size: `186`
- prototype: `HANDLE __stdcall(LPSECURITY_ATTRIBUTES lpJobAttributes, LPCWSTR lpName)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800704b0`

## callees

- `0x18000ccf0`
- `0x18003de80`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x18003def6`
- `ntdll!RtlSetLastWin32Error` at `0x18003def6`
- `ntdll!NtCreateJobObject` at `0x18003dedd`
- `ntdll!NtCreateJobObject` at `0x18003dedd`
- `ntdll!RtlInitUnicodeString` at `0x18003df21`
- `ntdll!RtlInitUnicodeString` at `0x18003df21`
- `KERNELBASE!BaseFormatObjectAttributes` at `0x18003dec0`
- `KERNELBASE!BaseFormatObjectAttributes` at `0x18003dec0`

## pseudocode

```c
HANDLE __stdcall CreateJobObjectW(LPSECURITY_ATTRIBUTES lpJobAttributes, LPCWSTR lpName)
{
  struct _UNICODE_STRING *p_DestinationString; // r8
  NTSTATUS v4; // eax
  ULONG v5; // ecx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  _OWORD v8[3]; // [rsp+30h] [rbp-30h] BYREF
  POBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp+18h] BYREF
  void *JobHandle; // [rsp+80h] [rbp+20h] BYREF

  ObjectAttributes = 0;
  JobHandle = 0;
  memset(v8, 0, 44);
  DestinationString = 0;
  if ( lpName )
  {
    RtlInitUnicodeString(&DestinationString, lpName);
    p_DestinationString = &DestinationString;
  }
  else
  {
    p_DestinationString = 0;
  }
  v4 = ((__int64 (__fastcall *)(_OWORD *, LPSECURITY_ATTRIBUTES, struct _UNICODE_STRING *, POBJECT_ATTRIBUTES *, _QWORD, PWSTR))BaseFormatObjectAttributes)(
         v8,
         lpJobAttributes,
         p_DestinationString,
         &ObjectAttributes,
         *(_QWORD *)&DestinationString.Length,
         DestinationString.Buffer);
  if ( v4 < 0 || (v4 = NtCreateJobObject(&JobHandle, 0x1F003Fu, ObjectAttributes), v4 < 0) )
  {
    BaseSetLastNTError((unsigned int)v4);
    return 0;
  }
  else
  {
    if ( v4 == 0x40000000 )
      v5 = 183;
    else
      v5 = 0;
    RtlSetLastWin32Error(v5);
    return JobHandle;
  }
}

```

## disassembly

```asm
0x18003de80  mov     [rsp-8+arg_0], rbx
0x18003de85  push    rbp
0x18003de86  mov     rbp, rsp
0x18003de89  sub     rsp, 60h
0x18003de8d  xorps   xmm0, xmm0
0x18003de90  xor     eax, eax
0x18003de92  mov     [rbp+ObjectAttributes], rax
0x18003de96  mov     rbx, rcx
0x18003de99  mov     [rbp+JobHandle], rax
0x18003de9d  movups  xmmword ptr [rbp+var_20], xmm0
0x18003dea1  movups  xmmword ptr [rbp+var_20+0Ch], xmm0
0x18003dea5  movups  [rbp+var_30], xmm0
0x18003dea9  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18003dead  test    rdx, rdx
0x18003deb0  jnz     short loc_18003DF1D
0x18003deb2  xor     r8d, r8d
0x18003deb5  lea     r9, [rbp+ObjectAttributes]
0x18003deb9  mov     rdx, rbx
0x18003debc  lea     rcx, [rbp+var_30]
0x18003dec0  call    cs:__imp_BaseFormatObjectAttributes
0x18003dec7  nop     dword ptr [rax+rax+00h]
0x18003decc  test    eax, eax
0x18003dece  js      short loc_18003DF12
0x18003ded0  mov     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18003ded4  lea     rcx, [rbp+JobHandle]; JobHandle
0x18003ded8  mov     edx, 1F003Fh; DesiredAccess
0x18003dedd  call    cs:__imp_NtCreateJobObject
0x18003dee4  nop     dword ptr [rax+rax+00h]
0x18003dee9  test    eax, eax
0x18003deeb  js      short loc_18003DF12
0x18003deed  cmp     eax, 40000000h
0x18003def2  jz      short loc_18003DF33
0x18003def4  xor     ecx, ecx; LastError
0x18003def6  call    cs:__imp_RtlSetLastWin32Error
0x18003defd  nop     dword ptr [rax+rax+00h]
0x18003df02  mov     rax, [rbp+JobHandle]
0x18003df06  mov     rbx, [rsp+60h+arg_0]
0x18003df0b  add     rsp, 60h
0x18003df0f  pop     rbp
0x18003df10  retn
0x18003df12  mov     ecx, eax
0x18003df14  call    BaseSetLastNTError
0x18003df19  xor     eax, eax
0x18003df1b  jmp     short loc_18003DF06
0x18003df1d  lea     rcx, [rbp+DestinationString]; DestinationString
0x18003df21  call    cs:__imp_RtlInitUnicodeString
0x18003df28  nop     dword ptr [rax+rax+00h]
0x18003df2d  lea     r8, [rbp+DestinationString]
0x18003df31  jmp     short loc_18003DEB5
0x18003df33  mov     ecx, 0B7h
0x18003df38  jmp     short loc_18003DEF6
```
