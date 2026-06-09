# FwArrayDestroy

- ea: `0x180006ac0`
- end: `0x180006b30`
- name: `FwArrayDestroy`
- size: `112`
- prototype: ``
- caller_count: `8`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180006a50`
- `0x180006aa0`
- `0x180006b68`
- `0x180006fd0`
- `0x180006ff0`
- `0x1800138f0`
- `0x180029d10`
- `0x18002c310`

## callees

- `0x180004840`
- `0x180006ac0`
- `0x18001164c`
- `0x180017b38`
- `0x18002f43c`
- `0x180030010`

## pseudocode

```c
void __fastcall FwArrayDestroy(__int64 a1, void (__fastcall *a2)(__int64), __int64 a3)
{
  unsigned int i; // edi
  __int64 v7; // rax

  if ( !a1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( !(unsigned int)FwArrayIsValid((const struct FW_GENERIC_ARRAY_ *)a3) )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  for ( i = 0; i < *(_DWORD *)a3; ++i )
  {
    v7 = FwArrayAt(a1, a3, i);
    a2(v7);
  }
  FwFree(*(void **)(a3 + 8));
  *(_OWORD *)a3 = 0;
}

```

## disassembly

```asm
0x180006ac0  push    rbx
0x180006ac2  push    rbp
0x180006ac3  push    rsi
0x180006ac4  push    rdi
0x180006ac5  sub     rsp, 28h
0x180006ac9  mov     rbx, r8
0x180006acc  mov     rbp, rdx
0x180006acf  mov     rsi, rcx
0x180006ad2  test    rcx, rcx
0x180006ad5  jz      short loc_180006B01
0x180006ad7  mov     rcx, rbx; struct FW_GENERIC_ARRAY_ *
0x180006ada  call    ?FwArrayIsValid@@YAHPEBUFW_GENERIC_ARRAY_@@@Z; FwArrayIsValid(FW_GENERIC_ARRAY_ const *)
0x180006adf  test    eax, eax
0x180006ae1  jz      short loc_180006B08
0x180006ae3  xor     edi, edi
0x180006ae5  cmp     [rbx], edi
0x180006ae7  ja      short loc_180006B0F
0x180006ae9  mov     rcx, [rbx+8]
0x180006aed  call    FwFree
0x180006af2  xorps   xmm0, xmm0
0x180006af5  movups  xmmword ptr [rbx], xmm0
0x180006af8  add     rsp, 28h
0x180006afc  pop     rdi
0x180006afd  pop     rsi
0x180006afe  pop     rbp
0x180006aff  pop     rbx
0x180006b00  retn
0x180006b01  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "elementSize > 0")
0x180006b06  jmp     short loc_180006AD7
0x180006b08  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "FwArrayIsValid(array)")
0x180006b0d  jmp     short loc_180006AE3
0x180006b0f  mov     r8d, edi
0x180006b12  mov     rdx, rbx
0x180006b15  mov     rcx, rsi
0x180006b18  call    FwArrayAt
0x180006b1d  mov     rcx, rax
0x180006b20  mov     rax, rbp
0x180006b23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b28  inc     edi
0x180006b2a  cmp     edi, [rbx]
0x180006b2c  jb      short loc_180006B0F
0x180006b2e  jmp     short loc_180006AE9
```
