# TracingFailureCache::FindMatch(TracingFailureHash &,CallStackContext &,char const *,long)

- ea: `0x18000872c`
- end: `0x1800088e4`
- name: `?FindMatch@TracingFailureCache@@IEAAPEAVTracingFailureDetails@@AEAVTracingFailureHash@@AEAVCallStackContext@@PEBDJ@Z`
- size: `440`
- prototype: `struct TracingFailureDetails *__fastcall(TracingFailureCache *__hidden this, struct TracingFailureHash *, struct CallStackContext *, const char *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180008ce8`

## callees

- `0x180001120`
- `0x18000854c`
- `0x18000872c`
- `0x18001d35d`

## pseudocode

```c
struct TracingFailureDetails *__fastcall TracingFailureCache::FindMatch(
        TracingFailureCache *this,
        struct TracingFailureHash *a2,
        struct CallStackContext *a3,
        const char *a4,
        int a5)
{
  __int64 v5; // r14
  __int64 v9; // r15
  _QWORD *v10; // rax
  __int64 v11; // rdi
  _QWORD *v12; // rsi
  TracingFailureDetails *v13; // rbp
  unsigned int v14; // ebp
  int v15; // edx
  unsigned int i; // edi
  __int64 v17; // rbx
  __int128 v18; // xmm1
  __int128 Buf1; // [rsp+20h] [rbp-68h] BYREF
  _OWORD Buf2[5]; // [rsp+30h] [rbp-58h] BYREF

  v5 = 0;
  if ( a4 )
  {
    v9 = *((_QWORD *)this + 11);
    if ( v9 )
    {
      v14 = *((_DWORD *)this + 10);
      if ( v14 )
      {
        v15 = *((_DWORD *)a3 + 499);
        for ( i = 0; i < v14; ++i )
        {
          v17 = v9 + 2328LL * i;
          if ( *(_DWORD *)(v17 + 1996) == v15
            && *(_QWORD *)a2 == *(_QWORD *)(v17 + 2309)
            && *((_QWORD *)a2 + 1) == *(_QWORD *)(v17 + 2317)
            && *(_DWORD *)(v17 + 2288) == a5 )
          {
            v18 = *(_OWORD *)(v17 + 2000);
            Buf2[0] = *((_OWORD *)a3 + 125);
            Buf1 = v18;
            if ( !memcmp_0(&Buf1, Buf2, 0x10u) && *(_DWORD *)(v17 + 2016) == *((_DWORD *)a3 + 504) )
              return (struct TracingFailureDetails *)(v9 + 2328LL * i);
            Buf1 = *(_OWORD *)(v17 + 2000);
            if ( !memcmp_0(&Buf1, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
              return (struct TracingFailureDetails *)(v9 + 2328LL * i);
            Buf1 = *((_OWORD *)a3 + 125);
            if ( !memcmp_0(&Buf1, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
              return (struct TracingFailureDetails *)(v9 + 2328LL * i);
            v15 = *((_DWORD *)a3 + 499);
          }
        }
      }
    }
    else
    {
      v10 = operator new(0xFEA8u);
      if ( v10 )
      {
        v11 = 28;
        v12 = v10 + 1;
        *v10 = 28;
        v13 = (TracingFailureDetails *)(v10 + 1);
        do
        {
          TracingFailureDetails::TracingFailureDetails(v13);
          v13 = (TracingFailureDetails *)((char *)v13 + 2328);
          --v11;
        }
        while ( v11 );
      }
      else
      {
        v12 = 0;
      }
      *((_QWORD *)this + 11) = v12;
      if ( !*((_QWORD *)this + 12) )
        *((_QWORD *)this + 12) = operator new(0x1000u);
      if ( !*((_QWORD *)this + 13) )
        *((_QWORD *)this + 13) = operator new(0x1000u);
    }
  }
  return (struct TracingFailureDetails *)v5;
}

```

## disassembly

