# std::deque<JsonValue *,std::allocator<JsonValue *>>::_Tidy(void)

- ea: `0x14000df44`
- end: `0x14000dff7`
- name: `?_Tidy@?$deque@PEAVJsonValue@@V?$allocator@PEAVJsonValue@@@std@@@std@@AEAAXXZ`
- size: `179`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x14000d02c`
- `0x14000d384`
- `0x14000ea0c`
- `0x1400239a4`
- `0x140024cc0`
- `0x1400251d4`

## callees

- `0x1400028ac`
- `0x14000df44`

## pseudocode

```c
void __fastcall std::deque<JsonValue *>::_Tidy(_QWORD *a1)
{
  __int64 v2; // rax
  __int64 v3; // rax
  __int64 v4; // rdi
  void *v5; // rcx
  __int64 v6; // rcx
  void *v7; // rax

  while ( 1 )
  {
    v2 = a1[4];
    if ( !v2 )
      break;
    v3 = v2 - 1;
    a1[4] = v3;
    if ( !v3 )
      a1[3] = 0;
  }
  if ( a1[1] )
  {
    v4 = a1[2];
    while ( v4 > 0 )
    {
      --v4;
      v5 = *(void **)(a1[1] + 8 * v4);
      if ( v5 )
        operator delete(v5);
    }
    v6 = a1[1];
    if ( (unsigned __int64)(8LL * a1[2]) < 0x1000 )
    {
      v7 = (void *)a1[1];
    }
    else
    {
      v7 = *(void **)(v6 - 8);
      if ( (unsigned __int64)(v6 - (_QWORD)v7 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v7);
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x14000df44  mov     [rsp+arg_0], rbx
0x14000df49  push    rdi
0x14000df4a  sub     rsp, 20h
0x14000df4e  mov     rbx, rcx
0x14000df51  mov     rax, [rcx+20h]
0x14000df55  test    rax, rax
0x14000df58  jz      short loc_14000DF6E
0x14000df5a  sub     rax, 1
0x14000df5e  mov     [rcx+20h], rax
0x14000df62  jnz     short loc_14000DF51
0x14000df64  mov     qword ptr [rcx+18h], 0
0x14000df6c  jmp     short loc_14000DF51
0x14000df6e  cmp     qword ptr [rcx+8], 0
0x14000df73  jz      short loc_14000DFEC
0x14000df75  mov     rdi, [rcx+10h]
0x14000df79  jmp     short loc_14000DF95
0x14000df7b  mov     rax, [rbx+8]
0x14000df7f  dec     rdi
0x14000df82  mov     rcx, [rax+rdi*8]; Block
0x14000df86  test    rcx, rcx
0x14000df89  jz      short loc_14000DF95
0x14000df8b  mov     edx, 10h
0x14000df90  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14000df95  test    rdi, rdi
0x14000df98  jg      short loc_14000DF7B
0x14000df9a  mov     rax, [rbx+10h]
0x14000df9e  mov     rcx, [rbx+8]
0x14000dfa2  lea     rdx, ds:0[rax*8]
0x14000dfaa  cmp     rdx, 1000h
0x14000dfb1  jb      short loc_14000DFD1
0x14000dfb3  mov     rax, [rcx-8]
0x14000dfb7  sub     rcx, rax
0x14000dfba  sub     rcx, 8
0x14000dfbe  cmp     rcx, 1Fh
0x14000dfc2  ja      short loc_14000DFCA
0x14000dfc4  add     rdx, 27h ; '''
0x14000dfc8  jmp     short loc_14000DFD4
0x14000dfca  mov     ecx, 5
0x14000dfcf  int     29h; Win8: RtlFailFast(ecx)
0x14000dfd1  mov     rax, rcx
0x14000dfd4  mov     rcx, rax; Block
0x14000dfd7  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14000dfdc  mov     qword ptr [rbx+8], 0
0x14000dfe4  mov     qword ptr [rbx+10h], 0
0x14000dfec  mov     rbx, [rsp+28h+arg_0]
0x14000dff1  add     rsp, 20h
0x14000dff5  pop     rdi
0x14000dff6  retn
```
