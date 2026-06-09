# ReadCFFILEEntry

- ea: `0x180002978`
- end: `0x180002a22`
- name: `ReadCFFILEEntry`
- size: `170`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800039b8`

## callees

- `0x180002718`
- `0x180002978`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall ReadCFFILEEntry(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  int v5; // edi
  int v8; // eax
  int v9; // r8d
  _DWORD *v10; // rcx
  int v12; // eax
  int v13; // [rsp+60h] [rbp+8h] BYREF

  *a4 = 0;
  v5 = a1;
  v13 = 0;
  v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, int *, __int64))(a1 + 48))(
         *(_QWORD *)(a2 + 376),
         a1 + 2564,
         16,
         &v13,
         a3);
  if ( !v8 )
    return 0;
  v10 = *(_DWORD **)(a2 + 88);
  if ( v8 != 16 )
  {
    v12 = v13;
    *v10 = 4;
    v10[1] = v12;
    v10[2] = 1;
    goto LABEL_4;
  }
  if ( !(unsigned int)ReadPSZ(*(_QWORD *)(a2 + 376), v5 + 2858, v9, v5, (__int64)v10, a3) )
  {
LABEL_4:
    *a4 = 1;
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180002978  push    rbx
0x18000297a  push    rbp
0x18000297b  push    rsi
0x18000297c  push    rdi
0x18000297d  sub     rsp, 38h
0x180002981  mov     dword ptr [r9], 0
0x180002988  mov     rsi, rdx
0x18000298b  mov     rdi, rcx
0x18000298e  mov     [rsp+58h+var_38], r8
0x180002993  mov     rbx, r9
0x180002996  mov     [rsp+58h+arg_0], 0
0x18000299e  mov     rbp, r8
0x1800029a1  lea     rdx, [rcx+0A04h]
0x1800029a8  mov     rcx, [rsi+178h]
0x1800029af  lea     r9, [rsp+58h+arg_0]
0x1800029b4  mov     rax, [rdi+30h]
0x1800029b8  mov     r8d, 10h
0x1800029be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029c3  test    eax, eax
0x1800029c5  jz      short loc_1800029FA
0x1800029c7  mov     rcx, [rsi+58h]
0x1800029cb  cmp     eax, 10h
0x1800029ce  jnz     short loc_180002A0C
0x1800029d0  mov     [rsp+58h+var_30], rbp
0x1800029d5  lea     rdx, [rdi+0B2Ah]
0x1800029dc  mov     [rsp+58h+var_38], rcx
0x1800029e1  mov     r9, rdi
0x1800029e4  mov     rcx, [rsi+178h]
0x1800029eb  call    ReadPSZ
0x1800029f0  test    eax, eax
0x1800029f2  jnz     short loc_180002A05
0x1800029f4  mov     dword ptr [rbx], 1
0x1800029fa  xor     eax, eax
0x1800029fc  add     rsp, 38h
0x180002a00  pop     rdi
0x180002a01  pop     rsi
0x180002a02  pop     rbp
0x180002a03  pop     rbx
0x180002a04  retn
0x180002a05  mov     eax, 1
0x180002a0a  jmp     short loc_1800029FC
0x180002a0c  mov     eax, [rsp+58h+arg_0]
0x180002a10  mov     dword ptr [rcx], 4
0x180002a16  mov     [rcx+4], eax
0x180002a19  mov     dword ptr [rcx+8], 1
0x180002a20  jmp     short loc_1800029F4
```
