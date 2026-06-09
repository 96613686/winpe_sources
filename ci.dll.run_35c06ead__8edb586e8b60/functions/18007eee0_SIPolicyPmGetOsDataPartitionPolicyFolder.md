# SIPolicyPmGetOsDataPartitionPolicyFolder

- ea: `0x18007eee0`
- end: `0x18007ef5e`
- name: `SIPolicyPmGetOsDataPartitionPolicyFolder`
- size: `126`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f8a0`
- `0x18007e3f8`
- `0x18007eca0`

## callees

- `0x18007eee0`
- `0x1800e2a68`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18007ef44`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18007ef44`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007ef2d`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007ef2d`

## string_xrefs

- `0x18007eefa`: `\OSDataRoot\Windows\System32\CodeIntegrity`

## pseudocode

```c
__int64 __fastcall SIPolicyPmGetOsDataPartitionPolicyFolder(struct _UNICODE_STRING *a1, const UNICODE_STRING *a2)
{
  int v3; // edi
  UNICODE_STRING v5; // [rsp+20h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF

  *(_QWORD *)&v5.Length = 5636180;
  v5.Buffer = L"\\OSDataRoot\\Windows\\System32\\CodeIntegrity";
  DestinationString = 0;
  v3 = SIPolicyBuildPath(&v5, a2);
  if ( v3 >= 0 )
  {
    *a1 = DestinationString;
    RtlInitUnicodeString(&DestinationString, 0);
    a1[1].Length = 257;
  }
  RtlFreeUnicodeString(&DestinationString);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18007eee0  mov     r11, rsp
0x18007eee3  mov     [r11+8], rbx
0x18007eee7  push    rdi
0x18007eee8  sub     rsp, 40h
0x18007eeec  mov     rbx, rcx
0x18007eeef  mov     qword ptr [r11-28h], 560054h
0x18007eef7  xorps   xmm0, xmm0
0x18007eefa  lea     rax, aOsdatarootWind; "\\OSDataRoot\\Windows\\System32\\CodeIn"...
0x18007ef01  lea     rcx, [r11-28h]; Source
0x18007ef05  mov     [r11-20h], rax
0x18007ef09  lea     r8, [r11-18h]
0x18007ef0d  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x18007ef12  call    SIPolicyBuildPath
0x18007ef17  mov     edi, eax
0x18007ef19  test    eax, eax
0x18007ef1b  js      short loc_18007EF3F
0x18007ef1d  movups  xmm0, xmmword ptr [rsp+48h+DestinationString.Length]
0x18007ef22  xor     edx, edx; SourceString
0x18007ef24  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x18007ef29  movdqu  xmmword ptr [rbx], xmm0
0x18007ef2d  call    cs:__imp_RtlInitUnicodeString
0x18007ef34  nop     dword ptr [rax+rax+00h]
0x18007ef39  mov     word ptr [rbx+10h], 101h
0x18007ef3f  lea     rcx, [rsp+48h+DestinationString]; UnicodeString
0x18007ef44  call    cs:__imp_RtlFreeUnicodeString
0x18007ef4b  nop     dword ptr [rax+rax+00h]
0x18007ef50  mov     rbx, [rsp+48h+arg_0]
0x18007ef55  mov     eax, edi
0x18007ef57  add     rsp, 40h
0x18007ef5b  pop     rdi
0x18007ef5c  retn
```
