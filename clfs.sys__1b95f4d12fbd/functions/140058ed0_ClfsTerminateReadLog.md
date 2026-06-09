# ClfsTerminateReadLog

- ea: `0x140058ed0`
- end: `0x14005905b`
- name: `ClfsTerminateReadLog`
- size: `395`
- prototype: `NTSTATUS __stdcall(PVOID pvCursorContext)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x14000ed64`
- `0x140011d90`
- `0x1400577c0`
- `0x140058ed0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x140058f24`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140058f24`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140058f50`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140079bcf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140058f50`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140079bcf`

## string_xrefs

- `0x140058f9d`: `ClfsTerminateReadLog`
- `0x140059005`: `ClfsTerminateReadLog`
- `0x14005903f`: `ClfsTerminateReadLog`

## pseudocode

```c
NTSTATUS __stdcall ClfsTerminateReadLog(PVOID pvCursorContext)
{
  volatile signed __int32 *v2; // rcx

  if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      281,
      (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
      (unsigned int)"ClfsTerminateReadLog",
      59);
  }
  if ( !pvCursorContext )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        282,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsTerminateReadLog",
        70,
        -1073741811);
    }
    return -1073741811;
  }
  if ( *(_DWORD *)pvCursorContext != -1040322545
    || *((_DWORD *)pvCursorContext + 1) != 176
    || (*((_DWORD *)pvCursorContext + 32) & 0x14) == 0 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        283,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsTerminateReadLog",
        87,
        -1073741811);
    }
    return -1073741811;
  }
  KeEnterCriticalRegion();
  v2 = (volatile signed __int32 *)*((_QWORD *)pvCursorContext + 19);
  _InterlockedDecrement(v2 + 46);
  CClfsKernelMarshallingContext::DeallocateIocb((CClfsKernelMarshallingContext *)v2, pvCursorContext);
  KeLeaveCriticalRegion();
  if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      284,
      (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
      (unsigned int)"ClfsTerminateReadLog",
      132);
  }
  return 0;
}

```

## disassembly

```asm
0x140058ed0  mov     [rsp+arg_0], rbx
0x140058ed5  push    rsi
0x140058ed6  sub     rsp, 40h
0x140058eda  mov     rbx, rcx
0x140058edd  lea     rsi, WPP_GLOBAL_Control
0x140058ee4  mov     rcx, cs:WPP_GLOBAL_Control
0x140058eeb  cmp     rcx, rsi
0x140058eee  jnz     loc_140058F83
0x140058ef4  test    rbx, rbx
0x140058ef7  jz      loc_140058FCC
0x140058efd  cmp     dword ptr [rbx], 0C1FDF00Fh
0x140058f03  jnz     loc_140058FB9
0x140058f09  cmp     dword ptr [rbx+4], 0B0h
0x140058f10  jnz     loc_140058FB9
0x140058f16  mov     eax, [rbx+80h]
0x140058f1c  test    al, 14h
0x140058f1e  jz      loc_140058FB9
0x140058f24  call    cs:__imp_KeEnterCriticalRegion
0x140058f2b  nop     dword ptr [rax+rax+00h]
0x140058f30  nop
0x140058f31  mov     rcx, [rbx+98h]; this
0x140058f38  lock dec dword ptr [rcx+0B8h]
0x140058f3f  mov     rdx, rbx; Entry
0x140058f42  call    ?DeallocateIocb@CClfsKernelMarshallingContext@@AEAAXQEAU_LOGIOCB@@@Z; CClfsKernelMarshallingContext::DeallocateIocb(_LOGIOCB * const)
0x140058f47  jmp     short loc_140058F50
0x140058f49  lea     rsi, WPP_GLOBAL_Control
0x140058f50  call    cs:__imp_KeLeaveCriticalRegion
0x140058f57  nop     dword ptr [rax+rax+00h]
0x140058f5c  mov     rcx, cs:WPP_GLOBAL_Control
0x140058f63  cmp     rcx, rsi
0x140058f66  jz      short loc_140058F75
0x140058f68  test    dword ptr [rcx+2Ch], 4000000h
0x140058f6f  jnz     loc_140058FF8
0x140058f75  xor     eax, eax
0x140058f77  mov     rbx, [rsp+48h+arg_0]
0x140058f7c  add     rsp, 40h
0x140058f80  pop     rsi
0x140058f81  retn
0x140058f83  test    dword ptr [rcx+2Ch], 4000000h
0x140058f8a  jz      loc_140058EF4
0x140058f90  mov     edx, 119h
0x140058f95  mov     [rsp+48h+var_28], 223Bh
0x140058f9d  lea     r9, aClfsterminater; "ClfsTerminateReadLog"
0x140058fa4  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x140058fab  mov     rcx, [rcx+18h]
0x140058faf  call    WPP_SF_sd
0x140058fb4  jmp     loc_140058EF4
0x140058fb9  mov     rcx, cs:WPP_GLOBAL_Control
0x140058fc0  cmp     rcx, rsi
0x140058fc3  jnz     short loc_140059021
0x140058fc5  mov     eax, 0C000000Dh
0x140058fca  jmp     short loc_140058F77
0x140058fcc  mov     rcx, cs:WPP_GLOBAL_Control
0x140058fd3  cmp     rcx, rsi
0x140058fd6  jz      short loc_140058FC5
0x140058fd8  test    dword ptr [rcx+2Ch], 4000000h
0x140058fdf  jz      short loc_140058FC5
0x140058fe1  mov     edx, 11Ah
0x140058fe6  mov     [rsp+48h+var_20], 0C000000Dh
0x140058fee  mov     [rsp+48h+var_28], 2246h
0x140058ff6  jmp     short loc_14005903F
0x140058ff8  mov     edx, 11Ch
0x140058ffd  mov     [rsp+48h+var_28], 2284h
0x140059005  lea     r9, aClfsterminater; "ClfsTerminateReadLog"
0x14005900c  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x140059013  mov     rcx, [rcx+18h]
0x140059017  call    WPP_SF_sd
0x14005901c  jmp     loc_140058F75
0x140059021  test    dword ptr [rcx+2Ch], 4000000h
0x140059028  jz      short loc_140058FC5
0x14005902a  mov     edx, 11Bh
0x14005902f  mov     [rsp+48h+var_20], 0C000000Dh
0x140059037  mov     [rsp+48h+var_28], 2257h
0x14005903f  lea     r9, aClfsterminater; "ClfsTerminateReadLog"
0x140059046  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14005904d  mov     rcx, [rcx+18h]
0x140059051  call    WPP_SF_slD
0x140059056  jmp     loc_140058FC5
0x140079bc6  push    rbp
0x140079bc8  sub     rsp, 30h
0x140079bcc  mov     rbp, rdx
0x140079bcf  call    cs:__imp_KeLeaveCriticalRegion
0x140079bd6  nop     dword ptr [rax+rax+00h]
0x140079bdb  nop
0x140079bdc  add     rsp, 30h
0x140079be0  pop     rbp
0x140079be1  retn
```
