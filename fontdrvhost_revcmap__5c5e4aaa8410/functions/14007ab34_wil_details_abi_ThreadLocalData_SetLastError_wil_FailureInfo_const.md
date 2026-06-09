# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x14007ab34`
- end: `0x14007ac03`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400789a0`

## callees

- `0x140079c0c`
- `0x14007a6b0`
- `0x14007ab34`

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
0x14007ab34  push    rbx
0x14007ab36  push    rbp
0x14007ab37  push    rsi
0x14007ab38  push    rdi
0x14007ab39  sub     rsp, 28h
0x14007ab3d  cmp     qword ptr [rcx+18h], 0
0x14007ab42  mov     rsi, rdx
0x14007ab45  mov     edi, [rcx+10h]
0x14007ab48  mov     rbx, rcx
0x14007ab4b  mov     ebp, 50h ; 'P'
0x14007ab50  jnz     short loc_14007AB87
0x14007ab52  test    edi, edi
0x14007ab54  jz      short loc_14007AB87
0x14007ab56  mov     edx, 190h; dwBytes
0x14007ab5b  lea     ecx, [rbp-48h]; dwFlags
0x14007ab5e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14007ab63  mov     [rbx+18h], rax
0x14007ab67  test    rax, rax
0x14007ab6a  jz      short loc_14007AB87
0x14007ab6c  mov     dword ptr [rbx+20h], 5
0x14007ab73  lea     rcx, [rax+190h]
0x14007ab7a  jmp     short loc_14007AB82
0x14007ab7c  mov     [rax], bp
0x14007ab7f  add     rax, rbp
0x14007ab82  cmp     rax, rcx
0x14007ab85  jnz     short loc_14007AB7C
0x14007ab87  mov     r9, [rbx+18h]
0x14007ab8b  test    r9, r9
0x14007ab8e  jz      short loc_14007ABFA
0x14007ab90  test    edi, edi
0x14007ab92  jz      short loc_14007ABC0
0x14007ab94  movzx   eax, word ptr [rbx+20h]
0x14007ab98  mov     rcx, r9
0x14007ab9b  lea     rdx, [rax+rax*4]
0x14007ab9f  shl     rdx, 4
0x14007aba3  add     rdx, r9
0x14007aba6  cmp     rcx, rdx
0x14007aba9  jz      short loc_14007ABC0
0x14007abab  mov     eax, [rbx+10h]
0x14007abae  cmp     [rcx+4], eax
0x14007abb1  jbe     short loc_14007ABBB
0x14007abb3  mov     eax, [rsi+8]
0x14007abb6  cmp     [rcx+8], eax
0x14007abb9  jz      short loc_14007ABFA
0x14007abbb  add     rcx, rbp
0x14007abbe  jmp     short loc_14007ABA6
0x14007abc0  movzx   eax, word ptr [rbx+22h]
0x14007abc4  xor     edx, edx
0x14007abc6  movzx   ecx, word ptr [rbx+20h]
0x14007abca  inc     eax
0x14007abcc  div     ecx
0x14007abce  mov     rax, [rbx+8]
0x14007abd2  mov     r8d, 1
0x14007abd8  mov     [rbx+22h], dx
0x14007abdc  lock xadd [rax], r8d
0x14007abe1  movzx   eax, dx
0x14007abe4  inc     r8d; unsigned int
0x14007abe7  mov     rdx, rsi; struct wil::FailureInfo *
0x14007abea  lea     rcx, [rax+rax*4]
0x14007abee  shl     rcx, 4
0x14007abf2  add     rcx, r9; this
0x14007abf5  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x14007abfa  add     rsp, 28h
0x14007abfe  pop     rdi
0x14007abff  pop     rsi
0x14007ac00  pop     rbp
0x14007ac01  pop     rbx
0x14007ac02  retn
```
