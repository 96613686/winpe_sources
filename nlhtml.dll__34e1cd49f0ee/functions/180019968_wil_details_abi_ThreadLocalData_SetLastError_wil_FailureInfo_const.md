# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180019968`
- end: `0x180019a37`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180017070`

## callees

- `0x1800183ec`
- `0x1800194e0`
- `0x180019968`

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
0x180019968  push    rbx
0x18001996a  push    rbp
0x18001996b  push    rsi
0x18001996c  push    rdi
0x18001996d  sub     rsp, 28h
0x180019971  cmp     qword ptr [rcx+18h], 0
0x180019976  mov     rsi, rdx
0x180019979  mov     edi, [rcx+10h]
0x18001997c  mov     rbx, rcx
0x18001997f  mov     ebp, 50h ; 'P'
0x180019984  jnz     short loc_1800199BB
0x180019986  test    edi, edi
0x180019988  jz      short loc_1800199BB
0x18001998a  mov     edx, 190h; dwBytes
0x18001998f  lea     ecx, [rbp-48h]; dwFlags
0x180019992  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180019997  mov     [rbx+18h], rax
0x18001999b  test    rax, rax
0x18001999e  jz      short loc_1800199BB
0x1800199a0  mov     dword ptr [rbx+20h], 5
0x1800199a7  lea     rcx, [rax+190h]
0x1800199ae  jmp     short loc_1800199B6
0x1800199b0  mov     [rax], bp
0x1800199b3  add     rax, rbp
0x1800199b6  cmp     rax, rcx
0x1800199b9  jnz     short loc_1800199B0
0x1800199bb  mov     r9, [rbx+18h]
0x1800199bf  test    r9, r9
0x1800199c2  jz      short loc_180019A2E
0x1800199c4  test    edi, edi
0x1800199c6  jz      short loc_1800199F4
0x1800199c8  movzx   eax, word ptr [rbx+20h]
0x1800199cc  mov     rcx, r9
0x1800199cf  lea     rdx, [rax+rax*4]
0x1800199d3  shl     rdx, 4
0x1800199d7  add     rdx, r9
0x1800199da  cmp     rcx, rdx
0x1800199dd  jz      short loc_1800199F4
0x1800199df  mov     eax, [rbx+10h]
0x1800199e2  cmp     [rcx+4], eax
0x1800199e5  jbe     short loc_1800199EF
0x1800199e7  mov     eax, [rsi+8]
0x1800199ea  cmp     [rcx+8], eax
0x1800199ed  jz      short loc_180019A2E
0x1800199ef  add     rcx, rbp
0x1800199f2  jmp     short loc_1800199DA
0x1800199f4  movzx   eax, word ptr [rbx+22h]
0x1800199f8  xor     edx, edx
0x1800199fa  movzx   ecx, word ptr [rbx+20h]
0x1800199fe  inc     eax
0x180019a00  div     ecx
0x180019a02  mov     rax, [rbx+8]
0x180019a06  mov     r8d, 1
0x180019a0c  mov     [rbx+22h], dx
0x180019a10  lock xadd [rax], r8d
0x180019a15  movzx   eax, dx
0x180019a18  inc     r8d; unsigned int
0x180019a1b  mov     rdx, rsi; struct wil::FailureInfo *
0x180019a1e  lea     rcx, [rax+rax*4]
0x180019a22  shl     rcx, 4
0x180019a26  add     rcx, r9; this
0x180019a29  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180019a2e  add     rsp, 28h
0x180019a32  pop     rdi
0x180019a33  pop     rsi
0x180019a34  pop     rbp
0x180019a35  pop     rbx
0x180019a36  retn
```
