# Common::StringBuffer::SetCapacity(ulong)

- ea: `0x1800029c0`
- end: `0x180002abb`
- name: `?SetCapacity@StringBuffer@Common@@QEAAJK@Z`
- size: `251`
- prototype: `__int64 __fastcall(Common::StringBuffer *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180001ef0`
- `0x1800020d0`
- `0x180002850`

## callees

- `0x1800029c0`
- `0x180002ad0`
- `0x180002af0`
- `0x1800058d0`

## string_xrefs

- `0x180002a59`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180002a7f`: `onecore\base\appmodel\common\widestring.cpp`

## pseudocode

```c
__int64 __fastcall Common::StringBuffer::SetCapacity(Common::StringBuffer *this, unsigned int a2)
{
  int v2; // r14d
  __int64 v3; // rbx
  unsigned int v5; // eax
  unsigned int v6; // esi
  void *v7; // rcx
  int v8; // eax
  unsigned int v9; // ebp
  _WORD *v10; // rcx
  unsigned int v11; // eax
  void *v13; // rcx
  int v14; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  void *v16; // [rsp+50h] [rbp+18h] BYREF

  v3 = a2;
  if ( a2 > 0x3FFFFFFF )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A9,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)0x80070503LL,
      v14);
    return 2147943683LL;
  }
  else
  {
    if ( !a2 )
    {
      v13 = (void *)*((_QWORD *)this + 1);
      if ( v13 )
      {
        Common::GlobalHeap::Free(v13);
        *((_QWORD *)this + 1) = 0;
        *(_DWORD *)this = 0;
      }
      *((_DWORD *)this + 4) = 0;
      return 0;
    }
    v5 = *((_DWORD *)this + 4);
    v6 = a2 + 1;
    if ( a2 + 1 == v5 )
      return 0;
    v7 = (void *)*((_QWORD *)this + 1);
    v16 = 0;
    v8 = CommonHeapReAllocDefault(v7, 2LL * v5, 2LL * v6, &v16);
    v9 = v8;
    if ( v8 >= 0 )
    {
      v10 = v16;
      v11 = *(_DWORD *)this;
      *((_QWORD *)this + 1) = v16;
      *((_DWORD *)this + 4) = v6;
      if ( v11 > (unsigned int)v3 )
      {
        *(_DWORD *)this = v3;
        v10[v3] = 0;
      }
      else if ( v11 < (unsigned int)v3 && !v11 )
      {
        *v10 = 0;
      }
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CA,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)(unsigned int)v8,
      v2);
    return v9;
  }
}

```

## disassembly

```asm
0x1800029c0  push    rbx
0x1800029c2  push    rdi
0x1800029c3  sub     rsp, 28h
0x1800029c7  mov     ebx, edx
0x1800029c9  mov     rdi, rcx
0x1800029cc  cmp     edx, 3FFFFFFFh
0x1800029d2  ja      loc_180002A7A
0x1800029d8  mov     [rsp+38h+arg_0], rbp
0x1800029dd  mov     [rsp+38h+arg_8], rsi
0x1800029e2  mov     qword ptr [rsp+38h+var_18], r14; int
0x1800029e7  test    edx, edx
0x1800029e9  jz      loc_180002A9D
0x1800029ef  mov     eax, [rcx+10h]
0x1800029f2  lea     esi, [rbx+1]
0x1800029f5  cmp     esi, eax
0x1800029f7  jz      short loc_180002A3C
0x1800029f9  mov     rcx, [rcx+8]; void *
0x1800029fd  lea     r9, [rsp+38h+arg_10]; void **
0x180002a02  mov     edx, eax
0x180002a04  mov     r8d, esi
0x180002a07  xor     r14d, r14d
0x180002a0a  add     r8, r8; unsigned __int64
0x180002a0d  add     rdx, rdx; unsigned __int64
0x180002a10  mov     [rsp+38h+arg_10], r14
0x180002a15  call    ?CommonHeapReAllocDefault@@YAJPEAX_K1PEAPEAX@Z; CommonHeapReAllocDefault(void *,unsigned __int64,unsigned __int64,void * *)
0x180002a1a  mov     ebp, eax
0x180002a1c  test    eax, eax
0x180002a1e  js      short loc_180002A54
0x180002a20  mov     rcx, [rsp+38h+arg_10]
0x180002a25  mov     eax, [rdi]
0x180002a27  mov     [rdi+8], rcx
0x180002a2b  mov     [rdi+10h], esi
0x180002a2e  cmp     eax, ebx
0x180002a30  ja      short loc_180002A71
0x180002a32  jnb     short loc_180002A3C
0x180002a34  test    eax, eax
0x180002a36  jnz     short loc_180002A3C
0x180002a38  mov     [rcx], r14w
0x180002a3c  xor     eax, eax
0x180002a3e  mov     rsi, [rsp+38h+arg_8]
0x180002a43  mov     rbp, [rsp+38h+arg_0]
0x180002a48  mov     r14, qword ptr [rsp+38h+var_18]
0x180002a4d  add     rsp, 28h
0x180002a51  pop     rdi
0x180002a52  pop     rbx
0x180002a53  retn
0x180002a54  mov     rcx, [rsp+38h]; this
0x180002a59  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\widest"...
0x180002a60  mov     r9d, ebp; char *
0x180002a63  mov     edx, 1CAh; void *
0x180002a68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002a6d  mov     eax, ebp
0x180002a6f  jmp     short loc_180002A3E
0x180002a71  mov     [rdi], ebx
0x180002a73  mov     [rcx+rbx*2], r14w
0x180002a78  jmp     short loc_180002A3C
0x180002a7a  mov     rcx, [rsp+38h]; this
0x180002a7f  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\widest"...
0x180002a86  mov     r9d, 80070503h; char *
0x180002a8c  mov     edx, 1A9h; void *
0x180002a91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002a96  mov     eax, 80070503h
0x180002a9b  jmp     short loc_180002A4D
0x180002a9d  mov     rcx, [rcx+8]; void *
0x180002aa1  xor     r14d, r14d
0x180002aa4  test    rcx, rcx
0x180002aa7  jz      short loc_180002AB5
0x180002aa9  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180002aae  mov     [rdi+8], r14
0x180002ab2  mov     [rdi], r14d
0x180002ab5  mov     [rdi+10h], r14d
0x180002ab9  jmp     short loc_180002A3C
```
