# WebRequestFactory::CreateBasicConnection(AuthenticationContext const &,bool)

- ea: `0x14001e1a8`
- end: `0x14001e239`
- name: `?CreateBasicConnection@WebRequestFactory@@CA?AV?$unique_ptr@VWebRequest@@U?$default_delete@VWebRequest@@@std@@@std@@AEBVAuthenticationContext@@_N@Z`
- size: `145`
- prototype: `WebRequest **__fastcall(WebRequest **, __int64, bool)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000d9a8`
- `0x140010378`
- `0x14001604c`
- `0x1400176b4`
- `0x140018000`
- `0x14001bd58`

## callees

- `0x140001814`
- `0x14001e1a8`
- `0x14001eb64`

## string_xrefs

- `0x14001e1c4`: `onecore\ds\security\dsreg\win32\adal.native\webrequestfactory.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
WebRequest **__fastcall WebRequestFactory::CreateBasicConnection(WebRequest **a1, __int64 a2, bool a3)
{
  WebRequest *v6; // rax
  WebRequest *v7; // rdi
  bool v8; // bl

  v6 = (WebRequest *)operator new(0xA8u, 1, "onecore\\ds\\security\\dsreg\\win32\\adal.native\\webrequestfactory.cpp");
  v7 = v6;
  if ( v6 )
  {
    v8 = (*(_DWORD *)(a2 + 296) & 4) != 0;
    WebRequest::WebRequest(v6, a3, v8);
    *(_QWORD *)v7 = &HttpWebRequest::`vftable';
    *((_QWORD *)v7 + 19) = 0;
    *((_QWORD *)v7 + 20) = 0;
    *((_BYTE *)v7 + 24) = a3;
    *((_BYTE *)v7 + 25) = v8;
  }
  else
  {
    v7 = 0;
  }
  *a1 = v7;
  return a1;
}

```

## disassembly

```asm
0x14001e1a8  mov     [rsp+arg_0], rcx
0x14001e1ad  push    rbx
0x14001e1ae  push    rbp
0x14001e1af  push    rsi
0x14001e1b0  push    rdi
0x14001e1b1  sub     rsp, 38h
0x14001e1b5  mov     bpl, r8b
0x14001e1b8  mov     rbx, rdx
0x14001e1bb  mov     rsi, rcx
0x14001e1be  mov     r9d, 3Bh ; ';'; int
0x14001e1c4  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14001e1cb  lea     edx, [r9-3Ah]; int
0x14001e1cf  lea     ecx, [r9+6Dh]; unsigned __int64
0x14001e1d3  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x14001e1d8  mov     rdi, rax
0x14001e1db  mov     [rsp+58h+arg_0], rax
0x14001e1e0  test    rax, rax
0x14001e1e3  jz      short loc_14001E228
0x14001e1e5  mov     ebx, [rbx+128h]
0x14001e1eb  shr     ebx, 2
0x14001e1ee  and     bl, 1
0x14001e1f1  mov     r8b, bl; bool
0x14001e1f4  mov     dl, bpl; bool
0x14001e1f7  mov     rcx, rax; this
0x14001e1fa  call    ??0WebRequest@@IEAA@_N0@Z; WebRequest::WebRequest(bool,bool)
0x14001e1ff  lea     rax, ??_7HttpWebRequest@@6B@; const HttpWebRequest::`vftable'
0x14001e206  mov     [rdi], rax
0x14001e209  mov     qword ptr [rdi+98h], 0
0x14001e214  mov     qword ptr [rdi+0A0h], 0
0x14001e21f  mov     [rdi+18h], bpl
0x14001e223  mov     [rdi+19h], bl
0x14001e226  jmp     short loc_14001E22A
0x14001e228  xor     edi, edi
0x14001e22a  mov     [rsi], rdi
0x14001e22d  mov     rax, rsi
0x14001e230  add     rsp, 38h
0x14001e234  pop     rdi
0x14001e235  pop     rsi
0x14001e236  pop     rbp
0x14001e237  pop     rbx
0x14001e238  retn
```
