# GetOpenFileNameW

- ea: `0x18001c930`
- end: `0x18001c99e`
- name: `GetOpenFileNameW`
- size: `110`
- prototype: `BOOL __stdcall(LPOPENFILENAMEW)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000d4d0`

## callees

- `0x18001c0c4`
- `0x18001c930`
- `0x18001cc60`
- `0x18001f010`

## import_xrefs

- `KERNEL32!DeactivateActCtx` at `0x18001c98b`
- `KERNEL32!DeactivateActCtx` at `0x18001c98b`

## string_xrefs

- `0x18001c94f`: `GetOpenFileNameW`

## pseudocode

```c
BOOL __stdcall GetOpenFileNameW(LPOPENFILENAMEW a1)
{
  int v2; // ebx
  ULONG_PTR ulCookie; // [rsp+38h] [rbp+10h] BYREF

  ulCookie = 0;
  v2 = 0;
  GetProcFromComDlg((HMODULE *)&qword_180028658, "GetOpenFileNameW");
  if ( qword_180028658 )
  {
    SHActivateContext(&ulCookie);
    v2 = ((__int64 (__fastcall *)(LPOPENFILENAMEW))qword_180028658)(a1);
    if ( ulCookie )
      DeactivateActCtx(0, ulCookie);
  }
  return v2;
}

```

## disassembly

```asm
0x18001c930  mov     [rsp+arg_0], rbx
0x18001c935  push    rdi
0x18001c936  sub     rsp, 20h
0x18001c93a  mov     rdi, rcx
0x18001c93d  mov     [rsp+28h+ulCookie], 0
0x18001c946  lea     rcx, qword_180028658
0x18001c94d  xor     ebx, ebx
0x18001c94f  lea     rdx, aGetopenfilenam; "GetOpenFileNameW"
0x18001c956  call    _GetProcFromComDlg
0x18001c95b  cmp     cs:qword_180028658, rbx
0x18001c962  jz      short loc_18001C991
0x18001c964  lea     rcx, [rsp+28h+ulCookie]
0x18001c969  call    SHActivateContext
0x18001c96e  mov     rax, cs:qword_180028658
0x18001c975  mov     rcx, rdi
0x18001c978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c97d  mov     rdx, [rsp+28h+ulCookie]; ulCookie
0x18001c982  mov     ebx, eax
0x18001c984  test    rdx, rdx
0x18001c987  jz      short loc_18001C991
0x18001c989  xor     ecx, ecx; dwFlags
0x18001c98b  call    cs:__imp_DeactivateActCtx
0x18001c991  mov     eax, ebx
0x18001c993  mov     rbx, [rsp+28h+arg_0]
0x18001c998  add     rsp, 20h
0x18001c99c  pop     rdi
0x18001c99d  retn
```
