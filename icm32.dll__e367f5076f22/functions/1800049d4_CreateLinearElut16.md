# CreateLinearElut16

- ea: `0x1800049d4`
- end: `0x180004a33`
- name: `CreateLinearElut16`
- size: `95`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800029a4`
- `0x1800042fc`
- `0x18001a358`
- `0x18001bb30`

## callees

- `0x1800049d4`

## pseudocode

```c
void __fastcall CreateLinearElut16(__int64 a1, int a2)
{
  __int16 i; // r10
  __int64 v4; // rcx
  unsigned int v5; // eax

  if ( a2 > 0 )
  {
    for ( i = 0; i < a2; ++i )
    {
      v4 = i;
      v5 = (((unsigned int)(a2 - 1) >> 1) + 0xFFFF * i - 1) / (a2 - 1);
      if ( v5 > 0xFFFF )
        LOWORD(v5) = -1;
      *(_WORD *)(a1 + 2 * v4) = v5;
    }
  }
}

```

## disassembly

```asm
0x1800049d4  test    edx, edx
0x1800049d6  jle     short locret_180004A32
0x1800049d8  mov     [rsp+arg_0], rbx
0x1800049dd  mov     [rsp+arg_8], rdi
0x1800049e2  lea     r11d, [rdx-1]
0x1800049e6  mov     r8d, edx
0x1800049e9  mov     r9d, r11d
0x1800049ec  mov     rbx, rcx
0x1800049ef  shr     r9d, 1
0x1800049f2  mov     edi, 0FFFFh
0x1800049f7  xor     r10d, r10d
0x1800049fa  xor     edx, edx
0x1800049fc  movsx   eax, r10w
0x180004a00  imul    eax, 0FFFFh
0x180004a06  movsx   rcx, r10w
0x180004a0a  dec     eax
0x180004a0c  add     eax, r9d
0x180004a0f  div     r11d
0x180004a12  cmp     eax, edi
0x180004a14  cmova   eax, edi
0x180004a17  inc     r10w
0x180004a1b  mov     [rbx+rcx*2], ax
0x180004a1f  movsx   eax, r10w
0x180004a23  cmp     eax, r8d
0x180004a26  jl      short loc_1800049FA
0x180004a28  mov     rbx, [rsp+arg_0]
0x180004a2d  mov     rdi, [rsp+arg_8]
0x180004a32  retn
```
