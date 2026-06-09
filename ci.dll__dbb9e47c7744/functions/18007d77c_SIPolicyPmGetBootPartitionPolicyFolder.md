# SIPolicyPmGetBootPartitionPolicyFolder

- ea: `0x18007d77c`
- end: `0x18007d7fa`
- name: `SIPolicyPmGetBootPartitionPolicyFolder`
- size: `126`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f890`
- `0x18007d9e4`
- `0x18007deac`
- `0x18007e28c`

## callees

- `0x18007d77c`
- `0x1800e2a9c`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18007d7e0`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18007d7e0`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007d7c9`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007d7c9`

## string_xrefs

- `0x18007d796`: `\SystemRoot\System32\CodeIntegrity`

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
0x18007d77c  mov     r11, rsp
0x18007d77f  mov     [r11+8], rbx
0x18007d783  push    rdi
0x18007d784  sub     rsp, 40h
0x18007d788  mov     rbx, rcx
0x18007d78b  mov     qword ptr [r11-28h], 460044h
0x18007d793  xorps   xmm0, xmm0
0x18007d796  lea     rax, aSystemrootSyst_3; "\\SystemRoot\\System32\\CodeIntegrity"
0x18007d79d  lea     rcx, [r11-28h]; Source
0x18007d7a1  mov     [r11-20h], rax
0x18007d7a5  lea     r8, [r11-18h]
0x18007d7a9  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x18007d7ae  call    SIPolicyBuildPath
0x18007d7b3  mov     edi, eax
0x18007d7b5  test    eax, eax
0x18007d7b7  js      short loc_18007D7DB
0x18007d7b9  movups  xmm0, xmmword ptr [rsp+48h+DestinationString.Length]
0x18007d7be  xor     edx, edx; SourceString
0x18007d7c0  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x18007d7c5  movdqu  xmmword ptr [rbx], xmm0
0x18007d7c9  call    cs:__imp_RtlInitUnicodeString
0x18007d7d0  nop     dword ptr [rax+rax+00h]
0x18007d7d5  mov     word ptr [rbx+10h], 1
0x18007d7db  lea     rcx, [rsp+48h+DestinationString]; UnicodeString
0x18007d7e0  call    cs:__imp_RtlFreeUnicodeString
0x18007d7e7  nop     dword ptr [rax+rax+00h]
0x18007d7ec  mov     rbx, [rsp+48h+arg_0]
0x18007d7f1  mov     eax, edi
0x18007d7f3  add     rsp, 40h
0x18007d7f7  pop     rdi
0x18007d7f8  retn
```