```asm
0x18000872c  push    rbx
0x18000872e  push    rbp
0x18000872f  push    rsi
0x180008730  push    rdi
0x180008731  push    r12
0x180008733  push    r13
0x180008735  push    r14
0x180008737  push    r15
0x180008739  sub     rsp, 48h
0x18000873d  xor     r14d, r14d
0x180008740  mov     rsi, r8
0x180008743  mov     r12, rdx
0x180008746  mov     rbx, rcx
0x180008749  test    r9, r9
0x18000874c  jz      loc_1800088D0
0x180008752  mov     r15, [rcx+58h]
0x180008756  test    r15, r15
0x180008759  jnz     short loc_1800087C6
0x18000875b  mov     ecx, 0FEA8h; Size
0x180008760  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008765  test    rax, rax
0x180008768  jz      short loc_18000878F
0x18000876a  lea     edi, [r14+1Ch]
0x18000876e  lea     rsi, [rax+8]
0x180008772  mov     [rax], rdi
0x180008775  mov     rbp, rsi
0x180008778  mov     rcx, rbp; this
0x18000877b  call    ??0TracingFailureDetails@@QEAA@XZ; TracingFailureDetails::TracingFailureDetails(void)
0x180008780  add     rbp, 918h
0x180008787  sub     rdi, 1
0x18000878b  jnz     short loc_180008778
0x18000878d  jmp     short loc_180008791
0x18000878f  xor     esi, esi
0x180008791  mov     edi, 1000h
0x180008796  mov     [rbx+58h], rsi
0x18000879a  cmp     [rbx+60h], r14
0x18000879e  jnz     short loc_1800087AB
0x1800087a0  mov     ecx, edi; Size
0x1800087a2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800087a7  mov     [rbx+60h], rax
0x1800087ab  cmp     [rbx+68h], r14
0x1800087af  jnz     loc_1800088D0
0x1800087b5  mov     rcx, rdi; Size
0x1800087b8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800087bd  mov     [rbx+68h], rax
0x1800087c1  jmp     loc_1800088D0
0x1800087c6  mov     ebp, [rcx+28h]
0x1800087c9  test    ebp, ebp
0x1800087cb  jz      loc_1800088D0
0x1800087d1  mov     edx, [r8+7CCh]
0x1800087d8  xor     edi, edi
0x1800087da  mov     r13d, [rsp+88h+arg_20]
0x1800087e2  mov     eax, edi
0x1800087e4  imul    rbx, rax, 918h
0x1800087eb  add     rbx, r15
0x1800087ee  cmp     [rbx+7CCh], edx
0x1800087f4  jnz     loc_1800088C1
0x1800087fa  mov     rax, [r12]
0x1800087fe  cmp     rax, [rbx+905h]
0x180008805  jnz     loc_1800088C1
0x18000880b  mov     rax, [r12+8]
0x180008810  cmp     rax, [rbx+90Dh]
0x180008817  jnz     loc_1800088C1
0x18000881d  cmp     [rbx+8F0h], r13d
0x180008824  jnz     loc_1800088C1
0x18000882a  movups  xmm0, xmmword ptr [rsi+7D0h]
0x180008831  mov     r8d, 10h; Size
0x180008837  lea     rdx, [rsp+88h+Buf2]; Buf2
0x18000883c  movups  xmm1, xmmword ptr [rbx+7D0h]
0x180008843  lea     rcx, [rsp+88h+Buf1]; Buf1
0x180008848  movdqu  [rsp+88h+Buf2], xmm0
0x18000884e  movdqu  [rsp+88h+Buf1], xmm1
0x180008854  call    memcmp_0
0x180008859  test    eax, eax
0x18000885b  jnz     short loc_18000886B
0x18000885d  mov     eax, [rsi+7E0h]
0x180008863  cmp     [rbx+7E0h], eax
0x180008869  jz      short loc_1800088CD
0x18000886b  movups  xmm0, xmmword ptr [rbx+7D0h]
0x180008872  mov     r8d, 10h; Size
0x180008878  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x18000887f  lea     rcx, [rsp+88h+Buf1]; Buf1
0x180008884  movdqu  [rsp+88h+Buf1], xmm0
0x18000888a  call    memcmp_0
0x18000888f  test    eax, eax
0x180008891  jz      short loc_1800088CD
0x180008893  movups  xmm0, xmmword ptr [rsi+7D0h]
0x18000889a  mov     r8d, 10h; Size
0x1800088a0  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x1800088a7  lea     rcx, [rsp+88h+Buf1]; Buf1
0x1800088ac  movdqu  [rsp+88h+Buf1], xmm0
0x1800088b2  call    memcmp_0
0x1800088b7  test    eax, eax
0x1800088b9  jz      short loc_1800088CD
0x1800088bb  mov     edx, [rsi+7CCh]
0x1800088c1  inc     edi
0x1800088c3  cmp     edi, ebp
0x1800088c5  jb      loc_1800087E2
0x1800088cb  jmp     short loc_1800088D0
0x1800088cd  mov     r14, rbx
0x1800088d0  mov     rax, r14
0x1800088d3  add     rsp, 48h
0x1800088d7  pop     r15
0x1800088d9  pop     r14
0x1800088db  pop     r13
0x1800088dd  pop     r12
0x1800088df  pop     rdi
0x1800088e0  pop     rsi
0x1800088e1  pop     rbp
0x1800088e2  pop     rbx
0x1800088e3  retn
```
