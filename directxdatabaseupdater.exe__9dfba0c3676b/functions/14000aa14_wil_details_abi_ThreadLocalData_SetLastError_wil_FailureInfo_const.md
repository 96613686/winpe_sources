# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x14000aa14`
- end: `0x14000aae3`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `207`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140007170`

## callees

- `0x140009340`
- `0x14000a590`
- `0x14000aa14`

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
0x14000aa14  push    rbx
0x14000aa16  push    rbp
0x14000aa17  push    rsi
0x14000aa18  push    rdi
0x14000aa19  sub     rsp, 28h
0x14000aa1d  cmp     qword ptr [rcx+18h], 0
0x14000aa22  mov     rsi, rdx
0x14000aa25  mov     edi, [rcx+10h]
0x14000aa28  mov     rbx, rcx
0x14000aa2b  mov     ebp, 50h ; 'P'
0x14000aa30  jnz     short loc_14000AA67
0x14000aa32  test    edi, edi
0x14000aa34  jz      short loc_14000AA67
0x14000aa36  mov     edx, 190h; dwBytes
0x14000aa3b  lea     ecx, [rbp-48h]; dwFlags
0x14000aa3e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x14000aa43  mov     [rbx+18h], rax
0x14000aa47  test    rax, rax
0x14000aa4a  jz      short loc_14000AA67
0x14000aa4c  mov     dword ptr [rbx+20h], 5
0x14000aa53  lea     rcx, [rax+190h]
0x14000aa5a  jmp     short loc_14000AA62
0x14000aa5c  mov     [rax], bp
0x14000aa5f  add     rax, rbp
0x14000aa62  cmp     rax, rcx
0x14000aa65  jnz     short loc_14000AA5C
0x14000aa67  mov     r9, [rbx+18h]
0x14000aa6b  test    r9, r9
0x14000aa6e  jz      short loc_14000AADA
0x14000aa70  test    edi, edi
0x14000aa72  jz      short loc_14000AAA0
0x14000aa74  movzx   eax, word ptr [rbx+20h]
0x14000aa78  mov     rcx, r9
0x14000aa7b  lea     rdx, [rax+rax*4]
0x14000aa7f  shl     rdx, 4
0x14000aa83  add     rdx, r9
0x14000aa86  cmp     rcx, rdx
0x14000aa89  jz      short loc_14000AAA0
0x14000aa8b  mov     eax, [rbx+10h]
0x14000aa8e  cmp     [rcx+4], eax
0x14000aa91  jbe     short loc_14000AA9B
0x14000aa93  mov     eax, [rsi+8]
0x14000aa96  cmp     [rcx+8], eax
0x14000aa99  jz      short loc_14000AADA
0x14000aa9b  add     rcx, rbp
0x14000aa9e  jmp     short loc_14000AA86
0x14000aaa0  movzx   eax, word ptr [rbx+22h]
0x14000aaa4  xor     edx, edx
0x14000aaa6  movzx   ecx, word ptr [rbx+20h]
0x14000aaaa  inc     eax
0x14000aaac  div     ecx
0x14000aaae  mov     rax, [rbx+8]
0x14000aab2  mov     r8d, 1
0x14000aab8  mov     [rbx+22h], dx
0x14000aabc  lock xadd [rax], r8d
0x14000aac1  movzx   eax, dx
0x14000aac4  inc     r8d; unsigned int
0x14000aac7  mov     rdx, rsi; struct wil::FailureInfo *
0x14000aaca  lea     rcx, [rax+rax*4]
0x14000aace  shl     rcx, 4
0x14000aad2  add     rcx, r9; this
0x14000aad5  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x14000aada  add     rsp, 28h
0x14000aade  pop     rdi
0x14000aadf  pop     rsi
0x14000aae0  pop     rbp
0x14000aae1  pop     rbx
0x14000aae2  retn
```
