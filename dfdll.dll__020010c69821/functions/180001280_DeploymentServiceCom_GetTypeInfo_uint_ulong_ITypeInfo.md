# DeploymentServiceCom::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x180001280`
- end: `0x1800012e5`
- name: `?GetTypeInfo@DeploymentServiceCom@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `101`
- prototype: `__int64 __fastcall(DeploymentServiceCom *__hidden this, unsigned int, unsigned int, struct ITypeInfo **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800012f0`

## callees

- `0x180001280`
- `0x1800013cc`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall DeploymentServiceCom::GetTypeInfo(
        DeploymentServiceCom *this,
        int a2,
        __int64 a3,
        struct ITypeInfo **a4)
{
  int TypeInfo; // ebx

  if ( !a4 )
    return 2147942487LL;
  if ( a2 )
    return 2147614731LL;
  *a4 = 0;
  TypeInfo = DeploymentServiceCom::LoadTypeInfo(this);
  if ( TypeInfo >= 0 )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 8LL))(*((_QWORD *)this + 3));
    *a4 = (struct ITypeInfo *)*((_QWORD *)this + 3);
  }
  return (unsigned int)TypeInfo;
}

```

## disassembly

```asm
0x180001280  mov     [rsp+arg_0], rbx
0x180001285  mov     [rsp+arg_8], rsi
0x18000128a  push    rdi
0x18000128b  sub     rsp, 20h
0x18000128f  mov     rdi, r9
0x180001292  mov     rsi, rcx
0x180001295  test    r9, r9
0x180001298  jnz     short loc_1800012A1
0x18000129a  mov     eax, 80070057h
0x18000129f  jmp     short loc_1800012D5
0x1800012a1  test    edx, edx
0x1800012a3  jz      short loc_1800012AC
0x1800012a5  mov     eax, 8002000Bh
0x1800012aa  jmp     short loc_1800012D5
0x1800012ac  and     qword ptr [r9], 0
0x1800012b0  call    ?LoadTypeInfo@DeploymentServiceCom@@QEAAJXZ; DeploymentServiceCom::LoadTypeInfo(void)
0x1800012b5  mov     ebx, eax
0x1800012b7  test    eax, eax
0x1800012b9  js      short loc_1800012D3
0x1800012bb  mov     rcx, [rsi+18h]
0x1800012bf  mov     rdx, [rcx]
0x1800012c2  mov     rax, [rdx+8]
0x1800012c6  call    cs:__guard_dispatch_icall_fptr
0x1800012cc  mov     rcx, [rsi+18h]
0x1800012d0  mov     [rdi], rcx
0x1800012d3  mov     eax, ebx
0x1800012d5  mov     rbx, [rsp+28h+arg_0]
0x1800012da  mov     rsi, [rsp+28h+arg_8]
0x1800012df  add     rsp, 20h
0x1800012e3  pop     rdi
0x1800012e4  retn
```
