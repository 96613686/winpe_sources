# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x14001a924`
- end: `0x14001a9f3`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140018150`

## callees

- `0x140019514`
- `0x14001a460`
- `0x14001a924`

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
0x14001a924  push    rbx
0x14001a926  push    rbp
0x14001a927  push    rsi
0x14001a928  push    rdi
0x14001a929  sub     rsp, 28h
0x14001a92d  cmp     qword ptr [rcx+18h], 0
0x14001a932  mov     rsi, rdx
0x14001a935  mov     edi, [rcx+10h]
0x14001a938  mov     rbx, rcx
0x14001a93b  mov     ebp, 50h ; 'P'
0x14001a940  jnz     short loc_14001A977
0x14001a942  test    edi, edi
0x14001a944  jz      short loc_14001A977
0x14001a946  mov     edx, 190h; dwBytes
0x14001a94b  lea     ecx, [rbp-48h]; dwFlags
0x14001a94e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14001a953  mov     [rbx+18h], rax
0x14001a957  test    rax, rax
0x14001a95a  jz      short loc_14001A977
0x14001a95c  mov     dword ptr [rbx+20h], 5
0x14001a963  lea     rcx, [rax+190h]
0x14001a96a  jmp     short loc_14001A972
0x14001a96c  mov     [rax], bp
0x14001a96f  add     rax, rbp
0x14001a972  cmp     rax, rcx
0x14001a975  jnz     short loc_14001A96C
0x14001a977  mov     r9, [rbx+18h]
0x14001a97b  test    r9, r9
0x14001a97e  jz      short loc_14001A9EA
0x14001a980  test    edi, edi
0x14001a982  jz      short loc_14001A9B0
0x14001a984  movzx   eax, word ptr [rbx+20h]
0x14001a988  mov     rcx, r9
0x14001a98b  lea     rdx, [rax+rax*4]
0x14001a98f  shl     rdx, 4
0x14001a993  add     rdx, r9
0x14001a996  cmp     rcx, rdx
0x14001a999  jz      short loc_14001A9B0
0x14001a99b  mov     eax, [rbx+10h]
0x14001a99e  cmp     [rcx+4], eax
0x14001a9a1  jbe     short loc_14001A9AB
0x14001a9a3  mov     eax, [rsi+8]
0x14001a9a6  cmp     [rcx+8], eax
0x14001a9a9  jz      short loc_14001A9EA
0x14001a9ab  add     rcx, rbp
0x14001a9ae  jmp     short loc_14001A996
0x14001a9b0  movzx   eax, word ptr [rbx+22h]
0x14001a9b4  xor     edx, edx
0x14001a9b6  movzx   ecx, word ptr [rbx+20h]
0x14001a9ba  inc     eax
0x14001a9bc  div     ecx
0x14001a9be  mov     rax, [rbx+8]
0x14001a9c2  mov     r8d, 1
0x14001a9c8  mov     [rbx+22h], dx
0x14001a9cc  lock xadd [rax], r8d
0x14001a9d1  movzx   eax, dx
0x14001a9d4  inc     r8d; unsigned int
0x14001a9d7  mov     rdx, rsi; struct wil::FailureInfo *
0x14001a9da  lea     rcx, [rax+rax*4]
0x14001a9de  shl     rcx, 4
0x14001a9e2  add     rcx, r9; this
0x14001a9e5  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x14001a9ea  add     rsp, 28h
0x14001a9ee  pop     rdi
0x14001a9ef  pop     rsi
0x14001a9f0  pop     rbp
0x14001a9f1  pop     rbx
0x14001a9f2  retn
```
