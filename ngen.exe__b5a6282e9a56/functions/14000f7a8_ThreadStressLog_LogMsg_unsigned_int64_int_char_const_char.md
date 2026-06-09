# ThreadStressLog::LogMsg(unsigned __int64,int,char const *,char *)

- ea: `0x14000f7a8`
- end: `0x14000f87c`
- name: `?LogMsg@ThreadStressLog@@QEAAX_KHPEBDPEAD@Z`
- size: `212`
- prototype: `void __fastcall(ThreadStressLog *this, LARGE_INTEGER, int, const char *, char *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f8e0`

## callees

- `0x14000f0ac`
- `0x14000f7a8`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x14000f80d`
- `KERNEL32!QueryPerformanceCounter` at `0x14000f80d`

## pseudocode

```c
void __fastcall ThreadStressLog::LogMsg(ThreadStressLog *this, LARGE_INTEGER a2, int a3, const char *a4, char *a5)
{
  __int64 v6; // rsi
  unsigned __int64 v8; // rdi
  LARGE_INTEGER *v9; // rbx
  char *v10; // rcx
  LARGE_INTEGER *v11; // rbx
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+8h] BYREF

  v6 = a3;
  v8 = (unsigned __int64)&a4[-qword_140027158] & -(__int64)((unsigned __int64)&a4[-qword_140027158] < 0x20000000);
  v9 = (LARGE_INTEGER *)(*((_QWORD *)this + 2) - (8LL * a3 + 24));
  if ( (unsigned __int64)v9 < *((_QWORD *)this + 8) + 16LL )
    v9 = (LARGE_INTEGER *)ThreadStressLog::AdvWritePastBoundary(this, a3);
  *((_QWORD *)this + 2) = v9;
  PerformanceCount.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  v9[2] = PerformanceCount;
  v9->QuadPart &= 0xFFFFFFFF00000000uLL;
  v9[1] = a2;
  v9->QuadPart |= v6 & 7 | (8 * (v8 & 0x1FFFFFFF));
  if ( v6 > 0 )
  {
    v10 = a5 - 8;
    v11 = v9 + 3;
    do
    {
      v10 += 8;
      *v11++ = *(LARGE_INTEGER *)v10;
      --v6;
    }
    while ( v6 );
  }
}

```

## disassembly

```asm
0x14000f7a8  mov     [rsp+arg_8], rbx
0x14000f7ad  mov     [rsp+arg_10], rbp
0x14000f7b2  push    rsi
0x14000f7b3  push    rdi
0x14000f7b4  push    r14
0x14000f7b6  sub     rsp, 20h
0x14000f7ba  sub     r9, cs:qword_140027158
0x14000f7c1  mov     r14, rdx
0x14000f7c4  mov     rbx, [rcx+10h]
0x14000f7c8  cmp     r9, 20000000h
0x14000f7cf  movsxd  rsi, r8d
0x14000f7d2  mov     rbp, rcx
0x14000f7d5  sbb     rdi, rdi
0x14000f7d8  and     rdi, r9
0x14000f7db  lea     rax, ds:18h[rsi*8]
0x14000f7e3  sub     rbx, rax
0x14000f7e6  mov     rax, [rcx+40h]
0x14000f7ea  add     rax, 10h
0x14000f7ee  cmp     rbx, rax
0x14000f7f1  jnb     short loc_14000F7FE
0x14000f7f3  mov     edx, r8d; int
0x14000f7f6  call    ?AdvWritePastBoundary@ThreadStressLog@@AEAAPEAUStressMsg@@H@Z; ThreadStressLog::AdvWritePastBoundary(int)
0x14000f7fb  mov     rbx, rax
0x14000f7fe  mov     [rbp+10h], rbx
0x14000f802  lea     rcx, [rsp+38h+PerformanceCount]; lpPerformanceCount
0x14000f807  and     qword ptr [rsp+38h+PerformanceCount], 0
0x14000f80d  call    cs:__imp_QueryPerformanceCounter
0x14000f813  mov     rax, qword ptr [rsp+38h+PerformanceCount]
0x14000f818  and     edi, 1FFFFFFFh
0x14000f81e  mov     [rbx+10h], rax
0x14000f822  mov     rax, 0FFFFFFFF00000000h
0x14000f82c  and     [rbx], rax
0x14000f82f  mov     rax, rsi
0x14000f832  and     eax, 7
0x14000f835  shl     rdi, 3
0x14000f839  or      rdi, rax
0x14000f83c  mov     [rbx+8], r14
0x14000f840  or      [rbx], rdi
0x14000f843  test    rsi, rsi
0x14000f846  jle     short loc_14000F869
0x14000f848  mov     rcx, [rsp+38h+arg_20]
0x14000f84d  add     rcx, 0FFFFFFFFFFFFFFF8h
0x14000f851  add     rbx, 18h
0x14000f855  lea     rcx, [rcx+8]
0x14000f859  mov     rax, [rcx]
0x14000f85c  mov     [rbx], rax
0x14000f85f  lea     rbx, [rbx+8]
0x14000f863  sub     rsi, 1
0x14000f867  jnz     short loc_14000F855
0x14000f869  mov     rbx, [rsp+38h+arg_8]
0x14000f86e  mov     rbp, [rsp+38h+arg_10]
0x14000f873  add     rsp, 20h
0x14000f877  pop     r14
0x14000f879  pop     rdi
0x14000f87a  pop     rsi
0x14000f87b  retn
```
