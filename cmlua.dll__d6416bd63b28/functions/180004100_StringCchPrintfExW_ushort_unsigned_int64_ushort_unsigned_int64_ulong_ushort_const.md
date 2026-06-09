# StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)

- ea: `0x180004100`
- end: `0x1800042bd`
- name: `?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ`
- size: `445`
- prototype: `__int64(wchar_t *Buffer, unsigned __int64, unsigned __int16 **, unsigned __int64 *, unsigned int, const unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002af0`

## callees

- `0x180004100`
- `0x1800042c4`
- `0x180005486`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180004244`
- `msvcrt!_vsnwprintf` at `0x180004244`

## pseudocode

```c
__int64 StringCchPrintfExW(
        wchar_t *Buffer,
        size_t a2,
        unsigned __int16 **a3,
        unsigned __int64 *a4,
        DWORD dwFlags,
        const unsigned __int16 *a6,
        ...)
{
  bool v8; // cc
  int v9; // ebx
  const unsigned __int16 *v10; // r8
  STRSAFE_LPWSTR v11; // r13
  size_t v12; // r15
  unsigned __int64 v14; // rsi
  int v15; // eax
  STRSAFE_LPWSTR ppszDestEnd; // [rsp+30h] [rbp-18h] BYREF
  size_t pcchRemaining[2]; // [rsp+38h] [rbp-10h] BYREF
  unsigned __int64 *v19; // [rsp+A8h] [rbp+60h]
  va_list Args; // [rsp+C0h] [rbp+78h] BYREF

  va_start(Args, a6);
  v19 = a4;
  if ( (dwFlags & 0x100) != 0 )
  {
    if ( !Buffer && a2 )
    {
LABEL_7:
      v9 = -2147024809;
      if ( a2 )
        *Buffer = 0;
      return (unsigned int)v9;
    }
    v8 = a2 <= 0x7FFFFFFF;
  }
  else
  {
    v8 = a2 - 1 <= 0x7FFFFFFE;
  }
  if ( !v8 )
    goto LABEL_7;
  v10 = a6;
  v11 = Buffer;
  ppszDestEnd = Buffer;
  v12 = a2;
  pcchRemaining[0] = a2;
  if ( (dwFlags & 0x100) != 0 && !a6 )
    v10 = (const unsigned __int16 *)&Format;
  if ( (dwFlags & 0xFFFFE000) != 0 )
  {
    v9 = -2147024809;
    if ( a2 )
      *Buffer = 0;
    goto LABEL_15;
  }
  if ( !a2 )
  {
    v9 = 0;
    if ( !*v10 )
      goto LABEL_20;
    v9 = Buffer != 0 ? -2147024774 : -2147024809;
    goto LABEL_15;
  }
  pcchRemaining[0] = 0;
  v14 = a2 - 1;
  v15 = _vsnwprintf(Buffer, a2 - 1, v10, Args);
  if ( v15 < 0 || v15 > v14 )
  {
    v9 = -2147024774;
  }
  else
  {
    v9 = 0;
    if ( v15 != v14 )
    {
      v14 = v15;
      goto LABEL_34;
    }
  }
  Buffer[v14] = 0;
LABEL_34:
  v12 = a2 - v14;
  v11 = &Buffer[v14];
  ppszDestEnd = v11;
  pcchRemaining[0] = a2 - v14;
  if ( v9 >= 0 )
  {
    if ( (dwFlags & 0x200) != 0 && v12 > 1 && 2 * v12 > 2 )
      memset_0(v11 + 1, (unsigned __int8)dwFlags, 2 * v12 - 2);
    goto LABEL_19;
  }
LABEL_15:
  if ( (dwFlags & 0x1C00) != 0 && a2 )
  {
    StringExHandleOtherFlagsW(Buffer, 2 * a2, (size_t)v10, &ppszDestEnd, pcchRemaining, dwFlags);
    v11 = ppszDestEnd;
    v12 = pcchRemaining[0];
  }
  if ( v9 == -2147024774 )
  {
LABEL_19:
    a4 = v19;
LABEL_20:
    if ( a3 )
      *a3 = v11;
    if ( a4 )
      *a4 = v12;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180004100  mov     [rsp-40h+arg_18], r9
0x180004105  mov     [rsp-40h+arg_10], r8
0x18000410a  push    rbp
0x18000410b  push    rbx
0x18000410c  push    rsi
0x18000410d  push    rdi
0x18000410e  push    r12
0x180004110  push    r13
0x180004112  push    r14
0x180004114  push    r15
0x180004116  mov     rbp, rsp
0x180004119  sub     rsp, 48h
0x18000411d  mov     r12d, [rbp+arg_20]
0x180004121  mov     r14, rcx
0x180004124  mov     ecx, r12d
0x180004127  xor     esi, esi
0x180004129  mov     rdi, rdx
0x18000412c  and     ecx, 100h
0x180004132  jz      short loc_180004147
0x180004134  test    r14, r14
0x180004137  jnz     short loc_18000413E
0x180004139  test    rdx, rdx
0x18000413c  jnz     short loc_180004153
0x18000413e  cmp     rdi, 7FFFFFFFh
0x180004145  jmp     short loc_180004151
0x180004147  lea     rax, [rdx-1]
0x18000414b  cmp     rax, 7FFFFFFEh
0x180004151  jbe     short loc_18000416A
0x180004153  mov     ebx, 80070057h
0x180004158  test    rdi, rdi
0x18000415b  jz      loc_1800041FB
0x180004161  mov     [r14], si
0x180004165  jmp     loc_1800041FB
0x18000416a  mov     r8, [rbp+arg_28]
0x18000416e  mov     r13, r14
0x180004171  mov     [rbp+ppszDestEnd], r14
0x180004175  mov     r15, rdi
0x180004178  mov     [rbp+var_10], rdi
0x18000417c  test    ecx, ecx
0x18000417e  jz      short loc_180004190
0x180004180  test    r8, r8
0x180004183  jnz     short loc_180004190
0x180004185  lea     r8, Format; Format
0x18000418c  mov     [rbp+arg_28], r8
0x180004190  test    r12d, 0FFFFE000h
0x180004197  jz      short loc_18000420E
0x180004199  mov     ebx, 80070057h
0x18000419e  test    rdi, rdi
0x1800041a1  jz      short loc_1800041A7
0x1800041a3  mov     [r14], si
0x1800041a7  test    r12d, 1C00h
0x1800041ae  jz      short loc_1800041DB
0x1800041b0  test    rdi, rdi
0x1800041b3  jz      short loc_1800041DB
0x1800041b5  lea     rax, [rbp+var_10]
0x1800041b9  mov     [rsp+48h+dwFlags], r12d; dwFlags
0x1800041be  lea     rdx, [rdi+rdi]; cbDest
0x1800041c2  mov     [rsp+48h+pcchRemaining], rax; pcchRemaining
0x1800041c7  lea     r9, [rbp+ppszDestEnd]; ppszDestEnd
0x1800041cb  mov     rcx, r14; pszDest
0x1800041ce  call    StringExHandleOtherFlagsW
0x1800041d3  mov     r13, [rbp+ppszDestEnd]
0x1800041d7  mov     r15, [rbp+var_10]
0x1800041db  cmp     ebx, 8007007Ah
0x1800041e1  jnz     short loc_1800041FB
0x1800041e3  mov     r9, [rbp+arg_18]
0x1800041e7  mov     rax, [rbp+arg_10]
0x1800041eb  test    rax, rax
0x1800041ee  jz      short loc_1800041F3
0x1800041f0  mov     [rax], r13
0x1800041f3  test    r9, r9
0x1800041f6  jz      short loc_1800041FB
0x1800041f8  mov     [r9], r15
0x1800041fb  mov     eax, ebx
0x1800041fd  add     rsp, 48h
0x180004201  pop     r15
0x180004203  pop     r14
0x180004205  pop     r13
0x180004207  pop     r12
0x180004209  pop     rdi
0x18000420a  pop     rsi
0x18000420b  pop     rbx
0x18000420c  pop     rbp
0x18000420d  retn
0x18000420e  test    rdi, rdi
0x180004211  jnz     short loc_180004232
0x180004213  mov     ebx, esi
0x180004215  cmp     [r8], si
0x180004219  jz      short loc_1800041E7
0x18000421b  mov     rax, r14
0x18000421e  mov     ebx, 80070057h
0x180004223  neg     rax
0x180004226  sbb     ecx, ecx
0x180004228  and     ecx, 23h
0x18000422b  add     ebx, ecx
0x18000422d  jmp     loc_1800041A7
0x180004232  mov     [rbp+var_10], rsi
0x180004236  lea     r9, [rbp+Args]; Args
0x18000423a  lea     rsi, [rdx-1]
0x18000423e  mov     rcx, r14; Buffer
0x180004241  mov     rdx, rsi; BufferCount
0x180004244  call    cs:__imp__vsnwprintf
0x18000424a  test    eax, eax
0x18000424c  js      short loc_180004261
0x18000424e  cdqe
0x180004250  cmp     rax, rsi
0x180004253  ja      short loc_180004261
0x180004255  xor     ebx, ebx
0x180004257  cmp     rax, rsi
0x18000425a  jz      short loc_180004266
0x18000425c  mov     rsi, rax
0x18000425f  jmp     short loc_18000426D
0x180004261  mov     ebx, 8007007Ah
0x180004266  xor     eax, eax
0x180004268  mov     [r14+rsi*2], ax
0x18000426d  sub     r15, rsi
0x180004270  lea     r13, [r14+rsi*2]
0x180004274  mov     [rbp+ppszDestEnd], r13
0x180004278  mov     [rbp+var_10], r15
0x18000427c  test    ebx, ebx
0x18000427e  js      loc_1800041A7
0x180004284  bt      r12d, 9
0x180004289  jnb     loc_1800041E3
0x18000428f  cmp     r15, 1
0x180004293  jbe     loc_1800041E3
0x180004299  lea     r8, [r15+r15]
0x18000429d  cmp     r8, 2
0x1800042a1  jbe     loc_1800041E3
0x1800042a7  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x1800042ab  movzx   edx, r12b; Val
0x1800042af  lea     rcx, [r13+2]; void *
0x1800042b3  call    memset_0
0x1800042b8  jmp     loc_1800041E3
```
