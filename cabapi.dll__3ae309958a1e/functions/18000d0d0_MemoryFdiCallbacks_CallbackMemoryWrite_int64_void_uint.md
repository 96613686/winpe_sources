# MemoryFdiCallbacks::CallbackMemoryWrite(__int64,void *,uint)

- ea: `0x18000d0d0`
- end: `0x18000d166`
- name: `?CallbackMemoryWrite@MemoryFdiCallbacks@@SAI_JPEAXI@Z`
- size: `150`
- prototype: `__int64 __fastcall(__int64, void *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001f22`
- `0x180001f52`
- `0x180001fd6`
- `0x18000d0d0`
- `0x180013df8`

## pseudocode

```c
__int64 __fastcall MemoryFdiCallbacks::CallbackMemoryWrite(__int64 a1, void *a2, unsigned int a3)
{
  __int64 v6; // rdx
  void *v7; // rcx
  unsigned int v8; // edi
  unsigned int v9; // r8d
  __int64 result; // rax
  int v11; // ecx

  if ( a3 )
  {
    v6 = *(unsigned int *)(a1 + 24);
    v7 = (void *)(v6 + **(_QWORD **)(a1 + 8));
    if ( !v7 )
      goto LABEL_3;
    v8 = **(_DWORD **)(a1 + 16) - v6;
    if ( a2 && v8 >= a3 )
    {
      memcpy_0(v7, a2, a3);
      goto LABEL_11;
    }
    memset_0(v7, 0, v8);
    if ( a2 )
    {
      if ( v8 >= a3 )
        goto LABEL_11;
      *(_DWORD *)o__errno_0() = 34;
    }
    else
    {
LABEL_3:
      *(_DWORD *)o__errno_0() = 22;
    }
    invalid_parameter_noinfo();
  }
LABEL_11:
  v9 = *(_DWORD *)(a1 + 24);
  result = 0xFFFFFFFFLL;
  v11 = -1;
  if ( v9 + a3 >= v9 )
  {
    v11 = v9 + a3;
    result = a3;
  }
  *(_DWORD *)(a1 + 24) = v11;
  return result;
}

```

## disassembly

```asm
0x18000d0d0  push    rbx
0x18000d0d2  push    rbp
0x18000d0d3  push    rsi
0x18000d0d4  push    rdi
0x18000d0d5  sub     rsp, 28h
0x18000d0d9  mov     ebx, r8d
0x18000d0dc  mov     rbp, rdx
0x18000d0df  mov     rsi, rcx
0x18000d0e2  test    r8d, r8d
0x18000d0e5  jz      short loc_18000D144
0x18000d0e7  mov     rax, [rcx+8]
0x18000d0eb  mov     edx, [rcx+18h]
0x18000d0ee  mov     rcx, [rax]
0x18000d0f1  add     rcx, rdx; void *
0x18000d0f4  jnz     short loc_18000D103
0x18000d0f6  call    _o__errno_0
0x18000d0fb  mov     dword ptr [rax], 16h
0x18000d101  jmp     short loc_18000D13F
0x18000d103  mov     rax, [rsi+10h]
0x18000d107  mov     edi, [rax]
0x18000d109  sub     edi, edx
0x18000d10b  test    rbp, rbp
0x18000d10e  jz      short loc_18000D121
0x18000d110  cmp     edi, ebx
0x18000d112  jb      short loc_18000D121
0x18000d114  mov     r8, rbx; Size
0x18000d117  mov     rdx, rbp; Src
0x18000d11a  call    memcpy_0
0x18000d11f  jmp     short loc_18000D144
0x18000d121  mov     r8d, edi; Size
0x18000d124  xor     edx, edx; Val
0x18000d126  call    memset_0
0x18000d12b  test    rbp, rbp
0x18000d12e  jz      short loc_18000D0F6
0x18000d130  cmp     edi, ebx
0x18000d132  jnb     short loc_18000D144
0x18000d134  call    _o__errno_0
0x18000d139  mov     dword ptr [rax], 22h ; '"'
0x18000d13f  call    _invalid_parameter_noinfo
0x18000d144  mov     r8d, [rsi+18h]
0x18000d148  or      eax, 0FFFFFFFFh
0x18000d14b  mov     ecx, eax
0x18000d14d  lea     edx, [r8+rbx]
0x18000d151  cmp     edx, r8d
0x18000d154  cmovnb  ecx, edx
0x18000d157  cmovnb  eax, ebx
0x18000d15a  mov     [rsi+18h], ecx
0x18000d15d  add     rsp, 28h
0x18000d161  pop     rdi
0x18000d162  pop     rsi
0x18000d163  pop     rbp
0x18000d164  pop     rbx
0x18000d165  retn
```
