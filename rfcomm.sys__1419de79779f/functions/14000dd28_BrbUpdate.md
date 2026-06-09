# BrbUpdate

- ea: `0x14000dd28`
- end: `0x14000de89`
- name: `BrbUpdate`
- size: `353`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x140005f2c`
- `0x140018e9c`

## callees

- `0x140004b4c`
- `0x1400051b4`
- `0x14000dd28`
- `0x14000e094`
- `0x14001bfa8`
- `0x14001fc70`

## pseudocode

```c
__int64 __fastcall BrbUpdate(__int64 a1)
{
  __int64 v1; // r14
  unsigned int v3; // edi
  __int64 v4; // r15
  __int64 v5; // r12
  int v6; // edx
  __int64 v7; // rbp
  int v8; // ecx
  int v9; // esi
  void *DeviceExtension; // rbx
  const char *v11; // rax
  int v12; // edx

  v1 = *(_QWORD *)(a1 + 280);
  if ( v1 )
  {
    v4 = *(_QWORD *)(a1 + 72);
    v5 = *(_QWORD *)(a1 + 264);
    v7 = (*(__int64 (__fastcall **)(__int64, __int64))(v4 + 312))(262, 1111647826);
    if ( v7 )
    {
      v8 = *(_DWORD *)(a1 + 472);
      v9 = 0;
      v3 = 259;
      if ( (v8 & 0x20000) != 0 && !_bittest((const signed __int32 *)(a1 + 476), 0x11u) )
        v9 = 393216;
      if ( (v8 & 0x40000) != 0 && !_bittest((const signed __int32 *)(a1 + 476), 0x12u) )
        v9 = 393216;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          v6,
          3,
          44,
          (__int64)WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids,
          v1,
          v9);
      *(_QWORD *)(v7 + 112) = v5;
      *(_QWORD *)(v7 + 120) = v1;
      *(_DWORD *)(v7 + 128) = v9;
      *(_DWORD *)(v7 + 132) = v9;
      BrbpCallDriverAsync(
        v4,
        (_DWORD *)v7,
        (void (__fastcall *)(__int64, _DWORD *, __int64))BrbUpdateCompletion,
        a1,
        a1 + 240);
    }
    else
    {
      v3 = -1073741670;
    }
  }
  else
  {
    v3 = -1073741816;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    DeviceExtension = WPP_GLOBAL_Control->DeviceExtension;
    v11 = NtStatusTxt(v3);
    WPP_RECORDER_SF_s(
      (_DWORD)DeviceExtension,
      v12,
      3,
      45,
      (__int64)WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids,
      (__int64)v11);
  }
  return v3;
}

```

## disassembly

```asm
0x14000dd28  push    rbx
0x14000dd2a  push    rbp
0x14000dd2b  push    rsi
0x14000dd2c  push    rdi
0x14000dd2d  push    r12
0x14000dd2f  push    r13
0x14000dd31  push    r14
0x14000dd33  push    r15
0x14000dd35  sub     rsp, 48h
0x14000dd39  mov     r14, [rcx+118h]
0x14000dd40  lea     r13, WPP_RECORDER_INITIALIZED
0x14000dd47  lea     rsi, WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids
0x14000dd4e  mov     rbx, rcx
0x14000dd51  test    r14, r14
0x14000dd54  jnz     short loc_14000DD60
0x14000dd56  mov     edi, 0C0000008h
0x14000dd5b  jmp     loc_14000DE3E
0x14000dd60  mov     r15, [rcx+48h]
0x14000dd64  mov     edx, 42426652h
0x14000dd69  mov     r12, [rcx+108h]
0x14000dd70  mov     ecx, 106h
0x14000dd75  mov     rax, [r15+138h]
0x14000dd7c  call    _guard_dispatch_icall
0x14000dd81  mov     rbp, rax
0x14000dd84  test    rax, rax
0x14000dd87  jnz     short loc_14000DD93
0x14000dd89  mov     edi, 0C000009Ah
0x14000dd8e  jmp     loc_14000DE3E
0x14000dd93  mov     ecx, [rbx+1D8h]
0x14000dd99  xor     esi, esi
0x14000dd9b  bt      ecx, 11h
0x14000dd9f  mov     edi, 103h
0x14000dda4  mov     r8d, 60000h
0x14000ddaa  jnb     short loc_14000DDB8
0x14000ddac  bt      dword ptr [rbx+1DCh], 11h
0x14000ddb4  cmovnb  esi, r8d
0x14000ddb8  bt      ecx, 12h
0x14000ddbc  jnb     short loc_14000DDCA
0x14000ddbe  bt      dword ptr [rbx+1DCh], 12h
0x14000ddc6  cmovnb  esi, r8d
0x14000ddca  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14000ddd1  jz      short loc_14000DE02
0x14000ddd3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ddda  lea     rax, WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids
0x14000dde1  mov     r9d, 2Ch ; ','
0x14000dde7  mov     [rsp+88h+var_58], esi
0x14000ddeb  mov     [rsp+88h+var_60], r14
0x14000ddf0  mov     [rsp+88h+var_68], rax
0x14000ddf5  mov     rcx, [rcx+40h]
0x14000ddf9  lea     r8d, [r9-29h]
0x14000ddfd  call    WPP_RECORDER_SF_qD
0x14000de02  lea     rax, [rbx+0F0h]
0x14000de09  mov     [rbp+70h], r12
0x14000de0d  mov     r9, rbx
0x14000de10  mov     [rsp+88h+var_68], rax
0x14000de15  lea     r8, BrbUpdateCompletion
0x14000de1c  mov     [rbp+78h], r14
0x14000de20  mov     rdx, rbp
0x14000de23  mov     [rbp+80h], esi
0x14000de29  mov     rcx, r15
0x14000de2c  mov     [rbp+84h], esi
0x14000de32  call    BrbpCallDriverAsync
0x14000de37  lea     rsi, WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids
0x14000de3e  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14000de45  jz      short loc_14000DE75
0x14000de47  mov     rcx, cs:WPP_GLOBAL_Control
0x14000de4e  mov     rbx, [rcx+40h]
0x14000de52  mov     ecx, edi
0x14000de54  call    NtStatusTxt
0x14000de59  mov     r9d, 2Dh ; '-'
0x14000de5f  mov     [rsp+88h+var_60], rax
0x14000de64  mov     rcx, rbx
0x14000de67  mov     [rsp+88h+var_68], rsi
0x14000de6c  lea     r8d, [r9-2Ah]
0x14000de70  call    WPP_RECORDER_SF_s
0x14000de75  mov     eax, edi
0x14000de77  add     rsp, 48h
0x14000de7b  pop     r15
0x14000de7d  pop     r14
0x14000de7f  pop     r13
0x14000de81  pop     r12
0x14000de83  pop     rdi
0x14000de84  pop     rsi
0x14000de85  pop     rbp
0x14000de86  pop     rbx
0x14000de87  retn
```
