# ndisCreateFilterAdapterRegistry(_UNICODE_STRING const *,_NDIS_MINIPORT_BLOCK *,uchar)

- ea: `0x1400641e0`
- end: `0x14006455b`
- name: `?ndisCreateFilterAdapterRegistry@@YAHPEBU_UNICODE_STRING@@PEAU_NDIS_MINIPORT_BLOCK@@E@Z`
- size: `891`
- prototype: `__int64 __fastcall(const struct _UNICODE_STRING *, struct _NDIS_MINIPORT_BLOCK *, unsigned __int8)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140180960`

## callees

- `0x140019c70`
- `0x14001c050`
- `0x1400641e0`
- `0x1400961c8`
- `0x1400e65c0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14006433e`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14006433e`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140064355`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140064389`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400643ba`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140064355`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140064389`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400643ba`
- `ntoskrnl!RtlStringFromGUID` at `0x1400642ab`
- `ntoskrnl!RtlStringFromGUID` at `0x1400642ab`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400642dc`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400643e7`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400642dc`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400643e7`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400644e0`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x1400644e0`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x1400642ca`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x1400642ca`
- `ntoskrnl!RtlCheckRegistryKey` at `0x14006436a`
- `ntoskrnl!RtlCheckRegistryKey` at `0x14006439e`
- `ntoskrnl!RtlCheckRegistryKey` at `0x1400643cf`
- `ntoskrnl!RtlCheckRegistryKey` at `0x14006436a`
- `ntoskrnl!RtlCheckRegistryKey` at `0x14006439e`
- `ntoskrnl!RtlCheckRegistryKey` at `0x1400643cf`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x1400641fc`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x1400641fc`
- `ntoskrnl!RtlCreateRegistryKey` at `0x140064516`
- `ntoskrnl!RtlCreateRegistryKey` at `0x14006453d`
- `ntoskrnl!RtlCreateRegistryKey` at `0x140064516`
- `ntoskrnl!RtlCreateRegistryKey` at `0x14006453d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006440d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006440d`
- `ntoskrnl!ExAllocatePool2` at `0x14006431b`
- `ntoskrnl!ExAllocatePool2` at `0x14006431b`

## pseudocode

```c
__int64 __fastcall ndisCreateFilterAdapterRegistry(
        const struct _UNICODE_STRING *a1,
        struct _NDIS_MINIPORT_BLOCK *a2,
        unsigned __int8 a3)
{
  int v6; // edx
  _NDIS_MINIPORT_BLOCK *BaseMiniport; // rcx
  NTSTATUS v8; // ebx
  unsigned int v9; // ebx
  struct _UNICODE_STRING Destination; // [rsp+40h] [rbp-69h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-59h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+60h] [rbp-49h] BYREF
  _QWORD v14[14]; // [rsp+70h] [rbp-39h] BYREF
  int v15; // [rsp+128h] [rbp+7Fh] BYREF

  if ( (unsigned __int8)RtlIsStateSeparationEnabled() )
    return 0;
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  *(_QWORD *)&GuidString.Length = 0;
  GuidString.Buffer = 0;
  *(_QWORD *)&Destination.Length = 0;
  Destination.Buffer = 0;
  v15 = 0;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = 4;
    WPP_RECORDER_SF_qq(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v6,
      1,
      90,
      (struct _GUID *)&WPP_9524bb9419753e2807bcae08715ee655_Traceguids,
      (char)a1,
      (char)a2);
  }
  BaseMiniport = a2->BaseMiniport;
  if ( BaseMiniport )
  {
    if ( RtlStringFromGUID(&BaseMiniport->InterfaceGuid, &GuidString)
      || (v8 = RtlUpcaseUnicodeString(&DestinationString, &GuidString, 1u), RtlFreeUnicodeString(&GuidString), v8) )
    {
      v9 = -1073741823;
    }
    else
    {
      Destination.MaximumLength = DestinationString.Length
                                + ndisParameterStr.Length
                                + ndisFilterAdapterStr.Length
                                + a1->Length
                                + 2;
      Destination.Buffer = (wchar_t *)ExAllocatePool2(64, Destination.MaximumLength, 538985550);
      if ( Destination.Buffer )
      {
        v9 = 0;
        RtlCopyUnicodeString(&Destination, a1);
        RtlAppendUnicodeStringToString(&Destination, &ndisParameterStr);
        if ( RtlCheckRegistryKey(1u, Destination.Buffer)
          || (memset(v14, 0, sizeof(v14)),
              v14[2] = L"SkipNdisAdaptersKeyGeneration",
              LODWORD(v14[1]) = 292,
              v14[3] = &v15,
              LODWORD(v14[4]) = 0x4000000,
              v14[9] = 0,
              (unsigned int)RtlQueryRegistryValuesEx(1, Destination.Buffer, v14, 0, 0))
          || v15 != 1 )
        {
          RtlAppendUnicodeStringToString(&Destination, &ndisFilterAdapterStr);
          if ( RtlCheckRegistryKey(1u, Destination.Buffer) && RtlCreateRegistryKey(1u, Destination.Buffer) )
          {
            v9 = -1073741823;
          }
          else
          {
            RtlAppendUnicodeStringToString(&Destination, &DestinationString);
            if ( RtlCheckRegistryKey(1u, Destination.Buffer) )
            {
              if ( RtlCreateRegistryKey(1u, Destination.Buffer) )
                v9 = -1073741823;
              else
                v9 = ndisSetAllFilterDefaultParameters(a1, &Destination, &ndisFilterAdapterParamsStr, a3);
            }
          }
        }
      }
      else
      {
        v9 = -1073741670;
      }
      RtlFreeUnicodeString(&DestinationString);
    }
  }
  else
  {
    v9 = -1073741811;
  }
  if ( Destination.Buffer )
    ExFreePoolWithTag(Destination.Buffer, 0);
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = 4;
    WPP_RECORDER_SF_qqL(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v6,
      1,
      91,
      (struct _GUID *)&WPP_9524bb9419753e2807bcae08715ee655_Traceguids,
      (char)a1,
      (char)a2,
      v9);
  }
  return v9;
}

