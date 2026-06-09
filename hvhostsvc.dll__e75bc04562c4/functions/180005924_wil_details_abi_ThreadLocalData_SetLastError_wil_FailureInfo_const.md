# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180005924`
- end: `0x1800059f3`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003f00`

## callees

- `0x180005108`
- `0x18000558c`
- `0x180005924`

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
0x180005924  push    rbx
0x180005926  push    rbp
0x180005927  push    rsi
0x180005928  push    rdi
0x180005929  sub     rsp, 28h
0x18000592d  cmp     qword ptr [rcx+18h], 0
0x180005932  mov     rsi, rdx
0x180005935  mov     edi, [rcx+10h]
0x180005938  mov     rbx, rcx
0x18000593b  mov     ebp, 50h ; 'P'
0x180005940  jnz     short loc_180005977
0x180005942  test    edi, edi
0x180005944  jz      short loc_180005977
0x180005946  mov     edx, 190h; dwBytes
0x18000594b  lea     ecx, [rbp-48h]; dwFlags
0x18000594e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180005953  mov     [rbx+18h], rax
0x180005957  test    rax, rax
0x18000595a  jz      short loc_180005977
0x18000595c  mov     dword ptr [rbx+20h], 5
0x180005963  lea     rcx, [rax+190h]
0x18000596a  jmp     short loc_180005972
0x18000596c  mov     [rax], bp
0x18000596f  add     rax, rbp
0x180005972  cmp     rax, rcx
0x180005975  jnz     short loc_18000596C
0x180005977  mov     r9, [rbx+18h]
0x18000597b  test    r9, r9
0x18000597e  jz      short loc_1800059EA
0x180005980  test    edi, edi
0x180005982  jz      short loc_1800059B0
0x180005984  movzx   eax, word ptr [rbx+20h]
0x180005988  mov     rcx, r9
0x18000598b  lea     rdx, [rax+rax*4]
0x18000598f  shl     rdx, 4
0x180005993  add     rdx, r9
0x180005996  cmp     rcx, rdx
0x180005999  jz      short loc_1800059B0
0x18000599b  mov     eax, [rbx+10h]
0x18000599e  cmp     [rcx+4], eax
0x1800059a1  jbe     short loc_1800059AB
0x1800059a3  mov     eax, [rsi+8]
0x1800059a6  cmp     [rcx+8], eax
0x1800059a9  jz      short loc_1800059EA
0x1800059ab  add     rcx, rbp
0x1800059ae  jmp     short loc_180005996
0x1800059b0  movzx   eax, word ptr [rbx+22h]
0x1800059b4  xor     edx, edx
0x1800059b6  movzx   ecx, word ptr [rbx+20h]
0x1800059ba  inc     eax
0x1800059bc  div     ecx
0x1800059be  mov     rax, [rbx+8]
0x1800059c2  mov     r8d, 1
0x1800059c8  mov     [rbx+22h], dx
0x1800059cc  lock xadd [rax], r8d
0x1800059d1  movzx   eax, dx
0x1800059d4  inc     r8d; unsigned int
0x1800059d7  mov     rdx, rsi; struct wil::FailureInfo *
0x1800059da  lea     rcx, [rax+rax*4]
0x1800059de  shl     rcx, 4
0x1800059e2  add     rcx, r9; this
0x1800059e5  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800059ea  add     rsp, 28h
0x1800059ee  pop     rdi
0x1800059ef  pop     rsi
0x1800059f0  pop     rbp
0x1800059f1  pop     rbx
0x1800059f2  retn
```
