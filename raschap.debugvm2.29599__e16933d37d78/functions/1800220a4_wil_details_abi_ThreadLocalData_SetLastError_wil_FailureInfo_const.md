# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x1800220a4`
- end: `0x180022173`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001ffb0`

## callees

- `0x180021260`
- `0x180021c20`
- `0x1800220a4`

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
0x1800220a4  push    rbx
0x1800220a6  push    rbp
0x1800220a7  push    rsi
0x1800220a8  push    rdi
0x1800220a9  sub     rsp, 28h
0x1800220ad  cmp     qword ptr [rcx+18h], 0
0x1800220b2  mov     rsi, rdx
0x1800220b5  mov     edi, [rcx+10h]
0x1800220b8  mov     rbx, rcx
0x1800220bb  mov     ebp, 50h ; 'P'
0x1800220c0  jnz     short loc_1800220F7
0x1800220c2  test    edi, edi
0x1800220c4  jz      short loc_1800220F7
0x1800220c6  mov     edx, 190h; dwBytes
0x1800220cb  lea     ecx, [rbp-48h]; dwFlags
0x1800220ce  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800220d3  mov     [rbx+18h], rax
0x1800220d7  test    rax, rax
0x1800220da  jz      short loc_1800220F7
0x1800220dc  mov     dword ptr [rbx+20h], 5
0x1800220e3  lea     rcx, [rax+190h]
0x1800220ea  jmp     short loc_1800220F2
0x1800220ec  mov     [rax], bp
0x1800220ef  add     rax, rbp
0x1800220f2  cmp     rax, rcx
0x1800220f5  jnz     short loc_1800220EC
0x1800220f7  mov     r9, [rbx+18h]
0x1800220fb  test    r9, r9
0x1800220fe  jz      short loc_18002216A
0x180022100  test    edi, edi
0x180022102  jz      short loc_180022130
0x180022104  movzx   eax, word ptr [rbx+20h]
0x180022108  mov     rcx, r9
0x18002210b  lea     rdx, [rax+rax*4]
0x18002210f  shl     rdx, 4
0x180022113  add     rdx, r9
0x180022116  cmp     rcx, rdx
0x180022119  jz      short loc_180022130
0x18002211b  mov     eax, [rbx+10h]
0x18002211e  cmp     [rcx+4], eax
0x180022121  jbe     short loc_18002212B
0x180022123  mov     eax, [rsi+8]
0x180022126  cmp     [rcx+8], eax
0x180022129  jz      short loc_18002216A
0x18002212b  add     rcx, rbp
0x18002212e  jmp     short loc_180022116
0x180022130  movzx   eax, word ptr [rbx+22h]
0x180022134  xor     edx, edx
0x180022136  movzx   ecx, word ptr [rbx+20h]
0x18002213a  inc     eax
0x18002213c  div     ecx
0x18002213e  mov     rax, [rbx+8]
0x180022142  mov     r8d, 1
0x180022148  mov     [rbx+22h], dx
0x18002214c  lock xadd [rax], r8d
0x180022151  movzx   eax, dx
0x180022154  inc     r8d; unsigned int
0x180022157  mov     rdx, rsi; struct wil::FailureInfo *
0x18002215a  lea     rcx, [rax+rax*4]
0x18002215e  shl     rcx, 4
0x180022162  add     rcx, r9; this
0x180022165  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18002216a  add     rsp, 28h
0x18002216e  pop     rdi
0x18002216f  pop     rsi
0x180022170  pop     rbp
0x180022171  pop     rbx
0x180022172  retn
```
