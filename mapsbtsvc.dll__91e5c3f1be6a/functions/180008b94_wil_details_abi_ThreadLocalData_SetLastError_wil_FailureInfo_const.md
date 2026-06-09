# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180008b94`
- end: `0x180008c63`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007350`

## callees

- `0x180008378`
- `0x1800087fc`
- `0x180008b94`

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
0x180008b94  push    rbx
0x180008b96  push    rbp
0x180008b97  push    rsi
0x180008b98  push    rdi
0x180008b99  sub     rsp, 28h
0x180008b9d  cmp     qword ptr [rcx+18h], 0
0x180008ba2  mov     rsi, rdx
0x180008ba5  mov     edi, [rcx+10h]
0x180008ba8  mov     rbx, rcx
0x180008bab  mov     ebp, 50h ; 'P'
0x180008bb0  jnz     short loc_180008BE7
0x180008bb2  test    edi, edi
0x180008bb4  jz      short loc_180008BE7
0x180008bb6  mov     edx, 190h; dwBytes
0x180008bbb  lea     ecx, [rbp-48h]; dwFlags
0x180008bbe  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180008bc3  mov     [rbx+18h], rax
0x180008bc7  test    rax, rax
0x180008bca  jz      short loc_180008BE7
0x180008bcc  mov     dword ptr [rbx+20h], 5
0x180008bd3  lea     rcx, [rax+190h]
0x180008bda  jmp     short loc_180008BE2
0x180008bdc  mov     [rax], bp
0x180008bdf  add     rax, rbp
0x180008be2  cmp     rax, rcx
0x180008be5  jnz     short loc_180008BDC
0x180008be7  mov     r9, [rbx+18h]
0x180008beb  test    r9, r9
0x180008bee  jz      short loc_180008C5A
0x180008bf0  test    edi, edi
0x180008bf2  jz      short loc_180008C20
0x180008bf4  movzx   eax, word ptr [rbx+20h]
0x180008bf8  mov     rcx, r9
0x180008bfb  lea     rdx, [rax+rax*4]
0x180008bff  shl     rdx, 4
0x180008c03  add     rdx, r9
0x180008c06  cmp     rcx, rdx
0x180008c09  jz      short loc_180008C20
0x180008c0b  mov     eax, [rbx+10h]
0x180008c0e  cmp     [rcx+4], eax
0x180008c11  jbe     short loc_180008C1B
0x180008c13  mov     eax, [rsi+8]
0x180008c16  cmp     [rcx+8], eax
0x180008c19  jz      short loc_180008C5A
0x180008c1b  add     rcx, rbp
0x180008c1e  jmp     short loc_180008C06
0x180008c20  movzx   eax, word ptr [rbx+22h]
0x180008c24  xor     edx, edx
0x180008c26  movzx   ecx, word ptr [rbx+20h]
0x180008c2a  inc     eax
0x180008c2c  div     ecx
0x180008c2e  mov     rax, [rbx+8]
0x180008c32  mov     r8d, 1
0x180008c38  mov     [rbx+22h], dx
0x180008c3c  lock xadd [rax], r8d
0x180008c41  movzx   eax, dx
0x180008c44  inc     r8d; unsigned int
0x180008c47  mov     rdx, rsi; struct wil::FailureInfo *
0x180008c4a  lea     rcx, [rax+rax*4]
0x180008c4e  shl     rcx, 4
0x180008c52  add     rcx, r9; this
0x180008c55  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180008c5a  add     rsp, 28h
0x180008c5e  pop     rdi
0x180008c5f  pop     rsi
0x180008c60  pop     rbp
0x180008c61  pop     rbx
0x180008c62  retn
```
