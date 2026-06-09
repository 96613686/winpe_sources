# PerfLibraryData::SavePerformanceData(void * *,ulong *,ulong *)

- ea: `0x18000fd0c`
- end: `0x18000fefc`
- name: `?SavePerformanceData@PerfLibraryData@@QEAAXPEAPEAXPEAK1@Z`
- size: `496`
- prototype: `void __fastcall(const wchar_t **this, void **, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010db0`

## callees

- `0x18000fd0c`
- `0x18001067c`
- `0x1800156c8`

## string_xrefs

- `0x18000fd68`: `"onecoreuap\\base\\appmodel\\search\\common\\pkmcntrs\\pkmcntrs.cxx"`
- `0x18000fdef`: `"onecoreuap\\base\\appmodel\\search\\common\\pkmcntrs\\pkmcntrs.cxx"`
- `0x18000fe66`: `"onecoreuap\\base\\appmodel\\search\\common\\pkmcntrs\\pkmcntrs.cxx"`
- `0x18000fd5c`: `[UtilCommon] MSSCNTRS: Saving performance data for %ls.`
- `0x18000fde3`: `[UtilCommon] MSSCNTRS:  Writing out data for %ls with no instances.`
- `0x18000fe55`: `[UtilCommon] MSSCNTRS:  Writing out data for %ls instance %ls.`

## pseudocode

```c
void __fastcall PerfLibraryData::SavePerformanceData(
        const wchar_t **this,
        void **a2,
        unsigned int *a3,
        unsigned int *a4)
{
  __int64 v4; // rbp
  void **i; // rbx
  const wchar_t *v8; // rax
  _OWORD *v9; // r14
  __int64 v10; // rbx
  __int64 v11; // rcx
  _DWORD *v12; // rbx
  int v13; // r15d
  __int64 v14; // rcx
  const wchar_t *v15; // r14
  unsigned int v16; // r12d
  const wchar_t *v17; // rcx
  __int64 v18; // rax
  _OWORD *v19; // [rsp+70h] [rbp+8h]

  v4 = 0;
  for ( i = a2; (unsigned int)v4 < *((_DWORD *)this + 4); v4 = (unsigned int)(v4 + 1) )
  {
    if ( LODWORD(this[10 * v4 + 6]) )
    {
      SearchIndexerTrace::Verbose(
        (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\pkmcntrs\\\\pkmcntrs.cxx\"",
        (const wchar_t *)0x11B,
        (unsigned int)L"[UtilCommon] MSSCNTRS: Saving performance data for %ls.",
        this[10 * v4 + 7]);
      v8 = this[10 * v4 + 8];
      v9 = *i;
      v19 = v9;
      v10 = (__int64)*i + 64;
      *v9 = *(_OWORD *)v8;
      v9[1] = *((_OWORD *)v8 + 1);
      v9[2] = *((_OWORD *)v8 + 2);
      v9[3] = *((_OWORD *)v8 + 3);
      memcpy_0(v9 + 4, this[10 * v4 + 9], 40LL * *((unsigned int *)v9 + 8));
      v11 = *((unsigned int *)v9 + 8);
      v12 = (_DWORD *)(v10 + 40 * v11);
      v13 = 40 * v11 + 64;
      if ( *((_DWORD *)v9 + 10) == -1 )
      {
        SearchIndexerTrace::Verbose(
          (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\pkmcntrs\\\\pkmcntrs.cxx\"",
          (const wchar_t *)0x133,
          (unsigned int)L"[UtilCommon] MSSCNTRS:  Writing out data for %ls with no instances.",
          this[10 * v4 + 7]);
        memcpy_0(v12, this[10 * v4 + 12], *(unsigned int *)this[10 * v4 + 10]);
        *v12 = *(_DWORD *)this[10 * v4 + 10];
        v14 = *(unsigned int *)this[10 * v4 + 10];
        v12 = (_DWORD *)((char *)v12 + v14);
        v13 += v14;
      }
      else if ( *(_DWORD *)this[10 * v4 + 11] )
      {
        v15 = this[10 * v4 + 13];
        v16 = 0;
        v17 = this[10 * v4 + 10];
        do
        {
          if ( *(_DWORD *)v15 )
          {
            SearchIndexerTrace::Verbose(
              (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\pkmcntrs\\\\pkmcntrs.cxx\"",
              (const wchar_t *)0x14C,
              (unsigned int)L"[UtilCommon] MSSCNTRS:  Writing out data for %ls instance %ls.",
              this[10 * v4 + 7],
              v15 + 14);
            memcpy_0(v12, v15 + 2, *(unsigned int *)this[10 * v4 + 10] + 88LL);
            v17 = this[10 * v4 + 10];
            v18 = *(unsigned int *)v17;
            v12 = (_DWORD *)((char *)v12 + v18 + 88);
            v13 += v18 + 88;
          }
          else
          {
            v18 = *(unsigned int *)v17;
          }
          ++v16;
          v15 = (const wchar_t *)((char *)v15 + v18 + 92);
        }
        while ( v16 < *(_DWORD *)this[10 * v4 + 11] );
        v9 = v19;
      }
      *(_DWORD *)v9 = v13;
      *a2 = v12;
      i = a2;
      *a3 += v13;
      ++*a4;
    }
  }
}

```

