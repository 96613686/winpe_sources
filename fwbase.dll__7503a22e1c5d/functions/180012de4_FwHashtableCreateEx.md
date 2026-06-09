# FwHashtableCreateEx

- ea: `0x180012de4`
- end: `0x180012e5a`
- name: `FwHashtableCreateEx`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180012da0`

## callees

- `0x180004750`
- `0x1800047e0`
- `0x180012de4`
- `0x18001e1d0`

## import_xrefs

- `ntdll!RtlCreateHashTable` at `0x180012e0a`
- `ntdll!RtlCreateHashTable` at `0x180012e0a`

## string_xrefs

- `0x180012e2f`: `RtlCreateHashTable`
- `0x180012e36`: `FwHashtableCreateEx`
- `0x180012e4a`: `FwHashtableCreateEx`

## pseudocode

```c
__int64 __fastcall FwHashtableCreateEx(__int64 a1, __int64 a2)
{
  unsigned int v2; // ebx
  int v4; // eax
  __int64 v5; // [rsp+20h] [rbp-18h] BYREF

  v5 = a2;
  v2 = 0;
  if ( !(unsigned __int8)RtlCreateHashTable(&v5, 0, 0) )
  {
    v4 = FwReportErrorAsWinError("FwHashtableCreateEx", "RtlCreateHashTable", 8);
    v2 = v4;
    if ( v4 < 0 )
      return (unsigned int)FwReportReturnError("FwHashtableCreateEx", (unsigned int)v4);
  }
  return v2;
}

```

## disassembly

```asm
0x180012de4  push    rbx
0x180012de6  sub     rsp, 30h
0x180012dea  mov     rax, cs:__security_cookie
0x180012df1  xor     rax, rsp
0x180012df4  mov     [rsp+38h+var_10], rax
0x180012df9  mov     [rsp+38h+var_18], rdx
0x180012dfe  lea     rcx, [rsp+38h+var_18]
0x180012e03  xor     edx, edx
0x180012e05  xor     r8d, r8d
0x180012e08  xor     ebx, ebx
0x180012e0a  call    cs:__imp_RtlCreateHashTable
0x180012e10  test    al, al
0x180012e12  jz      short loc_180012E29
0x180012e14  mov     eax, ebx
0x180012e16  mov     rcx, [rsp+38h+var_10]
0x180012e1b  xor     rcx, rsp; StackCookie
0x180012e1e  call    __security_check_cookie
0x180012e23  add     rsp, 30h
0x180012e27  pop     rbx
0x180012e28  retn
0x180012e29  mov     r8d, 8
0x180012e2f  lea     rdx, aRtlcreatehasht; "RtlCreateHashTable"
0x180012e36  lea     rcx, aFwhashtablecre_1; "FwHashtableCreateEx"
0x180012e3d  call    FwReportErrorAsWinError
0x180012e42  mov     ebx, eax
0x180012e44  test    eax, eax
0x180012e46  jns     short loc_180012E14
0x180012e48  mov     edx, eax
0x180012e4a  lea     rcx, aFwhashtablecre_1; "FwHashtableCreateEx"
0x180012e51  call    FwReportReturnError
0x180012e56  mov     ebx, eax
0x180012e58  jmp     short loc_180012E14
```
