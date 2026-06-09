# CscStringTableInitialize

- ea: `0x140051e50`
- end: `0x140051f7b`
- name: `CscStringTableInitialize`
- size: `299`
- prototype: `__int64 __fastcall(PERESOURCE Resource)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14005015c`

## callees

- `0x140018fd0`
- `0x14002f440`
- `0x140051e50`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x140051f1d`
- `ntoskrnl!ExDeleteResourceLite` at `0x140051f1d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140051e78`
- `ntoskrnl!RtlInitUnicodeString` at `0x140051e78`
- `ntoskrnl!ExInitializeResourceLite` at `0x140051eeb`
- `ntoskrnl!ExInitializeResourceLite` at `0x140051f08`
- `ntoskrnl!ExInitializeResourceLite` at `0x140051eeb`
- `ntoskrnl!ExInitializeResourceLite` at `0x140051f08`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140051eb2`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140051edc`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140051eb2`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140051edc`

## pseudocode

```c
__int64 __fastcall CscStringTableInitialize(PERESOURCE Resource)
{
  NTSTATUS v2; // ebx

  memset(Resource, 0, 0x1C8u);
  RtlInitUnicodeString((PUNICODE_STRING)&Resource[2].SystemResourcesList.Blink, L",;");
  HIDWORD(Resource[2].SystemResourcesList.Flink) = 1129530196;
  RtlInitializeGenericTableAvl(
    (PRTL_AVL_TABLE)&Resource[2].ActiveCount,
    (PRTL_AVL_COMPARE_ROUTINE)CscStringTablepCompare,
    CscStringTablepAllocateMemory,
    CscStringTablepFree,
    Resource);
  RtlInitializeGenericTableAvl(
    (PRTL_AVL_TABLE)&Resource[3].ActiveCount,
    (PRTL_AVL_COMPARE_ROUTINE)CscStringTablepCompare,
    CscStringTablepAllocateMemory,
    CscStringTablepFree,
    Resource);
  v2 = ExInitializeResourceLite(Resource);
  if ( v2 >= 0 )
  {
    v2 = ExInitializeResourceLite(Resource + 1);
    if ( v2 < 0 )
      ExDeleteResourceLite(Resource);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_qDD(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_b518ab25fbea3b6d6a0c343b200072f4_Traceguids);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140051e50  mov     [rsp+arg_0], rbx
0x140051e55  push    rdi
0x140051e56  sub     rsp, 30h
0x140051e5a  xor     edx, edx; Val
0x140051e5c  mov     r8d, 1C8h; Size
0x140051e62  mov     rdi, rcx
0x140051e65  call    memset
0x140051e6a  lea     rcx, [rdi+0D8h]; DestinationString
0x140051e71  lea     rdx, asc_140031BB0; ",;"
0x140051e78  call    cs:__imp_RtlInitUnicodeString
0x140051e7f  nop     dword ptr [rax+rax+00h]
0x140051e84  lea     rbx, [rdi+0E8h]
0x140051e8b  mov     dword ptr [rdi+0D4h], 43534354h
0x140051e95  mov     rcx, rbx; Table
0x140051e98  mov     [rsp+38h+TableContext], rdi; TableContext
0x140051e9d  lea     r9, CscStringTablepFree; FreeRoutine
0x140051ea4  lea     r8, CscStringTablepAllocateMemory; AllocateRoutine
0x140051eab  lea     rdx, CscStringTablepCompare; CompareRoutine
0x140051eb2  call    cs:__imp_RtlInitializeGenericTableAvl
0x140051eb9  nop     dword ptr [rax+rax+00h]
0x140051ebe  lea     rcx, [rbx+68h]; Table
0x140051ec2  mov     [rsp+38h+TableContext], rdi; TableContext
0x140051ec7  lea     r9, CscStringTablepFree; FreeRoutine
0x140051ece  lea     r8, CscStringTablepAllocateMemory; AllocateRoutine
0x140051ed5  lea     rdx, CscStringTablepCompare; CompareRoutine
0x140051edc  call    cs:__imp_RtlInitializeGenericTableAvl
0x140051ee3  nop     dword ptr [rax+rax+00h]
0x140051ee8  mov     rcx, rdi; Resource
0x140051eeb  call    cs:__imp_ExInitializeResourceLite
0x140051ef2  nop     dword ptr [rax+rax+00h]
0x140051ef7  mov     ebx, eax
0x140051ef9  test    eax, eax
0x140051efb  jns     short loc_140051F04
0x140051efd  mov     ecx, 24Ah
0x140051f02  jmp     short loc_140051F32
0x140051f04  lea     rcx, [rdi+68h]; Resource
0x140051f08  call    cs:__imp_ExInitializeResourceLite
0x140051f0f  nop     dword ptr [rax+rax+00h]
0x140051f14  mov     ebx, eax
0x140051f16  test    eax, eax
0x140051f18  jns     short loc_140051F30
0x140051f1a  mov     rcx, rdi; Resource
0x140051f1d  call    cs:__imp_ExDeleteResourceLite
0x140051f24  nop     dword ptr [rax+rax+00h]
0x140051f29  mov     ecx, 250h
0x140051f2e  jmp     short loc_140051F32
0x140051f30  xor     ecx, ecx
0x140051f32  mov     r10, cs:WPP_GLOBAL_Control
0x140051f39  lea     rax, WPP_GLOBAL_Control
0x140051f40  cmp     r10, rax
0x140051f43  jz      short loc_140051F6D
0x140051f45  mov     eax, [r10+2Ch]
0x140051f49  test    al, 40h
0x140051f4b  jz      short loc_140051F6D
0x140051f4d  mov     [rsp+38h+var_10], ecx
0x140051f51  lea     r8, WPP_b518ab25fbea3b6d6a0c343b200072f4_Traceguids
0x140051f58  mov     rcx, [r10+18h]
0x140051f5c  mov     edx, 0Ah
0x140051f61  mov     r9, rdi
0x140051f64  mov     dword ptr [rsp+38h+TableContext], ebx
0x140051f68  call    WPP_SF_qDD
0x140051f6d  mov     eax, ebx
0x140051f6f  mov     rbx, [rsp+38h+arg_0]
0x140051f74  add     rsp, 30h
0x140051f78  pop     rdi
0x140051f79  retn
```
