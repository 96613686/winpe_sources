# wil::ActivityBase<DXGIAdapterCacheLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DXGIAdapterCacheLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)

- ea: `0x140005f4c`
- end: `0x140005fbd`
- name: `??1?$ActivityBase@VDXGIAdapterCacheLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ`
- size: `113`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14000672c`

## callees

- `0x140002578`
- `0x140005f4c`
- `0x140005fc4`
- `0x140006c50`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<DXGIAdapterCacheLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DXGIAdapterCacheLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
        __int64 a1)
{
  volatile signed __int32 *v2; // rcx
  char *v3; // rdi

  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
  v2 = *(volatile signed __int32 **)(a1 + 280);
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2, 0xFFFFFFFF) == 1 )
    {
      v3 = *(char **)(a1 + 280);
      if ( v3 )
      {
        wil::ActivityBase<DXGIAdapterCacheLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DXGIAdapterCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<DXGIAdapterCacheLogging,_TlgReflectorTag_Param0IsProviderType>(v3 + 8);
        operator delete(v3, 0x110u);
      }
    }
    *(_QWORD *)(a1 + 280) = 0;
  }
  return wil::ActivityBase<DXGIAdapterCacheLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DXGIAdapterCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<DXGIAdapterCacheLogging,_TlgReflectorTag_Param0IsProviderType>(a1 + 8);
}

```

## disassembly

```asm
0x140005f4c  mov     [rsp+arg_0], rbx
0x140005f51  push    rdi
0x140005f52  sub     rsp, 20h
0x140005f56  mov     rbx, rcx
0x140005f59  add     rcx, 120h; this
0x140005f60  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x140005f65  mov     rcx, [rbx+118h]
0x140005f6c  test    rcx, rcx
0x140005f6f  jz      short loc_140005FAA
0x140005f71  or      eax, 0FFFFFFFFh
0x140005f74  lock xadd [rcx], eax
0x140005f78  cmp     eax, 1
0x140005f7b  jnz     short loc_140005F9F
0x140005f7d  mov     rdi, [rbx+118h]
0x140005f84  test    rdi, rdi
0x140005f87  jz      short loc_140005F9F
0x140005f89  lea     rcx, [rdi+8]
0x140005f8d  call    ??1?$ActivityData@VDXGIAdapterCacheLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDXGIAdapterCacheLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DXGIAdapterCacheLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DXGIAdapterCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<DXGIAdapterCacheLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x140005f92  mov     edx, 110h; unsigned __int64
0x140005f97  mov     rcx, rdi; void *
0x140005f9a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140005f9f  mov     qword ptr [rbx+118h], 0
0x140005faa  lea     rcx, [rbx+8]
0x140005fae  mov     rbx, [rsp+28h+arg_0]
0x140005fb3  add     rsp, 20h
0x140005fb7  pop     rdi
0x140005fb8  jmp     ??1?$ActivityData@VDXGIAdapterCacheLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDXGIAdapterCacheLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DXGIAdapterCacheLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DXGIAdapterCacheLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<DXGIAdapterCacheLogging,_TlgReflectorTag_Param0IsProviderType>(void)
```
