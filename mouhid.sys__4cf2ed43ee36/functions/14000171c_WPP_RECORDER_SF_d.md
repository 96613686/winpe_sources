# WPP_RECORDER_SF_d

- ea: `0x14000171c`
- end: `0x140001801`
- name: `WPP_RECORDER_SF_d`
- size: `229`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140001100`
- `0x140001960`
- `0x140002370`
- `0x14000d228`

## callees

- `0x14000171c`
- `0x140004e10`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400017e9`
- `WppRecorder!WppAutoLogTrace` at `0x1400017e9`

## pseudocode

```c
__int64 WPP_RECORDER_SF_d(__int64 a1, unsigned __int8 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
{
  unsigned __int64 v7; // rbx
  unsigned int v9; // edi
  int v10; // eax
  int v12; // [rsp+20h] [rbp-48h]
  va_list va; // [rsp+98h] [rbp+30h] BYREF

  va_start(va, a5);
  v7 = (unsigned __int64)a3 >> 16;
  v9 = a2;
  v10 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v7 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v10, a3 - 1) && *((_BYTE *)&WPP_GLOBAL_Control->Timer + 80 * v7 + 1) >= a2 )
    ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, char *, __int64, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v7),
      43,
      a5,
      a4,
      va,
      4,
      0);
  LOWORD(v12) = a4;
  return WppAutoLogTrace(a1, v9, a3, a5, v12, va);
}

```

## disassembly

```asm
0x14000171c  push    rbx
0x14000171e  push    rbp
0x14000171f  push    rsi
0x140001720  push    rdi
0x140001721  push    r14
0x140001723  sub     rsp, 40h
0x140001727  mov     ebp, r8d
0x14000172a  mov     r14, rcx
0x14000172d  mov     ebx, r8d
0x140001730  shr     rbx, 10h
0x140001734  movzx   esi, r9w
0x140001738  lea     r11d, [rbp-1]
0x14000173c  movzx   edi, dl
0x14000173f  mov     r10d, r11d
0x140001742  shr     r10, 5
0x140001746  lea     rax, [rbx+rbx*4]
0x14000174a  and     r10d, 7FFh
0x140001751  lea     rax, [r10+rax*4]
0x140001755  mov     r10, cs:WPP_GLOBAL_Control
0x14000175c  mov     eax, [r10+rax*4+2Ch]
0x140001761  bt      eax, r11d
0x140001765  jnb     short loc_1400017B5
0x140001767  lea     rcx, [rbx+rbx*4]
0x14000176b  add     rcx, rcx
0x14000176e  cmp     [r10+rcx*8+29h], dil
0x140001773  jb      short loc_1400017B5
0x140001775  mov     rax, cs:pfnWppTraceMessage
0x14000177c  lea     rdx, [rsp+68h+arg_28]
0x140001784  mov     r8, [rsp+68h+arg_20]
0x14000178c  mov     r9d, esi
0x14000178f  mov     rcx, [r10+rcx*8+18h]
0x140001794  mov     [rsp+68h+var_38], 0
0x14000179d  mov     [rsp+68h+var_40], 4
0x1400017a6  mov     [rsp+68h+var_48], rdx
0x1400017ab  mov     edx, 2Bh ; '+'
0x1400017b0  call    _guard_dispatch_icall
0x1400017b5  mov     r9, [rsp+68h+arg_20]
0x1400017bd  lea     rax, [rsp+68h+arg_28]
0x1400017c5  mov     [rsp+68h+var_30], 0
0x1400017ce  mov     r8d, ebp
0x1400017d1  mov     [rsp+68h+var_38], 4
0x1400017da  mov     edx, edi
0x1400017dc  mov     [rsp+68h+var_40], rax
0x1400017e1  mov     rcx, r14
0x1400017e4  mov     word ptr [rsp+68h+var_48], si
0x1400017e9  call    cs:__imp_WppAutoLogTrace
0x1400017f0  nop     dword ptr [rax+rax+00h]
0x1400017f5  add     rsp, 40h
0x1400017f9  pop     r14
0x1400017fb  pop     rdi
0x1400017fc  pop     rsi
0x1400017fd  pop     rbp
0x1400017fe  pop     rbx
0x1400017ff  retn
```
