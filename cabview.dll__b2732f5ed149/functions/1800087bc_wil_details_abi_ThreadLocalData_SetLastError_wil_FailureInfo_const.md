# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x1800087bc`
- end: `0x180008892`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `214`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005be0`

## callees

- `0x180007460`
- `0x180008594`
- `0x1800087bc`

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
0x1800087bc  mov     [rsp+arg_10], rbx
0x1800087c1  push    rbp
0x1800087c2  push    rsi
0x1800087c3  push    rdi
0x1800087c4  sub     rsp, 20h
0x1800087c8  cmp     qword ptr [rcx+18h], 0
0x1800087cd  mov     rsi, rdx
0x1800087d0  mov     edi, [rcx+10h]
0x1800087d3  mov     rbx, rcx
0x1800087d6  mov     ebp, 50h ; 'P'
0x1800087db  jnz     short loc_180008812
0x1800087dd  test    edi, edi
0x1800087df  jz      short loc_180008812
0x1800087e1  mov     edx, 190h; dwBytes
0x1800087e6  lea     ecx, [rbp-48h]; dwFlags
0x1800087e9  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800087ee  mov     [rbx+18h], rax
0x1800087f2  test    rax, rax
0x1800087f5  jz      short loc_180008812
0x1800087f7  mov     dword ptr [rbx+20h], 5
0x1800087fe  lea     rcx, [rax+190h]
0x180008805  jmp     short loc_18000880D
0x180008807  mov     [rax], bp
0x18000880a  add     rax, rbp
0x18000880d  cmp     rax, rcx
0x180008810  jnz     short loc_180008807
0x180008812  mov     r9, [rbx+18h]
0x180008816  test    r9, r9
0x180008819  jz      short loc_180008885
0x18000881b  test    edi, edi
0x18000881d  jz      short loc_18000884B
0x18000881f  movzx   eax, word ptr [rbx+20h]
0x180008823  mov     rcx, r9
0x180008826  lea     rdx, [rax+rax*4]
0x18000882a  shl     rdx, 4
0x18000882e  add     rdx, r9
0x180008831  cmp     rcx, rdx
0x180008834  jz      short loc_18000884B
0x180008836  mov     eax, [rbx+10h]
0x180008839  cmp     [rcx+4], eax
0x18000883c  jbe     short loc_180008846
0x18000883e  mov     eax, [rsi+8]
0x180008841  cmp     [rcx+8], eax
0x180008844  jz      short loc_180008885
0x180008846  add     rcx, rbp
0x180008849  jmp     short loc_180008831
0x18000884b  movzx   eax, word ptr [rbx+22h]
0x18000884f  xor     edx, edx
0x180008851  movzx   ecx, word ptr [rbx+20h]
0x180008855  inc     eax
0x180008857  div     ecx
0x180008859  mov     rax, [rbx+8]
0x18000885d  mov     r8d, 1
0x180008863  mov     [rbx+22h], dx
0x180008867  lock xadd [rax], r8d
0x18000886c  movzx   eax, dx
0x18000886f  inc     r8d; unsigned int
0x180008872  mov     rdx, rsi; struct wil::FailureInfo *
0x180008875  lea     rcx, [rax+rax*4]
0x180008879  shl     rcx, 4
0x18000887d  add     rcx, r9; this
0x180008880  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180008885  mov     rbx, [rsp+38h+arg_10]
0x18000888a  add     rsp, 20h
0x18000888e  pop     rdi
0x18000888f  pop     rsi
0x180008890  pop     rbp
0x180008891  retn
```
