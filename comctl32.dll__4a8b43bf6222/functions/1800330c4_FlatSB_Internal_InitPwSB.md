# FlatSB_Internal_InitPwSB

- ea: `0x1800330c4`
- end: `0x180033205`
- name: `FlatSB_Internal_InitPwSB`
- size: `321`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x1800315e0`
- `0x180031890`
- `0x180034450`
- `0x180034620`
- `0x180034880`
- `0x1800349c0`
- `0x180034cd0`

## callees

- `0x1800115f0`
- `0x180031ac8`
- `0x1800330c4`

## import_xrefs

- `GDI32!DeleteObject` at `0x18003319c`
- `GDI32!DeleteObject` at `0x18003319c`
- `GDI32!CreatePatternBrush` at `0x180033187`
- `GDI32!CreatePatternBrush` at `0x180033187`
- `GDI32!CreateBitmap` at `0x180033168`
- `GDI32!CreateBitmap` at `0x180033168`
- `KERNEL32!LocalFree` at `0x180033179`
- `KERNEL32!LocalFree` at `0x180033179`
- `KERNEL32!LocalAlloc` at `0x1800330ea`
- `KERNEL32!LocalAlloc` at `0x1800330ea`

## pseudocode

```c
char *__fastcall FlatSB_Internal_InitPwSB(__int64 a1)
{
  char *v2; // rbx
  char *result; // rax
  __int64 v4; // xmm1_8
  HBITMAP v5; // rax
  HBITMAP v6; // rdi
  HBRUSH PatternBrush; // rax
  __m128i Bits; // [rsp+30h] [rbp-28h] BYREF

  v2 = (char *)LocalAlloc(0x40u, 0x168u);
  if ( !v2 )
    return 0;
  Bits = _mm_load_si128((const __m128i *)&_xmm);
  *((_DWORD *)v2 + 70) = 100;
  *((_DWORD *)v2 + 74) = 100;
  *((_QWORD *)v2 + 33) = a1;
  FlatSB_InitWSBMetrics(v2);
  v4 = *((_QWORD *)v2 + 44);
  *(_OWORD *)(v2 + 312) = *((_OWORD *)v2 + 21);
  *((_DWORD *)v2 + 77) = 8;
  *((_QWORD *)v2 + 41) = v4;
  v5 = CreateBitmap(8, 8, 1u, 1u, &Bits);
  v6 = v5;
  if ( !v5 )
  {
LABEL_4:
    LocalFree(v2);
    return 0;
  }
  PatternBrush = CreatePatternBrush(v5);
  *((_QWORD *)v2 + 28) = PatternBrush;
  if ( !PatternBrush )
  {
    DeleteObject(v6);
    goto LABEL_4;
  }
  *((_QWORD *)v2 + 29) = PatternBrush;
  *((_QWORD *)v2 + 30) = PatternBrush;
  *((_DWORD *)v2 + 54) = 0xFFFFFF;
  *((_DWORD *)v2 + 53) = 0xFFFFFF;
  *((_DWORD *)v2 + 48) = 2;
  *((_DWORD *)v2 + 49) = 2;
  *((_DWORD *)v2 + 50) = -1;
  *((_DWORD *)v2 + 51) = -1;
  result = v2;
  *((_QWORD *)v2 + 31) = v6;
  return result;
}

```

## disassembly

```asm
0x1800330c4  mov     [rsp+arg_0], rbx
0x1800330c9  push    rdi
0x1800330ca  sub     rsp, 50h
0x1800330ce  mov     rax, cs:__security_cookie
0x1800330d5  xor     rax, rsp
0x1800330d8  mov     [rsp+58h+var_18], rax
0x1800330dd  mov     rdi, rcx
0x1800330e0  mov     edx, 168h; uBytes
0x1800330e5  mov     ecx, 40h ; '@'; uFlags
0x1800330ea  call    cs:__imp_LocalAlloc
0x1800330f0  mov     rbx, rax
0x1800330f3  test    rax, rax
0x1800330f6  jnz     short loc_1800330FF
0x1800330f8  xor     eax, eax
0x1800330fa  jmp     loc_1800331ED
0x1800330ff  movdqa  xmm0, cs:__xmm@005500aa005500aa005500aa005500aa
0x180033107  mov     eax, 64h ; 'd'
0x18003310c  movups  [rsp+58h+Bits], xmm0
0x180033111  mov     rcx, rbx
0x180033114  mov     [rbx+118h], eax
0x18003311a  mov     [rbx+128h], eax
0x180033120  mov     [rbx+108h], rdi
0x180033127  call    FlatSB_InitWSBMetrics
0x18003312c  movups  xmm0, xmmword ptr [rbx+150h]
0x180033133  lea     rax, [rsp+58h+Bits]
0x180033138  mov     ecx, 8; nWidth
0x18003313d  movsd   xmm1, qword ptr [rbx+160h]
0x180033145  mov     edx, ecx; nHeight
0x180033147  movups  xmmword ptr [rbx+138h], xmm0
0x18003314e  mov     [rbx+134h], ecx
0x180033154  lea     r8d, [rcx-7]; nPlanes
0x180033158  movsd   qword ptr [rbx+148h], xmm1
0x180033160  mov     r9d, r8d; nBitCount
0x180033163  mov     [rsp+58h+lpBits], rax; lpBits
0x180033168  call    cs:__imp_CreateBitmap
0x18003316e  mov     rdi, rax
0x180033171  test    rax, rax
0x180033174  jnz     short loc_180033184
0x180033176  mov     rcx, rbx; hMem
0x180033179  call    cs:__imp_LocalFree
0x18003317f  jmp     loc_1800330F8
0x180033184  mov     rcx, rdi; hbm
0x180033187  call    cs:__imp_CreatePatternBrush
0x18003318d  mov     [rbx+0E0h], rax
0x180033194  test    rax, rax
0x180033197  jnz     short loc_1800331A4
0x180033199  mov     rcx, rdi; ho
0x18003319c  call    cs:__imp_DeleteObject
0x1800331a2  jmp     short loc_180033176
0x1800331a4  mov     [rbx+0E8h], rax
0x1800331ab  mov     [rbx+0F0h], rax
0x1800331b2  mov     eax, 0FFFFFFh
0x1800331b7  mov     [rbx+0D8h], eax
0x1800331bd  mov     [rbx+0D4h], eax
0x1800331c3  mov     eax, 2
0x1800331c8  mov     [rbx+0C0h], eax
0x1800331ce  mov     [rbx+0C4h], eax
0x1800331d4  or      eax, 0FFFFFFFFh
0x1800331d7  mov     [rbx+0C8h], eax
0x1800331dd  mov     [rbx+0CCh], eax
0x1800331e3  mov     rax, rbx
0x1800331e6  mov     [rbx+0F8h], rdi
0x1800331ed  mov     rcx, [rsp+58h+var_18]
0x1800331f2  xor     rcx, rsp; StackCookie
0x1800331f5  call    __security_check_cookie
0x1800331fa  mov     rbx, [rsp+58h+arg_0]
0x1800331ff  add     rsp, 50h
0x180033203  pop     rdi
0x180033204  retn
```
