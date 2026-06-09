# _pewprint(ulong,_PROCESS_ENTRY *,ushort const *,...)

- ea: `0x18002147c`
- end: `0x18002151c`
- name: `?_pewprint@@YAHKPEAU_PROCESS_ENTRY@@PEBGZZ`
- size: `160`
- prototype: `__int64(unsigned int, struct _PROCESS_ENTRY *, const unsigned __int16 *, ...)`
- caller_count: `9`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000e5e0`
- `0x180021374`
- `0x18002384c`
- `0x18018b7b4`
- `0x18018bc28`
- `0x18018bd80`
- `0x18019eca0`
- `0x18019f980`
- `0x1801a32cc`

## callees

- `0x18000f998`
- `0x18002147c`
- `0x180021788`
- `0x1801ad080`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vswprintf_s` at `0x1800214c5`
- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vswprintf_s` at `0x1800214c5`

## pseudocode

```c
__int64 _pewprint(unsigned int a1, struct _PROCESS_ENTRY *a2, const unsigned __int16 *a3, ...)
{
  unsigned __int64 *v6; // rax
  va_list va; // [rsp+98h] [rbp+20h] BYREF

  va_start(va, a3);
  v6 = _local_stdio_printf_options();
  _o___stdio_common_vswprintf_s(*v6, &word_1802CC4F0, 1001, a3, 0, (__int64 *)va);
  if ( word_1802CC4F0 && !(unsigned int)evtwprint(a2, a1, 0, 0, 0, L"%s", &word_1802CC4F0) )
    DoCallback(a2, a1, &word_1802CC4F0);
  return 1;
}

```

## disassembly

```asm
0x18002147c  mov     rax, rsp
0x18002147f  mov     [rax+18h], r8
0x180021483  mov     [rax+20h], r9
0x180021487  push    rbx
0x180021488  push    rbp
0x180021489  push    rsi
0x18002148a  push    rdi
0x18002148b  push    r14
0x18002148d  sub     rsp, 50h
0x180021491  mov     rbx, r8
0x180021494  lea     rbp, [rax+20h]
0x180021498  mov     rdi, rdx
0x18002149b  mov     esi, ecx
0x18002149d  xor     r14d, r14d
0x1800214a0  call    __local_stdio_printf_options
0x1800214a5  mov     r9, rbx
0x1800214a8  mov     [rsp+78h+var_50], rbp
0x1800214ad  lea     rbx, word_1802CC4F0
0x1800214b4  mov     [rsp+78h+var_58], r14
0x1800214b9  mov     rdx, rbx
0x1800214bc  mov     r8d, 3E9h
0x1800214c2  mov     rcx, [rax]
0x1800214c5  call    cs:__imp__o___stdio_common_vswprintf_s
0x1800214cb  cmp     cs:word_1802CC4F0, r14w
0x1800214d3  jz      short loc_18002150C
0x1800214d5  lea     rax, aS_5; "%s"
0x1800214dc  mov     [rsp+78h+var_48], rbx
0x1800214e1  mov     [rsp+78h+var_50], rax; unsigned __int16 *
0x1800214e6  xor     r9d, r9d; unsigned int
0x1800214e9  xor     r8d, r8d; unsigned int
0x1800214ec  mov     [rsp+78h+var_58], r14; void *
0x1800214f1  mov     edx, esi; unsigned int
0x1800214f3  mov     rcx, rdi; struct _PROCESS_ENTRY *
0x1800214f6  call    ?evtwprint@@YAHPEAU_PROCESS_ENTRY@@KKKPEAXPEBGZZ; evtwprint(_PROCESS_ENTRY *,ulong,ulong,ulong,void *,ushort const *,...)
0x1800214fb  test    eax, eax
0x1800214fd  jnz     short loc_18002150C
0x1800214ff  mov     r8, rbx; void *
0x180021502  mov     edx, esi; unsigned int
0x180021504  mov     rcx, rdi; struct _PROCESS_ENTRY *
0x180021507  call    ?DoCallback@@YAHPEAU_PROCESS_ENTRY@@KPEAX@Z; DoCallback(_PROCESS_ENTRY *,ulong,void *)
0x18002150c  mov     eax, 1
0x180021511  add     rsp, 50h
0x180021515  pop     r14
0x180021517  pop     rdi
0x180021518  pop     rsi
0x180021519  pop     rbp
0x18002151a  pop     rbx
0x18002151b  retn
```
