# IsRegTSAppCompatEnabled

- ea: `0x18002fd88`
- end: `0x18002ff2c`
- name: `IsRegTSAppCompatEnabled`
- size: `420`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002f878`

## callees

- `0x18002fd88`
- `0x18007a7dd`

## import_xrefs

- `ntdll!NtQueryValueKey` at `0x18002fe6e`
- `ntdll!NtQueryValueKey` at `0x18002feac`
- `ntdll!NtQueryValueKey` at `0x18002fe6e`
- `ntdll!NtQueryValueKey` at `0x18002feac`
- `ntdll!NtOpenKey` at `0x18002fe32`
- `ntdll!NtOpenKey` at `0x18002fe32`
- `ntdll!NtClose` at `0x18002fec5`
- `ntdll!NtClose` at `0x18002fec5`
- `ntdll!RtlInitUnicodeString` at `0x18002fdc7`
- `ntdll!RtlInitUnicodeString` at `0x18002fe4b`
- `ntdll!RtlInitUnicodeString` at `0x18002fe87`
- `ntdll!RtlInitUnicodeString` at `0x18002fdc7`
- `ntdll!RtlInitUnicodeString` at `0x18002fe4b`
- `ntdll!RtlInitUnicodeString` at `0x18002fe87`
- `ntdll!RtlFreeHeap` at `0x18002feea`
- `ntdll!RtlFreeHeap` at `0x18002feea`
- `ntdll!RtlAllocateHeap` at `0x18002fde5`
- `ntdll!RtlAllocateHeap` at `0x18002fde5`

## string_xrefs

- `0x18002fda0`: `\Registry\Machine\System\CurrentControlSet\Control\Terminal Server`
- `0x18002fe40`: `TSAppCompat`

## pseudocode

```c
_BOOL8 __fastcall IsRegTSAppCompatEnabled(_BYTE *a1)
{
  _DWORD *Heap; // rax
  BOOL v3; // edi
  _DWORD *v4; // rbx
  char v5; // al
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  ULONG ResultLength; // [rsp+98h] [rbp+28h] BYREF
  void *KeyHandle; // [rsp+A0h] [rbp+30h] BYREF

  KeyHandle = 0;
  ResultLength = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Terminal Server");
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 0x224u);
  v3 = 0;
  v4 = Heap;
  if ( !DestinationString.Buffer )
  {
    if ( !Heap )
      return v3;
    goto LABEL_9;
  }
  if ( Heap )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"TSAppCompat");
      if ( NtQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, v4, 0x224u, &ResultLength) >= 0
        && v4[1] == 4 )
      {
        v3 = v4[3] != 0;
      }
      RtlInitUnicodeString(&DestinationString, L"TSUserEnabled");
      if ( NtQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, v4, 0x224u, &ResultLength) >= 0
        && v4[1] == 4 )
      {
        v5 = *((_BYTE *)v4 + 12);
      }
      else
      {
        v5 = 0;
      }
      *a1 = v5;
      NtClose(KeyHandle);
    }
LABEL_9:
    memset_0(v4, 0, 0x224u);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  }
  return v3;
}

