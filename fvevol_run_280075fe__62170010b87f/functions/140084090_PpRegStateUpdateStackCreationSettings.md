# PpRegStateUpdateStackCreationSettings

- ea: `0x140084090`
- end: `0x140084204`
- name: `PpRegStateUpdateStackCreationSettings`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x140082fa0`

## callees

- `0x140020cdc`
- `0x140083ba8`
- `0x140084090`
- `0x1400843b8`

## import_xrefs

- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140084188`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x140084188`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400840fe`
- `ntoskrnl!SeCaptureSecurityDescriptor` at `0x1400840fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008411e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008411e`
- `ntoskrnl!ZwClose` at `0x140084174`
- `ntoskrnl!ZwClose` at `0x1400841e5`
- `ntoskrnl!ZwClose` at `0x140084174`
- `ntoskrnl!ZwClose` at `0x1400841e5`
- `ntoskrnl!ZwSetValueKey` at `0x1400841d3`
- `ntoskrnl!ZwSetValueKey` at `0x1400841d3`

## string_xrefs

- `0x140084198`: `Security`

## pseudocode

```c
__int64 __fastcall PpRegStateUpdateStackCreationSettings(int a1, __int64 a2)
{
  __int64 result; // rax
  int v4; // r8d
  __int64 v5; // r9
  __int64 *v6; // rbx
  NTSTATUS WstrKey; // ebx
  ULONG DataSize; // r10d
  void *Data; // r11
  HANDLE KeyHandle; // [rsp+40h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-18h] BYREF
  PVOID P; // [rsp+80h] [rbp+20h] BYREF
  HANDLE Handle; // [rsp+88h] [rbp+28h] BYREF

  P = 0;
  KeyHandle = 0;
  Handle = 0;
  result = PiRegStateOpenClassKey(a1, a2, 0, 0, (__int64)&Handle);
  if ( (int)result >= 0 )
  {
    v6 = PiRegStateSysAllInherittedSecurityDescriptor;
    if ( !PiRegStateDiscriptor )
    {
      LOBYTE(v5) = 1;
      if ( (int)SeCaptureSecurityDescriptor(PiRegStateSysAllInherittedSecurityDescriptor, 0, 1, v5, &P) < 0 )
      {
        PiRegStateDiscriptor = 2;
      }
      else
      {
        PiRegStateDiscriptor = 1;
        ExFreePoolWithTag(P, 0);
      }
    }
    if ( PiRegStateDiscriptor != 1 )
      v6 = 0;
    P = v6;
    WstrKey = CmRegUtilCreateWstrKey(
                (_DWORD)Handle,
                (unsigned int)L"Properties",
                v4,
                v5,
                (__int64)v6,
                0,
                (__int64)&KeyHandle);
    ZwClose(Handle);
    if ( WstrKey >= 0 )
    {
      RtlLengthSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(a2 + 8));
      DestinationString = 0;
      WstrKey = WdmlibRtlInitUnicodeStringEx(&DestinationString, L"Security");
      if ( WstrKey >= 0 )
        WstrKey = ZwSetValueKey(KeyHandle, &DestinationString, 0, 3u, Data, DataSize);
      ZwClose(KeyHandle);
    }
    return (unsigned int)WstrKey;
  }
  return result;
}

```

## disassembly

