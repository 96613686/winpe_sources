# wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>(void)

- ea: `0x1400058bc`
- end: `0x14000591b`
- name: `??1?$ActivityData@VDirectXDatabaseUpdaterLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ`
- size: `95`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140005884`
- `0x14000e5e0`

## callees

- `0x1400058bc`
- `0x140005bd4`
- `0x14000e734`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400058e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400058e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400058f2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400058f2`

## pseudocode

```c
void __fastcall wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>(
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
  _TlgActivityBase<wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>,70368744177664,5>::~_TlgActivityBase<wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>,70368744177664,5>((_DWORD *)a1);
}

```

## disassembly

```asm
0x1400058bc  mov     [rsp+arg_0], rbx
0x1400058c1  mov     [rsp+arg_8], rsi
0x1400058c6  push    rdi
0x1400058c7  sub     rsp, 20h
0x1400058cb  mov     rdi, rcx
0x1400058ce  add     rcx, 0E8h; this
0x1400058d5  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x1400058da  cmp     byte ptr [rdi+40h], 0
0x1400058de  jz      short loc_1400058FC
0x1400058e0  mov     rbx, [rdi+38h]
0x1400058e4  call    cs:__imp_GetProcessHeap
0x1400058ea  mov     r8, rbx; lpMem
0x1400058ed  xor     edx, edx; dwFlags
0x1400058ef  mov     rcx, rax; hHeap
0x1400058f2  call    cs:__imp_HeapFree
0x1400058f8  mov     byte ptr [rdi+40h], 0
0x1400058fc  mov     rcx, rdi
0x1400058ff  mov     qword ptr [rdi+38h], 0
0x140005907  mov     rbx, [rsp+28h+arg_0]
0x14000590c  mov     rsi, [rsp+28h+arg_8]
0x140005911  add     rsp, 20h
0x140005915  pop     rdi
0x140005916  jmp     ??1?$_TlgActivityBase@V?$ActivityData@VDirectXDatabaseUpdaterLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>,70368744177664,5>::~_TlgActivityBase<wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>,70368744177664,5>(void)
```
