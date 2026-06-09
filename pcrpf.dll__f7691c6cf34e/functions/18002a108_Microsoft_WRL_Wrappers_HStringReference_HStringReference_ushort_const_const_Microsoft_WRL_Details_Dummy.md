# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x18002a108`
- end: `0x18002a17f`
- name: `??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z`
- size: `119`
- prototype: `HSTRING_HEADER *__fastcall(HSTRING_HEADER *, const WCHAR **, unsigned int)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002da6c`
- `0x180043d8c`
- `0x180047b20`
- `0x18004b710`
- `0x18004de90`

## callees

- `0x18002a108`
- `0x180034724`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002a142`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002a142`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
    JUMPOUT(0x18002A17ELL);
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
0x18002a108  mov     [rsp+arg_0], rbx
0x18002a10d  push    rdi
0x18002a10e  sub     rsp, 20h
0x18002a112  lea     r9, [rcx+18h]; string
0x18002a116  xor     edi, edi
0x18002a118  mov     [r9], rdi
0x18002a11b  mov     rbx, rcx
0x18002a11e  mov     rcx, [rdx]; sourceString
0x18002a121  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002a125  inc     rdx; int
0x18002a128  cmp     [rcx+rdx*2], di
0x18002a12c  jnz     short loc_18002A125
0x18002a12e  mov     eax, 0FFFFFFFFh
0x18002a133  cmp     rdx, rax
0x18002a136  ja      short loc_18002A169
0x18002a138  lea     eax, [rdx+1]
0x18002a13b  cmp     eax, edx
0x18002a13d  jb      short loc_18002A174
0x18002a13f  mov     r8, rbx; hstringHeader
0x18002a142  call    cs:__imp_WindowsCreateStringReference
0x18002a149  nop     dword ptr [rax+rax+00h]
0x18002a14e  test    eax, eax
0x18002a150  js      short loc_18002A161
0x18002a152  mov     rax, rbx
0x18002a155  mov     rbx, [rsp+28h+arg_0]
0x18002a15a  add     rsp, 20h
0x18002a15e  pop     rdi
0x18002a15f  retn
0x18002a161  mov     ecx, eax; this
0x18002a163  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18002a168  int     3; Trap to Debugger
0x18002a169  mov     ecx, 80070216h; this
0x18002a16e  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18002a173  int     3; Trap to Debugger
0x18002a174  mov     ecx, 80070216h; this
0x18002a179  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
