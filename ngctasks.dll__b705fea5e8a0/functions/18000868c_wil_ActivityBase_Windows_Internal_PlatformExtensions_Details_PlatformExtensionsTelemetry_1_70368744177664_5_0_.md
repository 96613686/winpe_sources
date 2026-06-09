# wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>(void)

- ea: `0x18000868c`
- end: `0x1800086ee`
- name: `??1?$ActivityData@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ`
- size: `98`
- prototype: `void __fastcall(__int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800085e8`
- `0x180008ea4`
- `0x18001ecd3`
- `0x18001ee76`

## callees

- `0x18000868c`
- `0x180008a5c`
- `0x180008f8c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800086b7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800086b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800086c5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800086c5`

## pseudocode

```c
void __fastcall wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>(
        __int64 a1)
{
  void *v2; // rbx
  HANDLE ProcessHeap; // rax

  wil::StoredFailureInfo::~StoredFailureInfo((wil::StoredFailureInfo *)(a1 + 80));
  if ( *(_BYTE *)(a1 + 64) )
  {
    v2 = *(void **)(a1 + 56);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
    *(_BYTE *)(a1 + 64) = 0;
  }
  *(_QWORD *)(a1 + 56) = 0;
  _TlgActivityBase<wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>,70368744177664,5>::~_TlgActivityBase<wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>,70368744177664,5>((_DWORD *)a1);
}

```

## disassembly

```asm
0x18000868c  mov     [rsp+arg_8], rbx
0x180008691  mov     [rsp+arg_10], rsi
0x180008696  mov     [rsp+arg_0], rcx
0x18000869b  push    rdi
0x18000869c  sub     rsp, 20h
0x1800086a0  mov     rdi, rcx
0x1800086a3  add     rcx, 50h ; 'P'; this
0x1800086a7  call    ??1StoredFailureInfo@wil@@QEAA@XZ; wil::StoredFailureInfo::~StoredFailureInfo(void)
0x1800086ac  nop
0x1800086ad  cmp     byte ptr [rdi+40h], 0
0x1800086b1  jz      short loc_1800086CF
0x1800086b3  mov     rbx, [rdi+38h]
0x1800086b7  call    cs:__imp_GetProcessHeap
0x1800086bd  mov     r8, rbx; lpMem
0x1800086c0  xor     edx, edx; dwFlags
0x1800086c2  mov     rcx, rax; hHeap
0x1800086c5  call    cs:__imp_HeapFree
0x1800086cb  mov     byte ptr [rdi+40h], 0
0x1800086cf  mov     qword ptr [rdi+38h], 0
0x1800086d7  mov     rcx, rdi
0x1800086da  mov     rbx, [rsp+28h+arg_8]
0x1800086df  mov     rsi, [rsp+28h+arg_10]
0x1800086e4  add     rsp, 20h
0x1800086e8  pop     rdi
0x1800086e9  jmp     ??1?$_TlgActivityBase@V?$ActivityData@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>,70368744177664,5>::~_TlgActivityBase<wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>,70368744177664,5>(void)
```
