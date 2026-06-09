# WPP_RECORDER_SF_d

- ea: `0x1400014e0`
- end: `0x1400015b4`
- name: `WPP_RECORDER_SF_d`
- size: `212`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x140001ac0`
- `0x140001d30`
- `0x140002610`
- `0x140005f60`
- `0x14000b8a8`
- `0x140017f98`
- `0x1400183a4`
- `0x14001a7ac`
- `0x14001aa98`
- `0x14001b924`
- `0x14001f4e0`
- `0x1400213ec`

## callees

- `0x1400014e0`
- `0x14000daa0`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000159c`
- `WppRecorder!WppAutoLogTrace` at `0x14000159c`

## pseudocode

```c
__int64 WPP_RECORDER_SF_d(__int64 a1, __int64 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
{
  unsigned __int64 v7; // rax
  int v9; // edx
  int v11; // [rsp+20h] [rbp-48h]
  va_list va; // [rsp+98h] [rbp+30h] BYREF

  va_start(va, a5);
  v7 = (unsigned __int64)a3 >> 16;
  v9 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v7 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v9, a3 - 1) )
    ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, char *, __int64, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v7),
      43,
      a5,
      a4,
      va,
      4,
      0);
  LOWORD(v11) = a4;
  return WppAutoLogTrace(a1, 0, a3, a5, v11, va);
}

```

## disassembly

```asm
0x1400014e0  push    rbx
0x1400014e2  push    rbp
0x1400014e3  push    rsi
0x1400014e4  push    rdi
0x1400014e5  push    r14
0x1400014e7  sub     rsp, 40h
0x1400014eb  mov     rdi, [rsp+68h+arg_20]
0x1400014f3  xor     r14d, r14d
0x1400014f6  mov     esi, r8d
0x1400014f9  mov     rbp, rcx
0x1400014fc  mov     eax, r8d
0x1400014ff  shr     rax, 10h
0x140001503  movzx   ebx, r9w
0x140001507  lea     r11d, [rsi-1]
0x14000150b  mov     r10d, r11d
0x14000150e  shr     r10, 5
0x140001512  lea     rdx, [rax+rax*4]
0x140001516  and     r10d, 7FFh
0x14000151d  lea     rdx, [r10+rdx*4]
0x140001521  mov     r10, cs:WPP_GLOBAL_Control
0x140001528  mov     edx, [r10+rdx*4+2Ch]
0x14000152d  bt      edx, r11d
0x140001531  jnb     short loc_140001571
0x140001533  lea     rcx, [rax+rax*4]
0x140001537  mov     [rsp+68h+var_38], r14
0x14000153c  mov     rax, cs:pfnWppTraceMessage
0x140001543  lea     rdx, [rsp+68h+arg_28]
0x14000154b  add     rcx, rcx
0x14000154e  mov     [rsp+68h+var_40], 4
0x140001557  mov     [rsp+68h+var_48], rdx
0x14000155c  mov     r9d, ebx
0x14000155f  mov     r8, rdi
0x140001562  mov     edx, 2Bh ; '+'
0x140001567  mov     rcx, [r10+rcx*8+18h]
0x14000156c  call    _guard_dispatch_icall
0x140001571  mov     [rsp+68h+var_30], r14
0x140001576  lea     rax, [rsp+68h+arg_28]
0x14000157e  mov     [rsp+68h+var_38], 4
0x140001587  mov     r9, rdi
0x14000158a  mov     [rsp+68h+var_40], rax
0x14000158f  mov     r8d, esi
0x140001592  xor     edx, edx
0x140001594  mov     word ptr [rsp+68h+var_48], bx
0x140001599  mov     rcx, rbp
0x14000159c  call    cs:__imp_WppAutoLogTrace
0x1400015a3  nop     dword ptr [rax+rax+00h]
0x1400015a8  add     rsp, 40h
0x1400015ac  pop     r14
0x1400015ae  pop     rdi
0x1400015af  pop     rsi
0x1400015b0  pop     rbp
0x1400015b1  pop     rbx
0x1400015b2  retn
```
