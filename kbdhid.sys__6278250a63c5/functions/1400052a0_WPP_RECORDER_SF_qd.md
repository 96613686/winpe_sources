# WPP_RECORDER_SF_qd

- ea: `0x1400052a0`
- end: `0x1400053b3`
- name: `WPP_RECORDER_SF_qd`
- size: `275`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x140001ed0`
- `0x1400026a0`
- `0x1400042d0`
- `0x14000fd50`
- `0x14000ff70`
- `0x140010690`

## callees

- `0x1400052a0`
- `0x140007170`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000539b`
- `WppRecorder!WppAutoLogTrace` at `0x14000539b`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qd(__int64 a1, unsigned __int8 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
{
  unsigned __int64 v7; // rdi
  unsigned int v9; // esi
  int v10; // eax
  char *v11; // rcx
  int v13; // [rsp+20h] [rbp-58h]
  __int64 v14; // [rsp+A8h] [rbp+30h] BYREF
  va_list va; // [rsp+A8h] [rbp+30h]
  va_list va1; // [rsp+B0h] [rbp+38h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v14 = va_arg(va1, _QWORD);
  v7 = (unsigned __int64)a3 >> 16;
  v9 = a2;
  v10 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v7 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v10, a3 - 1) )
  {
    v11 = (char *)WPP_GLOBAL_Control + 80 * v7;
    if ( (unsigned __int8)v11[41] >= a2 )
      ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
        *((_QWORD *)v11 + 3),
        43,
        a5,
        a4,
        (__int64 *)va,
        8,
        va1,
        4,
        0);
  }
  LOWORD(v13) = a4;
  return WppAutoLogTrace(a1, v9, a3, a5, v13, (__int64 *)va);
}

```

## disassembly

```asm
0x1400052a0  push    rbx
0x1400052a2  push    rbp
0x1400052a3  push    rsi
0x1400052a4  push    rdi
0x1400052a5  push    r15
0x1400052a7  sub     rsp, 50h
0x1400052ab  mov     ebx, r8d
0x1400052ae  mov     r15, rcx
0x1400052b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400052b8  mov     edi, r8d
0x1400052bb  shr     rdi, 10h
0x1400052bf  lea     r11d, [rbx-1]
0x1400052c3  movzx   ebp, r9w
0x1400052c7  mov     r8d, r11d
0x1400052ca  movzx   esi, dl
0x1400052cd  shr     r8, 5
0x1400052d1  and     r8d, 7FFh
0x1400052d8  lea     rax, [rdi+rdi*4]
0x1400052dc  lea     r10, [r8+rax*4]
0x1400052e0  mov     eax, [rcx+r10*4+2Ch]
0x1400052e5  bt      eax, r11d
0x1400052e9  jnb     short loc_140005351
0x1400052eb  lea     rax, [rdi+rdi*4]
0x1400052ef  shl     rax, 4
0x1400052f3  add     rcx, rax
0x1400052f6  cmp     [rcx+29h], sil
0x1400052fa  jb      short loc_140005351
0x1400052fc  mov     rax, cs:pfnWppTraceMessage
0x140005303  lea     rdx, [rsp+78h+arg_30]
0x14000530b  mov     r8, [rsp+78h+arg_20]
0x140005313  mov     r9d, ebp
0x140005316  mov     rcx, [rcx+18h]
0x14000531a  mov     [rsp+78h+var_38], 0
0x140005323  mov     [rsp+78h+var_40], 4
0x14000532c  mov     [rsp+78h+var_48], rdx
0x140005331  lea     rdx, [rsp+78h+arg_28]
0x140005339  mov     [rsp+78h+var_50], 8
0x140005342  mov     [rsp+78h+var_58], rdx
0x140005347  mov     edx, 2Bh ; '+'
0x14000534c  call    _guard_dispatch_icall
0x140005351  mov     r9, [rsp+78h+arg_20]
0x140005359  lea     rax, [rsp+78h+arg_30]
0x140005361  mov     [rsp+78h+var_30], 0
0x14000536a  mov     r8d, ebx
0x14000536d  mov     [rsp+78h+var_38], 4
0x140005376  mov     edx, esi
0x140005378  mov     [rsp+78h+var_40], rax
0x14000537d  mov     rcx, r15
0x140005380  lea     rax, [rsp+78h+arg_28]
0x140005388  mov     [rsp+78h+var_48], 8
0x140005391  mov     [rsp+78h+var_50], rax
0x140005396  mov     word ptr [rsp+78h+var_58], bp
0x14000539b  call    cs:__imp_WppAutoLogTrace
0x1400053a2  nop     dword ptr [rax+rax+00h]
0x1400053a7  add     rsp, 50h
0x1400053ab  pop     r15
0x1400053ad  pop     rdi
0x1400053ae  pop     rsi
0x1400053af  pop     rbp
0x1400053b0  pop     rbx
0x1400053b1  retn
```