```

## disassembly

```asm
0x18002fd88  mov     [rsp-18h+arg_0], rbx
0x18002fd8d  mov     [rsp-18h+arg_18], rsi
0x18002fd92  push    rbp
0x18002fd93  push    rdi
0x18002fd94  push    r15
0x18002fd96  mov     rbp, rsp
0x18002fd99  sub     rsp, 70h
0x18002fd9d  xorps   xmm0, xmm0
0x18002fda0  lea     rdx, aRegistryMachin_11; "\\Registry\\Machine\\System\\CurrentCon"...
0x18002fda7  xor     eax, eax
0x18002fda9  mov     rsi, rcx
0x18002fdac  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18002fdb0  lea     rcx, [rbp+DestinationString]; DestinationString
0x18002fdb4  mov     [rbp+KeyHandle], rax
0x18002fdb8  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18002fdbc  mov     [rbp+arg_8], eax
0x18002fdbf  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18002fdc3  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18002fdc7  call    cs:__imp_RtlInitUnicodeString
0x18002fdcd  mov     rcx, gs:60h
0x18002fdd6  mov     r15d, 224h
0x18002fddc  mov     r8d, r15d; Size
0x18002fddf  xor     edx, edx; Flags
0x18002fde1  mov     rcx, [rcx+30h]; HeapHandle
0x18002fde5  call    cs:__imp_RtlAllocateHeap
0x18002fdeb  xor     edi, edi
0x18002fded  mov     rbx, rax
0x18002fdf0  cmp     [rbp+DestinationString.Buffer], rdi
0x18002fdf4  jz      loc_18002FF0B
0x18002fdfa  test    rax, rax
0x18002fdfd  jz      loc_18002FEF0
0x18002fe03  lea     rax, [rbp+DestinationString]
0x18002fe07  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18002fe0e  xorps   xmm0, xmm0
0x18002fe11  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18002fe15  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18002fe19  mov     [rbp+ObjectAttributes.RootDirectory], rdi
0x18002fe1d  mov     edx, 20019h; DesiredAccess
0x18002fe22  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18002fe29  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18002fe2d  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18002fe32  call    cs:__imp_NtOpenKey
0x18002fe38  test    eax, eax
0x18002fe3a  js      loc_18002FECB
0x18002fe40  lea     rdx, aTsappcompat; "TSAppCompat"
0x18002fe47  lea     rcx, [rbp+DestinationString]; DestinationString
0x18002fe4b  call    cs:__imp_RtlInitUnicodeString
0x18002fe51  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18002fe55  lea     rax, [rbp+arg_8]
0x18002fe59  mov     [rsp+70h+ResultLength], rax; ResultLength
0x18002fe5e  lea     r8d, [rdi+2]; KeyValueInformationClass
0x18002fe62  mov     r9, rbx; KeyValueInformation
0x18002fe65  mov     [rsp+70h+Length], r15d; Length
0x18002fe6a  lea     rdx, [rbp+DestinationString]; ValueName
0x18002fe6e  call    cs:__imp_NtQueryValueKey
0x18002fe74  test    eax, eax
0x18002fe76  jns     loc_18002FF12
0x18002fe7c  lea     rdx, aTsuserenabled; "TSUserEnabled"
0x18002fe83  lea     rcx, [rbp+DestinationString]; DestinationString
0x18002fe87  call    cs:__imp_RtlInitUnicodeString
0x18002fe8d  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18002fe91  lea     rax, [rbp+arg_8]
0x18002fe95  mov     [rsp+70h+ResultLength], rax; ResultLength
0x18002fe9a  lea     rdx, [rbp+DestinationString]; ValueName
0x18002fe9e  mov     r9, rbx; KeyValueInformation
0x18002fea1  mov     [rsp+70h+Length], r15d; Length
0x18002fea6  mov     r8d, 2; KeyValueInformationClass
0x18002feac  call    cs:__imp_NtQueryValueKey
0x18002feb2  test    eax, eax
0x18002feb4  js      short loc_18002FF07
0x18002feb6  cmp     dword ptr [rbx+4], 4
0x18002feba  jnz     short loc_18002FF07
0x18002febc  mov     al, [rbx+0Ch]
0x18002febf  mov     [rsi], al
0x18002fec1  mov     rcx, [rbp+KeyHandle]; Handle
0x18002fec5  call    cs:__imp_NtClose
0x18002fecb  mov     r8, r15; Size
0x18002fece  xor     edx, edx; Val
0x18002fed0  mov     rcx, rbx; void *
0x18002fed3  call    memset_0
0x18002fed8  mov     rcx, gs:60h
0x18002fee1  mov     r8, rbx; P
0x18002fee4  xor     edx, edx; Flags
0x18002fee6  mov     rcx, [rcx+30h]; HeapHandle
0x18002feea  call    cs:__imp_RtlFreeHeap
0x18002fef0  lea     r11, [rsp+70h+var_s0]
0x18002fef5  mov     eax, edi
0x18002fef7  mov     rbx, [r11+20h]
0x18002fefb  mov     rsi, [r11+38h]
0x18002feff  mov     rsp, r11
0x18002ff02  pop     r15
0x18002ff04  pop     rdi
0x18002ff05  pop     rbp
0x18002ff06  retn
0x18002ff07  xor     al, al
0x18002ff09  jmp     short loc_18002FEBF
0x18002ff0b  test    rbx, rbx
0x18002ff0e  jnz     short loc_18002FECB
0x18002ff10  jmp     short loc_18002FEF0
0x18002ff12  cmp     dword ptr [rbx+4], 4
0x18002ff16  jnz     loc_18002FE7C
0x18002ff1c  cmp     [rbx+0Ch], edi
0x18002ff1f  mov     eax, 1
0x18002ff24  cmovnz  edi, eax
0x18002ff27  jmp     loc_18002FE7C
```
