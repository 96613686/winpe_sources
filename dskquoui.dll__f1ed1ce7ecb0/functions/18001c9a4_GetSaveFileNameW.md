# GetSaveFileNameW

- ea: `0x18001c9a4`
- end: `0x18001ca12`
- name: `GetSaveFileNameW`
- size: `110`
- prototype: `BOOL __stdcall(LPOPENFILENAMEW)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d138`

## callees

- `0x18001c0c4`
- `0x18001c9a4`
- `0x18001cc60`
- `0x18001f010`

## import_xrefs

- `KERNEL32!DeactivateActCtx` at `0x18001c9ff`
- `KERNEL32!DeactivateActCtx` at `0x18001c9ff`

## pseudocode

```c
BOOL __stdcall GetSaveFileNameW(LPOPENFILENAMEW a1)
{
  int v2; // ebx
  ULONG_PTR ulCookie; // [rsp+38h] [rbp+10h] BYREF

  ulCookie = 0;
  v2 = 0;
  GetProcFromComDlg((HMODULE *)&qword_180028650, "GetSaveFileNameW");
  if ( qword_180028650 )
  {
    SHActivateContext(&ulCookie);
    v2 = ((__int64 (__fastcall *)(LPOPENFILENAMEW))qword_180028650)(a1);
    if ( ulCookie )
      DeactivateActCtx(0, ulCookie);
  }
  return v2;
}

```

## disassembly

```asm
0x18001c9a4  mov     [rsp+arg_0], rbx
0x18001c9a9  push    rdi
0x18001c9aa  sub     rsp, 20h
0x18001c9ae  mov     rdi, rcx
0x18001c9b1  mov     [rsp+28h+ulCookie], 0
0x18001c9ba  lea     rcx, qword_180028650
0x18001c9c1  xor     ebx, ebx
0x18001c9c3  lea     rdx, aGetsavefilenam; "GetSaveFileNameW"
0x18001c9ca  call    _GetProcFromComDlg
0x18001c9cf  cmp     cs:qword_180028650, rbx
0x18001c9d6  jz      short loc_18001CA05
0x18001c9d8  lea     rcx, [rsp+28h+ulCookie]
0x18001c9dd  call    SHActivateContext
0x18001c9e2  mov     rax, cs:qword_180028650
0x18001c9e9  mov     rcx, rdi
0x18001c9ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c9f1  mov     rdx, [rsp+28h+ulCookie]; ulCookie
0x18001c9f6  mov     ebx, eax
0x18001c9f8  test    rdx, rdx
0x18001c9fb  jz      short loc_18001CA05
0x18001c9fd  xor     ecx, ecx; dwFlags
0x18001c9ff  call    cs:__imp_DeactivateActCtx
0x18001ca05  mov     eax, ebx
0x18001ca07  mov     rbx, [rsp+28h+arg_0]
0x18001ca0c  add     rsp, 20h
0x18001ca10  pop     rdi
0x18001ca11  retn
```
