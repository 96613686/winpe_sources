# WPP_RECORDER_SF_s

- ea: `0x1400051b4`
- end: `0x1400052e0`
- name: `WPP_RECORDER_SF_s`
- size: `300`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x1400011ac`
- `0x1400035cc`
- `0x1400060c4`
- `0x140007350`
- `0x140007d40`
- `0x14000dd28`
- `0x14000e700`
- `0x14000fc00`
- `0x140010810`
- `0x140013abc`
- `0x140019b64`
- `0x140037080`

## callees

- `0x1400051b4`
- `0x14001fc70`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400052c4`
- `WppRecorder!WppAutoLogTrace` at `0x1400052c4`

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
  const char *v6; // rbx
  __int64 v7; // rdi
  unsigned __int64 v10; // r14
  int v12; // ecx
  __int64 v13; // rax
  __int64 v14; // rcx
  const char *v15; // rdx
  bool v16; // zf
  int v18; // [rsp+20h] [rbp-58h]

  v6 = a6;
  v7 = -1;
  v10 = (unsigned __int64)a3 >> 16;
  v12 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v10 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v12, a3 - 1) )
  {
    if ( a6 )
    {
      v13 = -1;
      do
        ++v13;
      while ( a6[v13] );
      v14 = v13 + 1;
    }
    else
    {
      v14 = 5;
    }
    v15 = a6;
    if ( !a6 )
      v15 = "NULL";
    pfnWppTraceMessage(*((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v10), 43, a5, a4, v15, v14, 0);
  }
  v16 = a6 == 0;
  if ( a6 )
  {
    do
      ++v7;
    while ( a6[v7] );
    v16 = a6 == 0;
  }
  if ( v16 )
    v6 = "NULL";
  LOWORD(v18) = a4;
  return WppAutoLogTrace(a1, 0, a3, a5, v18, v6);
}

```

## disassembly

```asm
0x1400051b4  push    rbx
0x1400051b6  push    rbp
0x1400051b7  push    rsi
0x1400051b8  push    rdi
0x1400051b9  push    r12
0x1400051bb  push    r14
0x1400051bd  push    r15
0x1400051bf  sub     rsp, 40h
0x1400051c3  mov     rbx, [rsp+78h+arg_28]
0x1400051cb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400051cf  mov     ebp, r8d
0x1400051d2  mov     r12, rcx
0x1400051d5  mov     r14d, r8d
0x1400051d8  lea     r8, aNull; "NULL"
0x1400051df  shr     r14, 10h
0x1400051e3  movzx   r15d, r9w
0x1400051e7  lea     esi, [rdi+6]
0x1400051ea  lea     r11d, [rbp-1]
0x1400051ee  mov     edx, r11d
0x1400051f1  shr     rdx, 5
0x1400051f5  lea     rax, [r14+r14*4]
0x1400051f9  and     edx, 7FFh
0x1400051ff  lea     r10, [rdx+rax*4]
0x140005203  mov     rax, cs:WPP_GLOBAL_Control
0x14000520a  mov     ecx, [rax+r10*4+2Ch]
0x14000520f  bt      ecx, r11d
0x140005213  jnb     short loc_140005282
0x140005215  test    rbx, rbx
0x140005218  jz      short loc_14000522C
0x14000521a  mov     rax, rdi
0x14000521d  inc     rax
0x140005220  cmp     byte ptr [rbx+rax], 0
0x140005224  jnz     short loc_14000521D
0x140005226  lea     rcx, [rax+1]
0x14000522a  jmp     short loc_14000522F
0x14000522c  mov     rcx, rsi
0x14000522f  mov     rax, cs:pfnWppTraceMessage
0x140005236  lea     r10, [r14+r14*4]
0x14000523a  test    rbx, rbx
0x14000523d  mov     [rsp+78h+var_48], 0
0x140005246  mov     [rsp+78h+var_50], rcx
0x14000524b  mov     rdx, rbx
0x14000524e  mov     rcx, cs:WPP_GLOBAL_Control
0x140005255  cmovz   rdx, r8
0x140005259  mov     r8, [rsp+78h+arg_20]
0x140005261  add     r10, r10
0x140005264  mov     [rsp+78h+var_58], rdx
0x140005269  mov     r9d, r15d
0x14000526c  mov     edx, 2Bh ; '+'
0x140005271  mov     rcx, [rcx+r10*8+18h]
0x140005276  call    _guard_dispatch_icall
0x14000527b  lea     r8, aNull; "NULL"
0x140005282  test    rbx, rbx
0x140005285  jz      short loc_140005297
0x140005287  inc     rdi
0x14000528a  cmp     byte ptr [rbx+rdi], 0
0x14000528e  jnz     short loc_140005287
0x140005290  lea     rsi, [rdi+1]
0x140005294  test    rbx, rbx
0x140005297  mov     r9, [rsp+78h+arg_20]
0x14000529f  cmovz   rbx, r8
0x1400052a3  mov     [rsp+78h+var_40], 0
0x1400052ac  mov     r8d, ebp
0x1400052af  mov     [rsp+78h+var_48], rsi
0x1400052b4  xor     edx, edx
0x1400052b6  mov     [rsp+78h+var_50], rbx
0x1400052bb  mov     rcx, r12
0x1400052be  mov     word ptr [rsp+78h+var_58], r15w
0x1400052c4  call    cs:__imp_WppAutoLogTrace
0x1400052cb  nop     dword ptr [rax+rax+00h]
0x1400052d0  add     rsp, 40h
0x1400052d4  pop     r15
0x1400052d6  pop     r14
0x1400052d8  pop     r12
0x1400052da  pop     rdi
0x1400052db  pop     rsi
0x1400052dc  pop     rbp
0x1400052dd  pop     rbx
0x1400052de  retn
```
