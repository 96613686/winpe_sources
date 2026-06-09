# I8xInitializeDataQueue

- ea: `0x140009720`
- end: `0x140009837`
- name: `I8xInitializeDataQueue`
- size: `279`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400198e0`
- `0x14001c068`

## callees

- `0x140004530`
- `0x140009720`

## pseudocode

```c
char __fastcall I8xInitializeDataQueue(_BYTE *a1, __int64 a2)
{
  __int64 v3; // rax
  __int64 v4; // rcx
  unsigned __int16 v5; // r9
  __int64 v6; // rcx

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      (__int64)WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3u,
      0x55u,
      (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
  LOBYTE(v3) = a1[8];
  if ( (_BYTE)v3 == 1 )
  {
    v4 = *(_QWORD *)a1;
    v3 = *(_QWORD *)(*(_QWORD *)a1 + 872LL);
    *(_QWORD *)(v4 + 880) = v3;
    *(_QWORD *)(v4 + 888) = v3;
    *(_DWORD *)(v4 + 92) = 0;
    *(_BYTE *)(v4 + 562) = 1;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v3;
    v5 = 86;
  }
  else
  {
    if ( (_BYTE)v3 != 2 )
      goto LABEL_10;
    v6 = *(_QWORD *)a1;
    v3 = *(_QWORD *)(*(_QWORD *)a1 + 944LL);
    *(_QWORD *)(v6 + 952) = v3;
    *(_QWORD *)(v6 + 960) = v3;
    *(_DWORD *)(v6 + 92) = 0;
    *(_BYTE *)(v6 + 562) = 1;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v3;
    v5 = 87;
  }
  LOBYTE(v3) = WPP_RECORDER_SF_(
                 (__int64)WPP_GLOBAL_Control->DeviceExtension,
                 a2,
                 4u,
                 v5,
                 (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
LABEL_10:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    LOBYTE(v3) = WPP_RECORDER_SF_(
                   (__int64)WPP_GLOBAL_Control->DeviceExtension,
                   a2,
                   3u,
                   0x58u,
                   (__int64)WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids);
  return v3;
}

```

## disassembly

```asm
0x140009720  mov     [rsp+arg_0], rbx
0x140009725  mov     [rsp+arg_8], rsi
0x14000972a  push    rdi
0x14000972b  sub     rsp, 30h
0x14000972f  mov     rbx, rcx
0x140009732  lea     rdi, WPP_RECORDER_INITIALIZED
0x140009739  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140009740  lea     rsi, WPP_69ad5fa20b14395ecb5f7e203cce2975_Traceguids
0x140009747  jz      short loc_140009768
0x140009749  mov     rcx, cs:WPP_GLOBAL_Control
0x140009750  mov     r9d, 55h ; 'U'
0x140009756  mov     [rsp+38h+var_18], rsi
0x14000975b  mov     rcx, [rcx+40h]
0x14000975f  lea     r8d, [r9-52h]
0x140009763  call    WPP_RECORDER_SF_
0x140009768  mov     al, [rbx+8]
0x14000976b  cmp     al, 1
0x14000976d  jnz     short loc_1400097AA
0x14000976f  mov     rcx, [rbx]
0x140009772  mov     rax, [rcx+368h]
0x140009779  mov     [rcx+370h], rax
0x140009780  mov     [rcx+378h], rax
0x140009787  mov     dword ptr [rcx+5Ch], 0
0x14000978e  mov     byte ptr [rcx+232h], 1
0x140009795  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14000979c  jz      loc_140009826
0x1400097a2  mov     r9d, 56h ; 'V'
0x1400097a8  jmp     short loc_1400097E3
0x1400097aa  cmp     al, 2
0x1400097ac  jnz     short loc_1400097FE
0x1400097ae  mov     rcx, [rbx]
0x1400097b1  mov     rax, [rcx+3B0h]
0x1400097b8  mov     [rcx+3B8h], rax
0x1400097bf  mov     [rcx+3C0h], rax
0x1400097c6  mov     dword ptr [rcx+5Ch], 0
0x1400097cd  mov     byte ptr [rcx+232h], 1
0x1400097d4  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400097db  jz      short loc_140009826
0x1400097dd  mov     r9d, 57h ; 'W'
0x1400097e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400097ea  mov     r8d, 4
0x1400097f0  mov     [rsp+38h+var_18], rsi
0x1400097f5  mov     rcx, [rcx+40h]
0x1400097f9  call    WPP_RECORDER_SF_
0x1400097fe  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140009805  jz      short loc_140009826
0x140009807  mov     rcx, cs:WPP_GLOBAL_Control
0x14000980e  mov     r9d, 58h ; 'X'
0x140009814  mov     [rsp+38h+var_18], rsi
0x140009819  mov     rcx, [rcx+40h]
0x14000981d  lea     r8d, [r9-55h]
0x140009821  call    WPP_RECORDER_SF_
0x140009826  mov     rbx, [rsp+38h+arg_0]
0x14000982b  mov     rsi, [rsp+38h+arg_8]
0x140009830  add     rsp, 30h
0x140009834  pop     rdi
0x140009835  retn
```
