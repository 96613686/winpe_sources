# KERNEL32::F_CreateWaitableTimerW

- ea: `0x1400091f0`
- end: `0x140009243`
- name: `KERNEL32::F_CreateWaitableTimerW`
- size: `83`
- prototype: `__int64 (*__fastcall(__int64, unsigned int, __int64))(void)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140008dfc`
- `0x1400091f0`
- `0x14000a010`

## string_xrefs

- `0x14000920e`: `CreateWaitableTimerW`

## pseudocode

```c
__int64 (*__fastcall KERNEL32::F_CreateWaitableTimerW(__int64 a1, unsigned int a2, __int64 a3))(void)
{
  __int64 (*result)(void); // rax

  result = Bind_KERNEL32("CreateWaitableTimerW", &KERNEL32::CreateWaitableTimerW);
  if ( result )
    return (__int64 (*)(void))((__int64 (__fastcall *)(__int64, _QWORD, __int64))KERNEL32::CreateWaitableTimerW)(
                                a1,
                                a2,
                                a3);
  return result;
}

```

## disassembly

```asm
0x1400091f0  mov     [rsp+arg_0], rbx
0x1400091f5  mov     [rsp+arg_8], rsi
0x1400091fa  push    rdi
0x1400091fb  sub     rsp, 20h
0x1400091ff  mov     edi, edx
0x140009201  mov     rsi, rcx
0x140009204  lea     rdx, ?CreateWaitableTimerW@KERNEL32@@3P6APEAXPEAU_SECURITY_ATTRIBUTES@@HPEBG@ZEA; __int64 (**)(void)
0x14000920b  mov     rbx, r8
0x14000920e  lea     rcx, aCreatewaitable; "CreateWaitableTimerW"
0x140009215  call    ?Bind_KERNEL32@@YAP6A_JXZPEBDPEAP6A_JXZ@Z; Bind_KERNEL32(char const *,__int64 (**)(void))
0x14000921a  test    rax, rax
0x14000921d  jz      short loc_140009233
0x14000921f  mov     rax, cs:?CreateWaitableTimerW@KERNEL32@@3P6APEAXPEAU_SECURITY_ATTRIBUTES@@HPEBG@ZEA; void * (*KERNEL32::CreateWaitableTimerW)(_SECURITY_ATTRIBUTES *,int,ushort const *)
0x140009226  mov     r8, rbx
0x140009229  mov     edx, edi
0x14000922b  mov     rcx, rsi
0x14000922e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009233  mov     rbx, [rsp+28h+arg_0]
0x140009238  mov     rsi, [rsp+28h+arg_8]
0x14000923d  add     rsp, 20h
0x140009241  pop     rdi
0x140009242  retn
```
