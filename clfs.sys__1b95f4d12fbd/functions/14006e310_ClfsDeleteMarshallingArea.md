# ClfsDeleteMarshallingArea

- ea: `0x14006e310`
- end: `0x14006e4ab`
- name: `ClfsDeleteMarshallingArea`
- size: `411`
- prototype: `NTSTATUS __stdcall(PVOID pvMarshalContext)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x14000ed64`
- `0x140011d90`
- `0x14006e310`
- `0x14006e4b4`
- `0x14006e500`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14006e383`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14006e383`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006e3b2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007ba48`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14006e3b2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14007ba48`

## string_xrefs

- `0x14006e3e2`: `ClfsDeleteMarshallingArea`
- `0x14006e420`: `ClfsDeleteMarshallingArea`
- `0x14006e48f`: `ClfsDeleteMarshallingArea`

## pseudocode

```c
NTSTATUS __stdcall ClfsDeleteMarshallingArea(PVOID pvMarshalContext)
{
  if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      157,
      (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
      (unsigned int)"ClfsDeleteMarshallingArea",
      111);
  }
  if ( !pvMarshalContext )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        158,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsDeleteMarshallingArea",
        123,
        -1073741811);
    }
    return -1073741811;
  }
  if ( *(_DWORD *)pvMarshalContext != -1040322550 || *((_DWORD *)pvMarshalContext + 1) != 200 )
  {
    if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
    {
      WPP_SF_slD(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        159,
        (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
        (unsigned int)"ClfsDeleteMarshallingArea",
        140,
        -1073741811);
    }
    return -1073741811;
  }
  KeEnterCriticalRegion();
  CClfsKernelMarshallingContext::PrepareForDelete((CClfsKernelMarshallingContext *)pvMarshalContext);
  CClfsKernelMarshallingContext::Release(pvMarshalContext);
  KeLeaveCriticalRegion();
  if ( WPP_GLOBAL_Control != (CClfsBaseFile *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000000) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      160,
      (unsigned int)WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids,
      (unsigned int)"ClfsDeleteMarshallingArea",
      188);
  }
  return 0;
}

```

## disassembly

```asm
0x14006e310  mov     [rsp+arg_8], rbx
0x14006e315  mov     [rsp+arg_10], rsi
0x14006e31a  mov     [rsp+arg_0], rcx
0x14006e31f  push    r14
0x14006e321  sub     rsp, 30h
0x14006e325  mov     rbx, rcx
0x14006e328  lea     rsi, WPP_GLOBAL_Control
0x14006e32f  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e336  cmp     rcx, rsi
0x14006e339  jnz     loc_14006E3C8
0x14006e33f  test    rbx, rbx
0x14006e342  jz      loc_14006E439
0x14006e348  cmp     dword ptr [rbx], 0C1FDF00Ah
0x14006e34e  jz      short loc_14006E377
0x14006e350  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e357  cmp     rcx, rsi
0x14006e35a  jnz     loc_14006E46D
0x14006e360  mov     eax, 0C000000Dh
0x14006e365  mov     rbx, [rsp+38h+arg_8]
0x14006e36a  mov     rsi, [rsp+38h+arg_10]
0x14006e36f  add     rsp, 30h
0x14006e373  pop     r14
0x14006e375  retn
0x14006e377  xor     r14d, r14d
0x14006e37a  cmp     dword ptr [rbx+4], 0C8h
0x14006e381  jnz     short loc_14006E350
0x14006e383  call    cs:__imp_KeEnterCriticalRegion
0x14006e38a  nop     dword ptr [rax+rax+00h]
0x14006e38f  nop
0x14006e390  mov     rcx, rbx; this
0x14006e393  call    ?PrepareForDelete@CClfsKernelMarshallingContext@@QEAAJXZ; CClfsKernelMarshallingContext::PrepareForDelete(void)
0x14006e398  jmp     short loc_14006E3A9
0x14006e39a  mov     r14d, eax
0x14006e39d  lea     rsi, WPP_GLOBAL_Control
0x14006e3a4  mov     rbx, [rsp+38h+arg_0]
0x14006e3a9  mov     rcx, rbx; P
0x14006e3ac  call    ?Release@CClfsKernelMarshallingContext@@QEAAKXZ; CClfsKernelMarshallingContext::Release(void)
0x14006e3b1  nop
0x14006e3b2  call    cs:__imp_KeLeaveCriticalRegion
0x14006e3b9  nop     dword ptr [rax+rax+00h]
0x14006e3be  test    r14d, r14d
0x14006e3c1  jns     short loc_14006E3FE
0x14006e3c3  mov     eax, r14d
0x14006e3c6  jmp     short loc_14006E365
0x14006e3c8  mov     eax, [rcx+2Ch]
0x14006e3cb  bt      eax, 1Ah
0x14006e3cf  jnb     loc_14006E33F
0x14006e3d5  mov     edx, 9Dh
0x14006e3da  mov     [rsp+38h+var_18], 126Fh
0x14006e3e2  lea     r9, aClfsdeletemars; "ClfsDeleteMarshallingArea"
0x14006e3e9  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14006e3f0  mov     rcx, [rcx+18h]
0x14006e3f4  call    WPP_SF_sd
0x14006e3f9  jmp     loc_14006E33F
0x14006e3fe  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e405  cmp     rcx, rsi
0x14006e408  jz      short loc_14006E3C3
0x14006e40a  test    dword ptr [rcx+2Ch], 4000000h
0x14006e411  jz      short loc_14006E3C3
0x14006e413  mov     edx, 0A0h
0x14006e418  mov     [rsp+38h+var_18], 12BCh
0x14006e420  lea     r9, aClfsdeletemars; "ClfsDeleteMarshallingArea"
0x14006e427  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14006e42e  mov     rcx, [rcx+18h]
0x14006e432  call    WPP_SF_sd
0x14006e437  jmp     short loc_14006E3C3
0x14006e439  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e440  cmp     rcx, rsi
0x14006e443  jz      loc_14006E360
0x14006e449  test    dword ptr [rcx+2Ch], 4000000h
0x14006e450  jz      loc_14006E360
0x14006e456  mov     edx, 9Eh
0x14006e45b  mov     [rsp+38h+var_10], 0C000000Dh
0x14006e463  mov     [rsp+38h+var_18], 127Bh
0x14006e46b  jmp     short loc_14006E48F
0x14006e46d  test    dword ptr [rcx+2Ch], 4000000h
0x14006e474  jz      loc_14006E360
0x14006e47a  mov     edx, 9Fh
0x14006e47f  mov     [rsp+38h+var_10], 0C000000Dh
0x14006e487  mov     [rsp+38h+var_18], 128Ch
0x14006e48f  lea     r9, aClfsdeletemars; "ClfsDeleteMarshallingArea"
0x14006e496  lea     r8, WPP_a9b578d2f85634512c30dd5bad26339c_Traceguids
0x14006e49d  mov     rcx, [rcx+18h]
0x14006e4a1  call    WPP_SF_slD
0x14006e4a6  jmp     loc_14006E360
0x14007ba3f  push    rbp
0x14007ba41  sub     rsp, 30h
0x14007ba45  mov     rbp, rdx
0x14007ba48  call    cs:__imp_KeLeaveCriticalRegion
0x14007ba4f  nop     dword ptr [rax+rax+00h]
0x14007ba54  nop
0x14007ba55  add     rsp, 30h
0x14007ba59  pop     rbp
0x14007ba5a  retn
```
