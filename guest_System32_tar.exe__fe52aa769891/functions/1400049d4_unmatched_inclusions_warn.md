# unmatched_inclusions_warn

- ea: `0x1400049d4`
- end: `0x140004a4d`
- name: `unmatched_inclusions_warn`
- size: `121`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140001f9c`

## callees

- `0x1400049d4`
- `0x1400071a4`
- `0x140007298`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140004a33`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140004a33`
- `archiveint!archive_match_path_unmatched_inclusions_next` at `0x140004a15`
- `archiveint!archive_match_path_unmatched_inclusions_next` at `0x140004a15`
- `archiveint!archive_match_path_unmatched_inclusions` at `0x140004a27`
- `archiveint!archive_match_path_unmatched_inclusions` at `0x140004a27`

## pseudocode

```c
__int64 __fastcall unmatched_inclusions_warn(__int64 a1)
{
  __int64 v1; // rbx
  int matched; // eax
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  const char *v7; // [rsp+38h] [rbp+10h] BYREF

  v7 = 0;
  v1 = a1;
  if ( !a1 )
    return 0;
  while ( 1 )
  {
    matched = archive_match_path_unmatched_inclusions_next(a1, &v7);
    if ( matched )
      break;
    lafe_warnc(0, "%s: %s", v7, "Not found in archive");
    a1 = v1;
  }
  if ( matched == -30 )
  {
    _o__errno(v5, v4, v6);
    lafe_errc(1);
  }
  return archive_match_path_unmatched_inclusions(v1);
}

```

## disassembly

```asm
0x1400049d4  mov     [rsp+arg_8], rdx
0x1400049d9  push    rbx
0x1400049da  sub     rsp, 20h
0x1400049de  mov     [rsp+28h+arg_8], 0
0x1400049e7  mov     rbx, rcx
0x1400049ea  test    rcx, rcx
0x1400049ed  jnz     short loc_140004A10
0x1400049ef  xor     eax, eax
0x1400049f1  jmp     short loc_140004A2D
0x1400049f3  mov     r8, [rsp+28h+arg_8]
0x1400049f8  lea     r9, aNotFoundInArch; "Not found in archive"
0x1400049ff  lea     rdx, aSS_1; "%s: %s"
0x140004a06  xor     ecx, ecx
0x140004a08  call    lafe_warnc
0x140004a0d  mov     rcx, rbx
0x140004a10  lea     rdx, [rsp+28h+arg_8]
0x140004a15  call    cs:__imp_archive_match_path_unmatched_inclusions_next
0x140004a1b  test    eax, eax
0x140004a1d  jz      short loc_1400049F3
0x140004a1f  cmp     eax, 0FFFFFFE2h
0x140004a22  jz      short loc_140004A33
0x140004a24  mov     rcx, rbx
0x140004a27  call    cs:__imp_archive_match_path_unmatched_inclusions
0x140004a2d  add     rsp, 20h
0x140004a31  pop     rbx
0x140004a32  retn
0x140004a33  call    cs:__imp__o__errno
0x140004a39  lea     r8, aOutOfMemory; "Out of memory"
0x140004a40  mov     ecx, 1; Code
0x140004a45  mov     edx, [rax]
0x140004a47  call    lafe_errc
```
