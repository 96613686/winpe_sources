# Marshal::XmlReader::CaptureNodeName(bool)

- ea: `0x18001f75c`
- end: `0x18001f81e`
- name: `?CaptureNodeName@XmlReader@Marshal@@QEAAX_N@Z`
- size: `194`
- prototype: `void(Marshal::XmlReader *__hidden this, bool)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001ff3c`
- `0x180020ccc`

## callees

- `0x180003620`
- `0x18000cd50`
- `0x18001f75c`
- `0x1800215cc`
- `0x180034010`

## string_xrefs

- `0x18001f809`: `onecore\internal\vm\inc\MarshalXml.h`

## pseudocode

```c
void __fastcall Marshal::XmlReader::CaptureNodeName(Marshal::XmlReader *this, char a2)
{
  __int64 v4; // rcx
  int v5; // eax
  __int64 v6; // r8
  void *v7; // r9
  char **v8; // rcx
  unsigned __int64 v9; // rdx
  char *v10; // rsi
  __int64 v11; // rbx
  __int64 v12; // rax
  int v13; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  void *Src; // [rsp+40h] [rbp+8h] BYREF

  v4 = *(_QWORD *)this;
  Src = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, void **, _QWORD))(*(_QWORD *)v4 + 112LL))(v4, &Src, 0);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x2A,
      (unsigned int)"onecore\\internal\\vm\\inc\\MarshalXml.h",
      (const char *)(unsigned int)v5,
      v13);
  v7 = Src;
  v8 = (char **)((char *)this + 8);
  v9 = -1;
  do
    ++v9;
  while ( *((_WORD *)Src + v9) );
  if ( v9 > *((_QWORD *)this + 4) )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v8, v9, v6, Src);
  }
  else
  {
    if ( *((_QWORD *)this + 4) <= 7u )
      v10 = (char *)this + 8;
    else
      v10 = *v8;
    v11 = 2 * v9;
    *((_QWORD *)this + 3) = v9;
    memmove_0(v10, v7, 2 * v9);
    *(_WORD *)&v10[v11] = 0;
  }
  v12 = *((_QWORD *)this + 3);
  *((_BYTE *)this + 48) = a2;
  *((_QWORD *)this + 5) = v12;
}

```

## disassembly

```asm
0x18001f75c  mov     r11, rsp
0x18001f75f  mov     [r11+10h], rbx
0x18001f763  mov     [r11+18h], rbp
0x18001f767  push    rsi
0x18001f768  push    rdi
0x18001f769  push    r14; int
0x18001f76b  sub     rsp, 20h
0x18001f76f  mov     rdi, rcx
0x18001f772  mov     bpl, dl
0x18001f775  mov     rcx, [rcx]
0x18001f778  lea     rdx, [r11+8]
0x18001f77c  xor     r14d, r14d
0x18001f77f  xor     r8d, r8d
0x18001f782  mov     [r11+8], r14
0x18001f786  mov     rax, [rcx]
0x18001f789  mov     rax, [rax+70h]
0x18001f78d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f792  test    eax, eax
0x18001f794  js      short loc_18001F804
0x18001f796  mov     r9, [rsp+38h+Src]
0x18001f79b  lea     rcx, [rdi+8]
0x18001f79f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001f7a3  inc     rdx
0x18001f7a6  cmp     [r9+rdx*2], r14w
0x18001f7ab  jnz     short loc_18001F7A3
0x18001f7ad  cmp     rdx, [rcx+18h]
0x18001f7b1  ja      short loc_18001F7DF
0x18001f7b3  cmp     qword ptr [rcx+18h], 7
0x18001f7b8  jbe     short loc_18001F7BF
0x18001f7ba  mov     rsi, [rcx]
0x18001f7bd  jmp     short loc_18001F7C2
0x18001f7bf  mov     rsi, rcx
0x18001f7c2  lea     rbx, [rdx+rdx]
0x18001f7c6  mov     [rcx+10h], rdx
0x18001f7ca  mov     r8, rbx; Size
0x18001f7cd  mov     rdx, r9; Src
0x18001f7d0  mov     rcx, rsi; void *
0x18001f7d3  call    memmove_0
0x18001f7d8  mov     [rbx+rsi], r14w
0x18001f7dd  jmp     short loc_18001F7E4
0x18001f7df  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18001f7e4  mov     rax, [rdi+18h]
0x18001f7e8  mov     rbx, [rsp+38h+arg_8]
0x18001f7ed  mov     [rdi+30h], bpl
0x18001f7f1  mov     rbp, [rsp+38h+arg_10]
0x18001f7f6  mov     [rdi+28h], rax
0x18001f7fa  add     rsp, 20h
0x18001f7fe  pop     r14
0x18001f800  pop     rdi
0x18001f801  pop     rsi
0x18001f802  retn
0x18001f804  mov     rcx, [rsp+38h]; this
0x18001f809  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x18001f810  mov     r9d, eax; char *
0x18001f813  mov     edx, 2Ah ; '*'; void *
0x18001f818  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
