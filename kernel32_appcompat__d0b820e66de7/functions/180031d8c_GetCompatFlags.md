# GetCompatFlags

- ea: `0x180031d8c`
- end: `0x18003205d`
- name: `GetCompatFlags`
- size: `721`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800315f8`

## callees

- `0x180031d8c`
- `0x18008275d`
- `0x1800827c0`

## import_xrefs

- `ntdll!wcsrchr` at `0x180031dee`
- `ntdll!wcsrchr` at `0x180031e28`
- `ntdll!wcsrchr` at `0x180031dee`
- `ntdll!wcsrchr` at `0x180031e28`
- `ntdll!NtQueryValueKey` at `0x180031f4c`
- `ntdll!NtQueryValueKey` at `0x180031f4c`
- `ntdll!NtOpenKey` at `0x180031eff`
- `ntdll!NtOpenKey` at `0x180031eff`
- `ntdll!NtClose` at `0x180031f6a`
- `ntdll!NtClose` at `0x180031f6a`
- `ntdll!wcslen` at `0x180031e4f`
- `ntdll!wcslen` at `0x180031e4f`
- `ntdll!wcscpy_s` at `0x180031e13`
- `ntdll!wcscpy_s` at `0x18003201e`
- `ntdll!wcscpy_s` at `0x180031e13`
- `ntdll!wcscpy_s` at `0x18003201e`
- `ntdll!wcscat_s` at `0x180032038`
- `ntdll!wcscat_s` at `0x180032038`
- `ntdll!RtlInitUnicodeString` at `0x180031f1b`
- `ntdll!RtlInitUnicodeString` at `0x18003204c`
- `ntdll!RtlInitUnicodeString` at `0x180031f1b`
- `ntdll!RtlInitUnicodeString` at `0x18003204c`
- `ntdll!RtlFreeHeap` at `0x180031f9d`
- `ntdll!RtlFreeHeap` at `0x180031fd0`
- `ntdll!RtlFreeHeap` at `0x180031f9d`
- `ntdll!RtlFreeHeap` at `0x180031fd0`
- `ntdll!RtlAllocateHeap` at `0x180031e78`
- `ntdll!RtlAllocateHeap` at `0x180031ea5`
- `ntdll!RtlAllocateHeap` at `0x180031e78`
- `ntdll!RtlAllocateHeap` at `0x180031ea5`

## string_xrefs

- `0x180032011`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\Terminal Server\Compatibility\Applications\`

## pseudocode

```c
__int64 GetCompatFlags()
{
  unsigned int v0; // esi
  struct _RTL_USER_PROCESS_PARAMETERS *ProcessParameters; // rbx
  wchar_t *v2; // rax
  const wchar_t *Buffer; // rax
  wchar_t *v4; // rcx
  wchar_t *Heap; // rax
  wchar_t *v6; // rdi
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-C8h] BYREF
  void *KeyHandle; // [rsp+48h] [rbp-B8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Destination[264]; // [rsp+80h] [rbp-80h] BYREF

  *(_QWORD *)&DestinationString.Length = 0;
  v0 = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  ResultLength = 0;
  DestinationString.Buffer = 0;
  ProcessParameters = NtCurrentPeb()->ProcessParameters;
  v2 = wcsrchr(ProcessParameters->ImagePathName.Buffer, 0x5Cu);
  if ( v2 )
    Buffer = v2 + 1;
  else
    Buffer = ProcessParameters->ImagePathName.Buffer;
  wcscpy_s(Destination, 0x105u, Buffer);
  v4 = wcsrchr(Destination, 0x2Eu);
  if ( v4 )
    *v4 = 0;
  DestinationString.Buffer = 0;
  *(_DWORD *)&DestinationString.Length = 0;
  ResultLength = 2 * wcslen(Destination) + 216;
  Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, ResultLength);
  v6 = Heap;
  if ( Heap )
  {
    wcscpy_s(
      Heap,
      (unsigned __int64)ResultLength >> 1,
      L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\Terminal Server\\Compatibility\\Applications\\");
    wcscat_s(v6, (unsigned __int64)ResultLength >> 1, Destination);
    RtlInitUnicodeString(&DestinationString, v6);
  }
  v7 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x224u);
  v8 = v7;
  if ( DestinationString.Buffer )
  {
    if ( v7 )
    {
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
      {
        RtlInitUnicodeString(&DestinationString, L"Flags");
        if ( NtQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, v8, 0x224u, &ResultLength) >= 0
          && v8[1] == 4 )
        {
          v0 = v8[3];
        }
        NtClose(KeyHandle);
      }
    }
  }
  if ( v6 )
  {
    memset_0(v6, 0, DestinationString.MaximumLength);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  }
  if ( v8 )
  {
    memset_0(v8, 0, 0x224u);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  }
  return v0;
}

