# HidpFdoCompleteSIrp

- ea: `0x180009bec`
- end: `0x180009ced`
- name: `HidpFdoCompleteSIrp`
- size: `257`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001a560`
- `0x18001a6b0`
- `0x18001c704`
- `0x180025bd0`

## callees

- `0x180009bec`
- `0x18000a15c`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x180009c11`
- `ntoskrnl!PoStartNextPowerIrp` at `0x180009c2e`
- `ntoskrnl!PoStartNextPowerIrp` at `0x180009c2e`
- `ntoskrnl!IofCompleteRequest` at `0x180009cd0`
- `ntoskrnl!IofCompleteRequest` at `0x180009cd0`

## pseudocode

```c
void __fastcall HidpFdoCompleteSIrp(_QWORD *a1, int *a2)
{
  IRP *v2; // rbx
  int v5; // edx
  int v6; // r8d

  v2 = (IRP *)a1[63];
  if ( v2 && v2 != MmBadPointer )
  {
    a1[63] = MmBadPointer;
    PoStartNextPowerIrp(v2);
    if ( a2 )
      v2->IoStatus.Status = *a2;
    LOBYTE(v5) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qqd(
        WPP_GLOBAL_Control->AttachedDevice,
        v5,
        v6,
        a1[84],
        4,
        9,
        42,
        (__int64)WPP_6b932ec2eebc3f4dfedaae6e204fdc15_Traceguids,
        *a1,
        (char)v2,
        v2->IoStatus.Status);
    }
    IofCompleteRequest(v2, 0);
  }
}

```

## disassembly

```asm
0x180009bec  mov     [rsp+arg_0], rbx
0x180009bf1  mov     [rsp+arg_8], rsi
0x180009bf6  push    rdi
0x180009bf7  sub     rsp, 60h
0x180009bfb  mov     rbx, [rcx+1F8h]
0x180009c02  mov     rdi, rdx
0x180009c05  mov     rsi, rcx
0x180009c08  test    rbx, rbx
0x180009c0b  jz      loc_180009CDC
0x180009c11  mov     rax, cs:MmBadPointer
0x180009c18  mov     rcx, [rax]
0x180009c1b  cmp     rbx, rcx
0x180009c1e  jz      loc_180009CDC
0x180009c24  mov     [rsi+1F8h], rcx
0x180009c2b  mov     rcx, rbx; Irp
0x180009c2e  call    cs:__imp_PoStartNextPowerIrp
0x180009c35  nop     dword ptr [rax+rax+00h]
0x180009c3a  test    rdi, rdi
0x180009c3d  jz      short loc_180009C44
0x180009c3f  mov     eax, [rdi]
0x180009c41  mov     [rbx+30h], eax
0x180009c44  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c4b  lea     rax, WPP_GLOBAL_Control
0x180009c52  cmp     rcx, rax
0x180009c55  jz      short loc_180009C6A
0x180009c57  test    dword ptr [rcx+2Ch], 100h
0x180009c5e  jz      short loc_180009C6A
0x180009c60  cmp     byte ptr [rcx+29h], 4
0x180009c64  jb      short loc_180009C6A
0x180009c66  mov     dl, 1
0x180009c68  jmp     short loc_180009C6C
0x180009c6a  xor     dl, dl
0x180009c6c  lea     rax, WPP_RECORDER_INITIALIZED
0x180009c73  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180009c7a  setnz   r8b
0x180009c7e  test    dl, dl
0x180009c80  jnz     short loc_180009C87
0x180009c82  test    r8b, r8b
0x180009c85  jz      short loc_180009CCB
0x180009c87  mov     eax, [rbx+30h]
0x180009c8a  mov     r9, [rsi+2A0h]
0x180009c91  mov     rcx, [rcx+18h]
0x180009c95  mov     [rsp+68h+var_18], eax
0x180009c99  mov     rax, [rsi]
0x180009c9c  mov     [rsp+68h+var_20], rbx
0x180009ca1  mov     [rsp+68h+var_28], rax
0x180009ca6  lea     rax, WPP_6b932ec2eebc3f4dfedaae6e204fdc15_Traceguids
0x180009cad  mov     [rsp+68h+var_30], rax
0x180009cb2  mov     [rsp+68h+var_38], 2Ah ; '*'
0x180009cb9  mov     [rsp+68h+var_40], 9
0x180009cc1  mov     [rsp+68h+var_48], 4
0x180009cc6  call    WPP_RECORDER_AND_TRACE_SF_qqd
0x180009ccb  xor     edx, edx; PriorityBoost
0x180009ccd  mov     rcx, rbx; Irp
0x180009cd0  call    cs:__imp_IofCompleteRequest
0x180009cd7  nop     dword ptr [rax+rax+00h]
0x180009cdc  mov     rbx, [rsp+68h+arg_0]
0x180009ce1  mov     rsi, [rsp+68h+arg_8]
0x180009ce6  add     rsp, 60h
0x180009cea  pop     rdi
0x180009ceb  retn
```
