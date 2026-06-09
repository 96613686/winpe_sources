# Windows::Internal::String::_InitializeHelper(ushort const *)

- ea: `0x18001dd14`
- end: `0x18001dd7a`
- name: `?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z`
- size: `102`
- prototype: `__int64 __fastcall(HSTRING *this, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x1800012e0`
- `0x18000e2c8`
- `0x18001c744`
- `0x18001cc50`
- `0x18001d4e0`
- `0x180022ba0`

## callees

- `0x18000aea4`
- `0x18001b3b8`
- `0x18001dd14`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001dd56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001dd56`

## pseudocode

```c
HRESULT __fastcall Windows::Internal::String::_InitializeHelper(HSTRING *this, const unsigned __int16 *a2)
{
  unsigned __int64 v3; // rcx
  HRESULT result; // eax
  const WCHAR *v5; // r9
  UINT32 length; // [rsp+40h] [rbp+18h] BYREF
  HSTRING string; // [rsp+48h] [rbp+20h] BYREF

  length = 0;
  v3 = -1;
  string = 0;
  do
    ++v3;
  while ( a2[v3] );
  result = ULongLongToUInt(v3, &length);
  if ( result >= 0 )
  {
    result = WindowsCreateString(v5, length, &string);
    if ( result >= 0 )
      return Windows::Internal::String::FreeAndAssignOnSuccess(result, string, this);
  }
  return result;
}

```

## disassembly

```asm
0x18001dd14  mov     [rsp+arg_0], rbx
0x18001dd19  push    rdi
0x18001dd1a  sub     rsp, 20h
0x18001dd1e  xor     edi, edi
0x18001dd20  mov     rbx, rcx
0x18001dd23  mov     [rsp+28h+length], edi
0x18001dd27  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001dd2b  mov     [rsp+28h+string], rdi
0x18001dd30  mov     r9, rdx
0x18001dd33  inc     rcx; unsigned __int64
0x18001dd36  cmp     [rdx+rcx*2], di
0x18001dd3a  jnz     short loc_18001DD33
0x18001dd3c  lea     rdx, [rsp+28h+length]; unsigned int *
0x18001dd41  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18001dd46  test    eax, eax
0x18001dd48  js      short loc_18001DD6F
0x18001dd4a  mov     edx, [rsp+28h+length]; length
0x18001dd4e  lea     r8, [rsp+28h+string]; string
0x18001dd53  mov     rcx, r9; sourceString
0x18001dd56  call    cs:__imp_WindowsCreateString
0x18001dd5c  test    eax, eax
0x18001dd5e  js      short loc_18001DD6F
0x18001dd60  mov     rdx, [rsp+28h+string]; HSTRING
0x18001dd65  mov     r8, rbx; HSTRING *
0x18001dd68  mov     ecx, eax; int
0x18001dd6a  call    ?FreeAndAssignOnSuccess@String@Internal@Windows@@CAJJPEAUHSTRING__@@PEAPEAU4@@Z; Windows::Internal::String::FreeAndAssignOnSuccess(long,HSTRING__ *,HSTRING__ * *)
0x18001dd6f  mov     rbx, [rsp+28h+arg_0]
0x18001dd74  add     rsp, 20h
0x18001dd78  pop     rdi
0x18001dd79  retn
```
