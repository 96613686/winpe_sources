# NewCommandLineOptions::~NewCommandLineOptions(void)

- ea: `0x140008414`
- end: `0x140008548`
- name: `??1NewCommandLineOptions@@QEAA@XZ`
- size: `308`
- prototype: `void __fastcall(NewCommandLineOptions *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400081f8`
- `0x140014b2b`

## callees

- `0x140008414`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140008440`
- `OLEAUT32!__imp_SysFreeString` at `0x14000845d`
- `OLEAUT32!__imp_SysFreeString` at `0x14000847a`
- `OLEAUT32!__imp_SysFreeString` at `0x14000848f`
- `OLEAUT32!__imp_SysFreeString` at `0x1400084ad`
- `OLEAUT32!__imp_SysFreeString` at `0x1400084c7`
- `OLEAUT32!__imp_SysFreeString` at `0x1400084e1`
- `OLEAUT32!__imp_SysFreeString` at `0x1400084fb`
- `OLEAUT32!__imp_SysFreeString` at `0x140008515`
- `OLEAUT32!__imp_SysFreeString` at `0x14000852f`
- `OLEAUT32!__imp_SysFreeString` at `0x140008440`
- `OLEAUT32!__imp_SysFreeString` at `0x14000845d`
- `OLEAUT32!__imp_SysFreeString` at `0x14000847a`
- `OLEAUT32!__imp_SysFreeString` at `0x14000848f`
- `OLEAUT32!__imp_SysFreeString` at `0x1400084ad`
- `OLEAUT32!__imp_SysFreeString` at `0x1400084c7`
- `OLEAUT32!__imp_SysFreeString` at `0x1400084e1`
- `OLEAUT32!__imp_SysFreeString` at `0x1400084fb`
- `OLEAUT32!__imp_SysFreeString` at `0x140008515`
- `OLEAUT32!__imp_SysFreeString` at `0x14000852f`

## pseudocode

```c
void __fastcall NewCommandLineOptions::~NewCommandLineOptions(NewCommandLineOptions *this)
{
  char *v2; // rdi
  OLECHAR *v3; // rcx
  char *v4; // rbx

  v2 = (char *)this + 216;
  if ( *((_DWORD *)this + 56) )
  {
    SysFreeString(*(BSTR *)v2);
    *((_DWORD *)v2 + 2) = 0;
  }
  if ( *((_DWORD *)this + 50) )
  {
    SysFreeString(*((BSTR *)this + 24));
    *((_DWORD *)this + 50) = 0;
  }
  if ( *((_DWORD *)this + 46) )
  {
    SysFreeString(*((BSTR *)this + 22));
    *((_DWORD *)this + 46) = 0;
  }
  v3 = (OLECHAR *)*((_QWORD *)this + 17);
  if ( v3 )
  {
    SysFreeString(v3);
    *((_QWORD *)this + 17) = 0;
  }
  if ( *((_DWORD *)this + 30) )
  {
    SysFreeString(*((BSTR *)this + 14));
    *((_DWORD *)this + 30) = 0;
  }
  if ( *((_DWORD *)this + 26) )
  {
    SysFreeString(*((BSTR *)this + 12));
    *((_DWORD *)this + 26) = 0;
  }
  if ( *((_DWORD *)this + 22) )
  {
    SysFreeString(*((BSTR *)this + 10));
    *((_DWORD *)this + 22) = 0;
  }
  if ( *((_DWORD *)this + 16) )
  {
    SysFreeString(*((BSTR *)this + 7));
    *((_DWORD *)this + 16) = 0;
  }
  if ( *((_DWORD *)this + 12) )
  {
    SysFreeString(*((BSTR *)this + 5));
    *((_DWORD *)this + 12) = 0;
  }
  v4 = (char *)this + 8;
  if ( *((_DWORD *)v4 + 2) )
  {
    SysFreeString(*(BSTR *)v4);
    *((_DWORD *)v4 + 2) = 0;
  }
}

