# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180007de4`
- end: `0x180007eb3`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006d20`

## callees

- `0x180007788`
- `0x180007a4c`
- `0x180007de4`

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
0x180007de4  push    rbx
0x180007de6  push    rbp
0x180007de7  push    rsi
0x180007de8  push    rdi
0x180007de9  sub     rsp, 28h
0x180007ded  cmp     qword ptr [rcx+18h], 0
0x180007df2  mov     rsi, rdx
0x180007df5  mov     edi, [rcx+10h]
0x180007df8  mov     rbx, rcx
0x180007dfb  mov     ebp, 50h ; 'P'
0x180007e00  jnz     short loc_180007E37
0x180007e02  test    edi, edi
0x180007e04  jz      short loc_180007E37
0x180007e06  mov     edx, 190h; dwBytes
0x180007e0b  lea     ecx, [rbp-48h]; dwFlags
0x180007e0e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180007e13  mov     [rbx+18h], rax
0x180007e17  test    rax, rax
0x180007e1a  jz      short loc_180007E37
0x180007e1c  mov     dword ptr [rbx+20h], 5
0x180007e23  lea     rcx, [rax+190h]
0x180007e2a  jmp     short loc_180007E32
0x180007e2c  mov     [rax], bp
0x180007e2f  add     rax, rbp
0x180007e32  cmp     rax, rcx
0x180007e35  jnz     short loc_180007E2C
0x180007e37  mov     r9, [rbx+18h]
0x180007e3b  test    r9, r9
0x180007e3e  jz      short loc_180007EAA
0x180007e40  test    edi, edi
0x180007e42  jz      short loc_180007E70
0x180007e44  movzx   eax, word ptr [rbx+20h]
0x180007e48  mov     rcx, r9
0x180007e4b  lea     rdx, [rax+rax*4]
0x180007e4f  shl     rdx, 4
0x180007e53  add     rdx, r9
0x180007e56  cmp     rcx, rdx
0x180007e59  jz      short loc_180007E70
0x180007e5b  mov     eax, [rbx+10h]
0x180007e5e  cmp     [rcx+4], eax
0x180007e61  jbe     short loc_180007E6B
0x180007e63  mov     eax, [rsi+8]
0x180007e66  cmp     [rcx+8], eax
0x180007e69  jz      short loc_180007EAA
0x180007e6b  add     rcx, rbp
0x180007e6e  jmp     short loc_180007E56
0x180007e70  movzx   eax, word ptr [rbx+22h]
0x180007e74  xor     edx, edx
0x180007e76  movzx   ecx, word ptr [rbx+20h]
0x180007e7a  inc     eax
0x180007e7c  div     ecx
0x180007e7e  mov     rax, [rbx+8]
0x180007e82  mov     r8d, 1
0x180007e88  mov     [rbx+22h], dx
0x180007e8c  lock xadd [rax], r8d
0x180007e91  movzx   eax, dx
0x180007e94  inc     r8d; unsigned int
0x180007e97  mov     rdx, rsi; struct wil::FailureInfo *
0x180007e9a  lea     rcx, [rax+rax*4]
0x180007e9e  shl     rcx, 4
0x180007ea2  add     rcx, r9; this
0x180007ea5  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180007eaa  add     rsp, 28h
0x180007eae  pop     rdi
0x180007eaf  pop     rsi
0x180007eb0  pop     rbp
0x180007eb1  pop     rbx
0x180007eb2  retn
```
