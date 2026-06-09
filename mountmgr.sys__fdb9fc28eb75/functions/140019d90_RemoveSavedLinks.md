# RemoveSavedLinks

- ea: `0x140019d90`
- end: `0x140019e1f`
- name: `RemoveSavedLinks`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140014fc0`

## callees

- `0x140019d90`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140019dc6`
- `ntoskrnl!RtlCompareMemory` at `0x140019dc6`

## pseudocode

```c
_QWORD *__fastcall RemoveSavedLinks(__int64 a1, unsigned __int16 *a2)
{
  _QWORD *v2; // rbx
  _QWORD *v4; // rsi
  _WORD *v5; // rcx
  SIZE_T v6; // rdi
  _QWORD *v8; // rax
  _QWORD *v9; // rcx

  v2 = (_QWORD *)(a1 + 176);
  v4 = *(_QWORD **)(a1 + 176);
  if ( v4 == (_QWORD *)(a1 + 176) )
    return 0;
  while ( 1 )
  {
    v5 = (_WORD *)v4[4];
    if ( *v5 == *a2 )
    {
      v6 = *a2;
      if ( RtlCompareMemory(v5 + 1, a2 + 1, v6) == v6 )
        break;
    }
    v4 = (_QWORD *)*v4;
    if ( v4 == v2 )
      return 0;
  }
  if ( v4 == v2 )
    return 0;
  v8 = (_QWORD *)*v4;
  if ( *(_QWORD **)(*v4 + 8LL) != v4 || (v9 = (_QWORD *)v4[1], (_QWORD *)*v9 != v4) )
    __fastfail(3u);
  *v9 = v8;
  v8[1] = v9;
  return v4;
}

```

## disassembly

```asm
0x140019d90  push    rbx
0x140019d92  push    rsi
0x140019d93  push    rdi
0x140019d94  push    r14
0x140019d96  sub     rsp, 28h
0x140019d9a  lea     rbx, [rcx+0B0h]
0x140019da1  mov     r14, rdx
0x140019da4  mov     rsi, [rbx]
0x140019da7  cmp     rsi, rbx
0x140019daa  jz      short loc_140019DDF
0x140019dac  mov     rcx, [rsi+20h]
0x140019db0  movzx   eax, word ptr [r14]
0x140019db4  cmp     [rcx], ax
0x140019db7  jnz     short loc_140019DD7
0x140019db9  lea     rdx, [r14+2]; Source2
0x140019dbd  add     rcx, 2; Source1
0x140019dc1  mov     r8d, eax; Length
0x140019dc4  mov     edi, eax
0x140019dc6  call    cs:__imp_RtlCompareMemory
0x140019dcd  nop     dword ptr [rax+rax+00h]
0x140019dd2  cmp     rax, rdi
0x140019dd5  jz      short loc_140019DEC
0x140019dd7  mov     rsi, [rsi]
0x140019dda  cmp     rsi, rbx
0x140019ddd  jnz     short loc_140019DAC
0x140019ddf  xor     eax, eax
0x140019de1  add     rsp, 28h
0x140019de5  pop     r14
0x140019de7  pop     rdi
0x140019de8  pop     rsi
0x140019de9  pop     rbx
0x140019dea  retn
0x140019dec  cmp     rsi, rbx
0x140019def  jz      short loc_140019DDF
0x140019df1  mov     rax, [rsi]
0x140019df4  cmp     [rax+8], rsi
0x140019df8  jnz     short loc_140019E18
0x140019dfa  mov     rcx, [rsi+8]
0x140019dfe  cmp     [rcx], rsi
0x140019e01  jnz     short loc_140019E18
0x140019e03  mov     [rcx], rax
0x140019e06  mov     [rax+8], rcx
0x140019e0a  mov     rax, rsi
0x140019e0d  add     rsp, 28h
0x140019e11  pop     r14
0x140019e13  pop     rdi
0x140019e14  pop     rsi
0x140019e15  pop     rbx
0x140019e16  retn
0x140019e18  mov     ecx, 3
0x140019e1d  int     29h; Win8: RtlFailFast(ecx)
```
