# DeploymentServiceCom::Release(void)

- ea: `0x180001570`
- end: `0x1800015a0`
- name: `?Release@DeploymentServiceCom@@UEAAKXZ`
- size: `48`
- prototype: `unsigned int __fastcall(DeploymentServiceCom *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800015a0`

## callees

- `0x180001570`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall DeploymentServiceCom::Release(DeploymentServiceCom *this)
{
  unsigned __int32 v1; // ebx

  v1 = _InterlockedDecrement((volatile signed __int32 *)this + 4);
  if ( !v1 && this )
    (*(void (__fastcall **)(DeploymentServiceCom *, __int64))(*(_QWORD *)this + 112LL))(this, 1);
  return v1;
}

```

## disassembly

```asm
0x180001570  push    rbx
0x180001572  sub     rsp, 20h
0x180001576  or      ebx, 0FFFFFFFFh
0x180001579  lock xadd [rcx+10h], ebx
0x18000157e  sub     ebx, 1
0x180001581  jnz     short loc_180001598
0x180001583  test    rcx, rcx
0x180001586  jz      short loc_180001598
0x180001588  mov     rdx, [rcx]
0x18000158b  mov     rax, [rdx+70h]
0x18000158f  lea     edx, [rbx+1]
0x180001592  call    cs:__guard_dispatch_icall_fptr
0x180001598  mov     eax, ebx
0x18000159a  add     rsp, 20h
0x18000159e  pop     rbx
0x18000159f  retn
```
