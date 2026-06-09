# ndisCreateFilterDriverRegistry(_UNICODE_STRING const *,uchar)

- ea: `0x14008ae10`
- end: `0x14008b0fc`
- name: `?ndisCreateFilterDriverRegistry@@YAHPEBU_UNICODE_STRING@@E@Z`
- size: `748`
- prototype: `__int64 __fastcall(const struct _UNICODE_STRING *, unsigned __int8)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14009c0c0`

## callees

- `0x1400110b0`
- `0x1400114b0`
- `0x140065890`
- `0x14008ae10`
- `0x14009b448`
- `0x1400eb7c0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14008aef8`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14008aef8`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14008af0f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14008af0f`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14008afc3`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14008afc3`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14008b060`
- `ntoskrnl!RtlWriteRegistryValue` at `0x14008b060`
- `ntoskrnl!RtlCheckRegistryKey` at `0x14008af24`
- `ntoskrnl!RtlCheckRegistryKey` at `0x14008af24`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x14008ae26`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x14008ae26`
- `ntoskrnl!RtlCreateRegistryKey` at `0x14008af3d`
- `ntoskrnl!RtlCreateRegistryKey` at `0x14008af3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008b095`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008b095`
- `ntoskrnl!ExAllocatePool2` at `0x14008aed2`
- `ntoskrnl!ExAllocatePool2` at `0x14008aed2`

## pseudocode

```c
__int64 __fastcall ndisCreateFilterDriverRegistry(const struct _UNICODE_STRING *a1, char a2)
{
  int v4; // edx
  int v6; // edx
  unsigned int v7; // esi
  int v8; // eax
  int RegistryValues; // eax
  int v10; // r14d
  NTSTATUS v11; // eax
  int v12; // ecx
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-49h] BYREF
  _QWORD v14[14]; // [rsp+50h] [rbp-39h] BYREF
  int ValueData; // [rsp+100h] [rbp+77h] BYREF

  if ( (unsigned __int8)RtlIsStateSeparationEnabled() )
    return 0;
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  ValueData = 0;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v4) = 4;
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v4,
      1,
      87,
      (struct _GUID *)&WPP_9524bb9419753e2807bcae08715ee655_Traceguids,
      (char)a1);
  }
  DestinationString.MaximumLength = ndisParameterStr.Length + a1->Length + 2;
  DestinationString.Buffer = (wchar_t *)ExAllocatePool2(64, DestinationString.MaximumLength, 538985550);
  if ( DestinationString.Buffer )
  {
    RtlCopyUnicodeString(&DestinationString, a1);
    RtlAppendUnicodeStringToString(&DestinationString, &ndisParameterStr);
    if ( RtlCheckRegistryKey(1u, DestinationString.Buffer) && RtlCreateRegistryKey(1u, DestinationString.Buffer) )
    {
      v7 = -1073741823;
    }
    else
    {
      v7 = 0;
      memset(v14, 0, sizeof(v14));
      v14[2] = L"DefaultFilterSettings";
      v14[9] = 0;
      v8 = 292;
      if ( !a2 )
        v8 = 36;
      LODWORD(v14[1]) = v8;
      v14[3] = &ValueData;
      LODWORD(v14[4]) = a2 != 0 ? 0x4000000 : 0;
      RegistryValues = RtlQueryRegistryValuesEx(1, DestinationString.Buffer, v14, 0, 0);
      v10 = RegistryValues;
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          v6,
          1,
          88,
          (struct _GUID *)&WPP_9524bb9419753e2807bcae08715ee655_Traceguids,
          RegistryValues,
          a2);
      if ( v10 )
      {
        if ( v10 == -1073741772 )
        {
          v7 = ndisSetAllFilterDefaultParameters(a1, &DestinationString, &ndisFilterDriverParamsStr, a2);
          if ( !v7 )
          {
            ValueData = 1;
            v11 = RtlWriteRegistryValue(1u, DestinationString.Buffer, L"DefaultFilterSettings", 4u, &ValueData, 4u);
            v12 = 0;
            if ( v11 )
              v12 = -1073741823;
            v7 = v12;
          }
        }
        else
        {
          v7 = -1073741823;
        }
      }
    }
  }
  else
  {
    v7 = -1073741670;
  }
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0);
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = 4;
    WPP_RECORDER_SF_qL(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v6,
      1,
      89,
      (struct _GUID *)&WPP_9524bb9419753e2807bcae08715ee655_Traceguids,
      (char)a1,
      v7);
  }
  return v7;
}

```

## disassembly

