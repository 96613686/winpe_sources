# CreateNewVolumeName

- ea: `0x1400195d0`
- end: `0x140019775`
- name: `CreateNewVolumeName`
- size: `421`
- prototype: `__int64 __fastcall(PUNICODE_STRING Destination)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140014fc0`
- `0x1400192f0`

## callees

- `0x140001ae0`
- `0x140001b30`
- `0x140002d70`
- `0x1400195d0`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001972d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14001972d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140019719`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140019719`
- `ntoskrnl!ExAllocatePool2` at `0x1400196b8`
- `ntoskrnl!ExAllocatePool2` at `0x1400196b8`
- `ntoskrnl!RtlStringFromGUID` at `0x140019613`
- `ntoskrnl!RtlStringFromGUID` at `0x140019613`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400196d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001974e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400196d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001974e`
- `ntoskrnl!ExUuidCreate` at `0x14001965d`
- `ntoskrnl!ExUuidCreate` at `0x14001965d`

## pseudocode

```c
__int64 __fastcall CreateNewVolumeName(PUNICODE_STRING Destination, GUID *a2)
{
  unsigned int v3; // edi
  __int64 v4; // r8
  __int64 v6; // r8
  WCHAR *Pool2; // rax
  struct _UNICODE_STRING GuidString; // [rsp+20h] [rbp-38h] BYREF
  GUID Guid; // [rsp+30h] [rbp-28h] BYREF

  Guid = 0;
  GuidString = 0;
  if ( a2 )
  {
    Guid = *a2;
  }
  else
  {
    v3 = ExUuidCreate(&Guid);
    if ( (v3 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 21, v6, v3);
      return v3;
    }
  }
  v3 = RtlStringFromGUID(&Guid, &GuidString);
  if ( (v3 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 22, v4, v3);
      return v3;
    }
    return v3;
  }
  Destination->MaximumLength = 96;
  Pool2 = (WCHAR *)ExAllocatePool2(258, 98, 1098149453);
  Destination->Buffer = Pool2;
  if ( Pool2 )
  {
    RtlCopyUnicodeString(Destination, &stru_140007098);
    RtlAppendUnicodeStringToString(Destination, &GuidString);
    Destination->Buffer[(unsigned __int64)Destination->Length >> 1] = 0;
    ExFreePoolWithTag(GuidString.Buffer, 0);
    return 0;
  }
  else
  {
    ExFreePoolWithTag(GuidString.Buffer, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23);
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x1400195d0  mov     [rsp+arg_10], rbx
0x1400195d5  push    rdi
0x1400195d6  sub     rsp, 50h
0x1400195da  mov     rax, cs:__security_cookie
0x1400195e1  xor     rax, rsp
0x1400195e4  mov     [rsp+58h+var_18], rax
0x1400195e9  xorps   xmm0, xmm0
0x1400195ec  xorps   xmm1, xmm1
0x1400195ef  mov     rbx, rcx
0x1400195f2  movups  xmmword ptr [rsp+58h+Guid.Data1], xmm0
0x1400195f7  movups  xmmword ptr [rsp+58h+GuidString.Length], xmm1
0x1400195fc  test    rdx, rdx
0x1400195ff  jz      short loc_140019658
0x140019601  movups  xmm0, xmmword ptr [rdx]
0x140019604  movups  xmmword ptr [rsp+58h+Guid.Data1], xmm0
0x140019609  lea     rdx, [rsp+58h+GuidString]; GuidString
0x14001960e  lea     rcx, [rsp+58h+Guid]; Guid
0x140019613  call    cs:__imp_RtlStringFromGUID
0x14001961a  nop     dword ptr [rax+rax+00h]
0x14001961f  mov     edi, eax
0x140019621  test    eax, eax
0x140019623  jns     short loc_1400196A2
0x140019625  mov     rcx, cs:WPP_GLOBAL_Control
0x14001962c  lea     rax, WPP_GLOBAL_Control
0x140019633  cmp     rcx, rax
0x140019636  jz      short loc_14001969B
0x140019638  mov     edx, [rcx+2Ch]
0x14001963b  test    dl, 1
0x14001963e  jz      short loc_14001969B
0x140019640  mov     rcx, [rcx+18h]
0x140019644  mov     edx, 16h
0x140019649  mov     r9d, edi
0x14001964c  call    WPP_SF_L
0x140019651  mov     eax, edi
0x140019653  jmp     loc_14001975C
0x140019658  lea     rcx, [rsp+58h+Guid]; Uuid
0x14001965d  call    cs:__imp_ExUuidCreate
0x140019664  nop     dword ptr [rax+rax+00h]
0x140019669  mov     edi, eax
0x14001966b  test    eax, eax
0x14001966d  jns     short loc_140019609
0x14001966f  mov     rcx, cs:WPP_GLOBAL_Control
0x140019676  lea     rax, WPP_GLOBAL_Control
0x14001967d  cmp     rcx, rax
0x140019680  jz      short loc_14001969B
0x140019682  mov     edx, [rcx+2Ch]
0x140019685  test    dl, 1
0x140019688  jz      short loc_14001969B
0x14001968a  mov     rcx, [rcx+18h]
0x14001968e  mov     edx, 15h
0x140019693  mov     r9d, edi
0x140019696  call    WPP_SF_L
0x14001969b  mov     eax, edi
0x14001969d  jmp     loc_14001975C
0x1400196a2  mov     edx, 62h ; 'b'
0x1400196a7  mov     word ptr [rbx+2], 60h ; '`'
0x1400196ad  mov     ecx, 102h
0x1400196b2  mov     r8d, 41746E4Dh
0x1400196b8  call    cs:__imp_ExAllocatePool2
0x1400196bf  nop     dword ptr [rax+rax+00h]
0x1400196c4  mov     [rbx+8], rax
0x1400196c8  test    rax, rax
0x1400196cb  jnz     short loc_14001970F
0x1400196cd  mov     rcx, [rsp+58h+GuidString.Buffer]; P
0x1400196d2  xor     edx, edx; Tag
0x1400196d4  call    cs:__imp_ExFreePoolWithTag
0x1400196db  nop     dword ptr [rax+rax+00h]
0x1400196e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400196e7  lea     rax, WPP_GLOBAL_Control
0x1400196ee  cmp     rcx, rax
0x1400196f1  jz      short loc_140019708
0x1400196f3  mov     eax, [rcx+2Ch]
0x1400196f6  test    al, 4
0x1400196f8  jz      short loc_140019708
0x1400196fa  mov     rcx, [rcx+18h]
0x1400196fe  mov     edx, 17h
0x140019703  call    WPP_SF_
0x140019708  mov     eax, 0C000009Ah
0x14001970d  jmp     short loc_14001975C
0x14001970f  lea     rdx, stru_140007098; SourceString
0x140019716  mov     rcx, rbx; DestinationString
0x140019719  call    cs:__imp_RtlCopyUnicodeString
0x140019720  nop     dword ptr [rax+rax+00h]
0x140019725  lea     rdx, [rsp+58h+GuidString]; Source
0x14001972a  mov     rcx, rbx; Destination
0x14001972d  call    cs:__imp_RtlAppendUnicodeStringToString
0x140019734  nop     dword ptr [rax+rax+00h]
0x140019739  movzx   ecx, word ptr [rbx]
0x14001973c  xor     edx, edx; Tag
0x14001973e  mov     rax, [rbx+8]
0x140019742  shr     rcx, 1
0x140019745  mov     [rax+rcx*2], dx
0x140019749  mov     rcx, [rsp+58h+GuidString.Buffer]; P
0x14001974e  call    cs:__imp_ExFreePoolWithTag
0x140019755  nop     dword ptr [rax+rax+00h]
0x14001975a  xor     eax, eax
0x14001975c  mov     rcx, [rsp+58h+var_18]
0x140019761  xor     rcx, rsp; StackCookie
0x140019764  call    __security_check_cookie
0x140019769  mov     rbx, [rsp+58h+arg_10]
0x14001976e  add     rsp, 50h
0x140019772  pop     rdi
0x140019773  retn
```
