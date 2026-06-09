# CompressFree

- ea: `0x180001f58`
- end: `0x180001fd7`
- name: `CompressFree`
- size: `127`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001f30`
- `0x180003bd0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180001f6f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180001f8b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180001fa7`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180001fc3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180001f6f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180001f8b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180001fa7`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180001fc3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180001f65`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180001f81`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180001f9d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180001fb9`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180001f65`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180001f81`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180001f9d`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180001fb9`

## pseudocode

```c
HGLOBAL __fastcall CompressFree(HGLOBAL *a1)
{
  HGLOBAL v2; // rcx
  HGLOBAL v3; // rcx
  HGLOBAL v4; // rcx
  HGLOBAL result; // rax

  GlobalUnlock(a1[2]);
  GlobalFree(a1[2]);
  v2 = a1[4];
  a1[2] = 0;
  GlobalUnlock(v2);
  GlobalFree(a1[4]);
  v3 = a1[3];
  a1[4] = 0;
  GlobalUnlock(v3);
  GlobalFree(a1[3]);
  v4 = a1[5];
  a1[3] = 0;
  GlobalUnlock(v4);
  result = GlobalFree(a1[5]);
  a1[5] = 0;
  return result;
}

```

## disassembly

```asm
0x180001f58  push    rbx
0x180001f5a  sub     rsp, 20h
0x180001f5e  mov     rbx, rcx
0x180001f61  mov     rcx, [rcx+10h]; hMem
0x180001f65  call    cs:__imp_GlobalUnlock
0x180001f6b  mov     rcx, [rbx+10h]; hMem
0x180001f6f  call    cs:__imp_GlobalFree
0x180001f75  mov     rcx, [rbx+20h]; hMem
0x180001f79  mov     qword ptr [rbx+10h], 0
0x180001f81  call    cs:__imp_GlobalUnlock
0x180001f87  mov     rcx, [rbx+20h]; hMem
0x180001f8b  call    cs:__imp_GlobalFree
0x180001f91  mov     rcx, [rbx+18h]; hMem
0x180001f95  mov     qword ptr [rbx+20h], 0
0x180001f9d  call    cs:__imp_GlobalUnlock
0x180001fa3  mov     rcx, [rbx+18h]; hMem
0x180001fa7  call    cs:__imp_GlobalFree
0x180001fad  mov     rcx, [rbx+28h]; hMem
0x180001fb1  mov     qword ptr [rbx+18h], 0
0x180001fb9  call    cs:__imp_GlobalUnlock
0x180001fbf  mov     rcx, [rbx+28h]; hMem
0x180001fc3  call    cs:__imp_GlobalFree
0x180001fc9  mov     qword ptr [rbx+28h], 0
0x180001fd1  add     rsp, 20h
0x180001fd5  pop     rbx
0x180001fd6  retn
```
