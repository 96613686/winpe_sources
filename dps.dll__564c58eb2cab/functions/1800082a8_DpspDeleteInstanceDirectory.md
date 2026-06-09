# DpspDeleteInstanceDirectory

- ea: `0x1800082a8`
- end: `0x180008321`
- name: `DpspDeleteInstanceDirectory`
- size: `121`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct _GUID *, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180015918`
- `0x180015b84`

## callees

- `0x1800080c8`
- `0x1800082a8`
- `0x180009090`
- `0x180009fb0`
- `0x180015740`

## string_xrefs

- `0x1800082e1`: `DpspDeleteInstanceDirectory`

## pseudocode

```c
__int64 __fastcall DpspDeleteInstanceDirectory(
        const struct _GUID *a1,
        const struct _GUID *a2,
        __int64 a3,
        unsigned int a4)
{
  int Args; // eax
  unsigned int v5; // ebx
  unsigned __int16 v7[264]; // [rsp+30h] [rbp-228h] BYREF

  Args = DpspGetInstanceDirectory(a1, a2, v7, a4);
  v5 = Args;
  if ( Args >= 0 )
    DpspDeleteDirectory(v7);
  else
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsdataret.cpp",
      (int)L"DpspDeleteInstanceDirectory",
      440,
      (int)L"Error = %d",
      Args);
  return v5;
}

```

## disassembly

```asm
0x1800082a8  push    rbx
0x1800082aa  sub     rsp, 250h
0x1800082b1  mov     rax, cs:__security_cookie
0x1800082b8  xor     rax, rsp
0x1800082bb  mov     [rsp+258h+var_18], rax
0x1800082c3  lea     r8, [rsp+258h+var_228]; unsigned __int16 *
0x1800082c8  call    ?DpspGetInstanceDirectory@@YAJPEBU_GUID@@0PEAGK@Z; DpspGetInstanceDirectory(_GUID const *,_GUID const *,ushort *,ulong)
0x1800082cd  mov     ebx, eax
0x1800082cf  test    eax, eax
0x1800082d1  jns     short loc_1800082FC
0x1800082d3  movzx   ecx, bx
0x1800082d6  lea     r9, aErrorD; "Error = %d"
0x1800082dd  mov     dword ptr [rsp+258h+Args], ecx; Args
0x1800082e1  lea     rdx, aDpspdeleteinst; "DpspDeleteInstanceDirectory"
0x1800082e8  lea     rcx, aClientcoreBase_1; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800082ef  mov     r8d, 1B8h; int
0x1800082f5  call    WdipTraceError
0x1800082fa  jmp     short loc_180008306
0x1800082fc  lea     rcx, [rsp+258h+var_228]
0x180008301  call    DpspDeleteDirectory
0x180008306  mov     eax, ebx
0x180008308  mov     rcx, [rsp+258h+var_18]
0x180008310  xor     rcx, rsp; StackCookie
0x180008313  call    __security_check_cookie
0x180008318  add     rsp, 250h
0x18000831f  pop     rbx
0x180008320  retn
```
