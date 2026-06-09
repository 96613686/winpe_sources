# wil::details_abi::ThreadLocalData::SetLastError(wil::FailureInfo const &)

- ea: `0x1800050c0`
- end: `0x1800051a9`
- name: `?SetLastError@ThreadLocalData@details_abi@wil@@QEAAXAEBUFailureInfo@3@@Z`
- size: `233`
- prototype: `void(wil::details_abi::ThreadLocalData *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003b70`

## callees

- `0x1800032bc`
- `0x180004b28`
- `0x180004ea0`
- `0x1800050c0`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::SetLastError(
        wil::details_abi::ThreadLocalData *this,
        const struct wil::FailureInfo *a2)
{
  int v3; // edi
  LPVOID v5; // rax
  _WORD *i; // rcx
  __int64 v7; // r9
  _WORD *v8; // rcx
  unsigned __int16 v9; // dx
  volatile signed __int32 *v10; // rax
  _WORD *v11; // [rsp+20h] [rbp-38h] BYREF
  _WORD *v12; // [rsp+28h] [rbp-30h]

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
        wil::make_range<wil::details_abi::ThreadLocalFailureInfo *>(&v11, v5);
        for ( i = v11; i != v12; i += 40 )
          *i = 80;
      }
    }
  }
  v7 = *((_QWORD *)this + 3);
  if ( v7 )
  {
    if ( !v3
      || (wil::make_range<wil::details_abi::ThreadLocalFailureInfo *>(&v11, *((_QWORD *)this + 3)), v8 = v11, v11 == v12) )
    {
LABEL_13:
      v9 = ((unsigned int)*((unsigned __int16 *)this + 17) + 1) % *((unsigned __int16 *)this + 16);
      v10 = (volatile signed __int32 *)*((_QWORD *)this + 1);
      *((_WORD *)this + 17) = v9;
      wil::details_abi::ThreadLocalFailureInfo::Set(
        (wil::details_abi::ThreadLocalFailureInfo *)(v7 + 80LL * v9),
        a2,
        _InterlockedIncrement(v10));
    }
    else
    {
      while ( *((_DWORD *)v8 + 1) <= *((_DWORD *)this + 4) || *((_DWORD *)v8 + 2) != *((_DWORD *)a2 + 2) )
      {
        v8 += 40;
        if ( v8 == v12 )
          goto LABEL_13;
      }
    }
  }
}

```

## disassembly

```asm
0x1800050c0  push    rbx
0x1800050c2  push    rbp
0x1800050c3  push    rsi
0x1800050c4  push    rdi
0x1800050c5  sub     rsp, 38h
0x1800050c9  cmp     qword ptr [rcx+18h], 0
0x1800050ce  mov     rsi, rdx
0x1800050d1  mov     edi, [rcx+10h]
0x1800050d4  mov     rbx, rcx
0x1800050d7  mov     ebp, 50h ; 'P'
0x1800050dc  jnz     short loc_180005121
0x1800050de  test    edi, edi
0x1800050e0  jz      short loc_180005121
0x1800050e2  mov     edx, 190h; dwBytes
0x1800050e7  lea     ecx, [rbp-48h]; dwFlags
0x1800050ea  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800050ef  mov     [rbx+18h], rax
0x1800050f3  test    rax, rax
0x1800050f6  jz      short loc_180005121
0x1800050f8  lea     r8d, [rbp-4Bh]
0x1800050fc  mov     rdx, rax
0x1800050ff  lea     rcx, [rsp+58h+var_38]
0x180005104  mov     [rbx+20h], r8d
0x180005108  call    ??$make_range@PEAUThreadLocalFailureInfo@details_abi@wil@@@wil@@YA?AV?$pointer_range@PEAUThreadLocalFailureInfo@details_abi@wil@@@details@0@PEAUThreadLocalFailureInfo@details_abi@0@_K@Z; wil::make_range<wil::details_abi::ThreadLocalFailureInfo *>(wil::details_abi::ThreadLocalFailureInfo *,unsigned __int64)
0x18000510d  mov     rcx, [rsp+58h+var_38]
0x180005112  jmp     short loc_18000511A
0x180005114  mov     [rcx], bp
0x180005117  add     rcx, rbp
0x18000511a  cmp     rcx, [rsp+58h+var_30]
0x18000511f  jnz     short loc_180005114
0x180005121  mov     r9, [rbx+18h]
0x180005125  test    r9, r9
0x180005128  jz      short loc_1800051A0
0x18000512a  test    edi, edi
0x18000512c  jz      short loc_180005166
0x18000512e  movzx   r8d, word ptr [rbx+20h]
0x180005133  lea     rcx, [rsp+58h+var_38]
0x180005138  mov     rdx, r9
0x18000513b  call    ??$make_range@PEAUThreadLocalFailureInfo@details_abi@wil@@@wil@@YA?AV?$pointer_range@PEAUThreadLocalFailureInfo@details_abi@wil@@@details@0@PEAUThreadLocalFailureInfo@details_abi@0@_K@Z; wil::make_range<wil::details_abi::ThreadLocalFailureInfo *>(wil::details_abi::ThreadLocalFailureInfo *,unsigned __int64)
0x180005140  mov     rcx, [rsp+58h+var_38]
0x180005145  cmp     rcx, [rsp+58h+var_30]
0x18000514a  jz      short loc_180005166
0x18000514c  mov     edx, [rbx+10h]
0x18000514f  cmp     [rcx+4], edx
0x180005152  jbe     short loc_18000515C
0x180005154  mov     eax, [rsi+8]
0x180005157  cmp     [rcx+8], eax
0x18000515a  jz      short loc_1800051A0
0x18000515c  add     rcx, rbp
0x18000515f  cmp     rcx, [rsp+58h+var_30]
0x180005164  jnz     short loc_18000514F
0x180005166  movzx   eax, word ptr [rbx+22h]
0x18000516a  xor     edx, edx
0x18000516c  movzx   ecx, word ptr [rbx+20h]
0x180005170  inc     eax
0x180005172  div     ecx
0x180005174  mov     rax, [rbx+8]
0x180005178  mov     r8d, 1
0x18000517e  mov     [rbx+22h], dx
0x180005182  lock xadd [rax], r8d
0x180005187  movzx   eax, dx
0x18000518a  inc     r8d; unsigned int
0x18000518d  mov     rdx, rsi; struct wil::FailureInfo *
0x180005190  lea     rcx, [rax+rax*4]
0x180005194  shl     rcx, 4
0x180005198  add     rcx, r9; this
0x18000519b  call    ?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z; wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)
0x1800051a0  add     rsp, 38h
0x1800051a4  pop     rdi
0x1800051a5  pop     rsi
0x1800051a6  pop     rbp
0x1800051a7  pop     rbx
0x1800051a8  retn
```
