# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x18000b1e8`
- end: `0x18000b2b7`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180008b30`

## callees

- `0x180009c48`
- `0x18000afc0`
- `0x18000b1e8`

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
0x18000b1e8  push    rbx
0x18000b1ea  push    rbp
0x18000b1eb  push    rsi
0x18000b1ec  push    rdi
0x18000b1ed  sub     rsp, 28h
0x18000b1f1  cmp     qword ptr [rcx+18h], 0
0x18000b1f6  mov     rsi, rdx
0x18000b1f9  mov     edi, [rcx+10h]
0x18000b1fc  mov     rbx, rcx
0x18000b1ff  mov     ebp, 50h ; 'P'
0x18000b204  jnz     short loc_18000B23B
0x18000b206  test    edi, edi
0x18000b208  jz      short loc_18000B23B
0x18000b20a  mov     edx, 190h; dwBytes
0x18000b20f  lea     ecx, [rbp-48h]; dwFlags
0x18000b212  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000b217  mov     [rbx+18h], rax
0x18000b21b  test    rax, rax
0x18000b21e  jz      short loc_18000B23B
0x18000b220  mov     dword ptr [rbx+20h], 5
0x18000b227  lea     rcx, [rax+190h]
0x18000b22e  jmp     short loc_18000B236
0x18000b230  mov     [rax], bp
0x18000b233  add     rax, rbp
0x18000b236  cmp     rax, rcx
0x18000b239  jnz     short loc_18000B230
0x18000b23b  mov     r9, [rbx+18h]
0x18000b23f  test    r9, r9
0x18000b242  jz      short loc_18000B2AE
0x18000b244  test    edi, edi
0x18000b246  jz      short loc_18000B274
0x18000b248  movzx   eax, word ptr [rbx+20h]
0x18000b24c  mov     rcx, r9
0x18000b24f  lea     rdx, [rax+rax*4]
0x18000b253  shl     rdx, 4
0x18000b257  add     rdx, r9
0x18000b25a  cmp     rcx, rdx
0x18000b25d  jz      short loc_18000B274
0x18000b25f  mov     eax, [rbx+10h]
0x18000b262  cmp     [rcx+4], eax
0x18000b265  jbe     short loc_18000B26F
0x18000b267  mov     eax, [rsi+8]
0x18000b26a  cmp     [rcx+8], eax
0x18000b26d  jz      short loc_18000B2AE
0x18000b26f  add     rcx, rbp
0x18000b272  jmp     short loc_18000B25A
0x18000b274  movzx   eax, word ptr [rbx+22h]
0x18000b278  xor     edx, edx
0x18000b27a  movzx   ecx, word ptr [rbx+20h]
0x18000b27e  inc     eax
0x18000b280  div     ecx
0x18000b282  mov     rax, [rbx+8]
0x18000b286  mov     r8d, 1
0x18000b28c  mov     [rbx+22h], dx
0x18000b290  lock xadd [rax], r8d
0x18000b295  movzx   eax, dx
0x18000b298  inc     r8d; unsigned int
0x18000b29b  mov     rdx, rsi; struct wil::FailureInfo *
0x18000b29e  lea     rcx, [rax+rax*4]
0x18000b2a2  shl     rcx, 4
0x18000b2a6  add     rcx, r9; this
0x18000b2a9  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000b2ae  add     rsp, 28h
0x18000b2b2  pop     rdi
0x18000b2b3  pop     rsi
0x18000b2b4  pop     rbp
0x18000b2b5  pop     rbx
0x18000b2b6  retn
```
