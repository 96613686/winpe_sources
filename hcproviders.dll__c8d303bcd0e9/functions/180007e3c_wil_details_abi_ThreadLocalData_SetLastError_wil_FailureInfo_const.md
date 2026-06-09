# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180007e3c`
- end: `0x180007f0c`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `208`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006c10`

## callees

- `0x180007a80`
- `0x180007cb0`
- `0x180007e3c`

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
0x180007e3c  push    rbx
0x180007e3e  push    rbp
0x180007e3f  push    rsi
0x180007e40  push    rdi
0x180007e41  sub     rsp, 28h
0x180007e45  cmp     qword ptr [rcx+18h], 0
0x180007e4a  mov     rsi, rdx
0x180007e4d  mov     edi, [rcx+10h]
0x180007e50  mov     rbx, rcx
0x180007e53  mov     ebp, 50h ; 'P'
0x180007e58  jnz     short loc_180007E8F
0x180007e5a  test    edi, edi
0x180007e5c  jz      short loc_180007E8F
0x180007e5e  mov     edx, 190h; dwBytes
0x180007e63  lea     ecx, [rbp-48h]; dwFlags
0x180007e66  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007e6b  mov     [rbx+18h], rax
0x180007e6f  test    rax, rax
0x180007e72  jz      short loc_180007E8F
0x180007e74  mov     dword ptr [rbx+20h], 5
0x180007e7b  lea     rcx, [rax+190h]
0x180007e82  jmp     short loc_180007E8A
0x180007e84  mov     [rax], bp
0x180007e87  add     rax, rbp
0x180007e8a  cmp     rax, rcx
0x180007e8d  jnz     short loc_180007E84
0x180007e8f  mov     r9, [rbx+18h]
0x180007e93  test    r9, r9
0x180007e96  jz      short loc_180007F02
0x180007e98  test    edi, edi
0x180007e9a  jz      short loc_180007EC8
0x180007e9c  movzx   eax, word ptr [rbx+20h]
0x180007ea0  mov     rcx, r9
0x180007ea3  lea     rdx, [rax+rax*4]
0x180007ea7  shl     rdx, 4
0x180007eab  add     rdx, r9
0x180007eae  cmp     rcx, rdx
0x180007eb1  jz      short loc_180007EC8
0x180007eb3  mov     eax, [rbx+10h]
0x180007eb6  cmp     [rcx+4], eax
0x180007eb9  jbe     short loc_180007EC3
0x180007ebb  mov     eax, [rsi+8]
0x180007ebe  cmp     [rcx+8], eax
0x180007ec1  jz      short loc_180007F02
0x180007ec3  add     rcx, rbp
0x180007ec6  jmp     short loc_180007EAE
0x180007ec8  movzx   eax, word ptr [rbx+22h]
0x180007ecc  xor     edx, edx
0x180007ece  movzx   ecx, word ptr [rbx+20h]
0x180007ed2  inc     eax
0x180007ed4  div     ecx
0x180007ed6  mov     rax, [rbx+8]
0x180007eda  mov     r8d, 1
0x180007ee0  mov     [rbx+22h], dx
0x180007ee4  lock xadd [rax], r8d
0x180007ee9  movzx   eax, dx
0x180007eec  inc     r8d; unsigned int
0x180007eef  mov     rdx, rsi; struct wil::FailureInfo *
0x180007ef2  lea     rcx, [rax+rax*4]
0x180007ef6  shl     rcx, 4
0x180007efa  add     rcx, r9; this
0x180007efd  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180007f02  add     rsp, 28h
0x180007f06  pop     rdi
0x180007f07  pop     rsi
0x180007f08  pop     rbp
0x180007f09  pop     rbx
0x180007f0a  retn
```
