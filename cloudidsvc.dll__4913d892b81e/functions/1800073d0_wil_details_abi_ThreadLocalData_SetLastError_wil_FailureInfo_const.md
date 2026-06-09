# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x1800073d0`
- end: `0x18000749f`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005580`

## callees

- `0x180006854`
- `0x180007038`
- `0x1800073d0`

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
0x1800073d0  push    rbx
0x1800073d2  push    rbp
0x1800073d3  push    rsi
0x1800073d4  push    rdi
0x1800073d5  sub     rsp, 28h
0x1800073d9  cmp     qword ptr [rcx+18h], 0
0x1800073de  mov     rsi, rdx
0x1800073e1  mov     edi, [rcx+10h]
0x1800073e4  mov     rbx, rcx
0x1800073e7  mov     ebp, 50h ; 'P'
0x1800073ec  jnz     short loc_180007423
0x1800073ee  test    edi, edi
0x1800073f0  jz      short loc_180007423
0x1800073f2  mov     edx, 190h; dwBytes
0x1800073f7  lea     ecx, [rbp-48h]; dwFlags
0x1800073fa  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800073ff  mov     [rbx+18h], rax
0x180007403  test    rax, rax
0x180007406  jz      short loc_180007423
0x180007408  mov     dword ptr [rbx+20h], 5
0x18000740f  lea     rcx, [rax+190h]
0x180007416  jmp     short loc_18000741E
0x180007418  mov     [rax], bp
0x18000741b  add     rax, rbp
0x18000741e  cmp     rax, rcx
0x180007421  jnz     short loc_180007418
0x180007423  mov     r9, [rbx+18h]
0x180007427  test    r9, r9
0x18000742a  jz      short loc_180007496
0x18000742c  test    edi, edi
0x18000742e  jz      short loc_18000745C
0x180007430  movzx   eax, word ptr [rbx+20h]
0x180007434  mov     rcx, r9
0x180007437  lea     rdx, [rax+rax*4]
0x18000743b  shl     rdx, 4
0x18000743f  add     rdx, r9
0x180007442  cmp     rcx, rdx
0x180007445  jz      short loc_18000745C
0x180007447  mov     eax, [rbx+10h]
0x18000744a  cmp     [rcx+4], eax
0x18000744d  jbe     short loc_180007457
0x18000744f  mov     eax, [rsi+8]
0x180007452  cmp     [rcx+8], eax
0x180007455  jz      short loc_180007496
0x180007457  add     rcx, rbp
0x18000745a  jmp     short loc_180007442
0x18000745c  movzx   eax, word ptr [rbx+22h]
0x180007460  xor     edx, edx
0x180007462  movzx   ecx, word ptr [rbx+20h]
0x180007466  inc     eax
0x180007468  div     ecx
0x18000746a  mov     rax, [rbx+8]
0x18000746e  mov     r8d, 1
0x180007474  mov     [rbx+22h], dx
0x180007478  lock xadd [rax], r8d
0x18000747d  movzx   eax, dx
0x180007480  inc     r8d; unsigned int
0x180007483  mov     rdx, rsi; struct wil::FailureInfo *
0x180007486  lea     rcx, [rax+rax*4]
0x18000748a  shl     rcx, 4
0x18000748e  add     rcx, r9; this
0x180007491  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180007496  add     rsp, 28h
0x18000749a  pop     rdi
0x18000749b  pop     rsi
0x18000749c  pop     rbp
0x18000749d  pop     rbx
0x18000749e  retn
```
