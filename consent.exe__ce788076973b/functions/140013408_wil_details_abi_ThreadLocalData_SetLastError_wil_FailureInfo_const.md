# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x140013408`
- end: `0x1400134d7`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140011d60`

## callees

- `0x14000f32c`
- `0x140013070`
- `0x140013408`

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
0x140013408  push    rbx
0x14001340a  push    rbp
0x14001340b  push    rsi
0x14001340c  push    rdi
0x14001340d  sub     rsp, 28h
0x140013411  cmp     qword ptr [rcx+18h], 0
0x140013416  mov     rsi, rdx
0x140013419  mov     edi, [rcx+10h]
0x14001341c  mov     rbx, rcx
0x14001341f  mov     ebp, 50h ; 'P'
0x140013424  jnz     short loc_14001345B
0x140013426  test    edi, edi
0x140013428  jz      short loc_14001345B
0x14001342a  mov     edx, 190h; dwBytes
0x14001342f  lea     ecx, [rbp-48h]; dwFlags
0x140013432  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140013437  mov     [rbx+18h], rax
0x14001343b  test    rax, rax
0x14001343e  jz      short loc_14001345B
0x140013440  mov     dword ptr [rbx+20h], 5
0x140013447  lea     rcx, [rax+190h]
0x14001344e  jmp     short loc_140013456
0x140013450  mov     [rax], bp
0x140013453  add     rax, rbp
0x140013456  cmp     rax, rcx
0x140013459  jnz     short loc_140013450
0x14001345b  mov     r9, [rbx+18h]
0x14001345f  test    r9, r9
0x140013462  jz      short loc_1400134CE
0x140013464  test    edi, edi
0x140013466  jz      short loc_140013494
0x140013468  movzx   eax, word ptr [rbx+20h]
0x14001346c  mov     rcx, r9
0x14001346f  lea     rdx, [rax+rax*4]
0x140013473  shl     rdx, 4
0x140013477  add     rdx, r9
0x14001347a  cmp     rcx, rdx
0x14001347d  jz      short loc_140013494
0x14001347f  mov     eax, [rbx+10h]
0x140013482  cmp     [rcx+4], eax
0x140013485  jbe     short loc_14001348F
0x140013487  mov     eax, [rsi+8]
0x14001348a  cmp     [rcx+8], eax
0x14001348d  jz      short loc_1400134CE
0x14001348f  add     rcx, rbp
0x140013492  jmp     short loc_14001347A
0x140013494  movzx   eax, word ptr [rbx+22h]
0x140013498  xor     edx, edx
0x14001349a  movzx   ecx, word ptr [rbx+20h]
0x14001349e  inc     eax
0x1400134a0  div     ecx
0x1400134a2  mov     rax, [rbx+8]
0x1400134a6  mov     r8d, 1
0x1400134ac  mov     [rbx+22h], dx
0x1400134b0  lock xadd [rax], r8d
0x1400134b5  movzx   eax, dx
0x1400134b8  inc     r8d; unsigned int
0x1400134bb  mov     rdx, rsi; struct wil::FailureInfo *
0x1400134be  lea     rcx, [rax+rax*4]
0x1400134c2  shl     rcx, 4
0x1400134c6  add     rcx, r9; this
0x1400134c9  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1400134ce  add     rsp, 28h
0x1400134d2  pop     rdi
0x1400134d3  pop     rsi
0x1400134d4  pop     rbp
0x1400134d5  pop     rbx
0x1400134d6  retn
```
