# CEnumSTATPROPSETSTG::CEnumSTATPROPSETSTG(CEnumSTATPROPSETSTG &,long *)

- ea: `0x180056950`
- end: `0x180056a4a`
- name: `??0CEnumSTATPROPSETSTG@@QEAA@AEAV0@PEAJ@Z`
- size: `250`
- prototype: `CEnumSTATPROPSETSTG *__fastcall(CEnumSTATPROPSETSTG *__hidden this, struct CEnumSTATPROPSETSTG *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180056b00`

## callees

- `0x18001e2f0`
- `0x180056950`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180056a0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180056a0a`

## pseudocode

```c
CEnumSTATPROPSETSTG *__fastcall CEnumSTATPROPSETSTG::CEnumSTATPROPSETSTG(
        CEnumSTATPROPSETSTG *this,
        struct CEnumSTATPROPSETSTG *a2,
        int *a3)
{
  int v6; // eax
  unsigned int v7; // edi
  __int64 v8; // rax
  SIZE_T v9; // r14
  unsigned __int16 *v10; // rax

  *((_DWORD *)this + 2) = 1397968979;
  *(_QWORD *)this = &CEnumSTATPROPSETSTG::`vftable';
  *((_DWORD *)this + 3) = 1;
  *((_DWORD *)this + 26) = 0;
  *((_DWORD *)this + 27) = *((_DWORD *)a2 + 27);
  v6 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)a2 + 2) + 48LL))(
         *((_QWORD *)a2 + 2),
         (char *)this + 16);
  *a3 = v6;
  if ( !v6 )
  {
    v7 = 0;
    *(_OWORD *)((char *)this + 24) = *(_OWORD *)((char *)a2 + 24);
    *(_OWORD *)((char *)this + 40) = *(_OWORD *)((char *)a2 + 40);
    *(_OWORD *)((char *)this + 56) = *(_OWORD *)((char *)a2 + 56);
    *(_OWORD *)((char *)this + 72) = *(_OWORD *)((char *)a2 + 72);
    *(_OWORD *)((char *)this + 88) = *(_OWORD *)((char *)a2 + 88);
    *((_DWORD *)this + 26) = *((_DWORD *)a2 + 26);
    while ( v7 < *((_DWORD *)this + 26) )
    {
      v8 = -1;
      do
        ++v8;
      while ( *(_WORD *)(*((_QWORD *)a2 + 10 * v7 + 3) + 2 * v8) );
      v9 = (unsigned int)(2 * v8 + 2);
      v10 = (unsigned __int16 *)CoTaskMemAlloc(v9);
      *((_QWORD *)this + 10 * v7 + 3) = v10;
      if ( !v10 )
      {
        *((_DWORD *)this + 26) = v7;
        *a3 = -2147287032;
        return this;
      }
      StringCbCopyW(v10, (unsigned int)v9, *((const unsigned __int16 **)a2 + 10 * v7++ + 3));
    }
  }
  return this;
}

```

## disassembly

```asm
0x180056950  push    rbx
0x180056952  push    rbp
0x180056953  push    rsi
0x180056954  push    rdi
0x180056955  push    r12
0x180056957  push    r14
0x180056959  push    r15
0x18005695b  sub     rsp, 20h
0x18005695f  mov     dword ptr [rcx+8], 53535053h
0x180056966  lea     rax, ??_7CEnumSTATPROPSETSTG@@6B@; const CEnumSTATPROPSETSTG::`vftable'
0x18005696d  mov     [rcx], rax
0x180056970  mov     rbx, rcx
0x180056973  mov     dword ptr [rcx+0Ch], 1
0x18005697a  mov     rsi, rdx
0x18005697d  xor     r12d, r12d
0x180056980  mov     r15, r8
0x180056983  mov     [rcx+68h], r12d
0x180056987  mov     eax, [rdx+6Ch]
0x18005698a  mov     [rcx+6Ch], eax
0x18005698d  mov     rcx, [rdx+10h]
0x180056991  lea     rdx, [rbx+10h]
0x180056995  mov     rax, [rcx]
0x180056998  mov     rax, [rax+30h]
0x18005699c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800569a1  mov     [r15], eax
0x1800569a4  test    eax, eax
0x1800569a6  jnz     loc_180056A38
0x1800569ac  movups  xmm0, xmmword ptr [rsi+18h]
0x1800569b0  mov     edi, r12d
0x1800569b3  movups  xmmword ptr [rbx+18h], xmm0
0x1800569b7  movups  xmm1, xmmword ptr [rsi+28h]
0x1800569bb  movups  xmmword ptr [rbx+28h], xmm1
0x1800569bf  movups  xmm0, xmmword ptr [rsi+38h]
0x1800569c3  movups  xmmword ptr [rbx+38h], xmm0
0x1800569c7  movups  xmm1, xmmword ptr [rsi+48h]
0x1800569cb  movups  xmmword ptr [rbx+48h], xmm1
0x1800569cf  movups  xmm0, xmmword ptr [rsi+58h]
0x1800569d3  movups  xmmword ptr [rbx+58h], xmm0
0x1800569d7  mov     eax, [rsi+68h]
0x1800569da  mov     [rbx+68h], eax
0x1800569dd  cmp     edi, [rbx+68h]
0x1800569e0  jnb     short loc_180056A38
0x1800569e2  mov     eax, edi
0x1800569e4  lea     rbp, [rax+rax*4]
0x1800569e8  add     rbp, rbp
0x1800569eb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800569ef  mov     rcx, [rsi+rbp*8+18h]
0x1800569f4  inc     rax
0x1800569f7  cmp     [rcx+rax*2], r12w
0x1800569fc  jnz     short loc_1800569F4
0x1800569fe  lea     eax, ds:2[rax*2]
0x180056a05  mov     ecx, eax; cb
0x180056a07  mov     r14d, eax
0x180056a0a  call    cs:__imp_CoTaskMemAlloc
0x180056a10  mov     [rbx+rbp*8+18h], rax
0x180056a15  test    rax, rax
0x180056a18  jz      short loc_180056A2E
0x180056a1a  mov     r8, [rsi+rbp*8+18h]; unsigned __int16 *
0x180056a1f  mov     edx, r14d; unsigned __int64
0x180056a22  mov     rcx, rax; unsigned __int16 *
0x180056a25  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x180056a2a  inc     edi
0x180056a2c  jmp     short loc_1800569DD
0x180056a2e  mov     [rbx+68h], edi
0x180056a31  mov     dword ptr [r15], 80030008h
0x180056a38  mov     rax, rbx
0x180056a3b  add     rsp, 20h
0x180056a3f  pop     r15
0x180056a41  pop     r14
0x180056a43  pop     r12
0x180056a45  pop     rdi
0x180056a46  pop     rsi
0x180056a47  pop     rbp
0x180056a48  pop     rbx
0x180056a49  retn
```
