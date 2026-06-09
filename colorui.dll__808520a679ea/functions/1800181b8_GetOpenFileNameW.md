# GetOpenFileNameW

- ea: `0x1800181b8`
- end: `0x180018226`
- name: `GetOpenFileNameW`
- size: `110`
- prototype: `BOOL __stdcall(LPOPENFILENAMEW)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d7dc`
- `0x18000f074`
- `0x180016a70`

## callees

- `0x180017c70`
- `0x1800181b8`
- `0x180018434`
- `0x180019010`

## import_xrefs

- `KERNEL32!DeactivateActCtx` at `0x180018213`
- `KERNEL32!DeactivateActCtx` at `0x180018213`

## string_xrefs

- `0x1800181d7`: `GetOpenFileNameW`

## pseudocode

```c
BOOL __stdcall GetOpenFileNameW(LPOPENFILENAMEW a1)
{
  int v2; // ebx
  ULONG_PTR ulCookie; // [rsp+38h] [rbp+10h] BYREF

  ulCookie = 0;
  v2 = 0;
  GetProcFromComDlg((HMODULE *)&qword_180021DF0, "GetOpenFileNameW");
  if ( qword_180021DF0 )
  {
    SHActivateContext(&ulCookie);
    v2 = ((__int64 (__fastcall *)(LPOPENFILENAMEW))qword_180021DF0)(a1);
    if ( ulCookie )
      DeactivateActCtx(0, ulCookie);
  }
  return v2;
}

```

## disassembly

```asm
0x1800181b8  mov     [rsp+arg_0], rbx
0x1800181bd  push    rdi
0x1800181be  sub     rsp, 20h
0x1800181c2  mov     rdi, rcx
0x1800181c5  mov     [rsp+28h+ulCookie], 0
0x1800181ce  lea     rcx, qword_180021DF0
0x1800181d5  xor     ebx, ebx
0x1800181d7  lea     rdx, aGetopenfilenam; "GetOpenFileNameW"
0x1800181de  call    _GetProcFromComDlg
0x1800181e3  cmp     cs:qword_180021DF0, rbx
0x1800181ea  jz      short loc_180018219
0x1800181ec  lea     rcx, [rsp+28h+ulCookie]
0x1800181f1  call    SHActivateContext
0x1800181f6  mov     rax, cs:qword_180021DF0
0x1800181fd  mov     rcx, rdi
0x180018200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018205  mov     rdx, [rsp+28h+ulCookie]; ulCookie
0x18001820a  mov     ebx, eax
0x18001820c  test    rdx, rdx
0x18001820f  jz      short loc_180018219
0x180018211  xor     ecx, ecx; dwFlags
0x180018213  call    cs:__imp_DeactivateActCtx
0x180018219  mov     eax, ebx
0x18001821b  mov     rbx, [rsp+28h+arg_0]
0x180018220  add     rsp, 20h
0x180018224  pop     rdi
0x180018225  retn
```
