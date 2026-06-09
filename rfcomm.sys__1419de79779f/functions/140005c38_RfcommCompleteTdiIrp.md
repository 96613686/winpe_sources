# RfcommCompleteTdiIrp

- ea: `0x140005c38`
- end: `0x140005cf5`
- name: `RfcommCompleteTdiIrp`
- size: `189`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `16`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140001eec`
- `0x1400031d0`
- `0x140005350`
- `0x140005cfc`
- `0x140007350`
- `0x14000877c`
- `0x140008ac0`
- `0x140008fd4`
- `0x1400097f4`
- `0x14000aca0`
- `0x140011050`
- `0x140011634`
- `0x14001204c`
- `0x1400121d4`
- `0x140013d20`
- `0x140013fb4`

## callees

- `0x140005c38`
- `0x14000c4ac`
- `0x14000c5e0`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140005cd8`
- `ntoskrnl!IofCompleteRequest` at `0x140005cd8`

## pseudocode

```c
void __fastcall RfcommCompleteTdiIrp(PIRP Irp, int a2, unsigned __int64 a3, int a4)
{
  int v5; // esi

  v5 = a2;
  LOBYTE(a2) = Irp->Tail.Overlay.CurrentStackLocation->MajorFunction;
  if ( (_BYTE)a2 == 15 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qcdi(WPP_GLOBAL_Control->DeviceExtension, a2, a3, a4);
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_qccdi(WPP_GLOBAL_Control->DeviceExtension, a2, a3, a4);
  }
  Irp->IoStatus.Status = v5;
  Irp->IoStatus.Information = a3;
  IofCompleteRequest(Irp, 2);
}

```

## disassembly

```asm
0x140005c38  mov     r11, rsp
0x140005c3b  mov     [r11+8], rbx
0x140005c3f  mov     [r11+10h], rsi
0x140005c43  push    rdi
0x140005c44  sub     rsp, 50h
0x140005c48  mov     rbx, rcx
0x140005c4b  mov     esi, edx
0x140005c4d  mov     rcx, [rcx+0B8h]
0x140005c54  mov     rdi, r8
0x140005c57  mov     dl, [rcx]
0x140005c59  cmp     dl, 0Fh
0x140005c5c  jnz     short loc_140005C93
0x140005c5e  lea     rax, WPP_RECORDER_INITIALIZED
0x140005c65  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140005c6c  jz      short loc_140005CCC
0x140005c6e  mov     al, [rcx+1]
0x140005c71  mov     rcx, cs:WPP_GLOBAL_Control
0x140005c78  mov     [r11-18h], r8
0x140005c7c  mov     [rsp+58h+var_20], esi
0x140005c80  mov     [rsp+58h+var_28], al
0x140005c84  mov     rcx, [rcx+40h]
0x140005c88  mov     [r11-30h], rbx
0x140005c8c  call    WPP_RECORDER_SF_qcdi
0x140005c91  jmp     short loc_140005CCC
0x140005c93  lea     rax, WPP_RECORDER_INITIALIZED
0x140005c9a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140005ca1  jz      short loc_140005CCC
0x140005ca3  mov     al, [rcx+1]
0x140005ca6  mov     rcx, cs:WPP_GLOBAL_Control
0x140005cad  mov     [rsp+58h+var_10], rdi
0x140005cb2  mov     [rsp+58h+var_18], esi
0x140005cb6  mov     byte ptr [rsp+58h+var_20], al
0x140005cba  mov     rcx, [rcx+40h]
0x140005cbe  mov     [rsp+58h+var_28], dl
0x140005cc2  mov     [rsp+58h+var_30], rbx
0x140005cc7  call    WPP_RECORDER_SF_qccdi
0x140005ccc  mov     dl, 2; PriorityBoost
0x140005cce  mov     [rbx+30h], esi
0x140005cd1  mov     rcx, rbx; Irp
0x140005cd4  mov     [rbx+38h], rdi
0x140005cd8  call    cs:__imp_IofCompleteRequest
0x140005cdf  nop     dword ptr [rax+rax+00h]
0x140005ce4  mov     rbx, [rsp+58h+arg_0]
0x140005ce9  mov     rsi, [rsp+58h+arg_8]
0x140005cee  add     rsp, 50h
0x140005cf2  pop     rdi
0x140005cf3  retn
```
