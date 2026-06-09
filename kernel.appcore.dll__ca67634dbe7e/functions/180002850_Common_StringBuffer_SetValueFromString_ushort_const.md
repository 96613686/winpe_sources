# Common::StringBuffer::SetValueFromString(ushort const *)

- ea: `0x180002850`
- end: `0x1800029b8`
- name: `?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z`
- size: `360`
- prototype: `int(Common::StringBuffer *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800020d0`

## callees

- `0x180002850`
- `0x1800029c0`
- `0x180006324`
- `0x180009c30`
- `0x180009d92`

## string_xrefs

- `0x180002943`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180002966`: `onecore\base\appmodel\common\widestring.cpp`

## pseudocode

```c
__int64 __fastcall Common::StringBuffer::SetValueFromString(Common::StringBuffer *this, const unsigned __int16 *a2)
{
  const unsigned __int16 *v4; // rax
  __int64 v5; // rcx
  unsigned int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdi
  int v9; // ecx
  unsigned int i; // edx
  int v11; // eax
  int v12; // edx
  unsigned int v13; // ecx
  __int64 v15; // rdx
  unsigned __int64 v16; // r9
  int v17; // eax
  int v18; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 )
  {
    v4 = a2;
    v5 = 1073741822;
    do
    {
      if ( !*v4 )
        break;
      ++v4;
      --v5;
    }
    while ( v5 );
    v6 = 0;
    v7 = -2147024809;
    if ( v5 )
    {
      v8 = (unsigned int)(1073741822 - v5);
      if ( (unsigned int)v8 > 0x7FFFFFFF )
      {
        v7 = -2147024362;
        v15 = 559;
      }
      else
      {
        v9 = *((_DWORD *)this + 4);
        if ( v9 )
          v6 = v9 - 1;
        if ( (unsigned int)v8 > v6 || v9 && (unsigned int)(v9 - 1) > 0x20 )
        {
          if ( (unsigned int)v8 <= 0x20 )
          {
            for ( i = 8; i < (unsigned int)v8; i *= 2 )
              ;
          }
          else
          {
            i = v8;
          }
          v11 = Common::StringBuffer::SetCapacity(this, i);
          v7 = v11;
          if ( v11 < 0 )
          {
            v16 = (unsigned int)v11;
            v15 = 562;
            goto LABEL_25;
          }
        }
        v12 = *((_DWORD *)this + 4);
        v13 = 0;
        if ( v12 )
          v13 = v12 - 1;
        if ( (unsigned int)v8 <= v13 || (v17 = Common::StringBuffer::SetCapacity(this, v8), v7 = v17, v17 >= 0) )
        {
          *(_DWORD *)this = v8;
          if ( (_DWORD)v8 )
            *(_WORD *)(*((_QWORD *)this + 1) + 2 * v8) = 0;
          memcpy_0(*((void **)this + 1), a2, (unsigned int)(2 * v8));
          return 0;
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x20C,
          (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
          (const char *)(unsigned int)v17,
          v18);
        v15 = 565;
      }
    }
    else
    {
      v15 = 585;
    }
    v16 = v7;
LABEL_25:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)v16,
      v18);
    return v7;
  }
  Common::StringBuffer::Clear(this);
  return 0;
}

