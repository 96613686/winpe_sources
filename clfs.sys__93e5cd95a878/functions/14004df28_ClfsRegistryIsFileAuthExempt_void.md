# ClfsRegistryIsFileAuthExempt(void *)

- ea: `0x14004df28`
- end: `0x14004dfeb`
- name: `?ClfsRegistryIsFileAuthExempt@@YAEPEAX@Z`
- size: `195`
- prototype: `unsigned __int8 __fastcall(PVOID Object)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, registry_config, service_task`

## callers

- `0x14003a7cc`
- `0x140078d5c`

## callees

- `0x14000f7bc`
- `0x140018280`
- `0x14004df28`
- `0x14004ea80`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14004dfae`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14004dfae`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004dfc2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004dfc2`

## string_xrefs

- `0x14004df9c`: `\Registry\Machine\System\CurrentControlSet\Services\CLFS\Authentication\Exemptions`

## pseudocode

```c
unsigned __int8 __fastcall ClfsRegistryIsFileAuthExempt(PVOID Object)
{
  __int64 v2; // rcx
  int v3; // ebx
  UNICODE_STRING Destination; // [rsp+30h] [rbp-39h] BYREF
  PVOID P; // [rsp+40h] [rbp-29h]
  _QWORD v7[14]; // [rsp+50h] [rbp-19h] BYREF

  memset(v7, 0, sizeof(v7));
  P = 0;
  Destination = 0;
  if ( Object
    && (unsigned int)Feature_CLFS_AuthenticationExemptions__private_IsEnabledDeviceUsageNoInline(v2)
    && (LOBYTE(Destination.Length) = 0, (int)QueryNormalizedObjectName(Object, (PUNICODE_STRING)&Destination.Buffer) >= 0)
    && (LODWORD(v7[1]) = 20,
        v7[0] = ClfsRegistryQueryExemptionRoutine,
        LODWORD(v7[4]) = 0,
        v3 = RtlQueryRegistryValuesEx(
               0,
               L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\CLFS\\Authentication\\Exemptions",
               v7,
               &Destination,
               0),
        ExFreePoolWithTag(P, 0),
        v3 >= 0) )
  {
    return Destination.Length;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x14004df28  mov     [rsp-8+arg_0], rbx
0x14004df2d  push    rbp
0x14004df2e  lea     rbp, [rsp-57h]
0x14004df33  sub     rsp, 0C0h
0x14004df3a  xor     edx, edx; Val
0x14004df3c  mov     rbx, rcx
0x14004df3f  lea     rcx, [rbp+57h+var_70]; void *
0x14004df43  lea     r8d, [rdx+70h]; Size
0x14004df47  call    memset
0x14004df4c  xor     eax, eax
0x14004df4e  xorps   xmm0, xmm0
0x14004df51  mov     [rbp+57h+P], rax
0x14004df55  movups  xmmword ptr [rbp+57h+Destination.Length], xmm0
0x14004df59  test    rbx, rbx
0x14004df5c  jz      short loc_14004DFD7
0x14004df5e  call    Feature_CLFS_AuthenticationExemptions__private_IsEnabledDeviceUsageNoInline
0x14004df63  test    eax, eax
0x14004df65  jz      short loc_14004DFD7
0x14004df67  lea     rdx, [rbp+57h+Destination.Buffer]; Destination
0x14004df6b  mov     byte ptr [rbp+57h+Destination.Length], 0
0x14004df6f  mov     rcx, rbx; Object
0x14004df72  call    QueryNormalizedObjectName
0x14004df77  test    eax, eax
0x14004df79  js      short loc_14004DFD7
0x14004df7b  lea     rax, ClfsRegistryQueryExemptionRoutine
0x14004df82  mov     [rbp+57h+var_68], 14h
0x14004df89  lea     r9, [rbp+57h+Destination]
0x14004df8d  mov     [rbp+57h+var_70], rax
0x14004df91  lea     r8, [rbp+57h+var_70]
0x14004df95  mov     [rbp+57h+var_50], 0
0x14004df9c  lea     rdx, aRegistryMachin_3; "\\Registry\\Machine\\System\\CurrentCon"...
0x14004dfa3  mov     [rsp+0C0h+var_A0], 0
0x14004dfac  xor     ecx, ecx
0x14004dfae  call    cs:__imp_RtlQueryRegistryValuesEx
0x14004dfb5  nop     dword ptr [rax+rax+00h]
0x14004dfba  mov     rcx, [rbp+57h+P]; P
0x14004dfbe  xor     edx, edx; Tag
0x14004dfc0  mov     ebx, eax
0x14004dfc2  call    cs:__imp_ExFreePoolWithTag
0x14004dfc9  nop     dword ptr [rax+rax+00h]
0x14004dfce  test    ebx, ebx
0x14004dfd0  js      short loc_14004DFD7
0x14004dfd2  mov     al, byte ptr [rbp+57h+Destination.Length]
0x14004dfd5  jmp     short loc_14004DFD9
0x14004dfd7  xor     al, al
0x14004dfd9  mov     rbx, [rsp+0C0h+arg_0]
0x14004dfe1  add     rsp, 0C0h
0x14004dfe8  pop     rbp
0x14004dfe9  retn
```
