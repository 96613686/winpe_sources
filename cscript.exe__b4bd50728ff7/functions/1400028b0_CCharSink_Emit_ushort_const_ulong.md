# CCharSink::Emit(ushort const *,ulong)

- ea: `0x1400028b0`
- end: `0x1400029db`
- name: `?Emit@CCharSink@@QEAAJPEBGK@Z`
- size: `299`
- prototype: `int(CCharSink *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140002820`
- `0x140002a70`
- `0x140005f10`

## callees

- `0x1400028b0`
- `0x140006250`
- `0x140016182`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1400029a6`
- `KERNEL32!GetProcessHeap` at `0x1400029a6`
- `KERNEL32!HeapReAlloc` at `0x1400029b9`
- `KERNEL32!HeapReAlloc` at `0x1400029b9`

## pseudocode

```c
__int64 __fastcall CCharSink::Emit(CCharSink *this, const unsigned __int16 *a2, unsigned int a3)
{
  unsigned int v3; // eax
  unsigned __int64 v5; // rbp
  unsigned int v7; // esi
  __int64 result; // rax
  unsigned int v9; // ecx
  __int64 v10; // r9
  unsigned int v11; // r8d
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rdx
  unsigned int v14; // eax
  void *v15; // rdi
  HANDLE ProcessHeap; // rax
  LPVOID v17; // rax
  SIZE_T dwBytes; // [rsp+40h] [rbp+8h] BYREF

  v3 = *((_DWORD *)this + 2);
  v5 = a3;
  v7 = v3 + a3;
  if ( v3 + a3 < v3 || v7 + 1 < v7 )
    return 2147942934LL;
  v9 = *((_DWORD *)this + 3);
  if ( v7 + 1 < v9 )
  {
LABEL_6:
    v10 = *(_QWORD *)this;
    if ( !*(_QWORD *)this )
      return 0;
    if ( !(_DWORD)v5 )
    {
LABEL_10:
      *(_WORD *)(*(_QWORD *)this + 2LL * *((unsigned int *)this + 2)) = 0;
      return 0;
    }
    dwBytes = 0;
    if ( is_mul_ok(v5, 2u) )
    {
      memcpy_0((void *)(v10 + 2LL * *((unsigned int *)this + 2)), a2, 2 * v5);
      *((_DWORD *)this + 2) = v7;
      goto LABEL_10;
    }
    return 2147942934LL;
  }
  v11 = v9 + a3;
  if ( v9 + (unsigned int)v5 < v9 )
    return 2147942934LL;
  v12 = 50LL * v11;
  *((_DWORD *)this + 3) = v11;
  if ( v12 > 0xFFFFFFFF )
    return 2147942934LL;
  v13 = (unsigned int)v12 / 0x64;
  v14 = v13 + v11;
  if ( (unsigned int)v13 + v11 < v11 )
    return 2147942934LL;
  *((_DWORD *)this + 3) = v14;
  dwBytes = 0;
  result = ULongLongMult(v14, v13, &dwBytes);
  if ( (int)result >= 0 )
  {
    v15 = *(void **)this;
    ProcessHeap = GetProcessHeap();
    v17 = HeapReAlloc(ProcessHeap, 0, v15, dwBytes);
    if ( !v17 )
      return 2147942414LL;
    *(_QWORD *)this = v17;
    goto LABEL_6;
  }
  return result;
}

