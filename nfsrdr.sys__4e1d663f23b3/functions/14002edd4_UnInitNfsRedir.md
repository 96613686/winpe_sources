# UnInitNfsRedir

- ea: `0x14002edd4`
- end: `0x14002efd7`
- name: `UnInitNfsRedir`
- size: `515`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x14002246c`
- `0x1400232dc`

## callees

- `0x1400159cc`
- `0x1400159fc`
- `0x140016138`
- `0x14002c998`
- `0x14002e7fc`
- `0x14002edd4`
- `0x140036f30`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x14002ee25`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14002ee25`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002ef31`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002ef31`
- `ntoskrnl!LsaDeregisterLogonProcess` at `0x14002ee43`
- `ntoskrnl!LsaDeregisterLogonProcess` at `0x14002ee43`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ef03`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ef46`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ef5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ef70`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ef03`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ef46`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ef5b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ef70`
- `rpcxdr!OncRpcEndpointClose` at `0x14002ee66`
- `rpcxdr!OncRpcEndpointClose` at `0x14002eeae`
- `rpcxdr!OncRpcEndpointClose` at `0x14002ee66`
- `rpcxdr!OncRpcEndpointClose` at `0x14002eeae`

## pseudocode

```c
void __fastcall UnInitNfsRedir(__int64 a1)
{
  _QWORD *v2; // rcx
  _QWORD *v3; // rbx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids);
  MdaUserCacheFinish(a1);
  RtlFreeUnicodeString((PUNICODE_STRING)(a1 + 2080));
  NuiFinish();
  if ( *(_QWORD *)(a1 + 2024) != -1 )
  {
    LsaDeregisterLogonProcess();
    *(_QWORD *)(a1 + 2024) = -1;
  }
  if ( *(_QWORD *)(a1 + 1448)
    && (unsigned int)OncRpcEndpointClose()
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids);
  }
  if ( *(_QWORD *)(a1 + 1440)
    && (unsigned int)OncRpcEndpointClose()
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids);
  }
  NfsFreeCodePageTables(a1);
  v2 = *(_QWORD **)(a1 + 2008);
  if ( v2 )
  {
    do
    {
      v3 = (_QWORD *)*v2;
      ExFreePoolWithTag(v2, 0);
      *(_QWORD *)(a1 + 2008) = v3;
      v2 = v3;
    }
    while ( v3 );
  }
  NfsRdrCryptoTeardown(a1 + 1352);
  ExDeleteResourceLite(*(PERESOURCE *)(a1 + 1464));
  ExFreePoolWithTag(*(PVOID *)(a1 + 1984), 0);
  ExFreePoolWithTag(*(PVOID *)(a1 + 1992), 0);
  ExFreePoolWithTag(*(PVOID *)(a1 + 1464), 0);
  *(_QWORD *)(a1 + 1984) = 0;
  *(_QWORD *)(a1 + 1992) = 0;
  *(_QWORD *)(a1 + 1464) = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids);
}

