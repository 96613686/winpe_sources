# TracingFailureCache::Add(TracingFailureHash &,CallStackContext &,char const *,long)

- ea: `0x1800224f0`
- end: `0x1800225e5`
- name: `?Add@TracingFailureCache@@IEAA_NAEAVTracingFailureHash@@AEAVCallStackContext@@PEBDJ@Z`
- size: `245`
- prototype: `bool(TracingFailureCache *__hidden this, struct TracingFailureHash *, struct CallStackContext *, const char *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18006e3a0`

## callees

- `0x1800224f0`
- `0x1800225ec`
- `0x180024bb8`
- `0x18006dadc`
- `0x18006df50`
- `0x18006e1e8`
- `0x18006e358`
- `0x18006ef8f`

## import_xrefs

- `MFPlat!MFGetSystemTime` at `0x18002253b`
- `MFPlat!MFGetSystemTime` at `0x18002253b`

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
0x1800224f0  push    rbx
0x1800224f2  push    rbp
0x1800224f3  push    rsi
0x1800224f4  push    rdi
0x1800224f5  push    r14
0x1800224f7  sub     rsp, 30h
0x1800224fb  cmp     dword ptr [rcx+28h], 1Ch
0x1800224ff  mov     rbp, r9
0x180022502  mov     r14, r8
0x180022505  mov     rbx, rcx
0x180022508  jnz     short loc_18002250F
0x18002250a  call    ?EvictOldest@TracingFailureCache@@IEAAXK@Z; TracingFailureCache::EvictOldest(ulong)
0x18002250f  cmp     dword ptr [rbx+28h], 1Ch
0x180022513  jnb     loc_1800225D8
0x180022519  mov     rdx, [rbx+58h]
0x18002251d  test    rdx, rdx
0x180022520  jz      loc_1800225D8
0x180022526  mov     eax, [rbx+28h]
0x180022529  imul    rdi, rax, 918h
0x180022530  add     rdi, rdx
0x180022533  mov     rcx, rdi; this
0x180022536  call    ?Reset@TracingFailureDetails@@QEAAXXZ; TracingFailureDetails::Reset(void)
0x18002253b  call    cs:__imp_MFGetSystemTime
0x180022541  inc     dword ptr [rdi+900h]
0x180022547  mov     rdx, r14; struct CallStackContext *
0x18002254a  mov     rcx, rdi; this
0x18002254d  mov     [rdi+8F8h], rax
0x180022554  call    ?CloneFrom@CallStackContext@@QEAAXAEBV1@@Z; CallStackContext::CloneFrom(CallStackContext const &)
0x180022559  lea     rsi, [rdi+7F0h]
0x180022560  test    rbp, rbp
0x180022563  jz      short loc_18002258A
0x180022565  mov     rdx, rsi; char *
0x180022568  mov     rcx, rbp; char *
0x18002256b  call    ?HashFunctionTemplate@TracingFailureDetails@@SA_NPEBDPEAD@Z; TracingFailureDetails::HashFunctionTemplate(char const *,char *)
0x180022570  test    al, al
0x180022572  jnz     short loc_18002258D
0x180022574  or      r9, 0FFFFFFFFFFFFFFFFh
0x180022578  mov     r8, rbp
0x18002257b  mov     edx, 100h
0x180022580  mov     rcx, rsi
0x180022583  call    _o_strncpy_s_0
0x180022588  jmp     short loc_18002258D
0x18002258a  mov     byte ptr [rsi], 0
0x18002258d  mov     eax, [rsp+58h+arg_20]
0x180022594  lea     rdx, [rdi+905h]; struct TracingFailureHash *
0x18002259b  mov     rcx, rdi; struct CallStackContext *
0x18002259e  mov     [rdi+8F0h], eax
0x1800225a4  call    ?GenerateHashCodeForContext@TracingFailureDetails@@SAXAEAVCallStackContext@@AEAVTracingFailureHash@@@Z; TracingFailureDetails::GenerateHashCodeForContext(CallStackContext &,TracingFailureHash &)
0x1800225a9  inc     dword ptr [rbx+28h]
0x1800225ac  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x1800225b3  movups  xmm0, xmmword ptr [r14+7D0h]
0x1800225bb  mov     r8d, 10h; Size
0x1800225c1  lea     rcx, [rsp+58h+Buf1]; Buf1
0x1800225c6  movdqu  [rsp+58h+Buf1], xmm0
0x1800225cc  call    memcmp_0
0x1800225d1  test    eax, eax
0x1800225d3  jnz     short loc_1800225D8
0x1800225d5  inc     dword ptr [rbx+30h]
0x1800225d8  mov     al, 1
0x1800225da  add     rsp, 30h
0x1800225de  pop     r14
0x1800225e0  pop     rdi
0x1800225e1  pop     rsi
0x1800225e2  pop     rbp
0x1800225e3  pop     rbx
0x1800225e4  retn
```
