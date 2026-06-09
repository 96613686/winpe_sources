# WPP_RECORDER_SF_

- ea: `0x140004530`
- end: `0x1400045e3`
- name: `WPP_RECORDER_SF_`
- size: `179`
- prototype: ``
- caller_count: `76`
- callee_count: `2`
- tags: ``

## callers

- `0x140001130`
- `0x140001360`
- `0x1400019e0`
- `0x140001ac0`
- `0x140001d30`
- `0x140002610`
- `0x140004180`
- `0x1400045f0`
- `0x1400048f0`
- `0x140004f00`
- `0x140005260`
- `0x140005560`
- `0x140005830`
- `0x1400059c0`
- `0x140005de0`
- `0x140005e90`
- `0x140005f60`
- `0x140006170`
- `0x1400063a0`
- `0x1400066d0`
- `0x140006a60`
- `0x140007090`
- `0x140007c20`
- `0x140008000`
- `0x1400080e0`
- `0x140008b80`
- `0x140008f80`
- `0x1400090c0`
- `0x1400092d0`
- `0x1400096a0`
- `0x140009720`
- `0x14000b72c`
- `0x14000b8a8`
- `0x14000ba98`
- `0x14000c290`
- `0x14000c330`
- `0x14000c3e0`
- `0x14000c700`
- `0x14000cb40`
- `0x14000d1a8`
- `0x14000d460`
- `0x14000d610`
- `0x140017008`
- `0x140017410`
- `0x140017f98`
- `0x1400183a4`
- `0x140019490`
- `0x140019714`
- `0x1400197e8`
- `0x1400198e0`

## callees

- `0x140004530`
- `0x14000daa0`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140004596`
- `WppRecorder!WppAutoLogTrace` at `0x140004596`

## pseudocode

```c
__int64 __fastcall WPP_RECORDER_SF_(__int64 a1, __int64 a2, unsigned int a3, unsigned __int16 a4, __int64 a5)
{
  unsigned __int64 v8; // r10
  unsigned int v9; // r8d
  int v10; // eax
  int v12; // [rsp+20h] [rbp-18h]

  v8 = (unsigned __int64)a3 >> 16;
  v9 = a3 - 1;
  v10 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v8 + ((unsigned __int16)v9 >> 5) + 1);
  if ( _bittest(&v10, v9) )
    ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v8),
      43,
      a5,
      a4,
      0);
  LOWORD(v12) = a4;
  return WppAutoLogTrace(a1, 0, a3, a5, v12, 0);
}

```

## disassembly

```asm
0x140004530  mov     [rsp+arg_0], rbx
0x140004535  mov     [rsp+arg_8], rbp
0x14000453a  push    rdi
0x14000453b  sub     rsp, 30h
0x14000453f  mov     r11, cs:WPP_GLOBAL_Control
0x140004546  mov     rbp, rcx
0x140004549  mov     ebx, r8d
0x14000454c  mov     r10d, ebx
0x14000454f  movzx   edi, r9w
0x140004553  shr     r10, 10h
0x140004557  lea     r8d, [rbx-1]
0x14000455b  mov     edx, r8d
0x14000455e  shr     rdx, 5
0x140004562  lea     rax, [r10+r10*4]
0x140004566  and     edx, 7FFh
0x14000456c  lea     rax, [rdx+rax*4]
0x140004570  mov     eax, [r11+rax*4+2Ch]
0x140004575  bt      eax, r8d
0x140004579  jb      short loc_1400045B3
0x14000457b  mov     r9, [rsp+38h+arg_20]
0x140004580  mov     r8d, ebx
0x140004583  mov     [rsp+38h+var_10], 0
0x14000458c  xor     edx, edx
0x14000458e  mov     rcx, rbp
0x140004591  mov     word ptr [rsp+38h+var_18], di
0x140004596  call    cs:__imp_WppAutoLogTrace
0x14000459d  nop     dword ptr [rax+rax+00h]
0x1400045a2  mov     rbx, [rsp+38h+arg_0]
0x1400045a7  mov     rbp, [rsp+38h+arg_8]
0x1400045ac  add     rsp, 30h
0x1400045b0  pop     rdi
0x1400045b1  retn
0x1400045b3  mov     rax, cs:pfnWppTraceMessage
0x1400045ba  lea     rcx, [r10+r10*4]
0x1400045be  mov     r8, [rsp+38h+arg_20]
0x1400045c3  add     rcx, rcx
0x1400045c6  mov     r9d, edi
0x1400045c9  mov     [rsp+38h+var_18], 0
0x1400045d2  mov     edx, 2Bh ; '+'
0x1400045d7  mov     rcx, [r11+rcx*8+18h]
0x1400045dc  call    _guard_dispatch_icall
0x1400045e1  jmp     short loc_14000457B
```
