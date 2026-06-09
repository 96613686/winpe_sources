# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x18001a874`
- end: `0x18001a8eb`
- name: `??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z`
- size: `119`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001c1b8`
- `0x18001c560`
- `0x18002dc24`

## callees

- `0x18001a874`
- `0x18001dc10`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001a8ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001a8ae`

## pseudocode

```c
HSTRING_HEADER *__fastcall Microsoft::WRL::Wrappers::HStringReference::HStringReference(
        HSTRING_HEADER *a1,
        const WCHAR **a2,
        unsigned int a3)
{
  HSTRING *v3; // r9
  const WCHAR *v5; // rcx
  unsigned __int64 v6; // rdx
  HRESULT StringReference; // eax
  int v8; // edx
  unsigned int v9; // r8d

  v3 = (HSTRING *)&a1[1];
  a1[1].Reserved.Reserved1 = 0;
  v5 = *a2;
  v6 = -1;
  do
    ++v6;
  while ( v5[v6] );
  if ( v6 > 0xFFFFFFFF )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v6, a3);
    __debugbreak();
  }
  if ( (int)v6 + 1 < (unsigned int)v6 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v6, a3);
    JUMPOUT(0x18001A8EALL);
  }
  StringReference = WindowsCreateStringReference(v5, v6, a1, v3);
  if ( StringReference < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)StringReference, v8, v9);
    __debugbreak();
  }
  return a1;
}

```

## disassembly

```asm
0x18001a874  mov     [rsp+arg_0], rbx
0x18001a879  push    rdi
0x18001a87a  sub     rsp, 20h
0x18001a87e  lea     r9, [rcx+18h]; string
0x18001a882  xor     edi, edi
0x18001a884  mov     [r9], rdi
0x18001a887  mov     rbx, rcx
0x18001a88a  mov     rcx, [rdx]; sourceString
0x18001a88d  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001a891  inc     rdx; int
0x18001a894  cmp     [rcx+rdx*2], di
0x18001a898  jnz     short loc_18001A891
0x18001a89a  mov     eax, 0FFFFFFFFh
0x18001a89f  cmp     rdx, rax
0x18001a8a2  ja      short loc_18001A8D5
0x18001a8a4  lea     eax, [rdx+1]
0x18001a8a7  cmp     eax, edx
0x18001a8a9  jb      short loc_18001A8E0
0x18001a8ab  mov     r8, rbx; hstringHeader
0x18001a8ae  call    cs:__imp_WindowsCreateStringReference
0x18001a8b5  nop     dword ptr [rax+rax+00h]
0x18001a8ba  test    eax, eax
0x18001a8bc  js      short loc_18001A8CD
0x18001a8be  mov     rax, rbx
0x18001a8c1  mov     rbx, [rsp+28h+arg_0]
0x18001a8c6  add     rsp, 20h
0x18001a8ca  pop     rdi
0x18001a8cb  retn
0x18001a8cd  mov     ecx, eax; this
0x18001a8cf  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18001a8d4  int     3; Trap to Debugger
0x18001a8d5  mov     ecx, 80070216h; this
0x18001a8da  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18001a8df  int     3; Trap to Debugger
0x18001a8e0  mov     ecx, 80070216h; this
0x18001a8e5  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
