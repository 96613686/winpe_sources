# ndisCreateFilterAdapterRegistry(_UNICODE_STRING const *,_NDIS_MINIPORT_BLOCK *,uchar)

- ea: `0x140069920`
- end: `0x140069c9b`
- name: `?ndisCreateFilterAdapterRegistry@@YAHPEBU_UNICODE_STRING@@PEAU_NDIS_MINIPORT_BLOCK@@E@Z`
- size: `891`
- prototype: `__int64 __fastcall(const struct _UNICODE_STRING *, struct _NDIS_MINIPORT_BLOCK *, unsigned __int8)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140186f10`

## callees

- `0x14000dd10`
- `0x1400100f0`
- `0x140069920`
- `0x14009b448`
- `0x1400eb7c0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140069a7e`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140069a7e`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140069a95`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140069ac9`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140069afa`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140069a95`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140069ac9`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140069afa`
- `ntoskrnl!RtlStringFromGUID` at `0x1400699eb`
- `ntoskrnl!RtlStringFromGUID` at `0x1400699eb`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140069a1c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140069b27`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140069a1c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140069b27`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140069c20`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x140069c20`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140069a0a`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140069a0a`
- `ntoskrnl!RtlCheckRegistryKey` at `0x140069aaa`
- `ntoskrnl!RtlCheckRegistryKey` at `0x140069ade`
- `ntoskrnl!RtlCheckRegistryKey` at `0x140069b0f`
- `ntoskrnl!RtlCheckRegistryKey` at `0x140069aaa`
- `ntoskrnl!RtlCheckRegistryKey` at `0x140069ade`
- `ntoskrnl!RtlCheckRegistryKey` at `0x140069b0f`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x14006993c`
- `ntoskrnl!RtlIsStateSeparationEnabled` at `0x14006993c`
- `ntoskrnl!RtlCreateRegistryKey` at `0x140069c56`
- `ntoskrnl!RtlCreateRegistryKey` at `0x140069c7d`
- `ntoskrnl!RtlCreateRegistryKey` at `0x140069c56`
- `ntoskrnl!RtlCreateRegistryKey` at `0x140069c7d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140069b4d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140069b4d`
- `ntoskrnl!ExAllocatePool2` at `0x140069a5b`
- `ntoskrnl!ExAllocatePool2` at `0x140069a5b`

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
0x140069920  push    rbp
0x140069922  push    rsi
0x140069923  push    rdi
0x140069924  push    r14
0x140069926  lea     rbp, [rsp-3Fh]
0x14006992b  sub     rsp, 0E8h
0x140069932  movzx   r14d, r8b
0x140069936  mov     rdi, rdx
0x140069939  mov     rsi, rcx
0x14006993c  call    cs:__imp_RtlIsStateSeparationEnabled
0x140069943  nop     dword ptr [rax+rax+00h]
0x140069948  test    al, al
0x14006994a  jnz     loc_140069BC5
0x140069950  mov     [rsp+100h+arg_0], rbx
0x140069958  mov     [rsp+100h+arg_8], r12
0x140069960  mov     [rsp+100h+arg_10], r13
0x140069968  mov     [rsp+100h+var_20], r15
0x140069970  xor     r15d, r15d
0x140069973  mov     qword ptr [rbp+57h+DestinationString.Length], r15
0x140069977  mov     [rbp+57h+DestinationString.Buffer], r15
0x14006997b  mov     qword ptr [rbp+57h+GuidString.Length], r15
0x14006997f  mov     [rbp+57h+GuidString.Buffer], r15
0x140069983  mov     qword ptr [rbp+57h+Destination.Length], r15
0x140069987  mov     [rbp+57h+Destination.Buffer], r15
0x14006998b  mov     [rbp+57h+arg_18], r15d
0x14006998f  lea     r12, WPP_RECORDER_INITIALIZED
0x140069996  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14006999d  lea     r13, WPP_9524bb9419753e2807bcae08715ee655_Traceguids
0x1400699a4  jz      short loc_1400699D3
0x1400699a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400699ad  mov     r9d, 5Ah ; 'Z'; int
0x1400699b3  mov     qword ptr [rsp+100h+var_D0], rdi; char
0x1400699b8  mov     r8d, 1; int
0x1400699be  mov     qword ptr [rsp+100h+var_D8], rsi; char
0x1400699c3  mov     dl, 4; int
0x1400699c5  mov     [rsp+100h+var_E0], r13; struct _GUID *
0x1400699ca  mov     rcx, [rcx+40h]; int
0x1400699ce  call    WPP_RECORDER_SF_qq
0x1400699d3  mov     rcx, [rdi+10h]
0x1400699d7  test    rcx, rcx
0x1400699da  jz      loc_140069C43
0x1400699e0  add     rcx, 0FA8h; Guid
0x1400699e7  lea     rdx, [rbp+57h+GuidString]; GuidString
0x1400699eb  call    cs:__imp_RtlStringFromGUID
0x1400699f2  nop     dword ptr [rax+rax+00h]
0x1400699f7  test    eax, eax
0x1400699f9  jnz     loc_140069B35
0x1400699ff  mov     r8b, 1; AllocateDestinationString
0x140069a02  lea     rdx, [rbp+57h+GuidString]; SourceString
0x140069a06  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140069a0a  call    cs:__imp_RtlUpcaseUnicodeString
0x140069a11  nop     dword ptr [rax+rax+00h]
0x140069a16  lea     rcx, [rbp+57h+GuidString]; UnicodeString
0x140069a1a  mov     ebx, eax
0x140069a1c  call    cs:__imp_RtlFreeUnicodeString
0x140069a23  nop     dword ptr [rax+rax+00h]
0x140069a28  test    ebx, ebx
0x140069a2a  jnz     loc_140069B35
0x140069a30  movzx   eax, word ptr [rsi]
0x140069a33  mov     ecx, 40h ; '@'
0x140069a38  add     ax, 2
0x140069a3c  mov     r8d, 2020444Eh
0x140069a42  add     ax, cs:?ndisFilterAdapterStr@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING ndisFilterAdapterStr ...
0x140069a49  add     ax, cs:?ndisParameterStr@@3U_UNICODE_STRING@@A.Length; _UNICODE_STRING ndisParameterStr ...
0x140069a50  add     ax, [rbp+57h+DestinationString.Length]
0x140069a54  movzx   edx, ax
0x140069a57  mov     [rbp+57h+Destination.MaximumLength], dx
0x140069a5b  call    cs:__imp_ExAllocatePool2
0x140069a62  nop     dword ptr [rax+rax+00h]
0x140069a67  mov     [rbp+57h+Destination.Buffer], rax
0x140069a6b  test    rax, rax
0x140069a6e  jz      loc_140069BBB
0x140069a74  mov     rdx, rsi; SourceString
0x140069a77  lea     rcx, [rbp+57h+Destination]; DestinationString
0x140069a7b  mov     ebx, r15d
0x140069a7e  call    cs:__imp_RtlCopyUnicodeString
0x140069a85  nop     dword ptr [rax+rax+00h]
0x140069a8a  lea     rdx, ?ndisParameterStr@@3U_UNICODE_STRING@@A; Source
0x140069a91  lea     rcx, [rbp+57h+Destination]; Destination
0x140069a95  call    cs:__imp_RtlAppendUnicodeStringToString
0x140069a9c  nop     dword ptr [rax+rax+00h]
0x140069aa1  mov     rdx, [rbp+57h+Destination.Buffer]; Path
0x140069aa5  mov     ecx, 1; RelativeTo
0x140069aaa  call    cs:__imp_RtlCheckRegistryKey
0x140069ab1  nop     dword ptr [rax+rax+00h]
0x140069ab6  test    eax, eax
0x140069ab8  jz      loc_140069BD5
0x140069abe  lea     rdx, ?ndisFilterAdapterStr@@3U_UNICODE_STRING@@A; Source
0x140069ac5  lea     rcx, [rbp+57h+Destination]; Destination
0x140069ac9  call    cs:__imp_RtlAppendUnicodeStringToString
0x140069ad0  nop     dword ptr [rax+rax+00h]
0x140069ad5  mov     rdx, [rbp+57h+Destination.Buffer]; Path
0x140069ad9  mov     ecx, 1; RelativeTo
0x140069ade  call    cs:__imp_RtlCheckRegistryKey
0x140069ae5  nop     dword ptr [rax+rax+00h]
0x140069aea  test    eax, eax
0x140069aec  jnz     loc_140069C4D
0x140069af2  lea     rdx, [rbp+57h+DestinationString]; Source
0x140069af6  lea     rcx, [rbp+57h+Destination]; Destination
0x140069afa  call    cs:__imp_RtlAppendUnicodeStringToString
0x140069b01  nop     dword ptr [rax+rax+00h]
0x140069b06  mov     rdx, [rbp+57h+Destination.Buffer]; Path
0x140069b0a  mov     ecx, 1; RelativeTo
0x140069b0f  call    cs:__imp_RtlCheckRegistryKey
0x140069b16  nop     dword ptr [rax+rax+00h]
0x140069b1b  test    eax, eax
0x140069b1d  jnz     loc_140069C74
0x140069b23  lea     rcx, [rbp+57h+DestinationString]; UnicodeString
0x140069b27  call    cs:__imp_RtlFreeUnicodeString
0x140069b2e  nop     dword ptr [rax+rax+00h]
0x140069b33  jmp     short loc_140069B3A
0x140069b35  mov     ebx, 0C0000001h
0x140069b3a  mov     rcx, [rbp+57h+Destination.Buffer]; P
0x140069b3e  mov     r15, [rsp+100h+var_20]
0x140069b46  test    rcx, rcx
0x140069b49  jz      short loc_140069B59
0x140069b4b  xor     edx, edx; Tag
0x140069b4d  call    cs:__imp_ExFreePoolWithTag
0x140069b54  nop     dword ptr [rax+rax+00h]
0x140069b59  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140069b60  mov     r12, [rsp+100h+arg_8]
0x140069b68  jz      short loc_140069B9B
0x140069b6a  mov     rcx, cs:WPP_GLOBAL_Control
0x140069b71  mov     r9d, 5Bh ; '['; int
0x140069b77  mov     dword ptr [rsp+100h+var_C8], ebx; char
0x140069b7b  mov     r8d, 1; int
0x140069b81  mov     qword ptr [rsp+100h+var_D0], rdi; char
0x140069b86  mov     dl, 4; int
0x140069b88  mov     qword ptr [rsp+100h+var_D8], rsi; char
0x140069b8d  mov     rcx, [rcx+40h]; int
0x140069b91  mov     [rsp+100h+var_E0], r13; struct _GUID *
0x140069b96  call    WPP_RECORDER_SF_qqL
0x140069b9b  mov     r13, [rsp+100h+arg_10]
0x140069ba3  mov     eax, ebx
0x140069ba5  mov     rbx, [rsp+100h+arg_0]
0x140069bad  add     rsp, 0E8h
0x140069bb4  pop     r14
0x140069bb6  pop     rdi
0x140069bb7  pop     rsi
0x140069bb8  pop     rbp
0x140069bb9  retn
0x140069bbb  mov     ebx, 0C000009Ah
0x140069bc0  jmp     loc_140069B23
0x140069bc5  xor     eax, eax
0x140069bc7  add     rsp, 0E8h
0x140069bce  pop     r14
0x140069bd0  pop     rdi
0x140069bd1  pop     rsi
0x140069bd2  pop     rbp
0x140069bd3  retn
0x140069bd5  xor     edx, edx; Val
0x140069bd7  lea     rcx, [rbp+57h+var_90]; void *
0x140069bdb  mov     r8d, 70h ; 'p'; Size
0x140069be1  call    memset
0x140069be6  mov     rdx, [rbp+57h+Destination.Buffer]
0x140069bea  lea     rax, aSkipndisadapte; "SkipNdisAdaptersKeyGeneration"
0x140069bf1  mov     [rbp+57h+var_80], rax
0x140069bf5  lea     r8, [rbp+57h+var_90]
0x140069bf9  lea     rax, [rbp+57h+arg_18]
0x140069bfd  mov     [rbp+57h+var_88], 124h
0x140069c04  xor     r9d, r9d
0x140069c07  mov     [rbp+57h+var_78], rax
0x140069c0b  mov     ecx, 1
0x140069c10  mov     [rbp+57h+var_70], 4000000h
0x140069c17  mov     [rbp+57h+var_48], r15
0x140069c1b  mov     [rsp+100h+var_E0], r15
0x140069c20  call    cs:__imp_RtlQueryRegistryValuesEx
0x140069c27  nop     dword ptr [rax+rax+00h]
0x140069c2c  test    eax, eax
0x140069c2e  jnz     loc_140069ABE
0x140069c34  cmp     [rbp+57h+arg_18], 1
0x140069c38  jz      loc_140069B23
0x140069c3e  jmp     loc_140069ABE
0x140069c43  mov     ebx, 0C000000Dh
0x140069c48  jmp     loc_140069B3A
0x140069c4d  mov     rdx, [rbp+57h+Destination.Buffer]; Path
0x140069c51  mov     ecx, 1; RelativeTo
0x140069c56  call    cs:__imp_RtlCreateRegistryKey
0x140069c5d  nop     dword ptr [rax+rax+00h]
0x140069c62  test    eax, eax
0x140069c64  jz      loc_140069AF2
0x140069c6a  mov     ebx, 0C0000001h
0x140069c6f  jmp     loc_140069B23
0x140069c74  mov     rdx, [rbp+57h+Destination.Buffer]; Path
0x140069c78  mov     ecx, 1; RelativeTo
0x140069c7d  call    cs:__imp_RtlCreateRegistryKey
0x140069c84  nop     dword ptr [rax+rax+00h]
0x140069c89  test    eax, eax
0x140069c8b  jz      loc_1400F2BC0
0x140069c91  mov     ebx, 0C0000001h
0x140069c96  jmp     loc_140069B23
0x1400f2bc0  movzx   r9d, r14b; unsigned __int8
0x1400f2bc4  lea     r8, ?ndisFilterAdapterParamsStr@@3U_UNICODE_STRING@@A; struct _UNICODE_STRING *
0x1400f2bcb  lea     rdx, [rbp+57h+Destination]; struct _UNICODE_STRING *
0x1400f2bcf  mov     rcx, rsi; struct _UNICODE_STRING *
0x1400f2bd2  call    ?ndisSetAllFilterDefaultParameters@@YAHPEBU_UNICODE_STRING@@00E@Z; ndisSetAllFilterDefaultParameters(_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,uchar)
0x1400f2bd7  mov     ebx, eax
0x1400f2bd9  jmp     loc_140069B23
```
