# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x1800133b8`
- end: `0x180013487`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800101a0`

## callees

- `0x1800115ac`
- `0x18001316c`
- `0x1800133b8`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::SetLastError(
        wil::details_abi::ThreadLocalData *this,
        const struct wil::FailureInfo *a2)
{
  int v3; // edi
  _WORD *v5; // rax
  _WORD *v6; // rcx
  __int64 v7; // r9
  __int64 i; // rcx
  unsigned __int16 v9; // dx
  volatile signed __int32 *v10; // rax

  v3 = *((_DWORD *)this + 4);
  if ( !*((_QWORD *)this + 3) )
  {
    if ( v3 )
    {
      v5 = wil::details::ProcessHeapAlloc(8u, 0x190u);
      *((_QWORD *)this + 3) = v5;
      if ( v5 )
      {
        *((_DWORD *)this + 8) = 5;
        v6 = v5 + 200;
        while ( v5 != v6 )
        {
          *v5 = 80;
          v5 += 40;
        }
      }
    }
  }
  v7 = *((_QWORD *)this + 3);
  if ( v7 )
  {
    if ( v3 )
    {
      for ( i = *((_QWORD *)this + 3); i != v7 + 80LL * *((unsigned __int16 *)this + 16); i += 80 )
      {
        if ( *(_DWORD *)(i + 4) > *((_DWORD *)this + 4) && *(_DWORD *)(i + 8) == *((_DWORD *)a2 + 2) )
          return;
      }
    }
    v9 = ((unsigned int)*((unsigned __int16 *)this + 17) + 1) % *((unsigned __int16 *)this + 16);
    v10 = (volatile signed __int32 *)*((_QWORD *)this + 1);
    *((_WORD *)this + 17) = v9;
    wil::details_abi::ThreadLocalFailureInfo::Set(
      (wil::details_abi::ThreadLocalFailureInfo *)(v7 + 80LL * v9),
      a2,
      _InterlockedIncrement(v10));
  }
}

```

## disassembly

```asm
0x1800133b8  push    rbx
0x1800133ba  push    rbp
0x1800133bb  push    rsi
0x1800133bc  push    rdi
0x1800133bd  sub     rsp, 28h
0x1800133c1  cmp     qword ptr [rcx+18h], 0
0x1800133c6  mov     rsi, rdx
0x1800133c9  mov     edi, [rcx+10h]
0x1800133cc  mov     rbx, rcx
0x1800133cf  mov     ebp, 50h ; 'P'
0x1800133d4  jnz     short loc_18001340B
0x1800133d6  test    edi, edi
0x1800133d8  jz      short loc_18001340B
0x1800133da  mov     edx, 190h; dwBytes
0x1800133df  lea     ecx, [rbp-48h]; dwFlags
0x1800133e2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800133e7  mov     [rbx+18h], rax
0x1800133eb  test    rax, rax
0x1800133ee  jz      short loc_18001340B
0x1800133f0  mov     dword ptr [rbx+20h], 5
0x1800133f7  lea     rcx, [rax+190h]
0x1800133fe  jmp     short loc_180013406
0x180013400  mov     [rax], bp
0x180013403  add     rax, rbp
0x180013406  cmp     rax, rcx
0x180013409  jnz     short loc_180013400
0x18001340b  mov     r9, [rbx+18h]
0x18001340f  test    r9, r9
0x180013412  jz      short loc_18001347E
0x180013414  test    edi, edi
0x180013416  jz      short loc_180013444
0x180013418  movzx   eax, word ptr [rbx+20h]
0x18001341c  mov     rcx, r9
0x18001341f  lea     rdx, [rax+rax*4]
0x180013423  shl     rdx, 4
0x180013427  add     rdx, r9
0x18001342a  cmp     rcx, rdx
0x18001342d  jz      short loc_180013444
0x18001342f  mov     eax, [rbx+10h]
0x180013432  cmp     [rcx+4], eax
0x180013435  jbe     short loc_18001343F
0x180013437  mov     eax, [rsi+8]
0x18001343a  cmp     [rcx+8], eax
0x18001343d  jz      short loc_18001347E
0x18001343f  add     rcx, rbp
0x180013442  jmp     short loc_18001342A
0x180013444  movzx   eax, word ptr [rbx+22h]
0x180013448  xor     edx, edx
0x18001344a  movzx   ecx, word ptr [rbx+20h]
0x18001344e  inc     eax
0x180013450  div     ecx
0x180013452  mov     rax, [rbx+8]
0x180013456  mov     r8d, 1
0x18001345c  mov     [rbx+22h], dx
0x180013460  lock xadd [rax], r8d
0x180013465  movzx   eax, dx
0x180013468  inc     r8d; unsigned int
0x18001346b  mov     rdx, rsi; struct wil::FailureInfo *
0x18001346e  lea     rcx, [rax+rax*4]
0x180013472  shl     rcx, 4
0x180013476  add     rcx, r9; this
0x180013479  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18001347e  add     rsp, 28h
0x180013482  pop     rdi
0x180013483  pop     rsi
0x180013484  pop     rbp
0x180013485  pop     rbx
0x180013486  retn
```
