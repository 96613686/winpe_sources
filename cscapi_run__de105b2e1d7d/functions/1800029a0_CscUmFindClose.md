# CscUmFindClose

- ea: `0x1800029a0`
- end: `0x180002a0c`
- name: `CscUmFindClose`
- size: `108`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `4`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180001020`
- `0x1800016b0`
- `0x180002080`
- `0x180002820`

## callees

- `0x1800029a0`
- `0x180002a20`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800029e5`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800029fe`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800029e5`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800029fe`
- `ntdll!NtClose` at `0x1800029d6`
- `ntdll!NtClose` at `0x1800029d6`
- `ntdll!RtlFreeUnicodeString` at `0x1800029ef`
- `ntdll!RtlFreeUnicodeString` at `0x1800029ef`

## pseudocode

```c
__int64 __fastcall CscUmFindClose(struct _UNICODE_STRING *hMem)
{
  __int64 v3; // rcx
  void *v4; // rcx
  PWSTR Buffer; // rcx

  if ( !CscUmpLibraryState )
    return 3221225860LL;
  if ( !(unsigned __int8)IsValidCscEnumHandle() )
    return 3221225485LL;
  v4 = *(void **)(v3 + 8);
  if ( v4 )
    NtClose(v4);
  Buffer = hMem[2].Buffer;
  if ( Buffer )
    LocalFree(Buffer);
  RtlFreeUnicodeString(hMem + 1);
  *(_DWORD *)&hMem->Length = 0;
  LocalFree(hMem);
  return 0;
}

```

## disassembly

```asm
0x1800029a0  push    rbx
0x1800029a2  sub     rsp, 20h
0x1800029a6  cmp     cs:CscUmpLibraryState, 0
0x1800029ad  mov     rbx, rcx
0x1800029b0  jnz     short loc_1800029BD
0x1800029b2  mov     eax, 0C0000184h
0x1800029b7  add     rsp, 20h
0x1800029bb  pop     rbx
0x1800029bc  retn
0x1800029bd  call    IsValidCscEnumHandle
0x1800029c2  test    al, al
0x1800029c4  jnz     short loc_1800029CD
0x1800029c6  mov     eax, 0C000000Dh
0x1800029cb  jmp     short loc_180002A06
0x1800029cd  mov     rcx, [rcx+8]; Handle
0x1800029d1  test    rcx, rcx
0x1800029d4  jz      short loc_1800029DC
0x1800029d6  call    cs:__imp_NtClose
0x1800029dc  mov     rcx, [rbx+28h]; hMem
0x1800029e0  test    rcx, rcx
0x1800029e3  jz      short loc_1800029EB
0x1800029e5  call    cs:__imp_LocalFree
0x1800029eb  lea     rcx, [rbx+10h]; UnicodeString
0x1800029ef  call    cs:__imp_RtlFreeUnicodeString
0x1800029f5  mov     rcx, rbx; hMem
0x1800029f8  mov     dword ptr [rbx], 0
0x1800029fe  call    cs:__imp_LocalFree
0x180002a04  xor     eax, eax
0x180002a06  add     rsp, 20h
0x180002a0a  pop     rbx
0x180002a0b  retn
```