```

## disassembly

```asm
0x1400028b0  mov     [rsp+arg_10], rbx
0x1400028b5  push    rbp
0x1400028b6  push    rsi
0x1400028b7  push    r14
0x1400028b9  sub     rsp, 20h
0x1400028bd  mov     eax, [rcx+8]
0x1400028c0  mov     r14, rdx
0x1400028c3  mov     ebp, r8d
0x1400028c6  mov     rbx, rcx
0x1400028c9  lea     esi, [rax+rbp]
0x1400028cc  cmp     esi, eax
0x1400028ce  jnb     short loc_1400028E3
0x1400028d0  mov     eax, 80070216h
0x1400028d5  mov     rbx, [rsp+38h+arg_10]
0x1400028da  add     rsp, 20h
0x1400028de  pop     r14
0x1400028e0  pop     rsi
0x1400028e1  pop     rbp
0x1400028e2  retn
0x1400028e3  lea     eax, [rsi+1]
0x1400028e6  cmp     eax, esi
0x1400028e8  jb      short loc_1400028D0
0x1400028ea  mov     ecx, [rcx+0Ch]
0x1400028ed  cmp     eax, ecx
0x1400028ef  jnb     short loc_140002945
0x1400028f1  mov     r9, [rbx]
0x1400028f4  test    r9, r9
0x1400028f7  jz      short loc_140002935
0x1400028f9  cmp     ebp, 1
0x1400028fc  jb      short loc_140002929
0x1400028fe  mov     eax, 2
0x140002903  mov     [rsp+38h+dwBytes], 0
0x14000290c  mul     rbp
0x14000290f  mov     r8, rax; Size
0x140002912  test    rdx, rdx
0x140002915  jnz     short loc_1400028D0
0x140002917  mov     eax, [rbx+8]
0x14000291a  mov     rdx, r14; Src
0x14000291d  lea     rcx, [r9+rax*2]; void *
0x140002921  call    memcpy_0
0x140002926  mov     [rbx+8], esi
0x140002929  mov     edx, [rbx+8]
0x14000292c  xor     eax, eax
0x14000292e  mov     rcx, [rbx]
0x140002931  mov     [rcx+rdx*2], ax
0x140002935  mov     rbx, [rsp+38h+arg_10]
0x14000293a  xor     eax, eax
0x14000293c  add     rsp, 20h
0x140002940  pop     r14
0x140002942  pop     rsi
0x140002943  pop     rbp
0x140002944  retn
0x140002945  lea     r8d, [rcx+rbp]
0x140002949  cmp     r8d, ecx
0x14000294c  jb      short loc_1400028D0
0x14000294e  mov     eax, r8d
0x140002951  imul    rcx, rax, 32h ; '2'
0x140002955  mov     eax, 0FFFFFFFFh
0x14000295a  mov     [rbx+0Ch], r8d
0x14000295e  cmp     rcx, rax
0x140002961  ja      loc_1400028D0
0x140002967  mov     eax, 51EB851Fh
0x14000296c  mul     ecx
0x14000296e  shr     edx, 5; unsigned __int64
0x140002971  lea     eax, [rdx+r8]
0x140002975  cmp     eax, r8d
0x140002978  jb      loc_1400028D0
0x14000297e  mov     ecx, eax; unsigned __int64
0x140002980  lea     r8, [rsp+38h+dwBytes]; unsigned __int64 *
0x140002985  mov     [rbx+0Ch], eax
0x140002988  mov     [rsp+38h+dwBytes], 0
0x140002991  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x140002996  test    eax, eax
0x140002998  js      loc_1400028D5
0x14000299e  mov     [rsp+38h+arg_8], rdi
0x1400029a3  mov     rdi, [rbx]
0x1400029a6  call    cs:__imp_GetProcessHeap
0x1400029ac  mov     r9, [rsp+38h+dwBytes]; dwBytes
0x1400029b1  mov     r8, rdi; lpMem
0x1400029b4  mov     rcx, rax; hHeap
0x1400029b7  xor     edx, edx; dwFlags
0x1400029b9  call    cs:__imp_HeapReAlloc
0x1400029bf  mov     rdi, [rsp+38h+arg_8]
0x1400029c4  test    rax, rax
0x1400029c7  jnz     short loc_1400029D3
0x1400029c9  mov     eax, 8007000Eh
0x1400029ce  jmp     loc_1400028D5
0x1400029d3  mov     [rbx], rax
0x1400029d6  jmp     loc_1400028F1
```
