# CIISComputer::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x180005fa0`
- end: `0x180006007`
- name: `?Invoke@CIISComputer@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `103`
- prototype: `__int64 __fastcall(CIISComputer *__hidden this, int, const struct _GUID *, unsigned int, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180012010`

## pseudocode

```c
__int64 __fastcall CIISComputer::Invoke(
        CIISComputer *this,
        unsigned int a2,
        const struct _GUID *a3,
        unsigned int a4,
        unsigned __int16 a5,
        struct tagDISPPARAMS *a6,
        struct tagVARIANT *a7,
        struct tagEXCEPINFO *a8,
        unsigned int *a9)
{
  return (*(__int64 (__fastcall **)(_QWORD, _QWORD, const struct _GUID *, _QWORD, unsigned __int16, struct tagDISPPARAMS *, struct tagVARIANT *, struct tagEXCEPINFO *, unsigned int *))(**((_QWORD **)this + 7) + 48LL))(
           *((_QWORD *)this + 7),
           a2,
           a3,
           a4,
           a5,
           a6,
           a7,
           a8,
           a9);
}

```

## disassembly

```asm
0x180005fa0  push    rbx
0x180005fa2  sub     rsp, 50h
0x180005fa6  mov     r10, [rsp+58h+arg_40]
0x180005fae  mov     r11d, r9d
0x180005fb1  mov     r9, [rsp+58h+arg_28]
0x180005fb9  mov     ebx, edx
0x180005fbb  movzx   edx, [rsp+58h+arg_20]
0x180005fc3  mov     rcx, [rcx+38h]
0x180005fc7  mov     [rsp+58h+var_18], r10
0x180005fcc  mov     r10, [rsp+58h+arg_38]
0x180005fd4  mov     [rsp+58h+var_20], r10
0x180005fd9  mov     r10, [rsp+58h+arg_30]
0x180005fe1  mov     rax, [rcx]
0x180005fe4  mov     [rsp+58h+var_28], r10
0x180005fe9  mov     [rsp+58h+var_30], r9
0x180005fee  mov     r9d, r11d
0x180005ff1  mov     [rsp+58h+var_38], dx
0x180005ff6  mov     edx, ebx
0x180005ff8  mov     rax, [rax+30h]
0x180005ffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006001  add     rsp, 50h
0x180006005  pop     rbx
0x180006006  retn
```
