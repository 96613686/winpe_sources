# Windows::Internal::String::Initialize<ushort *>(ushort * const &,Windows::Internal::_StringDetail::dummy_t)

- ea: `0x180016028`
- end: `0x1800160aa`
- name: `??$Initialize@PEAG@String@Internal@Windows@@QEAAJAEBQEAGUdummy_t@_StringDetail@12@@Z`
- size: `130`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800144e0`
- `0x180015ed8`
- `0x1800160b0`

## callees

- `0x180016028`
- `0x180023298`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180016077`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180016077`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001608e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001608e`

## pseudocode

```c
__int64 __fastcall Windows::Internal::String::Initialize<unsigned short *>(HSTRING *a1, const WCHAR **a2, char a3)
{
  const WCHAR *v3; // rdi
  unsigned __int64 v5; // rcx
  HRESULT v6; // ebx
  HSTRING v7; // rcx
  HSTRING string; // [rsp+48h] [rbp+10h] BYREF
  UINT32 length; // [rsp+50h] [rbp+18h] BYREF

  LOBYTE(length) = a3;
  v3 = *a2;
  if ( *a2 )
  {
    length = 0;
    v5 = -1;
    string = 0;
    do
      ++v5;
    while ( v3[v5] );
    v6 = ULongLongToULong(v5, &length);
    if ( v6 >= 0 )
    {
      v6 = WindowsCreateString(v3, length, &string);
      if ( v6 >= 0 )
      {
        v7 = *a1;
        *a1 = string;
        WindowsDeleteString(v7);
      }
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180016028  mov     rax, rsp
0x18001602b  mov     [rax+8], rbx
0x18001602f  mov     [rax+18h], r8b
0x180016033  push    rbp
0x180016034  push    rsi
0x180016035  push    rdi
0x180016036  sub     rsp, 20h
0x18001603a  mov     rdi, [rdx]
0x18001603d  xor     ebp, ebp
0x18001603f  mov     rsi, rcx
0x180016042  test    rdi, rdi
0x180016045  jz      short loc_180016096
0x180016047  mov     [rax+18h], ebp
0x18001604a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001604e  mov     [rax+10h], rbp
0x180016052  inc     rcx; unsigned __int64
0x180016055  cmp     [rdi+rcx*2], bp
0x180016059  jnz     short loc_180016052
0x18001605b  lea     rdx, [rsp+38h+length]; unsigned int *
0x180016060  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180016065  mov     ebx, eax
0x180016067  test    eax, eax
0x180016069  js      short loc_18001609B
0x18001606b  mov     edx, [rsp+38h+length]; length
0x18001606f  lea     r8, [rsp+38h+string]; string
0x180016074  mov     rcx, rdi; sourceString
0x180016077  call    cs:__imp_WindowsCreateString
0x18001607d  mov     ebx, eax
0x18001607f  test    eax, eax
0x180016081  js      short loc_18001609B
0x180016083  mov     rax, [rsp+38h+string]
0x180016088  mov     rcx, [rsi]; string
0x18001608b  mov     [rsi], rax
0x18001608e  call    cs:__imp_WindowsDeleteString
0x180016094  jmp     short loc_18001609B
0x180016096  mov     ebx, 80004003h
0x18001609b  mov     eax, ebx
0x18001609d  mov     rbx, [rsp+38h+arg_0]
0x1800160a2  add     rsp, 20h
0x1800160a6  pop     rdi
0x1800160a7  pop     rsi
0x1800160a8  pop     rbp
0x1800160a9  retn
```
