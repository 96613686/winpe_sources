# WPP_RECORDER_SF_

- ea: `0x140005a0c`
- end: `0x140005ac5`
- name: `WPP_RECORDER_SF_`
- size: `185`
- prototype: ``
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x1400010c0`
- `0x140001300`
- `0x140001a00`
- `0x140001db0`
- `0x140001ed0`
- `0x1400026a0`
- `0x140003470`
- `0x140003b20`
- `0x140004d30`
- `0x140006680`
- `0x14000f930`
- `0x14000fd50`
- `0x14000ff70`
- `0x140010510`
- `0x140010690`

## callees

- `0x140005a0c`
- `0x140007170`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140005aad`
- `WppRecorder!WppAutoLogTrace` at `0x140005aad`

## pseudocode

```c
__int64 __fastcall WPP_RECORDER_SF_(__int64 a1, unsigned __int8 a2, unsigned int a3, unsigned __int16 a4, __int64 a5)
{
  unsigned __int64 v7; // rbx
  unsigned int v9; // edi
  int v10; // eax
  int v12; // [rsp+20h] [rbp-38h]

  v7 = (unsigned __int64)a3 >> 16;
  v9 = a2;
  v10 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v7 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v10, a3 - 1) && *((_BYTE *)&WPP_GLOBAL_Control->Timer + 80 * v7 + 1) >= a2 )
    ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v7),
      43,
      a5,
      a4,
      0);
  LOWORD(v12) = a4;
  return WppAutoLogTrace(a1, v9, a3, a5, v12, 0);
}

```

## disassembly

```asm
0x140005a0c  push    rbx
0x140005a0e  push    rbp
0x140005a0f  push    rsi
0x140005a10  push    rdi
0x140005a11  push    r14
0x140005a13  sub     rsp, 30h
0x140005a17  mov     ebp, r8d
0x140005a1a  mov     r14, rcx
0x140005a1d  mov     ebx, r8d
0x140005a20  shr     rbx, 10h
0x140005a24  movzx   esi, r9w
0x140005a28  lea     r11d, [rbp-1]
0x140005a2c  movzx   edi, dl
0x140005a2f  mov     r10d, r11d
0x140005a32  shr     r10, 5
0x140005a36  lea     rax, [rbx+rbx*4]
0x140005a3a  and     r10d, 7FFh
0x140005a41  lea     rax, [r10+rax*4]
0x140005a45  mov     r10, cs:WPP_GLOBAL_Control
0x140005a4c  mov     eax, [r10+rax*4+2Ch]
0x140005a51  bt      eax, r11d
0x140005a55  jnb     short loc_140005A8F
0x140005a57  lea     rcx, [rbx+rbx*4]
0x140005a5b  add     rcx, rcx
0x140005a5e  cmp     [r10+rcx*8+29h], dil
0x140005a63  jb      short loc_140005A8F
0x140005a65  mov     rax, cs:pfnWppTraceMessage
0x140005a6c  mov     r9d, esi
0x140005a6f  mov     r8, [rsp+58h+arg_20]
0x140005a77  mov     edx, 2Bh ; '+'
0x140005a7c  mov     rcx, [r10+rcx*8+18h]
0x140005a81  mov     [rsp+58h+var_38], 0
0x140005a8a  call    _guard_dispatch_icall
0x140005a8f  mov     r9, [rsp+58h+arg_20]
0x140005a97  mov     r8d, ebp
0x140005a9a  mov     [rsp+58h+var_30], 0
0x140005aa3  mov     edx, edi
0x140005aa5  mov     rcx, r14
0x140005aa8  mov     word ptr [rsp+58h+var_38], si
0x140005aad  call    cs:__imp_WppAutoLogTrace
0x140005ab4  nop     dword ptr [rax+rax+00h]
0x140005ab9  add     rsp, 30h
0x140005abd  pop     r14
0x140005abf  pop     rdi
0x140005ac0  pop     rsi
0x140005ac1  pop     rbp
0x140005ac2  pop     rbx
0x140005ac3  retn
```
