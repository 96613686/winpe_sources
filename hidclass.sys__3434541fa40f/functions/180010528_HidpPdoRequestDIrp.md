# HidpPdoRequestDIrp

- ea: `0x180010528`
- end: `0x18001080b`
- name: `HidpPdoRequestDIrp`
- size: `739`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800100e4`
- `0x180010454`

## callees

- `0x180010528`
- `0x180013860`
- `0x18001952c`

## import_xrefs

- `ntoskrnl!PoRequestPowerIrp` at `0x1800105f3`
- `ntoskrnl!PoRequestPowerIrp` at `0x1800105f3`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x180010573`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x180010573`

## pseudocode

```c
NTSTATUS __fastcall HidpPdoRequestDIrp(__int64 a1, POWER_STATE a2, REQUEST_POWER_COMPLETE *a3)
{
  __int64 Context; // rsi
  char v6; // di
  NTSTATUS result; // eax
  int v8; // edx
  int v9; // r8d
  int v10; // edx
  int v11; // r8d
  __int64 v12; // r8
  __int64 v13; // rax

  Context = *(_QWORD *)(a1 + 64) + 32LL;
  v6 = 1;
  result = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(*(_QWORD *)(a1 + 64) + 672LL), (PVOID)0x50444954, File, 1u, 0x20u);
  if ( result < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || (LOBYTE(v8) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    {
      LOBYTE(v8) = 0;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED || !LOWORD(WPP_GLOBAL_Control->DeviceType) )
      v6 = 0;
    if ( (_BYTE)v8 || v6 )
    {
      v12 = *(_QWORD *)(a1 + 64);
      v13 = *(_QWORD *)(v12 + 32);
      LOBYTE(v12) = v6;
      result = WPP_RECORDER_AND_TRACE_SF_qdqL(
                 WPP_GLOBAL_Control->AttachedDevice,
                 v8,
                 v12,
                 *(_QWORD *)(Context + 672),
                 5,
                 9,
                 12,
                 (__int64)WPP_6b932ec2eebc3f4dfedaae6e204fdc15_Traceguids,
                 v13,
                 *(_DWORD *)(a1 + 8),
                 *(_QWORD *)(a1 + 48),
                 LOBYTE(a2.SystemState) - 1);
    }
    goto LABEL_19;
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
    || (LOBYTE(v8) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
  {
    LOBYTE(v8) = 0;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    || (LOBYTE(v9) = 1, !LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v9) = 0;
  }
  if ( (_BYTE)v8 || (_BYTE)v9 )
    WPP_RECORDER_AND_TRACE_SF_qdqL(
      WPP_GLOBAL_Control->AttachedDevice,
      v8,
      v9,
      *(_QWORD *)(Context + 672),
      5,
      9,
      10,
      (__int64)WPP_6b932ec2eebc3f4dfedaae6e204fdc15_Traceguids,
      *(_QWORD *)(*(_QWORD *)(a1 + 64) + 32LL),
      *(_DWORD *)(a1 + 8),
      *(_QWORD *)(a1 + 48),
      LOBYTE(a2.SystemState) - 1);
  result = PoRequestPowerIrp(*(PDEVICE_OBJECT *)(a1 + 48), 2u, a2, a3, (PVOID)Context, 0);
  v11 = 0;
  if ( result < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || (LOBYTE(v10) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 5u) )
    {
      LOBYTE(v10) = 0;
    }
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED || !LOWORD(WPP_GLOBAL_Control->DeviceType) )
      v6 = 0;
    if ( (_BYTE)v10 || v6 )
    {
      LOBYTE(v11) = v6;
      result = WPP_RECORDER_AND_TRACE_SF_qdqLd(
                 WPP_GLOBAL_Control->AttachedDevice,
                 v10,
                 v11,
                 *(_QWORD *)(Context + 672),
                 5,
                 9,
                 11,
                 (__int64)WPP_6b932ec2eebc3f4dfedaae6e204fdc15_Traceguids,
                 *(_QWORD *)(*(_QWORD *)(a1 + 64) + 32LL),
                 *(_DWORD *)(a1 + 8),
                 *(_QWORD *)(a1 + 48),
                 LOBYTE(a2.SystemState) - 1,
                 result);
    }
LABEL_19:
    _InterlockedDecrement((volatile signed __int32 *)(Context + 464));
  }
  return result;
}

