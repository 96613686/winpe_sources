# _log_special_common

- ea: `0x18001e520`
- end: `0x18001e5b6`
- name: `_log_special_common`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001e500`

## callees

- `0x18001e360`
- `0x18001e520`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
__m128 __fastcall log_special_common(double a1, double a2, int a3, int a4, __int64 a5)
{
  int v6; // r8d
  int v7; // r9d
  int v9; // [rsp+20h] [rbp-48h]
  int v10; // [rsp+28h] [rbp-40h]
  __int64 v11; // [rsp+30h] [rbp-38h]

  v6 = a3 - 1;
  if ( !v6 )
  {
    v7 = 2;
    v11 = *(_QWORD *)&a1;
    v10 = 34;
    v9 = 4;
    goto LABEL_5;
  }
  if ( v6 == 1 )
  {
    v7 = 1;
    v11 = *(_QWORD *)&a1;
    v10 = 33;
    v9 = 8;
LABEL_5:
    handle_error(a5, a4, LODWORD(a2), v7, v9, v10, v11, 0, 1);
  }
  return *(__m128 *)&a2;
}

```

## disassembly

```asm
0x18001e520  mov     rax, rsp
0x18001e523  sub     rsp, 68h
0x18001e527  movaps  xmmword ptr [rax-18h], xmm6
0x18001e52b  movaps  xmm6, xmm1
0x18001e52e  mov     edx, r9d
0x18001e531  movaps  xmm3, xmm0
0x18001e534  sub     r8d, 1
0x18001e538  jz      short loc_18001E564
0x18001e53a  cmp     r8d, 1
0x18001e53e  jnz     short loc_18001E5A9
0x18001e540  mov     [rax-28h], r8d
0x18001e544  xorps   xmm2, xmm2
0x18001e547  movsd   qword ptr [rax-30h], xmm2
0x18001e54c  mov     r9d, r8d
0x18001e54f  movsd   qword ptr [rax-38h], xmm0
0x18001e554  mov     dword ptr [rax-40h], 21h ; '!'
0x18001e55b  mov     dword ptr [rax-48h], 8
0x18001e562  jmp     short loc_18001E591
0x18001e564  mov     [rsp+68h+var_28], 1
0x18001e56c  xorps   xmm0, xmm0
0x18001e56f  movsd   [rsp+68h+var_30], xmm0
0x18001e575  mov     r9d, 2
0x18001e57b  movsd   [rsp+68h+var_38], xmm3
0x18001e581  mov     [rsp+68h+var_40], 22h ; '"'
0x18001e589  mov     [rsp+68h+var_48], 4
0x18001e591  mov     rcx, [rsp+68h+arg_20]
0x18001e599  movsd   [rsp+68h+arg_8], xmm1
0x18001e59f  mov     r8, [rsp+68h+arg_8]
0x18001e5a4  call    _handle_error
0x18001e5a9  movaps  xmm0, xmm6
0x18001e5ac  movaps  xmm6, [rsp+68h+var_18]
0x18001e5b1  add     rsp, 68h
0x18001e5b5  retn
```
