# wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>(void)

- ea: `0x180010404`
- end: `0x180010463`
- name: `??1?$ActivityData@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ`
- size: `95`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800103cc`
- `0x18001506c`

## callees

- `0x180006c68`
- `0x180010404`
- `0x1800104d0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001042c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001042c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001043a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001043a`

## pseudocode

```c
void __fastcall wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>(
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
  _TlgActivityBase<wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>,35184372088832,5>::~_TlgActivityBase<wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>,35184372088832,5>((_DWORD *)a1);
}

```

## disassembly

```asm
0x180010404  mov     [rsp+arg_0], rbx
0x180010409  mov     [rsp+arg_8], rsi
0x18001040e  push    rdi
0x18001040f  sub     rsp, 20h
0x180010413  mov     rdi, rcx
0x180010416  add     rcx, 0E8h; this
0x18001041d  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x180010422  cmp     byte ptr [rdi+40h], 0
0x180010426  jz      short loc_180010444
0x180010428  mov     rbx, [rdi+38h]
0x18001042c  call    cs:__imp_GetProcessHeap
0x180010432  mov     r8, rbx; lpMem
0x180010435  xor     edx, edx; dwFlags
0x180010437  mov     rcx, rax; hHeap
0x18001043a  call    cs:__imp_HeapFree
0x180010440  mov     byte ptr [rdi+40h], 0
0x180010444  mov     rcx, rdi
0x180010447  mov     qword ptr [rdi+38h], 0
0x18001044f  mov     rbx, [rsp+28h+arg_0]
0x180010454  mov     rsi, [rsp+28h+arg_8]
0x180010459  add     rsp, 20h
0x18001045d  pop     rdi
0x18001045e  jmp     ??1?$_TlgActivityBase@V?$ActivityData@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VCTelemetryProvider@ShellExtension@IoT@Microsoft@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@$0CAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>,35184372088832,5>::~_TlgActivityBase<wil::ActivityBase<Microsoft::IoT::ShellExtension::CTelemetryProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<Microsoft::IoT::ShellExtension::CTelemetryProvider,_TlgReflectorTag_Param0IsProviderType>,35184372088832,5>(void)
```
