# CCompileProgressNotification::ProgressNotification(ulong,ushort *,int,long,ushort *,ulong)

- ea: `0x1400070a0`
- end: `0x1400070e6`
- name: `?ProgressNotification@CCompileProgressNotification@@UEAAJKPEAGHJ0K@Z`
- size: `70`
- prototype: `__int64 __fastcall(CCompileProgressNotification *this, __int64, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140013f30`

## pseudocode

```c
__int64 __fastcall CCompileProgressNotification::ProgressNotification(
        CCompileProgressNotification *this,
        __int64 a2,
        unsigned __int16 *a3)
{
  return (*(__int64 (__fastcall **)(char *, __int64, unsigned __int16 *))(*((_QWORD *)this + 2) + 32LL))(
           (char *)this + 16,
           a2,
           a3);
}

```

## disassembly

```asm
0x1400070a0  sub     rsp, 58h
0x1400070a4  and     [rsp+58h+var_20], 0
0x1400070a9  add     rcx, 10h
0x1400070ad  mov     r10d, [rsp+58h+arg_30]
0x1400070b5  mov     [rsp+58h+var_28], r10d
0x1400070ba  mov     r10, [rsp+58h+arg_28]
0x1400070c2  mov     rax, [rcx]
0x1400070c5  mov     [rsp+58h+var_30], r10
0x1400070ca  mov     r10d, [rsp+58h+arg_20]
0x1400070d2  mov     [rsp+58h+var_38], r10d
0x1400070d7  mov     rax, [rax+20h]
0x1400070db  call    cs:__guard_dispatch_icall_fptr
0x1400070e1  add     rsp, 58h
0x1400070e5  retn
```
