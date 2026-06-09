# SIPolicyPmGetBootPartitionPolicyFolder

- ea: `0x18007c1cc`
- end: `0x18007c24a`
- name: `SIPolicyPmGetBootPartitionPolicyFolder`
- size: `126`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f890`
- `0x18007c434`
- `0x18007c8fc`
- `0x18007ccdc`

## callees

- `0x18007c1cc`
- `0x1800e1aac`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18007c230`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18007c230`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007c219`
- `ntoskrnl!RtlInitUnicodeString` at `0x18007c219`

## string_xrefs

- `0x18007c1e6`: `\SystemRoot\System32\CodeIntegrity`

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
0x18007c1cc  mov     r11, rsp
0x18007c1cf  mov     [r11+8], rbx
0x18007c1d3  push    rdi
0x18007c1d4  sub     rsp, 40h
0x18007c1d8  mov     rbx, rcx
0x18007c1db  mov     qword ptr [r11-28h], 460044h
0x18007c1e3  xorps   xmm0, xmm0
0x18007c1e6  lea     rax, aSystemrootSyst_3; "\\SystemRoot\\System32\\CodeIntegrity"
0x18007c1ed  lea     rcx, [r11-28h]; Source
0x18007c1f1  mov     [r11-20h], rax
0x18007c1f5  lea     r8, [r11-18h]
0x18007c1f9  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x18007c1fe  call    SIPolicyBuildPath
0x18007c203  mov     edi, eax
0x18007c205  test    eax, eax
0x18007c207  js      short loc_18007C22B
0x18007c209  movups  xmm0, xmmword ptr [rsp+48h+DestinationString.Length]
0x18007c20e  xor     edx, edx; SourceString
0x18007c210  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x18007c215  movdqu  xmmword ptr [rbx], xmm0
0x18007c219  call    cs:__imp_RtlInitUnicodeString
0x18007c220  nop     dword ptr [rax+rax+00h]
0x18007c225  mov     word ptr [rbx+10h], 1
0x18007c22b  lea     rcx, [rsp+48h+DestinationString]; UnicodeString
0x18007c230  call    cs:__imp_RtlFreeUnicodeString
0x18007c237  nop     dword ptr [rax+rax+00h]
0x18007c23c  mov     rbx, [rsp+48h+arg_0]
0x18007c241  mov     eax, edi
0x18007c243  add     rsp, 40h
0x18007c247  pop     rdi
0x18007c248  retn
```