## disassembly

```asm
0x18000fd0c  mov     [rsp+arg_18], rbx
0x18000fd11  mov     [rsp+arg_10], r8
0x18000fd16  mov     [rsp+arg_8], rdx
0x18000fd1b  push    rbp
0x18000fd1c  push    rsi
0x18000fd1d  push    rdi
0x18000fd1e  push    r12
0x18000fd20  push    r13
0x18000fd22  push    r14
0x18000fd24  push    r15
0x18000fd26  sub     rsp, 30h
0x18000fd2a  xor     ebp, ebp
0x18000fd2c  mov     r13, r9
0x18000fd2f  mov     rbx, rdx
0x18000fd32  mov     rsi, rcx
0x18000fd35  cmp     [rcx+10h], ebp
0x18000fd38  jbe     loc_18000FEE4
0x18000fd3e  lea     rdi, ds:0[rbp*4]
0x18000fd46  add     rdi, rbp
0x18000fd49  add     rdi, rdi
0x18000fd4c  cmp     dword ptr [rsi+rdi*8+30h], 0
0x18000fd51  jz      loc_18000FED9
0x18000fd57  mov     r9, [rsi+rdi*8+38h]; wchar_t *
0x18000fd5c  lea     r8, aUtilcommonMssc_1; "[UtilCommon] MSSCNTRS: Saving performan"...
0x18000fd63  mov     edx, 11Bh; wchar_t *
0x18000fd68  lea     rcx, aOnecoreuapBase_1; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18000fd6f  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x18000fd74  mov     rax, [rsi+rdi*8+40h]
0x18000fd79  mov     r14, [rbx]
0x18000fd7c  mov     [rsp+68h+arg_0], r14
0x18000fd81  movups  xmm0, xmmword ptr [rax]
0x18000fd84  lea     rbx, [r14+40h]
0x18000fd88  mov     rcx, rbx; void *
0x18000fd8b  movups  xmmword ptr [r14], xmm0
0x18000fd8f  movups  xmm1, xmmword ptr [rax+10h]
0x18000fd93  movups  xmmword ptr [r14+10h], xmm1
0x18000fd98  movups  xmm0, xmmword ptr [rax+20h]
0x18000fd9c  movups  xmmword ptr [r14+20h], xmm0
0x18000fda1  movups  xmm1, xmmword ptr [rax+30h]
0x18000fda5  movups  xmmword ptr [r14+30h], xmm1
0x18000fdaa  mov     eax, [r14+20h]
0x18000fdae  mov     rdx, [rsi+rdi*8+48h]; Src
0x18000fdb3  lea     r8, [rax+rax*4]
0x18000fdb7  shl     r8, 3; Size
0x18000fdbb  call    memcpy_0
0x18000fdc0  cmp     dword ptr [r14+28h], 0FFFFFFFFh
0x18000fdc5  mov     ecx, [r14+20h]
0x18000fdc9  lea     rax, [rcx+rcx*4]
0x18000fdcd  lea     rbx, [rbx+rax*8]
0x18000fdd1  lea     eax, [rcx+rcx*4]
0x18000fdd4  lea     r15d, ds:40h[rax*8]
0x18000fddc  jnz     short loc_18000FE2B
0x18000fdde  mov     r9, [rsi+rdi*8+38h]; wchar_t *
0x18000fde3  lea     r8, aUtilcommonMssc_18; "[UtilCommon] MSSCNTRS:  Writing out dat"...
0x18000fdea  mov     edx, 133h; wchar_t *
0x18000fdef  lea     rcx, aOnecoreuapBase_1; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18000fdf6  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x18000fdfb  mov     rax, [rsi+rdi*8+50h]
0x18000fe00  mov     rcx, rbx; void *
0x18000fe03  mov     rdx, [rsi+rdi*8+60h]; Src
0x18000fe08  mov     r8d, [rax]; Size
0x18000fe0b  call    memcpy_0
0x18000fe10  mov     rax, [rsi+rdi*8+50h]
0x18000fe15  mov     ecx, [rax]
0x18000fe17  mov     [rbx], ecx
0x18000fe19  mov     rax, [rsi+rdi*8+50h]
0x18000fe1e  mov     ecx, [rax]
0x18000fe20  add     rbx, rcx
0x18000fe23  add     r15d, ecx
0x18000fe26  jmp     loc_18000FEBC
0x18000fe2b  mov     rax, [rsi+rdi*8+58h]
0x18000fe30  cmp     dword ptr [rax], 0
0x18000fe33  jbe     loc_18000FEBC
0x18000fe39  mov     r14, [rsi+rdi*8+68h]
0x18000fe3e  xor     r12d, r12d
0x18000fe41  mov     rcx, [rsi+rdi*8+50h]
0x18000fe46  cmp     dword ptr [r14], 0
0x18000fe4a  jz      short loc_18000FEA1
0x18000fe4c  mov     r9, [rsi+rdi*8+38h]; wchar_t *
0x18000fe51  lea     rax, [r14+1Ch]
0x18000fe55  lea     r8, aUtilcommonMssc_12; "[UtilCommon] MSSCNTRS:  Writing out dat"...
0x18000fe5c  mov     [rsp+68h+var_48], rax
0x18000fe61  mov     edx, 14Ch; wchar_t *
0x18000fe66  lea     rcx, aOnecoreuapBase_1; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18000fe6d  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x18000fe72  mov     rax, [rsi+rdi*8+50h]
0x18000fe77  lea     rdx, [r14+4]; Src
0x18000fe7b  mov     rcx, rbx; void *
0x18000fe7e  mov     r8d, [rax]
0x18000fe81  add     r8, 58h ; 'X'; Size
0x18000fe85  call    memcpy_0
0x18000fe8a  mov     rcx, [rsi+rdi*8+50h]
0x18000fe8f  add     rbx, 58h ; 'X'
0x18000fe93  add     r15d, 58h ; 'X'
0x18000fe97  mov     eax, [rcx]
0x18000fe99  add     rbx, rax
0x18000fe9c  add     r15d, eax
0x18000fe9f  jmp     short loc_18000FEA3
0x18000fea1  mov     eax, [rcx]
0x18000fea3  add     rax, 5Ch ; '\'
0x18000fea7  inc     r12d
0x18000feaa  add     r14, rax
0x18000fead  mov     rax, [rsi+rdi*8+58h]
0x18000feb2  cmp     r12d, [rax]
0x18000feb5  jb      short loc_18000FE46
0x18000feb7  mov     r14, [rsp+68h+arg_0]
0x18000febc  mov     rax, [rsp+68h+arg_8]
0x18000fec1  mov     r8, [rsp+68h+arg_10]
0x18000fec9  mov     [r14], r15d
0x18000fecc  mov     [rax], rbx
0x18000fecf  mov     rbx, rax
0x18000fed2  add     [r8], r15d
0x18000fed5  inc     dword ptr [r13+0]
0x18000fed9  inc     ebp
0x18000fedb  cmp     ebp, [rsi+10h]
0x18000fede  jb      loc_18000FD3E
0x18000fee4  mov     rbx, [rsp+68h+arg_18]
0x18000feec  add     rsp, 30h
0x18000fef0  pop     r15
0x18000fef2  pop     r14
0x18000fef4  pop     r13
0x18000fef6  pop     r12
0x18000fef8  pop     rdi
0x18000fef9  pop     rsi
0x18000fefa  pop     rbp
0x18000fefb  retn
```
