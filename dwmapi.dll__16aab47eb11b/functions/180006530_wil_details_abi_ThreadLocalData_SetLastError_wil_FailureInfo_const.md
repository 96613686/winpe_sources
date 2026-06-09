# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180006530`
- end: `0x180006624`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `244`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800062f0`

## callees

- `0x180006530`
- `0x18000a760`
- `0x18000c5c4`
- `0x18000c788`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::SetLastError(
        wil::details_abi::ThreadLocalData *this,
        const struct wil::FailureInfo *a2)
{
  int v3; // edi
  __int64 v5; // r9
  _WORD *j; // rcx
  LPVOID v7; // rax
  _WORD *i; // rcx
  unsigned __int16 v9; // dx
  volatile signed __int32 *v10; // rax
  _WORD *v11; // [rsp+20h] [rbp-38h] BYREF
  _WORD *v12; // [rsp+28h] [rbp-30h]

  v3 = *((_DWORD *)this + 4);
  if ( !*((_QWORD *)this + 3) )
  {
    if ( v3 )
    {
      v7 = wil::details::ProcessHeapAlloc(8u, 0x190u);
      *((_QWORD *)this + 3) = v7;
      if ( v7 )
      {
        *((_DWORD *)this + 8) = 5;
        wil::make_range<wil::details_abi::ThreadLocalFailureInfo *>(&v11, v7);
        for ( i = v11; i != v12; i += 40 )
          *i = 80;
      }
    }
  }
  v5 = *((_QWORD *)this + 3);
  if ( v5 )
  {
    if ( v3 )
    {
      wil::make_range<wil::details_abi::ThreadLocalFailureInfo *>(&v11, *((_QWORD *)this + 3));
      for ( j = v11; j != v12; j += 40 )
      {
        if ( *((_DWORD *)j + 1) > *((_DWORD *)this + 4) && *((_DWORD *)j + 2) == *((_DWORD *)a2 + 2) )
          return;
      }
    }
    v9 = ((unsigned int)*((unsigned __int16 *)this + 17) + 1) % *((unsigned __int16 *)this + 16);
    v10 = (volatile signed __int32 *)*((_QWORD *)this + 1);
    *((_WORD *)this + 17) = v9;
    wil::details_abi::ThreadLocalFailureInfo::Set(
      (wil::details_abi::ThreadLocalFailureInfo *)(v5 + 80LL * v9),
      a2,
      _InterlockedIncrement(v10));
  }
}

```

## disassembly

```asm
0x180006530  push    rbx
0x180006532  push    rbp
0x180006533  push    rsi
0x180006534  push    rdi
0x180006535  sub     rsp, 38h
0x180006539  cmp     qword ptr [rcx+18h], 0
0x18000653e  mov     rsi, rdx
0x180006541  mov     edi, [rcx+10h]
0x180006544  mov     rbx, rcx
0x180006547  mov     ebp, 50h ; 'P'
0x18000654c  jnz     short loc_180006552
0x18000654e  test    edi, edi
0x180006550  jnz     short loc_18000659D
0x180006552  mov     r9, [rbx+18h]
0x180006556  test    r9, r9
0x180006559  jnz     short loc_180006564
0x18000655b  add     rsp, 38h
0x18000655f  pop     rdi
0x180006560  pop     rsi
0x180006561  pop     rbp
0x180006562  pop     rbx
0x180006563  retn
0x180006564  test    edi, edi
0x180006566  jz      short loc_1800065E5
0x180006568  movzx   r8d, word ptr [rbx+20h]
0x18000656d  lea     rcx, [rsp+58h+var_38]
0x180006572  mov     rdx, r9
0x180006575  call    ??$make_range@PEAUThreadLocalFailureInfo@details_abi@wil@@@wil@@YA?AV?$pointer_range@PEAUThreadLocalFailureInfo@details_abi@wil@@@details@0@PEAUThreadLocalFailureInfo@details_abi@0@_K@Z; wil::make_range<wil::details_abi::ThreadLocalFailureInfo *>(wil::details_abi::ThreadLocalFailureInfo *,unsigned __int64)
0x18000657a  mov     rcx, [rsp+58h+var_38]
0x18000657f  cmp     rcx, [rsp+58h+var_30]
0x180006584  jz      short loc_1800065E5
0x180006586  mov     eax, [rbx+10h]
0x180006589  cmp     [rcx+4], eax
0x18000658c  ja      short loc_180006593
0x18000658e  add     rcx, rbp
0x180006591  jmp     short loc_18000657F
0x180006593  mov     eax, [rsi+8]
0x180006596  cmp     [rcx+8], eax
0x180006599  jnz     short loc_18000658E
0x18000659b  jmp     short loc_18000655B
0x18000659d  mov     edx, 190h; dwBytes
0x1800065a2  mov     ecx, 8; dwFlags
0x1800065a7  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800065ac  mov     [rbx+18h], rax
0x1800065b0  test    rax, rax
0x1800065b3  jz      short loc_180006552
0x1800065b5  mov     r8d, 5
0x1800065bb  lea     rcx, [rsp+58h+var_38]
0x1800065c0  mov     rdx, rax
0x1800065c3  mov     [rbx+20h], r8d
0x1800065c7  call    ??$make_range@PEAUThreadLocalFailureInfo@details_abi@wil@@@wil@@YA?AV?$pointer_range@PEAUThreadLocalFailureInfo@details_abi@wil@@@details@0@PEAUThreadLocalFailureInfo@details_abi@0@_K@Z; wil::make_range<wil::details_abi::ThreadLocalFailureInfo *>(wil::details_abi::ThreadLocalFailureInfo *,unsigned __int64)
0x1800065cc  mov     rcx, [rsp+58h+var_38]
0x1800065d1  jmp     short loc_1800065D9
0x1800065d3  mov     [rcx], bp
0x1800065d6  add     rcx, rbp
0x1800065d9  cmp     rcx, [rsp+58h+var_30]
0x1800065de  jnz     short loc_1800065D3
0x1800065e0  jmp     loc_180006552
0x1800065e5  movzx   eax, word ptr [rbx+22h]
0x1800065e9  xor     edx, edx
0x1800065eb  movzx   ecx, word ptr [rbx+20h]
0x1800065ef  inc     eax
0x1800065f1  div     ecx
0x1800065f3  mov     rax, [rbx+8]
0x1800065f7  mov     r8d, 1
0x1800065fd  mov     [rbx+22h], dx
0x180006601  lock xadd [rax], r8d
0x180006606  movzx   eax, dx
0x180006609  inc     r8d; unsigned int
0x18000660c  mov     rdx, rsi; struct wil::FailureInfo *
0x18000660f  lea     rcx, [rax+rax*4]
0x180006613  shl     rcx, 4
0x180006617  add     rcx, r9; this
0x18000661a  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000661f  jmp     loc_18000655B
```
