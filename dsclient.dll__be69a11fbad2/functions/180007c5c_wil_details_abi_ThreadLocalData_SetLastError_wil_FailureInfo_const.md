# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180007c5c`
- end: `0x180007d2b`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005760`

## callees

- `0x180006a5c`
- `0x1800079f4`
- `0x180007c5c`

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
0x180007c5c  push    rbx
0x180007c5e  push    rbp
0x180007c5f  push    rsi
0x180007c60  push    rdi
0x180007c61  sub     rsp, 28h
0x180007c65  cmp     qword ptr [rcx+18h], 0
0x180007c6a  mov     rsi, rdx
0x180007c6d  mov     edi, [rcx+10h]
0x180007c70  mov     rbx, rcx
0x180007c73  mov     ebp, 50h ; 'P'
0x180007c78  jnz     short loc_180007CAF
0x180007c7a  test    edi, edi
0x180007c7c  jz      short loc_180007CAF
0x180007c7e  mov     edx, 190h; dwBytes
0x180007c83  lea     ecx, [rbp-48h]; dwFlags
0x180007c86  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007c8b  mov     [rbx+18h], rax
0x180007c8f  test    rax, rax
0x180007c92  jz      short loc_180007CAF
0x180007c94  mov     dword ptr [rbx+20h], 5
0x180007c9b  lea     rcx, [rax+190h]
0x180007ca2  jmp     short loc_180007CAA
0x180007ca4  mov     [rax], bp
0x180007ca7  add     rax, rbp
0x180007caa  cmp     rax, rcx
0x180007cad  jnz     short loc_180007CA4
0x180007caf  mov     r9, [rbx+18h]
0x180007cb3  test    r9, r9
0x180007cb6  jz      short loc_180007D22
0x180007cb8  test    edi, edi
0x180007cba  jz      short loc_180007CE8
0x180007cbc  movzx   eax, word ptr [rbx+20h]
0x180007cc0  mov     rcx, r9
0x180007cc3  lea     rdx, [rax+rax*4]
0x180007cc7  shl     rdx, 4
0x180007ccb  add     rdx, r9
0x180007cce  cmp     rcx, rdx
0x180007cd1  jz      short loc_180007CE8
0x180007cd3  mov     eax, [rbx+10h]
0x180007cd6  cmp     [rcx+4], eax
0x180007cd9  jbe     short loc_180007CE3
0x180007cdb  mov     eax, [rsi+8]
0x180007cde  cmp     [rcx+8], eax
0x180007ce1  jz      short loc_180007D22
0x180007ce3  add     rcx, rbp
0x180007ce6  jmp     short loc_180007CCE
0x180007ce8  movzx   eax, word ptr [rbx+22h]
0x180007cec  xor     edx, edx
0x180007cee  movzx   ecx, word ptr [rbx+20h]
0x180007cf2  inc     eax
0x180007cf4  div     ecx
0x180007cf6  mov     rax, [rbx+8]
0x180007cfa  mov     r8d, 1
0x180007d00  mov     [rbx+22h], dx
0x180007d04  lock xadd [rax], r8d
0x180007d09  movzx   eax, dx
0x180007d0c  inc     r8d; unsigned int
0x180007d0f  mov     rdx, rsi; struct wil::FailureInfo *
0x180007d12  lea     rcx, [rax+rax*4]
0x180007d16  shl     rcx, 4
0x180007d1a  add     rcx, r9; this
0x180007d1d  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180007d22  add     rsp, 28h
0x180007d26  pop     rdi
0x180007d27  pop     rsi
0x180007d28  pop     rbp
0x180007d29  pop     rbx
0x180007d2a  retn
```
