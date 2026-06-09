# Marshal::Details::StartRead(Marshal::XmlReader &,ushort const *,Marshal::UnmarshalContext const &)

- ea: `0x180020ccc`
- end: `0x180020dba`
- name: `?StartRead@Details@Marshal@@YA_NAEAUXmlReader@2@PEBGAEBVUnmarshalContext@2@@Z`
- size: `238`
- prototype: `bool __fastcall(Marshal::Details *__hidden this, struct Marshal::XmlReader *, const unsigned __int16 *, const struct Marshal::UnmarshalContext *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800130d8`

## callees

- `0x18001f75c`
- `0x1800208b8`
- `0x180020ccc`
- `0x180021058`
- `0x1800215cc`
- `0x180022094`
- `0x180034010`

## string_xrefs

- `0x180020da8`: `onecore\internal\vm\inc\MarshalXml.h`

## pseudocode

```c
char __fastcall Marshal::Details::StartRead(
        Marshal::Details *this,
        struct Marshal::XmlReader *a2,
        const unsigned __int16 *a3,
        const struct Marshal::UnmarshalContext *a4)
{
  int v6; // eax
  int v7; // ecx
  const wchar_t *v9; // rcx
  int v10; // eax
  _QWORD v11[2]; // [rsp+20h] [rbp-28h] BYREF
  _QWORD v12[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned int v14; // [rsp+58h] [rbp+10h] BYREF
  int v15; // [rsp+5Ch] [rbp+14h]

  v15 = HIDWORD(a2);
  v14 = 0;
  while ( 1 )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *, const unsigned __int16 *, const struct Marshal::UnmarshalContext *))(**(_QWORD **)this + 48LL))(
           *(_QWORD *)this,
           &v14,
           a3,
           a4);
    if ( v6 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x578,
        (unsigned int)"onecore\\internal\\vm\\inc\\MarshalXml.h",
        (const char *)(unsigned int)v6,
        v11[0]);
    if ( v14 == 1 )
      break;
    if ( v14 <= 0x11 )
    {
      v7 = 139520;
      if ( _bittest(&v7, v14) )
        continue;
    }
    goto LABEL_6;
  }
  Marshal::XmlReader::CaptureNodeName(this, 0);
  if ( *((_QWORD *)this + 4) <= 7u )
    v9 = (const wchar_t *)((char *)this + 8);
  else
    v9 = (const wchar_t *)*((_QWORD *)this + 1);
  if ( *((_QWORD *)this + 3) != 9
    || ((*(_BYTE *)(*((_QWORD *)a3 + 1) + 24LL) & 2) == 0
      ? (v10 = wmemcmp(v9, L"container", 9u))
      : (v11[0] = L"container",
         v12[0] = v9,
         v11[1] = 9,
         v12[1] = 9,
         v10 = Marshal::Details::StringCompareCaseInsensitive(v12, v11)),
        v10) )
  {
LABEL_6:
    Marshal::UnmarshalContext::ReportError(a3, 15);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180020ccc  mov     [rsp+arg_0], rbx
0x180020cd1  mov     [rsp+arg_8], rdx
0x180020cd6  push    rdi
0x180020cd7  sub     rsp, 40h
0x180020cdb  mov     rdi, r8
0x180020cde  mov     dword ptr [rsp+48h+arg_8], 0
0x180020ce6  mov     rbx, rcx
0x180020ce9  mov     rcx, [rbx]
0x180020cec  lea     rdx, [rsp+48h+arg_8]
0x180020cf1  mov     rax, [rcx]
0x180020cf4  mov     rax, [rax+30h]
0x180020cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020cfd  mov     rcx, [rsp+48h]; this
0x180020d02  test    eax, eax
0x180020d04  js      loc_180020DA5
0x180020d0a  mov     eax, dword ptr [rsp+48h+arg_8]
0x180020d0e  cmp     eax, 1
0x180020d11  jz      short loc_180020D3D
0x180020d13  cmp     eax, 11h
0x180020d16  ja      short loc_180020D22
0x180020d18  mov     ecx, 22100h
0x180020d1d  bt      ecx, eax
0x180020d20  jb      short loc_180020CE9
0x180020d22  mov     edx, 0Fh
0x180020d27  mov     rcx, rdi
0x180020d2a  call    ?ReportError@UnmarshalContext@Marshal@@QEBAXW4UnmarshalError@2@@Z; Marshal::UnmarshalContext::ReportError(Marshal::UnmarshalError)
0x180020d2f  xor     al, al
0x180020d31  mov     rbx, [rsp+48h+arg_0]
0x180020d36  add     rsp, 40h
0x180020d3a  pop     rdi
0x180020d3b  retn
0x180020d3d  xor     edx, edx; bool
0x180020d3f  mov     rcx, rbx; this
0x180020d42  call    ?CaptureNodeName@XmlReader@Marshal@@QEAAX_N@Z; Marshal::XmlReader::CaptureNodeName(bool)
0x180020d47  cmp     qword ptr [rbx+20h], 7
0x180020d4c  jbe     short loc_180020D54
0x180020d4e  mov     rcx, [rbx+8]
0x180020d52  jmp     short loc_180020D58
0x180020d54  lea     rcx, [rbx+8]; S1
0x180020d58  mov     r8, [rbx+18h]; N
0x180020d5c  cmp     r8, 9
0x180020d60  jnz     short loc_180020D22
0x180020d62  mov     rax, [rdi+8]
0x180020d66  lea     rdx, aContainer; "container"
0x180020d6d  test    byte ptr [rax+18h], 2
0x180020d71  jz      short loc_180020D98
0x180020d73  mov     [rsp+48h+var_28], rdx
0x180020d78  lea     rdx, [rsp+48h+var_28]
0x180020d7d  mov     [rsp+48h+var_18], rcx
0x180020d82  lea     rcx, [rsp+48h+var_18]
0x180020d87  mov     [rsp+48h+var_20], r8
0x180020d8c  mov     [rsp+48h+var_10], r8
0x180020d91  call    ?StringCompareCaseInsensitive@Details@Marshal@@YAHV?$basic_string_view@GU?$char_traits@G@std@@@std@@0@Z; Marshal::Details::StringCompareCaseInsensitive(std::basic_string_view<ushort>,std::basic_string_view<ushort>)
0x180020d96  jmp     short loc_180020D9D
0x180020d98  call    wmemcmp
0x180020d9d  test    eax, eax
0x180020d9f  jnz     short loc_180020D22
0x180020da1  mov     al, 1
0x180020da3  jmp     short loc_180020D31
0x180020da5  mov     r9d, eax; char *
0x180020da8  lea     r8, aOnecoreInterna_2; "onecore\\internal\\vm\\inc\\MarshalXml."...
0x180020daf  mov     edx, 578h; void *
0x180020db4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
