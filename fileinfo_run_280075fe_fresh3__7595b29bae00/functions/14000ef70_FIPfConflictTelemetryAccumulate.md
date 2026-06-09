# FIPfConflictTelemetryAccumulate

- ea: `0x14000ef70`
- end: `0x14000f014`
- name: `FIPfConflictTelemetryAccumulate`
- size: `164`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140010cd0`
- `0x140015d3c`
- `0x14001606c`

## callees

- `0x14000ef70`
- `0x14000f9b8`

## pseudocode

```c
NTSTATUS __fastcall FIPfConflictTelemetryAccumulate(
        wchar_t *a1,
        unsigned __int16 a2,
        int a3,
        unsigned int a4,
        int a5,
        unsigned __int16 *a6,
        _WORD *a7)
{
  NTSTATUS result; // eax

  if ( !a7 )
    return FIPfConflictTelemetryUpdate(
             a1,
             a2,
             a3,
             a4,
             a6,
             ((MEMORY[0xFFFFF78000000004] * MEMORY[0xFFFFF78000000324]) << 8)
           + ((MEMORY[0xFFFFF78000000320] * (unsigned __int64)MEMORY[0xFFFFF78000000004]) >> 24)
           - a5);
  *a7 += *a6;
  a7[2] += a6[2];
  a7[1] += a6[1];
  result = a6[3];
  a7[3] += result;
  return result;
}

```

## disassembly

```asm
0x14000ef70  mov     [rsp+arg_0], rbx
0x14000ef75  push    rdi
0x14000ef76  sub     rsp, 30h
0x14000ef7a  mov     r10, [rsp+38h+arg_30]
0x14000ef7f  mov     r11d, r8d
0x14000ef82  movzx   ebx, dx
0x14000ef85  mov     rdi, rcx
0x14000ef88  test    r10, r10
0x14000ef8b  jz      short loc_14000EFB6
0x14000ef8d  mov     rcx, [rsp+38h+arg_28]
0x14000ef92  movzx   eax, word ptr [rcx]
0x14000ef95  add     [r10], ax
0x14000ef99  movzx   eax, word ptr [rcx+4]
0x14000ef9d  add     [r10+4], ax
0x14000efa2  movzx   eax, word ptr [rcx+2]
0x14000efa6  add     [r10+2], ax
0x14000efab  movzx   eax, word ptr [rcx+6]
0x14000efaf  add     [r10+6], ax
0x14000efb4  jmp     short loc_14000F008
0x14000efb6  mov     rcx, 0FFFFF78000000320h
0x14000efc0  mov     rcx, [rcx]
0x14000efc3  mov     eax, ds:0FFFFF78000000004h
0x14000efcc  mov     edx, ecx
0x14000efce  mov     r8d, eax
0x14000efd1  imul    r8, rdx
0x14000efd5  shr     rcx, 20h
0x14000efd9  movzx   edx, bx
0x14000efdc  imul    ecx, eax
0x14000efdf  mov     rax, [rsp+38h+arg_28]
0x14000efe4  shr     r8, 18h
0x14000efe8  shl     ecx, 8
0x14000efeb  add     r8d, ecx
0x14000efee  mov     rcx, rdi
0x14000eff1  sub     r8d, [rsp+38h+arg_20]
0x14000eff6  mov     [rsp+38h+var_10], r8d
0x14000effb  mov     r8d, r11d
0x14000effe  mov     [rsp+38h+var_18], rax
0x14000f003  call    FIPfConflictTelemetryUpdate
0x14000f008  mov     rbx, [rsp+38h+arg_0]
0x14000f00d  add     rsp, 30h
0x14000f011  pop     rdi
0x14000f012  retn
```
