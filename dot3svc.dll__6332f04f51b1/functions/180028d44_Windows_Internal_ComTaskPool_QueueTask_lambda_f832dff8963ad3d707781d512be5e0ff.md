# Windows::Internal::ComTaskPool::QueueTask__lambda_f832dff8963ad3d707781d512be5e0ff___

- ea: `0x180028d44`
- end: `0x180028dc4`
- name: `Windows::Internal::ComTaskPool::QueueTask__lambda_f832dff8963ad3d707781d512be5e0ff___`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002be18`

## callees

- `0x180028aec`
- `0x180028d44`
- `0x18002da30`
- `0x180040010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180028d9a`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180028d9a`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTask__lambda_f832dff8963ad3d707781d512be5e0ff___(
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

  v5 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_f832dff8963ad3d707781d512be5e0ff_____lambda_f832dff8963ad3d707781d512be5e0ff___(
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
0x180028d44  mov     [rsp+arg_0], rbx
0x180028d49  push    rdi
0x180028d4a  sub     rsp, 40h
0x180028d4e  mov     edi, r8d
0x180028d51  mov     rdx, r9
0x180028d54  lea     rcx, [rsp+48h+var_18]
0x180028d59  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_f832dff8963ad3d707781d512be5e0ff_____lambda_f832dff8963ad3d707781d512be5e0ff___
0x180028d5e  mov     rbx, [rax]
0x180028d61  mov     qword ptr [rax], 0
0x180028d68  mov     rcx, [rsp+48h+var_18]
0x180028d6d  test    rcx, rcx
0x180028d70  jz      short loc_180028D80
0x180028d72  mov     [rsp+48h+var_18], 0
0x180028d7b  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180028d80  mov     [rsp+48h+var_20], 0
0x180028d89  mov     [rsp+48h+var_28], rbx
0x180028d8e  xor     r9d, r9d
0x180028d91  mov     r8d, edi
0x180028d94  lea     edx, [r9+2]
0x180028d98  xor     ecx, ecx
0x180028d9a  call    cs:__imp_SHTaskPoolQueueTask
0x180028da0  mov     edi, eax
0x180028da2  test    rbx, rbx
0x180028da5  jz      short loc_180028DB7
0x180028da7  mov     rdx, [rbx]
0x180028daa  mov     rcx, rbx
0x180028dad  mov     rax, [rdx+10h]
0x180028db1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028db6  nop
0x180028db7  mov     eax, edi
0x180028db9  mov     rbx, [rsp+48h+arg_0]
0x180028dbe  add     rsp, 40h
0x180028dc2  pop     rdi
0x180028dc3  retn
```
