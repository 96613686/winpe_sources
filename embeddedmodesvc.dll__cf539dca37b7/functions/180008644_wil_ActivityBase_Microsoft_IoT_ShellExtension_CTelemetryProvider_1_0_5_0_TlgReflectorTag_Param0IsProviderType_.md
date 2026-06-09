# wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>(void)

- ea: `0x180008644`
- end: `0x1800086a3`
- name: `??1?$ActivityData@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ`
- size: `95`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000860c`
- `0x180009564`

## callees

- `0x180006c68`
- `0x180008644`
- `0x1800086d0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000866c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000866c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000867a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000867a`

## pseudocode

```c
void __fastcall wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>(
        __int64 a1)
{
  void *v2; // rbx
  HANDLE ProcessHeap; // rax

  wil::details::shared_buffer::reset((wil::details::shared_buffer *)(a1 + 232));
  if ( *(_BYTE *)(a1 + 64) )
  {
    v2 = *(void **)(a1 + 56);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
    *(_BYTE *)(a1 + 64) = 0;
  }
  *(_QWORD *)(a1 + 56) = 0;
  _TlgActivityBase<wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>,0,5>::~_TlgActivityBase<wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>,0,5>((_DWORD *)a1);
}

```

## disassembly

```asm
0x180008644  mov     [rsp+arg_0], rbx
0x180008649  mov     [rsp+arg_8], rsi
0x18000864e  push    rdi
0x18000864f  sub     rsp, 20h
0x180008653  mov     rdi, rcx
0x180008656  add     rcx, 0E8h; this
0x18000865d  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x180008662  cmp     byte ptr [rdi+40h], 0
0x180008666  jz      short loc_180008684
0x180008668  mov     rbx, [rdi+38h]
0x18000866c  call    cs:__imp_GetProcessHeap
0x180008672  mov     r8, rbx; lpMem
0x180008675  xor     edx, edx; dwFlags
0x180008677  mov     rcx, rax; hHeap
0x18000867a  call    cs:__imp_HeapFree
0x180008680  mov     byte ptr [rdi+40h], 0
0x180008684  mov     rcx, rdi
0x180008687  mov     qword ptr [rdi+38h], 0
0x18000868f  mov     rbx, [rsp+28h+arg_0]
0x180008694  mov     rsi, [rsp+28h+arg_8]
0x180008699  add     rsp, 20h
0x18000869d  pop     rdi
0x18000869e  jmp     ??1?$_TlgActivityBase@V?$ActivityData@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@$0A@$04@@IEAA@XZ; _TlgActivityBase<wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>,0,5>::~_TlgActivityBase<wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>,0,5>(void)
```
