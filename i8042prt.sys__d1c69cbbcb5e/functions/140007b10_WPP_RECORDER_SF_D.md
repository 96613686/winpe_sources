# WPP_RECORDER_SF_D

- ea: `0x140007b10`
- end: `0x140007bec`
- name: `WPP_RECORDER_SF_D`
- size: `220`
- prototype: ``
- caller_count: `37`
- callee_count: `2`
- tags: ``

## callers

- `0x140001130`
- `0x140001d30`
- `0x140002610`
- `0x140004180`
- `0x1400045f0`
- `0x140005560`
- `0x1400059c0`
- `0x1400063a0`
- `0x1400066d0`
- `0x140007090`
- `0x1400080e0`
- `0x14000b72c`
- `0x14000d1a8`
- `0x14000d460`
- `0x140017f98`
- `0x1400183a4`
- `0x140018bf0`
- `0x14001908c`
- `0x1400198e0`
- `0x140019cfc`
- `0x14001a19c`
- `0x14001a7ac`
- `0x14001aa98`
- `0x14001b574`
- `0x14001b924`
- `0x14001be20`
- `0x14001c068`
- `0x14001c590`
- `0x14001cce0`
- `0x14001d300`
- `0x14001d8b0`
- `0x14001e700`
- `0x14001e950`
- `0x14001eea0`
- `0x14001fa30`
- `0x140021078`
- `0x1400213ec`

## callees

- `0x140007b10`
- `0x14000daa0`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140007b89`
- `WppRecorder!WppAutoLogTrace` at `0x140007b89`

## pseudocode

```c
__int64 WPP_RECORDER_SF_D(__int64 a1, _DWORD a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
{
  unsigned __int64 v8; // r10
  unsigned int v9; // r8d
  int v10; // eax
  int v12; // [rsp+20h] [rbp-28h]
  va_list va; // [rsp+78h] [rbp+30h] BYREF

  va_start(va, a5);
  v8 = (unsigned __int64)a3 >> 16;
  v9 = a3 - 1;
  v10 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v8 + ((unsigned __int16)v9 >> 5) + 1);
  if ( _bittest(&v10, v9) )
    ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, char *, __int64, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v8),
      43,
      a5,
      a4,
      va,
      4,
      0);
  LOWORD(v12) = a4;
  return WppAutoLogTrace(a1, 0, a3, a5, v12, va);
}

```

## disassembly

```asm
0x140007b10  mov     [rsp+arg_0], rbx
0x140007b15  mov     [rsp+arg_8], rbp
0x140007b1a  push    rdi
0x140007b1b  sub     rsp, 40h
0x140007b1f  mov     r11, cs:WPP_GLOBAL_Control
0x140007b26  mov     rbp, rcx
0x140007b29  mov     ebx, r8d
0x140007b2c  mov     r10d, ebx
0x140007b2f  movzx   edi, r9w
0x140007b33  shr     r10, 10h
0x140007b37  lea     r8d, [rbx-1]
0x140007b3b  mov     edx, r8d
0x140007b3e  shr     rdx, 5
0x140007b42  lea     rax, [r10+r10*4]
0x140007b46  and     edx, 7FFh
0x140007b4c  lea     rax, [rdx+rax*4]
0x140007b50  mov     eax, [r11+rax*4+2Ch]
0x140007b55  bt      eax, r8d
0x140007b59  jb      short loc_140007BA6
0x140007b5b  mov     r9, [rsp+48h+arg_20]
0x140007b60  lea     rax, [rsp+48h+arg_28]
0x140007b65  mov     [rsp+48h+var_10], 0
0x140007b6e  mov     r8d, ebx
0x140007b71  mov     [rsp+48h+var_18], 4
0x140007b7a  xor     edx, edx
0x140007b7c  mov     [rsp+48h+var_20], rax
0x140007b81  mov     rcx, rbp
0x140007b84  mov     word ptr [rsp+48h+var_28], di
0x140007b89  call    cs:__imp_WppAutoLogTrace
0x140007b90  nop     dword ptr [rax+rax+00h]
0x140007b95  mov     rbx, [rsp+48h+arg_0]
0x140007b9a  mov     rbp, [rsp+48h+arg_8]
0x140007b9f  add     rsp, 40h
0x140007ba3  pop     rdi
0x140007ba4  retn
0x140007ba6  mov     rax, cs:pfnWppTraceMessage
0x140007bad  lea     rdx, [rsp+48h+arg_28]
0x140007bb2  mov     r8, [rsp+48h+arg_20]
0x140007bb7  lea     rcx, [r10+r10*4]
0x140007bbb  add     rcx, rcx
0x140007bbe  mov     [rsp+48h+var_18], 0
0x140007bc7  mov     [rsp+48h+var_20], 4
0x140007bd0  mov     r9d, edi
0x140007bd3  mov     [rsp+48h+var_28], rdx
0x140007bd8  mov     edx, 2Bh ; '+'
0x140007bdd  mov     rcx, [r11+rcx*8+18h]
0x140007be2  call    _guard_dispatch_icall
0x140007be7  jmp     loc_140007B5B
```
