# StringCchCatA

- ea: `0x140002344`
- end: `0x1400023e9`
- name: `StringCchCatA`
- size: `165`
- prototype: `HRESULT __stdcall(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140002c80`
- `0x140008f70`
- `0x140009c24`

## callees

- `0x140002344`

## pseudocode

```c
HRESULT __stdcall StringCchCatA(STRSAFE_LPSTR pszDest, size_t cchDest, STRSAFE_LPCSTR pszSrc)
{
  __int64 v3; // r10
  size_t v5; // r11
  STRSAFE_LPSTR v6; // rax
  HRESULT v7; // edx
  size_t v8; // rax
  char *v9; // rcx
  size_t i; // r9
  char *v11; // rax

  v3 = 2147483646;
  if ( cchDest - 1 > 0x7FFFFFFE )
    return -2147024809;
  v5 = cchDest;
  v6 = pszDest;
  do
  {
    if ( !*v6 )
      break;
    ++v6;
    --v5;
  }
  while ( v5 );
  v7 = v5 == 0 ? 0x80070057 : 0;
  v8 = (cchDest - v5) & -(__int64)(v5 != 0);
  if ( v5 )
  {
    v9 = &pszDest[v8];
    for ( i = cchDest - v8; i; --i )
    {
      if ( !v3 )
        break;
      if ( !*pszSrc )
        break;
      *v9++ = *pszSrc++;
      --v3;
    }
    v11 = v9 - 1;
    if ( i )
      v11 = v9;
    v7 = i == 0 ? 0x8007007A : 0;
    *v11 = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x140002344  mov     [rsp+arg_0], rbx
0x140002349  lea     rax, [rdx-1]
0x14000234d  mov     r10d, 7FFFFFFEh
0x140002353  mov     r9, rdx
0x140002356  mov     rbx, rcx
0x140002359  cmp     rax, r10
0x14000235c  ja      short loc_1400023DC
0x14000235e  mov     r11, rdx
0x140002361  mov     rax, rcx
0x140002364  cmp     byte ptr [rax], 0
0x140002367  jz      short loc_140002372
0x140002369  inc     rax
0x14000236c  sub     r11, 1
0x140002370  jnz     short loc_140002364
0x140002372  mov     rax, r11
0x140002375  mov     rcx, r9
0x140002378  neg     rax
0x14000237b  mov     rax, r11
0x14000237e  sbb     edx, edx
0x140002380  sub     rcx, r11
0x140002383  not     edx
0x140002385  and     edx, 80070057h
0x14000238b  neg     rax
0x14000238e  sbb     rax, rax
0x140002391  and     rax, rcx
0x140002394  test    r11, r11
0x140002397  jz      short loc_1400023E1
0x140002399  lea     rcx, [rax+rbx]
0x14000239d  sub     r9, rax
0x1400023a0  jz      short loc_1400023BF
0x1400023a2  test    r10, r10
0x1400023a5  jz      short loc_1400023BF
0x1400023a7  mov     al, [r8]
0x1400023aa  test    al, al
0x1400023ac  jz      short loc_1400023BF
0x1400023ae  mov     [rcx], al
0x1400023b0  inc     r8
0x1400023b3  inc     rcx
0x1400023b6  dec     r10
0x1400023b9  sub     r9, 1
0x1400023bd  jnz     short loc_1400023A2
0x1400023bf  test    r9, r9
0x1400023c2  lea     rax, [rcx-1]
0x1400023c6  cmovnz  rax, rcx
0x1400023ca  neg     r9
0x1400023cd  sbb     edx, edx
0x1400023cf  not     edx
0x1400023d1  and     edx, 8007007Ah
0x1400023d7  mov     byte ptr [rax], 0
0x1400023da  jmp     short loc_1400023E1
0x1400023dc  mov     edx, 80070057h
0x1400023e1  mov     rbx, [rsp+arg_0]
0x1400023e6  mov     eax, edx
0x1400023e8  retn
```
