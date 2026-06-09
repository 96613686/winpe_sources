# Windows::Internal::ComTaskPool::QueueTask__lambda_080f8fc71c33ea6c39c72d91d5b2a0aa___

- ea: `0x180028b98`
- end: `0x180028c18`
- name: `Windows::Internal::ComTaskPool::QueueTask__lambda_080f8fc71c33ea6c39c72d91d5b2a0aa___`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002bc7c`

## callees

- `0x18002891c`
- `0x180028b98`
- `0x18002da30`
- `0x180040010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180028bee`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180028bee`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTask__lambda_080f8fc71c33ea6c39c72d91d5b2a0aa___(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4)
{
  __int64 *v5; // rax
  __int64 v6; // rbx
  volatile signed __int32 *v7; // rcx
  unsigned int v8; // edi
  volatile signed __int32 *v10; // [rsp+30h] [rbp-18h] BYREF

  v5 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_080f8fc71c33ea6c39c72d91d5b2a0aa_____lambda_080f8fc71c33ea6c39c72d91d5b2a0aa___(
                    &v10,
                    a4);
  v6 = *v5;
  *v5 = 0;
  v7 = v10;
  if ( v10 )
  {
    v10 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(v7);
  }
  v8 = SHTaskPoolQueueTask(0, 2, a3);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  return v8;
}

```

## disassembly

```asm
0x180028b98  mov     [rsp+arg_0], rbx
0x180028b9d  push    rdi
0x180028b9e  sub     rsp, 40h
0x180028ba2  mov     edi, r8d
0x180028ba5  mov     rdx, r9
0x180028ba8  lea     rcx, [rsp+48h+var_18]
0x180028bad  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_080f8fc71c33ea6c39c72d91d5b2a0aa_____lambda_080f8fc71c33ea6c39c72d91d5b2a0aa___
0x180028bb2  mov     rbx, [rax]
0x180028bb5  mov     qword ptr [rax], 0
0x180028bbc  mov     rcx, [rsp+48h+var_18]
0x180028bc1  test    rcx, rcx
0x180028bc4  jz      short loc_180028BD4
0x180028bc6  mov     [rsp+48h+var_18], 0
0x180028bcf  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180028bd4  mov     [rsp+48h+var_20], 0
0x180028bdd  mov     [rsp+48h+var_28], rbx
0x180028be2  xor     r9d, r9d
0x180028be5  mov     r8d, edi
0x180028be8  lea     edx, [r9+2]
0x180028bec  xor     ecx, ecx
0x180028bee  call    cs:__imp_SHTaskPoolQueueTask
0x180028bf4  mov     edi, eax
0x180028bf6  test    rbx, rbx
0x180028bf9  jz      short loc_180028C0B
0x180028bfb  mov     rdx, [rbx]
0x180028bfe  mov     rcx, rbx
0x180028c01  mov     rax, [rdx+10h]
0x180028c05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c0a  nop
0x180028c0b  mov     eax, edi
0x180028c0d  mov     rbx, [rsp+48h+arg_0]
0x180028c12  add     rsp, 40h
0x180028c16  pop     rdi
0x180028c17  retn
```
