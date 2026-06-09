# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x14000ab88`
- end: `0x14000ac57`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140008990`

## callees

- `0x140009b40`
- `0x14000a924`
- `0x14000ab88`

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
0x14000ab88  push    rbx
0x14000ab8a  push    rbp
0x14000ab8b  push    rsi
0x14000ab8c  push    rdi
0x14000ab8d  sub     rsp, 28h
0x14000ab91  cmp     qword ptr [rcx+18h], 0
0x14000ab96  mov     rsi, rdx
0x14000ab99  mov     edi, [rcx+10h]
0x14000ab9c  mov     rbx, rcx
0x14000ab9f  mov     ebp, 50h ; 'P'
0x14000aba4  jnz     short loc_14000ABDB
0x14000aba6  test    edi, edi
0x14000aba8  jz      short loc_14000ABDB
0x14000abaa  mov     edx, 190h; dwBytes
0x14000abaf  lea     ecx, [rbp-48h]; dwFlags
0x14000abb2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000abb7  mov     [rbx+18h], rax
0x14000abbb  test    rax, rax
0x14000abbe  jz      short loc_14000ABDB
0x14000abc0  mov     dword ptr [rbx+20h], 5
0x14000abc7  lea     rcx, [rax+190h]
0x14000abce  jmp     short loc_14000ABD6
0x14000abd0  mov     [rax], bp
0x14000abd3  add     rax, rbp
0x14000abd6  cmp     rax, rcx
0x14000abd9  jnz     short loc_14000ABD0
0x14000abdb  mov     r9, [rbx+18h]
0x14000abdf  test    r9, r9
0x14000abe2  jz      short loc_14000AC4E
0x14000abe4  test    edi, edi
0x14000abe6  jz      short loc_14000AC14
0x14000abe8  movzx   eax, word ptr [rbx+20h]
0x14000abec  mov     rcx, r9
0x14000abef  lea     rdx, [rax+rax*4]
0x14000abf3  shl     rdx, 4
0x14000abf7  add     rdx, r9
0x14000abfa  cmp     rcx, rdx
0x14000abfd  jz      short loc_14000AC14
0x14000abff  mov     eax, [rbx+10h]
0x14000ac02  cmp     [rcx+4], eax
0x14000ac05  jbe     short loc_14000AC0F
0x14000ac07  mov     eax, [rsi+8]
0x14000ac0a  cmp     [rcx+8], eax
0x14000ac0d  jz      short loc_14000AC4E
0x14000ac0f  add     rcx, rbp
0x14000ac12  jmp     short loc_14000ABFA
0x14000ac14  movzx   eax, word ptr [rbx+22h]
0x14000ac18  xor     edx, edx
0x14000ac1a  movzx   ecx, word ptr [rbx+20h]
0x14000ac1e  inc     eax
0x14000ac20  div     ecx
0x14000ac22  mov     rax, [rbx+8]
0x14000ac26  mov     r8d, 1
0x14000ac2c  mov     [rbx+22h], dx
0x14000ac30  lock xadd [rax], r8d
0x14000ac35  movzx   eax, dx
0x14000ac38  inc     r8d; unsigned int
0x14000ac3b  mov     rdx, rsi; struct wil::FailureInfo *
0x14000ac3e  lea     rcx, [rax+rax*4]
0x14000ac42  shl     rcx, 4
0x14000ac46  add     rcx, r9; this
0x14000ac49  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x14000ac4e  add     rsp, 28h
0x14000ac52  pop     rdi
0x14000ac53  pop     rsi
0x14000ac54  pop     rbp
0x14000ac55  pop     rbx
0x14000ac56  retn
```