```

## disassembly

```asm
0x14002edd4  mov     [rsp+arg_0], rbx
0x14002edd9  mov     [rsp+arg_8], rdi
0x14002edde  push    r14
0x14002ede0  sub     rsp, 20h
0x14002ede4  mov     rdi, rcx
0x14002ede7  mov     rcx, cs:WPP_GLOBAL_Control
0x14002edee  lea     r14, WPP_GLOBAL_Control
0x14002edf5  cmp     rcx, r14
0x14002edf8  jz      short loc_14002EE16
0x14002edfa  mov     eax, [rcx+2Ch]
0x14002edfd  test    al, 8
0x14002edff  jz      short loc_14002EE16
0x14002ee01  mov     rcx, [rcx+18h]
0x14002ee05  lea     r8, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids
0x14002ee0c  mov     edx, 24h ; '$'
0x14002ee11  call    WPP_SF_
0x14002ee16  mov     rcx, rdi
0x14002ee19  call    MdaUserCacheFinish
0x14002ee1e  lea     rcx, [rdi+820h]; UnicodeString
0x14002ee25  call    cs:__imp_RtlFreeUnicodeString
0x14002ee2c  nop     dword ptr [rax+rax+00h]
0x14002ee31  call    NuiFinish
0x14002ee36  mov     rcx, [rdi+7E8h]
0x14002ee3d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14002ee41  jz      short loc_14002EE5A
0x14002ee43  call    cs:__imp_LsaDeregisterLogonProcess
0x14002ee4a  nop     dword ptr [rax+rax+00h]
0x14002ee4f  mov     qword ptr [rdi+7E8h], 0FFFFFFFFFFFFFFFFh
0x14002ee5a  mov     rcx, [rdi+5A8h]
0x14002ee61  test    rcx, rcx
0x14002ee64  jz      short loc_14002EEA2
0x14002ee66  call    cs:__imp_OncRpcEndpointClose
0x14002ee6d  nop     dword ptr [rax+rax+00h]
0x14002ee72  test    eax, eax
0x14002ee74  jz      short loc_14002EEA2
0x14002ee76  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ee7d  cmp     rcx, r14
0x14002ee80  jz      short loc_14002EEA2
0x14002ee82  mov     edx, [rcx+2Ch]
0x14002ee85  test    dl, 1
0x14002ee88  jz      short loc_14002EEA2
0x14002ee8a  mov     rcx, [rcx+18h]
0x14002ee8e  lea     r8, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids
0x14002ee95  mov     edx, 25h ; '%'
0x14002ee9a  mov     r9d, eax
0x14002ee9d  call    WPP_SF_d
0x14002eea2  mov     rcx, [rdi+5A0h]
0x14002eea9  test    rcx, rcx
0x14002eeac  jz      short loc_14002EEEA
0x14002eeae  call    cs:__imp_OncRpcEndpointClose
0x14002eeb5  nop     dword ptr [rax+rax+00h]
0x14002eeba  test    eax, eax
0x14002eebc  jz      short loc_14002EEEA
0x14002eebe  mov     rcx, cs:WPP_GLOBAL_Control
0x14002eec5  cmp     rcx, r14
0x14002eec8  jz      short loc_14002EEEA
0x14002eeca  mov     edx, [rcx+2Ch]
0x14002eecd  test    dl, 1
0x14002eed0  jz      short loc_14002EEEA
0x14002eed2  mov     rcx, [rcx+18h]
0x14002eed6  lea     r8, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids
0x14002eedd  mov     edx, 26h ; '&'
0x14002eee2  mov     r9d, eax
0x14002eee5  call    WPP_SF_d
0x14002eeea  mov     rcx, rdi
0x14002eeed  call    NfsFreeCodePageTables
0x14002eef2  mov     rcx, [rdi+7D8h]; P
0x14002eef9  test    rcx, rcx
0x14002eefc  jz      short loc_14002EF1E
0x14002eefe  mov     rbx, [rcx]
0x14002ef01  xor     edx, edx; Tag
0x14002ef03  call    cs:__imp_ExFreePoolWithTag
0x14002ef0a  nop     dword ptr [rax+rax+00h]
0x14002ef0f  mov     [rdi+7D8h], rbx
0x14002ef16  mov     rcx, rbx
0x14002ef19  test    rbx, rbx
0x14002ef1c  jnz     short loc_14002EEFE
0x14002ef1e  lea     rcx, [rdi+548h]
0x14002ef25  call    NfsRdrCryptoTeardown
0x14002ef2a  mov     rcx, [rdi+5B8h]; Resource
0x14002ef31  call    cs:__imp_ExDeleteResourceLite
0x14002ef38  nop     dword ptr [rax+rax+00h]
0x14002ef3d  mov     rcx, [rdi+7C0h]; P
0x14002ef44  xor     edx, edx; Tag
0x14002ef46  call    cs:__imp_ExFreePoolWithTag
0x14002ef4d  nop     dword ptr [rax+rax+00h]
0x14002ef52  mov     rcx, [rdi+7C8h]; P
0x14002ef59  xor     edx, edx; Tag
0x14002ef5b  call    cs:__imp_ExFreePoolWithTag
0x14002ef62  nop     dword ptr [rax+rax+00h]
0x14002ef67  mov     rcx, [rdi+5B8h]; P
0x14002ef6e  xor     edx, edx; Tag
0x14002ef70  call    cs:__imp_ExFreePoolWithTag
0x14002ef77  nop     dword ptr [rax+rax+00h]
0x14002ef7c  mov     qword ptr [rdi+7C0h], 0
0x14002ef87  mov     qword ptr [rdi+7C8h], 0
0x14002ef92  mov     qword ptr [rdi+5B8h], 0
0x14002ef9d  mov     rcx, cs:WPP_GLOBAL_Control
0x14002efa4  cmp     rcx, r14
0x14002efa7  jz      short loc_14002EFC5
0x14002efa9  mov     eax, [rcx+2Ch]
0x14002efac  test    al, 8
0x14002efae  jz      short loc_14002EFC5
0x14002efb0  mov     rcx, [rcx+18h]
0x14002efb4  lea     r8, WPP_a72d5c9d96ac38aede72f4cc5ca0ad09_Traceguids
0x14002efbb  mov     edx, 27h ; '''
0x14002efc0  call    WPP_SF_
0x14002efc5  mov     rbx, [rsp+28h+arg_0]
0x14002efca  mov     rdi, [rsp+28h+arg_8]
0x14002efcf  add     rsp, 20h
0x14002efd3  pop     r14
0x14002efd5  retn
```
