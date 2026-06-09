# CValueChunk::GetValueChunk(tagFULLPROPSPEC &,tagPROPVARIANT * &)

- ea: `0x18000d57c`
- end: `0x18000d67e`
- name: `?GetValueChunk@CValueChunk@@QEAAXAEAUtagFULLPROPSPEC@@AEAPEAUtagPROPVARIANT@@@Z`
- size: `258`
- prototype: `void __fastcall(CValueChunk *__hidden this, struct tagFULLPROPSPEC *, struct tagPROPVARIANT **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d400`

## callees

- `0x18000d57c`
- `0x180013500`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d654`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d654`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d5a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d5f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d5a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d5f9`

## pseudocode

```c
void __fastcall CValueChunk::GetValueChunk(CValueChunk *this, struct tagFULLPROPSPEC *a2, LPVOID *a3)
{
  struct tagPROPVARIANT *v5; // rax
  __int64 i; // r9
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *a2 = *(struct tagFULLPROPSPEC *)this;
  v5 = (struct tagPROPVARIANT *)CoTaskMemAlloc(0x18u);
  *a3 = v5;
  if ( !v5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5B,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\deferred.hxx",
      (const char *)0x8007000ELL,
      v7);
  if ( *((_DWORD *)this + 9) == 1 )
  {
    v5->vt = 31;
    *((_QWORD *)*a3 + 1) = **((_QWORD **)this + 5);
  }
  else
  {
    v5->vt = 4127;
    *((_DWORD *)*a3 + 2) = *((_DWORD *)this + 9);
    *((_QWORD *)*a3 + 2) = CoTaskMemAlloc(8LL * *((unsigned int *)this + 9));
    if ( !*((_QWORD *)*a3 + 2) )
    {
      CoTaskMemFree(*a3);
      *a3 = 0;
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6C,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\deferred.hxx",
        (const char *)0x8007000ELL,
        v7);
    }
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 9); i = (unsigned int)(i + 1) )
      *(_QWORD *)(*((_QWORD *)*a3 + 2) + 8 * i) = *(_QWORD *)(*((_QWORD *)this + 5) + 8 * i);
  }
  *((_DWORD *)this + 9) = 0;
}

```

## disassembly

```asm
0x18000d57c  mov     [rsp+arg_0], rbx
0x18000d581  push    rdi; int
0x18000d582  sub     rsp, 20h
0x18000d586  movups  xmm0, xmmword ptr [rcx]
0x18000d589  mov     rbx, rcx
0x18000d58c  mov     rdi, r8
0x18000d58f  movdqu  xmmword ptr [rdx], xmm0
0x18000d593  movups  xmm1, xmmword ptr [rcx+10h]
0x18000d597  mov     ecx, 18h; cb
0x18000d59c  movdqu  xmmword ptr [rdx+10h], xmm1
0x18000d5a1  call    cs:__imp_CoTaskMemAlloc
0x18000d5a7  mov     [rdi], rax
0x18000d5aa  test    rax, rax
0x18000d5ad  jz      loc_18000D637
0x18000d5b3  cmp     dword ptr [rbx+24h], 1
0x18000d5b7  jnz     short loc_18000D5E1
0x18000d5b9  mov     ecx, 1Fh
0x18000d5be  mov     [rax], cx
0x18000d5c1  mov     rax, [rbx+28h]
0x18000d5c5  mov     rcx, [rdi]
0x18000d5c8  mov     rax, [rax]
0x18000d5cb  mov     [rcx+8], rax
0x18000d5cf  mov     dword ptr [rbx+24h], 0
0x18000d5d6  mov     rbx, [rsp+28h+arg_0]
0x18000d5db  add     rsp, 20h
0x18000d5df  pop     rdi
0x18000d5e0  retn
0x18000d5e1  mov     ecx, 101Fh
0x18000d5e6  mov     [rax], cx
0x18000d5e9  mov     rcx, [rdi]
0x18000d5ec  mov     eax, [rbx+24h]
0x18000d5ef  mov     [rcx+8], eax
0x18000d5f2  mov     ecx, [rbx+24h]
0x18000d5f5  shl     rcx, 3; cb
0x18000d5f9  call    cs:__imp_CoTaskMemAlloc
0x18000d5ff  mov     rcx, [rdi]
0x18000d602  mov     [rcx+10h], rax
0x18000d606  mov     rcx, [rdi]; pv
0x18000d609  cmp     qword ptr [rcx+10h], 0
0x18000d60e  jz      short loc_18000D654
0x18000d610  xor     r9d, r9d
0x18000d613  cmp     [rbx+24h], r9d
0x18000d617  jbe     short loc_18000D5CF
0x18000d619  mov     rax, [rdi]
0x18000d61c  mov     rdx, [rbx+28h]
0x18000d620  mov     rcx, [rax+10h]
0x18000d624  mov     rax, [rdx+r9*8]
0x18000d628  mov     [rcx+r9*8], rax
0x18000d62c  inc     r9d
0x18000d62f  cmp     r9d, [rbx+24h]
0x18000d633  jb      short loc_18000D619
0x18000d635  jmp     short loc_18000D5CF
0x18000d637  mov     rcx, [rsp+28h]; this
0x18000d63c  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18000d643  mov     r9d, 8007000Eh; char *
0x18000d649  mov     edx, 5Bh ; '['; void *
0x18000d64e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000d654  call    cs:__imp_CoTaskMemFree
0x18000d65a  mov     rcx, [rsp+28h]; this
0x18000d65f  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18000d666  mov     r9d, 8007000Eh; char *
0x18000d66c  mov     qword ptr [rdi], 0
0x18000d673  mov     edx, 6Ch ; 'l'; void *
0x18000d678  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
