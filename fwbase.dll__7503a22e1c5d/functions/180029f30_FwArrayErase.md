# FwArrayErase

- ea: `0x180029f30`
- end: `0x180029fc0`
- name: `FwArrayErase`
- size: `144`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180011790`
- `0x180011d60`
- `0x180011e40`
- `0x18002a9f4`
- `0x18002b710`

## callees

- `0x180004840`
- `0x18001164c`
- `0x180017b38`
- `0x180029f30`
- `0x18002f43c`
- `0x18002f680`
- `0x180030010`

## pseudocode

```c
void __fastcall FwArrayErase(__int64 a1, void (__fastcall *a2)(char *), __int64 a3, unsigned int a4)
{
  char *v8; // rbx

  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !(unsigned int)FwArrayIsValid((const struct FW_GENERIC_ARRAY_ *)a3) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( a4 >= *(_DWORD *)a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v8 = (char *)FwArrayAt(a1, a3, a4);
  a2(v8);
  memmove_0(v8, &v8[a1], a1 * (--*(_DWORD *)a3 - a4));
  if ( !*(_DWORD *)a3 )
  {
    FwFree(*(void **)(a3 + 8));
    *(_QWORD *)(a3 + 8) = 0;
  }
}

```

## disassembly

```asm
0x180029f30  push    rbx
0x180029f32  push    rbp
0x180029f33  push    rsi
0x180029f34  push    rdi
0x180029f35  push    r14
0x180029f37  sub     rsp, 20h
0x180029f3b  mov     esi, r9d
0x180029f3e  mov     rdi, r8
0x180029f41  mov     r14, rdx
0x180029f44  mov     rbp, rcx
0x180029f47  test    rcx, rcx
0x180029f4a  jnz     short loc_180029F51
0x180029f4c  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "elementSize > 0")
0x180029f51  mov     rcx, rdi; struct FW_GENERIC_ARRAY_ *
0x180029f54  call    ?FwArrayIsValid@@YAHPEBUFW_GENERIC_ARRAY_@@@Z; FwArrayIsValid(FW_GENERIC_ARRAY_ const *)
0x180029f59  test    eax, eax
0x180029f5b  jnz     short loc_180029F62
0x180029f5d  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "FwArrayIsValid(array)")
0x180029f62  cmp     esi, [rdi]
0x180029f64  jb      short loc_180029F6B
0x180029f66  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "index < array->numElements")
0x180029f6b  mov     r8d, esi
0x180029f6e  mov     rdx, rdi
0x180029f71  mov     rcx, rbp
0x180029f74  call    FwArrayAt
0x180029f79  mov     rbx, rax
0x180029f7c  mov     rcx, rax
0x180029f7f  mov     rax, r14
0x180029f82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f87  dec     dword ptr [rdi]
0x180029f89  lea     rdx, [rbx+rbp]; Src
0x180029f8d  mov     r8d, [rdi]
0x180029f90  mov     rcx, rbx; void *
0x180029f93  sub     r8d, esi
0x180029f96  imul    r8, rbp; Size
0x180029f9a  call    memmove_0
0x180029f9f  cmp     dword ptr [rdi], 0
0x180029fa2  jnz     short loc_180029FB5
0x180029fa4  mov     rcx, [rdi+8]
0x180029fa8  call    FwFree
0x180029fad  mov     qword ptr [rdi+8], 0
0x180029fb5  add     rsp, 20h
0x180029fb9  pop     r14
0x180029fbb  pop     rdi
0x180029fbc  pop     rsi
0x180029fbd  pop     rbp
0x180029fbe  pop     rbx
0x180029fbf  retn
```
