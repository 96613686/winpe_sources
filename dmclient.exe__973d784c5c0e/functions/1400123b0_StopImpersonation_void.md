# StopImpersonation(void *)

- ea: `0x1400123b0`
- end: `0x140012402`
- name: `?StopImpersonation@@YAJPEAX@Z`
- size: `82`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000c928`

## callees

- `0x1400123b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400123de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400123de`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400123be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400123be`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1400123ce`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1400123ce`

## pseudocode

```c
__int64 __fastcall StopImpersonation(void *a1)
{
  unsigned int v1; // ebx
  signed int LastError; // eax

  v1 = 0;
  if ( a1 != (void *)-1LL && (!CloseHandle(a1) || !RevertToSelf()) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v1;
}

```

## disassembly

```asm
0x1400123b0  push    rbx
0x1400123b2  sub     rsp, 20h
0x1400123b6  xor     ebx, ebx
0x1400123b8  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400123bc  jz      short loc_1400123F9
0x1400123be  call    cs:__imp_CloseHandle
0x1400123c5  nop     dword ptr [rax+rax+00h]
0x1400123ca  test    eax, eax
0x1400123cc  jz      short loc_1400123DE
0x1400123ce  call    cs:__imp_RevertToSelf
0x1400123d5  nop     dword ptr [rax+rax+00h]
0x1400123da  test    eax, eax
0x1400123dc  jnz     short loc_1400123F9
0x1400123de  call    cs:__imp_GetLastError
0x1400123e5  nop     dword ptr [rax+rax+00h]
0x1400123ea  mov     ebx, eax
0x1400123ec  test    eax, eax
0x1400123ee  jle     short loc_1400123F9
0x1400123f0  movzx   ebx, ax
0x1400123f3  or      ebx, 80070000h
0x1400123f9  mov     eax, ebx
0x1400123fb  add     rsp, 20h
0x1400123ff  pop     rbx
0x140012400  retn
```
