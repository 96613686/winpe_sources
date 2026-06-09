# TracingFailureCache::Add(TracingFailureHash &,CallStackContext &,char const *,long)

- ea: `0x1800026d8`
- end: `0x1800027cd`
- name: `?Add@TracingFailureCache@@IEAA_NAEAVTracingFailureHash@@AEAVCallStackContext@@PEBDJ@Z`
- size: `245`
- prototype: `bool(TracingFailureCache *__hidden this, struct TracingFailureHash *, struct CallStackContext *, const char *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180004ed8`

## callees

- `0x1800026d8`
- `0x1800027d4`
- `0x180003878`
- `0x18000460c`
- `0x180004a28`
- `0x180004d20`
- `0x180004e90`
- `0x18000502d`

## import_xrefs

- `MFPlat!MFGetSystemTime` at `0x180002723`
- `MFPlat!MFGetSystemTime` at `0x180002723`

## pseudocode

```c
char __fastcall TracingFailureCache::Add(
        TracingFailureCache *this,
        struct TracingFailureHash *a2,
        struct CallStackContext *a3,
        const char *a4,
        int a5)
{
  __int64 v8; // rdx
  __int64 v9; // rdi
  MFTIME v10; // rax
  _OWORD Buf1[3]; // [rsp+20h] [rbp-38h] BYREF

  if ( *((_DWORD *)this + 10) == 28 )
    TracingFailureCache::EvictOldest(this, (unsigned int)a2);
  if ( *((_DWORD *)this + 10) < 0x1Cu )
  {
    v8 = *((_QWORD *)this + 11);
    if ( v8 )
    {
      v9 = v8 + 2328LL * *((unsigned int *)this + 10);
      TracingFailureDetails::Reset((TracingFailureDetails *)v9);
      v10 = MFGetSystemTime();
      ++*(_DWORD *)(v9 + 2304);
      *(_QWORD *)(v9 + 2296) = v10;
      CallStackContext::CloneFrom((CallStackContext *)v9, a3);
      if ( a4 )
      {
        if ( !TracingFailureDetails::HashFunctionTemplate(a4, (char *)(v9 + 2032)) )
          o_strncpy_s_0(v9 + 2032, 256, a4, -1);
      }
      else
      {
        *(_BYTE *)(v9 + 2032) = 0;
      }
      *(_DWORD *)(v9 + 2288) = a5;
      TracingFailureDetails::GenerateHashCodeForContext(
        (struct CallStackContext *)v9,
        (struct TracingFailureHash *)(v9 + 2309));
      ++*((_DWORD *)this + 10);
      Buf1[0] = *((_OWORD *)a3 + 125);
      if ( !memcmp_0(Buf1, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
        ++*((_DWORD *)this + 12);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x1800026d8  push    rbx
0x1800026da  push    rbp
0x1800026db  push    rsi
0x1800026dc  push    rdi
0x1800026dd  push    r14
0x1800026df  sub     rsp, 30h
0x1800026e3  cmp     dword ptr [rcx+28h], 1Ch
0x1800026e7  mov     rbp, r9
0x1800026ea  mov     r14, r8
0x1800026ed  mov     rbx, rcx
0x1800026f0  jnz     short loc_1800026F7
0x1800026f2  call    ?EvictOldest@TracingFailureCache@@IEAAXK@Z; TracingFailureCache::EvictOldest(ulong)
0x1800026f7  cmp     dword ptr [rbx+28h], 1Ch
0x1800026fb  jnb     loc_1800027C0
0x180002701  mov     rdx, [rbx+58h]
0x180002705  test    rdx, rdx
0x180002708  jz      loc_1800027C0
0x18000270e  mov     eax, [rbx+28h]
0x180002711  imul    rdi, rax, 918h
0x180002718  add     rdi, rdx
0x18000271b  mov     rcx, rdi; this
0x18000271e  call    ?Reset@TracingFailureDetails@@QEAAXXZ; TracingFailureDetails::Reset(void)
0x180002723  call    cs:__imp_MFGetSystemTime
0x180002729  inc     dword ptr [rdi+900h]
0x18000272f  mov     rdx, r14; struct CallStackContext *
0x180002732  mov     rcx, rdi; this
0x180002735  mov     [rdi+8F8h], rax
0x18000273c  call    ?CloneFrom@CallStackContext@@QEAAXAEBV1@@Z; CallStackContext::CloneFrom(CallStackContext const &)
0x180002741  lea     rsi, [rdi+7F0h]
0x180002748  test    rbp, rbp
0x18000274b  jz      short loc_180002772
0x18000274d  mov     rdx, rsi; char *
0x180002750  mov     rcx, rbp; char *
0x180002753  call    ?HashFunctionTemplate@TracingFailureDetails@@SA_NPEBDPEAD@Z; TracingFailureDetails::HashFunctionTemplate(char const *,char *)
0x180002758  test    al, al
0x18000275a  jnz     short loc_180002775
0x18000275c  or      r9, 0FFFFFFFFFFFFFFFFh
0x180002760  mov     r8, rbp
0x180002763  mov     edx, 100h
0x180002768  mov     rcx, rsi
0x18000276b  call    _o_strncpy_s_0
0x180002770  jmp     short loc_180002775
0x180002772  mov     byte ptr [rsi], 0
0x180002775  mov     eax, [rsp+58h+arg_20]
0x18000277c  lea     rdx, [rdi+905h]; struct TracingFailureHash *
0x180002783  mov     rcx, rdi; struct CallStackContext *
0x180002786  mov     [rdi+8F0h], eax
0x18000278c  call    ?GenerateHashCodeForContext@TracingFailureDetails@@SAXAEAVCallStackContext@@AEAVTracingFailureHash@@@Z; TracingFailureDetails::GenerateHashCodeForContext(CallStackContext &,TracingFailureHash &)
0x180002791  inc     dword ptr [rbx+28h]
0x180002794  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x18000279b  movups  xmm0, xmmword ptr [r14+7D0h]
0x1800027a3  mov     r8d, 10h; Size
0x1800027a9  lea     rcx, [rsp+58h+Buf1]; Buf1
0x1800027ae  movdqu  [rsp+58h+Buf1], xmm0
0x1800027b4  call    memcmp_0
0x1800027b9  test    eax, eax
0x1800027bb  jnz     short loc_1800027C0
0x1800027bd  inc     dword ptr [rbx+30h]
0x1800027c0  mov     al, 1
0x1800027c2  add     rsp, 30h
0x1800027c6  pop     r14
0x1800027c8  pop     rdi
0x1800027c9  pop     rsi
0x1800027ca  pop     rbp
0x1800027cb  pop     rbx
0x1800027cc  retn
```
