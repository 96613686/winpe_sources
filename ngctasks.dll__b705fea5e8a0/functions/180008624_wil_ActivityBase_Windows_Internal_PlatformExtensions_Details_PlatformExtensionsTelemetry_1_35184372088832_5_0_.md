# wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>(void)

- ea: `0x180008624`
- end: `0x180008686`
- name: `??1?$ActivityData@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ`
- size: `98`
- prototype: `void __fastcall(__int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800085ac`
- `0x180008e88`
- `0x18001ec34`
- `0x18001ee2e`

## callees

- `0x180008624`
- `0x180008a1c`
- `0x180008f8c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000864f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000864f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000865d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000865d`

## pseudocode

```c
void __fastcall wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>(
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
  _TlgActivityBase<wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>,35184372088832,5>::~_TlgActivityBase<wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>,35184372088832,5>((_DWORD *)a1);
}

```

## disassembly

```asm
0x180008624  mov     [rsp+arg_8], rbx
0x180008629  mov     [rsp+arg_10], rsi
0x18000862e  mov     [rsp+arg_0], rcx
0x180008633  push    rdi
0x180008634  sub     rsp, 20h
0x180008638  mov     rdi, rcx
0x18000863b  add     rcx, 50h ; 'P'; this
0x18000863f  call    ??1StoredFailureInfo@wil@@QEAA@XZ; wil::StoredFailureInfo::~StoredFailureInfo(void)
0x180008644  nop
0x180008645  cmp     byte ptr [rdi+40h], 0
0x180008649  jz      short loc_180008667
0x18000864b  mov     rbx, [rdi+38h]
0x18000864f  call    cs:__imp_GetProcessHeap
0x180008655  mov     r8, rbx; lpMem
0x180008658  xor     edx, edx; dwFlags
0x18000865a  mov     rcx, rax; hHeap
0x18000865d  call    cs:__imp_HeapFree
0x180008663  mov     byte ptr [rdi+40h], 0
0x180008667  mov     qword ptr [rdi+38h], 0
0x18000866f  mov     rcx, rdi
0x180008672  mov     rbx, [rsp+28h+arg_8]
0x180008677  mov     rsi, [rsp+28h+arg_10]
0x18000867c  add     rsp, 20h
0x180008680  pop     rdi
0x180008681  jmp     ??1?$_TlgActivityBase@V?$ActivityData@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@$0CAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>,35184372088832,5>::~_TlgActivityBase<wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,_TlgReflectorTag_Param0IsProviderType>,35184372088832,5>(void)
```
