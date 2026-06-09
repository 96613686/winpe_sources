# FwBuildIndirectString

- ea: `0x18001f990`
- end: `0x18001fa07`
- name: `FwBuildIndirectString`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18002c310`

## callees

- `0x180002c10`
- `0x1800047e0`
- `0x18001e1d0`
- `0x18001f990`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ultow` at `0x18001f9b3`
- `api-ms-win-crt-private-l1-1-0!_o__ultow` at `0x18001f9b3`

## string_xrefs

- `0x18001f9bc`: `@FirewallAPI.dll,-`

## pseudocode

```c
__int64 __fastcall FwBuildIndirectString(unsigned int a1, __int64 a2)
{
  wchar_t *v3; // rax
  int v4; // eax
  int v5; // r8d
  unsigned int v6; // ebx
  int v7; // r8d
  wchar_t Buffer[12]; // [rsp+20h] [rbp-28h] BYREF

  v3 = _ultow(a1, Buffer, 10);
  v4 = FwStringBuild(a2, L"@FirewallAPI.dll,-", v3, 0);
  v6 = v4;
  if ( v4 < 0 )
  {
    FwReportReturnError((int)"FwBuildIndirectString", (unsigned int)v4, v5);
    return (unsigned int)FwReportReturnError((int)"FwBuildIndirectString", v6, v7);
  }
  return v6;
}

```

## disassembly

```asm
0x18001f990  push    rbx
0x18001f992  sub     rsp, 40h
0x18001f996  mov     rax, cs:__security_cookie
0x18001f99d  xor     rax, rsp
0x18001f9a0  mov     [rsp+48h+var_10], rax
0x18001f9a5  mov     rbx, rdx
0x18001f9a8  mov     r8d, 0Ah; Radix
0x18001f9ae  lea     rdx, [rsp+48h+Buffer]; Buffer
0x18001f9b3  call    cs:__imp__ultow
0x18001f9b9  xor     r9d, r9d
0x18001f9bc  lea     rdx, aFirewallapiDll_0; "@FirewallAPI.dll,-"
0x18001f9c3  mov     r8, rax
0x18001f9c6  mov     rcx, rbx
0x18001f9c9  call    FwStringBuild
0x18001f9ce  mov     ebx, eax
0x18001f9d0  test    eax, eax
0x18001f9d2  jns     short loc_18001F9F2
0x18001f9d4  mov     edx, eax
0x18001f9d6  lea     rcx, aFwbuildindirec_0; "FwBuildIndirectString"
0x18001f9dd  call    FwReportReturnError
0x18001f9e2  mov     edx, ebx
0x18001f9e4  lea     rcx, aFwbuildindirec_0; "FwBuildIndirectString"
0x18001f9eb  call    FwReportReturnError
0x18001f9f0  mov     ebx, eax
0x18001f9f2  mov     eax, ebx
0x18001f9f4  mov     rcx, [rsp+48h+var_10]
0x18001f9f9  xor     rcx, rsp; StackCookie
0x18001f9fc  call    __security_check_cookie
0x18001fa01  add     rsp, 40h
0x18001fa05  pop     rbx
0x18001fa06  retn
```
