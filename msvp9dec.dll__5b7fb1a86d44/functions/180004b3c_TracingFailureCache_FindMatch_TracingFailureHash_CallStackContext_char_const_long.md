# TracingFailureCache::FindMatch(TracingFailureHash &,CallStackContext &,char const *,long)

- ea: `0x180004b3c`
- end: `0x180004ce0`
- name: `?FindMatch@TracingFailureCache@@IEAAPEAVTracingFailureDetails@@AEAVTracingFailureHash@@AEAVCallStackContext@@PEBDJ@Z`
- size: `420`
- prototype: `struct TracingFailureDetails *__fastcall(TracingFailureCache *__hidden this, struct TracingFailureHash *, struct CallStackContext *, const char *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180004ed8`

## callees

- `0x180001e10`
- `0x180003280`
- `0x180004b3c`
- `0x18000502d`

## pseudocode

```c
struct TracingFailureDetails *__fastcall TracingFailureCache::FindMatch(
        TracingFailureCache *this,
        struct TracingFailureHash *a2,
        struct CallStackContext *a3,
        const char *a4,
        int a5)
{
  __int64 v5; // rbp
  __int64 v9; // rbx
  _QWORD *v10; // rax
  _QWORD *v11; // rbx
  unsigned int v12; // r12d
  unsigned int i; // esi
  __int64 v14; // rdi
  __int64 v15; // rax
  __int128 v16; // xmm1
  __int128 Buf1; // [rsp+20h] [rbp-68h] BYREF
  _OWORD Buf2[5]; // [rsp+30h] [rbp-58h] BYREF

  v5 = 0;
  if ( a4 )
  {
    v9 = *((_QWORD *)this + 11);
    if ( v9 )
    {
      v12 = *((_DWORD *)this + 10);
      for ( i = 0; i < v12; ++i )
      {
        v14 = 2328LL * i;
        if ( *(_DWORD *)(v14 + v9 + 1996) == *((_DWORD *)a3 + 499) )
        {
          v15 = *(_QWORD *)a2 - *(_QWORD *)(v14 + v9 + 2309);
          if ( *(_QWORD *)a2 == *(_QWORD *)(v14 + v9 + 2309) )
            v15 = *((_QWORD *)a2 + 1) - *(_QWORD *)(v14 + v9 + 2317);
          if ( !v15 && *(_DWORD *)(v14 + v9 + 2288) == a5 )
          {
            v16 = *(_OWORD *)(v14 + v9 + 2000);
            Buf2[0] = *((_OWORD *)a3 + 125);
            Buf1 = v16;
            if ( !memcmp_0(&Buf1, Buf2, 0x10u) && *(_DWORD *)(v14 + v9 + 2016) == *((_DWORD *)a3 + 504) )
              return (struct TracingFailureDetails *)(v14 + v9);
            Buf1 = *(_OWORD *)(v14 + v9 + 2000);
            if ( !memcmp_0(&Buf1, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
              return (struct TracingFailureDetails *)(v14 + v9);
            Buf1 = *((_OWORD *)a3 + 125);
            if ( !memcmp_0(&Buf1, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
              return (struct TracingFailureDetails *)(v14 + v9);
          }
        }
      }
    }
    else
    {
      v10 = operator new(0xFEA8u);
      v11 = v10 + 1;
      *v10 = 28;
      `vector constructor iterator'(
        v10 + 1,
        0x918u,
        0x1Cu,
        (void *(*)(void *))TracingFailureDetails::TracingFailureDetails);
      *((_QWORD *)this + 11) = v11;
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
0x180004b3c  push    rbx
0x180004b3e  push    rbp
0x180004b3f  push    rsi
0x180004b40  push    rdi
0x180004b41  push    r12
0x180004b43  push    r13
0x180004b45  push    r14
0x180004b47  push    r15
0x180004b49  sub     rsp, 48h
0x180004b4d  xor     ebp, ebp
0x180004b4f  mov     r14, r8
0x180004b52  mov     r15, rdx
0x180004b55  mov     rdi, rcx
0x180004b58  test    r9, r9
0x180004b5b  jz      loc_180004CCC
0x180004b61  mov     rbx, [rcx+58h]
0x180004b65  test    rbx, rbx
0x180004b68  jnz     short loc_180004BC8
0x180004b6a  mov     ecx, 0FEA8h; Size
0x180004b6f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004b74  lea     r8d, [rbp+1Ch]; unsigned __int64
0x180004b78  mov     edx, 918h; unsigned __int64
0x180004b7d  lea     r9, ??0TracingFailureDetails@@QEAA@XZ; void *(*)(void *)
0x180004b84  lea     rbx, [rax+8]
0x180004b88  mov     [rax], r8
0x180004b8b  mov     rcx, rbx; void *
0x180004b8e  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180004b93  mov     [rdi+58h], rbx
0x180004b97  mov     ebx, 1000h
0x180004b9c  cmp     [rdi+60h], rbp
0x180004ba0  jnz     short loc_180004BAD
0x180004ba2  mov     ecx, ebx; Size
0x180004ba4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004ba9  mov     [rdi+60h], rax
0x180004bad  cmp     [rdi+68h], rbp
0x180004bb1  jnz     loc_180004CCC
0x180004bb7  mov     rcx, rbx; Size
0x180004bba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004bbf  mov     [rdi+68h], rax
0x180004bc3  jmp     loc_180004CCC
0x180004bc8  mov     r12d, [rcx+28h]
0x180004bcc  xor     esi, esi
0x180004bce  mov     r13d, [rsp+88h+arg_20]
0x180004bd6  cmp     esi, r12d
0x180004bd9  jnb     loc_180004CCC
0x180004bdf  mov     eax, esi
0x180004be1  imul    rdi, rax, 918h
0x180004be8  mov     eax, [r14+7CCh]
0x180004bef  cmp     [rdi+rbx+7CCh], eax
0x180004bf6  jnz     loc_180004CC1
0x180004bfc  mov     rax, [r15]
0x180004bff  sub     rax, [rdi+rbx+905h]
0x180004c07  jnz     short loc_180004C15
0x180004c09  mov     rax, [r15+8]
0x180004c0d  sub     rax, [rdi+rbx+90Dh]
0x180004c15  test    rax, rax
0x180004c18  jnz     loc_180004CC1
0x180004c1e  cmp     [rdi+rbx+8F0h], r13d
0x180004c26  jnz     loc_180004CC1
0x180004c2c  movups  xmm0, xmmword ptr [r14+7D0h]
0x180004c34  lea     r8d, [rax+10h]; Size
0x180004c38  movups  xmm1, xmmword ptr [rdi+rbx+7D0h]
0x180004c40  lea     rdx, [rsp+88h+Buf2]; Buf2
0x180004c45  lea     rcx, [rsp+88h+Buf1]; Buf1
0x180004c4a  movdqu  [rsp+88h+Buf2], xmm0
0x180004c50  movdqu  [rsp+88h+Buf1], xmm1
0x180004c56  call    memcmp_0
0x180004c5b  test    eax, eax
0x180004c5d  jnz     short loc_180004C6F
0x180004c5f  mov     eax, [r14+7E0h]
0x180004c66  cmp     [rdi+rbx+7E0h], eax
0x180004c6d  jz      short loc_180004CC8
0x180004c6f  movups  xmm0, xmmword ptr [rdi+rbx+7D0h]
0x180004c77  mov     r8d, 10h; Size
0x180004c7d  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x180004c84  lea     rcx, [rsp+88h+Buf1]; Buf1
0x180004c89  movdqu  [rsp+88h+Buf1], xmm0
0x180004c8f  call    memcmp_0
0x180004c94  test    eax, eax
0x180004c96  jz      short loc_180004CC8
0x180004c98  movups  xmm0, xmmword ptr [r14+7D0h]
0x180004ca0  mov     r8d, 10h; Size
0x180004ca6  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x180004cad  lea     rcx, [rsp+88h+Buf1]; Buf1
0x180004cb2  movdqu  [rsp+88h+Buf1], xmm0
0x180004cb8  call    memcmp_0
0x180004cbd  test    eax, eax
0x180004cbf  jz      short loc_180004CC8
0x180004cc1  inc     esi
0x180004cc3  jmp     loc_180004BD6
0x180004cc8  lea     rbp, [rdi+rbx]
0x180004ccc  mov     rax, rbp
0x180004ccf  add     rsp, 48h
0x180004cd3  pop     r15
0x180004cd5  pop     r14
0x180004cd7  pop     r13
0x180004cd9  pop     r12
0x180004cdb  pop     rdi
0x180004cdc  pop     rsi
0x180004cdd  pop     rbp
0x180004cde  pop     rbx
0x180004cdf  retn
```
