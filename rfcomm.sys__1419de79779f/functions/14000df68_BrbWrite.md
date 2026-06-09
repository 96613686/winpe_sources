# BrbWrite

- ea: `0x14000df68`
- end: `0x14000e08b`
- name: `BrbWrite`
- size: `291`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140013abc`

## callees

- `0x140003bf4`
- `0x140003cb4`
- `0x14000df68`
- `0x14000e094`
- `0x14001fc70`

## pseudocode

```c
__int64 __fastcall BrbWrite(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, int a6, __int64 a7)
{
  __int64 v9; // r14
  unsigned int v11; // ebx
  __int64 v12; // rax

  v9 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      55,
      (__int64)WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids);
  if ( a3 )
  {
    v12 = (*(__int64 (__fastcall **)(__int64, __int64))(a1 + 312))(261, 1111647826);
    LODWORD(a2) = v12;
    if ( v12 )
    {
      *(_QWORD *)(v12 + 112) = v9;
      *(_QWORD *)(v12 + 144) = a4;
      v11 = 259;
      *(_QWORD *)(v12 + 136) = a5;
      *(_DWORD *)(v12 + 132) = a6;
      *(_QWORD *)(v12 + 120) = a3;
      *(_DWORD *)(v12 + 128) = 0;
      BrbpCallDriverAsync(
        a1,
        (_DWORD *)v12,
        (void (__fastcall *)(__int64, _DWORD *, __int64))&BrbpWriteComplete,
        a7,
        *(_QWORD *)(a7 + 8) + 240LL);
    }
    else
    {
      v11 = -1073741670;
    }
  }
  else
  {
    v11 = -1073741816;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      56,
      (__int64)WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids,
      v11);
  return v11;
}

```

## disassembly

```asm
0x14000df68  push    rbx
0x14000df6a  push    rbp
0x14000df6b  push    rsi
0x14000df6c  push    rdi
0x14000df6d  push    r13
0x14000df6f  push    r14
0x14000df71  push    r15
0x14000df73  sub     rsp, 30h
0x14000df77  mov     rbp, r9
0x14000df7a  mov     rdi, r8
0x14000df7d  mov     r14, rdx
0x14000df80  mov     rsi, rcx
0x14000df83  lea     r15, WPP_RECORDER_INITIALIZED
0x14000df8a  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000df91  lea     r13, WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids
0x14000df98  jz      short loc_14000DFB9
0x14000df9a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dfa1  mov     r9d, 37h ; '7'
0x14000dfa7  mov     [rsp+68h+var_48], r13
0x14000dfac  mov     rcx, [rcx+40h]
0x14000dfb0  lea     r8d, [r9-34h]
0x14000dfb4  call    WPP_RECORDER_SF_
0x14000dfb9  test    rdi, rdi
0x14000dfbc  jnz     short loc_14000DFC8
0x14000dfbe  mov     ebx, 0C0000008h
0x14000dfc3  jmp     loc_14000E04D
0x14000dfc8  mov     rax, [rsi+138h]
0x14000dfcf  mov     edx, 42426652h
0x14000dfd4  mov     ecx, 105h
0x14000dfd9  call    _guard_dispatch_icall
0x14000dfde  mov     rdx, rax
0x14000dfe1  test    rax, rax
0x14000dfe4  jnz     short loc_14000DFED
0x14000dfe6  mov     ebx, 0C000009Ah
0x14000dfeb  jmp     short loc_14000E04D
0x14000dfed  mov     r9, [rsp+68h+arg_30]
0x14000dff5  lea     r8, BrbpWriteComplete
0x14000dffc  mov     [rax+70h], r14
0x14000e000  mov     rcx, rsi
0x14000e003  mov     [rax+90h], rbp
0x14000e00a  mov     ebx, 103h
0x14000e00f  mov     rax, [rsp+68h+arg_20]
0x14000e017  mov     [rdx+88h], rax
0x14000e01e  mov     eax, [rsp+68h+arg_28]
0x14000e025  mov     [rdx+84h], eax
0x14000e02b  mov     [rdx+78h], rdi
0x14000e02f  mov     dword ptr [rdx+80h], 0
0x14000e039  mov     rax, [r9+8]
0x14000e03d  add     rax, 0F0h
0x14000e043  mov     [rsp+68h+var_48], rax
0x14000e048  call    BrbpCallDriverAsync
0x14000e04d  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14000e054  jz      short loc_14000E079
0x14000e056  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e05d  mov     r9d, 38h ; '8'
0x14000e063  mov     [rsp+68h+var_40], ebx
0x14000e067  mov     [rsp+68h+var_48], r13
0x14000e06c  mov     rcx, [rcx+40h]
0x14000e070  lea     r8d, [r9-35h]
0x14000e074  call    WPP_RECORDER_SF_d
0x14000e079  mov     eax, ebx
0x14000e07b  add     rsp, 30h
0x14000e07f  pop     r15
0x14000e081  pop     r14
0x14000e083  pop     r13
0x14000e085  pop     rdi
0x14000e086  pop     rsi
0x14000e087  pop     rbp
0x14000e088  pop     rbx
0x14000e089  retn
```
