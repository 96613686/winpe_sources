# MupiProviderIsInstalled

- ea: `0x140003cb8`
- end: `0x140003e3c`
- name: `MupiProviderIsInstalled`
- size: `388`
- prototype: `__int64 __fastcall(PCUNICODE_STRING Source)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140012bd8`

## callees

- `0x140003cb8`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140003d8a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140003d8a`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140003da1`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140003da1`
- `ntoskrnl!ExAllocatePool2` at `0x140003d05`
- `ntoskrnl!ExAllocatePool2` at `0x140003d05`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003e18`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003e18`
- `ntoskrnl!ZwClose` at `0x140003df9`
- `ntoskrnl!ZwClose` at `0x140003df9`
- `ntoskrnl!ZwOpenKey` at `0x140003de0`
- `ntoskrnl!ZwOpenKey` at `0x140003de0`

## string_xrefs

- `0x140003d23`: `\Registry\Machine\System\CurrentControlSet\Services\`

## pseudocode

```c
__int64 __fastcall MupiProviderIsInstalled(PCUNICODE_STRING Source, _BYTE *a2)
{
  unsigned int v4; // r14d
  __int64 Pool2; // rax
  void *v6; // rbx
  NTSTATUS v8; // eax
  unsigned int v9; // edi
  void *v10; // rcx
  struct _UNICODE_STRING Destination; // [rsp+20h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+80h] [rbp+20h] BYREF

  v4 = Source->Length + 140;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  Destination = 0;
  Pool2 = ExAllocatePool2(258, v4, 544240973);
  v6 = (void *)Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  Destination.Buffer = (PWSTR)Pool2;
  Destination.Length = 104;
  Destination.MaximumLength = v4;
  *(_OWORD *)Pool2 = *(_OWORD *)L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\";
  *(_OWORD *)(Pool2 + 16) = *(_OWORD *)L"y\\Machine\\System\\CurrentControlSet\\Services\\";
  *(_OWORD *)(Pool2 + 32) = *(_OWORD *)L"e\\System\\CurrentControlSet\\Services\\";
  *(_OWORD *)(Pool2 + 48) = *(_OWORD *)L"\\CurrentControlSet\\Services\\";
  *(_OWORD *)(Pool2 + 64) = *(_OWORD *)L"ControlSet\\Services\\";
  *(_OWORD *)(Pool2 + 80) = *(_OWORD *)L"et\\Services\\";
  *(_QWORD *)(Pool2 + 96) = *(_QWORD *)L"ces\\";
  RtlAppendUnicodeStringToString(&Destination, Source);
  RtlAppendUnicodeToString(&Destination, L"\\NetworkProvider");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &Destination;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v8 = ZwOpenKey(&KeyHandle, 1u, &ObjectAttributes);
  v9 = v8;
  if ( v8 < 0 )
  {
    if ( v8 == -1073741772 )
    {
      *a2 = 0;
      v9 = 0;
    }
  }
  else
  {
    v10 = KeyHandle;
    *a2 = 1;
    ZwClose(v10);
  }
  ExFreePoolWithTag(v6, 0);
  return v9;
}