```

## disassembly

```asm
0x180002850  mov     [rsp+arg_10], rsi
0x180002855  push    r14; int
0x180002857  sub     rsp, 20h
0x18000285b  mov     rsi, rdx
0x18000285e  mov     r14, rcx
0x180002861  test    rdx, rdx
0x180002864  jz      loc_180002981
0x18000286a  mov     [rsp+28h+arg_0], rbx
0x18000286f  mov     rax, rdx
0x180002872  mov     [rsp+28h+arg_8], rdi
0x180002877  mov     edi, 3FFFFFFEh
0x18000287c  mov     ecx, edi
0x18000287e  xchg    ax, ax
0x180002880  cmp     word ptr [rax], 0
0x180002884  jz      short loc_180002890
0x180002886  add     rax, 2
0x18000288a  sub     rcx, 1
0x18000288e  jnz     short loc_180002880
0x180002890  xor     eax, eax
0x180002892  mov     ebx, 80070057h
0x180002897  test    rcx, rcx
0x18000289a  cmovnz  ebx, eax
0x18000289d  jz      loc_180002936
0x1800028a3  sub     edi, ecx
0x1800028a5  cmp     edi, 7FFFFFFFh
0x1800028ab  ja      loc_18000298A
0x1800028b1  mov     ecx, [r14+10h]
0x1800028b5  test    ecx, ecx
0x1800028b7  lea     edx, [rcx-1]
0x1800028ba  cmovnz  eax, edx
0x1800028bd  cmp     edi, eax
0x1800028bf  jbe     short loc_18000292B
0x1800028c1  cmp     edi, 20h ; ' '
0x1800028c4  jbe     loc_180002996
0x1800028ca  mov     edx, edi; unsigned int
0x1800028cc  mov     rcx, r14; this
0x1800028cf  call    ?SetCapacity@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetCapacity(ulong)
0x1800028d4  mov     ebx, eax
0x1800028d6  test    eax, eax
0x1800028d8  js      loc_1800029AE
0x1800028de  mov     edx, [r14+10h]
0x1800028e2  xor     ecx, ecx
0x1800028e4  test    edx, edx
0x1800028e6  lea     eax, [rdx-1]
0x1800028e9  cmovnz  ecx, eax
0x1800028ec  cmp     edi, ecx
0x1800028ee  ja      short loc_180002951
0x1800028f0  mov     [r14], edi
0x1800028f3  test    edi, edi
0x1800028f5  jz      short loc_180002901
0x1800028f7  mov     rcx, [r14+8]
0x1800028fb  xor     eax, eax
0x1800028fd  mov     [rcx+rdi*2], ax
0x180002901  mov     rcx, [r14+8]; void *
0x180002905  lea     r8d, [rdi+rdi]; Size
0x180002909  mov     rdx, rsi; Src
0x18000290c  call    memcpy_0
0x180002911  xor     ebx, ebx
0x180002913  mov     rdi, [rsp+28h+arg_8]
0x180002918  mov     eax, ebx
0x18000291a  mov     rbx, [rsp+28h+arg_0]
0x18000291f  mov     rsi, [rsp+28h+arg_10]
0x180002924  add     rsp, 20h
0x180002928  pop     r14
0x18000292a  retn
0x18000292b  test    ecx, ecx
0x18000292d  jz      short loc_1800028DE
0x18000292f  cmp     edx, 20h ; ' '
0x180002932  jbe     short loc_1800028DE
0x180002934  jmp     short loc_1800028C1
0x180002936  mov     edx, 249h; void *
0x18000293b  mov     r9d, ebx; char *
0x18000293e  mov     rcx, [rsp+28h]; this
0x180002943  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\widest"...
0x18000294a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000294f  jmp     short loc_180002913
0x180002951  mov     edx, edi; unsigned int
0x180002953  mov     rcx, r14; this
0x180002956  call    ?SetCapacity@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetCapacity(ulong)
0x18000295b  mov     ebx, eax
0x18000295d  test    eax, eax
0x18000295f  jns     short loc_1800028F0
0x180002961  mov     rcx, [rsp+28h]; this
0x180002966  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\widest"...
0x18000296d  mov     r9d, eax; char *
0x180002970  mov     edx, 20Ch; void *
0x180002975  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000297a  mov     edx, 235h
0x18000297f  jmp     short loc_18000293B
0x180002981  call    ?Clear@StringBuffer@Common@@QEAAXXZ; Common::StringBuffer::Clear(void)
0x180002986  xor     eax, eax
0x180002988  jmp     short loc_18000291F
0x18000298a  mov     ebx, 80070216h
0x18000298f  mov     edx, 22Fh
0x180002994  jmp     short loc_18000293B
0x180002996  mov     edx, 8
0x18000299b  cmp     edi, edx
0x18000299d  jbe     loc_1800028CC
0x1800029a3  add     edx, edx
0x1800029a5  cmp     edx, edi
0x1800029a7  jb      short loc_1800029A3
0x1800029a9  jmp     loc_1800028CC
0x1800029ae  mov     r9d, eax
0x1800029b1  mov     edx, 232h
0x1800029b6  jmp     short loc_18000293E
```
