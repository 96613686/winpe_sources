# lldpCreateDriverWdf

- ea: `0x1400133dc`
- end: `0x1400134c2`
- name: `lldpCreateDriverWdf`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140013350`

## callees

- `0x140004b00`
- `0x140006670`
- `0x1400133dc`

## pseudocode

```c
__int64 __fastcall lldpCreateDriverWdf(__int64 a1, __int64 a2)
{
  int v2; // ebx
  _QWORD v4[4]; // [rsp+40h] [rbp-9h] BYREF
  __int128 v5; // [rsp+60h] [rbp+17h] BYREF
  __int64 v6; // [rsp+70h] [rbp+27h]
  __int64 v7; // [rsp+78h] [rbp+2Fh]
  __int128 v8; // [rsp+80h] [rbp+37h]
  __int64 v9; // [rsp+90h] [rbp+47h]

  v4[0] = 32;
  v6 = 0;
  v4[2] = lldpDriverUnloadWdf;
  v9 = 0;
  v5 = 0;
  v4[3] = 1;
  v4[1] = 0;
  v8 = 0;
  LODWORD(v5) = 56;
  v7 = 0x100000002LL;
  v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int128 *, _QWORD *, ULONG *))(WdfFunctions_01015 + 928))(
         WdfDriverGlobals,
         a1,
         a2,
         &v5,
         v4,
         &WPP_MAIN_CB.ActiveThreadCount);
  if ( v2 < 0 && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_ea1b45b0a6943981c34a08d8d3c26e2c_Traceguids, (unsigned int)v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400133dc  mov     [rsp-8+arg_0], rbx
0x1400133e1  push    rbp
0x1400133e2  lea     rbp, [rsp-57h]
0x1400133e7  sub     rsp, 0A0h
0x1400133ee  xorps   xmm0, xmm0
0x1400133f1  mov     [rbp+57h+var_60], 20h ; ' '
0x1400133f9  movups  [rbp+57h+var_30], xmm0
0x1400133fd  mov     r8d, 1
0x140013403  lea     rax, lldpDriverUnloadWdf
0x14001340a  mov     dword ptr [rbp+57h+var_30+0Ch], r8d
0x14001340e  lea     r9, [rbp+57h+var_40]
0x140013412  mov     [rbp+57h+var_50], rax
0x140013416  lea     r8, WPP_MAIN_CB.ActiveThreadCount
0x14001341d  xor     eax, eax
0x14001341f  mov     [rsp+0A0h+var_78], r8
0x140013424  mov     [rbp+57h+var_10], rax
0x140013428  lea     r8, [rbp+57h+var_60]
0x14001342c  mov     rax, cs:WdfFunctions_01015
0x140013433  movups  [rbp+57h+var_40], xmm0
0x140013437  mov     [rsp+0A0h+var_80], r8
0x14001343c  mov     r8, rdx
0x14001343f  mov     rdx, rcx
0x140013442  mov     [rbp+57h+var_48], 1
0x14001344a  mov     rcx, cs:WdfDriverGlobals
0x140013451  mov     [rbp+57h+var_58], 0
0x140013459  movups  [rbp+57h+var_20], xmm0
0x14001345d  mov     dword ptr [rbp+57h+var_40], 38h ; '8'
0x140013464  mov     dword ptr [rbp+57h+var_30+8], 2
0x14001346b  mov     rax, [rax+3A0h]
0x140013472  call    _guard_dispatch_icall
0x140013477  mov     ebx, eax
0x140013479  test    eax, eax
0x14001347b  jns     short loc_1400134AE
0x14001347d  mov     rcx, cs:WPP_GLOBAL_Control
0x140013484  lea     rax, WPP_GLOBAL_Control
0x14001348b  cmp     rcx, rax
0x14001348e  jz      short loc_1400134AE
0x140013490  cmp     byte ptr [rcx+29h], 2
0x140013494  jb      short loc_1400134AE
0x140013496  mov     rcx, [rcx+18h]
0x14001349a  lea     r8, WPP_ea1b45b0a6943981c34a08d8d3c26e2c_Traceguids
0x1400134a1  mov     edx, 0Ah
0x1400134a6  mov     r9d, ebx
0x1400134a9  call    WPP_SF_d
0x1400134ae  mov     eax, ebx
0x1400134b0  mov     rbx, [rsp+0A0h+arg_0]
0x1400134b8  add     rsp, 0A0h
0x1400134bf  pop     rbp
0x1400134c0  retn
```
