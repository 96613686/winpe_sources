# WPP_RECORDER_SF_s

- ea: `0x1400043e0`
- end: `0x140004520`
- name: `WPP_RECORDER_SF_s`
- size: `320`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x140004180`
- `0x1400066d0`
- `0x1400080e0`
- `0x1400172a0`
- `0x140017f98`
- `0x1400198e0`
- `0x14001c068`
- `0x14001c808`
- `0x14001eda0`
- `0x14001f4e0`
- `0x1400213ec`

## callees

- `0x1400043e0`
- `0x14000daa0`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140004488`
- `WppRecorder!WppAutoLogTrace` at `0x140004488`

## pseudocode

```c
__int64 __fastcall WPP_RECORDER_SF_s(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned __int16 a4,
        __int64 a5,
        const char *a6)
{
  const char *v6; // rdi
  __int64 v9; // rbx
  unsigned __int64 v10; // r14
  int v12; // ecx
  bool v13; // zf
  __int64 v15; // rax
  __int64 v16; // rcx
  const char *v17; // rdx
  int v18; // [rsp+20h] [rbp-58h]

  v6 = a6;
  v9 = -1;
  v10 = (unsigned __int64)a3 >> 16;
  v12 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v10 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v12, a3 - 1) )
  {
    if ( a6 )
    {
      v15 = -1;
      do
        v13 = a6[++v15] == 0;
      while ( !v13 );
      v16 = v15 + 1;
    }
    else
    {
      v16 = 5;
    }
    v17 = a6;
    if ( !a6 )
      v17 = "NULL";
    pfnWppTraceMessage(*((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v10), 43, a5, a4, v17, v16, 0);
  }
  if ( a6 )
  {
    do
      v13 = a6[++v9] == 0;
    while ( !v13 );
  }
  else
  {
    v6 = "NULL";
  }
  LOWORD(v18) = a4;
  return WppAutoLogTrace(a1, 0, a3, a5, v18, v6);
}

```

## disassembly

```asm
0x1400043e0  push    rbx
0x1400043e2  push    rbp
0x1400043e3  push    rsi
0x1400043e4  push    rdi
0x1400043e5  push    r13
0x1400043e7  push    r14
0x1400043e9  push    r15
0x1400043eb  sub     rsp, 40h
0x1400043ef  mov     rdi, [rsp+78h+arg_28]
0x1400043f7  mov     r13, rcx
0x1400043fa  mov     ebp, r8d
0x1400043fd  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x140004404  mov     r14d, r8d
0x140004407  mov     esi, 5
0x14000440c  shr     r14, 10h
0x140004410  lea     r8, aNull; "NULL"
0x140004417  movzx   r15d, r9w
0x14000441b  lea     r11d, [rbp-1]
0x14000441f  mov     edx, r11d
0x140004422  shr     rdx, 5
0x140004426  lea     rax, [r14+r14*4]
0x14000442a  and     edx, 7FFh
0x140004430  lea     r10, [rdx+rax*4]
0x140004434  mov     rax, cs:WPP_GLOBAL_Control
0x14000443b  mov     ecx, [rax+r10*4+2Ch]
0x140004440  bt      ecx, r11d
0x140004444  jb      short loc_1400044A4
0x140004446  test    rdi, rdi
0x140004449  jz      loc_140004518
0x14000444f  nop
0x140004450  cmp     byte ptr [rdi+rbx+1], 0
0x140004455  lea     rbx, [rbx+1]
0x140004459  jnz     short loc_140004450
0x14000445b  lea     rsi, [rbx+1]
0x14000445f  mov     r9, [rsp+78h+arg_20]
0x140004467  mov     r8d, ebp
0x14000446a  mov     [rsp+78h+var_40], 0
0x140004473  xor     edx, edx
0x140004475  mov     [rsp+78h+var_48], rsi
0x14000447a  mov     rcx, r13
0x14000447d  mov     [rsp+78h+var_50], rdi
0x140004482  mov     word ptr [rsp+78h+var_58], r15w
0x140004488  call    cs:__imp_WppAutoLogTrace
0x14000448f  nop     dword ptr [rax+rax+00h]
0x140004494  add     rsp, 40h
0x140004498  pop     r15
0x14000449a  pop     r14
0x14000449c  pop     r13
0x14000449e  pop     rdi
0x14000449f  pop     rsi
0x1400044a0  pop     rbp
0x1400044a1  pop     rbx
0x1400044a2  retn
0x1400044a4  test    rdi, rdi
0x1400044a7  jz      short loc_1400044BD
0x1400044a9  mov     rax, rbx
0x1400044ac  cmp     byte ptr [rdi+rax+1], 0
0x1400044b1  lea     rax, [rax+1]
0x1400044b5  jnz     short loc_1400044AC
0x1400044b7  lea     rcx, [rax+1]
0x1400044bb  jmp     short loc_1400044C0
0x1400044bd  mov     rcx, rsi
0x1400044c0  mov     rax, cs:pfnWppTraceMessage
0x1400044c7  lea     r10, [r14+r14*4]
0x1400044cb  test    rdi, rdi
0x1400044ce  mov     [rsp+78h+var_48], 0
0x1400044d7  mov     [rsp+78h+var_50], rcx
0x1400044dc  mov     rdx, rdi
0x1400044df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400044e6  cmovz   rdx, r8
0x1400044ea  mov     r8, [rsp+78h+arg_20]
0x1400044f2  add     r10, r10
0x1400044f5  mov     [rsp+78h+var_58], rdx
0x1400044fa  mov     r9d, r15d
0x1400044fd  mov     edx, 2Bh ; '+'
0x140004502  mov     rcx, [rcx+r10*8+18h]
0x140004507  call    _guard_dispatch_icall
0x14000450c  lea     r8, aNull; "NULL"
0x140004513  jmp     loc_140004446
0x140004518  mov     rdi, r8
0x14000451b  jmp     loc_14000445F
```
