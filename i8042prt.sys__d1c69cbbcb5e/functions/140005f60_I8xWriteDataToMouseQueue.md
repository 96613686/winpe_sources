# I8xWriteDataToMouseQueue

- ea: `0x140005f60`
- end: `0x14000615b`
- name: `I8xWriteDataToMouseQueue`
- size: `507`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140005e90`

## callees

- `0x1400014e0`
- `0x140004530`
- `0x140005140`
- `0x140005f60`

## pseudocode

```c
char __fastcall I8xWriteDataToMouseQueue(__int64 a1, __int64 a2)
{
  __int64 v4; // rax

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      22,
      (__int64)WPP_15ecbda4bf0b3f54a10722a21773d3ef_Traceguids);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_qq(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        2,
        23,
        (__int64)WPP_15ecbda4bf0b3f54a10722a21773d3ef_Traceguids,
        *(_QWORD *)(a1 + 952),
        *(_QWORD *)(a1 + 960));
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          2,
          24,
          (__int64)WPP_15ecbda4bf0b3f54a10722a21773d3ef_Traceguids,
          *(_DWORD *)(a1 + 92));
    }
  }
  v4 = *(_QWORD *)(a1 + 952);
  if ( v4 == *(_QWORD *)(a1 + 960) && *(_DWORD *)(a1 + 92) )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        5,
        25,
        (__int64)WPP_15ecbda4bf0b3f54a10722a21773d3ef_Traceguids);
    return 0;
  }
  else
  {
    *(_OWORD *)v4 = *(_OWORD *)a2;
    *(_QWORD *)(v4 + 16) = *(_QWORD *)(a2 + 16);
    ++*(_DWORD *)(a1 + 92);
    *(_QWORD *)(a1 + 952) += 24LL;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        8,
        26,
        (__int64)WPP_15ecbda4bf0b3f54a10722a21773d3ef_Traceguids,
        *(_DWORD *)(a1 + 92));
    if ( *(_QWORD *)(a1 + 952) == *(_QWORD *)(a1 + 968) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_(
          WPP_GLOBAL_Control->DeviceExtension,
          a2,
          6,
          27,
          (__int64)WPP_15ecbda4bf0b3f54a10722a21773d3ef_Traceguids);
      *(_QWORD *)(a1 + 952) = *(_QWORD *)(a1 + 944);
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        7,
        28,
        (__int64)WPP_15ecbda4bf0b3f54a10722a21773d3ef_Traceguids);
    return 1;
  }
}

