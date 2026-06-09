# WPP_RECORDER_SF_qs

- ea: `0x140005050`
- end: `0x1400051ac`
- name: `WPP_RECORDER_SF_qs`
- size: `348`
- prototype: ``
- caller_count: `11`
- callee_count: `2`
- tags: ``

## callers

- `0x140001460`
- `0x1400060c4`
- `0x140007350`
- `0x14000877c`
- `0x140010260`
- `0x140017ab8`
- `0x140018040`
- `0x140018e9c`
- `0x1400197ec`
- `0x140019cd0`
- `0x140037080`

## callees

- `0x140005050`
- `0x14001fc70`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140005190`
- `WppRecorder!WppAutoLogTrace` at `0x140005190`

## pseudocode

```c
__int64 __fastcall WPP_RECORDER_SF_qs(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned __int16 a4,
        __int64 a5,
        char a6,
        const char *a7)
{
  __int64 v7; // rbx
  __int64 v8; // rdi
  unsigned __int64 v11; // r14
  int v13; // ecx
  __int64 v14; // rax
  const char *v15; // rdx
  int v17; // [rsp+20h] [rbp-68h]

  v7 = (__int64)a7;
  v8 = -1;
  v11 = (unsigned __int64)a3 >> 16;
  v13 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v11 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v13, a3 - 1) )
  {
    if ( a7 )
    {
      v14 = -1;
      do
        ++v14;
      while ( a7[v14] );
    }
    v15 = a7;
    if ( !a7 )
      v15 = "NULL";
    pfnWppTraceMessage(*((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v11), 43, a5, a4, &a6, 8, v15);
  }
  if ( v7 )
  {
    do
      ++v8;
    while ( *(_BYTE *)(v7 + v8) );
  }
  LOWORD(v17) = a4;
  return WppAutoLogTrace(a1, 0, a3, a5, v17, &a6);
}

```

## disassembly

```asm
0x140005050  push    rbx
0x140005052  push    rbp
0x140005053  push    rsi
0x140005054  push    rdi
0x140005055  push    r12
0x140005057  push    r14
0x140005059  push    r15
0x14000505b  sub     rsp, 50h
0x14000505f  mov     rbx, [rsp+88h+arg_30]
0x140005067  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14000506b  mov     ebp, r8d
0x14000506e  mov     r12, rcx
0x140005071  mov     r14d, r8d
0x140005074  lea     r8, aNull; "NULL"
0x14000507b  shr     r14, 10h
0x14000507f  movzx   r15d, r9w
0x140005083  lea     esi, [rdi+6]
0x140005086  lea     r11d, [rbp-1]
0x14000508a  mov     edx, r11d
0x14000508d  shr     rdx, 5
0x140005091  lea     rax, [r14+r14*4]
0x140005095  and     edx, 7FFh
0x14000509b  lea     r10, [rdx+rax*4]
0x14000509f  mov     rax, cs:WPP_GLOBAL_Control
0x1400050a6  mov     ecx, [rax+r10*4+2Ch]
0x1400050ab  bt      ecx, r11d
0x1400050af  jnb     loc_140005138
0x1400050b5  test    rbx, rbx
0x1400050b8  jz      short loc_1400050CC
0x1400050ba  mov     rax, rdi
0x1400050bd  inc     rax
0x1400050c0  cmp     byte ptr [rbx+rax], 0
0x1400050c4  jnz     short loc_1400050BD
0x1400050c6  lea     rcx, [rax+1]
0x1400050ca  jmp     short loc_1400050CF
0x1400050cc  mov     rcx, rsi
0x1400050cf  mov     rax, cs:pfnWppTraceMessage
0x1400050d6  lea     r10, [r14+r14*4]
0x1400050da  mov     [rsp+88h+var_48], 0
0x1400050e3  test    rbx, rbx
0x1400050e6  mov     [rsp+88h+var_50], rcx
0x1400050eb  mov     rdx, rbx
0x1400050ee  cmovz   rdx, r8
0x1400050f2  lea     rcx, [rsp+88h+arg_28]
0x1400050fa  mov     r8, [rsp+88h+arg_20]
0x140005102  add     r10, r10
0x140005105  mov     [rsp+88h+var_58], rdx
0x14000510a  mov     r9d, r15d
0x14000510d  mov     [rsp+88h+var_60], 8
0x140005116  mov     edx, 2Bh ; '+'
0x14000511b  mov     [rsp+88h+var_68], rcx
0x140005120  mov     rcx, cs:WPP_GLOBAL_Control
0x140005127  mov     rcx, [rcx+r10*8+18h]
0x14000512c  call    _guard_dispatch_icall
0x140005131  lea     r8, aNull; "NULL"
0x140005138  test    rbx, rbx
0x14000513b  jz      short loc_14000514D
0x14000513d  inc     rdi
0x140005140  cmp     byte ptr [rbx+rdi], 0
0x140005144  jnz     short loc_14000513D
0x140005146  lea     rsi, [rdi+1]
0x14000514a  test    rbx, rbx
0x14000514d  mov     r9, [rsp+88h+arg_20]
0x140005155  lea     rax, [rsp+88h+arg_28]
0x14000515d  mov     [rsp+88h+var_40], 0
0x140005166  cmovz   rbx, r8
0x14000516a  mov     [rsp+88h+var_48], rsi
0x14000516f  mov     r8d, ebp
0x140005172  mov     [rsp+88h+var_50], rbx
0x140005177  xor     edx, edx
0x140005179  mov     [rsp+88h+var_58], 8
0x140005182  mov     rcx, r12
0x140005185  mov     [rsp+88h+var_60], rax
0x14000518a  mov     word ptr [rsp+88h+var_68], r15w
0x140005190  call    cs:__imp_WppAutoLogTrace
0x140005197  nop     dword ptr [rax+rax+00h]
0x14000519c  add     rsp, 50h
0x1400051a0  pop     r15
0x1400051a2  pop     r14
0x1400051a4  pop     r12
0x1400051a6  pop     rdi
0x1400051a7  pop     rsi
0x1400051a8  pop     rbp
0x1400051a9  pop     rbx
0x1400051aa  retn
```
