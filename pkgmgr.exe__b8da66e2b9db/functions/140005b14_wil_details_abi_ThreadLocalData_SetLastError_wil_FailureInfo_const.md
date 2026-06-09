# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x140005b14`
- end: `0x140005bea`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `214`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400044b0`

## callees

- `0x1400054b0`
- `0x14000577c`
- `0x140005b14`

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
0x140005b14  mov     [rsp+arg_10], rbx
0x140005b19  push    rbp
0x140005b1a  push    rsi
0x140005b1b  push    rdi
0x140005b1c  sub     rsp, 20h
0x140005b20  cmp     qword ptr [rcx+18h], 0
0x140005b25  mov     rsi, rdx
0x140005b28  mov     edi, [rcx+10h]
0x140005b2b  mov     rbx, rcx
0x140005b2e  mov     ebp, 50h ; 'P'
0x140005b33  jnz     short loc_140005B6A
0x140005b35  test    edi, edi
0x140005b37  jz      short loc_140005B6A
0x140005b39  mov     edx, 190h; dwBytes
0x140005b3e  lea     ecx, [rbp-48h]; dwFlags
0x140005b41  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140005b46  mov     [rbx+18h], rax
0x140005b4a  test    rax, rax
0x140005b4d  jz      short loc_140005B6A
0x140005b4f  mov     dword ptr [rbx+20h], 5
0x140005b56  lea     rcx, [rax+190h]
0x140005b5d  jmp     short loc_140005B65
0x140005b5f  mov     [rax], bp
0x140005b62  add     rax, rbp
0x140005b65  cmp     rax, rcx
0x140005b68  jnz     short loc_140005B5F
0x140005b6a  mov     r9, [rbx+18h]
0x140005b6e  test    r9, r9
0x140005b71  jz      short loc_140005BDD
0x140005b73  test    edi, edi
0x140005b75  jz      short loc_140005BA3
0x140005b77  movzx   eax, word ptr [rbx+20h]
0x140005b7b  mov     rcx, r9
0x140005b7e  lea     rdx, [rax+rax*4]
0x140005b82  shl     rdx, 4
0x140005b86  add     rdx, r9
0x140005b89  cmp     rcx, rdx
0x140005b8c  jz      short loc_140005BA3
0x140005b8e  mov     eax, [rbx+10h]
0x140005b91  cmp     [rcx+4], eax
0x140005b94  jbe     short loc_140005B9E
0x140005b96  mov     eax, [rsi+8]
0x140005b99  cmp     [rcx+8], eax
0x140005b9c  jz      short loc_140005BDD
0x140005b9e  add     rcx, rbp
0x140005ba1  jmp     short loc_140005B89
0x140005ba3  movzx   eax, word ptr [rbx+22h]
0x140005ba7  xor     edx, edx
0x140005ba9  movzx   ecx, word ptr [rbx+20h]
0x140005bad  inc     eax
0x140005baf  div     ecx
0x140005bb1  mov     rax, [rbx+8]
0x140005bb5  mov     r8d, 1
0x140005bbb  mov     [rbx+22h], dx
0x140005bbf  lock xadd [rax], r8d
0x140005bc4  movzx   eax, dx
0x140005bc7  inc     r8d; unsigned int
0x140005bca  mov     rdx, rsi; struct wil::FailureInfo *
0x140005bcd  lea     rcx, [rax+rax*4]
0x140005bd1  shl     rcx, 4
0x140005bd5  add     rcx, r9; this
0x140005bd8  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x140005bdd  mov     rbx, [rsp+38h+arg_10]
0x140005be2  add     rsp, 20h
0x140005be6  pop     rdi
0x140005be7  pop     rsi
0x140005be8  pop     rbp
0x140005be9  retn
```
