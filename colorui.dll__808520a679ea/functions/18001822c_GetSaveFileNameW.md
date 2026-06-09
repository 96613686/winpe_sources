# GetSaveFileNameW

- ea: `0x18001822c`
- end: `0x18001829a`
- name: `GetSaveFileNameW`
- size: `110`
- prototype: `BOOL __stdcall(LPOPENFILENAMEW)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000de80`

## callees

- `0x180017c70`
- `0x18001822c`
- `0x180018434`
- `0x180019010`

## import_xrefs

- `KERNEL32!DeactivateActCtx` at `0x180018287`
- `KERNEL32!DeactivateActCtx` at `0x180018287`

## pseudocode

```c
BOOL __stdcall GetSaveFileNameW(LPOPENFILENAMEW a1)
{
  int v2; // ebx
  ULONG_PTR ulCookie; // [rsp+38h] [rbp+10h] BYREF

  ulCookie = 0;
  v2 = 0;
  GetProcFromComDlg((HMODULE *)&qword_180021DE8, "GetSaveFileNameW");
  if ( qword_180021DE8 )
  {
    SHActivateContext(&ulCookie);
    v2 = ((__int64 (__fastcall *)(LPOPENFILENAMEW))qword_180021DE8)(a1);
    if ( ulCookie )
      DeactivateActCtx(0, ulCookie);
  }
  return v2;
}

```

## disassembly

```asm
0x18001822c  mov     [rsp+arg_0], rbx
0x180018231  push    rdi
0x180018232  sub     rsp, 20h
0x180018236  mov     rdi, rcx
0x180018239  mov     [rsp+28h+ulCookie], 0
0x180018242  lea     rcx, qword_180021DE8
0x180018249  xor     ebx, ebx
0x18001824b  lea     rdx, aGetsavefilenam; "GetSaveFileNameW"
0x180018252  call    _GetProcFromComDlg
0x180018257  cmp     cs:qword_180021DE8, rbx
0x18001825e  jz      short loc_18001828D
0x180018260  lea     rcx, [rsp+28h+ulCookie]
0x180018265  call    SHActivateContext
0x18001826a  mov     rax, cs:qword_180021DE8
0x180018271  mov     rcx, rdi
0x180018274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018279  mov     rdx, [rsp+28h+ulCookie]; ulCookie
0x18001827e  mov     ebx, eax
0x180018280  test    rdx, rdx
0x180018283  jz      short loc_18001828D
0x180018285  xor     ecx, ecx; dwFlags
0x180018287  call    cs:__imp_DeactivateActCtx
0x18001828d  mov     eax, ebx
0x18001828f  mov     rbx, [rsp+28h+arg_0]
0x180018294  add     rsp, 20h
0x180018298  pop     rdi
0x180018299  retn
```
