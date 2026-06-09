# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x140004c14`
- end: `0x140004ce3`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400035a0`

## callees

- `0x140004768`
- `0x140004a9c`
- `0x140004c14`

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
0x140004c14  push    rbx
0x140004c16  push    rbp
0x140004c17  push    rsi
0x140004c18  push    rdi
0x140004c19  sub     rsp, 28h
0x140004c1d  cmp     qword ptr [rcx+18h], 0
0x140004c22  mov     rsi, rdx
0x140004c25  mov     edi, [rcx+10h]
0x140004c28  mov     rbx, rcx
0x140004c2b  mov     ebp, 50h ; 'P'
0x140004c30  jnz     short loc_140004C67
0x140004c32  test    edi, edi
0x140004c34  jz      short loc_140004C67
0x140004c36  mov     edx, 190h; dwBytes
0x140004c3b  lea     ecx, [rbp-48h]; dwFlags
0x140004c3e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140004c43  mov     [rbx+18h], rax
0x140004c47  test    rax, rax
0x140004c4a  jz      short loc_140004C67
0x140004c4c  mov     dword ptr [rbx+20h], 5
0x140004c53  lea     rcx, [rax+190h]
0x140004c5a  jmp     short loc_140004C62
0x140004c5c  mov     [rax], bp
0x140004c5f  add     rax, rbp
0x140004c62  cmp     rax, rcx
0x140004c65  jnz     short loc_140004C5C
0x140004c67  mov     r9, [rbx+18h]
0x140004c6b  test    r9, r9
0x140004c6e  jz      short loc_140004CDA
0x140004c70  test    edi, edi
0x140004c72  jz      short loc_140004CA0
0x140004c74  movzx   eax, word ptr [rbx+20h]
0x140004c78  mov     rcx, r9
0x140004c7b  lea     rdx, [rax+rax*4]
0x140004c7f  shl     rdx, 4
0x140004c83  add     rdx, r9
0x140004c86  cmp     rcx, rdx
0x140004c89  jz      short loc_140004CA0
0x140004c8b  mov     eax, [rbx+10h]
0x140004c8e  cmp     [rcx+4], eax
0x140004c91  jbe     short loc_140004C9B
0x140004c93  mov     eax, [rsi+8]
0x140004c96  cmp     [rcx+8], eax
0x140004c99  jz      short loc_140004CDA
0x140004c9b  add     rcx, rbp
0x140004c9e  jmp     short loc_140004C86
0x140004ca0  movzx   eax, word ptr [rbx+22h]
0x140004ca4  xor     edx, edx
0x140004ca6  movzx   ecx, word ptr [rbx+20h]
0x140004caa  inc     eax
0x140004cac  div     ecx
0x140004cae  mov     rax, [rbx+8]
0x140004cb2  mov     r8d, 1
0x140004cb8  mov     [rbx+22h], dx
0x140004cbc  lock xadd [rax], r8d
0x140004cc1  movzx   eax, dx
0x140004cc4  inc     r8d; unsigned int
0x140004cc7  mov     rdx, rsi; struct wil::FailureInfo *
0x140004cca  lea     rcx, [rax+rax*4]
0x140004cce  shl     rcx, 4
0x140004cd2  add     rcx, r9; this
0x140004cd5  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x140004cda  add     rsp, 28h
0x140004cde  pop     rdi
0x140004cdf  pop     rsi
0x140004ce0  pop     rbp
0x140004ce1  pop     rbx
0x140004ce2  retn
```