```

## disassembly

```asm
0x140005f60  push    rbx
0x140005f62  push    rbp
0x140005f63  push    rsi
0x140005f64  push    rdi
0x140005f65  sub     rsp, 48h
0x140005f69  mov     rdi, rdx
0x140005f6c  mov     rbx, rcx
0x140005f6f  lea     rsi, WPP_RECORDER_INITIALIZED
0x140005f76  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140005f7d  lea     rbp, WPP_15ecbda4bf0b3f54a10722a21773d3ef_Traceguids
0x140005f84  jnz     loc_140006057
0x140005f8a  mov     rax, [rbx+3B8h]
0x140005f91  cmp     rax, [rbx+3C0h]
0x140005f98  jz      loc_140006034
0x140005f9e  movups  xmm0, xmmword ptr [rdi]
0x140005fa1  movups  xmmword ptr [rax], xmm0
0x140005fa4  movsd   xmm1, qword ptr [rdi+10h]
0x140005fa9  movsd   qword ptr [rax+10h], xmm1
0x140005fae  inc     dword ptr [rbx+5Ch]
0x140005fb1  add     qword ptr [rbx+3B8h], 18h
0x140005fb9  mov     eax, [rbx+5Ch]
0x140005fbc  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140005fc3  jz      short loc_140005FEA
0x140005fc5  mov     rcx, cs:WPP_GLOBAL_Control
0x140005fcc  mov     r9d, 1Ah
0x140005fd2  mov     dword ptr [rsp+68h+var_40], eax
0x140005fd6  mov     r8d, 8
0x140005fdc  mov     [rsp+68h+var_48], rbp
0x140005fe1  mov     rcx, [rcx+40h]
0x140005fe5  call    WPP_RECORDER_SF_d
0x140005fea  mov     rax, [rbx+3C8h]
0x140005ff1  cmp     [rbx+3B8h], rax
0x140005ff8  jz      loc_14000611E
0x140005ffe  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140006005  jz      short loc_140006028
0x140006007  mov     rcx, cs:WPP_GLOBAL_Control
0x14000600e  mov     r9d, 1Ch
0x140006014  mov     r8d, 7
0x14000601a  mov     [rsp+68h+var_48], rbp
0x14000601f  mov     rcx, [rcx+40h]
0x140006023  call    WPP_RECORDER_SF_
0x140006028  mov     al, 1
0x14000602a  add     rsp, 48h
0x14000602e  pop     rdi
0x14000602f  pop     rsi
0x140006030  pop     rbp
0x140006031  pop     rbx
0x140006032  retn
0x140006034  cmp     dword ptr [rbx+5Ch], 0
0x140006038  jz      loc_140005F9E
0x14000603e  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140006045  jnz     loc_1400060F8
0x14000604b  xor     al, al
0x14000604d  add     rsp, 48h
0x140006051  pop     rdi
0x140006052  pop     rsi
0x140006053  pop     rbp
0x140006054  pop     rbx
0x140006055  retn
0x140006057  mov     rcx, cs:WPP_GLOBAL_Control
0x14000605e  mov     r9d, 16h
0x140006064  mov     r8d, 3
0x14000606a  mov     [rsp+68h+var_48], rbp
0x14000606f  mov     rcx, [rcx+40h]
0x140006073  call    WPP_RECORDER_SF_
0x140006078  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14000607f  jz      loc_140005F8A
0x140006085  mov     rax, [rbx+3C0h]
0x14000608c  mov     r9d, 17h
0x140006092  mov     rcx, cs:WPP_GLOBAL_Control
0x140006099  mov     r8d, 2
0x14000609f  mov     [rsp+68h+var_38], rax
0x1400060a4  mov     rax, [rbx+3B8h]
0x1400060ab  mov     [rsp+68h+var_40], rax
0x1400060b0  mov     rcx, [rcx+40h]
0x1400060b4  mov     [rsp+68h+var_48], rbp
0x1400060b9  call    WPP_RECORDER_SF_qq
0x1400060be  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400060c5  jz      loc_140005F8A
0x1400060cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400060d2  mov     r9d, 18h
0x1400060d8  mov     eax, [rbx+5Ch]
0x1400060db  mov     r8d, 2
0x1400060e1  mov     dword ptr [rsp+68h+var_40], eax
0x1400060e5  mov     [rsp+68h+var_48], rbp
0x1400060ea  mov     rcx, [rcx+40h]
0x1400060ee  call    WPP_RECORDER_SF_d
0x1400060f3  jmp     loc_140005F8A
0x1400060f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400060ff  mov     r9d, 19h
0x140006105  mov     r8d, 5
0x14000610b  mov     [rsp+68h+var_48], rbp
0x140006110  mov     rcx, [rcx+40h]
0x140006114  call    WPP_RECORDER_SF_
0x140006119  jmp     loc_14000604B
0x14000611e  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140006125  jz      short loc_140006148
0x140006127  mov     rcx, cs:WPP_GLOBAL_Control
0x14000612e  mov     r9d, 1Bh
0x140006134  mov     r8d, 6
0x14000613a  mov     [rsp+68h+var_48], rbp
0x14000613f  mov     rcx, [rcx+40h]
0x140006143  call    WPP_RECORDER_SF_
0x140006148  mov     rax, [rbx+3B0h]
0x14000614f  mov     [rbx+3B8h], rax
0x140006156  jmp     loc_140005FFE
```