```

## disassembly

```asm
0x1400641e0  push    rbp
0x1400641e2  push    rsi
0x1400641e3  push    rdi
0x1400641e4  push    r14
0x1400641e6  lea     rbp, [rsp-3Fh]
0x1400641eb  sub     rsp, 0E8h
0x1400641f2  movzx   r14d, r8b
0x1400641f6  mov     rdi, rdx
0x1400641f9  mov     rsi, rcx
0x1400641fc  call    cs:__imp_RtlIsStateSeparationEnabled
0x140064203  nop     dword ptr [rax+rax+00h]
0x140064208  test    al, al
0x14006420a  jnz     loc_140064485
0x140064210  mov     [rsp+100h+arg_0], rbx
0x140064218  mov     [rsp+100h+arg_8], r12
0x140064220  mov     [rsp+100h+arg_10], r13
0x140064228  mov     [rsp+100h+var_20], r15
0x140064230  xor     r15d, r15d
0x140064233  mov     qword ptr [rbp+57h+DestinationString.Length], r15
0x140064237  mov     [rbp+57h+DestinationString.Buffer], r15
0x14006423b  mov     qword ptr [rbp+57h+GuidString.Length], r15
0x14006423f  mov     [rbp+57h+GuidString.Buffer], r15
0x140064243  mov     qword ptr [rbp+57h+Destination.Length], r15
0x140064247  mov     [rbp+57h+Destination.Buffer], r15
0x14006424b  mov     [rbp+57h+arg_18], r15d
0x14006424f  lea     r12, WPP_RECORDER_INITIALIZED
0x140064256  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14006425d  lea     r13, WPP_9524bb9419753e2807bcae08715ee655_Traceguids
0x140064264  jz      short loc_140064293
0x140064266  mov     rcx, cs:WPP_GLOBAL_Control
0x14006426d  mov     r9d, 5Ah ; 'Z'; int
0x140064273  mov     qword ptr [rsp+100h+var_D0], rdi; char
0x140064278  mov     r8d, 1; int
0x14006427e  mov     qword ptr [rsp+100h+var_D8], rsi; char
0x140064283  mov     dl, 4; int
0x140064285  mov     [rsp+100h+var_E0], r13; struct _GUID *
0x14006428a  mov     rcx, [rcx+40h]; int
0x14006428e  call    WPP_RECORDER_SF_qq
0x140064293  mov     rcx, [rdi+10h]
0x140064297  test    rcx, rcx
0x14006429a  jz      loc_140064503
0x1400642a0  add     rcx, 0FA8h; Guid
0x1400642a7  lea     rdx, [rbp+57h+GuidString]; GuidString
0x1400642ab  call    cs:__imp_RtlStringFromGUID
0x1400642b2  nop     dword ptr [rax+rax+00h]
0x1400642b7  test    eax, eax
0x1400642b9  jnz     loc_1400643F5
0x1400642bf  mov     r8b, 1; AllocateDestinationString
0x1400642c2  lea     rdx, [rbp+57h+GuidString]; SourceString
0x1400642c6  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400642ca  call    cs:__imp_RtlUpcaseUnicodeString
0x1400642d1  nop     dword ptr [rax+rax+00h]
0x1400642d6  lea     rcx, [rbp+57h+GuidString]; UnicodeString
0x1400642da  mov     ebx, eax
0x1400642dc  call    cs:__imp_RtlFreeUnicodeString
0x1400642e3  nop     dword ptr [rax+rax+00h]
0x1400642e8  test    ebx, ebx
0x1400642ea  jnz     loc_1400643F5
0x1400642f0  movzx   eax, word ptr [rsi]
0x1400642f3  mov     ecx, 40h ; '@'
0x1400642f8  add     ax, 2
0x1400642fc  mov     r8d, 2020444Eh
0x140064302  add     ax, cs:?ndisFilterAdapterStr@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING ndisFilterAdapterStr ...
0x140064309  add     ax, cs:?ndisParameterStr@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING ndisParameterStr ...
0x140064310  add     ax, [rbp+57h+DestinationString.Length]
0x140064314  movzx   edx, ax
0x140064317  mov     [rbp+57h+Destination.MaximumLength], dx
0x14006431b  call    cs:__imp_ExAllocatePool2
0x140064322  nop     dword ptr [rax+rax+00h]
0x140064327  mov     [rbp+57h+Destination.Buffer], rax
0x14006432b  test    rax, rax
0x14006432e  jz      loc_14006447B
0x140064334  mov     rdx, rsi; SourceString
0x140064337  lea     rcx, [rbp+57h+Destination]; DestinationString
0x14006433b  mov     ebx, r15d
0x14006433e  call    cs:__imp_RtlCopyUnicodeString
0x140064345  nop     dword ptr [rax+rax+00h]
0x14006434a  lea     rdx, ?ndisParameterStr@@3U_UNICODE_STRING@@A; Source
0x140064351  lea     rcx, [rbp+57h+Destination]; Destination
0x140064355  call    cs:__imp_RtlAppendUnicodeStringToString
0x14006435c  nop     dword ptr [rax+rax+00h]
0x140064361  mov     rdx, [rbp+57h+Destination.Buffer]; Path
0x140064365  mov     ecx, 1; RelativeTo
0x14006436a  call    cs:__imp_RtlCheckRegistryKey
0x140064371  nop     dword ptr [rax+rax+00h]
0x140064376  test    eax, eax
0x140064378  jz      loc_140064495
0x14006437e  lea     rdx, ?ndisFilterAdapterStr@@3U_UNICODE_STRING@@A; Source
0x140064385  lea     rcx, [rbp+57h+Destination]; Destination
0x140064389  call    cs:__imp_RtlAppendUnicodeStringToString
0x140064390  nop     dword ptr [rax+rax+00h]
0x140064395  mov     rdx, [rbp+57h+Destination.Buffer]; Path
0x140064399  mov     ecx, 1; RelativeTo
0x14006439e  call    cs:__imp_RtlCheckRegistryKey
0x1400643a5  nop     dword ptr [rax+rax+00h]
0x1400643aa  test    eax, eax
0x1400643ac  jnz     loc_14006450D
0x1400643b2  lea     rdx, [rbp+57h+DestinationString]; Source
0x1400643b6  lea     rcx, [rbp+57h+Destination]; Destination
0x1400643ba  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400643c1  nop     dword ptr [rax+rax+00h]
0x1400643c6  mov     rdx, [rbp+57h+Destination.Buffer]; Path
0x1400643ca  mov     ecx, 1; RelativeTo
0x1400643cf  call    cs:__imp_RtlCheckRegistryKey
0x1400643d6  nop     dword ptr [rax+rax+00h]
0x1400643db  test    eax, eax
0x1400643dd  jnz     loc_140064534
0x1400643e3  lea     rcx, [rbp+57h+DestinationString]; UnicodeString
0x1400643e7  call    cs:__imp_RtlFreeUnicodeString
0x1400643ee  nop     dword ptr [rax+rax+00h]
0x1400643f3  jmp     short loc_1400643FA
0x1400643f5  mov     ebx, 0C0000001h
0x1400643fa  mov     rcx, [rbp+57h+Destination.Buffer]; P
0x1400643fe  mov     r15, [rsp+100h+var_20]
0x140064406  test    rcx, rcx
0x140064409  jz      short loc_140064419
0x14006440b  xor     edx, edx; Tag
0x14006440d  call    cs:__imp_ExFreePoolWithTag
0x140064414  nop     dword ptr [rax+rax+00h]
0x140064419  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140064420  mov     r12, [rsp+100h+arg_8]
0x140064428  jz      short loc_14006445B
0x14006442a  mov     rcx, cs:WPP_GLOBAL_Control
0x140064431  mov     r9d, 5Bh ; '['; int
0x140064437  mov     dword ptr [rsp+100h+var_C8], ebx; char
0x14006443b  mov     r8d, 1; int
0x140064441  mov     qword ptr [rsp+100h+var_D0], rdi; char
0x140064446  mov     dl, 4; int
0x140064448  mov     qword ptr [rsp+100h+var_D8], rsi; char
0x14006444d  mov     rcx, [rcx+40h]; int
0x140064451  mov     [rsp+100h+var_E0], r13; struct _GUID *
0x140064456  call    WPP_RECORDER_SF_qqL
0x14006445b  mov     r13, [rsp+100h+arg_10]
0x140064463  mov     eax, ebx
0x140064465  mov     rbx, [rsp+100h+arg_0]
0x14006446d  add     rsp, 0E8h
0x140064474  pop     r14
0x140064476  pop     rdi
0x140064477  pop     rsi
0x140064478  pop     rbp
0x140064479  retn
0x14006447b  mov     ebx, 0C000009Ah
0x140064480  jmp     loc_1400643E3
0x140064485  xor     eax, eax
0x140064487  add     rsp, 0E8h
0x14006448e  pop     r14
0x140064490  pop     rdi
0x140064491  pop     rsi
0x140064492  pop     rbp
0x140064493  retn
0x140064495  xor     edx, edx; Val
0x140064497  lea     rcx, [rbp+57h+var_90]; void *
0x14006449b  mov     r8d, 70h ; 'p'; Size
0x1400644a1  call    memset
0x1400644a6  mov     rdx, [rbp+57h+Destination.Buffer]
0x1400644aa  lea     rax, aSkipndisadapte; "SkipNdisAdaptersKeyGeneration"
0x1400644b1  mov     [rbp+57h+var_80], rax
0x1400644b5  lea     r8, [rbp+57h+var_90]
0x1400644b9  lea     rax, [rbp+57h+arg_18]
0x1400644bd  mov     [rbp+57h+var_88], 124h
0x1400644c4  xor     r9d, r9d
0x1400644c7  mov     [rbp+57h+var_78], rax
0x1400644cb  mov     ecx, 1
0x1400644d0  mov     [rbp+57h+var_70], 4000000h
0x1400644d7  mov     [rbp+57h+var_48], r15
0x1400644db  mov     [rsp+100h+var_E0], r15
0x1400644e0  call    cs:__imp_RtlQueryRegistryValuesEx
0x1400644e7  nop     dword ptr [rax+rax+00h]
0x1400644ec  test    eax, eax
0x1400644ee  jnz     loc_14006437E
0x1400644f4  cmp     [rbp+57h+arg_18], 1
0x1400644f8  jz      loc_1400643E3
0x1400644fe  jmp     loc_14006437E
0x140064503  mov     ebx, 0C000000Dh
0x140064508  jmp     loc_1400643FA
0x14006450d  mov     rdx, [rbp+57h+Destination.Buffer]; Path
0x140064511  mov     ecx, 1; RelativeTo
0x140064516  call    cs:__imp_RtlCreateRegistryKey
0x14006451d  nop     dword ptr [rax+rax+00h]
0x140064522  test    eax, eax
0x140064524  jz      loc_1400643B2
0x14006452a  mov     ebx, 0C0000001h
0x14006452f  jmp     loc_1400643E3
0x140064534  mov     rdx, [rbp+57h+Destination.Buffer]; Path
0x140064538  mov     ecx, 1; RelativeTo
0x14006453d  call    cs:__imp_RtlCreateRegistryKey
0x140064544  nop     dword ptr [rax+rax+00h]
0x140064549  test    eax, eax
0x14006454b  jz      loc_1400ED8E6
0x140064551  mov     ebx, 0C0000001h
0x140064556  jmp     loc_1400643E3
0x1400ed8e6  movzx   r9d, r14b; unsigned __int8
0x1400ed8ea  lea     r8, ?ndisFilterAdapterParamsStr@@3U_UNICODE_STRING@@A; struct _UNICODE_STRING *
0x1400ed8f1  lea     rdx, [rbp+57h+Destination]; struct _UNICODE_STRING *
0x1400ed8f5  mov     rcx, rsi; struct _UNICODE_STRING *
0x1400ed8f8  call    ?ndisSetAllFilterDefaultParameters@@YAHPEBU_UNICODE_STRING@@00E@Z; ndisSetAllFilterDefaultParameters(_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,uchar)
0x1400ed8fd  mov     ebx, eax
0x1400ed8ff  jmp     loc_1400643E3
```