```

## disassembly

```asm
0x140008414  mov     rax, rsp
0x140008417  mov     [rax+18h], rbx
0x14000841b  mov     [rax+20h], rsi
0x14000841f  mov     [rax+8], rcx
0x140008423  push    rdi
0x140008424  sub     rsp, 20h
0x140008428  mov     rbx, rcx
0x14000842b  lea     rdi, [rcx+0D8h]
0x140008432  mov     [rax+10h], rdi
0x140008436  xor     esi, esi
0x140008438  cmp     [rdi+8], esi
0x14000843b  jz      short loc_140008449
0x14000843d  mov     rcx, [rdi]; bstrString
0x140008440  call    cs:__imp_SysFreeString
0x140008446  mov     [rdi+8], esi
0x140008449  lea     rdi, [rbx+0C0h]
0x140008450  mov     [rsp+28h+arg_8], rdi
0x140008455  cmp     [rdi+8], esi
0x140008458  jz      short loc_140008466
0x14000845a  mov     rcx, [rdi]; bstrString
0x14000845d  call    cs:__imp_SysFreeString
0x140008463  mov     [rdi+8], esi
0x140008466  lea     rdi, [rbx+0B0h]
0x14000846d  mov     [rsp+28h+arg_8], rdi
0x140008472  cmp     [rdi+8], esi
0x140008475  jz      short loc_140008483
0x140008477  mov     rcx, [rdi]; bstrString
0x14000847a  call    cs:__imp_SysFreeString
0x140008480  mov     [rdi+8], esi
0x140008483  mov     rcx, [rbx+88h]; bstrString
0x14000848a  test    rcx, rcx
0x14000848d  jz      short loc_14000849C
0x14000848f  call    cs:__imp_SysFreeString
0x140008495  mov     [rbx+88h], rsi
0x14000849c  lea     rdi, [rbx+70h]
0x1400084a0  mov     [rsp+28h+arg_8], rdi
0x1400084a5  cmp     [rdi+8], esi
0x1400084a8  jz      short loc_1400084B6
0x1400084aa  mov     rcx, [rdi]; bstrString
0x1400084ad  call    cs:__imp_SysFreeString
0x1400084b3  mov     [rdi+8], esi
0x1400084b6  lea     rdi, [rbx+60h]
0x1400084ba  mov     [rsp+28h+arg_8], rdi
0x1400084bf  cmp     [rdi+8], esi
0x1400084c2  jz      short loc_1400084D0
0x1400084c4  mov     rcx, [rdi]; bstrString
0x1400084c7  call    cs:__imp_SysFreeString
0x1400084cd  mov     [rdi+8], esi
0x1400084d0  lea     rdi, [rbx+50h]
0x1400084d4  mov     [rsp+28h+arg_8], rdi
0x1400084d9  cmp     [rdi+8], esi
0x1400084dc  jz      short loc_1400084EA
0x1400084de  mov     rcx, [rdi]; bstrString
0x1400084e1  call    cs:__imp_SysFreeString
0x1400084e7  mov     [rdi+8], esi
0x1400084ea  lea     rdi, [rbx+38h]
0x1400084ee  mov     [rsp+28h+arg_8], rdi
0x1400084f3  cmp     [rdi+8], esi
0x1400084f6  jz      short loc_140008504
0x1400084f8  mov     rcx, [rdi]; bstrString
0x1400084fb  call    cs:__imp_SysFreeString
0x140008501  mov     [rdi+8], esi
0x140008504  lea     rdi, [rbx+28h]
0x140008508  mov     [rsp+28h+arg_8], rdi
0x14000850d  cmp     [rdi+8], esi
0x140008510  jz      short loc_14000851E
0x140008512  mov     rcx, [rdi]; bstrString
0x140008515  call    cs:__imp_SysFreeString
0x14000851b  mov     [rdi+8], esi
0x14000851e  add     rbx, 8
0x140008522  mov     [rsp+28h+arg_0], rbx
0x140008527  cmp     [rbx+8], esi
0x14000852a  jz      short loc_140008538
0x14000852c  mov     rcx, [rbx]; bstrString
0x14000852f  call    cs:__imp_SysFreeString
0x140008535  mov     [rbx+8], esi
0x140008538  mov     rbx, [rsp+28h+arg_10]
0x14000853d  mov     rsi, [rsp+28h+arg_18]
0x140008542  add     rsp, 20h
0x140008546  pop     rdi
0x140008547  retn
```
