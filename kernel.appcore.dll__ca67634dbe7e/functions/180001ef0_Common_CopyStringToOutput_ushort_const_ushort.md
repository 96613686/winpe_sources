# Common::CopyStringToOutput(ushort const *,ushort * *)

- ea: `0x180001ef0`
- end: `0x1800020bf`
- name: `?CopyStringToOutput@Common@@YAJPEBGPEAPEAG@Z`
- size: `463`
- prototype: `__int64 __fastcall(Common *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800020d0`

## callees

- `0x180001ef0`
- `0x1800029c0`
- `0x180002ad0`
- `0x1800058d0`
- `0x180006324`
- `0x180009c30`
- `0x180009d92`

## string_xrefs

- `0x180001fe3`: `onecore\base\appmodel\common\stateseparation.cpp`
- `0x180001fca`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180002025`: `onecore\base\appmodel\common\widestring.cpp`
- `0x18000203e`: `onecore\base\appmodel\common\widestring.cpp`
- `0x18000206b`: `onecore\base\appmodel\common\widestring.cpp`
- `0x1800020a6`: `onecore\base\appmodel\common\widestring.cpp`

## pseudocode

```c
__int64 __fastcall Common::CopyStringToOutput(Common *this, void **a2, unsigned __int16 **a3)
{
  Common *v5; // rax
  __int64 v6; // rcx
  unsigned int v7; // ebx
  __int64 v8; // rdi
  unsigned int i; // edx
  int v10; // eax
  unsigned int v11; // eax
  int v13; // eax
  void *v14[2]; // [rsp+20h] [rbp-48h] BYREF
  int v15; // [rsp+30h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v15 = 0;
  *(_OWORD *)v14 = 0;
  if ( !this )
  {
    Common::StringBuffer::Clear((Common::StringBuffer *)v14);
    goto LABEL_19;
  }
  v5 = this;
  v6 = 1073741822;
  do
  {
    if ( !*(_WORD *)v5 )
      break;
    v5 = (Common *)((char *)v5 + 2);
    --v6;
  }
  while ( v6 );
  v7 = -2147024809;
  if ( !v6 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x249,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)0x80070057LL,
      (int)v14[0]);
    goto LABEL_21;
  }
  v8 = (unsigned int)(1073741822 - v6);
  if ( (unsigned int)v8 > 0x7FFFFFFF )
  {
    v7 = -2147024362;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x22F,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)0x80070216LL,
      (int)v14[0]);
    goto LABEL_18;
  }
  if ( !(_DWORD)v8 )
    goto LABEL_13;
  if ( (unsigned int)v8 <= 0x20 )
  {
    for ( i = 8; i < (unsigned int)v8; i *= 2 )
      ;
  }
  else
  {
    i = 1073741822 - v6;
  }
  v10 = Common::StringBuffer::SetCapacity((Common::StringBuffer *)v14, i);
  v7 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x232,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)(unsigned int)v10,
      (int)v14[0]);
    goto LABEL_18;
  }
  if ( v15 )
    v11 = v15 - 1;
  else
LABEL_13:
    v11 = 0;
  if ( (unsigned int)v8 <= v11
    || (v13 = Common::StringBuffer::SetCapacity((Common::StringBuffer *)v14, v8), v7 = v13, v13 >= 0) )
  {
    if ( (_DWORD)v8 )
      *((_WORD *)v14[1] + v8) = 0;
    memcpy_0(v14[1], this, (unsigned int)(2 * v8));
    v7 = 0;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x20C,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)(unsigned int)v13,
      (int)v14[0]);
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x235,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)v7,
      (int)v14[0]);
  }
LABEL_18:
  if ( (v7 & 0x80000000) == 0 )
  {
LABEL_19:
    *a2 = v14[1];
    return 0;
  }
LABEL_21:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x31,
    (unsigned int)"onecore\\base\\appmodel\\common\\stateseparation.cpp",
    (const char *)v7,
    (int)v14[0]);
  if ( v14[1] )
    Common::GlobalHeap::Free(v14[1]);
  return v7;
}