```asm
0x140084090  mov     [rsp-8+arg_0], rbx
0x140084095  mov     [rsp-8+arg_8], rdi
0x14008409a  push    rbp
0x14008409b  mov     rbp, rsp
0x14008409e  sub     rsp, 60h
0x1400840a2  lea     rax, [rbp+Handle]
0x1400840a6  mov     [rbp+P], 0
0x1400840ae  xor     r9d, r9d
0x1400840b1  mov     [rsp+60h+Data], rax
0x1400840b6  xor     r8d, r8d
0x1400840b9  mov     [rbp+KeyHandle], 0
0x1400840c1  mov     rdi, rdx
0x1400840c4  mov     [rbp+Handle], 0
0x1400840cc  call    PiRegStateOpenClassKey
0x1400840d1  test    eax, eax
0x1400840d3  js      loc_1400841F3
0x1400840d9  cmp     cs:PiRegStateDiscriptor, 0
0x1400840e0  lea     rbx, PiRegStateSysAllInherittedSecurityDescriptor
0x1400840e7  jnz     short loc_140084136
0x1400840e9  xor     edx, edx
0x1400840eb  lea     rax, [rbp+P]
0x1400840ef  mov     r9b, 1
0x1400840f2  mov     [rsp+60h+Data], rax
0x1400840f7  mov     rcx, rbx
0x1400840fa  lea     r8d, [rdx+1]
0x1400840fe  call    cs:__imp_SeCaptureSecurityDescriptor
0x140084105  nop     dword ptr [rax+rax+00h]
0x14008410a  test    eax, eax
0x14008410c  js      short loc_14008412C
0x14008410e  mov     rcx, [rbp+P]; P
0x140084112  xor     edx, edx; Tag
0x140084114  mov     cs:PiRegStateDiscriptor, 1
0x14008411e  call    cs:__imp_ExFreePoolWithTag
0x140084125  nop     dword ptr [rax+rax+00h]
0x14008412a  jmp     short loc_140084136
0x14008412c  mov     cs:PiRegStateDiscriptor, 2
0x140084136  mov     rcx, [rbp+Handle]
0x14008413a  lea     rdx, aProperties; "Properties"
0x140084141  xor     eax, eax
0x140084143  cmp     cs:PiRegStateDiscriptor, 1
0x14008414a  cmovnz  rbx, rax
0x14008414e  lea     rax, [rbp+KeyHandle]
0x140084152  mov     [rsp+60h+var_30], rax
0x140084157  mov     qword ptr [rsp+60h+DataSize], 0
0x140084160  mov     [rsp+60h+Data], rbx
0x140084165  mov     [rbp+P], rbx
0x140084169  call    CmRegUtilCreateWstrKey
0x14008416e  mov     rcx, [rbp+Handle]; Handle
0x140084172  mov     ebx, eax
0x140084174  call    cs:__imp_ZwClose
0x14008417b  nop     dword ptr [rax+rax+00h]
0x140084180  test    ebx, ebx
0x140084182  js      short loc_1400841F1
0x140084184  mov     rcx, [rdi+8]; SecurityDescriptor
0x140084188  call    cs:__imp_RtlLengthSecurityDescriptor
0x14008418f  nop     dword ptr [rax+rax+00h]
0x140084194  mov     r11, [rdi+8]
0x140084198  lea     rdx, aSecurity; "Security"
0x14008419f  xorps   xmm0, xmm0
0x1400841a2  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400841a6  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400841aa  mov     r10d, eax
0x1400841ad  call    WdmlibRtlInitUnicodeStringEx
0x1400841b2  mov     ebx, eax
0x1400841b4  test    eax, eax
0x1400841b6  js      short loc_1400841E1
0x1400841b8  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1400841bc  lea     rdx, [rbp+DestinationString]; ValueName
0x1400841c0  mov     [rsp+60h+DataSize], r10d; DataSize
0x1400841c5  mov     r9d, 3; Type
0x1400841cb  xor     r8d, r8d; TitleIndex
0x1400841ce  mov     [rsp+60h+Data], r11; Data
0x1400841d3  call    cs:__imp_ZwSetValueKey
0x1400841da  nop     dword ptr [rax+rax+00h]
0x1400841df  mov     ebx, eax
0x1400841e1  mov     rcx, [rbp+KeyHandle]; Handle
0x1400841e5  call    cs:__imp_ZwClose
0x1400841ec  nop     dword ptr [rax+rax+00h]
0x1400841f1  mov     eax, ebx
0x1400841f3  mov     rbx, [rsp+60h+arg_0]
0x1400841f8  mov     rdi, [rsp+60h+arg_8]
0x1400841fd  add     rsp, 60h
0x140084201  pop     rbp
0x140084202  retn
```
