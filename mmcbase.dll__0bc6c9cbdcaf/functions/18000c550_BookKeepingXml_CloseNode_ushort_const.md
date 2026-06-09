# BookKeepingXml::CloseNode(ushort const *)

- ea: `0x18000c550`
- end: `0x18000c603`
- name: `?CloseNode@BookKeepingXml@@AEAAJPEBG@Z`
- size: `179`
- prototype: `__int64 __fastcall(BookKeepingXml *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000c464`
- `0x18000c60c`
- `0x18000c64c`

## callees

- `0x18000c378`
- `0x18000c3e8`
- `0x18000c550`
- `0x18000c88c`
- `0x18000cfbc`

## pseudocode

```c
__int64 __fastcall BookKeepingXml::CloseNode(BookKeepingXml *this, const unsigned __int16 *a2)
{
  __int64 v4; // rax
  unsigned __int64 v5; // rdx
  __int64 v6; // rax
  int v7; // ebx

  if ( a2 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a2[v4] );
    v5 = v4 + 5;
    v6 = *((_QWORD *)this + 1030);
    if ( v6 )
      *((_QWORD *)this + 1030) = v6 - 1;
    v7 = BookKeepingXml::CheckBufferSize(this, v5);
    if ( v7 >= 0 )
    {
      BookKeepingXml::Indent(this);
      v7 = BookKeepingXml::Append(this, L"</%s>\r\n", a2);
      if ( v7 < 0
        && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        WPP_SF_Sd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          23,
          (unsigned int)WPP_9741a39f05e03860cc0b7f50af82ce94_Traceguids,
          (_DWORD)a2,
          v7);
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000c550  push    rbx
0x18000c552  push    rbp
0x18000c553  push    rsi
0x18000c554  push    rdi
0x18000c555  sub     rsp, 38h
0x18000c559  xor     ebp, ebp
0x18000c55b  mov     rsi, rdx
0x18000c55e  mov     rdi, rcx
0x18000c561  test    rdx, rdx
0x18000c564  jz      loc_18000C5F3
0x18000c56a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c56e  inc     rax
0x18000c571  cmp     [rdx+rax*2], bp
0x18000c575  jnz     short loc_18000C56E
0x18000c577  lea     rdx, [rax+5]; unsigned __int64
0x18000c57b  mov     rax, [rcx+2030h]
0x18000c582  test    rax, rax
0x18000c585  jz      short loc_18000C591
0x18000c587  dec     rax
0x18000c58a  mov     [rcx+2030h], rax
0x18000c591  call    ?CheckBufferSize@BookKeepingXml@@AEAAJ_K@Z; BookKeepingXml::CheckBufferSize(unsigned __int64)
0x18000c596  mov     ebx, eax
0x18000c598  test    eax, eax
0x18000c59a  js      short loc_18000C5F8
0x18000c59c  mov     rcx, rdi; this
0x18000c59f  call    ?Indent@BookKeepingXml@@AEAAJXZ; BookKeepingXml::Indent(void)
0x18000c5a4  mov     r8, rsi
0x18000c5a7  lea     rdx, aS_0; "</%s>\r\n"
0x18000c5ae  mov     rcx, rdi; this
0x18000c5b1  call    ?Append@BookKeepingXml@@AEAAJPEBGZZ; BookKeepingXml::Append(ushort const *,...)
0x18000c5b6  mov     ebx, eax
0x18000c5b8  test    eax, eax
0x18000c5ba  jns     short loc_18000C5F8
0x18000c5bc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c5c3  lea     rax, WPP_GLOBAL_Control
0x18000c5ca  cmp     rcx, rax
0x18000c5cd  jz      short loc_18000C5F8
0x18000c5cf  cmp     byte ptr [rcx+19h], 2
0x18000c5d3  jb      short loc_18000C5F8
0x18000c5d5  mov     rcx, [rcx+10h]
0x18000c5d9  lea     r8, WPP_9741a39f05e03860cc0b7f50af82ce94_Traceguids
0x18000c5e0  mov     edx, 17h
0x18000c5e5  mov     [rsp+58h+var_38], ebx
0x18000c5e9  mov     r9, rsi
0x18000c5ec  call    WPP_SF_Sd
0x18000c5f1  jmp     short loc_18000C5F8
0x18000c5f3  mov     ebx, 80070057h
0x18000c5f8  mov     eax, ebx
0x18000c5fa  add     rsp, 38h
0x18000c5fe  pop     rdi
0x18000c5ff  pop     rsi
0x18000c600  pop     rbp
0x18000c601  pop     rbx
0x18000c602  retn
```
