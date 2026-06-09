# DfscConnOpenIpcConnection

- ea: `0x140027650`
- end: `0x1400276f0`
- name: `DfscConnOpenIpcConnection`
- size: `160`
- prototype: `NTSTATUS __fastcall(__int64, __int64, __int64, int, __int64, char, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140011fd8`

## callees

- `0x140027650`

## import_xrefs

- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1400276d1`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x1400276d1`

## pseudocode

```c
NTSTATUS __fastcall DfscConnOpenIpcConnection(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        char a6,
        __int64 a7,
        __int64 a8)
{
  NTSTATUS result; // eax
  _QWORD v9[3]; // [rsp+30h] [rbp-58h] BYREF
  int v10; // [rsp+48h] [rbp-40h]
  int v11; // [rsp+4Ch] [rbp-3Ch]
  __int64 v12; // [rsp+50h] [rbp-38h]
  __int64 v13; // [rsp+58h] [rbp-30h]
  char v14; // [rsp+60h] [rbp-28h]
  int v15; // [rsp+61h] [rbp-27h]
  __int16 v16; // [rsp+65h] [rbp-23h]
  char v17; // [rsp+67h] [rbp-21h]
  __int64 v18; // [rsp+68h] [rbp-20h]
  __int64 v19; // [rsp+70h] [rbp-18h]

  v12 = a5;
  v13 = a8;
  v9[0] = a1;
  v9[1] = a2;
  v9[2] = a3;
  v10 = a4;
  v11 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v19 = 0;
  v14 = a6;
  v18 = a7;
  result = KeExpandKernelStackAndCalloutEx(
             (PEXPAND_STACK_CALLOUT)DfscConnOpenIpcConnectionCallout,
             v9,
             0x6000u,
             0,
             Context);
  if ( !result )
    return v19;
  return result;
}

```

## disassembly

```asm
0x140027650  mov     r11, rsp
0x140027653  sub     rsp, 88h
0x14002765a  mov     rax, [rsp+88h+arg_20]
0x140027662  xor     r10d, r10d
0x140027665  mov     [r11-38h], rax
0x140027669  mov     rax, [rsp+88h+arg_38]
0x140027671  mov     [r11-30h], rax
0x140027675  movzx   eax, [rsp+88h+arg_28]
0x14002767d  mov     [r11-58h], rcx
0x140027681  lea     rcx, DfscConnOpenIpcConnectionCallout; Callout
0x140027688  mov     [r11-50h], rdx
0x14002768c  lea     rdx, [r11-58h]; Parameter
0x140027690  mov     [r11-48h], r8
0x140027694  mov     r8d, 6000h; Size
0x14002769a  mov     [r11-40h], r9d
0x14002769e  xor     r9d, r9d; Wait
0x1400276a1  mov     [r11-3Ch], r10d
0x1400276a5  mov     [r11-27h], r10d
0x1400276a9  mov     [r11-23h], r10w
0x1400276ae  mov     [r11-21h], r10b
0x1400276b2  mov     [r11-18h], r10
0x1400276b6  mov     [rsp+88h+var_28], al
0x1400276ba  mov     rax, [rsp+88h+arg_30]
0x1400276c2  mov     [r11-20h], rax
0x1400276c6  mov     rax, cs:Context
0x1400276cd  mov     [r11-68h], rax
0x1400276d1  call    cs:__imp_KeExpandKernelStackAndCalloutEx
0x1400276d8  nop     dword ptr [rax+rax+00h]
0x1400276dd  test    eax, eax
0x1400276df  jz      short loc_1400276EA
0x1400276e1  add     rsp, 88h
0x1400276e8  retn
0x1400276ea  mov     eax, dword ptr [rsp+88h+var_18]
0x1400276ee  jmp     short loc_1400276E1
```
