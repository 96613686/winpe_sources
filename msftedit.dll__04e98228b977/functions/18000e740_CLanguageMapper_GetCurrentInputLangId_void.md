# CLanguageMapper::GetCurrentInputLangId(void)

- ea: `0x18000e740`
- end: `0x18000e7f2`
- name: `?GetCurrentInputLangId@CLanguageMapper@@SAGXZ`
- size: `178`
- prototype: `unsigned __int16(void)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000e108`

## callees

- `0x18000e740`
- `0x18000e7f8`
- `0x18000e8c0`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000e78f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000e78f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e7b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000e7b0`

## pseudocode

```c
__int64 CLanguageMapper::GetCurrentInputLangId(void)
{
  int v0; // eax
  HSTRING v1; // rcx
  int v2; // edi
  int v3; // eax
  unsigned __int16 v4; // bx
  const unsigned __int16 *StringRawBuffer; // rax
  unsigned __int16 LidForName; // ax
  __int64 v7; // rcx
  __int64 v9; // [rsp+30h] [rbp+8h] BYREF
  HSTRING string; // [rsp+38h] [rbp+10h] BYREF

  v9 = 0;
  v0 = OSGetLanguageStatics((__int64)&v9);
  v1 = 0;
  v2 = v0;
  string = 0;
  if ( !v0 )
  {
    v3 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v9 + 56LL))(v9, &string);
    v1 = string;
    v2 = v3;
  }
  v4 = 0;
  if ( !v2 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(v1, 0);
    LidForName = GetLidForName(StringRawBuffer);
    v1 = string;
    v4 = LidForName;
  }
  if ( v1 )
    WindowsDeleteString(v1);
  if ( v2 )
    v4 = 0;
  v7 = v9;
  if ( v9 )
  {
    v9 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  return v4;
}

```

## disassembly

```asm
0x18000e740  mov     [rsp+arg_10], rbx
0x18000e745  push    rdi
0x18000e746  sub     rsp, 20h
0x18000e74a  lea     rcx, [rsp+28h+arg_0]
0x18000e74f  mov     [rsp+28h+arg_0], 0
0x18000e758  call    OSGetLanguageStatics
0x18000e75d  xor     ecx, ecx
0x18000e75f  mov     edi, eax
0x18000e761  mov     [rsp+28h+string], rcx
0x18000e766  test    eax, eax
0x18000e768  jnz     short loc_18000E787
0x18000e76a  mov     rcx, [rsp+28h+arg_0]
0x18000e76f  lea     rdx, [rsp+28h+string]
0x18000e774  mov     rax, [rcx]
0x18000e777  mov     rax, [rax+38h]
0x18000e77b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e780  mov     rcx, [rsp+28h+string]; string
0x18000e785  mov     edi, eax
0x18000e787  xor     ebx, ebx
0x18000e789  test    edi, edi
0x18000e78b  jnz     short loc_18000E7AB
0x18000e78d  xor     edx, edx; length
0x18000e78f  call    cs:__imp_WindowsGetStringRawBuffer
0x18000e796  nop     dword ptr [rax+rax+00h]
0x18000e79b  mov     rcx, rax; unsigned __int16 *
0x18000e79e  call    ?GetLidForName@@YAGPEBG@Z; GetLidForName(ushort const *)
0x18000e7a3  mov     rcx, [rsp+28h+string]; string
0x18000e7a8  movzx   ebx, ax
0x18000e7ab  test    rcx, rcx
0x18000e7ae  jz      short loc_18000E7BC
0x18000e7b0  call    cs:__imp_WindowsDeleteString
0x18000e7b7  nop     dword ptr [rax+rax+00h]
0x18000e7bc  xor     ecx, ecx
0x18000e7be  test    edi, edi
0x18000e7c0  cmovnz  bx, cx
0x18000e7c4  mov     rcx, [rsp+28h+arg_0]
0x18000e7c9  test    rcx, rcx
0x18000e7cc  jz      short loc_18000E7E3
0x18000e7ce  mov     [rsp+28h+arg_0], 0
0x18000e7d7  mov     rax, [rcx]
0x18000e7da  mov     rax, [rax+10h]
0x18000e7de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7e3  movzx   eax, bx
0x18000e7e6  mov     rbx, [rsp+28h+arg_10]
0x18000e7eb  add     rsp, 20h
0x18000e7ef  pop     rdi
0x18000e7f0  retn
```
