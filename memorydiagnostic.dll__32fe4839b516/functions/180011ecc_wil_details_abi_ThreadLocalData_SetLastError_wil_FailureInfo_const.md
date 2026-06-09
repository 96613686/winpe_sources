# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x180011ecc`
- end: `0x180011fc8`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `252`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d070`

## callees

- `0x18000efd0`
- `0x180011660`
- `0x180011ecc`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::SetLastError(
        wil::details_abi::ThreadLocalData *this,
        const struct wil::FailureInfo *a2)
{
  int v2; // edi
  _WORD *v5; // rax
  _WORD *v6; // rcx
  _DWORD *v7; // r8
  _DWORD *v8; // rcx
  _DWORD *v9; // rdx
  unsigned __int16 v10; // dx

  v2 = *((_DWORD *)this + 4);
  if ( !*((_QWORD *)this + 3) )
  {
    if ( v2 )
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
  v7 = (_DWORD *)*((_QWORD *)this + 3);
  if ( v7 )
  {
    if ( !v2 || (v8 = &v7[20 * *((unsigned __int16 *)this + 16)], v7 == v8) )
    {
LABEL_14:
      v10 = ((unsigned int)*((unsigned __int16 *)this + 17) + 1) % *((unsigned __int16 *)this + 16);
      *((_WORD *)this + 17) = v10;
      wil::details_abi::ThreadLocalFailureInfo::Set(
        (wil::details_abi::ThreadLocalFailureInfo *)&v7[20 * v10],
        a2,
        _InterlockedIncrement(*((volatile signed __int32 **)this + 1)));
    }
    else
    {
      v9 = v7 + 2;
      while ( *(v9 - 1) <= *((_DWORD *)this + 4) || *v9 != *((_DWORD *)a2 + 2) )
      {
        v9 += 20;
        if ( v9 - 2 == v8 )
          goto LABEL_14;
      }
    }
  }
}

```

## disassembly

```asm
0x180011ecc  mov     rax, rsp
0x180011ecf  mov     [rax+8], rbx
0x180011ed3  mov     [rax+10h], rbp
0x180011ed7  mov     [rax+18h], rsi
0x180011edb  mov     [rax+20h], rdi
0x180011edf  push    r14
0x180011ee1  sub     rsp, 20h
0x180011ee5  mov     edi, [rcx+10h]
0x180011ee8  xor     ebp, ebp
0x180011eea  mov     rsi, rdx
0x180011eed  mov     rbx, rcx
0x180011ef0  lea     r14d, [rbp+50h]
0x180011ef4  cmp     [rcx+18h], rbp
0x180011ef8  jnz     short loc_180011F30
0x180011efa  test    edi, edi
0x180011efc  jz      short loc_180011F30
0x180011efe  mov     edx, 190h; dwBytes
0x180011f03  lea     ecx, [rbp+8]; dwFlags
0x180011f06  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180011f0b  mov     [rbx+18h], rax
0x180011f0f  test    rax, rax
0x180011f12  jz      short loc_180011F30
0x180011f14  mov     dword ptr [rbx+20h], 5
0x180011f1b  lea     rcx, [rax+190h]
0x180011f22  jmp     short loc_180011F2B
0x180011f24  mov     [rax], r14w
0x180011f28  add     rax, r14
0x180011f2b  cmp     rax, rcx
0x180011f2e  jnz     short loc_180011F24
0x180011f30  mov     r8, [rbx+18h]
0x180011f34  test    r8, r8
0x180011f37  jz      short loc_180011FAC
0x180011f39  test    edi, edi
0x180011f3b  jz      short loc_180011F72
0x180011f3d  movzx   eax, word ptr [rbx+20h]
0x180011f41  lea     rcx, [rax+rax*4]
0x180011f45  shl     rcx, 4
0x180011f49  add     rcx, r8
0x180011f4c  cmp     r8, rcx
0x180011f4f  jz      short loc_180011F72
0x180011f51  mov     r9d, [rbx+10h]
0x180011f55  lea     rdx, [r8+8]
0x180011f59  cmp     [rdx-4], r9d
0x180011f5d  jbe     short loc_180011F66
0x180011f5f  mov     eax, [rsi+8]
0x180011f62  cmp     [rdx], eax
0x180011f64  jz      short loc_180011FAC
0x180011f66  add     rdx, r14
0x180011f69  lea     rax, [rdx-8]
0x180011f6d  cmp     rax, rcx
0x180011f70  jnz     short loc_180011F59
0x180011f72  movzx   eax, word ptr [rbx+22h]
0x180011f76  xor     edx, edx
0x180011f78  movzx   ecx, word ptr [rbx+20h]
0x180011f7c  inc     eax
0x180011f7e  div     ecx
0x180011f80  movzx   eax, dx
0x180011f83  mov     [rbx+22h], dx
0x180011f87  lea     rcx, [rax+rax*4]
0x180011f8b  mov     rax, [rbx+8]
0x180011f8f  shl     rcx, 4
0x180011f93  add     rcx, r8; this
0x180011f96  mov     r8d, 1
0x180011f9c  lock xadd [rax], r8d
0x180011fa1  inc     r8d; unsigned int
0x180011fa4  mov     rdx, rsi; struct wil::FailureInfo *
0x180011fa7  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x180011fac  mov     rbx, [rsp+28h+arg_0]
0x180011fb1  mov     rbp, [rsp+28h+arg_8]
0x180011fb6  mov     rsi, [rsp+28h+arg_10]
0x180011fbb  mov     rdi, [rsp+28h+arg_18]
0x180011fc0  add     rsp, 20h
0x180011fc4  pop     r14
0x180011fc6  retn
```