```asm
0x14008ae10  push    rbp
0x14008ae12  push    rbx
0x14008ae13  push    rdi
0x14008ae14  lea     rbp, [rsp-47h]
0x14008ae19  sub     rsp, 0D0h
0x14008ae20  movzx   edi, dl
0x14008ae23  mov     rbx, rcx
0x14008ae26  call    cs:__imp_RtlIsStateSeparationEnabled
0x14008ae2d  nop     dword ptr [rax+rax+00h]
0x14008ae32  test    al, al
0x14008ae34  jz      short loc_14008AE44
0x14008ae36  xor     eax, eax
0x14008ae38  add     rsp, 0D0h
0x14008ae3f  pop     rdi
0x14008ae40  pop     rbx
0x14008ae41  pop     rbp
0x14008ae42  retn
0x14008ae44  mov     [rsp+0E0h+arg_0], rsi
0x14008ae4c  mov     [rsp+0E0h+arg_8], r12
0x14008ae54  mov     [rsp+0E0h+var_18], r14
0x14008ae5c  xor     r14d, r14d
0x14008ae5f  mov     qword ptr [rbp+57h+DestinationString.Length], r14
0x14008ae63  mov     [rbp+57h+DestinationString.Buffer], r14
0x14008ae67  mov     [rbp+57h+arg_10], r14d
0x14008ae6b  mov     [rsp+0E0h+var_20], r15
0x14008ae73  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008ae7a  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14008ae81  lea     r15, WPP_9524bb9419753e2807bcae08715ee655_Traceguids
0x14008ae88  jz      short loc_14008AEB2
0x14008ae8a  mov     rcx, cs:WPP_GLOBAL_Control
0x14008ae91  mov     r9d, 57h ; 'W'; int
0x14008ae97  mov     qword ptr [rsp+0E0h+ValueLength], rbx; char
0x14008ae9c  mov     r8d, 1; int
0x14008aea2  mov     dl, 4; int
0x14008aea4  mov     [rsp+0E0h+ValueData], r15; struct _GUID *
0x14008aea9  mov     rcx, [rcx+40h]; int
0x14008aead  call    WPP_RECORDER_SF_q
0x14008aeb2  movzx   eax, word ptr [rbx]
0x14008aeb5  mov     ecx, 40h ; '@'
0x14008aeba  add     ax, 2
0x14008aebe  mov     r8d, 2020444Eh
0x14008aec4  add     ax, cs:?ndisParameterStr@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING ndisParameterStr ...
0x14008aecb  movzx   edx, ax
0x14008aece  mov     [rbp+57h+DestinationString.MaximumLength], dx
0x14008aed2  call    cs:__imp_ExAllocatePool2
0x14008aed9  nop     dword ptr [rax+rax+00h]
0x14008aede  mov     [rbp+57h+DestinationString.Buffer], rax
0x14008aee2  test    rax, rax
0x14008aee5  jnz     short loc_14008AEF1
0x14008aee7  mov     esi, 0C000009Ah
0x14008aeec  jmp     loc_14008B082
0x14008aef1  mov     rdx, rbx; SourceString
0x14008aef4  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14008aef8  call    cs:__imp_RtlCopyUnicodeString
0x14008aeff  nop     dword ptr [rax+rax+00h]
0x14008af04  lea     rdx, ?ndisParameterStr@@3U_UNICODE_STRING@@A; Source
0x14008af0b  lea     rcx, [rbp+57h+DestinationString]; Destination
0x14008af0f  call    cs:__imp_RtlAppendUnicodeStringToString
0x14008af16  nop     dword ptr [rax+rax+00h]
0x14008af1b  mov     rdx, [rbp+57h+DestinationString.Buffer]; Path
0x14008af1f  mov     ecx, 1; RelativeTo
0x14008af24  call    cs:__imp_RtlCheckRegistryKey
0x14008af2b  nop     dword ptr [rax+rax+00h]
0x14008af30  test    eax, eax
0x14008af32  jz      short loc_14008AF57
0x14008af34  mov     rdx, [rbp+57h+DestinationString.Buffer]; Path
0x14008af38  mov     ecx, 1; RelativeTo
0x14008af3d  call    cs:__imp_RtlCreateRegistryKey
0x14008af44  nop     dword ptr [rax+rax+00h]
0x14008af49  test    eax, eax
0x14008af4b  jz      short loc_14008AF57
0x14008af4d  mov     esi, 0C0000001h
0x14008af52  jmp     loc_14008B082
0x14008af57  xor     edx, edx; Val
0x14008af59  mov     [rsp+0E0h+arg_18], r13
0x14008af61  mov     r8d, 70h ; 'p'; Size
0x14008af67  lea     rcx, [rbp+57h+var_90]; void *
0x14008af6b  mov     esi, r14d
0x14008af6e  call    memset
0x14008af73  mov     rdx, [rbp+57h+DestinationString.Buffer]
0x14008af77  lea     r13, aDefaultfilters; "DefaultFilterSettings"
0x14008af7e  test    dil, dil
0x14008af81  mov     [rbp+57h+var_80], r13
0x14008af85  mov     ecx, 24h ; '$'
0x14008af8a  mov     [rbp+57h+var_48], r14
0x14008af8e  mov     eax, 124h
0x14008af93  mov     [rsp+0E0h+ValueData], r14
0x14008af98  cmovz   eax, ecx
0x14008af9b  lea     r8, [rbp+57h+var_90]
0x14008af9f  mov     [rbp+57h+var_88], eax
0x14008afa2  lea     rax, [rbp+57h+arg_10]
0x14008afa6  mov     [rbp+57h+var_78], rax
0x14008afaa  movzx   eax, dil
0x14008afae  neg     al
0x14008afb0  sbb     ecx, ecx
0x14008afb2  xor     r9d, r9d
0x14008afb5  and     ecx, 4000000h
0x14008afbb  mov     [rbp+57h+var_70], ecx
0x14008afbe  mov     ecx, 1
0x14008afc3  call    cs:__imp_RtlQueryRegistryValuesEx
0x14008afca  nop     dword ptr [rax+rax+00h]
0x14008afcf  mov     r14d, eax
0x14008afd2  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14008afd9  jz      short loc_14008B004
0x14008afdb  mov     rcx, cs:WPP_GLOBAL_Control
0x14008afe2  mov     r9d, 58h ; 'X'; int
0x14008afe8  mov     dword ptr [rsp+0E0h+var_B0], edi; char
0x14008afec  mov     r8d, 1; int
0x14008aff2  mov     [rsp+0E0h+ValueLength], eax; char
0x14008aff6  mov     [rsp+0E0h+ValueData], r15; struct _GUID *
0x14008affb  mov     rcx, [rcx+40h]; int
0x14008afff  call    WPP_RECORDER_SF_dd
0x14008b004  test    r14d, r14d
0x14008b007  jz      short loc_14008B07A
0x14008b009  cmp     r14d, 0C0000034h
0x14008b010  jz      short loc_14008B019
0x14008b012  mov     esi, 0C0000001h
0x14008b017  jmp     short loc_14008B07A
0x14008b019  movzx   r9d, dil; unsigned __int8
0x14008b01d  lea     r8, ?ndisFilterDriverParamsStr@@3U_UNICODE_STRING@@A; struct _UNICODE_STRING *
0x14008b024  lea     rdx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x14008b028  mov     rcx, rbx; struct _UNICODE_STRING *
0x14008b02b  call    ?ndisSetAllFilterDefaultParameters@@YAHPEBU_UNICODE_STRING@@00E@Z; ndisSetAllFilterDefaultParameters(_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,uchar)
0x14008b030  mov     esi, eax
0x14008b032  test    eax, eax
0x14008b034  jnz     short loc_14008B07A
0x14008b036  mov     rdx, [rbp+57h+DestinationString.Buffer]; Path
0x14008b03a  lea     rax, [rbp+57h+arg_10]
0x14008b03e  mov     [rsp+0E0h+ValueLength], 4; ValueLength
0x14008b046  mov     r9d, 4; ValueType
0x14008b04c  mov     r8, r13; ValueName
0x14008b04f  mov     [rsp+0E0h+ValueData], rax; ValueData
0x14008b054  mov     ecx, 1; RelativeTo
0x14008b059  mov     [rbp+57h+arg_10], 1
0x14008b060  call    cs:__imp_RtlWriteRegistryValue
0x14008b067  nop     dword ptr [rax+rax+00h]
0x14008b06c  mov     ecx, esi
0x14008b06e  mov     esi, 0C0000001h
0x14008b073  test    eax, eax
0x14008b075  cmovnz  ecx, esi
0x14008b078  mov     esi, ecx
0x14008b07a  mov     r13, [rsp+0E0h+arg_18]
0x14008b082  mov     rcx, [rbp+57h+DestinationString.Buffer]; P
0x14008b086  mov     r14, [rsp+0E0h+var_18]
0x14008b08e  test    rcx, rcx
0x14008b091  jz      short loc_14008B0A1
0x14008b093  xor     edx, edx; Tag
0x14008b095  call    cs:__imp_ExFreePoolWithTag
0x14008b09c  nop     dword ptr [rax+rax+00h]
0x14008b0a1  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14008b0a8  mov     r12, [rsp+0E0h+arg_8]
0x14008b0b0  jz      short loc_14008B0DE
0x14008b0b2  mov     rcx, cs:WPP_GLOBAL_Control
0x14008b0b9  mov     r9d, 59h ; 'Y'; int
0x14008b0bf  mov     dword ptr [rsp+0E0h+var_B0], esi; char
0x14008b0c3  mov     r8d, 1; int
0x14008b0c9  mov     qword ptr [rsp+0E0h+ValueLength], rbx; char
0x14008b0ce  mov     dl, 4; int
0x14008b0d0  mov     [rsp+0E0h+ValueData], r15; struct _GUID *
0x14008b0d5  mov     rcx, [rcx+40h]; int
0x14008b0d9  call    WPP_RECORDER_SF_qL
0x14008b0de  mov     r15, [rsp+0E0h+var_20]
0x14008b0e6  mov     eax, esi
0x14008b0e8  mov     rsi, [rsp+0E0h+arg_0]
0x14008b0f0  add     rsp, 0D0h
0x14008b0f7  pop     rdi
0x14008b0f8  pop     rbx
0x14008b0f9  pop     rbp
0x14008b0fa  retn
```
