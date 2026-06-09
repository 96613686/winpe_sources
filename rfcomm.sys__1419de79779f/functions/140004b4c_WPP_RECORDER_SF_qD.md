# WPP_RECORDER_SF_qD

- ea: `0x140004b4c`
- end: `0x140004c54`
- name: `WPP_RECORDER_SF_qD`
- size: `264`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x140001958`
- `0x14000256c`
- `0x14000280c`
- `0x140002ac8`
- `0x140003074`
- `0x14000dd28`
- `0x140014b10`
- `0x1400178b8`
- `0x14003365c`

## callees

- `0x140004b4c`
- `0x14001fc70`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140004c3e`
- `WppRecorder!WppAutoLogTrace` at `0x140004c3e`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qD(__int64 a1, __int64 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
{
  unsigned __int64 v7; // rbx
  int v9; // eax
  int v11; // [rsp+20h] [rbp-58h]
  __int64 v12; // [rsp+A8h] [rbp+30h] BYREF
  va_list va; // [rsp+A8h] [rbp+30h]
  va_list va1; // [rsp+B0h] [rbp+38h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v12 = va_arg(va1, _QWORD);
  v7 = (unsigned __int64)a3 >> 16;
  v9 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v7 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v9, (a3 - 1) & 0x1F) )
    ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v7),
      43,
      a5,
      a4,
      (__int64 *)va,
      8,
      va1,
      4,
      0);
  LOWORD(v11) = a4;
  return WppAutoLogTrace(a1, 0, a3, a5, v11, (__int64 *)va);
}

```

## disassembly

```asm
0x140004b4c  push    rbx
0x140004b4e  push    rbp
0x140004b4f  push    rsi
0x140004b50  push    rdi
0x140004b51  sub     rsp, 58h
0x140004b55  mov     esi, r8d
0x140004b58  mov     rbp, rcx
0x140004b5b  mov     ebx, r8d
0x140004b5e  shr     rbx, 10h
0x140004b62  movzx   edi, r9w
0x140004b66  lea     r11d, [rsi-1]
0x140004b6a  mov     edx, r11d
0x140004b6d  and     r11d, 1Fh
0x140004b71  shr     rdx, 5
0x140004b75  lea     rax, [rbx+rbx*4]
0x140004b79  and     edx, 7FFh
0x140004b7f  lea     r10, [rdx+rax*4]
0x140004b83  mov     edx, r11d
0x140004b86  mov     r11, cs:WPP_GLOBAL_Control
0x140004b8d  mov     eax, [r11+r10*4+2Ch]
0x140004b92  bt      eax, edx
0x140004b95  jnb     short loc_140004BF4
0x140004b97  mov     rax, cs:pfnWppTraceMessage
0x140004b9e  lea     rdx, [rsp+78h+arg_30]
0x140004ba6  mov     r8, [rsp+78h+arg_20]
0x140004bae  lea     rcx, [rbx+rbx*4]
0x140004bb2  mov     [rsp+78h+var_38], 0
0x140004bbb  add     rcx, rcx
0x140004bbe  mov     [rsp+78h+var_40], 4
0x140004bc7  mov     r9d, edi
0x140004bca  mov     [rsp+78h+var_48], rdx
0x140004bcf  lea     rdx, [rsp+78h+arg_28]
0x140004bd7  mov     [rsp+78h+var_50], 8
0x140004be0  mov     rcx, [r11+rcx*8+18h]
0x140004be5  mov     [rsp+78h+var_58], rdx
0x140004bea  mov     edx, 2Bh ; '+'
0x140004bef  call    _guard_dispatch_icall
0x140004bf4  mov     r9, [rsp+78h+arg_20]
0x140004bfc  lea     rax, [rsp+78h+arg_30]
0x140004c04  mov     [rsp+78h+var_30], 0
0x140004c0d  mov     r8d, esi
0x140004c10  mov     [rsp+78h+var_38], 4
0x140004c19  xor     edx, edx
0x140004c1b  mov     [rsp+78h+var_40], rax
0x140004c20  mov     rcx, rbp
0x140004c23  lea     rax, [rsp+78h+arg_28]
0x140004c2b  mov     [rsp+78h+var_48], 8
0x140004c34  mov     [rsp+78h+var_50], rax
0x140004c39  mov     word ptr [rsp+78h+var_58], di
0x140004c3e  call    cs:__imp_WppAutoLogTrace
0x140004c45  nop     dword ptr [rax+rax+00h]
0x140004c4a  add     rsp, 58h
0x140004c4e  pop     rdi
0x140004c4f  pop     rsi
0x140004c50  pop     rbp
0x140004c51  pop     rbx
0x140004c52  retn
```