```

## disassembly

```asm
0x180001ef0  push    rbx
0x180001ef2  push    rsi
0x180001ef3  push    rdi
0x180001ef4  push    r14
0x180001ef6  sub     rsp, 48h
0x180001efa  xor     eax, eax
0x180001efc  xorps   xmm0, xmm0
0x180001eff  mov     [rsp+68h+var_38], eax
0x180001f03  mov     r14, rdx
0x180001f06  mov     rsi, rcx
0x180001f09  movups  xmmword ptr [rsp+68h+var_48], xmm0; int
0x180001f0e  test    rcx, rcx
0x180001f11  jz      loc_180002057
0x180001f17  mov     edi, 3FFFFFFEh
0x180001f1c  mov     rax, rsi
0x180001f1f  mov     ecx, edi
0x180001f21  cmp     word ptr [rax], 0
0x180001f25  jz      short loc_180001F31
0x180001f27  add     rax, 2
0x180001f2b  sub     rcx, 1
0x180001f2f  jnz     short loc_180001F21
0x180001f31  xor     eax, eax
0x180001f33  mov     ebx, 80070057h
0x180001f38  test    rcx, rcx
0x180001f3b  cmovnz  ebx, eax
0x180001f3e  jz      loc_180001FC5
0x180001f44  sub     edi, ecx
0x180001f46  cmp     edi, 7FFFFFFFh
0x180001f4c  ja      loc_180002066
0x180001f52  test    edi, edi
0x180001f54  jz      short loc_180001F81
0x180001f56  cmp     edi, 20h ; ' '
0x180001f59  jbe     loc_180002089
0x180001f5f  mov     edx, edi; unsigned int
0x180001f61  lea     rcx, [rsp+68h+var_48]; this
0x180001f66  call    ?SetCapacity@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetCapacity(ulong)
0x180001f6b  mov     ebx, eax
0x180001f6d  test    eax, eax
0x180001f6f  js      loc_1800020A1
0x180001f75  mov     eax, [rsp+68h+var_38]
0x180001f79  test    eax, eax
0x180001f7b  jz      short loc_180001F81
0x180001f7d  dec     eax
0x180001f7f  jmp     short loc_180001F83
0x180001f81  xor     eax, eax
0x180001f83  cmp     edi, eax
0x180001f85  ja      loc_18000200A
0x180001f8b  test    edi, edi
0x180001f8d  jz      short loc_180001F9A
0x180001f8f  mov     rax, [rsp+68h+var_48+8]
0x180001f94  xor     ecx, ecx
0x180001f96  mov     [rax+rdi*2], cx
0x180001f9a  mov     rcx, [rsp+68h+var_48+8]; void *
0x180001f9f  lea     r8d, [rdi+rdi]; Size
0x180001fa3  mov     rdx, rsi; Src
0x180001fa6  call    memcpy_0
0x180001fab  xor     ebx, ebx
0x180001fad  test    ebx, ebx
0x180001faf  js      short loc_180001FDE
0x180001fb1  mov     rax, [rsp+68h+var_48+8]
0x180001fb6  mov     [r14], rax
0x180001fb9  xor     eax, eax
0x180001fbb  add     rsp, 48h
0x180001fbf  pop     r14
0x180001fc1  pop     rdi
0x180001fc2  pop     rsi
0x180001fc3  pop     rbx
0x180001fc4  retn
0x180001fc5  mov     rcx, [rsp+68h]; this
0x180001fca  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\widest"...
0x180001fd1  mov     r9d, ebx; char *
0x180001fd4  mov     edx, 249h; void *
0x180001fd9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180001fde  mov     rcx, [rsp+68h]; this
0x180001fe3  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\common\\states"...
0x180001fea  mov     r9d, ebx; char *
0x180001fed  mov     edx, 31h ; '1'; void *
0x180001ff2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180001ff7  mov     rcx, [rsp+68h+var_48+8]; void *
0x180001ffc  test    rcx, rcx
0x180001fff  jz      short loc_180002006
0x180002001  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x180002006  mov     eax, ebx
0x180002008  jmp     short loc_180001FBB
0x18000200a  mov     edx, edi; unsigned int
0x18000200c  lea     rcx, [rsp+68h+var_48]; this
0x180002011  call    ?SetCapacity@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetCapacity(ulong)
0x180002016  mov     ebx, eax
0x180002018  test    eax, eax
0x18000201a  jns     loc_180001F8B
0x180002020  mov     rcx, [rsp+68h]; this
0x180002025  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\widest"...
0x18000202c  mov     r9d, eax; char *
0x18000202f  mov     edx, 20Ch; void *
0x180002034  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180002039  mov     rcx, [rsp+68h]; this
0x18000203e  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\widest"...
0x180002045  mov     r9d, ebx; char *
0x180002048  mov     edx, 235h; void *
0x18000204d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180002052  jmp     loc_180001FAD
0x180002057  lea     rcx, [rsp+68h+var_48]; this
0x18000205c  call    ?Clear@StringBuffer@Common@@QEAAXXZ; Common::StringBuffer::Clear(void)
0x180002061  jmp     loc_180001FB1
0x180002066  mov     rcx, [rsp+68h]; this
0x18000206b  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\widest"...
0x180002072  mov     ebx, 80070216h
0x180002077  mov     edx, 22Fh; void *
0x18000207c  mov     r9d, ebx; char *
0x18000207f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180002084  jmp     loc_180001FAD
0x180002089  mov     edx, 8
0x18000208e  cmp     edi, edx
0x180002090  jbe     loc_180001F61
0x180002096  add     edx, edx
0x180002098  cmp     edx, edi
0x18000209a  jb      short loc_180002096
0x18000209c  jmp     loc_180001F61
0x1800020a1  mov     rcx, [rsp+68h]; this
0x1800020a6  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\widest"...
0x1800020ad  mov     r9d, eax; char *
0x1800020b0  mov     edx, 232h; void *
0x1800020b5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800020ba  jmp     loc_180001FAD
```
