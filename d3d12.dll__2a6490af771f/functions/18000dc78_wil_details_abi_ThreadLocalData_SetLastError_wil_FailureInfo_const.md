# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x18000dc78`
- end: `0x18000dd47`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000cc80`

## callees

- `0x18000a8f4`
- `0x18000d8e0`
- `0x18000dc78`

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
0x18000dc78  push    rbx
0x18000dc7a  push    rbp
0x18000dc7b  push    rsi
0x18000dc7c  push    rdi
0x18000dc7d  sub     rsp, 28h
0x18000dc81  cmp     qword ptr [rcx+18h], 0
0x18000dc86  mov     rsi, rdx
0x18000dc89  mov     edi, [rcx+10h]
0x18000dc8c  mov     rbx, rcx
0x18000dc8f  mov     ebp, 50h ; 'P'
0x18000dc94  jnz     short loc_18000DCCB
0x18000dc96  test    edi, edi
0x18000dc98  jz      short loc_18000DCCB
0x18000dc9a  mov     edx, 190h; dwBytes
0x18000dc9f  lea     ecx, [rbp-48h]; dwFlags
0x18000dca2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x18000dca7  mov     [rbx+18h], rax
0x18000dcab  test    rax, rax
0x18000dcae  jz      short loc_18000DCCB
0x18000dcb0  mov     dword ptr [rbx+20h], 5
0x18000dcb7  lea     rcx, [rax+190h]
0x18000dcbe  jmp     short loc_18000DCC6
0x18000dcc0  mov     [rax], bp
0x18000dcc3  add     rax, rbp
0x18000dcc6  cmp     rax, rcx
0x18000dcc9  jnz     short loc_18000DCC0
0x18000dccb  mov     r9, [rbx+18h]
0x18000dccf  test    r9, r9
0x18000dcd2  jz      short loc_18000DD3E
0x18000dcd4  test    edi, edi
0x18000dcd6  jz      short loc_18000DD04
0x18000dcd8  movzx   eax, word ptr [rbx+20h]
0x18000dcdc  mov     rcx, r9
0x18000dcdf  lea     rdx, [rax+rax*4]
0x18000dce3  shl     rdx, 4
0x18000dce7  add     rdx, r9
0x18000dcea  cmp     rcx, rdx
0x18000dced  jz      short loc_18000DD04
0x18000dcef  mov     eax, [rbx+10h]
0x18000dcf2  cmp     [rcx+4], eax
0x18000dcf5  jbe     short loc_18000DCFF
0x18000dcf7  mov     eax, [rsi+8]
0x18000dcfa  cmp     [rcx+8], eax
0x18000dcfd  jz      short loc_18000DD3E
0x18000dcff  add     rcx, rbp
0x18000dd02  jmp     short loc_18000DCEA
0x18000dd04  movzx   eax, word ptr [rbx+22h]
0x18000dd08  xor     edx, edx
0x18000dd0a  movzx   ecx, word ptr [rbx+20h]
0x18000dd0e  inc     eax
0x18000dd10  div     ecx
0x18000dd12  mov     rax, [rbx+8]
0x18000dd16  mov     r8d, 1
0x18000dd1c  mov     [rbx+22h], dx
0x18000dd20  lock xadd [rax], r8d
0x18000dd25  movzx   eax, dx
0x18000dd28  inc     r8d; unsigned int
0x18000dd2b  mov     rdx, rsi; struct wil::FailureInfo *
0x18000dd2e  lea     rcx, [rax+rax*4]
0x18000dd32  shl     rcx, 4
0x18000dd36  add     rcx, r9; this
0x18000dd39  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18000dd3e  add     rsp, 28h
0x18000dd42  pop     rdi
0x18000dd43  pop     rsi
0x18000dd44  pop     rbp
0x18000dd45  pop     rbx
0x18000dd46  retn
```
