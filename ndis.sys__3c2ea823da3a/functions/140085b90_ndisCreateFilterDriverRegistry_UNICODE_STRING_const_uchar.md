# ndisCreateFilterDriverRegistry(_UNICODE_STRING const *,uchar)

- ea: `0x140085b90`
- end: `0x140085e7c`
- name: `?ndisCreateFilterDriverRegistry@@YAHPEBU_UNICODE_STRING@@E@Z`
- size: `748`
- prototype: `__int64 __fastcall(const struct _UNICODE_STRING *, unsigned __int8)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x140096e40`

## callees

- `0x14001cf50`
- `0x14001d350`
- `0x140060a10`
- `0x140085b90`
- `0x1400961c8`
- `0x1400e65c0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140085c78`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140085c78`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140085c8f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140085c8f`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140085d43`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140085d43`
- `ntoskrnl!RtlWriteRegistryValue` at `0x140085de0`
- `ntoskrnl!RtlWriteRegistryValue` at `0x140085de0`
- `ntoskrnl!RtlCheckRegistryKey` at `0x140085ca4`
- `ntoskrnl!RtlCheckRegistryKey` at `0x140085ca4`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x140085ba6`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x140085ba6`
- `ntoskrnl!RtlCreateRegistryKey` at `0x140085cbd`
- `ntoskrnl!RtlCreateRegistryKey` at `0x140085cbd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085e15`
- `ntoskrnl!ExFreePoolWithTag` at `0x140085e15`
- `ntoskrnl!ExAllocatePool2` at `0x140085c52`
- `ntoskrnl!ExAllocatePool2` at `0x140085c52`

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
0x140085b90  push    rbp
0x140085b92  push    rbx
0x140085b93  push    rdi
0x140085b94  lea     rbp, [rsp-47h]
0x140085b99  sub     rsp, 0D0h
0x140085ba0  movzx   edi, dl
0x140085ba3  mov     rbx, rcx
0x140085ba6  call    cs:__imp_RtlIsStateSeparationEnabled
0x140085bad  nop     dword ptr [rax+rax+00h]
0x140085bb2  test    al, al
0x140085bb4  jz      short loc_140085BC4
0x140085bb6  xor     eax, eax
0x140085bb8  add     rsp, 0D0h
0x140085bbf  pop     rdi
0x140085bc0  pop     rbx
0x140085bc1  pop     rbp
0x140085bc2  retn
0x140085bc4  mov     [rsp+0E0h+arg_0], rsi
0x140085bcc  mov     [rsp+0E0h+arg_8], r12
0x140085bd4  mov     [rsp+0E0h+var_18], r14
0x140085bdc  xor     r14d, r14d
0x140085bdf  mov     qword ptr [rbp+57h+DestinationString.Length], r14
0x140085be3  mov     [rbp+57h+DestinationString.Buffer], r14
0x140085be7  mov     [rbp+57h+arg_10], r14d
0x140085beb  mov     [rsp+0E0h+var_20], r15
0x140085bf3  lea     r12, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140085bfa  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140085c01  lea     r15, WPP_9524bb9419753e2807bcae08715ee655_Traceguids
0x140085c08  jz      short loc_140085C32
0x140085c0a  mov     rcx, cs:WPP_GLOBAL_Control
0x140085c11  mov     r9d, 57h ; 'W'; int
0x140085c17  mov     qword ptr [rsp+0E0h+ValueLength], rbx; char
0x140085c1c  mov     r8d, 1; int
0x140085c22  mov     dl, 4; int
0x140085c24  mov     [rsp+0E0h+ValueData], r15; struct _GUID *
0x140085c29  mov     rcx, [rcx+40h]; int
0x140085c2d  call    WPP_RECORDER_SF_q
0x140085c32  movzx   eax, word ptr [rbx]
0x140085c35  mov     ecx, 40h ; '@'
0x140085c3a  add     ax, 2
0x140085c3e  mov     r8d, 2020444Eh
0x140085c44  add     ax, cs:?ndisParameterStr@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING ndisParameterStr ...
0x140085c4b  movzx   edx, ax
0x140085c4e  mov     [rbp+57h+DestinationString.MaximumLength], dx
0x140085c52  call    cs:__imp_ExAllocatePool2
0x140085c59  nop     dword ptr [rax+rax+00h]
0x140085c5e  mov     [rbp+57h+DestinationString.Buffer], rax
0x140085c62  test    rax, rax
0x140085c65  jnz     short loc_140085C71
0x140085c67  mov     esi, 0C000009Ah
0x140085c6c  jmp     loc_140085E02
0x140085c71  mov     rdx, rbx; SourceString
0x140085c74  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140085c78  call    cs:__imp_RtlCopyUnicodeString
0x140085c7f  nop     dword ptr [rax+rax+00h]
0x140085c84  lea     rdx, ?ndisParameterStr@@3U_UNICODE_STRING@@A; Source
0x140085c8b  lea     rcx, [rbp+57h+DestinationString]; Destination
0x140085c8f  call    cs:__imp_RtlAppendUnicodeStringToString
0x140085c96  nop     dword ptr [rax+rax+00h]
0x140085c9b  mov     rdx, [rbp+57h+DestinationString.Buffer]; Path
0x140085c9f  mov     ecx, 1; RelativeTo
0x140085ca4  call    cs:__imp_RtlCheckRegistryKey
0x140085cab  nop     dword ptr [rax+rax+00h]
0x140085cb0  test    eax, eax
0x140085cb2  jz      short loc_140085CD7
0x140085cb4  mov     rdx, [rbp+57h+DestinationString.Buffer]; Path
0x140085cb8  mov     ecx, 1; RelativeTo
0x140085cbd  call    cs:__imp_RtlCreateRegistryKey
0x140085cc4  nop     dword ptr [rax+rax+00h]
0x140085cc9  test    eax, eax
0x140085ccb  jz      short loc_140085CD7
0x140085ccd  mov     esi, 0C0000001h
0x140085cd2  jmp     loc_140085E02
0x140085cd7  xor     edx, edx; Val
0x140085cd9  mov     [rsp+0E0h+arg_18], r13
0x140085ce1  mov     r8d, 70h ; 'p'; Size
0x140085ce7  lea     rcx, [rbp+57h+var_90]; void *
0x140085ceb  mov     esi, r14d
0x140085cee  call    memset
0x140085cf3  mov     rdx, [rbp+57h+DestinationString.Buffer]
0x140085cf7  lea     r13, aDefaultfilters; "DefaultFilterSettings"
0x140085cfe  test    dil, dil
0x140085d01  mov     [rbp+57h+var_80], r13
0x140085d05  mov     ecx, 24h ; '$'
0x140085d0a  mov     [rbp+57h+var_48], r14
0x140085d0e  mov     eax, 124h
0x140085d13  mov     [rsp+0E0h+ValueData], r14
0x140085d18  cmovz   eax, ecx
0x140085d1b  lea     r8, [rbp+57h+var_90]
0x140085d1f  mov     [rbp+57h+var_88], eax
0x140085d22  lea     rax, [rbp+57h+arg_10]
0x140085d26  mov     [rbp+57h+var_78], rax
0x140085d2a  movzx   eax, dil
0x140085d2e  neg     al
0x140085d30  sbb     ecx, ecx
0x140085d32  xor     r9d, r9d
0x140085d35  and     ecx, 4000000h
0x140085d3b  mov     [rbp+57h+var_70], ecx
0x140085d3e  mov     ecx, 1
0x140085d43  call    cs:__imp_RtlQueryRegistryValuesEx
0x140085d4a  nop     dword ptr [rax+rax+00h]
0x140085d4f  mov     r14d, eax
0x140085d52  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140085d59  jz      short loc_140085D84
0x140085d5b  mov     rcx, cs:WPP_GLOBAL_Control
0x140085d62  mov     r9d, 58h ; 'X'; int
0x140085d68  mov     dword ptr [rsp+0E0h+var_B0], edi; char
0x140085d6c  mov     r8d, 1; int
0x140085d72  mov     [rsp+0E0h+ValueLength], eax; char
0x140085d76  mov     [rsp+0E0h+ValueData], r15; struct _GUID *
0x140085d7b  mov     rcx, [rcx+40h]; int
0x140085d7f  call    WPP_RECORDER_SF_dd
0x140085d84  test    r14d, r14d
0x140085d87  jz      short loc_140085DFA
0x140085d89  cmp     r14d, 0C0000034h
0x140085d90  jz      short loc_140085D99
0x140085d92  mov     esi, 0C0000001h
0x140085d97  jmp     short loc_140085DFA
0x140085d99  movzx   r9d, dil; unsigned __int8
0x140085d9d  lea     r8, ?ndisFilterDriverParamsStr@@3U_UNICODE_STRING@@A; struct _UNICODE_STRING *
0x140085da4  lea     rdx, [rbp+57h+DestinationString]; struct _UNICODE_STRING *
0x140085da8  mov     rcx, rbx; struct _UNICODE_STRING *
0x140085dab  call    ?ndisSetAllFilterDefaultParameters@@YAHPEBU_UNICODE_STRING@@00E@Z; ndisSetAllFilterDefaultParameters(_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,uchar)
0x140085db0  mov     esi, eax
0x140085db2  test    eax, eax
0x140085db4  jnz     short loc_140085DFA
0x140085db6  mov     rdx, [rbp+57h+DestinationString.Buffer]; Path
0x140085dba  lea     rax, [rbp+57h+arg_10]
0x140085dbe  mov     [rsp+0E0h+ValueLength], 4; ValueLength
0x140085dc6  mov     r9d, 4; ValueType
0x140085dcc  mov     r8, r13; ValueName
0x140085dcf  mov     [rsp+0E0h+ValueData], rax; ValueData
0x140085dd4  mov     ecx, 1; RelativeTo
0x140085dd9  mov     [rbp+57h+arg_10], 1
0x140085de0  call    cs:__imp_RtlWriteRegistryValue
0x140085de7  nop     dword ptr [rax+rax+00h]
0x140085dec  mov     ecx, esi
0x140085dee  mov     esi, 0C0000001h
0x140085df3  test    eax, eax
0x140085df5  cmovnz  ecx, esi
0x140085df8  mov     esi, ecx
0x140085dfa  mov     r13, [rsp+0E0h+arg_18]
0x140085e02  mov     rcx, [rbp+57h+DestinationString.Buffer]; P
0x140085e06  mov     r14, [rsp+0E0h+var_18]
0x140085e0e  test    rcx, rcx
0x140085e11  jz      short loc_140085E21
0x140085e13  xor     edx, edx; Tag
0x140085e15  call    cs:__imp_ExFreePoolWithTag
0x140085e1c  nop     dword ptr [rax+rax+00h]
0x140085e21  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140085e28  mov     r12, [rsp+0E0h+arg_8]
0x140085e30  jz      short loc_140085E5E
0x140085e32  mov     rcx, cs:WPP_GLOBAL_Control
0x140085e39  mov     r9d, 59h ; 'Y'; int
0x140085e3f  mov     dword ptr [rsp+0E0h+var_B0], esi; char
0x140085e43  mov     r8d, 1; int
0x140085e49  mov     qword ptr [rsp+0E0h+ValueLength], rbx; char
0x140085e4e  mov     dl, 4; int
0x140085e50  mov     [rsp+0E0h+ValueData], r15; struct _GUID *
0x140085e55  mov     rcx, [rcx+40h]; int
0x140085e59  call    WPP_RECORDER_SF_qL
0x140085e5e  mov     r15, [rsp+0E0h+var_20]
0x140085e66  mov     eax, esi
0x140085e68  mov     rsi, [rsp+0E0h+arg_0]
0x140085e70  add     rsp, 0D0h
0x140085e77  pop     rdi
0x140085e78  pop     rbx
0x140085e79  pop     rbp
0x140085e7a  retn
```
