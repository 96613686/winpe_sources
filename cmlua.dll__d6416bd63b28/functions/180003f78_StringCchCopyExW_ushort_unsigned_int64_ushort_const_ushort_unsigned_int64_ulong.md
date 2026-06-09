# StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)

- ea: `0x180003f78`
- end: `0x1800040f7`
- name: `?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z`
- size: `383`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest, unsigned __int64, const size_t *, unsigned __int16 **, unsigned __int64 *ppszDestEnd, DWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180001ec0`
- `0x1800026b0`
- `0x1800029d4`
- `0x180002af0`
- `0x180004630`

## callees

- `0x180003f78`
- `0x1800042c4`
- `0x180005486`

## pseudocode

```c
__int64 __fastcall StringCchCopyExW(
        STRSAFE_LPWSTR pszDest,
        unsigned __int64 a2,
        const size_t *a3,
        unsigned __int16 **a4,
        unsigned __int64 *ppszDestEnd,
        DWORD a6)
{
  DWORD dwFlags; // r9d
  __int64 v8; // rcx
  unsigned int v9; // ebx
  unsigned __int64 v10; // r11
  STRSAFE_LPWSTR v11; // rax
  __int64 v12; // rbx
  __int64 v13; // rdi
  STRSAFE_LPWSTR v14; // rcx
  __int64 v15; // rdx
  bool v16; // cf
  size_t pcchRemaining; // [rsp+58h] [rbp+20h] BYREF

  dwFlags = a6;
  v8 = 2147483646;
  if ( (a6 & 0x100) != 0 )
  {
    if ( (pszDest || !a2) && a2 <= 0x7FFFFFFF )
    {
      if ( !a3 )
        a3 = &Format;
      goto LABEL_8;
    }
LABEL_28:
    v9 = -2147024809;
    if ( a2 )
      *pszDest = 0;
    return v9;
  }
  if ( a2 - 1 > 0x7FFFFFFE )
    goto LABEL_28;
LABEL_8:
  if ( (a6 & 0xFFFFE000) != 0 )
  {
    v9 = -2147024809;
    if ( a2 )
      *pszDest = 0;
    goto LABEL_11;
  }
  if ( !a2 )
  {
    v9 = 0;
    if ( !*(_WORD *)a3 )
      return v9;
    v9 = pszDest != 0 ? -2147024774 : -2147024809;
    goto LABEL_11;
  }
  v10 = a2;
  v11 = pszDest;
  v12 = 0;
  do
  {
    if ( !v8 )
      break;
    if ( !*(_WORD *)a3 )
      break;
    *v11 = *(_WORD *)a3;
    a3 = (const size_t *)((char *)a3 + 2);
    ++v11;
    --v8;
    ++v12;
    --v10;
  }
  while ( v10 );
  v13 = v12 - 1;
  v14 = v11 - 1;
  if ( v10 )
  {
    v14 = v11;
    v13 = v12;
  }
  *v14 = 0;
  v9 = v10 == 0 ? 0x8007007A : 0;
  if ( !v10 )
  {
LABEL_11:
    if ( (dwFlags & 0x1C00) != 0 && a2 )
      StringExHandleOtherFlagsW(pszDest, 2 * a2, (size_t)a3, (STRSAFE_LPWSTR *)&ppszDestEnd, &pcchRemaining, dwFlags);
    return v9;
  }
  if ( (dwFlags & 0x200) != 0 )
  {
    v16 = a2 == v13;
    v15 = a2 - v13;
    if ( !v16 && v15 != 1 && (unsigned __int64)(2 * v15) > 2 )
      memset_0(&pszDest[v13 + 1], (unsigned __int8)dwFlags, 2 * v15 - 2);
  }
  return v9;
}