```

## disassembly

```asm
0x180010528  mov     rax, rsp
0x18001052b  mov     [rax+8], rbx
0x18001052f  mov     [rax+10h], rsi
0x180010533  mov     [rax+18h], r8
0x180010537  push    rdi
0x180010538  push    r12
0x18001053a  push    r13
0x18001053c  push    r14
0x18001053e  push    r15
0x180010540  sub     rsp, 70h
0x180010544  mov     rsi, [rcx+40h]
0x180010548  lea     r8, File; File
0x18001054f  mov     ebx, edx
0x180010551  mov     dword ptr [rax-78h], 20h ; ' '
0x180010558  mov     r15, rcx
0x18001055b  add     rsi, 20h ; ' '
0x18001055f  mov     edi, 1
0x180010564  mov     edx, 50444954h; Tag
0x180010569  mov     r9d, edi; Line
0x18001056c  lea     rcx, [rsi+280h]; RemoveLock
0x180010573  call    cs:__imp_IoAcquireRemoveLockEx
0x18001057a  nop     dword ptr [rax+rax+00h]
0x18001057f  xor     r9d, r9d
0x180010582  test    eax, eax
0x180010584  js      loc_180010631
0x18001058a  mov     rcx, cs:WPP_GLOBAL_Control
0x180010591  lea     r14, WPP_GLOBAL_Control
0x180010598  cmp     rcx, r14
0x18001059b  jz      short loc_1800105AA
0x18001059d  test    dword ptr [rcx+2Ch], 100h
0x1800105a4  jnz     loc_18001067C
0x1800105aa  mov     dl, r9b
0x1800105ad  lea     r12, WPP_RECORDER_INITIALIZED
0x1800105b4  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1800105bb  jnz     short loc_180010625
0x1800105bd  mov     r8b, r9b
0x1800105c0  lea     r13, WPP_6b932ec2eebc3f4dfedaae6e204fdc15_Traceguids
0x1800105c7  test    dl, dl
0x1800105c9  jnz     loc_18001068E
0x1800105cf  test    r8b, r8b
0x1800105d2  jnz     loc_18001068E
0x1800105d8  mov     rcx, [r15+30h]; DeviceObject
0x1800105dc  mov     r8d, ebx; PowerState
0x1800105df  mov     [rsp+98h+Irp], r9; Irp
0x1800105e4  mov     dl, 2; MinorFunction
0x1800105e6  mov     r9, [rsp+98h+CompletionFunction]; CompletionFunction
0x1800105ee  mov     [rsp+98h+Context], rsi; Context
0x1800105f3  call    cs:__imp_PoRequestPowerIrp
0x1800105fa  nop     dword ptr [rax+rax+00h]
0x1800105ff  xor     r8d, r8d
0x180010602  test    eax, eax
0x180010604  js      loc_1800106E4
0x18001060a  lea     r11, [rsp+98h+var_28]
0x18001060f  mov     rbx, [r11+30h]
0x180010613  mov     rsi, [r11+38h]
0x180010617  mov     rsp, r11
0x18001061a  pop     r15
0x18001061c  pop     r14
0x18001061e  pop     r13
0x180010620  pop     r12
0x180010622  pop     rdi
0x180010623  retn
0x180010625  mov     r8b, dil
0x180010628  cmp     [rcx+48h], r9w
0x18001062d  jnz     short loc_1800105C0
0x18001062f  jmp     short loc_1800105BD
0x180010631  mov     rcx, cs:WPP_GLOBAL_Control
0x180010638  lea     r14, WPP_GLOBAL_Control
0x18001063f  cmp     rcx, r14
0x180010642  jnz     loc_180010780
0x180010648  mov     dl, r9b
0x18001064b  lea     r12, WPP_RECORDER_INITIALIZED
0x180010652  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180010659  jnz     loc_18001079F
0x18001065f  mov     dil, r9b
0x180010662  test    dl, dl
0x180010664  jnz     loc_1800107AF
0x18001066a  test    dil, dil
0x18001066d  jnz     loc_1800107AF
0x180010673  lock dec dword ptr [rsi+1D0h]
0x18001067a  jmp     short loc_18001060A
0x18001067c  cmp     byte ptr [rcx+29h], 5
0x180010680  mov     dl, dil
0x180010683  jnb     loc_1800105AD
0x180010689  jmp     loc_1800105AA
0x18001068e  mov     r9, [r15+40h]
0x180010692  lea     eax, [rbx-1]
0x180010695  mov     rcx, [rcx+18h]
0x180010699  mov     [rsp+98h+var_40], eax
0x18001069d  mov     rax, [r15+30h]
0x1800106a1  mov     [rsp+98h+var_48], rax
0x1800106a6  mov     eax, [r15+8]
0x1800106aa  mov     [rsp+98h+var_50], eax
0x1800106ae  mov     rax, [r9+20h]
0x1800106b2  mov     r9, [rsi+2A0h]
0x1800106b9  mov     [rsp+98h+var_58], rax
0x1800106be  mov     [rsp+98h+var_60], r13
0x1800106c3  mov     [rsp+98h+var_68], 0Ah
0x1800106ca  mov     dword ptr [rsp+98h+Irp], 9
0x1800106d2  mov     byte ptr [rsp+98h+Context], 5
0x1800106d7  call    WPP_RECORDER_AND_TRACE_SF_qdqL
0x1800106dc  xor     r9d, r9d
0x1800106df  jmp     loc_1800105D8
0x1800106e4  mov     r10, cs:WPP_GLOBAL_Control
0x1800106eb  cmp     r10, r14
0x1800106ee  jz      short loc_180010704
0x1800106f0  test    dword ptr [r10+2Ch], 100h
0x1800106f8  jz      short loc_180010704
0x1800106fa  cmp     byte ptr [r10+29h], 5
0x1800106ff  mov     dl, dil
0x180010702  jnb     short loc_180010707
0x180010704  mov     dl, r8b
0x180010707  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18001070e  jz      short loc_180010717
0x180010710  cmp     [r10+48h], r8w
0x180010715  jnz     short loc_18001071A
0x180010717  mov     dil, r8b
0x18001071a  test    dl, dl
0x18001071c  jnz     short loc_180010727
0x18001071e  test    dil, dil
0x180010721  jz      loc_180010673
0x180010727  mov     r9, [r15+40h]
0x18001072b  dec     ebx
0x18001072d  mov     rcx, [r10+18h]
0x180010731  mov     r8b, dil
0x180010734  mov     [rsp+98h+var_38], eax
0x180010738  mov     rax, [r15+30h]
0x18001073c  mov     [rsp+98h+var_40], ebx
0x180010740  mov     [rsp+98h+var_48], rax
0x180010745  mov     eax, [r15+8]
0x180010749  mov     [rsp+98h+var_50], eax
0x18001074d  mov     rax, [r9+20h]
0x180010751  mov     r9, [rsi+2A0h]
0x180010758  mov     [rsp+98h+var_58], rax
0x18001075d  mov     [rsp+98h+var_60], r13
0x180010762  mov     [rsp+98h+var_68], 0Bh
0x180010769  mov     dword ptr [rsp+98h+Irp], 9
0x180010771  mov     byte ptr [rsp+98h+Context], 5
0x180010776  call    WPP_RECORDER_AND_TRACE_SF_qdqLd
0x18001077b  jmp     loc_180010673
0x180010780  test    dword ptr [rcx+2Ch], 100h
0x180010787  jz      loc_180010648
0x18001078d  cmp     byte ptr [rcx+29h], 5
0x180010791  mov     dl, dil
0x180010794  jnb     loc_18001064B
0x18001079a  jmp     loc_180010648
0x18001079f  cmp     [rcx+48h], r9w
0x1800107a4  jnz     loc_180010662
0x1800107aa  jmp     loc_18001065F
0x1800107af  mov     rax, [r15+30h]
0x1800107b3  lea     r13, WPP_6b932ec2eebc3f4dfedaae6e204fdc15_Traceguids
0x1800107ba  mov     r8, [r15+40h]
0x1800107be  dec     ebx
0x1800107c0  mov     r9, [rsi+2A0h]
0x1800107c7  mov     rcx, [rcx+18h]
0x1800107cb  mov     [rsp+98h+var_40], ebx
0x1800107cf  mov     [rsp+98h+var_48], rax
0x1800107d4  mov     eax, [r15+8]
0x1800107d8  mov     [rsp+98h+var_50], eax
0x1800107dc  mov     rax, [r8+20h]
0x1800107e0  mov     r8b, dil
0x1800107e3  mov     [rsp+98h+var_58], rax
0x1800107e8  mov     [rsp+98h+var_60], r13
0x1800107ed  mov     [rsp+98h+var_68], 0Ch
0x1800107f4  mov     dword ptr [rsp+98h+Irp], 9
0x1800107fc  mov     byte ptr [rsp+98h+Context], 5
0x180010801  call    WPP_RECORDER_AND_TRACE_SF_qdqL
0x180010806  jmp     loc_180010673
```
