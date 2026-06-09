# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180013fb8`
- end: `0x180014087`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800117d0`

## callees

- `0x180012ef4`
- `0x180013d54`
- `0x180013fb8`

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
0x180013fb8  push    rbx
0x180013fba  push    rbp
0x180013fbb  push    rsi
0x180013fbc  push    rdi
0x180013fbd  sub     rsp, 28h
0x180013fc1  cmp     qword ptr [rcx+18h], 0
0x180013fc6  mov     rsi, rdx
0x180013fc9  mov     edi, [rcx+10h]
0x180013fcc  mov     rbx, rcx
0x180013fcf  mov     ebp, 50h ; 'P'
0x180013fd4  jnz     short loc_18001400B
0x180013fd6  test    edi, edi
0x180013fd8  jz      short loc_18001400B
0x180013fda  mov     edx, 190h; dwBytes
0x180013fdf  lea     ecx, [rbp-48h]; dwFlags
0x180013fe2  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180013fe7  mov     [rbx+18h], rax
0x180013feb  test    rax, rax
0x180013fee  jz      short loc_18001400B
0x180013ff0  mov     dword ptr [rbx+20h], 5
0x180013ff7  lea     rcx, [rax+190h]
0x180013ffe  jmp     short loc_180014006
0x180014000  mov     [rax], bp
0x180014003  add     rax, rbp
0x180014006  cmp     rax, rcx
0x180014009  jnz     short loc_180014000
0x18001400b  mov     r9, [rbx+18h]
0x18001400f  test    r9, r9
0x180014012  jz      short loc_18001407E
0x180014014  test    edi, edi
0x180014016  jz      short loc_180014044
0x180014018  movzx   eax, word ptr [rbx+20h]
0x18001401c  mov     rcx, r9
0x18001401f  lea     rdx, [rax+rax*4]
0x180014023  shl     rdx, 4
0x180014027  add     rdx, r9
0x18001402a  cmp     rcx, rdx
0x18001402d  jz      short loc_180014044
0x18001402f  mov     eax, [rbx+10h]
0x180014032  cmp     [rcx+4], eax
0x180014035  jbe     short loc_18001403F
0x180014037  mov     eax, [rsi+8]
0x18001403a  cmp     [rcx+8], eax
0x18001403d  jz      short loc_18001407E
0x18001403f  add     rcx, rbp
0x180014042  jmp     short loc_18001402A
0x180014044  movzx   eax, word ptr [rbx+22h]
0x180014048  xor     edx, edx
0x18001404a  movzx   ecx, word ptr [rbx+20h]
0x18001404e  inc     eax
0x180014050  div     ecx
0x180014052  mov     rax, [rbx+8]
0x180014056  mov     r8d, 1
0x18001405c  mov     [rbx+22h], dx
0x180014060  lock xadd [rax], r8d
0x180014065  movzx   eax, dx
0x180014068  inc     r8d; unsigned int
0x18001406b  mov     rdx, rsi; struct wil::FailureInfo *
0x18001406e  lea     rcx, [rax+rax*4]
0x180014072  shl     rcx, 4
0x180014076  add     rcx, r9; this
0x180014079  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x18001407e  add     rsp, 28h
0x180014082  pop     rdi
0x180014083  pop     rsi
0x180014084  pop     rbp
0x180014085  pop     rbx
0x180014086  retn
```
