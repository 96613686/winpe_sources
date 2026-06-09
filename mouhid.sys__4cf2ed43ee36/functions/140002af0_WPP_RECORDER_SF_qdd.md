# WPP_RECORDER_SF_qdd

- ea: `0x140002af0`
- end: `0x140002c25`
- name: `WPP_RECORDER_SF_qdd`
- size: `309`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140002050`
- `0x1400047a0`

## callees

- `0x140002af0`
- `0x140004e10`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140002c0d`
- `WppRecorder!WppAutoLogTrace` at `0x140002c0d`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qdd(__int64 a1, __int64 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
{
  unsigned __int64 v7; // rbx
  int v9; // eax
  int v11; // [rsp+20h] [rbp-68h]
  __int64 v12; // [rsp+B8h] [rbp+30h] BYREF
  va_list va; // [rsp+B8h] [rbp+30h]
  __int64 v14; // [rsp+C0h] [rbp+38h] BYREF
  va_list va1; // [rsp+C0h] [rbp+38h]
  va_list va2; // [rsp+C8h] [rbp+40h] BYREF

  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v12 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v14 = va_arg(va2, _QWORD);
  v7 = (unsigned __int64)a3 >> 16;
  v9 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v7 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v9, (a3 - 1) & 0x1F) && *((_BYTE *)&WPP_GLOBAL_Control->Timer + 80 * v7 + 1) >= 4u )
    ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v7),
      43,
      a5,
      a4,
      (__int64 *)va,
      8,
      (__int64 *)va1,
      4,
      va2,
      4,
      0);
  LOWORD(v11) = a4;
  return WppAutoLogTrace(a1, 4, a3, a5, v11, (__int64 *)va);
}

```

## disassembly

```asm
0x140002af0  push    rbx
0x140002af2  push    rbp
0x140002af3  push    rsi
0x140002af4  push    rdi
0x140002af5  push    r14
0x140002af7  sub     rsp, 60h
0x140002afb  mov     esi, r8d
0x140002afe  mov     rbp, rcx
0x140002b01  mov     ebx, r8d
0x140002b04  mov     r14d, 4
0x140002b0a  shr     rbx, 10h
0x140002b0e  movzx   edi, r9w
0x140002b12  lea     r11d, [rsi-1]
0x140002b16  mov     edx, r11d
0x140002b19  and     r11d, 1Fh
0x140002b1d  shr     rdx, 5
0x140002b21  lea     rax, [rbx+rbx*4]
0x140002b25  and     edx, 7FFh
0x140002b2b  lea     r10, [rdx+rax*4]
0x140002b2f  mov     edx, r11d
0x140002b32  mov     r11, cs:WPP_GLOBAL_Control
0x140002b39  mov     eax, [r11+r10*4+2Ch]
0x140002b3e  bt      eax, edx
0x140002b41  jnb     short loc_140002BB4
0x140002b43  lea     rcx, [rbx+rbx*4]
0x140002b47  add     rcx, rcx
0x140002b4a  cmp     [r11+rcx*8+29h], r14b
0x140002b4f  jb      short loc_140002BB4
0x140002b51  mov     rax, cs:pfnWppTraceMessage
0x140002b58  lea     rdx, [rsp+88h+arg_38]
0x140002b60  mov     r8, [rsp+88h+arg_20]
0x140002b68  mov     r9d, edi
0x140002b6b  mov     rcx, [r11+rcx*8+18h]
0x140002b70  mov     [rsp+88h+var_38], 0
0x140002b79  mov     [rsp+88h+var_40], r14
0x140002b7e  mov     [rsp+88h+var_48], rdx
0x140002b83  lea     rdx, [rsp+88h+arg_30]
0x140002b8b  mov     [rsp+88h+var_50], r14
0x140002b90  mov     [rsp+88h+var_58], rdx
0x140002b95  lea     rdx, [rsp+88h+arg_28]
0x140002b9d  mov     [rsp+88h+var_60], 8
0x140002ba6  mov     [rsp+88h+var_68], rdx
0x140002bab  lea     edx, [r14+27h]
0x140002baf  call    _guard_dispatch_icall
0x140002bb4  mov     r9, [rsp+88h+arg_20]
0x140002bbc  lea     rax, [rsp+88h+arg_38]
0x140002bc4  mov     [rsp+88h+var_30], 0
0x140002bcd  mov     r8d, esi
0x140002bd0  mov     [rsp+88h+var_38], r14
0x140002bd5  mov     edx, r14d
0x140002bd8  mov     [rsp+88h+var_40], rax
0x140002bdd  mov     rcx, rbp
0x140002be0  mov     [rsp+88h+var_48], r14
0x140002be5  lea     rax, [rsp+88h+arg_30]
0x140002bed  mov     [rsp+88h+var_50], rax
0x140002bf2  lea     rax, [rsp+88h+arg_28]
0x140002bfa  mov     [rsp+88h+var_58], 8
0x140002c03  mov     [rsp+88h+var_60], rax
0x140002c08  mov     word ptr [rsp+88h+var_68], di
0x140002c0d  call    cs:__imp_WppAutoLogTrace
0x140002c14  nop     dword ptr [rax+rax+00h]
0x140002c19  add     rsp, 60h
0x140002c1d  pop     r14
0x140002c1f  pop     rdi
0x140002c20  pop     rsi
0x140002c21  pop     rbp
0x140002c22  pop     rbx
0x140002c23  retn
```