```

## disassembly

```asm
0x180003f78  mov     [rsp+arg_0], rbx
0x180003f7d  mov     [rsp+arg_8], rsi
0x180003f82  push    rdi
0x180003f83  sub     rsp, 30h
0x180003f87  mov     r9d, [rsp+38h+arg_28]
0x180003f8c  xor     esi, esi
0x180003f8e  mov     r10, rcx
0x180003f91  mov     ecx, 7FFFFFFEh
0x180003f96  bt      r9d, 8
0x180003f9b  jnb     short loc_180003FC6
0x180003f9d  test    r10, r10
0x180003fa0  jnz     short loc_180003FAB
0x180003fa2  test    rdx, rdx
0x180003fa5  jnz     loc_1800040D7
0x180003fab  cmp     rdx, 7FFFFFFFh
0x180003fb2  ja      loc_1800040D7
0x180003fb8  test    r8, r8
0x180003fbb  jnz     short loc_180003FD3
0x180003fbd  lea     r8, Format; cchOriginalDestLength
0x180003fc4  jmp     short loc_180003FD3
0x180003fc6  lea     rax, [rdx-1]
0x180003fca  cmp     rax, rcx
0x180003fcd  ja      loc_1800040D7
0x180003fd3  test    r9d, 0FFFFE000h
0x180003fda  jz      short loc_180004024
0x180003fdc  mov     ebx, 80070057h
0x180003fe1  test    rdx, rdx
0x180003fe4  jz      short loc_180003FEA
0x180003fe6  mov     [r10], si
0x180003fea  test    r9d, 1C00h
0x180003ff1  jz      loc_1800040E5
0x180003ff7  test    rdx, rdx
0x180003ffa  jz      loc_1800040E5
0x180004000  mov     [rsp+38h+dwFlags], r9d; dwFlags
0x180004005  lea     rax, [rsp+38h+arg_18]
0x18000400a  lea     r9, [rsp+38h+ppszDestEnd]; ppszDestEnd
0x18000400f  mov     [rsp+38h+pcchRemaining], rax; pcchRemaining
0x180004014  add     rdx, rdx; cbDest
0x180004017  mov     rcx, r10; pszDest
0x18000401a  call    StringExHandleOtherFlagsW
0x18000401f  jmp     loc_1800040E5
0x180004024  test    rdx, rdx
0x180004027  jnz     short loc_180004049
0x180004029  mov     ebx, esi
0x18000402b  cmp     [r8], si
0x18000402f  jz      loc_1800040E5
0x180004035  mov     rax, r10
0x180004038  mov     ebx, 80070057h
0x18000403d  neg     rax
0x180004040  sbb     ecx, ecx
0x180004042  and     ecx, 23h
0x180004045  add     ebx, ecx
0x180004047  jmp     short loc_180003FEA
0x180004049  mov     r11, rdx
0x18000404c  mov     rax, r10
0x18000404f  mov     rbx, rsi
0x180004052  test    rcx, rcx
0x180004055  jz      short loc_180004077
0x180004057  movzx   edi, word ptr [r8]
0x18000405b  test    di, di
0x18000405e  jz      short loc_180004077
0x180004060  mov     [rax], di
0x180004063  add     r8, 2
0x180004067  add     rax, 2
0x18000406b  dec     rcx
0x18000406e  inc     rbx
0x180004071  sub     r11, 1
0x180004075  jnz     short loc_180004052
0x180004077  test    r11, r11
0x18000407a  lea     rdi, [rbx-1]
0x18000407e  lea     rcx, [rax-2]
0x180004082  cmovnz  rcx, rax
0x180004086  cmovnz  rdi, rbx
0x18000408a  mov     rax, r11
0x18000408d  neg     rax
0x180004090  sbb     ebx, ebx
0x180004092  mov     [rcx], si
0x180004095  not     ebx
0x180004097  and     ebx, 8007007Ah
0x18000409d  test    r11, r11
0x1800040a0  jz      loc_180003FEA
0x1800040a6  bt      r9d, 9
0x1800040ab  jnb     short loc_1800040E5
0x1800040ad  sub     rdx, rdi
0x1800040b0  cmp     rdx, 1
0x1800040b4  jbe     short loc_1800040E5
0x1800040b6  lea     r8, [rdx+rdx]
0x1800040ba  cmp     r8, 2
0x1800040be  jbe     short loc_1800040E5
0x1800040c0  lea     rcx, [r10+2]
0x1800040c4  movzx   edx, r9b; Val
0x1800040c8  lea     rcx, [rcx+rdi*2]; void *
0x1800040cc  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x1800040d0  call    memset_0
0x1800040d5  jmp     short loc_1800040E5
0x1800040d7  mov     ebx, 80070057h
0x1800040dc  test    rdx, rdx
0x1800040df  jz      short loc_1800040E5
0x1800040e1  mov     [r10], si
0x1800040e5  mov     rsi, [rsp+38h+arg_8]
0x1800040ea  mov     eax, ebx
0x1800040ec  mov     rbx, [rsp+38h+arg_0]
0x1800040f1  add     rsp, 30h
0x1800040f5  pop     rdi
0x1800040f6  retn
```
