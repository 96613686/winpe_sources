# GetCompatFlags

- ea: `0x18002ff34`
- end: `0x1800301aa`
- name: `GetCompatFlags`
- size: `630`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002f878`

## callees

- `0x18002ff34`
- `0x18007a7dd`
- `0x18007a840`

## import_xrefs

- `ntdll!wcsrchr` at `0x18002ff96`
- `ntdll!wcsrchr` at `0x18002ffc4`
- `ntdll!wcsrchr` at `0x18002ff96`
- `ntdll!wcsrchr` at `0x18002ffc4`
- `ntdll!NtQueryValueKey` at `0x1800300c4`
- `ntdll!NtQueryValueKey` at `0x1800300c4`
- `ntdll!NtOpenKey` at `0x180030083`
- `ntdll!NtOpenKey` at `0x180030083`
- `ntdll!NtClose` at `0x1800300dc`
- `ntdll!NtClose` at `0x1800300dc`
- `ntdll!wcslen` at `0x18002ffe5`
- `ntdll!wcslen` at `0x18002ffe5`
- `ntdll!wcscpy_s` at `0x18002ffb5`
- `ntdll!wcscpy_s` at `0x18003017d`
- `ntdll!wcscpy_s` at `0x18002ffb5`
- `ntdll!wcscpy_s` at `0x18003017d`
- `ntdll!wcscat_s` at `0x180030191`
- `ntdll!wcscat_s` at `0x180030191`
- `ntdll!RtlInitUnicodeString` at `0x180030099`
- `ntdll!RtlInitUnicodeString` at `0x18003019f`
- `ntdll!RtlInitUnicodeString` at `0x180030099`
- `ntdll!RtlInitUnicodeString` at `0x18003019f`
- `ntdll!RtlFreeHeap` at `0x180030109`
- `ntdll!RtlFreeHeap` at `0x180030136`
- `ntdll!RtlFreeHeap` at `0x180030109`
- `ntdll!RtlFreeHeap` at `0x180030136`
- `ntdll!RtlAllocateHeap` at `0x180030008`
- `ntdll!RtlAllocateHeap` at `0x18003002f`
- `ntdll!RtlAllocateHeap` at `0x180030008`
- `ntdll!RtlAllocateHeap` at `0x18003002f`

## string_xrefs

- `0x180030170`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\Terminal Server\Compatibility\Applications\`

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
0x18002ff34  push    rbp
0x18002ff36  push    rbx
0x18002ff37  push    rsi
0x18002ff38  push    rdi
0x18002ff39  lea     rbp, [rsp-1A8h]
0x18002ff41  sub     rsp, 2A8h
0x18002ff48  mov     rax, cs:__security_cookie
0x18002ff4f  xor     rax, rsp
0x18002ff52  mov     [rbp+1C0h+var_30], rax
0x18002ff59  xor     eax, eax
0x18002ff5b  xorps   xmm0, xmm0
0x18002ff5e  movups  xmmword ptr [rsp+2C0h+ObjectAttributes.ObjectName], xmm0
0x18002ff63  mov     qword ptr [rsp+2C0h+DestinationString.Length], rax
0x18002ff68  xor     esi, esi
0x18002ff6a  movups  xmmword ptr [rsp+2C0h+ObjectAttributes+1Ch], xmm0
0x18002ff6f  mov     [rsp+2C0h+KeyHandle], rax
0x18002ff74  movups  xmmword ptr [rsp+2C0h+ObjectAttributes.Length], xmm0
0x18002ff79  mov     [rsp+2C0h+var_290], eax
0x18002ff7d  lea     edx, [rsi+5Ch]; Ch
0x18002ff80  mov     [rsp+2C0h+DestinationString.Buffer], rax
0x18002ff85  mov     rax, gs:60h
0x18002ff8e  mov     rbx, [rax+20h]
0x18002ff92  mov     rcx, [rbx+68h]; Str
0x18002ff96  call    cs:__imp_wcsrchr
0x18002ff9c  test    rax, rax
0x18002ff9f  jz      loc_180030159
0x18002ffa5  add     rax, 2
0x18002ffa9  mov     r8, rax; Source
0x18002ffac  lea     rcx, [rbp+1C0h+Destination]; Destination
0x18002ffb0  mov     edx, 105h; SizeInWords
0x18002ffb5  call    cs:__imp_wcscpy_s
0x18002ffbb  mov     edx, 2Eh ; '.'; Ch
0x18002ffc0  lea     rcx, [rbp+1C0h+Destination]; Str
0x18002ffc4  call    cs:__imp_wcsrchr
0x18002ffca  mov     rcx, rax
0x18002ffcd  test    rax, rax
0x18002ffd0  jnz     loc_180030162
0x18002ffd6  xor     eax, eax
0x18002ffd8  mov     [rsp+2C0h+DestinationString.Buffer], rsi
0x18002ffdd  lea     rcx, [rbp+1C0h+Destination]; String
0x18002ffe1  mov     dword ptr [rsp+2C0h+DestinationString.Length], eax
0x18002ffe5  call    cs:__imp_wcslen
0x18002ffeb  xor     edx, edx; Flags
0x18002ffed  lea     eax, ds:0D8h[rax*2]
0x18002fff4  mov     [rsp+2C0h+var_290], eax
0x18002fff8  mov     rcx, gs:60h
0x180030001  mov     r8d, eax; Size
0x180030004  mov     rcx, [rcx+30h]; HeapHandle
0x180030008  call    cs:__imp_RtlAllocateHeap
0x18003000e  mov     rdi, rax
0x180030011  test    rax, rax
0x180030014  jnz     loc_18003016C
0x18003001a  mov     rcx, gs:60h
0x180030023  xor     edx, edx; Flags
0x180030025  mov     r8d, 224h; Size
0x18003002b  mov     rcx, [rcx+30h]; HeapHandle
0x18003002f  call    cs:__imp_RtlAllocateHeap
0x180030035  mov     rbx, rax
0x180030038  cmp     [rsp+2C0h+DestinationString.Buffer], rsi
0x18003003d  jz      loc_1800300E2
0x180030043  test    rax, rax
0x180030046  jz      loc_1800300E2
0x18003004c  lea     rax, [rsp+2C0h+DestinationString]
0x180030051  mov     [rsp+2C0h+ObjectAttributes.Length], 30h ; '0'
0x180030059  xorps   xmm0, xmm0
0x18003005c  mov     [rsp+2C0h+ObjectAttributes.ObjectName], rax
0x180030061  lea     r8, [rsp+2C0h+ObjectAttributes]; ObjectAttributes
0x180030066  mov     [rsp+2C0h+ObjectAttributes.RootDirectory], rsi
0x18003006b  mov     edx, 20019h; DesiredAccess
0x180030070  mov     [rsp+2C0h+ObjectAttributes.Attributes], 40h ; '@'
0x180030078  lea     rcx, [rsp+2C0h+KeyHandle]; KeyHandle
0x18003007d  movdqu  xmmword ptr [rsp+2C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180030083  call    cs:__imp_NtOpenKey
0x180030089  test    eax, eax
0x18003008b  js      short loc_1800300E2
0x18003008d  lea     rdx, aFlags; "Flags"
0x180030094  lea     rcx, [rsp+2C0h+DestinationString]; DestinationString
0x180030099  call    cs:__imp_RtlInitUnicodeString
0x18003009f  mov     rcx, [rsp+2C0h+KeyHandle]; KeyHandle
0x1800300a4  lea     rax, [rsp+2C0h+var_290]
0x1800300a9  mov     [rsp+2C0h+ResultLength], rax; ResultLength
0x1800300ae  lea     rdx, [rsp+2C0h+DestinationString]; ValueName
0x1800300b3  mov     r9, rbx; KeyValueInformation
0x1800300b6  mov     [rsp+2C0h+Length], 224h; Length
0x1800300be  mov     r8d, 2; KeyValueInformationClass
0x1800300c4  call    cs:__imp_NtQueryValueKey
0x1800300ca  test    eax, eax
0x1800300cc  js      short loc_1800300D7
0x1800300ce  cmp     dword ptr [rbx+4], 4
0x1800300d2  jnz     short loc_1800300D7
0x1800300d4  mov     esi, [rbx+0Ch]
0x1800300d7  mov     rcx, [rsp+2C0h+KeyHandle]; Handle
0x1800300dc  call    cs:__imp_NtClose
0x1800300e2  test    rdi, rdi
0x1800300e5  jz      short loc_18003010F
0x1800300e7  movzx   r8d, [rsp+2C0h+DestinationString.MaximumLength]; Size
0x1800300ed  xor     edx, edx; Val
0x1800300ef  mov     rcx, rdi; void *
0x1800300f2  call    memset_0
0x1800300f7  mov     rcx, gs:60h
0x180030100  mov     r8, rdi; P
0x180030103  xor     edx, edx; Flags
0x180030105  mov     rcx, [rcx+30h]; HeapHandle
0x180030109  call    cs:__imp_RtlFreeHeap
0x18003010f  test    rbx, rbx
0x180030112  jz      short loc_18003013C
0x180030114  xor     edx, edx; Val
0x180030116  mov     r8d, 224h; Size
0x18003011c  mov     rcx, rbx; void *
0x18003011f  call    memset_0
0x180030124  mov     rcx, gs:60h
0x18003012d  mov     r8, rbx; P
0x180030130  xor     edx, edx; Flags
0x180030132  mov     rcx, [rcx+30h]; HeapHandle
0x180030136  call    cs:__imp_RtlFreeHeap
0x18003013c  mov     eax, esi
0x18003013e  mov     rcx, [rbp+1C0h+var_30]
0x180030145  xor     rcx, rsp; StackCookie
0x180030148  call    __security_check_cookie
0x18003014d  add     rsp, 2A8h
0x180030154  pop     rdi
0x180030155  pop     rsi
0x180030156  pop     rbx
0x180030157  pop     rbp
0x180030158  retn
0x180030159  mov     rax, [rbx+68h]
0x18003015d  jmp     loc_18002FFA9
0x180030162  xor     eax, eax
0x180030164  mov     [rcx], ax
0x180030167  jmp     loc_18002FFD6
0x18003016c  mov     edx, [rsp+2C0h+var_290]
0x180030170  lea     r8, aRegistryMachin_22; "\\Registry\\Machine\\Software\\Microsof"...
0x180030177  shr     rdx, 1; SizeInWords
0x18003017a  mov     rcx, rdi; Destination
0x18003017d  call    cs:__imp_wcscpy_s
0x180030183  mov     edx, [rsp+2C0h+var_290]
0x180030187  lea     r8, [rbp+1C0h+Destination]; Source
0x18003018b  shr     rdx, 1; SizeInWords
0x18003018e  mov     rcx, rdi; Destination
0x180030191  call    cs:__imp_wcscat_s
0x180030197  mov     rdx, rdi; SourceString
0x18003019a  lea     rcx, [rsp+2C0h+DestinationString]; DestinationString
0x18003019f  call    cs:__imp_RtlInitUnicodeString
0x1800301a5  jmp     loc_18003001A
```
