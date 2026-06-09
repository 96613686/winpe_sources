# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180008d24`
- end: `0x180008df3`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800065d0`

## callees

- `0x180007f04`
- `0x1800088a0`
- `0x180008d24`

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
0x180008d24  push    rbx
0x180008d26  push    rbp
0x180008d27  push    rsi
0x180008d28  push    rdi
0x180008d29  sub     rsp, 28h
0x180008d2d  cmp     qword ptr [rcx+18h], 0
0x180008d32  mov     rsi, rdx
0x180008d35  mov     edi, [rcx+10h]
0x180008d38  mov     rbx, rcx
0x180008d3b  mov     ebp, 50h ; 'P'
0x180008d40  jnz     short loc_180008D77
0x180008d42  test    edi, edi
0x180008d44  jz      short loc_180008D77
0x180008d46  mov     edx, 190h; dwBytes
0x180008d4b  lea     ecx, [rbp-48h]; dwFlags
0x180008d4e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008d53  mov     [rbx+18h], rax
0x180008d57  test    rax, rax
0x180008d5a  jz      short loc_180008D77
0x180008d5c  mov     dword ptr [rbx+20h], 5
0x180008d63  lea     rcx, [rax+190h]
0x180008d6a  jmp     short loc_180008D72
0x180008d6c  mov     [rax], bp
0x180008d6f  add     rax, rbp
0x180008d72  cmp     rax, rcx
0x180008d75  jnz     short loc_180008D6C
0x180008d77  mov     r9, [rbx+18h]
0x180008d7b  test    r9, r9
0x180008d7e  jz      short loc_180008DEA
0x180008d80  test    edi, edi
0x180008d82  jz      short loc_180008DB0
0x180008d84  movzx   eax, word ptr [rbx+20h]
0x180008d88  mov     rcx, r9
0x180008d8b  lea     rdx, [rax+rax*4]
0x180008d8f  shl     rdx, 4
0x180008d93  add     rdx, r9
0x180008d96  cmp     rcx, rdx
0x180008d99  jz      short loc_180008DB0
0x180008d9b  mov     eax, [rbx+10h]
0x180008d9e  cmp     [rcx+4], eax
0x180008da1  jbe     short loc_180008DAB
0x180008da3  mov     eax, [rsi+8]
0x180008da6  cmp     [rcx+8], eax
0x180008da9  jz      short loc_180008DEA
0x180008dab  add     rcx, rbp
0x180008dae  jmp     short loc_180008D96
0x180008db0  movzx   eax, word ptr [rbx+22h]
0x180008db4  xor     edx, edx
0x180008db6  movzx   ecx, word ptr [rbx+20h]
0x180008dba  inc     eax
0x180008dbc  div     ecx
0x180008dbe  mov     rax, [rbx+8]
0x180008dc2  mov     r8d, 1
0x180008dc8  mov     [rbx+22h], dx
0x180008dcc  lock xadd [rax], r8d
0x180008dd1  movzx   eax, dx
0x180008dd4  inc     r8d; unsigned int
0x180008dd7  mov     rdx, rsi; struct wil::FailureInfo *
0x180008dda  lea     rcx, [rax+rax*4]
0x180008dde  shl     rcx, 4
0x180008de2  add     rcx, r9; this
0x180008de5  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180008dea  add     rsp, 28h
0x180008dee  pop     rdi
0x180008def  pop     rsi
0x180008df0  pop     rbp
0x180008df1  pop     rbx
0x180008df2  retn
```
