# CreateLinearElut

- ea: `0x1800207d0`
- end: `0x180020821`
- name: `CreateLinearElut`
- size: `81`
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

- `0x1800207d0`

## pseudocode

```c
void __fastcall CreateLinearElut(__int64 a1, int a2)
{
  __int64 v2; // r10
  unsigned int v3; // eax

  if ( a2 > 0 )
  {
    v2 = 0;
    do
    {
      v3 = (((unsigned int)(a2 - 1) >> 1) + 1023 * (_DWORD)v2 - 1) / (a2 - 1);
      if ( v3 > 0x3FF )
        LOWORD(v3) = 1023;
      *(_WORD *)(a1 + 2 * v2) = v3;
      v2 = (unsigned int)(v2 + 1);
    }
    while ( (int)v2 < a2 );
  }
}

```

## disassembly

```asm
0x1800207d0  test    edx, edx
0x1800207d2  jle     short locret_180020820
0x1800207d4  mov     [rsp+arg_0], rbx
0x1800207d9  mov     [rsp+arg_8], rdi
0x1800207de  lea     r11d, [rdx-1]
0x1800207e2  mov     r8d, edx
0x1800207e5  mov     r9d, r11d
0x1800207e8  mov     edi, 3FFh
0x1800207ed  shr     r9d, 1
0x1800207f0  xor     r10d, r10d
0x1800207f3  imul    eax, r10d, 3FFh
0x1800207fa  xor     edx, edx
0x1800207fc  dec     eax
0x1800207fe  add     eax, r9d
0x180020801  div     r11d
0x180020804  cmp     eax, edi
0x180020806  cmova   eax, edi
0x180020809  mov     [rcx+r10*2], ax
0x18002080e  inc     r10d
0x180020811  cmp     r10d, r8d
0x180020814  jl      short loc_1800207F3
0x180020816  mov     rbx, [rsp+arg_0]
0x18002081b  mov     rdi, [rsp+arg_8]
0x180020820  retn
```
