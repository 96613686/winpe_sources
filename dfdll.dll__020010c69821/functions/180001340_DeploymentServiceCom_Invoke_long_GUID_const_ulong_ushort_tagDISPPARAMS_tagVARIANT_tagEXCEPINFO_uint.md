# DeploymentServiceCom::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x180001340`
- end: `0x1800013b7`
- name: `?Invoke@DeploymentServiceCom@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `119`
- prototype: `__int64 __fastcall(DeploymentServiceCom *__hidden this, int, const struct _GUID *, unsigned int, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800013c0`

## callees

- `0x180001340`
- `0x1800013cc`
- `0x18001efd0`

## pseudocode

```c
__int64 __fastcall DeploymentServiceCom::Invoke(
        DeploymentServiceCom *this,
        unsigned int a2,
        const struct _GUID *a3,
        __int64 a4,
        unsigned __int16 a5,
        struct tagDISPPARAMS *a6,
        struct tagVARIANT *a7,
        struct tagEXCEPINFO *a8,
        unsigned int *a9)
{
  __int64 result; // rax

  result = DeploymentServiceCom::LoadTypeInfo(this);
  if ( (int)result >= 0 )
    return (*(__int64 (__fastcall **)(_QWORD, DeploymentServiceCom *, _QWORD, _QWORD, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, unsigned int *))(**((_QWORD **)this + 3) + 88LL))(
             *((_QWORD *)this + 3),
             this,
             a2,
             a5,
             a6,
             a7,
             a8,
             a9);
  return result;
}

```

## disassembly

```asm
0x180001340  mov     [rsp+arg_0], rbx
0x180001345  push    rdi
0x180001346  sub     rsp, 50h
0x18000134a  mov     edi, edx
0x18000134c  mov     rbx, rcx
0x18000134f  call    ?LoadTypeInfo@DeploymentServiceCom@@QEAAJXZ; DeploymentServiceCom::LoadTypeInfo(void)
0x180001354  test    eax, eax
0x180001356  js      short loc_1800013AC
0x180001358  mov     rdx, [rsp+58h+arg_40]
0x180001360  mov     r8d, edi
0x180001363  mov     rcx, [rbx+18h]
0x180001367  movzx   r9d, [rsp+58h+arg_20]
0x180001370  mov     [rsp+58h+var_20], rdx
0x180001375  mov     rdx, [rsp+58h+arg_38]
0x18000137d  mov     rax, [rcx]
0x180001380  mov     [rsp+58h+var_28], rdx
0x180001385  mov     rdx, [rsp+58h+arg_30]
0x18000138d  mov     [rsp+58h+var_30], rdx
0x180001392  mov     rdx, [rsp+58h+arg_28]
0x18000139a  mov     rax, [rax+58h]
0x18000139e  mov     [rsp+58h+var_38], rdx
0x1800013a3  mov     rdx, rbx
0x1800013a6  call    cs:__guard_dispatch_icall_fptr
0x1800013ac  mov     rbx, [rsp+58h+arg_0]
0x1800013b1  add     rsp, 50h
0x1800013b5  pop     rdi
0x1800013b6  retn
```
