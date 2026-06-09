# Windows::Internal::ComTaskPool::QueueTask__lambda_acf8898fc7bcbd63c3fff83d949e72da___

- ea: `0x180028c20`
- end: `0x180028ca0`
- name: `Windows::Internal::ComTaskPool::QueueTask__lambda_acf8898fc7bcbd63c3fff83d949e72da___`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002bf94`

## callees

- `0x180028a48`
- `0x180028c20`
- `0x18002da30`
- `0x180040010`

## import_xrefs

- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180028c76`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x180028c76`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTask__lambda_acf8898fc7bcbd63c3fff83d949e72da___(
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

  v5 = (__int64 *)Microsoft::WRL::Details::Make_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_acf8898fc7bcbd63c3fff83d949e72da_____lambda_acf8898fc7bcbd63c3fff83d949e72da___(
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
0x180028c20  mov     [rsp+arg_0], rbx
0x180028c25  push    rdi
0x180028c26  sub     rsp, 40h
0x180028c2a  mov     edi, r8d
0x180028c2d  mov     rdx, r9
0x180028c30  lea     rcx, [rsp+48h+var_18]
0x180028c35  call    Microsoft__WRL__Details__Make_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_acf8898fc7bcbd63c3fff83d949e72da_____lambda_acf8898fc7bcbd63c3fff83d949e72da___
0x180028c3a  mov     rbx, [rax]
0x180028c3d  mov     qword ptr [rax], 0
0x180028c44  mov     rcx, [rsp+48h+var_18]
0x180028c49  test    rcx, rcx
0x180028c4c  jz      short loc_180028C5C
0x180028c4e  mov     [rsp+48h+var_18], 0
0x180028c57  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x180028c5c  mov     [rsp+48h+var_20], 0
0x180028c65  mov     [rsp+48h+var_28], rbx
0x180028c6a  xor     r9d, r9d
0x180028c6d  mov     r8d, edi
0x180028c70  lea     edx, [r9+2]
0x180028c74  xor     ecx, ecx
0x180028c76  call    cs:__imp_SHTaskPoolQueueTask
0x180028c7c  mov     edi, eax
0x180028c7e  test    rbx, rbx
0x180028c81  jz      short loc_180028C93
0x180028c83  mov     rdx, [rbx]
0x180028c86  mov     rcx, rbx
0x180028c89  mov     rax, [rdx+10h]
0x180028c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028c92  nop
0x180028c93  mov     eax, edi
0x180028c95  mov     rbx, [rsp+48h+arg_0]
0x180028c9a  add     rsp, 40h
0x180028c9e  pop     rdi
0x180028c9f  retn
```
