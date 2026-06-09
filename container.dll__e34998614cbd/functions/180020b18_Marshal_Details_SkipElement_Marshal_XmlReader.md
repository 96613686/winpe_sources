# Marshal::Details::SkipElement(Marshal::XmlReader &)

- ea: `0x180020b18`
- end: `0x180020bbb`
- name: `?SkipElement@Details@Marshal@@YA_NAEAUXmlReader@2@@Z`
- size: `163`
- prototype: `bool(Marshal::Details *__hidden this, struct Marshal::XmlReader *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180020470`

## callees

- `0x180020b18`
- `0x1800215cc`
- `0x180034010`

## string_xrefs

- `0x180020ba9`: `onecore\internal\vm\inc\MarshalXml.h`

## pseudocode

```c
char __fastcall Marshal::Details::SkipElement(Marshal::Details *this, struct Marshal::XmlReader *a2)
{
  int v3; // ebx
  __int64 v4; // rcx
  int v5; // eax
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v9; // [rsp+30h] [rbp+8h] BYREF

  if ( (*(unsigned int (__fastcall **)(_QWORD, struct Marshal::XmlReader *))(**(_QWORD **)this + 160LL))(
         *(_QWORD *)this,
         a2) )
  {
    return 1;
  }
  v3 = 1;
  while ( 1 )
  {
    v4 = *(_QWORD *)this;
    v9 = 0;
    v5 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v4 + 48LL))(v4, &v9);
    if ( v5 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x341,
        (unsigned int)"onecore\\internal\\vm\\inc\\MarshalXml.h",
        (const char *)(unsigned int)v5,
        v7);
    if ( !v9 )
      break;
    if ( v9 == 1 )
    {
      if ( !(*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)this + 160LL))(*(_QWORD *)this) )
        ++v3;
    }
    else if ( v9 == 15 && !--v3 )
    {
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180020b18  mov     [rsp+arg_8], rbx
0x180020b1d  push    rdi; int
0x180020b1e  sub     rsp, 20h
0x180020b22  mov     rdi, rcx
0x180020b25  mov     rcx, [rcx]
0x180020b28  mov     rax, [rcx]
0x180020b2b  mov     rax, [rax+0A0h]
0x180020b32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b37  test    eax, eax
0x180020b39  jnz     short loc_180020B7A
0x180020b3b  lea     ebx, [rax+1]
0x180020b3e  mov     rcx, [rdi]
0x180020b41  lea     rdx, [rsp+28h+arg_0]
0x180020b46  mov     [rsp+28h+arg_0], 0
0x180020b4e  mov     rax, [rcx]
0x180020b51  mov     rax, [rax+30h]
0x180020b55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b5a  mov     rcx, [rsp+28h]; this
0x180020b5f  test    eax, eax
0x180020b61  js      short loc_180020BA6
0x180020b63  mov     ecx, [rsp+28h+arg_0]
0x180020b67  test    ecx, ecx
0x180020b69  jz      short loc_180020BA2
0x180020b6b  sub     ecx, 1
0x180020b6e  jz      short loc_180020B88
0x180020b70  cmp     ecx, 0Eh
0x180020b73  jnz     short loc_180020B3E
0x180020b75  sub     ebx, 1
0x180020b78  jnz     short loc_180020B3E
0x180020b7a  mov     al, 1
0x180020b7c  mov     rbx, [rsp+28h+arg_8]
0x180020b81  add     rsp, 20h
0x180020b85  pop     rdi
0x180020b86  retn
0x180020b88  mov     rcx, [rdi]
0x180020b8b  mov     rax, [rcx]
0x180020b8e  mov     rax, [rax+0A0h]
0x180020b95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b9a  test    eax, eax
0x180020b9c  jnz     short loc_180020B3E
0x180020b9e  inc     ebx
0x180020ba0  jmp     short loc_180020B3E
0x180020ba2  xor     al, al
0x180020ba4  jmp     short loc_180020B7C
0x180020ba6  mov     r9d, eax; char *
0x180020ba9  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180020bb0  mov     edx, 341h; void *
0x180020bb5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
