# WPP_RECORDER_SF_Dd

- ea: `0x140001524`
- end: `0x140001635`
- name: `WPP_RECORDER_SF_Dd`
- size: `273`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140001100`
- `0x140001960`

## callees

- `0x140001524`
- `0x140004e10`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000161b`
- `WppRecorder!WppAutoLogTrace` at `0x14000161b`

## pseudocode

```c
__int64 WPP_RECORDER_SF_Dd(__int64 a1, unsigned __int8 a2, unsigned int a3, __int64 a4, __int64 a5, ...)
{
  unsigned __int64 v7; // rbx
  unsigned int v8; // edi
  int v9; // eax
  int v11; // [rsp+20h] [rbp-68h]
  __int64 v12; // [rsp+B8h] [rbp+30h] BYREF
  va_list va; // [rsp+B8h] [rbp+30h]
  va_list va1; // [rsp+C0h] [rbp+38h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v12 = va_arg(va1, _QWORD);
  v7 = (unsigned __int64)a3 >> 16;
  v8 = a2;
  v9 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v7 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v9, (a3 - 1) & 0x1F) && *((_BYTE *)&WPP_GLOBAL_Control->Timer + 80 * v7 + 1) >= a2 )
    ((void (__fastcall *)(_QWORD, __int64, __int64, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v7),
      43,
      a5,
      14,
      (__int64 *)va,
      4,
      va1,
      4,
      0);
  LOWORD(v11) = 14;
  return WppAutoLogTrace(a1, v8, a3, a5, v11, (__int64 *)va);
}

```

## disassembly

```asm
0x140001524  push    rbx
0x140001526  push    rbp
0x140001527  push    rsi
0x140001528  push    rdi
0x140001529  push    r14
0x14000152b  push    r15
0x14000152d  sub     rsp, 58h
0x140001531  mov     esi, r8d
0x140001534  mov     r15d, 0Eh
0x14000153a  mov     ebx, r8d
0x14000153d  mov     rbp, rcx
0x140001540  shr     rbx, 10h
0x140001544  movzx   edi, dl
0x140001547  lea     r11d, [rsi-1]
0x14000154b  mov     r9d, r11d
0x14000154e  lea     r14d, [r15-0Ah]
0x140001552  shr     r9, 5
0x140001556  lea     rax, [rbx+rbx*4]
0x14000155a  and     r11d, 1Fh
0x14000155e  and     r9d, 7FFh
0x140001565  mov     edx, r11d
0x140001568  mov     r11, cs:WPP_GLOBAL_Control
0x14000156f  lea     r10, [r9+rax*4]
0x140001573  mov     eax, [r11+r10*4+2Ch]
0x140001578  bt      eax, edx
0x14000157b  jnb     short loc_1400015D8
0x14000157d  lea     rcx, [rbx+rbx*4]
0x140001581  add     rcx, rcx
0x140001584  cmp     [r11+rcx*8+29h], dil
0x140001589  jb      short loc_1400015D8
0x14000158b  mov     rax, cs:pfnWppTraceMessage
0x140001592  lea     rdx, [rsp+88h+arg_30]
0x14000159a  mov     r8, [rsp+88h+arg_20]
0x1400015a2  mov     r9d, r15d
0x1400015a5  mov     rcx, [r11+rcx*8+18h]
0x1400015aa  mov     [rsp+88h+var_48], 0
0x1400015b3  mov     [rsp+88h+var_50], r14
0x1400015b8  mov     [rsp+88h+var_58], rdx
0x1400015bd  lea     rdx, [rsp+88h+arg_28]
0x1400015c5  mov     [rsp+88h+var_60], r14
0x1400015ca  mov     [rsp+88h+var_68], rdx
0x1400015cf  lea     edx, [r15+1Dh]
0x1400015d3  call    _guard_dispatch_icall
0x1400015d8  mov     r9, [rsp+88h+arg_20]
0x1400015e0  lea     rax, [rsp+88h+arg_30]
0x1400015e8  mov     [rsp+88h+var_40], 0
0x1400015f1  mov     r8d, esi
0x1400015f4  mov     [rsp+88h+var_48], r14
0x1400015f9  mov     edx, edi
0x1400015fb  mov     [rsp+88h+var_50], rax
0x140001600  mov     rcx, rbp
0x140001603  lea     rax, [rsp+88h+arg_28]
0x14000160b  mov     [rsp+88h+var_58], r14
0x140001610  mov     [rsp+88h+var_60], rax
0x140001615  mov     word ptr [rsp+88h+var_68], r15w
0x14000161b  call    cs:__imp_WppAutoLogTrace
0x140001622  nop     dword ptr [rax+rax+00h]
0x140001627  add     rsp, 58h
0x14000162b  pop     r15
0x14000162d  pop     r14
0x14000162f  pop     rdi
0x140001630  pop     rsi
0x140001631  pop     rbp
0x140001632  pop     rbx
0x140001633  retn
```
