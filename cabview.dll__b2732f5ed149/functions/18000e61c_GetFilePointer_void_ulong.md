# GetFilePointer(void *,ulong *)

- ea: `0x18000e61c`
- end: `0x18000e654`
- name: `?GetFilePointer@@YAHPEAXPEAK@Z`
- size: `56`
- prototype: `__int64 __fastcall(void *, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000d53c`
- `0x18000d724`

## callees

- `0x18000e61c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000e636`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x18000e636`

## pseudocode

```c
__int64 __fastcall GetFilePointer(void *a1, unsigned int *a2)
{
  unsigned int v3; // ebx
  DWORD v4; // eax

  v3 = 1;
  v4 = SetFilePointer(a1, 0, 0, 1u);
  if ( v4 == -1 )
    return 0;
  else
    *a2 = v4;
  return v3;
}

```

## disassembly

```asm
0x18000e61c  mov     [rsp+arg_0], rbx
0x18000e621  push    rdi
0x18000e622  sub     rsp, 20h
0x18000e626  mov     rdi, rdx
0x18000e629  mov     ebx, 1
0x18000e62e  mov     r9d, ebx; dwMoveMethod
0x18000e631  xor     r8d, r8d; lpDistanceToMoveHigh
0x18000e634  xor     edx, edx; lDistanceToMove
0x18000e636  call    cs:__imp_SetFilePointer
0x18000e63c  cmp     eax, 0FFFFFFFFh
0x18000e63f  jz      short loc_18000E645
0x18000e641  mov     [rdi], eax
0x18000e643  jmp     short loc_18000E647
0x18000e645  xor     ebx, ebx
0x18000e647  mov     eax, ebx
0x18000e649  mov     rbx, [rsp+28h+arg_0]
0x18000e64e  add     rsp, 20h
0x18000e652  pop     rdi
0x18000e653  retn
```
