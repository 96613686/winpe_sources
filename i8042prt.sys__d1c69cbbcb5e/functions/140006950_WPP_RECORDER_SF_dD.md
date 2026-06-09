# WPP_RECORDER_SF_dD

- ea: `0x140006950`
- end: `0x140006a50`
- name: `WPP_RECORDER_SF_dD`
- size: `256`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x140001360`
- `0x140002610`
- `0x140005560`
- `0x1400063a0`
- `0x1400098f0`
- `0x140018bf0`
- `0x14001908c`
- `0x140019cfc`
- `0x14001a19c`
- `0x14001b750`
- `0x14001c808`
- `0x14001d8b0`
- `0x14001eea0`

## callees

- `0x140006950`
- `0x14000daa0`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140006a38`
- `WppRecorder!WppAutoLogTrace` at `0x140006a38`

## pseudocode

```c
__int64 WPP_RECORDER_SF_dD(__int64 a1, __int64 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
{
  unsigned __int64 v7; // rax
  int v9; // ecx
  int v11; // [rsp+20h] [rbp-58h]
  __int64 v12; // [rsp+A8h] [rbp+30h] BYREF
  va_list va; // [rsp+A8h] [rbp+30h]
  va_list va1; // [rsp+B0h] [rbp+38h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v12 = va_arg(va1, _QWORD);
  v7 = (unsigned __int64)a3 >> 16;
  v9 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v7 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v9, a3 - 1) )
    ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v7),
      43,
      a5,
      a4,
      (__int64 *)va,
      4,
      va1,
      4,
      0);
  LOWORD(v11) = a4;
  return WppAutoLogTrace(a1, 0, a3, a5, v11, (__int64 *)va);
}

```

## disassembly

```asm
0x140006950  push    rbx
0x140006952  push    rbp
0x140006953  push    rsi
0x140006954  push    rdi
0x140006955  push    r14
0x140006957  sub     rsp, 50h
0x14000695b  mov     rdi, [rsp+78h+arg_20]
0x140006963  mov     rbp, rcx
0x140006966  mov     esi, r8d
0x140006969  xor     r14d, r14d
0x14000696c  mov     eax, r8d
0x14000696f  shr     rax, 10h
0x140006973  movzx   ebx, r9w
0x140006977  lea     r11d, [rsi-1]
0x14000697b  mov     r10d, r11d
0x14000697e  shr     r10, 5
0x140006982  lea     rdx, [rax+rax*4]
0x140006986  and     r10d, 7FFh
0x14000698d  lea     rcx, [r10+rdx*4]
0x140006991  mov     r10, cs:WPP_GLOBAL_Control
0x140006998  mov     ecx, [r10+rcx*4+2Ch]
0x14000699d  bt      ecx, r11d
0x1400069a1  jnb     short loc_1400069F7
0x1400069a3  mov     [rsp+78h+var_38], r14
0x1400069a8  lea     rcx, [rax+rax*4]
0x1400069ac  mov     rax, cs:pfnWppTraceMessage
0x1400069b3  lea     rdx, [rsp+78h+arg_30]
0x1400069bb  mov     [rsp+78h+var_40], 4
0x1400069c4  add     rcx, rcx
0x1400069c7  mov     [rsp+78h+var_48], rdx
0x1400069cc  mov     r9d, ebx
0x1400069cf  lea     rdx, [rsp+78h+arg_28]
0x1400069d7  mov     [rsp+78h+var_50], 4
0x1400069e0  mov     [rsp+78h+var_58], rdx
0x1400069e5  mov     r8, rdi
0x1400069e8  mov     rcx, [r10+rcx*8+18h]
0x1400069ed  mov     edx, 2Bh ; '+'
0x1400069f2  call    _guard_dispatch_icall
0x1400069f7  mov     [rsp+78h+var_30], r14
0x1400069fc  lea     rax, [rsp+78h+arg_30]
0x140006a04  mov     [rsp+78h+var_38], 4
0x140006a0d  mov     r9, rdi
0x140006a10  mov     [rsp+78h+var_40], rax
0x140006a15  mov     r8d, esi
0x140006a18  lea     rax, [rsp+78h+arg_28]
0x140006a20  mov     [rsp+78h+var_48], 4
0x140006a29  mov     [rsp+78h+var_50], rax
0x140006a2e  xor     edx, edx
0x140006a30  mov     rcx, rbp
0x140006a33  mov     word ptr [rsp+78h+var_58], bx
0x140006a38  call    cs:__imp_WppAutoLogTrace
0x140006a3f  nop     dword ptr [rax+rax+00h]
0x140006a44  add     rsp, 50h
0x140006a48  pop     r14
0x140006a4a  pop     rdi
0x140006a4b  pop     rsi
0x140006a4c  pop     rbp
0x140006a4d  pop     rbx
0x140006a4e  retn
```
