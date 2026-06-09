# PrjfMungeReparseEnumerate

- ea: `0x140028048`
- end: `0x1400280df`
- name: `PrjfMungeReparseEnumerate`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1400287d4`

## callees

- `0x14000b1d0`
- `0x14000ba50`
- `0x140021008`
- `0x140028048`

## pseudocode

```c
__int64 __fastcall PrjfMungeReparseEnumerate(__int64 a1, _DWORD *a2, void *a3, __int64 a4, char a5, _DWORD *a6)
{
  unsigned int v6; // r14d

  v6 = a4;
  if ( (_DWORD)a1 != 33 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(a1, a2, a3, a4);
  if ( v6 < 0x10 )
  {
    *a6 = 0;
  }
  else
  {
    if ( a2[2] != -1879048164 )
    {
      if ( a5 )
        RtlCopyToUser(a3, a2, 0x10u);
      else
        RtlCopyVolatileMemory(a3, a2, 0x10u);
    }
    *a6 = 16;
  }
  return 0;
}

```

## disassembly

```asm
0x140028048  push    rbx
0x14002804a  push    rsi
0x14002804b  push    rdi
0x14002804c  push    r14
0x14002804e  sub     rsp, 38h
0x140028052  mov     r14d, r9d
0x140028055  mov     rsi, r8
0x140028058  mov     rdi, rdx
0x14002805b  mov     [rsp+58h+var_38], 0
0x140028060  xor     ebx, ebx
0x140028062  cmp     ecx, 21h ; '!'
0x140028065  jz      short loc_14002806D
0x140028067  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002806c  nop
0x14002806d  cmp     r14d, 10h
0x140028071  jb      short loc_1400280BD
0x140028073  cmp     dword ptr [rdi+8], 9000001Ch
0x14002807a  jz      short loc_1400280A8
0x14002807c  mov     [rsp+58h+var_38], 1
0x140028081  mov     r8d, 10h; Size
0x140028087  mov     rdx, rdi; Src
0x14002808a  mov     rcx, rsi; void *
0x14002808d  cmp     [rsp+58h+arg_20], 0
0x140028095  jz      short loc_14002809E
0x140028097  call    RtlCopyToUser
0x14002809c  jmp     short loc_1400280A3
0x14002809e  call    RtlCopyVolatileMemory
0x1400280a3  mov     [rsp+58h+var_38], 0
0x1400280a8  mov     rax, [rsp+58h+arg_28]
0x1400280b0  mov     dword ptr [rax], 10h
0x1400280b6  mov     [rsp+58h+var_38], 0
0x1400280bb  jmp     short loc_1400280CB
0x1400280bd  mov     rax, [rsp+58h+arg_28]
0x1400280c5  mov     dword ptr [rax], 0
0x1400280cb  jmp     short loc_1400280D2
0x1400280cd  mov     ebx, 0C00000E8h
0x1400280d2  mov     eax, ebx
0x1400280d4  add     rsp, 38h
0x1400280d8  pop     r14
0x1400280da  pop     rdi
0x1400280db  pop     rsi
0x1400280dc  pop     rbx
0x1400280dd  retn
0x1400472d9  push    rbp
0x1400472db  sub     rsp, 20h
0x1400472df  mov     rbp, rdx
0x1400472e2  xor     eax, eax
0x1400472e4  cmp     [rbp+20h], al
0x1400472e7  jz      short loc_1400472F8
0x1400472e9  cmp     [rbp+80h], al
0x1400472ef  setnz   al
0x1400472f2  mov     [rbp+24h], eax
0x1400472f5  mov     eax, [rbp+24h]
0x1400472f8  add     rsp, 20h
0x1400472fc  pop     rbp
0x1400472fd  retn
```
