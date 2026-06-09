# DeploymentServiceComClassFactory::Release(void)

- ea: `0x180001740`
- end: `0x180001770`
- name: `?Release@DeploymentServiceComClassFactory@@UEAAKXZ`
- size: `48`
- prototype: `unsigned int __fastcall(DeploymentServiceComClassFactory *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001740`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall DeploymentServiceComClassFactory::Release(DeploymentServiceComClassFactory *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 2);
  if ( !v1 && this )
    (*(void (__fastcall **)(DeploymentServiceComClassFactory *, __int64))(*(_QWORD *)this + 40LL))(this, 1);
  return v1;
}

```

## disassembly

```asm
0x180001740  push    rbx
0x180001742  sub     rsp, 20h
0x180001746  or      ebx, 0FFFFFFFFh
0x180001749  lock xadd [rcx+8], ebx
0x18000174e  sub     ebx, 1
0x180001751  jnz     short loc_180001768
0x180001753  test    rcx, rcx
0x180001756  jz      short loc_180001768
0x180001758  mov     rdx, [rcx]
0x18000175b  mov     rax, [rdx+28h]
0x18000175f  lea     edx, [rbx+1]
0x180001762  call    cs:__guard_dispatch_icall_fptr
0x180001768  mov     eax, ebx
0x18000176a  add     rsp, 20h
0x18000176e  pop     rbx
0x18000176f  retn
```
