# WPP_RECORDER_SF_

- ea: `0x140001464`
- end: `0x14000151d`
- name: `WPP_RECORDER_SF_`
- size: `185`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x140001100`
- `0x140001960`
- `0x140002050`
- `0x140002370`
- `0x140002ff0`
- `0x14000383c`
- `0x140003e00`
- `0x140003fd0`
- `0x14000b5a4`
- `0x14000b730`
- `0x14000baf0`

## callees

- `0x140001464`
- `0x140004e10`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140001505`
- `WppRecorder!WppAutoLogTrace` at `0x140001505`

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
0x140001464  push    rbx
0x140001466  push    rbp
0x140001467  push    rsi
0x140001468  push    rdi
0x140001469  push    r14
0x14000146b  sub     rsp, 30h
0x14000146f  mov     ebp, r8d
0x140001472  mov     r14, rcx
0x140001475  mov     ebx, r8d
0x140001478  shr     rbx, 10h
0x14000147c  movzx   esi, r9w
0x140001480  lea     r11d, [rbp-1]
0x140001484  movzx   edi, dl
0x140001487  mov     r10d, r11d
0x14000148a  shr     r10, 5
0x14000148e  lea     rax, [rbx+rbx*4]
0x140001492  and     r10d, 7FFh
0x140001499  lea     rax, [r10+rax*4]
0x14000149d  mov     r10, cs:WPP_GLOBAL_Control
0x1400014a4  mov     eax, [r10+rax*4+2Ch]
0x1400014a9  bt      eax, r11d
0x1400014ad  jnb     short loc_1400014E7
0x1400014af  lea     rcx, [rbx+rbx*4]
0x1400014b3  add     rcx, rcx
0x1400014b6  cmp     [r10+rcx*8+29h], dil
0x1400014bb  jb      short loc_1400014E7
0x1400014bd  mov     rax, cs:pfnWppTraceMessage
0x1400014c4  mov     r9d, esi
0x1400014c7  mov     r8, [rsp+58h+arg_20]
0x1400014cf  mov     edx, 2Bh ; '+'
0x1400014d4  mov     rcx, [r10+rcx*8+18h]
0x1400014d9  mov     [rsp+58h+var_38], 0
0x1400014e2  call    _guard_dispatch_icall
0x1400014e7  mov     r9, [rsp+58h+arg_20]
0x1400014ef  mov     r8d, ebp
0x1400014f2  mov     [rsp+58h+var_30], 0
0x1400014fb  mov     edx, edi
0x1400014fd  mov     rcx, r14
0x140001500  mov     word ptr [rsp+58h+var_38], si
0x140001505  call    cs:__imp_WppAutoLogTrace
0x14000150c  nop     dword ptr [rax+rax+00h]
0x140001511  add     rsp, 30h
0x140001515  pop     r14
0x140001517  pop     rdi
0x140001518  pop     rsi
0x140001519  pop     rbp
0x14000151a  pop     rbx
0x14000151b  retn
```
