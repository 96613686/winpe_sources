# SIPolicyPmGetBootPartitionPolicyFolder

- ea: `0x18007e190`
- end: `0x18007e20e`
- name: `SIPolicyPmGetBootPartitionPolicyFolder`
- size: `126`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f8a0`
- `0x18007e3f8`
- `0x18007e8c0`
- `0x18007eca0`

## callees

- `0x18007e190`
- `0x1800e2a68`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18007e1f4`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18007e1f4`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007e1dd`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007e1dd`

## string_xrefs

- `0x18007e1aa`: `\SystemRoot\System32\CodeIntegrity`

## pseudocode

```c
__int64 __fastcall SIPolicyPmGetBootPartitionPolicyFolder(struct _UNICODE_STRING *a1, const UNICODE_STRING *a2)
{
  int v3; // edi
  UNICODE_STRING v5; // [rsp+20h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF

  *(_QWORD *)&v5.Length = 4587588;
  v5.Buffer = L"\\SystemRoot\\System32\\CodeIntegrity";
  DestinationString = 0;
  v3 = SIPolicyBuildPath(&v5, a2);
  if ( v3 >= 0 )
  {
    *a1 = DestinationString;
    RtlInitUnicodeString(&DestinationString, 0);
    a1[1].Length = 1;
  }
  RtlFreeUnicodeString(&DestinationString);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18007e190  mov     r11, rsp
0x18007e193  mov     [r11+8], rbx
0x18007e197  push    rdi
0x18007e198  sub     rsp, 40h
0x18007e19c  mov     rbx, rcx
0x18007e19f  mov     qword ptr [r11-28h], 460044h
0x18007e1a7  xorps   xmm0, xmm0
0x18007e1aa  lea     rax, aSystemrootSyst_3; "\\SystemRoot\\System32\\CodeIntegrity"
0x18007e1b1  lea     rcx, [r11-28h]; Source
0x18007e1b5  mov     [r11-20h], rax
0x18007e1b9  lea     r8, [r11-18h]
0x18007e1bd  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x18007e1c2  call    SIPolicyBuildPath
0x18007e1c7  mov     edi, eax
0x18007e1c9  test    eax, eax
0x18007e1cb  js      short loc_18007E1EF
0x18007e1cd  movups  xmm0, xmmword ptr [rsp+48h+DestinationString.Length]
0x18007e1d2  xor     edx, edx; SourceString
0x18007e1d4  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x18007e1d9  movdqu  xmmword ptr [rbx], xmm0
0x18007e1dd  call    cs:__imp_RtlInitUnicodeString
0x18007e1e4  nop     dword ptr [rax+rax+00h]
0x18007e1e9  mov     word ptr [rbx+10h], 1
0x18007e1ef  lea     rcx, [rsp+48h+DestinationString]; UnicodeString
0x18007e1f4  call    cs:__imp_RtlFreeUnicodeString
0x18007e1fb  nop     dword ptr [rax+rax+00h]
0x18007e200  mov     rbx, [rsp+48h+arg_0]
0x18007e205  mov     eax, edi
0x18007e207  add     rsp, 40h
0x18007e20b  pop     rdi
0x18007e20c  retn
```