```

## disassembly

```asm
0x180031d8c  push    rbp
0x180031d8e  push    rbx
0x180031d8f  push    rsi
0x180031d90  push    rdi
0x180031d91  lea     rbp, [rsp-1A8h]
0x180031d99  sub     rsp, 2A8h
0x180031da0  mov     rax, cs:__security_cookie
0x180031da7  xor     rax, rsp
0x180031daa  mov     [rbp+1C0h+var_30], rax
0x180031db1  xor     eax, eax
0x180031db3  xorps   xmm0, xmm0
0x180031db6  movups  xmmword ptr [rsp+2C0h+ObjectAttributes.ObjectName], xmm0
0x180031dbb  mov     qword ptr [rsp+2C0h+DestinationString.Length], rax
0x180031dc0  xor     esi, esi
0x180031dc2  movups  xmmword ptr [rsp+2C0h+ObjectAttributes+1Ch], xmm0
0x180031dc7  mov     [rsp+2C0h+KeyHandle], rax
0x180031dcc  movups  xmmword ptr [rsp+2C0h+ObjectAttributes.Length], xmm0
0x180031dd1  mov     [rsp+2C0h+var_290], eax
0x180031dd5  lea     edx, [rsi+5Ch]; Ch
0x180031dd8  mov     [rsp+2C0h+DestinationString.Buffer], rax
0x180031ddd  mov     rax, gs:60h
0x180031de6  mov     rbx, [rax+20h]
0x180031dea  mov     rcx, [rbx+68h]; Str
0x180031dee  call    cs:__imp_wcsrchr
0x180031df5  nop     dword ptr [rax+rax+00h]
0x180031dfa  test    rax, rax
0x180031dfd  jz      loc_180031FFA
0x180031e03  add     rax, 2
0x180031e07  mov     r8, rax; Source
0x180031e0a  lea     rcx, [rbp+1C0h+Destination]; Destination
0x180031e0e  mov     edx, 105h; SizeInWords
0x180031e13  call    cs:__imp_wcscpy_s
0x180031e1a  nop     dword ptr [rax+rax+00h]
0x180031e1f  mov     edx, 2Eh ; '.'; Ch
0x180031e24  lea     rcx, [rbp+1C0h+Destination]; Str
0x180031e28  call    cs:__imp_wcsrchr
0x180031e2f  nop     dword ptr [rax+rax+00h]
0x180031e34  mov     rcx, rax
0x180031e37  test    rax, rax
0x180031e3a  jnz     loc_180032003
0x180031e40  xor     eax, eax
0x180031e42  mov     [rsp+2C0h+DestinationString.Buffer], rsi
0x180031e47  lea     rcx, [rbp+1C0h+Destination]; String
0x180031e4b  mov     dword ptr [rsp+2C0h+DestinationString.Length], eax
0x180031e4f  call    cs:__imp_wcslen
0x180031e56  nop     dword ptr [rax+rax+00h]
0x180031e5b  xor     edx, edx; Flags
0x180031e5d  lea     eax, ds:0D8h[rax*2]
0x180031e64  mov     [rsp+2C0h+var_290], eax
0x180031e68  mov     rcx, gs:60h
0x180031e71  mov     r8d, eax; Size
0x180031e74  mov     rcx, [rcx+30h]; HeapHandle
0x180031e78  call    cs:__imp_RtlAllocateHeap
0x180031e7f  nop     dword ptr [rax+rax+00h]
0x180031e84  mov     rdi, rax
0x180031e87  test    rax, rax
0x180031e8a  jnz     loc_18003200D
0x180031e90  mov     rcx, gs:60h
0x180031e99  xor     edx, edx; Flags
0x180031e9b  mov     r8d, 224h; Size
0x180031ea1  mov     rcx, [rcx+30h]; HeapHandle
0x180031ea5  call    cs:__imp_RtlAllocateHeap
0x180031eac  nop     dword ptr [rax+rax+00h]
0x180031eb1  mov     rbx, rax
0x180031eb4  cmp     [rsp+2C0h+DestinationString.Buffer], rsi
0x180031eb9  jz      loc_180031F76
0x180031ebf  test    rax, rax
0x180031ec2  jz      loc_180031F76
0x180031ec8  lea     rax, [rsp+2C0h+DestinationString]
0x180031ecd  mov     [rsp+2C0h+ObjectAttributes.Length], 30h ; '0'
0x180031ed5  xorps   xmm0, xmm0
0x180031ed8  mov     [rsp+2C0h+ObjectAttributes.ObjectName], rax
0x180031edd  lea     r8, [rsp+2C0h+ObjectAttributes]; ObjectAttributes
0x180031ee2  mov     [rsp+2C0h+ObjectAttributes.RootDirectory], rsi
0x180031ee7  mov     edx, 20019h; DesiredAccess
0x180031eec  mov     [rsp+2C0h+ObjectAttributes.Attributes], 40h ; '@'
0x180031ef4  lea     rcx, [rsp+2C0h+KeyHandle]; KeyHandle
0x180031ef9  movdqu  xmmword ptr [rsp+2C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180031eff  call    cs:__imp_NtOpenKey
0x180031f06  nop     dword ptr [rax+rax+00h]
0x180031f0b  test    eax, eax
0x180031f0d  js      short loc_180031F76
0x180031f0f  lea     rdx, aFlags; "Flags"
0x180031f16  lea     rcx, [rsp+2C0h+DestinationString]; DestinationString
0x180031f1b  call    cs:__imp_RtlInitUnicodeString
0x180031f22  nop     dword ptr [rax+rax+00h]
0x180031f27  mov     rcx, [rsp+2C0h+KeyHandle]; KeyHandle
0x180031f2c  lea     rax, [rsp+2C0h+var_290]
0x180031f31  mov     [rsp+2C0h+ResultLength], rax; ResultLength
0x180031f36  lea     rdx, [rsp+2C0h+DestinationString]; ValueName
0x180031f3b  mov     r9, rbx; KeyValueInformation
0x180031f3e  mov     [rsp+2C0h+Length], 224h; Length
0x180031f46  mov     r8d, 2; KeyValueInformationClass
0x180031f4c  call    cs:__imp_NtQueryValueKey
0x180031f53  nop     dword ptr [rax+rax+00h]
0x180031f58  test    eax, eax
0x180031f5a  js      short loc_180031F65
0x180031f5c  cmp     dword ptr [rbx+4], 4
0x180031f60  jnz     short loc_180031F65
0x180031f62  mov     esi, [rbx+0Ch]
0x180031f65  mov     rcx, [rsp+2C0h+KeyHandle]; Handle
0x180031f6a  call    cs:__imp_NtClose
0x180031f71  nop     dword ptr [rax+rax+00h]
0x180031f76  test    rdi, rdi
0x180031f79  jz      short loc_180031FA9
0x180031f7b  movzx   r8d, [rsp+2C0h+DestinationString.MaximumLength]; Size
0x180031f81  xor     edx, edx; Val
0x180031f83  mov     rcx, rdi; void *
0x180031f86  call    memset_0
0x180031f8b  mov     rcx, gs:60h
0x180031f94  mov     r8, rdi; P
0x180031f97  xor     edx, edx; Flags
0x180031f99  mov     rcx, [rcx+30h]; HeapHandle
0x180031f9d  call    cs:__imp_RtlFreeHeap
0x180031fa4  nop     dword ptr [rax+rax+00h]
0x180031fa9  test    rbx, rbx
0x180031fac  jz      short loc_180031FDC
0x180031fae  xor     edx, edx; Val
0x180031fb0  mov     r8d, 224h; Size
0x180031fb6  mov     rcx, rbx; void *
0x180031fb9  call    memset_0
0x180031fbe  mov     rcx, gs:60h
0x180031fc7  mov     r8, rbx; P
0x180031fca  xor     edx, edx; Flags
0x180031fcc  mov     rcx, [rcx+30h]; HeapHandle
0x180031fd0  call    cs:__imp_RtlFreeHeap
0x180031fd7  nop     dword ptr [rax+rax+00h]
0x180031fdc  mov     eax, esi
0x180031fde  mov     rcx, [rbp+1C0h+var_30]
0x180031fe5  xor     rcx, rsp; StackCookie
0x180031fe8  call    __security_check_cookie
0x180031fed  add     rsp, 2A8h
0x180031ff4  pop     rdi
0x180031ff5  pop     rsi
0x180031ff6  pop     rbx
0x180031ff7  pop     rbp
0x180031ff8  retn
0x180031ffa  mov     rax, [rbx+68h]
0x180031ffe  jmp     loc_180031E07
0x180032003  xor     eax, eax
0x180032005  mov     [rcx], ax
0x180032008  jmp     loc_180031E40
0x18003200d  mov     edx, [rsp+2C0h+var_290]
0x180032011  lea     r8, aRegistryMachin_22; "\\Registry\\Machine\\Software\\Microsof"...
0x180032018  shr     rdx, 1; SizeInWords
0x18003201b  mov     rcx, rdi; Destination
0x18003201e  call    cs:__imp_wcscpy_s
0x180032025  nop     dword ptr [rax+rax+00h]
0x18003202a  mov     edx, [rsp+2C0h+var_290]
0x18003202e  lea     r8, [rbp+1C0h+Destination]; Source
0x180032032  shr     rdx, 1; SizeInWords
0x180032035  mov     rcx, rdi; Destination
0x180032038  call    cs:__imp_wcscat_s
0x18003203f  nop     dword ptr [rax+rax+00h]
0x180032044  mov     rdx, rdi; SourceString
0x180032047  lea     rcx, [rsp+2C0h+DestinationString]; DestinationString
0x18003204c  call    cs:__imp_RtlInitUnicodeString
0x180032053  nop     dword ptr [rax+rax+00h]
0x180032058  jmp     loc_180031E90
```