```

## disassembly

```asm
0x140003cb8  mov     [rsp-18h+arg_8], rbx
0x140003cbd  mov     [rsp-18h+arg_10], rsi
0x140003cc2  push    rbp
0x140003cc3  push    rdi
0x140003cc4  push    r14
0x140003cc6  mov     rbp, rsp
0x140003cc9  sub     rsp, 60h
0x140003ccd  movzx   r14d, word ptr [rcx]
0x140003cd1  xorps   xmm0, xmm0
0x140003cd4  mov     rsi, rdx
0x140003cd7  mov     rdi, rcx
0x140003cda  xor     eax, eax
0x140003cdc  add     r14d, 8Ch
0x140003ce3  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140003ce7  mov     edx, r14d
0x140003cea  mov     ecx, 102h
0x140003cef  mov     r8d, 2070754Dh
0x140003cf5  mov     [rbp+KeyHandle], rax
0x140003cf9  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140003cfd  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140003d01  movups  xmmword ptr [rbp+Destination.Length], xmm0
0x140003d05  call    cs:__imp_ExAllocatePool2
0x140003d0c  nop     dword ptr [rax+rax+00h]
0x140003d11  mov     rbx, rax
0x140003d14  test    rax, rax
0x140003d17  jnz     short loc_140003D23
0x140003d19  mov     eax, 0C000009Ah
0x140003d1e  jmp     loc_140003E26
0x140003d23  movaps  xmm0, xmmword ptr cs:aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x140003d2a  lea     rcx, [rbp+Destination]; Destination
0x140003d2e  mov     [rbp+Destination.Buffer], rbx
0x140003d32  mov     eax, 68h ; 'h'
0x140003d37  mov     [rbp+Destination.Length], ax
0x140003d3b  mov     rdx, rdi; Source
0x140003d3e  mov     [rbp+Destination.MaximumLength], r14w
0x140003d43  movups  xmmword ptr [rbx], xmm0
0x140003d46  movaps  xmm1, xmmword ptr cs:aRegistryMachin+10h; "y\\Machine\\System\\CurrentControlSet\\"...
0x140003d4d  movups  xmmword ptr [rbx+10h], xmm1
0x140003d51  movaps  xmm0, xmmword ptr cs:aRegistryMachin+20h; "e\\System\\CurrentControlSet\\Services"...
0x140003d58  movups  xmmword ptr [rbx+20h], xmm0
0x140003d5c  movaps  xmm1, xmmword ptr cs:aRegistryMachin+30h; "\\CurrentControlSet\\Services\\"
0x140003d63  movups  xmmword ptr [rbx+30h], xmm1
0x140003d67  movaps  xmm0, xmmword ptr cs:aRegistryMachin+40h; "ControlSet\\Services\\"
0x140003d6e  movups  xmmword ptr [rbx+40h], xmm0
0x140003d72  movaps  xmm1, xmmword ptr cs:aRegistryMachin+50h; "et\\Services\\"
0x140003d79  movups  xmmword ptr [rbx+50h], xmm1
0x140003d7d  movsd   xmm0, qword ptr cs:aRegistryMachin+60h; "ces\\"
0x140003d85  movsd   qword ptr [rbx+60h], xmm0
0x140003d8a  call    cs:__imp_RtlAppendUnicodeStringToString
0x140003d91  nop     dword ptr [rax+rax+00h]
0x140003d96  lea     rdx, Source; "\\NetworkProvider"
0x140003d9d  lea     rcx, [rbp+Destination]; Destination
0x140003da1  call    cs:__imp_RtlAppendUnicodeToString
0x140003da8  nop     dword ptr [rax+rax+00h]
0x140003dad  lea     rax, [rbp+Destination]
0x140003db1  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140003db8  xorps   xmm0, xmm0
0x140003dbb  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140003dbf  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140003dc3  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140003dcb  mov     edx, 1; DesiredAccess
0x140003dd0  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140003dd7  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x140003ddb  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140003de0  call    cs:__imp_ZwOpenKey
0x140003de7  nop     dword ptr [rax+rax+00h]
0x140003dec  mov     edi, eax
0x140003dee  test    eax, eax
0x140003df0  js      short loc_140003E07
0x140003df2  mov     rcx, [rbp+KeyHandle]; Handle
0x140003df6  mov     byte ptr [rsi], 1
0x140003df9  call    cs:__imp_ZwClose
0x140003e00  nop     dword ptr [rax+rax+00h]
0x140003e05  jmp     short loc_140003E13
0x140003e07  cmp     eax, 0C0000034h
0x140003e0c  jnz     short loc_140003E13
0x140003e0e  mov     byte ptr [rsi], 0
0x140003e11  xor     edi, edi
0x140003e13  xor     edx, edx; Tag
0x140003e15  mov     rcx, rbx; P
0x140003e18  call    cs:__imp_ExFreePoolWithTag
0x140003e1f  nop     dword ptr [rax+rax+00h]
0x140003e24  mov     eax, edi
0x140003e26  lea     r11, [rsp+60h+var_s0]
0x140003e2b  mov     rbx, [r11+28h]
0x140003e2f  mov     rsi, [r11+30h]
0x140003e33  mov     rsp, r11
0x140003e36  pop     r14
0x140003e38  pop     rdi
0x140003e39  pop     rbp
0x140003e3a  retn
```
