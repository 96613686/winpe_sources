# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180009124`
- end: `0x1800091fa`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `214`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006ca0`

## callees

- `0x18000816c`
- `0x180008ca0`
- `0x180009124`

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
0x180009124  mov     [rsp+arg_10], rbx
0x180009129  push    rbp
0x18000912a  push    rsi
0x18000912b  push    rdi
0x18000912c  sub     rsp, 20h
0x180009130  cmp     qword ptr [rcx+18h], 0
0x180009135  mov     rsi, rdx
0x180009138  mov     edi, [rcx+10h]
0x18000913b  mov     rbx, rcx
0x18000913e  mov     ebp, 50h ; 'P'
0x180009143  jnz     short loc_18000917A
0x180009145  test    edi, edi
0x180009147  jz      short loc_18000917A
0x180009149  mov     edx, 190h; dwBytes
0x18000914e  lea     ecx, [rbp-48h]; dwFlags
0x180009151  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009156  mov     [rbx+18h], rax
0x18000915a  test    rax, rax
0x18000915d  jz      short loc_18000917A
0x18000915f  mov     dword ptr [rbx+20h], 5
0x180009166  lea     rcx, [rax+190h]
0x18000916d  jmp     short loc_180009175
0x18000916f  mov     [rax], bp
0x180009172  add     rax, rbp
0x180009175  cmp     rax, rcx
0x180009178  jnz     short loc_18000916F
0x18000917a  mov     r9, [rbx+18h]
0x18000917e  test    r9, r9
0x180009181  jz      short loc_1800091ED
0x180009183  test    edi, edi
0x180009185  jz      short loc_1800091B3
0x180009187  movzx   eax, word ptr [rbx+20h]
0x18000918b  mov     rcx, r9
0x18000918e  lea     rdx, [rax+rax*4]
0x180009192  shl     rdx, 4
0x180009196  add     rdx, r9
0x180009199  cmp     rcx, rdx
0x18000919c  jz      short loc_1800091B3
0x18000919e  mov     eax, [rbx+10h]
0x1800091a1  cmp     [rcx+4], eax
0x1800091a4  jbe     short loc_1800091AE
0x1800091a6  mov     eax, [rsi+8]
0x1800091a9  cmp     [rcx+8], eax
0x1800091ac  jz      short loc_1800091ED
0x1800091ae  add     rcx, rbp
0x1800091b1  jmp     short loc_180009199
0x1800091b3  movzx   eax, word ptr [rbx+22h]
0x1800091b7  xor     edx, edx
0x1800091b9  movzx   ecx, word ptr [rbx+20h]
0x1800091bd  inc     eax
0x1800091bf  div     ecx
0x1800091c1  mov     rax, [rbx+8]
0x1800091c5  mov     r8d, 1
0x1800091cb  mov     [rbx+22h], dx
0x1800091cf  lock xadd [rax], r8d
0x1800091d4  movzx   eax, dx
0x1800091d7  inc     r8d; unsigned int
0x1800091da  mov     rdx, rsi; struct wil::FailureInfo *
0x1800091dd  lea     rcx, [rax+rax*4]
0x1800091e1  shl     rcx, 4
0x1800091e5  add     rcx, r9; this
0x1800091e8  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800091ed  mov     rbx, [rsp+38h+arg_10]
0x1800091f2  add     rsp, 20h
0x1800091f6  pop     rdi
0x1800091f7  pop     rsi
0x1800091f8  pop     rbp
0x1800091f9  retn
```
