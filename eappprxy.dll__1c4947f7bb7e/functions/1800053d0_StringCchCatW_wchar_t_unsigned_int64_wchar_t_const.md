# StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)

- ea: `0x1800053d0`
- end: `0x180005447`
- name: `?StringCchCatW@@YAJPEA_W_KPEB_W@Z`
- size: `119`
- prototype: `int(wchar_t *, unsigned __int64, const wchar_t *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800045a0`
- `0x180005590`
- `0x180005714`

## callees

- `0x1800053d0`
- `0x18000dd10`

## pseudocode

```c
__int64 __fastcall StringCchCatW(wchar_t *a1, __int64 a2, const wchar_t *a3)
{
  __int64 v4; // r9
  wchar_t *v5; // rax
  size_t *v6; // r8
  __int64 v7; // r10
  size_t v9; // [rsp+20h] [rbp-18h]

  v4 = 260;
  v5 = a1;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v4;
  }
  while ( v4 );
  v6 = v4 == 0 ? (size_t *)0x80070057LL : 0LL;
  if ( v4 )
  {
    v7 = (260 - v4) & -(__int64)(v4 != 0);
    LODWORD(v6) = StringCopyWorkerW(&a1[v7], 260 - v7, v6, a3, v9);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800053d0  mov     [rsp+arg_0], rbx
0x1800053d5  push    rdi
0x1800053d6  sub     rsp, 30h
0x1800053da  mov     edx, 104h
0x1800053df  mov     rbx, r8
0x1800053e2  mov     r9d, edx
0x1800053e5  mov     r11, rcx
0x1800053e8  mov     rax, rcx
0x1800053eb  xor     edi, edi
0x1800053ed  cmp     [rax], di
0x1800053f0  jz      short loc_1800053FC
0x1800053f2  add     rax, 2
0x1800053f6  sub     r9, 1
0x1800053fa  jnz     short loc_1800053ED
0x1800053fc  mov     rax, r9
0x1800053ff  mov     rcx, rdx
0x180005402  neg     rax
0x180005405  mov     rax, r9
0x180005408  sbb     r8d, r8d
0x18000540b  sub     rcx, r9
0x18000540e  not     r8d
0x180005411  and     r8d, 80070057h; pcchNewDestLength
0x180005418  neg     rax
0x18000541b  sbb     r10, r10
0x18000541e  and     r10, rcx
0x180005421  test    r9, r9
0x180005424  jz      short loc_180005438
0x180005426  sub     rdx, r10; cchDest
0x180005429  lea     rcx, [r11+r10*2]; pszDest
0x18000542d  mov     r9, rbx; pszSrc
0x180005430  call    StringCopyWorkerW
0x180005435  mov     r8d, eax
0x180005438  mov     rbx, [rsp+38h+arg_0]
0x18000543d  mov     eax, r8d
0x180005440  add     rsp, 30h
0x180005444  pop     rdi
0x180005445  retn
```
