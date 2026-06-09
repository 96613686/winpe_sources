# HrCoTaskMemAllocAndDupSzLen(ushort const *,ulong,ushort * *,ulong)

- ea: `0x180030544`
- end: `0x1800305d4`
- name: `?HrCoTaskMemAllocAndDupSzLen@@YAJPEBGKPEAPEAGK@Z`
- size: `144`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, unsigned __int16 **, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180030514`

## callees

- `0x180002320`
- `0x18001d2fc`
- `0x180030544`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180030581`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180030581`

## pseudocode

```c
__int64 __fastcall HrCoTaskMemAllocAndDupSzLen(
        const unsigned __int16 *a1,
        unsigned int a2,
        unsigned __int16 **a3,
        unsigned int a4)
{
  unsigned int v6; // ebx
  __int64 v7; // rsi
  unsigned __int16 *v8; // rax

  v6 = -2147024882;
  if ( a2 >= a4 )
    a2 = a4;
  v7 = 0;
  if ( a2 <= 0x7FFFFFFF )
    v7 = 2 * a2;
  if ( (int)v7 + 2 < (unsigned int)v7 )
  {
    *a3 = 0;
  }
  else
  {
    v8 = (unsigned __int16 *)CoTaskMemAlloc(v7 + 2);
    *a3 = v8;
    if ( v8 )
    {
      if ( (_DWORD)v7 && a1 )
      {
        return (unsigned int)StringCbCopyNW(v8, v7 + 2, a1, (unsigned int)v7);
      }
      else
      {
        memset_0(v8, 0, v7 + 2);
        return 0;
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180030544  push    rbx
0x180030546  push    rbp
0x180030547  push    rsi
0x180030548  push    rdi
0x180030549  push    r14
0x18003054b  push    r15
0x18003054d  sub     rsp, 28h
0x180030551  cmp     edx, r9d
0x180030554  mov     r14, r8
0x180030557  mov     r15, rcx
0x18003055a  mov     ebx, 8007000Eh
0x18003055f  cmovnb  edx, r9d
0x180030563  xor     esi, esi
0x180030565  cmp     edx, 7FFFFFFFh
0x18003056b  lea     eax, [rdx+rdx]
0x18003056e  cmovbe  esi, eax
0x180030571  lea     eax, [rsi+2]
0x180030574  cmp     eax, esi
0x180030576  jbe     short loc_1800305BE
0x180030578  lea     rdi, [rsi+2]
0x18003057c  mov     ebp, esi
0x18003057e  mov     rcx, rdi; cb
0x180030581  call    cs:__imp_CoTaskMemAlloc
0x180030587  mov     [r14], rax
0x18003058a  test    rax, rax
0x18003058d  jz      short loc_1800305C5
0x18003058f  test    esi, esi
0x180030591  jz      short loc_1800305AD
0x180030593  test    r15, r15
0x180030596  jz      short loc_1800305AD
0x180030598  mov     r9d, ebp; unsigned __int64
0x18003059b  mov     r8, r15; unsigned __int16 *
0x18003059e  mov     rdx, rdi; unsigned __int64
0x1800305a1  mov     rcx, rax; unsigned __int16 *
0x1800305a4  call    ?StringCbCopyNW@@YAJPEAG_KPEBG1@Z; StringCbCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800305a9  mov     ebx, eax
0x1800305ab  jmp     short loc_1800305C5
0x1800305ad  mov     r8, rdi; Size
0x1800305b0  xor     edx, edx; Val
0x1800305b2  mov     rcx, rax; void *
0x1800305b5  call    memset_0
0x1800305ba  xor     ebx, ebx
0x1800305bc  jmp     short loc_1800305C5
0x1800305be  mov     qword ptr [r8], 0
0x1800305c5  mov     eax, ebx
0x1800305c7  add     rsp, 28h
0x1800305cb  pop     r15
0x1800305cd  pop     r14
0x1800305cf  pop     rdi
0x1800305d0  pop     rsi
0x1800305d1  pop     rbp
0x1800305d2  pop     rbx
0x1800305d3  retn
```
