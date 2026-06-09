# Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)

- ea: `0x14000d9b0`
- end: `0x14000da27`
- name: `??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z`
- size: `119`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000e290`
- `0x140012e10`
- `0x1400135d4`

## callees

- `0x14000ac50`
- `0x14000d9b0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000d9ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14000d9ea`

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
    JUMPOUT(0x14000DA26LL);
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
0x14000d9b0  mov     [rsp+arg_0], rbx
0x14000d9b5  push    rdi
0x14000d9b6  sub     rsp, 20h
0x14000d9ba  lea     r9, [rcx+18h]; string
0x14000d9be  xor     edi, edi
0x14000d9c0  mov     [r9], rdi
0x14000d9c3  mov     rbx, rcx
0x14000d9c6  mov     rcx, [rdx]; sourceString
0x14000d9c9  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000d9cd  inc     rdx; int
0x14000d9d0  cmp     [rcx+rdx*2], di
0x14000d9d4  jnz     short loc_14000D9CD
0x14000d9d6  mov     eax, 0FFFFFFFFh
0x14000d9db  cmp     rdx, rax
0x14000d9de  ja      short loc_14000DA11
0x14000d9e0  lea     eax, [rdx+1]
0x14000d9e3  cmp     eax, edx
0x14000d9e5  jb      short loc_14000DA1C
0x14000d9e7  mov     r8, rbx; hstringHeader
0x14000d9ea  call    cs:__imp_WindowsCreateStringReference
0x14000d9f1  nop     dword ptr [rax+rax+00h]
0x14000d9f6  test    eax, eax
0x14000d9f8  js      short loc_14000DA09
0x14000d9fa  mov     rax, rbx
0x14000d9fd  mov     rbx, [rsp+28h+arg_0]
0x14000da02  add     rsp, 20h
0x14000da06  pop     rdi
0x14000da07  retn
0x14000da09  mov     ecx, eax; this
0x14000da0b  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x14000da10  int     3; Trap to Debugger
0x14000da11  mov     ecx, 80070216h; this
0x14000da16  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x14000da1b  int     3; Trap to Debugger
0x14000da1c  mov     ecx, 80070216h; this
0x14000da21  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
