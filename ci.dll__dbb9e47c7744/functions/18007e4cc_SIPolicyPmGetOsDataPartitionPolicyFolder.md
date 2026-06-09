# SIPolicyPmGetOsDataPartitionPolicyFolder

- ea: `0x18007e4cc`
- end: `0x18007e54a`
- name: `SIPolicyPmGetOsDataPartitionPolicyFolder`
- size: `126`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f890`
- `0x18007d9e4`
- `0x18007e28c`

## callees

- `0x18007e4cc`
- `0x1800e2a9c`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18007e530`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18007e530`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007e519`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007e519`

## string_xrefs

- `0x18007e4e6`: `\OSDataRoot\Windows\System32\CodeIntegrity`

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
0x18007e4cc  mov     r11, rsp
0x18007e4cf  mov     [r11+8], rbx
0x18007e4d3  push    rdi
0x18007e4d4  sub     rsp, 40h
0x18007e4d8  mov     rbx, rcx
0x18007e4db  mov     qword ptr [r11-28h], 560054h
0x18007e4e3  xorps   xmm0, xmm0
0x18007e4e6  lea     rax, aOsdatarootWind; "\\OSDataRoot\\Windows\\System32\\CodeIn"...
0x18007e4ed  lea     rcx, [r11-28h]; Source
0x18007e4f1  mov     [r11-20h], rax
0x18007e4f5  lea     r8, [r11-18h]
0x18007e4f9  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x18007e4fe  call    SIPolicyBuildPath
0x18007e503  mov     edi, eax
0x18007e505  test    eax, eax
0x18007e507  js      short loc_18007E52B
0x18007e509  movups  xmm0, xmmword ptr [rsp+48h+DestinationString.Length]
0x18007e50e  xor     edx, edx; SourceString
0x18007e510  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x18007e515  movdqu  xmmword ptr [rbx], xmm0
0x18007e519  call    cs:__imp_RtlInitUnicodeString
0x18007e520  nop     dword ptr [rax+rax+00h]
0x18007e525  mov     word ptr [rbx+10h], 101h
0x18007e52b  lea     rcx, [rsp+48h+DestinationString]; UnicodeString
0x18007e530  call    cs:__imp_RtlFreeUnicodeString
0x18007e537  nop     dword ptr [rax+rax+00h]
0x18007e53c  mov     rbx, [rsp+48h+arg_0]
0x18007e541  mov     eax, edi
0x18007e543  add     rsp, 40h
0x18007e547  pop     rdi
0x18007e548  retn
```
