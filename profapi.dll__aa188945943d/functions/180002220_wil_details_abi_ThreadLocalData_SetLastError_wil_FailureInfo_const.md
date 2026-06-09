# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180002220`
- end: `0x1800022c5`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `165`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *, unsigned __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001fe0`

## callees

- `0x180002220`
- `0x1800022cc`
- `0x1800114c0`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::SetLastError(
        wil::details_abi::ThreadLocalData *this,
        const struct wil::FailureInfo *a2,
        unsigned __int64 a3)
{
  int v3; // edi
  __int64 v6; // rcx
  __int64 v7; // rdx
  unsigned __int16 v8; // dx

  v3 = *((_DWORD *)this + 4);
  if ( wil::details_abi::ThreadLocalData::EnsureAllocated(this, v3 != 0, a3) )
  {
    if ( v3 )
    {
      v6 = *((_QWORD *)this + 3);
      v7 = v6 + 80LL * *((unsigned __int16 *)this + 16);
      while ( v6 != v7 )
      {
        if ( *(_DWORD *)(v6 + 4) > *((_DWORD *)this + 4) && *(_DWORD *)(v6 + 8) == *((_DWORD *)a2 + 2) )
          return;
        v6 += 80;
      }
    }
    v8 = ((unsigned int)*((unsigned __int16 *)this + 17) + 1) % *((unsigned __int16 *)this + 16);
    *((_WORD *)this + 17) = v8;
    wil::details_abi::ThreadLocalFailureInfo::Set(
      (wil::details_abi::ThreadLocalFailureInfo *)(*((_QWORD *)this + 3) + 80LL * v8),
      a2,
      _InterlockedIncrement(*((volatile signed __int32 **)this + 1)));
  }
}

```

## disassembly

```asm
0x180002220  mov     [rsp+arg_0], rbx
0x180002225  mov     [rsp+arg_8], rsi
0x18000222a  push    rdi
0x18000222b  sub     rsp, 20h
0x18000222f  mov     edi, [rcx+10h]
0x180002232  mov     rsi, rdx
0x180002235  test    edi, edi
0x180002237  mov     rbx, rcx
0x18000223a  setnz   dl; bool
0x18000223d  call    ?EnsureAllocated@ThreadLocalData@details_abi@wil@@QEAA_N_N@Z; wil::details_abi::ThreadLocalData::EnsureAllocated(bool)
0x180002242  test    al, al
0x180002244  jnz     short loc_180002256
0x180002246  mov     rbx, [rsp+28h+arg_0]
0x18000224b  mov     rsi, [rsp+28h+arg_8]
0x180002250  add     rsp, 20h
0x180002254  pop     rdi
0x180002255  retn
0x180002256  test    edi, edi
0x180002258  jz      short loc_180002288
0x18000225a  movzx   eax, word ptr [rbx+20h]
0x18000225e  mov     rcx, [rbx+18h]
0x180002262  lea     rdx, [rax+rax*4]
0x180002266  shl     rdx, 4
0x18000226a  add     rdx, rcx
0x18000226d  cmp     rcx, rdx
0x180002270  jz      short loc_180002288
0x180002272  mov     eax, [rbx+10h]
0x180002275  cmp     [rcx+4], eax
0x180002278  jbe     short loc_180002282
0x18000227a  mov     eax, [rsi+8]
0x18000227d  cmp     [rcx+8], eax
0x180002280  jz      short loc_180002246
0x180002282  add     rcx, 50h ; 'P'
0x180002286  jmp     short loc_18000226D
0x180002288  movzx   eax, word ptr [rbx+22h]
0x18000228c  xor     edx, edx
0x18000228e  movzx   ecx, word ptr [rbx+20h]
0x180002292  inc     eax
0x180002294  div     ecx
0x180002296  mov     r8d, 1
0x18000229c  movzx   eax, dx
0x18000229f  mov     [rbx+22h], dx
0x1800022a3  lea     rcx, [rax+rax*4]
0x1800022a7  mov     rax, [rbx+8]
0x1800022ab  shl     rcx, 4
0x1800022af  add     rcx, [rbx+18h]; this
0x1800022b3  lock xadd [rax], r8d
0x1800022b8  inc     r8d; unsigned int
0x1800022bb  mov     rdx, rsi; struct wil::FailureInfo *
0x1800022be  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800022c3  jmp     short loc_180002246
```
