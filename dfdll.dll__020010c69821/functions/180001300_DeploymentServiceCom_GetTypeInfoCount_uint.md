# DeploymentServiceCom::GetTypeInfoCount(uint *)

- ea: `0x180001300`
- end: `0x18000132a`
- name: `?GetTypeInfoCount@DeploymentServiceCom@@UEAAJPEAI@Z`
- size: `42`
- prototype: `__int64 __fastcall(DeploymentServiceCom *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180001330`

## callees

- `0x180001300`
- `0x1800013cc`

## pseudocode

```c
__int64 __fastcall DeploymentServiceCom::GetTypeInfoCount(DeploymentServiceCom *this, unsigned int *a2)
{
  __int64 result; // rax

  if ( !a2 )
    return 2147942487LL;
  result = DeploymentServiceCom::LoadTypeInfo(this);
  if ( (int)result >= 0 )
    *a2 = 1;
  return result;
}

```

## disassembly

```asm
0x180001300  push    rbx
0x180001302  sub     rsp, 20h
0x180001306  mov     rbx, rdx
0x180001309  test    rdx, rdx
0x18000130c  jnz     short loc_180001315
0x18000130e  mov     eax, 80070057h
0x180001313  jmp     short loc_180001324
0x180001315  call    ?LoadTypeInfo@DeploymentServiceCom@@QEAAJXZ; DeploymentServiceCom::LoadTypeInfo(void)
0x18000131a  test    eax, eax
0x18000131c  js      short loc_180001324
0x18000131e  mov     dword ptr [rbx], 1
0x180001324  add     rsp, 20h
0x180001328  pop     rbx
0x180001329  retn
```
