# CommDlgExtendedError

- ea: `0x180017e4c`
- end: `0x180017eaf`
- name: `CommDlgExtendedError`
- size: `99`
- prototype: `DWORD __stdcall()`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000f074`
- `0x180016a70`

## callees

- `0x180017c70`
- `0x180017e4c`
- `0x180018434`
- `0x180019010`

## import_xrefs

- `KERNEL32!DeactivateActCtx` at `0x180017ea1`
- `KERNEL32!DeactivateActCtx` at `0x180017ea1`

## string_xrefs

- `0x180017e52`: `CommDlgExtendedError`

## pseudocode

```c
DWORD __stdcall CommDlgExtendedError()
{
  DWORD v0; // ebx
  ULONG_PTR ulCookie; // [rsp+30h] [rbp+8h] BYREF

  ulCookie = 0;
  v0 = 2;
  GetProcFromComDlg((HMODULE *)&qword_180021DE0, "CommDlgExtendedError");
  if ( qword_180021DE0 )
  {
    SHActivateContext(&ulCookie);
    v0 = ((__int64 (*)(void))qword_180021DE0)();
    if ( ulCookie )
      DeactivateActCtx(0, ulCookie);
  }
  return v0;
}

```

## disassembly

```asm
0x180017e4c  push    rbx
0x180017e4e  sub     rsp, 20h
0x180017e52  lea     rdx, aCommdlgextende; "CommDlgExtendedError"
0x180017e59  mov     [rsp+28h+ulCookie], 0
0x180017e62  lea     rcx, qword_180021DE0
0x180017e69  mov     ebx, 2
0x180017e6e  call    _GetProcFromComDlg
0x180017e73  cmp     cs:qword_180021DE0, 0
0x180017e7b  jz      short loc_180017EA7
0x180017e7d  lea     rcx, [rsp+28h+ulCookie]
0x180017e82  call    SHActivateContext
0x180017e87  mov     rax, cs:qword_180021DE0
0x180017e8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e93  mov     rdx, [rsp+28h+ulCookie]; ulCookie
0x180017e98  mov     ebx, eax
0x180017e9a  test    rdx, rdx
0x180017e9d  jz      short loc_180017EA7
0x180017e9f  xor     ecx, ecx; dwFlags
0x180017ea1  call    cs:__imp_DeactivateActCtx
0x180017ea7  mov     eax, ebx
0x180017ea9  add     rsp, 20h
0x180017ead  pop     rbx
0x180017eae  retn
```
