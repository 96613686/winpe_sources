# DuplicateString(ushort const *,ushort * *)

- ea: `0x180014da0`
- end: `0x180014e6a`
- name: `?DuplicateString@@YAJPEBGPEAPEAG@Z`
- size: `202`
- prototype: `__int64 __fastcall(const unsigned __int16 *Src, unsigned __int16 **)`
- caller_count: `7`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000e008`
- `0x18000e170`
- `0x180011224`
- `0x180015234`
- `0x180015f1c`
- `0x180016eac`
- `0x180017340`

## callees

- `0x1800021c6`
- `0x18000f2d4`
- `0x180014660`
- `0x180014da0`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180014df7`
- `KERNEL32!GetProcessHeap` at `0x180014df7`
- `KERNEL32!HeapAlloc` at `0x180014e15`
- `KERNEL32!HeapAlloc` at `0x180014e15`

## string_xrefs

- `0x180014dd2`: `base\diagnosis\ra\racommon\src\stringutils.cpp`
- `0x180014e3d`: `base\diagnosis\ra\racommon\src\stringutils.cpp`

## pseudocode

```c
__int64 __fastcall DuplicateString(const unsigned __int16 *Src, unsigned __int16 **a2)
{
  signed int v4; // eax
  const struct _EVENT_DESCRIPTOR *v5; // rdx
  CEventLogger *v6; // rcx
  unsigned int v7; // ebx
  HANDLE ProcessHeap; // rax
  SIZE_T v9; // rsi
  unsigned __int16 *v10; // rax
  const struct _EVENT_DESCRIPTOR *v11; // rdx
  CEventLogger *v12; // rcx
  unsigned __int64 v14; // [rsp+70h] [rbp+18h] BYREF

  v14 = 0;
  v4 = StringCchLengthW(Src, 0x7FFFFFFFu, &v14);
  v7 = v4;
  if ( v4 >= 0 )
  {
    ProcessHeap = GetProcessHeap();
    v9 = 2 * v14 + 2;
    v10 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v9);
    *a2 = v10;
    if ( v10 )
    {
      memcpy_0(v10, Src, v9);
    }
    else
    {
      v7 = -2147024882;
      CEventLogger::LogError(
        v12,
        v11,
        L"base\\diagnosis\\ra\\racommon\\src\\stringutils.cpp",
        0xFDu,
        L"DuplicateString",
        0x8007000E);
    }
  }
  else
  {
    CEventLogger::LogError(
      v6,
      v5,
      L"base\\diagnosis\\ra\\racommon\\src\\stringutils.cpp",
      0xF5u,
      L"DuplicateString",
      v4);
    return (unsigned int)-2147024882;
  }
  return v7;
}

```

## disassembly

```asm
0x180014da0  push    rbx
0x180014da2  push    rsi
0x180014da3  push    rdi
0x180014da4  push    r14
0x180014da6  sub     rsp, 38h
0x180014daa  mov     r14, rdx
0x180014dad  mov     [rsp+58h+arg_10], 0
0x180014db6  mov     edx, 7FFFFFFFh; unsigned __int64
0x180014dbb  lea     r8, [rsp+58h+arg_10]; unsigned __int64 *
0x180014dc0  mov     rdi, rcx
0x180014dc3  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180014dc8  mov     ebx, eax
0x180014dca  test    eax, eax
0x180014dcc  jns     short loc_180014DF7
0x180014dce  mov     [rsp+58h+var_30], eax; unsigned int
0x180014dd2  lea     r8, aBaseDiagnosisR_9; "base\\diagnosis\\ra\\racommon\\src\\str"...
0x180014dd9  lea     rax, aDuplicatestrin; "DuplicateString"
0x180014de0  mov     r9d, 0F5h; unsigned int
0x180014de6  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x180014deb  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180014df0  mov     ebx, 8007000Eh
0x180014df5  jmp     short loc_180014E5E
0x180014df7  call    cs:__imp_GetProcessHeap
0x180014dfd  mov     rcx, [rsp+58h+arg_10]
0x180014e02  mov     edx, 8; dwFlags
0x180014e07  lea     rsi, ds:2[rcx*2]
0x180014e0f  mov     rcx, rax; hHeap
0x180014e12  mov     r8, rsi; dwBytes
0x180014e15  call    cs:__imp_HeapAlloc
0x180014e1b  mov     [r14], rax
0x180014e1e  test    rax, rax
0x180014e21  jnz     short loc_180014E50
0x180014e23  lea     rax, aDuplicatestrin; "DuplicateString"
0x180014e2a  mov     [rsp+58h+var_30], 8007000Eh; unsigned int
0x180014e32  mov     r9d, 0FDh; unsigned int
0x180014e38  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x180014e3d  lea     r8, aBaseDiagnosisR_9; "base\\diagnosis\\ra\\racommon\\src\\str"...
0x180014e44  mov     ebx, 8007000Eh
0x180014e49  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180014e4e  jmp     short loc_180014E5E
0x180014e50  mov     r8, rsi; Size
0x180014e53  mov     rdx, rdi; Src
0x180014e56  mov     rcx, rax; void *
0x180014e59  call    memcpy_0
0x180014e5e  mov     eax, ebx
0x180014e60  add     rsp, 38h
0x180014e64  pop     r14
0x180014e66  pop     rdi
0x180014e67  pop     rsi
0x180014e68  pop     rbx
0x180014e69  retn
```
