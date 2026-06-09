# TracingFailureCache::Add(TracingFailureHash &,CallStackContext &,char const *,long)

- ea: `0x18003a0f0`
- end: `0x18003a1e5`
- name: `?Add@TracingFailureCache@@IEAA_NAEAVTracingFailureHash@@AEAVCallStackContext@@PEBDJ@Z`
- size: `245`
- prototype: `bool(TracingFailureCache *__hidden this, struct TracingFailureHash *, struct CallStackContext *, const char *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18003a7cc`

## callees

- `0x180002894`
- `0x180016b18`
- `0x180039c68`
- `0x18003a0f0`
- `0x18003a2a0`
- `0x18003a500`
- `0x18003a614`
- `0x18003a784`

## import_xrefs

- `MFPlat!MFGetSystemTime` at `0x18003a13b`
- `MFPlat!MFGetSystemTime` at `0x18003a13b`

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
0x18003a0f0  push    rbx
0x18003a0f2  push    rbp
0x18003a0f3  push    rsi
0x18003a0f4  push    rdi
0x18003a0f5  push    r14
0x18003a0f7  sub     rsp, 30h
0x18003a0fb  cmp     dword ptr [rcx+28h], 1Ch
0x18003a0ff  mov     rbp, r9
0x18003a102  mov     r14, r8
0x18003a105  mov     rbx, rcx
0x18003a108  jnz     short loc_18003A10F
0x18003a10a  call    ?EvictOldest@TracingFailureCache@@IEAAXK@Z; TracingFailureCache::EvictOldest(ulong)
0x18003a10f  cmp     dword ptr [rbx+28h], 1Ch
0x18003a113  jnb     loc_18003A1D8
0x18003a119  mov     rdx, [rbx+58h]
0x18003a11d  test    rdx, rdx
0x18003a120  jz      loc_18003A1D8
0x18003a126  mov     eax, [rbx+28h]
0x18003a129  imul    rdi, rax, 918h
0x18003a130  add     rdi, rdx
0x18003a133  mov     rcx, rdi; this
0x18003a136  call    ?Reset@TracingFailureDetails@@QEAAXXZ; TracingFailureDetails::Reset(void)
0x18003a13b  call    cs:__imp_MFGetSystemTime
0x18003a141  inc     dword ptr [rdi+900h]
0x18003a147  mov     rdx, r14; struct CallStackContext *
0x18003a14a  mov     rcx, rdi; this
0x18003a14d  mov     [rdi+8F8h], rax
0x18003a154  call    ?CloneFrom@CallStackContext@@QEAAXAEBV1@@Z; CallStackContext::CloneFrom(CallStackContext const &)
0x18003a159  lea     rsi, [rdi+7F0h]
0x18003a160  test    rbp, rbp
0x18003a163  jz      short loc_18003A18A
0x18003a165  mov     rdx, rsi; char *
0x18003a168  mov     rcx, rbp; char *
0x18003a16b  call    ?HashFunctionTemplate@TracingFailureDetails@@SA_NPEBDPEAD@Z; TracingFailureDetails::HashFunctionTemplate(char const *,char *)
0x18003a170  test    al, al
0x18003a172  jnz     short loc_18003A18D
0x18003a174  or      r9, 0FFFFFFFFFFFFFFFFh
0x18003a178  mov     r8, rbp
0x18003a17b  mov     edx, 100h
0x18003a180  mov     rcx, rsi
0x18003a183  call    _o_strncpy_s_0
0x18003a188  jmp     short loc_18003A18D
0x18003a18a  mov     byte ptr [rsi], 0
0x18003a18d  mov     eax, [rsp+58h+arg_20]
0x18003a194  lea     rdx, [rdi+905h]; struct TracingFailureHash *
0x18003a19b  mov     rcx, rdi; struct CallStackContext *
0x18003a19e  mov     [rdi+8F0h], eax
0x18003a1a4  call    ?GenerateHashCodeForContext@TracingFailureDetails@@SAXAEAVCallStackContext@@AEAVTracingFailureHash@@@Z; TracingFailureDetails::GenerateHashCodeForContext(CallStackContext &,TracingFailureHash &)
0x18003a1a9  inc     dword ptr [rbx+28h]
0x18003a1ac  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x18003a1b3  movups  xmm0, xmmword ptr [r14+7D0h]
0x18003a1bb  mov     r8d, 10h; Size
0x18003a1c1  lea     rcx, [rsp+58h+Buf1]; Buf1
0x18003a1c6  movdqu  [rsp+58h+Buf1], xmm0
0x18003a1cc  call    memcmp_0
0x18003a1d1  test    eax, eax
0x18003a1d3  jnz     short loc_18003A1D8
0x18003a1d5  inc     dword ptr [rbx+30h]
0x18003a1d8  mov     al, 1
0x18003a1da  add     rsp, 30h
0x18003a1de  pop     r14
0x18003a1e0  pop     rdi
0x18003a1e1  pop     rsi
0x18003a1e2  pop     rbp
0x18003a1e3  pop     rbx
0x18003a1e4  retn
```
