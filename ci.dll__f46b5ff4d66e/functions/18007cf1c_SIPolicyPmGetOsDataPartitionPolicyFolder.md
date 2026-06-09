# SIPolicyPmGetOsDataPartitionPolicyFolder

- ea: `0x18007cf1c`
- end: `0x18007cf9a`
- name: `SIPolicyPmGetOsDataPartitionPolicyFolder`
- size: `126`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f890`
- `0x18007c434`
- `0x18007ccdc`

## callees

- `0x18007cf1c`
- `0x1800e1aac`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18007cf80`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18007cf80`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007cf69`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007cf69`

## string_xrefs

- `0x18007cf36`: `\OSDataRoot\Windows\System32\CodeIntegrity`

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
0x18007cf1c  mov     r11, rsp
0x18007cf1f  mov     [r11+8], rbx
0x18007cf23  push    rdi
0x18007cf24  sub     rsp, 40h
0x18007cf28  mov     rbx, rcx
0x18007cf2b  mov     qword ptr [r11-28h], 560054h
0x18007cf33  xorps   xmm0, xmm0
0x18007cf36  lea     rax, aOsdatarootWind; "\\OSDataRoot\\Windows\\System32\\CodeIn"...
0x18007cf3d  lea     rcx, [r11-28h]; Source
0x18007cf41  mov     [r11-20h], rax
0x18007cf45  lea     r8, [r11-18h]
0x18007cf49  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x18007cf4e  call    SIPolicyBuildPath
0x18007cf53  mov     edi, eax
0x18007cf55  test    eax, eax
0x18007cf57  js      short loc_18007CF7B
0x18007cf59  movups  xmm0, xmmword ptr [rsp+48h+DestinationString.Length]
0x18007cf5e  xor     edx, edx; SourceString
0x18007cf60  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x18007cf65  movdqu  xmmword ptr [rbx], xmm0
0x18007cf69  call    cs:__imp_RtlInitUnicodeString
0x18007cf70  nop     dword ptr [rax+rax+00h]
0x18007cf75  mov     word ptr [rbx+10h], 101h
0x18007cf7b  lea     rcx, [rsp+48h+DestinationString]; UnicodeString
0x18007cf80  call    cs:__imp_RtlFreeUnicodeString
0x18007cf87  nop     dword ptr [rax+rax+00h]
0x18007cf8c  mov     rbx, [rsp+48h+arg_0]
0x18007cf91  mov     eax, edi
0x18007cf93  add     rsp, 40h
0x18007cf97  pop     rdi
0x18007cf98  retn
```
