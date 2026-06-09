# CheckSyncObject(ushort const *)

- ea: `0x180045bac`
- end: `0x180045bdc`
- name: `?CheckSyncObject@@YA_NPEBG@Z`
- size: `48`
- prototype: `bool __fastcall(LPCWSTR lpName)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180045e70`

## callees

- `0x180045bac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x180045bbe`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x180045bbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045bce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180045bce`

## pseudocode

```c
char __fastcall CheckSyncObject(LPCWSTR lpName)
{
  char v1; // bl
  HANDLE v2; // rax

  v1 = 0;
  v2 = OpenMutexW(0x100000u, 0, lpName);
  if ( v2 )
  {
    v1 = 1;
    CloseHandle(v2);
  }
  return v1;
}

```

## disassembly

```asm
0x180045bac  push    rbx
0x180045bae  sub     rsp, 20h
0x180045bb2  mov     r8, rcx; lpName
0x180045bb5  xor     edx, edx; bInheritHandle
0x180045bb7  mov     ecx, 100000h; dwDesiredAccess
0x180045bbc  xor     bl, bl
0x180045bbe  call    cs:__imp_OpenMutexW
0x180045bc4  test    rax, rax
0x180045bc7  jz      short loc_180045BD4
0x180045bc9  mov     rcx, rax; hObject
0x180045bcc  mov     bl, 1
0x180045bce  call    cs:__imp_CloseHandle
0x180045bd4  mov     al, bl
0x180045bd6  add     rsp, 20h
0x180045bda  pop     rbx
0x180045bdb  retn
```
